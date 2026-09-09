---
title: Clientes potenciales en Sales Qualifier
description: Obtenga información sobre cómo crear su lista de clientes potenciales desde CRM, fuentes importadas y agregadas manualmente, filtrar clientes potenciales y revisar los detalles del cliente potencial en Sales Qualifier.
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
source-git-commit: c7f4e1b7adc4b3420ea5f16c3b426c40bb300d45
workflow-type: tm+mt
source-wordcount: 698
ht-degree: 1%

---


# Clientes potenciales

Seleccione **[!UICONTROL Clientes potenciales]** en el panel de navegación izquierdo para ver los posibles clientes y contactos a los que puede acceder. Utilice la lista para revisar el estado y la actividad más reciente de cada posible cliente.

![Tabla de clientes potenciales que muestra el estado del posible cliente y la última actividad para la administración de clientes potenciales](./assets/prospects.png){width="800" zoomable="yes"}

* **[!UICONTROL Posibles clientes]**: posibles clientes asignados a usted en el CRM conectado.
* **[!UICONTROL Contactos]**: contactos asignados a usted en el CRM conectado.
* **[!UICONTROL Aspectos destacados del marketing]**: clientes potenciales con actividad de Marketo activa, como aperturas de correos electrónicos o clics.
* **[!UICONTROL Lista de personas]**: clientes potenciales que se importan o agregan manualmente.

## Crear su lista de clientes potenciales

La lista de clientes potenciales combina personas de más de una fuente:

* **clientes potenciales de CRM**: Sales Qualifier importa automáticamente los posibles clientes y contactos asignados al usuario conectado. Consulte [Integraciones](integrations.md).
* **Clientes potenciales importados**: clientes potenciales importados desde un archivo CSV.
* **Perspectivas agregadas manualmente**: Perspectivas individuales agregadas en Sales Qualifier.

Para agregar clientes potenciales que no provienen de su CRM:

1. En la página **[!UICONTROL Posibles clientes]**, seleccione **[!UICONTROL Lista de personas]**.

   ![Lista de personas](assets/prospects-people-list.png){width="800" zoomable="yes"}

1. Seleccione **[!UICONTROL + Agregar personas]**, luego seleccione **[!UICONTROL Importar CSV]** o **[!UICONTROL Agregar persona]**.

   * Para una importación de CSV, cargue un CSV en formato `firstname,email`.
     El nombre y el correo electrónico son obligatorios. El apellido es opcional. La plantilla CSV no incluye la columna ID de posible cliente de CRM, pero puede agregar la columna y sus valores al archivo antes de la importación. Si la importación falla, revise el mensaje de error de los campos o valores para corregirlos y, a continuación, cargue el archivo de nuevo.
     Asigne cualquier campo CSV personalizado o adicional, no solo los estándar. Sales Qualifier guarda estos valores en cada posible cliente y los pone a disposición más adelante, incluso para la [generación de correo electrónico](outbound-workflows.md#step-5-add-prospects-and-start-email-generation).
   * Para añadir a una persona manualmente, introduzca sus detalles en el formulario.

1. Seleccione **[!UICONTROL Guardar]**.

## Filtrado y búsqueda de clientes potenciales

Seleccione **[!UICONTROL Filter]** para reducir la lista. Puede filtrar por:

* Estado de flujo de trabajo saliente
* Creado por
* Cargo
* Cuenta
* Origen
* Última actualización

Los administradores también pueden hacer que los campos CRM asignados estén disponibles como filtros. En **[!UICONTROL Configuración de administración]**, active **[!UICONTROL Filtrable]** para cada campo que los representantes utilicen para encontrar posibles clientes. Ver [Asignar campos CRM](integrations.md#map-crm-fields-inbound-mapping).

En **[!UICONTROL Mis contactos de oportunidad]**, también puede filtrar contactos por campos de sus oportunidades asociadas, como escenario, tipo y fecha de cierre. Los campos de oportunidad tienen etiquetas como **[!UICONTROL Stage (Opportunity)]**, que los distingue de los campos de contacto. El administrador controla qué campos de oportunidad están disponibles como filtros.

### Filtrar por aspectos destacados de marketing

Busque y dé prioridad a los posibles clientes por su participación de [!DNL Marketo] en directo, como aperturas y clics de correos electrónicos, visitas web, rellenos de formularios y momentos interesantes. El compromiso aparece en tiempo casi real, a medida que sucede.

Para filtrar posibles clientes por Aspectos destacados de marketing:

1. Seleccione **[!UICONTROL Filtro]**.
1. Agregue un filtro de Elementos destacados de marketing y establezca el tipo de actividad, la campaña u otros atributos para que se centren en la participación que importa.

Cada posible cliente muestra su última actividad [!DNL Marketo] junto con el historial reciente.

Marketing Highlights está disponible en todas las regiones de producción. Un administrador completa una configuración única que conecta a [!DNL Marketo] con Sales Qualifier. Ver [Configurar aspectos destacados de marketing](integrations.md#turn-on-marketo-engagement-filtering).

## Revisar detalles del cliente potencial

Seleccione un cliente potencial para abrir su perfil. Revise las señales que importan antes de ponerse en contacto con:

* **Resumen de persona de IA**: instantánea escrita por IA del posible cliente o contacto y su participación reciente. Utilice el resumen para comprender a la persona de un vistazo antes de revisar las actividades individuales. Los resúmenes personales de IA están disponibles en instancias en las que se ejecuta Adobe Journey Optimizer B2B edition Prime o Ultimate.
* **Lista de actividades**: una lista cronológica de actividades y comportamiento reciente.
* **Vista de cronología**: una cronología visual de la participación en todos los canales.
* **Contenido visto**: páginas web y recursos que el cliente potencial vio. Seleccione un elemento para abrirlo.

### Generar preparación de reunión

Además del resumen de la persona de IA permanente, puede generar una preparación de reunión adaptada a una llamada específica desde la pestaña **[!UICONTROL Investigación de la reunión]**, junto a **[!UICONTROL Investigación de la cuenta]**.

* **Basado en objetivos**: si el cliente potencial está inscrito en un flujo de trabajo saliente en ejecución, selecciónelo. La preparación se ajusta al objetivo de ese flujo de trabajo saliente, como reservar una reunión, presentar un producto, invitar a un evento o volver a atraer al posible cliente.
* **Mensaje personalizado**: escriba para qué desea prepararse, por ejemplo `Focus on renewal risk` o `Prepare for a technical deep dive with their IT lead`. La preparación coincide con el mensaje. La opción de mensaje personalizado está disponible siempre que el cliente potencial no esté en un flujo de trabajo saliente en ejecución.

>[!MORELIKETHIS]
>
>* [Cuentas](accounts.md)
>* [Flujos de trabajo salientes](outbound-workflows.md)
>* [Chat de IA](ai-assistant.md)
