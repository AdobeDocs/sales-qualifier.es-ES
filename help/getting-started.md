---
title: Introducción a Sales Qualifier
description: Obtenga información sobre cómo completar la configuración de administrador única para Sales Qualifier, incluidos los grupos de usuarios y una conexión CRM, antes de que su equipo empiece a utilizar la aplicación.
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
TQID: 'https://experienceleague.adobe.com/-nfmFwZyZFUZhm-uQUjSyTvrORuqJgKSKnENWYtvubs'
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2: id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4bid: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d095671a-1355-40aa-8b5f-06c33c68080bid: e1e0219c-f879-479f-8427-888ed2a6e9c2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 08dd05e1d13b501d43d457e6217a43aaabdb1d0d
workflow-type: tm+mt
source-wordcount: 1054
ht-degree: 0%

---


# Introducción a Sales Qualifier

Una vez que Adobe aprovisiona Sales Qualifier para su organización, un administrador del sistema de [!DNL Marketo] debe crear los grupos de usuarios necesarios y conectar Salesforce o Microsoft Dynamics 365.

[Página de inicio de Sales Qualifier](assets/homepage.png){width="800" zoomable="yes"}

## Configuración de grupos de usuarios

Dos grupos de usuarios en Adobe Admin Console controlan el acceso a Sales Qualifier. Cree ambos grupos antes de que los usuarios inicien sesión.

>[!PREREQUISITES]
>
>El administrador que crea los grupos debe cumplir estos dos requisitos:
>
>* Sea administrador de organización con acceso a **[!UICONTROL Admin Console]** desde el conmutador de aplicaciones de Adobe.
>* Tener asignado el producto Adobe Experience Platform o ser administrador del sistema. De lo contrario, Adobe Experience Platform no aparecerá en la lista de productos.

### Usuarios de Sales Qualifier

Los usuarios deben pertenecer al grupo de usuarios `Sales Qualifier` para tener acceso a la aplicación.

1. En el conmutador de aplicaciones de nueve puntos, seleccione **[!UICONTROL Admin Console]**.
1. Seleccione **[!UICONTROL Usuarios]** > **[!UICONTROL Grupos de usuarios]** > **[!UICONTROL Nuevo grupo de usuarios]**.
1. Escriba `Sales Qualifier` en el nombre del grupo y seleccione **[!UICONTROL Guardar]**.
1. Abra **[!UICONTROL Perfiles de producto asignados]** y seleccione **[!UICONTROL Asignar perfil]**.
1. Seleccione **[!UICONTROL Adobe Experience Platform]**.
1. Seleccione el perfil de producto **[!UICONTROL Acceso predeterminado a todos los equipos de producción]**, seleccione **[!UICONTROL Aplicar]** y, a continuación, seleccione **[!UICONTROL Guardar]**.
1. Abra **[!UICONTROL Usuarios]** y seleccione **[!UICONTROL Agregar usuarios]** para agregar a todos los que necesiten acceso a Sales Qualifier.

### Administradores de Sales Qualifier

Los administradores que configuran conexiones CRM, [Centro de conocimiento](knowledge-center.md) y la configuración global de exclusión de correo electrónico también deben pertenecer al grupo de usuarios `Sales Qualifier Admins`.

1. En Adobe Admin Console, seleccione **[!UICONTROL Usuarios]** > **[!UICONTROL Grupos de usuarios]** > **[!UICONTROL Nuevo grupo de usuarios]**.
1. Escriba `Sales Qualifier Admins` en el nombre del grupo y seleccione **[!UICONTROL Guardar]**.
1. Abra **[!UICONTROL Usuarios]**, seleccione **[!UICONTROL Agregar usuarios]** y agregue los administradores.
1. Confirme que cada administrador también es miembro del grupo `Sales Qualifier`.

La pertenencia a ambos grupos hace que **[!UICONTROL Configuración de administración]** sea visible en **[!UICONTROL Administración]** en el panel de navegación izquierdo. Los usuarios estándar trabajan con los campos, filtros y libros de reproducción que configuran los administradores. El pie de página de exclusión configurado se aplica automáticamente a sus correos electrónicos salientes. Los usuarios estándar no pueden cambiar esta configuración. Consulte [Funciones de usuario y permisos](user-roles-permissions.md) para obtener más información.

>[!NOTE]
>
>Los nombres de los grupos de usuarios deben coincidir exactamente como se muestra en los pasos anteriores.

También puede crear un grupo `Sales Qualifier BDR managers` opcional. Los miembros de este grupo pueden acceder a los informes de rendimiento del correo electrónico.

## Conectar su CRM

Sales Qualifier se conecta a Salesforce o Microsoft Dynamics 365 para proporcionar a los BDR una vista unificada de los usuarios, los posibles clientes, los contactos, las cuentas, las oportunidades, las asignaciones de propietarios y las actividades relacionadas. La conexión inicial requiere acceso de solo lectura a estos datos de CRM. Póngase en contacto con el administrador de CRM para preparar las credenciales antes de conectarse a Sales Qualifier. Consulte [Integraciones](integrations.md) para obtener detalles sobre la integración.

>[!PREREQUISITES]
>
>Para acceder a la interfaz de administración de CRM, debe pertenecer al grupo de Adobe Admin Console `Sales Qualifier Admins` y al grupo de `Sales Qualifier`.

>[!BEGINTABS]

>[!TAB Salesforce]

Un administrador del sistema de Salesforce crea una aplicación cliente externa (también denominada aplicación conectada) y configura su usuario de ejecución.

>[!PREREQUISITES]
>
>Confirme que el administrador de Salesforce tiene estos permisos:
>
>* Personalizar aplicación
>* Ver instalación y configuración
>* Modificar todos los datos
>* Administrar aplicaciones conectadas
>
>Sin _Administrar aplicaciones conectadas_, el administrador no puede ver el ID de cliente y el secreto de cliente.

1. En Salesforce, vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Administrador de aplicaciones]** y seleccione **[!UICONTROL Nueva aplicación conectada]** o **[!UICONTROL Nueva aplicación cliente externa]**.
1. Introduzca un nombre de aplicación y un correo electrónico de contacto administrativo.
1. Habilite OAuth e introduzca una URL de devolución de llamada.

   Si la conexión no utiliza una redirección, introduzca una dirección URL válida.

1. Agregue los siguientes ámbitos de OAuth:

   * Acceso al servicio de URL de identidad (`id`, `profile`, `email`, `address`, `phone`)
   * Administrar datos de usuario mediante API (`api`)
   * Acceder a identificadores de usuario únicos (`openid`)

1. Habilite el flujo de credenciales de cliente y seleccione un usuario de **[!UICONTROL Ejecutar como]**.
1. Confirme que el usuario que ejecuta como tiene acceso de **Lectura** para `Leads`, `Accounts`, `Contacts`, `Tasks`, `Events`, `Opportunity`, `OpportunityContactRoles` y `OpportunityLineItems`. Confirme también que **Actividades de acceso** está habilitada.
1. Guarde la aplicación.
1. En **[!UICONTROL Administrador de aplicaciones]**, abra la aplicación y seleccione **[!UICONTROL Ver]** > **[!UICONTROL Detalles del consumidor]**.
1. Copie los siguientes valores para la conexión de Sales Qualifier:

   * Clave de consumidor (ID de cliente)
   * Secreto del consumidor (Secreto del cliente)
   * URL de devolución de llamada
   * URL de instancia de Salesforce

>[!IMPORTANT]
>
>No enviar secretos de cliente por correo electrónico. Utilice el canal seguro aprobado de su organización para compartir credenciales con quien las introduzca en Sales Qualifier.

### Búsqueda de la URL de instancia de Salesforce

1. Inicie sesión y anote el subdominio de organización _Mi dominio_ desde la barra de direcciones del explorador (el valor `{{mydomain}}`).
1. Use el formulario canónico para Sales Qualifier: `https://{{mydomain}}.my.salesforce.com`.

No use una dirección URL `lightning.force.com` como dirección URL de instancia.

>[!TIP]
>
>Si la interfaz de conexiones de CRM informa de ámbitos que faltan, compruebe el perfil del usuario que ha ejecutado bajo **[!UICONTROL Permisos de objeto estándar]** para obtener acceso de **Lectura** a posibles clientes, contactos, cuentas y oportunidades. Compruebe también **[!UICONTROL Configuración de objeto]** en cada conjunto de permisos asignado.

>[!TAB Microsoft Dynamics 365]

Un administrador de Microsoft Dynamics 365 o Azure registra una aplicación y la añade al entorno de Dynamics.

1. En Microsoft Entra ID, seleccione **[!UICONTROL Registros de aplicaciones]** y registre una solicitud.
1. Copie el ID de cliente y el ID de inquilino y cree un secreto de cliente.
1. En el **[!UICONTROL Centro de administración de Power Platform]**, seleccione **[!UICONTROL Entornos]** y abra el entorno de Dynamics.
1. Vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Usuarios + permisos]** > **[!UICONTROL Usuarios de aplicaciones]** y seleccione **[!UICONTROL Nuevo usuario de aplicaciones]**.
1. Seleccione la aplicación registrada de Microsoft Entra.
1. Asigne una función de seguridad que conceda acceso de lectura a posibles clientes, contactos, cuentas, oportunidades y actividades.

   Se requiere una función de seguridad. Sin una, la aplicación no puede acceder a los datos de Dynamics.

1. Recopile el ID de cliente, el secreto de cliente, el ID de inquilino y la URL de instancia de Dynamics. Use el formulario de URL canónico `https://{{mydomain}}.crm.dynamics.com`.

>[!ENDTABS]

### Introduzca su conexión

1. Como miembro de ambos grupos de Sales Qualifier necesarios, inicie sesión en Sales Qualifier y confirme que se ha seleccionado la zona protegida o el entorno correctos.
1. En el panel de navegación izquierdo, expanda **[!UICONTROL Administración]** y seleccione **[!UICONTROL Configuración de administración]**.
1. Seleccione **[!UICONTROL conexiones CRM]** en **[!UICONTROL Integraciones]**.

   Las versiones anteriores de la interfaz podrían mostrar esta área como **[!UICONTROL Integraciones]** en **[!UICONTROL Administración]**.

   La página muestra tarjetas para Salesforce y Microsoft Dynamics. Una conexión inactiva muestra **[!UICONTROL Connect]**. Una conexión configurada muestra **[!UICONTROL Conectado]** y **[!UICONTROL Administrar]**.

1. Seleccione **[!UICONTROL Connect]** para el CRM que utilice.
1. Introduzca las credenciales y la URL de instancia de su administrador de CRM.
1. Después de una conexión correcta, confirma que la tarjeta muestra **[!UICONTROL Conectado]**.

### Importar campos de CRM

Después de conectar el CRM, configure la asignación de entrada para elegir qué campos de CRM aparecen en Sales Qualifier.

1. En la tarjeta CRM conectada, seleccione **[!UICONTROL Administrar]** para abrir **[!UICONTROL Asignación entrante]**.
1. Seleccione **[!UICONTROL Agregar sección]**.
1. Introduzca un nombre de sección y una descripción.
1. Seleccione el tipo de entidad. **[!UICONTROL Clientes potenciales]** está seleccionado de forma predeterminada. También están disponibles **[!UICONTROL Contactos]**, **[!UICONTROL Cuentas]** y **[!UICONTROL Oportunidades]**.
1. Seleccione los campos CRM que desea importar.
1. Previsualice la sección y seleccione **[!UICONTROL Agregar]**.

Los campos de posible cliente aparecen en la ficha **[!UICONTROL Persona]**, los campos de cuenta aparecen en la ficha **[!UICONTROL Cuenta]** y los campos de oportunidad aparecen en la sección **[!UICONTROL Oportunidad de cuenta]**. Active **[!UICONTROL Filtrable]** para cada campo asignado que los representantes necesiten como filtro.

Consulte [Integraciones](integrations.md#map-crm-fields-inbound-mapping) para administrar la asignación y sincronización de campos.

## Próximos pasos

>[!MORELIKETHIS]
>
>* [Clientes potenciales](prospects.md)
>* [Flujos de trabajo salientes](outbound-workflows.md)
>* [Roles y permisos de usuario](user-roles-permissions.md)
