---
title: Tareas en Sales Qualifier
description: Aprenda a procesar tareas de alcance manuales y a revisar los posibles clientes sugeridos por el agente en la cola de tareas de Sales Qualifier.
feature: Agentic AI, Sales Insights, Account Journeys
role: User
TQID: 'https://experienceleague.adobe.com/MbTN1r-ARrW-XYtdIS-KZT7K1Lk-B3GihT8iXL60GrQ'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8573d3891d5c8ec8a05637f160f120f933b0ec61
workflow-type: tm+mt
source-wordcount: 900
ht-degree: 0%

---


# Tareas

Use **[!UICONTROL Tareas]** para completar las acciones generadas por los flujos de trabajo salientes. Seleccione una tarea, tome medidas, márquela como completada y continúe a la siguiente tarea sin abandonar la página.

En el panel de navegación izquierdo, vaya a **[!UICONTROL Actividades]** > **[!UICONTROL Tareas]**.

## Vistas de tareas

La página tiene dos pestañas:

* **[!UICONTROL Tareas manuales]**: llamadas telefónicas, LinkedIn InMails y revisiones de correo electrónico para los posibles clientes inscritos en un flujo de trabajo saliente.
* **[!UICONTROL Sugerencias del agente]**: clientes potenciales que coinciden con los criterios de direccionamiento de un flujo de trabajo saliente y que se recomiendan para la inscripción.

Cada pestaña tiene sus propios filtros, opciones de ordenación y diseño de dos paneles. La lista de tareas aparece a la izquierda y el panel de trabajo a la derecha. Al seleccionar una tarea, se cargan sus detalles en el panel de trabajo. Al completar una tarea, la siguiente tarea se selecciona automáticamente.

## Tareas manuales

### Tipos de tareas

Las tareas manuales están vinculadas a los pasos del flujo de trabajo saliente y se presentan en tres tipos:

* **[!UICONTROL Llamada telefónica]**: se crea cuando una cadencia alcanza un paso de llamada telefónica. El panel de trabajo muestra el número de teléfono del cliente potencial y, cuando está disponible, un script de llamada generado por IA.

* **[!UICONTROL LinkedIn In InMail]**: se crea cuando una cadencia alcanza un paso de LinkedIn In InMail. El panel de trabajo muestra el contenido que se copia y envía desde LinkedIn. Expanda **[!UICONTROL Motivo de IA]** para revisar el motivo.

* **[!UICONTROL Revisión de correo electrónico]**: Creada después de que Sales Qualifier genere los correos electrónicos personalizados de un cliente potencial. Seleccione **[!UICONTROL Revisar correos electrónicos]** para revisar y aprobar los borradores antes de que comience el alcance. Ver [Revisar y perfeccionar los correos electrónicos generados](outbound-workflows.md#review-and-refine-generated-emails).

### El panel de trabajo

Para una tarea de **[!UICONTROL Phone Call]** o **[!UICONTROL LinkedIn In InMail]**, el panel de trabajo contiene:

* **[!UICONTROL Cliente potencial]**: el nombre, el vínculo de correo electrónico y el número de teléfono del posible cliente, cuando corresponda.
* **[!UICONTROL Flujo de trabajo saliente]**: el nombre del flujo de trabajo saliente vinculado, la fecha de vencimiento y el indicador de omisión automática, cuando corresponda.
* **Contenido de tarea**: el script de llamada o el contenido de InMail.
* **[!UICONTROL Notas]**: las notas se guardan automáticamente al seleccionar otra tarea. No puede editar notas después de completar, omitir o cancelar una tarea.

### Generación de un script de llamada

Para una tarea de **[!UICONTROL Llamada telefónica]**, seleccione **[!UICONTROL Generar script para la llamada]**. Cuando finalice la generación, seleccione **[!UICONTROL Ver script de llamada detallado]**. Si la generación falla, inténtelo de nuevo desde el panel.

### Acciones de tarea

Hay dos acciones disponibles en el encabezado del panel de trabajo:

* **[!UICONTROL Marcar como completado]**: utilice esta acción después de realizar la llamada, enviar el mensaje de correo electrónico o revisar los mensajes de correo electrónico. La cola avanza a la siguiente tarea.
* **[!UICONTROL Omitir]**: utilice esta acción cuando no pueda completar el paso pero desee mantener al cliente prospecto en el flujo de trabajo saliente. El cliente potencial avanza al siguiente paso de cadencia.

Las tareas de llamada telefónica y LinkedIn In InMail se pueden omitir automáticamente si permanecen abiertas más allá del umbral configurado. Una omisión automática hace avanzar al posible cliente a través de la cadencia y no afecta a los puntos de contacto de correo electrónico programados.

### Filtrar, buscar y ordenar

La barra de herramientas situada encima de la lista controla qué tareas aparecen y en qué orden. Las opciones de filtro y ordenación se guardan y se vuelven a aplicar la próxima vez que abra la página.

* **[!UICONTROL Filtro]**—Abra el panel de filtros:
  * **[!UICONTROL Estado]**—**[!UICONTROL Actual]**, **[!UICONTROL Próximo]**, **[!UICONTROL Vencido]**, **[!UICONTROL Completado]**, **[!UICONTROL Cancelado]**, **[!UICONTROL Omitido]**.
  * **[!UICONTROL Tipo de tarea]**—**[!UICONTROL Revisión de correo electrónico]**, **[!UICONTROL LinkedIn In InMail]**, **[!UICONTROL Llamada telefónica]**.
  * **[!UICONTROL Fecha de vencimiento]**.
  * **[!UICONTROL Flujo de trabajo saliente]**: una lista de los flujos de trabajo salientes en la que se pueden buscar.
* **[!UICONTROL Ordenar]**: ordena por fecha de vencimiento o fecha de creación. El criterio de ordenación también determina el orden en que avanza la cola.
* **[!UICONTROL Buscar tareas]**: busque tareas por nombre de cliente potencial, nombre de empresa o flujo de trabajo saliente. La búsqueda se aplica con filtros activos.

Los filtros activos aparecen como chips debajo de la barra de herramientas. Seleccione **[!UICONTROL Borrar todo]** para restablecerlos.

### Estado de tarea

Cada tarea muestra su estado actual:

| Estado | Descripción |
| --- | --- |
| **[!UICONTROL Actual]** | Vence ahora y listo para actuar. Las tareas actuales no muestran distintivo. |
| **[!UICONTROL Próximamente]** | El paso anterior se ha completado, pero la fecha de vencimiento es futura. Puedes actuar temprano si el momento es el adecuado. |
| **[!UICONTROL Vencido]** | Después de la fecha límite y aún no se ha completado. La tarea se marca para su atención. |
| **[!UICONTROL Completado]** | Ha completado la acción y ha marcado la tarea como completada. |
| **[!UICONTROL Omitido]** | Ha omitido el paso o se ha omitido automáticamente. El cliente potencial avanza en el flujo de trabajo saliente. |
| **[!UICONTROL Cancelado]** | El sistema ha cancelado la tarea debido a un cambio en el flujo de trabajo saliente. |

Las tareas completadas, omitidas y canceladas son finales. Sus acciones ya no están disponibles y sus notas son de solo lectura.

## Sugerencias del agente

La pestaña **[!UICONTROL Sugerencias del agente]** enumera los posibles clientes que coinciden con los criterios de segmentación de un flujo de trabajo saliente y se recomiendan para la inscripción. Para activar las recomendaciones, consulte [Flujos de trabajo salientes](outbound-workflows.md).

Seleccione una sugerencia para revisarla en el panel de trabajo:

* Un distintivo de actualización marca cada sugerencia como **[!UICONTROL Nueva]** o **[!UICONTROL Anterior]**.
* La tabla **[!UICONTROL Contactos recomendados]** o **[!UICONTROL Contactos recomendados]** enumera los posibles clientes propuestos con columnas para **[!UICONTROL Nombre]**, **[!UICONTROL Título]**, **[!UICONTROL Cuenta]**, **[!UICONTROL Estado]**, **[!UICONTROL Correo electrónico]** y **[!UICONTROL Última actualización]**.

Hay dos acciones disponibles:

* **[!UICONTROL Revisar clientes potenciales]**: abra el flujo de trabajo saliente para revisar e inscribir a los clientes potenciales recomendados. Ver [Agregar clientes potenciales e iniciar la generación de correo electrónico](outbound-workflows.md#step-5-add-prospects-and-start-email-generation).
* **[!UICONTROL Marcar como completado]**: descarte la sugerencia después de revisarla.

La ficha **[!UICONTROL Sugerencias del agente]** incluye los filtros de estado **[!UICONTROL Actual]**, **[!UICONTROL Completado]** y **[!UICONTROL Cancelado]**, un filtro de flujo de trabajo saliente y la ordenación por fecha de creación.

## Completar tareas desde un flujo de trabajo saliente

En la vista **[!UICONTROL Clientes potenciales comprometidos]** de un flujo de trabajo saliente, un punto de contacto manual proporciona las mismas opciones de **[!UICONTROL Marcar como completado]**, **[!UICONTROL Omitir]** y notas. Al completar una tarea, también se actualiza su estado en la página **[!UICONTROL Tareas]**. Ver [Flujos de trabajo salientes](outbound-workflows.md).

## Estados vacíos

* Cuando no tiene tareas en las que actuar, la lista muestra un mensaje _Se ha puesto al día con respecto al mensaje de hoy_.
* Cuando los filtros no coinciden con ninguna tarea, la lista indica que ninguna tarea coincide con los filtros.
* Cuando no se selecciona ninguna tarea, el panel de trabajo le solicita que seleccione una tarea para ver sus detalles.

>[!MORELIKETHIS]
>
>* [Flujos de trabajo salientes](outbound-workflows.md)
>* [Rendimiento de salida](performance.md)
>* [Clientes potenciales](prospects.md)
