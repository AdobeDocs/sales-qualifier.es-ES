---
title: Ajustar configuración de perfil
description: Obtenga información sobre cómo configurar la conexión de correo electrónico, la firma y la disponibilidad del calendario en la configuración del perfil de Sales Qualifier.
feature: Agentic AI, Sales Insights, Account Journeys
role: User
TQID: 'https://experienceleague.adobe.com/juP3sddkmc-nSTcTEKGWolbCwNWDgSA0yr6XK1X-w94'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 17bfe0a1ce9b289ed85af0f72ddd089b11cca875
workflow-type: tm+mt
source-wordcount: 394
ht-degree: 3%

---


# Configuración de perfil

En el panel de navegación izquierdo, expanda **[!UICONTROL Configuración]** y seleccione **[!UICONTROL Configuración del perfil]**. Utilice esta configuración para administrar sus datos personales, la conexión de correo electrónico, el calendario y la disponibilidad del chat.

![Configuración del perfil](assets/profile-email-config.png)

## Configuración de correo electrónico

En la pestaña **[!UICONTROL Configuración de correo electrónico]**, configure las conexiones de correo electrónico.

* **[!UICONTROL Conexiones de correo electrónico]**: seleccione Microsoft Outlook o Google y siga el proceso de inicio de sesión. Consulte [Conectar Outlook](integrations.md#connect-outlook) para obtener acceso que usted apruebe y la ruta de aprobación del administrador, si es necesario.
* **[!UICONTROL Firma de correo electrónico]**: agregue o actualice la firma utilizada en los correos electrónicos generados. Incluya su vínculo [reserva de reuniones](outbound-workflows.md#meeting-booking) para que los posibles clientes puedan programar su hora con usted.
* **[!UICONTROL Vínculo de reserva de reunión]** - Envíe una invitación a una reunión en sus correos electrónicos. Toma la dirección URL de la reunión.

### Contexto de redacción de correo electrónico

![Contexto del correo electrónico](assets/profile-email-instructions.png)

Use **[!UICONTROL Contexto del borrador del correo electrónico]** para establecer el tono, la estructura y el estilo del correo electrónico, de modo que los correos electrónicos sean coherentes.

Escriba su contexto en una marca sin formato en el área de **[!UICONTROL Contexto de borrador de correo electrónico]**.
Utilícelo para definir lo siguiente:

* Tono y voz
* Estructura y longitud
* Personalization y reglas de saludo
* Estilo de línea de asunto
* Uso de las señales de participación
* Cómo se enmarcan las métricas, los puntos de prueba y las historias de los clientes

De forma predeterminada, los borradores utilizan un contexto de estilo house, por lo que los borradores existentes no cambiarán hasta que agregue su propio contexto.

## Configuración del calendario

En la ficha **[!UICONTROL Configuración del calendario]**, establezca la zona horaria y la disponibilidad.

* **[!UICONTROL Conexión del calendario]**—Seleccione **[!UICONTROL Conectar]** y siga el proceso de inicio de sesión de Microsoft.
* **[!UICONTROL Correo electrónico de confirmación de la reunión]**: defina el asunto y el cuerpo del mensaje de correo electrónico de confirmación que recibe un posible cliente después de reservar una reunión.
* **[!UICONTROL Preferencias]**: establezca la longitud de reunión predeterminada y el búfer entre reuniones.

Si desconecta el calendario:

* Los vínculos de reserva activos dejan de funcionar.
* La página de reserva muestra un mensaje de no disponibilidad temporal.
* La configuración se conservará cuando vuelva a conectarse.

## Disponibilidad del calendario

La disponibilidad del calendario en Sales Qualifier se basa en dos entradas:

* Calendario de trabajo conectado, como Outlook o Gmail
* Las reglas de disponibilidad y de franja horaria de **[!UICONTROL Configuración del calendario]**

Sales Qualifier lee el estado de disponibilidad, no los detalles del evento, del calendario conectado. Combina este estado con las reglas para determinar los espacios de tiempo que los posibles clientes pueden reservar.

Puede configurar lo siguiente:

* Horas laborables por día de la semana
* Varios bloques al día, por ejemplo, de 9:00 a.m. a mediodía y de 1:00 a 5:00 p.m.
* Su huso horario
* Duración de la reunión
* Búfer antes y después de las reuniones
* Aviso mínimo
* Ventana de reserva

>[!MORELIKETHIS]
>
>* [Flujos de trabajo salientes](outbound-workflows.md)
>* [Integraciones](integrations.md)
>* [Tareas](tasks.md)
