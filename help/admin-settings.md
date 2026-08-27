---
title: Configuración de administración
description: Obtenga información sobre cómo administrar campos CRM, sincronización de actividades, exclusión de correo electrónico y otras configuraciones de administración de Sales Qualifier.
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
TQID: 'https://experienceleague.adobe.com/vbtO6I67ZEaZz3oio9InNErvq5D0wjbRxyDZpTq8Lzo'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
  - id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
internal-label: Administration
source-git-commit: 8573d3891d5c8ec8a05637f160f120f933b0ec61
workflow-type: tm+mt
source-wordcount: 670
ht-degree: 0%

---


# Configuración de administración

Use **[!UICONTROL Configuración de administración]** para configurar integraciones de CRM, administrar el Centro de conocimiento y configurar la exclusión de correo electrónico.

Sales Qualifier se conecta a Salesforce o Microsoft Dynamics 365. La conexión proporciona a Account Qualification Agent (AQA) una vista coherente de los posibles clientes, las cuentas, los contactos, las actividades y los propietarios. Sales Qualifier también puede escribir actividades de divulgación y estados de exclusión en CRM y sincronizar las actividades de divulgación con Marketo.

Para configurar las conexiones de CRM, la asignación de campos y la sincronización de actividades, vaya a **[!UICONTROL Administración]** > **[!UICONTROL Configuración de administración]** > **[!UICONTROL Conexiones de CRM]**. Los usuarios estándar pueden utilizar los datos y filtros de CRM configurados, pero no pueden cambiar esta configuración. Para conectar un CRM por primera vez, consulte [Introducción](getting-started.md#connect-your-crm).

>[!IMPORTANT]
>
>El acceso a **[!UICONTROL Configuración de administración]** requiere la pertenencia a los grupos de usuarios `Sales Qualifier` y `Sales Qualifier Admins`. Consulte [Funciones de usuario y permisos](user-roles-permissions.md).

## CRM MCP y el complemento incrustado

Sales Qualifier trabaja con su CRM de las siguientes maneras:

* **CRM MCP queries**: Account Qualification Agent consulta datos de CRM activos para que las respuestas y perspectivas reflejen el estado actual de sus registros.
* **Complemento incrustado**: el complemento CRM muestra [!DNL Marketo Sales Insights] (MSI) datos y datos auténticos en su CRM. Utilice el complemento para agregar un cliente potencial a Sales Qualifier.
* **Sincronización de actividades**: cuando un administrador activa **[!UICONTROL Sincronización de actividades]**, las actividades de alcance se sincronizan con CRM y Marketo.

## Ámbito de acceso CRM

Sales Qualifier lee usuarios, contactos, asignaciones de propietarios, posibles clientes, cuentas, oportunidades y actividades desde CRM. Solo escribe las actividades de divulgación registradas y el estado de exclusión en CRM, y sincroniza las actividades de divulgación con Marketo. El administrador de CRM prepara el acceso a la API en Salesforce o Dynamics. A continuación, un administrador de Sales Qualifier conecta el CRM, asigna campos de entrada y elige si desea sincronizar las actividades.

>[!NOTE]
>
>Los pasos de credenciales en [Introducción](getting-started.md#connect-your-crm) describen el acceso de lectura a objetos CRM. Si activa la sincronización de actividades o la reescritura de exclusión, trabaje con su administrador de CRM para conceder el acceso de escritura correspondiente requerido por su configuración de CRM.

## Asignar campos CRM (asignación de entrada)

Una vez conectado el CRM, seleccione **[!UICONTROL Administrar]** para la conexión y abra **[!UICONTROL Asignación entrante]**. La asignación de entrada controla qué campos CRM extrae Sales Qualifier en la aplicación.

1. Seleccione **[!UICONTROL Agregar sección]**.
1. Introduzca un nombre de sección y una descripción.
1. Seleccione un tipo de entidad. **[!UICONTROL Clientes potenciales]** está seleccionado de forma predeterminada. También están disponibles **[!UICONTROL Contactos]**, **[!UICONTROL Cuentas]** y **[!UICONTROL Oportunidades]**.
1. Seleccione los campos CRM que desea importar.

   Cada fila de campo muestra su **[!UICONTROL nombre para mostrar]**, **[!UICONTROL nombre de campo]** y **[!UICONTROL tipo de datos]**.

1. Active **[!UICONTROL Filtrable]** para cada cliente potencial, contacto o campo de oportunidad que desee poner a disposición como filtro en la lista de **[!UICONTROL clientes potenciales]**.
1. Previsualice la sección y seleccione **[!UICONTROL Agregar]**.

Los campos asignados aparecen en las áreas correspondientes de Sales Qualifier:

* Los campos de clientes potenciales aparecen en la ficha **[!UICONTROL Persona]**.
* Los campos de cuenta aparecen en la ficha **[!UICONTROL Cuenta]**.
* Los campos de oportunidad aparecen en la sección **[!UICONTROL Oportunidad de cuenta]**. Los campos de oportunidad que se pueden filtrar también aparecen como sus propias columnas en **[!UICONTROL Mis contactos de oportunidad]**, con etiquetas como **[!UICONTROL Etapa (oportunidad)]** para distinguirlos de los campos de contacto.

## Configuración de la sincronización de actividades (asignación saliente)

1. De **[!UICONTROL conexiones CRM]**, seleccione **[!UICONTROL Administrar]** para el CRM conectado.
1. Abrir **[!UICONTROL asignación saliente]**.
1. Active **[!UICONTROL Sincronización de actividades]** para sincronizar las actividades de Sales Qualifier con CRM y Marketo. Las actividades de enviar, abrir, hacer clic y responder por correo electrónico incluyen el nombre del flujo de trabajo saliente.

Cuando la sincronización de actividades está desactivada, Sales Qualifier sigue utilizando datos CRM entrantes, pero no sincroniza las actividades de divulgación con CRM o Marketo.

## Configuración de la exclusión de correo electrónico global

1. En el panel de navegación izquierdo, expanda **[!UICONTROL Administración]** y seleccione **[!UICONTROL Configuración de administración]**.
1. Seleccione **[!UICONTROL Configuración de correo electrónico]** en **[!UICONTROL Cumplimiento]**.
1. Active **[!UICONTROL Incluir vínculo de no participación en cada correo electrónico]** para anexar un pie de página de cancelación de suscripción a los correos electrónicos salientes.
1. En **[!UICONTROL Plantilla de mensaje de exclusión]**, escriba el texto del pie de página. Incluya el token `{opt_out_link}` donde debería aparecer el vínculo para cancelar la suscripción.

La configuración se guarda automáticamente.

Cuando un cliente potencial selecciona el vínculo, Sales Qualifier deja de enviarle correos electrónicos y sincroniza el estado de exclusión con el CRM conectado.

## Referencia: Parámetros de API de muestra

Su equipo de CRM puede utilizar estos ejemplos para confirmar que el acceso de lectura devuelve los campos de posibles clientes esperados.

### Ejemplo de OData de Dynamics

```text
$select=fullname,_ownerid_value,leadid,emailaddress1,jobtitle,statuscode,createdon,modifiedon,statecode
$filter=_ownerid_value eq '<crmUserId>' [AND additional filters]
$expand=Lead_ActivityPointers(...),parentaccountid(...)
$orderby=modifiedon desc
```

### Ejemplo de SOQL de Salesforce

```sql
SELECT Id, Salutation, FirstName, LastName, Name, Title, Company, Email,
  LeadSource, Status, OwnerId, LastModifiedDate, LastActivityDate, CreatedDate,
  (SELECT Id, Subject, ActivityDate, Status FROM Tasks ORDER BY ActivityDate DESC LIMIT 1),
  (SELECT Id, Subject, ActivityDateTime FROM Events ORDER BY ActivityDateTime DESC LIMIT 1)
FROM Lead
WHERE OwnerId = '<crmUserId>' AND IsDeleted = false
ORDER BY LastModifiedDate DESC
```

>[!MORELIKETHIS]
>
>* [Introducción](getting-started.md)
>* [Roles y permisos de usuario](user-roles-permissions.md)
>* [Clientes potenciales](prospects.md)
