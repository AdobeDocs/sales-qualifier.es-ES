---
title: Clientes potenciales en Sales Qualifier
description: Aprenda a crear, filtrar y revisar su lista de clientes potenciales en Sales Qualifier para priorizar el alcance.
feature: Agentic AI, Sales Insights, Account Journeys
role: User
TQID: 'https://experienceleague.adobe.com/zf2H5rq1JlIT26LqLPMrm2Mq3tSIrLOiTEw6BXb1w2U'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 08dd05e1d13b501d43d457e6217a43aaabdb1d0d
workflow-type: tm+mt
source-wordcount: 535
ht-degree: 2%

---


# Clientes potenciales

Seleccione **[!UICONTROL Clientes potenciales]** en el panel de navegación izquierdo para ver los posibles clientes y contactos a los que puede acceder. Utilice la lista para revisar el estado y la actividad más reciente de cada posible cliente.

![Tabla de clientes potenciales que muestra el estado del posible cliente y la última actividad para la administración de clientes potenciales](./assets/prospects.png){width="800" zoomable="yes"}

* **[!UICONTROL Posibles clientes]**: posibles clientes asignados a usted en el CRM conectado.
* **[!UICONTROL Contactos]**: contactos asignados a usted en el CRM conectado.
* **[!UICONTROL Lista de personas]**: clientes potenciales que se importan o agregan manualmente.

## Crear su lista de clientes potenciales

La lista de clientes potenciales combina personas de más de una fuente:

* **clientes potenciales de CRM**: Sales Qualifier importa automáticamente los posibles clientes y contactos asignados al usuario conectado. Consulte [Integraciones](integrations.md).
* **Clientes potenciales importados**: clientes potenciales importados desde un archivo CSV.
* **Perspectivas agregadas manualmente**: Perspectivas individuales agregadas en Sales Qualifier.

Para agregar clientes potenciales que no provienen de su CRM:

1. En la página **[!UICONTROL Posibles clientes]**, seleccione **[!UICONTROL Lista de personas]**.
1. Seleccione **[!UICONTROL + Agregar personas]**, luego seleccione **[!UICONTROL Importar CSV]** o **[!UICONTROL Agregar persona]**.

   * Para una importación de CSV, cargue un CSV en formato `firstname,email`.
     El nombre y el correo electrónico son obligatorios. El apellido es opcional. La plantilla CSV no incluye la columna ID de posible cliente de CRM, pero puede agregar la columna y sus valores al archivo antes de la importación. Si la importación falla, revise el mensaje de error de los campos o valores para corregirlos y, a continuación, cargue el archivo de nuevo.
   * Para añadir a una persona manualmente, introduzca sus detalles en el formulario.

1. Seleccione **[!UICONTROL Guardar]**.

## Filtrado y búsqueda de clientes potenciales

Seleccione **[!UICONTROL Filter]** para reducir la lista. Puede filtrar por:

* Estado del plan de participación
* Creado por
* Cargo
* cuenta
* Origen
* Última actualización

Los administradores también pueden hacer que los campos CRM asignados estén disponibles como filtros. En **[!UICONTROL Configuración de administración]**, active **[!UICONTROL Filtrable]** para cada campo que los representantes utilicen para encontrar posibles clientes. Ver [Asignar campos CRM](integrations.md#map-crm-fields-inbound-mapping).

En **[!UICONTROL Mis contactos de oportunidad]**, también puede filtrar contactos por campos de sus oportunidades asociadas, como escenario, tipo y fecha de cierre. Los campos de oportunidad tienen etiquetas como **[!UICONTROL Stage (Opportunity)]**, que los distingue de los campos de contacto. El administrador controla qué campos de oportunidad están disponibles como filtros.

### Filtrar por participación de Marketo

Busque y dé prioridad a los posibles clientes por su participación de [!DNL Marketo] en directo, como aperturas y clics de correos electrónicos, visitas web, rellenos de formularios y momentos interesantes. El compromiso aparece en tiempo casi real, a medida que sucede.

Para filtrar posibles clientes por participación de Marketo:

1. Seleccione **[!UICONTROL Filtro]**.
1. Agregue un filtro de participación de [!DNL Marketo] y establezca el tipo de actividad, la campaña u otros atributos para que se centren en la participación que importa.

Cada posible cliente muestra su última actividad [!DNL Marketo] junto con el historial reciente.

El filtrado de participación de Marketo está disponible en todas las regiones de producción. El administrador lo activa para su organización y zona protegida, y un especialista en marketing finaliza una configuración única en [!DNL Marketo]. Ver [Activar el filtrado de participación de Marketo](integrations.md#turn-on-marketo-engagement-filtering).

## Revisar detalles del cliente potencial

Seleccione un cliente potencial para abrir su perfil. Revise las señales que importan antes de ponerse en contacto con:

* **Resumen de persona de IA**: instantánea escrita por IA del posible cliente o contacto y su participación reciente. Utilice el resumen para comprender a la persona de un vistazo antes de revisar las actividades individuales. Los resúmenes personales de IA están disponibles en instancias en las que se ejecuta Adobe Journey Optimizer B2B edition Prime o Ultimate.
* **Lista de actividades**: una lista cronológica de actividades y comportamiento reciente.
* **Vista de cronología**: una cronología visual de la participación en todos los canales.
* **Contenido visto**: páginas web y recursos que el cliente potencial vio. Seleccione un elemento para abrirlo.

>[!MORELIKETHIS]
>
>* [Cuentas](accounts.md)
>* [Flujos de trabajo salientes](outbound-workflows.md)
>* [Chat de IA](ai-assistant.md)
