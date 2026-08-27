---
title: Configurar aspectos destacados de marketing
description: Aprenda a conectar Marketo a Sales Qualifier para que los representantes puedan ver y filtrar posibles clientes por actividad de Marketo en directo en Elementos destacados de marketing.
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
  - id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 17bfe0a1ce9b289ed85af0f72ddd089b11cca875
workflow-type: tm+mt
source-wordcount: 675
ht-degree: 3%

---


# Configurar aspectos destacados de marketing

Marketing Highlights muestra la actividad [!DNL Marketo] activa de cada posible cliente, tal como aperturas de correo electrónico y clics, visitas web y rellenos de formularios. Este artículo explica cómo conectar su instancia de [!DNL Marketo] para que la actividad fluya.

>[!IMPORTANT]
>
>Para completar esta configuración se requiere acceso a Adobe Developer Console y a **[!UICONTROL Admin]** en [!DNL Marketo]. Trabaje con su contacto de Adobe y con su administrador de [!DNL Marketo] para completar las cuatro partes siguientes.

El programa de instalación consta de cuatro partes:

* Parte A: Crear credenciales de API en Adobe Developer Console.
* Parte B: Recopilar el extremo y los identificadores de Sales Qualifier.
* Parte C: Configurar un webhook en [!DNL Marketo Engage].
* Parte D: Agregar el webhook a una campaña inteligente de déclencheur.

Una vez completada la configuración, los usuarios verán y filtrarán esta actividad en **[!UICONTROL Posibles clientes]** > **[!UICONTROL Aspectos destacados del marketing]**.

## Parte A: Creación de credenciales de API {#part-a-create-api-credentials}

Estas credenciales permiten que [!DNL Marketo] se autentique de forma segura en Sales Qualifier.

Para crear las credenciales:

1. Vaya a la [consola de desarrollador de Adobe](https://developer.adobe.com/console/) e inicie sesión con su Adobe ID.
1. Seleccione **[!UICONTROL Crear nuevo proyecto]** o abra un proyecto existente.
1. Seleccione **[!UICONTROL Editar proyecto]**, cambie el nombre del proyecto a algo identificable, como `Sales Qualifier Marketing Highlights`, y seleccione **[!UICONTROL Guardar]**.
1. Seleccione **[!UICONTROL Agregar API]**, seleccione **[!UICONTROL API de Experience Platform]** y, a continuación, seleccione **[!UICONTROL Siguiente]**.
1. Elija **[!UICONTROL Servidor a servidor OAuth]** como tipo de autenticación y, a continuación, seleccione **[!UICONTROL Siguiente]**.

   **[!UICONTROL OAuth Server-to-Server]** permite que [!DNL Marketo] llame a la API de Sales Qualifier directamente desde su servidor, sin que sea necesario que una persona inicie sesión.

1. Escriba un nombre de credencial de 45 caracteres o menos, como `Sales Qualifier Marketing Highlights Creds`.
1. Seleccione el perfil de producto que desea asociar y, a continuación, seleccione **[!UICONTROL Guardar la API configurada]**.
1. En **[!UICONTROL Credenciales conectadas]**, abra la credencial **[!UICONTROL Servidor a servidor OAuth]**. Seleccione **[!UICONTROL Recuperar secreto de cliente]** y copie el **[!UICONTROL ID de cliente]** y el **[!UICONTROL Secreto de cliente]**. Estos valores se usan en [Parte C](#part-c-configure-the-marketo-webhook).

>[!WARNING]
>
>Mantenga el secreto del cliente en privado. Trátela como una contraseña y no la envíe por correo electrónico. Utilice el canal seguro aprobado de su organización para compartirlo con quien configure el webhook.

## Parte B: Recopilar el punto final y los identificadores {#part-b-gather-your-endpoint-and-identifiers}

Necesita tres valores para [Parte C](#part-c-configure-the-marketo-webhook):

* **URL de extremo**: la dirección del webhook de Sales Qualifier para su región.
* **imsOrg ID**: el identificador de su organización en Adobe Identity Management System (IMS), con el formato `{ORG_ID}@AdobeOrg`.
* **Nombre de zona protegida**: El nombre de la zona protegida de AEP exactamente como aparece en la dirección URL de Sales Qualifier (el valor `sname`), no el nombre para mostrar mostrado en la interfaz de usuario. Utilice el valor de URL en minúsculas, por ejemplo `prod`, no `Prod`.

| Región | URL de extremo de webhook |
| --- | --- |
| América del Norte | `https://5r6xakp9k3.execute-api.us-east-1.amazonaws.com/prod/external/marketo/signals` |
| EMEA | `https://pc72i8q1k3.execute-api.eu-west-1.amazonaws.com/prod/external/marketo/signals` |
| Asia-Pacífico/Australia | `https://5cxxxyqlai.execute-api.ap-southeast-2.amazonaws.com/prod/external/marketo/signals` |

{style="table-layout:auto"}

Si no está seguro de su región, ID de imsOrg o nombre de la zona protegida, su contacto de Adobe puede confirmarlos.

## Parte C: Configuración del webhook de Marketo {#part-c-configure-the-marketo-webhook}

Para crear el webhook:

1. En [!DNL Marketo], seleccione **[!UICONTROL Administrador]** > **[!UICONTROL Webhooks]**.
1. Seleccione **[!UICONTROL Nuevo webhook]**.
1. Establece **[!UICONTROL URL]** a la URL de punto final para tu región desde [Parte B](#part-b-gather-your-endpoint-and-identifiers).
1. Establecer **[!UICONTROL tipo de solicitud]** en `POST`.
1. Establezca la codificación de token de solicitud **[!UICONTROL 1&rbrace; en `JSON`.]** Esta configuración es obligatoria.
1. Pegue la plantilla de carga útil siguiente en **[!UICONTROL Template]**. Use **[!UICONTROL Insertar token]** de [!DNL Marketo] para que coincidan con los nombres de campo de su instancia.

   >[!NOTE]
   >
   >Con la codificación JSON, no ajuste los tokens de cadena entre comillas. [!DNL Marketo] los agrega automáticamente.

   ```json
   {
     "leadId": {{lead.Id:default=0}},
     "email": {{lead.Email Address:default=}},
     "fullName": {{lead.Full Name:default=}},
     "company": {{company.Company Name:default=}},
     "title": {{lead.Job Title:default=}},
     "department": {{lead.Department:default=}},
     "country": {{lead.Country:default=}},
     "score": {{lead.Lead Score:default=0}},
     "rating": {{lead.Lead Rating:default=}},
     "leadStatus": {{lead.Lead Status:default=}},
     "leadSource": {{lead.Lead Source:default=}},
     "isCustomer": {{lead.Is Customer:default=false}},
     "industry": {{company.Industry:default=}},
     "annualRevenue": {{company.Annual Revenue:default=0}},
     "numEmployees": {{company.Num Employees:default=0}},
     "campaignId": {{campaign.id:default=0}},
     "campaignName": {{campaign.name:default=}},
     "programName": {{program.name:default=}},
     "occurredAt": {{system.dateTime:default=}},
     "munchkinId": {{system.munchkinId:default=}},
     "triggerName": {{trigger.Trigger Name:default=}},
     "crmId": {{lead.SFDC ID:default=}},
     "crmType": {{lead.SFDC Type:default=}},
     "crmOwnerEmail": {{lead.Lead Owner Email Address:default=}},
     "crmOwnerFirstName": {{lead.Lead Owner First Name:default=}},
     "crmOwnerLastName": {{lead.Lead Owner Last Name:default=}},
     "attributes": {
       "asset": {{trigger.Name:default=}},
       "link": {{trigger.Link:default=}},
       "subject": {{trigger.Subject:default=}},
       "webPage": {{trigger.Web Page:default=}},
       "category": {{trigger.Category:default=}},
       "details": {{trigger.Details:default=}},
       "sentBy": {{trigger.Sent By:default=}},
       "receivedBy": {{trigger.Received By:default=}},
       "referrer": {{trigger.Referrer:default=}},
       "searchEngine": {{trigger.Search Engine:default=}},
       "searchQuery": {{trigger.Search Query:default=}},
       "imDescription": {{lead.Last Interesting Moment Desc:default=}},
       "imType": {{lead.Last Interesting Moment Type:default=}},
       "imDate": {{lead.Last Interesting Moment Date:default=}},
       "imSource": {{lead.Last Interesting Moment Source:default=}},
       "chatAgentName": {{trigger.Agent Name:default=}},
       "chatAgentEmail": {{trigger.Agent Email:default=}},
       "chatConversationStatus": {{trigger.Conversation Status:default=}},
       "chatConversationSummary": {{trigger.Conversation Summary:default=}},
       "chatGoalName": {{trigger.Goal name:default=}},
       "chatMeetingStatus": {{trigger.meeting status:default=}},
       "chatScheduledFor": {{trigger.Scheduled For:default=}},
       "chatDocumentName": {{trigger.Document Name:default=}},
       "chatDocumentUrl": {{trigger.Document URL:default=}},
       "chatPageUrl": {{trigger.Page URL:default=}}
     }
   }
   ```

1. Seleccione **[!UICONTROL Acciones de webhook]** > **[!UICONTROL Definir encabezado personalizado]** y, a continuación, agregue los siguientes encabezados, utilizando los valores de [Parte A](#part-a-create-api-credentials) y [Parte B](#part-b-gather-your-endpoint-and-identifiers):

   | Encabezado | Valor |
   | --- | --- |
   | `Content-Type` | `application/json` |
   | `x-client-id` | Su ID de cliente |
   | `x-client-secret` | Secreto de cliente |
   | `x-gw-ims-org-id` | Su ID de imsOrg |
   | `x-sandbox-name` | Nombre de la zona protegida |

   {style="table-layout:auto"}

1. Seleccione **[!UICONTROL Guardar]**.

## Parte D: Agregar el webhook a una campaña inteligente de déclencheur {#part-d-add-the-webhook-to-a-trigger-smart-campaign}

Agregue un paso de flujo **[!UICONTROL Llamar al webhook]** a una campaña inteligente de déclencheur, ya sea una existente o una nueva. Los déclencheur de listas inteligentes de esa campaña deciden qué actividades se envían a Sales Qualifier.

Para agregar el webhook:

1. Abra una campaña inteligente de déclencheur existente o cree una nueva (**[!UICONTROL Actividades de marketing]** > **[!UICONTROL Nueva]** > **[!UICONTROL Campaña inteligente]**).
1. En la ficha **[!UICONTROL Lista inteligente]**, agregue el déclencheur o los déclencheur de las actividades que desee enviar; por ejemplo, **[!UICONTROL Hace clic en el vínculo del correo electrónico]**, **[!UICONTROL Rellena el formulario]** o **[!UICONTROL Visita la página web]**.
1. En la ficha **[!UICONTROL Flujo]**, agregue un paso **[!UICONTROL Llamar al webhook]** y seleccione el webhook que creó en [Parte C](#part-c-configure-the-marketo-webhook).
1. Active la campaña inteligente.

La actividad de esa campaña inteligente ahora fluye a Sales Qualifier. Los representantes ven y filtran esta actividad en **[!UICONTROL Prospects]** > **[!UICONTROL Marketing Highlights]**.

>[!MORELIKETHIS]
>
>* [Administrar integraciones](integrations.md)
>* [Clientes potenciales](prospects.md)
>* [Introducción](getting-started.md)
