---
title: Administración de integraciones
description: Obtenga información sobre cómo conectar Outlook, administrar conexiones CRM, asignar campos de entrada, sincronizar actividades y configurar la exclusión de correo electrónico global en Sales Qualifier.
feature: Agentic AI, Sales Insights, Account Journeys
role: User, Admin
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2: id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4bid: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d095671a-1355-40aa-8b5f-06c33c68080bid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 351b27d35049b0bb576e9b84f7fd6fada791bb52
workflow-type: tm+mt
source-wordcount: 1379
ht-degree: 1%

---


# Integraciones

Conecte Outlook para enviar correos electrónicos, reconocer las respuestas de los posibles clientes y programar reuniones. Para que los posibles clientes, los contactos, las cuentas, las oportunidades, las actividades y los propietarios estén disponibles para los flujos de trabajo salientes y de Account Qualification Agent (AQA), también puede conectar Sales Qualifier a Salesforce o Microsoft Dynamics 365. Sales Qualifier lee datos de CRM, puede escribir actividades de divulgación y estados de exclusión en CRM, y puede sincronizar actividades de divulgación con Marketo. De lo contrario, no modifica los registros CRM.

Este artículo explica cómo conectar Outlook, administrar una conexión CRM, asignar campos, sincronizar actividades y configurar la exclusión de correo electrónico. Para conectar un CRM por primera vez, consulte [Introducción](getting-started.md#connect-your-crm).

>[!IMPORTANT]
>
>La conexión de Outlook es por representante. La configuración de CRM y conformidad descrita más adelante en este artículo se aplica a toda la organización. Para tener acceso a esa configuración en toda la organización, debe pertenecer a los grupos de usuarios `Sales Qualifier` y `Sales Qualifier Admins`. Los usuarios estándar pueden utilizar los datos y filtros de CRM configurados, pero no pueden cambiar la configuración. Consulte [Funciones de usuario y permisos](user-roles-permissions.md).

## Conectar Outlook

Cada representante conecta su propia cuenta de Outlook:

1. Seleccione **[!UICONTROL Conectar Outlook]**.
1. Inicie sesión con su cuenta de Microsoft.
1. Revise y apruebe el acceso solicitado.

La conexión permite que Sales Qualifier envíe mensajes desde su buzón de correo, reconozca cuándo responde un posible cliente y programe reuniones en su calendario.

Al conectarse, aprueba el acceso que permite a Sales Qualifier:

* Reconocer las respuestas de los posibles clientes.
* Cree y envíe correos electrónicos en su nombre.
* Utilice el calendario para programar reuniones.
* Lea la zona horaria del buzón y las horas de trabajo para programarlos.
* Permanecer conectado automáticamente para que estas funciones sigan funcionando sin que sea necesario que vuelva a iniciar sesión.

### Aprobaciones de Outlook (si es necesario)

De forma predeterminada, no se requiere ninguna acción del administrador. Cada representante aprueba el acceso para sí mismo cuando se conectan a Outlook.

Si su organización ha desactivado el consentimiento del usuario para aplicaciones de terceros en Microsoft 365 o Microsoft Entra, un administrador de Microsoft 365 o Entra debe aprobar Sales Qualifier una vez para toda la organización. El administrador completa esta aprobación antes de que los representantes conecten sus cuentas de Outlook. Después de la aprobación en toda la organización, cada representante puede conectar su cuenta.

### Cómo administra Sales Qualifier los datos del buzón

Sales Qualifier solo lee las respuestas a los correos electrónicos enviados, no el resto de la bandeja de entrada. No almacena los archivos adjuntos entrantes ni los correos electrónicos fuera de una participación activa. Las credenciales de inicio de sesión almacenadas están cifradas.

## Abrir configuración de CRM

En el panel de navegación izquierdo, expanda **[!UICONTROL Administración]** y seleccione **[!UICONTROL Configuración de administración]**. La configuración se organiza en dos grupos:

| Grupo | Elementos |
| --- | --- |
| **[!UICONTROL Integraciones]** | **[!UICONTROL Conexiones CRM]**, **[!UICONTROL Centro de conocimiento]** |
| **[!UICONTROL Cumplimiento]** | **[!UICONTROL Configuración de correo electrónico]** |

Para el Centro de conocimientos, consulte [Centro de conocimientos](knowledge-center.md).

## Administrar conexiones CRM

Seleccione **[!UICONTROL conexiones CRM]**. La página contiene tarjetas para **[!UICONTROL Salesforce]** y **[!UICONTROL Microsoft]** (Microsoft Dynamics 365). Cada tarjeta muestra uno de estos estados:

| Estado | Significado |
| --- | --- |
| **[!UICONTROL Conectado]** | La conexión está activa y autenticada. |
| **[!UICONTROL No está activo]** | No hay ninguna conexión configurada para este CRM. |
| **[!UICONTROL Permisos necesarios]** | La conexión está autenticada, pero faltan los ámbitos necesarios. La tarjeta enumera los ámbitos que faltan. |

>[!NOTE]
>
>Solo puede haber un CRM activo a la vez. Cuando se conecta un CRM, la otra tarjeta se desactiva. Desconecte el CRM activo antes de conectar uno diferente.

Una tarjeta sin configurar muestra **[!UICONTROL Connect]**. Una tarjeta configurada muestra **[!UICONTROL Administrar]** y un menú de **[!UICONTROL Más]** con **[!UICONTROL Editar configuración]** y **[!UICONTROL Desconectar]**.

### Conexión o edición de una conexión

1. En la tarjeta CRM, seleccione **[!UICONTROL Conectar]** o **[!UICONTROL Más]** > **[!UICONTROL Editar configuración]** para actualizar una conexión existente.
1. Introduzca las credenciales de su administrador de CRM.

   >[!BEGINTABS]

   >[!TAB Salesforce]

   Escriba **[!UICONTROL ID de cliente (clave de consumidor)]**, **[!UICONTROL URL de instancia]** y **[!UICONTROL Secreto de cliente]**. Utilice el formulario de URL de instancia canónica `https://{{mydomain}}.my.salesforce.com`.

   ![Conexión de Salesforce](assets/crm-conn-salesforce.png){width="800" zoomable="yes"}

   >[!TAB Microsoft Dynamics]

   Escriba **[!UICONTROL ID de cliente (clave de consumidor)]**, **[!UICONTROL ID de inquilino]**, **[!UICONTROL URL de instancia de Microsoft Dynamics]** y **[!UICONTROL Secreto de cliente]**. Utilice el formulario de URL de instancia canónica `https://{{mydomain}}.crm.dynamics.com`.

   >[!ENDTABS]

1. Seleccione **[!UICONTROL Conectar]** (o **[!UICONTROL Guardar]** al editar).

Si Sales Qualifier rechaza las credenciales, identifica la causa, como credenciales no válidas o caducadas, permisos que faltan o un inquilino de Dynamics no reconocido. Corrija el valor e inténtelo de nuevo.

>[!IMPORTANT]
>
>No enviar secretos de cliente por correo electrónico. Utilice el canal seguro aprobado de su organización para compartir credenciales con quien las introduzca en Sales Qualifier.

### Desconexión de una conexión

1. En la tarjeta CRM conectada, seleccione **[!UICONTROL Más]** > **[!UICONTROL Desconectar]**.
1. Revise la advertencia y seleccione **[!UICONTROL Desconectar]** para confirmar.

>[!WARNING]
>
>Al desconectar un CRM, los flujos de trabajo salientes se pausan para todos los clientes potenciales de la organización y ningún cliente potencial nuevo se sincroniza desde el CRM hasta que se vuelva a conectar.

## Asignar campos CRM (asignación de entrada) {#map-crm-fields-inbound-mapping}

La asignación de entrada controla qué campos CRM importa Sales Qualifier y dónde aparecen. Los campos se agrupan en secciones y cada sección pertenece a un tipo de entidad.

1. En la tarjeta CRM conectada, seleccione **[!UICONTROL Administrar]**.
1. En la ficha **[!UICONTROL Asignación entrante]**, seleccione **[!UICONTROL Agregar sección]**.
1. En el paso **Seleccionar sección**, elija el tipo de entidad y, a continuación, seleccione **[!UICONTROL Siguiente]**:

   | Entidad | Dónde aparecen sus campos |
   | --- | --- |
   | **[!UICONTROL Clientes potenciales]** | La ficha **[!UICONTROL Persona]** de un cliente potencial. |
   | **[!UICONTROL Contactos]** | El registro de contacto. |
   | **[!UICONTROL Cuentas]** | La ficha **[!UICONTROL Cuenta]**. Ver [Cuentas](accounts.md). |
   | **[!UICONTROL Oportunidades]** | Los detalles de oportunidad de la cuenta. |

1. Escriba un **[!UICONTROL nombre de sección]** y una **[!UICONTROL descripción]** opcional. A continuación, seleccione **[!UICONTROL Siguiente]**.
1. En el paso **[!UICONTROL Agregar campo]**, busque y seleccione los campos CRM que desea importar. A continuación, seleccione **[!UICONTROL Siguiente]**. Cada campo muestra su **[!UICONTROL nombre para mostrar]**, **[!UICONTROL nombre de campo]** y **[!UICONTROL tipo de datos]**.
1. Para las secciones **[!UICONTROL Posibles clientes]**, **[!UICONTROL Contactos]** y **[!UICONTROL Oportunidades]**, active **[!UICONTROL Filtrable]** para cada campo que necesiten los representantes en la lista [Posibles clientes](prospects.md).

   Un campo no se puede convertir en filtrable si su tipo de datos no admite el filtrado o si ya se utiliza en otra sección.

   En **[!UICONTROL Mis contactos de oportunidad]**, los campos de oportunidad que se pueden filtrar aparecen como columnas independientes con etiquetas como **[!UICONTROL Fase (oportunidad)]**. El sufijo distingue los atributos de oportunidad de los campos del contacto asociado.

1. En el paso **[!UICONTROL Vista previa]**, confirma tu selección y selecciona **[!UICONTROL Agregar]**.

Para cambiar una sección más adelante, selecciona **[!UICONTROL Editar]** en la tarjeta de la sección. Para quitar una sección, selecciona **[!UICONTROL Quitar]** en la tarjeta de la sección. Para eliminar un campo individual, seleccione la acción Eliminar en la fila del campo. Confirme cada extracción.

## Configuración de la sincronización de actividades (asignación saliente) {#configure-activity-sync-outbound-mapping}

La sincronización de actividades escribe actividades de divulgación de Sales Qualifier en su CRM y Marketo. Las actividades de enviar, abrir, hacer clic y responder por correo electrónico incluyen el nombre del flujo de trabajo saliente. Los representantes pueden ver las actividades en CRM, mientras que los equipos de marketing pueden utilizar las actividades de Marketo en la puntuación de posibles clientes y los plazos de participación.

1. En la tarjeta CRM conectada, seleccione **[!UICONTROL Administrar]**.
1. Abra la ficha **[!UICONTROL Asignación de salida]**.
1. Activar **[!UICONTROL sincronización de actividades]**. La configuración se guarda inmediatamente.

Cuando la sincronización de actividades está desactivada, Sales Qualifier sigue utilizando datos CRM entrantes, pero no sincroniza las actividades de divulgación con CRM o Marketo.

>[!NOTE]
>
>La sincronización de actividades requiere acceso de escritura en su CRM. Si falta el permiso necesario, el conmutador se desactiva y Sales Qualifier le solicita que se ponga en contacto con el administrador. Para conceder acceso de escritura a la actividad, trabaje con su administrador de CRM.

## Configurar aspectos destacados de marketing {#turn-on-marketo-engagement-filtering}

Marketing Highlights les permite a los representantes encontrar y priorizar prospectos por su participación de [!DNL Marketo] en vivo, como aperturas de correo electrónico y clics. Ver [Filtrar por elementos destacados de marketing](prospects.md#filter-by-marketing-highlights).

Un administrador completa una configuración única que conecta a [!DNL Marketo] con Sales Qualifier para la organización y la zona protegida relevantes. La configuración cubre la creación de credenciales de API en Adobe Developer Console, la configuración de un enlace web en [!DNL Marketo] y la adición de ese enlace web a una campaña inteligente de déclencheur. Consulte [Configurar elementos destacados de marketing](marketing-highlights-setup.md) para ver los pasos completos.

Marketing Highlights está disponible en todas las regiones de producción: Norteamérica, EMEA y Australia.

## Configuración de la exclusión de correo electrónico global {#configure-global-email-opt-out}

La configuración de exclusión adjunta un pie de página para cancelar la suscripción a cada correo electrónico saliente. Los usuarios estándar no pueden desactivarlo para un correo electrónico individual.

1. En el panel de navegación izquierdo, expanda **[!UICONTROL Administración]** y seleccione **[!UICONTROL Configuración de administración]**.
1. Seleccione **[!UICONTROL Configuración de correo electrónico]** en **[!UICONTROL Cumplimiento]**.
1. Activar **[!UICONTROL Incluir vínculo de no participación en cada correo electrónico]**.
1. En **[!UICONTROL Plantilla de mensaje de exclusión]**, escriba el texto del pie de página. Incluya el token `{opt_out_link}` donde debería aparecer el vínculo de cancelación de suscripción al que se puede hacer clic.

   Por ejemplo: `If you'd prefer not to receive these emails, you can {opt_out_link}.`

La configuración y la plantilla se guardan automáticamente.

Cuando un cliente potencial selecciona el vínculo, Sales Qualifier deja de enviarle correos electrónicos y sincroniza el estado de exclusión con el CRM conectado.

## Ámbito de acceso CRM

Sales Qualifier lee las entidades CRM que necesita y solo escribe un conjunto definido de datos:

* **Leer**: usuarios, contactos, asignaciones de propietarios, posibles clientes, cuentas, oportunidades y actividades.
* **Write**: actividades de alcance registradas (cuando la [sincronización de actividades](#configure-activity-sync-outbound-mapping) está activada) y estado de exclusión.

El administrador de CRM prepara el acceso a la API en Salesforce o Dynamics. A continuación, un administrador de Sales Qualifier conecta el CRM, asigna campos de entrada y elige si desea sincronizar las actividades. La conexión inicial requiere acceso de solo lectura. La sincronización de actividades y la reescritura de exclusión requieren el acceso de escritura correspondiente.

>[!MORELIKETHIS]
>
>* [Introducción](getting-started.md)
>* [Roles y permisos de usuario](user-roles-permissions.md)
>* [Cuentas](accounts.md)
