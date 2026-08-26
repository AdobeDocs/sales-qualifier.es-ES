---
title: Crear y administrar flujos de trabajo salientes
description: Obtenga información sobre cómo crear, compartir, revisar y administrar flujos de trabajo salientes generados por IA en Sales Qualifier para ejecutar cadencias de alcance impulsadas por objetivos.
feature: Agentic AI, Sales Insights, Account Journeys
role: User
TQID: 'https://experienceleague.adobe.com/n3FbuiM2zF9QSqaKx1bhBSdbsf-w7vEsEGjCQTBo3g4'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8573d3891d5c8ec8a05637f160f120f933b0ec61
workflow-type: tm+mt
source-wordcount: 1905
ht-degree: 0%

---


# Flujos de trabajo salientes

Un flujo de trabajo saliente es una cadencia de alcance orientada a objetivos. El objetivo y los criterios de segmentación se definen. A continuación, IA propone una cadencia multitáctil y escribe contenido de correo electrónico personalizado para cada cliente potencial. Antes de activar la cadencia, revise y apruebe cada correo electrónico.

Un flujo de trabajo saliente conecta cuatro elementos:

* **Objetivo**: el resultado que desea obtener de la divulgación, como reservar una llamada de contacto o aumentar el registro de eventos.
* **Filtros de segmentación**: condiciones que determinan qué clientes potenciales son elegibles.
* **Cadencia de punto de contacto**: la secuencia ordenada de pasos de correo electrónico, llamada de teléfono y LinkedIn In InMail.
* **Contenido de correo electrónico personalizado**: contenido generado por IA basado en el perfil del posible cliente, el contexto de la cuenta, el historial de participación y las noticias recientes.

La API utiliza el objetivo para sugerir filtros de direccionamiento, diseñar la cadencia, redactar mensajes de punto de contacto y personalizar cada correo electrónico generado.

## Conceptos clave

| Concepto | Descripción |
| --- | --- |
| **Flujo de trabajo saliente** | Una actividad saliente reutilizable definida por un objetivo, filtros de objetivo, cadencia y configuración. |
| **Meta** | Lo que debe lograr el alcance. |
| **Punto de contacto** | Un paso en la cadencia (correo electrónico, llamada de teléfono o LinkedIn In InMail), programado en relación con la inscripción. |
| **Mensaje de Touchpoint** | Instrucciones que sigue la IA al generar una línea de asunto y un cuerpo de correo electrónico para un cliente potencial, incluidos el tono, la longitud, el enfoque y el call to action. |
| **Cadencia** | La secuencia completa de puntos de contacto: cuántos, en qué orden y en qué días. |
| **Filtro de segmentación** | Condición que limita el flujo de trabajo saliente a un subconjunto de clientes potenciales. |
| **Borrador** | Un correo electrónico generado que está listo para revisarse, pero aún no se ha aprobado. |
| **Razonamiento** | La explicación de la IA de cómo escribió un correo electrónico determinado, incluidas las señales y las fuentes de datos que utilizó. |
| **Inscripción** | Aprobación de los borradores de un cliente potencial, que activa la cadencia y pone en cola los correos electrónicos que se enviarán durante la ventana de envío del flujo de trabajo saliente. |

En las siguientes secciones se explica cómo crear un flujo de trabajo saliente, revisar los correos electrónicos generados, aprobar clientes potenciales y administrar los flujos de trabajo salientes.

## Crear un flujo de trabajo saliente

El asistente de flujo de trabajo saliente consta de cinco pasos: **[!UICONTROL Objetivo]**, **[!UICONTROL Segmentación]**, **[!UICONTROL Generar puntos de contacto]**, **[!UICONTROL Configuración]** y **[!UICONTROL Agregar perspectivas]**. El objetivo da forma a los pasos restantes.

1. En el panel de navegación izquierdo, seleccione **[!UICONTROL Flujos de trabajo de salida]**.
1. En la ficha **[!UICONTROL Examinar]**, seleccione **[!UICONTROL + Crear flujo de trabajo saliente]** en la esquina superior derecha.

### Paso 1: Defina su objetivo

El objetivo define el resultado deseado y guía la segmentación, la cadencia y la generación de correo electrónico.

1. Seleccione **[!UICONTROL Comenzar desde cero]** para escribir su propia meta o seleccione **[!UICONTROL Comenzar desde la plantilla]** para usar una plantilla guardada.

1. Seleccione una de las **[!UICONTROL metas recomendadas]** que coincida con su compañía. Cada recomendación incluye una breve explicación de por qué encaja. Seleccione una recomendación para completar la meta, seleccione **[!UICONTROL Ver todas]** para examinar el conjunto completo de recomendaciones o ingrese su propio objetivo. También puedes elegir de la lista **[!UICONTROL Metas populares]**.
1. Seleccione **[!UICONTROL Siguiente: Segmentación]**.

Indique un resultado específico en la meta. Por ejemplo, escriba `Book a 15-minute discovery call with marketing leaders evaluating campaign automation` en lugar de `Promote campaign automation`.

### Paso 2: Configuración de los filtros de segmentación

Los filtros de segmentación definen qué clientes potenciales son aptos. Cuando se agregan perspectivas más adelante, sólo aparecen en la lista de selección los posibles clientes que coinciden con estos filtros.

![Filtros de segmentación](assets/create-workflow-targeting.png){width="800" zoomable="yes"}

1. Seleccione la flecha hacia abajo para abrir la lista **[!UICONTROL Agregar un filtro]** y, a continuación, seleccione un filtro.

1. Establezca valores para el filtro.
1. Añada más filtros si necesita reducir la audiencia.

1. Seleccione **[!UICONTROL Siguiente: Generar puntos de contacto]**.

### Paso 3: Generar y revisar puntos de contacto

Después de configurar el direccionamiento, la IA analiza el objetivo y los criterios de direccionamiento, define la cadencia y escribe un mensaje para cada punto de contacto. La cadencia puede incluir pasos de correo electrónico, llamada de teléfono y LinkedIn In InMail.

![Puntos de contacto](assets/create-workflow-touchpoints.png){width="800" zoomable="yes"}

Expanda un punto de contacto de correo electrónico para leer su solicitud. El mensaje guía la IA a medida que escribe el correo electrónico de cada posible cliente, incluido el tono, la longitud, el enfoque y el call to action.

#### Regeneración de la cadencia

Si la cadencia no es la deseada, seleccione **[!UICONTROL Volver a generar]** e introduzca una instrucción de refinamiento. Por ejemplo:

* `Use three touchpoints across two weeks`
* `Lead with an executive briefing offer in the first email`
* `Add a nurture touch focused on a relevant case study`

AI reescribe la cadencia completa en función de sus instrucciones. Para ajustar un punto de contacto de correo electrónico, edite su mensaje en lugar de regenerar toda la cadencia.

Establezca un retraso de punto de contacto en días, horas y minutos. Establezca los días, horas y minutos en `0` para enviar el punto de contacto sin esperar después de inscribirse o finalizar el punto de contacto anterior. Utilice un retraso más largo para espaciar los puntos de contacto posteriores dentro de la cadencia.

#### Uso del Centro de conocimiento en las indicaciones

Si su organización ha creado un manual de [Centro de conocimiento](knowledge-center.md), consulte el manual. Asigne un nombre al documento y describa el contexto que desea utilizar. Por ejemplo, escriba `Use the ABC positioning guide from the Knowledge Center and focus on the security value proposition`.

Cuando la cadencia y las indicaciones estén listas, seleccione **[!UICONTROL Siguiente: Configuración]**.

Restrinja las indicaciones del punto de contacto antes de generar correos electrónicos de clientes potenciales. AI utiliza estos mensajes para cada cliente potencial seleccionado.

### Paso 4: Configurar el flujo de trabajo saliente

El paso **[!UICONTROL Configuración]** controla cómo se ejecuta el flujo de trabajo saliente.

![Panel de configuración](assets/create-workflow-settings.png){width="800" zoomable="yes"}

1. Revise **[!UICONTROL nombre de flujo de trabajo saliente]** y cámbielo si es necesario.
1. En **[!UICONTROL Máximo de clientes potenciales por flujo de trabajo saliente]**, confirme el número máximo de clientes potenciales que el flujo de trabajo saliente puede administrar a la vez.
1. Establece la ventana de **[!UICONTROL envío]** para las horas en las que se permite enviar correos electrónicos salientes.
1. Seleccione los días de la semana en los que se pueden enviar correos electrónicos. Para evitar envíos de fin de semana, selecciona solo los días de la semana en lugar de usar una configuración **[!UICONTROL Omitir fines de semana]** por separado.
1. Elija si desea enviar durante las horas más activas de cada posible cliente.
1. Para detener automáticamente los puntos de contacto de seguimiento una vez que el posible cliente reserve una reunión, active **[!UICONTROL Pausa para reserva de reuniones]**.
1. Elija si desea utilizar la zona horaria de cada cliente potencial o el flujo de trabajo saliente **[!UICONTROL Timezone]** para el tiempo de envío. Si utiliza la zona horaria del flujo de trabajo saliente, confirme que coincide con la audiencia.
1. En **[!UICONTROL Permisos]**, mantenga **[!UICONTROL Privado]** (predeterminado) o seleccione **[!UICONTROL Compartido con todos]**. Para obtener más información, consulte [Compartir un flujo de trabajo saliente](#share-an-outbound-workflow).
1. Seleccione **[!UICONTROL Guardar y agregar clientes potenciales]**.

Un administrador configura globalmente el pie de página de exclusión y se aplica a los correos electrónicos salientes independientemente de la configuración del flujo de trabajo saliente. Consulte [Configurar la exclusión de correo electrónico global](integrations.md#configure-global-email-opt-out).

### Paso 5: Añadir clientes potenciales e iniciar la generación de correo electrónico

Guardar abre la vista de selección de clientes potenciales con los filtros de objetivo del paso 2 aplicados.

1. Revise la lista.

   Las filas suelen incluir el nombre del cliente potencial, la cuenta, el correo electrónico, el puesto, el estado de participación y el estado del cliente potencial.

1. Ajuste los filtros aquí si necesita expandir o reducir la lista.
1. Seleccione los clientes potenciales mediante las casillas de verificación.
1. Seleccione **[!UICONTROL Siguiente: revise los puntos de contacto]** para iniciar la generación de correo electrónico por cliente potencial.

AI genera un correo electrónico personalizado para cada cliente potencial y punto de contacto de correo electrónico seleccionados. Los puntos de contacto de Phone y LinkedIn In InMail siguen siendo pasos programados. Para continuar trabajando durante la generación, seleccione **[!UICONTROL Notificar cuando esté listo]**.

Para cada cliente potencial, la IA combina el mensaje del punto de contacto con los datos de la persona y la cuenta, el historial de participación y las noticias recientes para producir una línea de asunto y un cuerpo.

## Revisar y perfeccionar correos electrónicos generados

Cuando finalice la generación, la vista de detalles Flujo de trabajo saliente le pedirá que revise los borradores. Sales Qualifier no envía correos electrónicos hasta que el usuario los aprueba.

1. En la vista de detalles del flujo de trabajo saliente, seleccione **[!UICONTROL Revisar borradores]** en el banner.
1. El paso **[!UICONTROL Revisar puntos de contacto]** tiene dos pestañas:
   * **[!UICONTROL Listo para revisión]**: correos electrónicos que se terminaron de generar.
   * **[!UICONTROL Generando]**: correos electrónicos que se siguen escribiendo.
1. En la lista de clientes potenciales de la izquierda, seleccione un nombre para cargar los puntos de contacto de ese cliente potencial a la derecha.
1. Use las comillas angulares (**>**) en un punto de contacto para expandir y leer la línea de asunto y el cuerpo completos.

### Lea el razonamiento de IA

Para cada correo electrónico generado, **[!UICONTROL Reasoning]** explica cómo la IA creó ese mensaje, incluidas las señales, atributos y fuentes que dieron forma al contenido y a call to action. Revise esta información y valide la personalización antes de aprobarla.

### Editar correos electrónicos directamente

Para cambios pequeños de redacción o de tono:

1. En el punto de contacto expandido, seleccione el icono **[!UICONTROL Editar]** para abrir el editor.
1. Edite la línea de asunto o el cuerpo.
1. Seleccione **[!UICONTROL Guardar]**.

### Refinamiento de correos electrónicos con IA

Para cambios estructurales o de énfasis, use **[!UICONTROL Generar con IA]**. AI reescribe el correo electrónico y mantiene su contexto de personalización.

1. En el editor de correo electrónico, seleccione **[!UICONTROL Generar con IA]**.

1. Introduzca una instrucción de borrado, por ejemplo:
   * `Make it shorter and more direct. Keep it under 100 words.`
   * `Focus more on the prospect's role and how the solution helps them specifically.`
   * `Change the call-to-action to suggest a 15-minute introductory call instead.`
1. Revise la revisión y edítela si es necesario.
1. Seleccione **[!UICONTROL Guardar]**.

>[!TIP]
>
>Utilice ediciones directas para los cambios de redacción y tono. Use **[!UICONTROL Generar con IA]** para reescribir el correo electrónico.

## Aprobar e inscribir clientes potenciales

La aprobación activa la cadencia de un cliente potencial. El sistema no envía correos electrónicos a un cliente potencial hasta que usted los aprueba e inscribe.

1. En la lista de clientes potenciales de la izquierda, seleccione los clientes potenciales cuyos correos electrónicos ha revisado y que están listos para enviar.
1. Seleccione **[!UICONTROL Aprobar e inscribir clientes potenciales]** en la esquina inferior derecha.

Los correos electrónicos aprobados se envían según los días seleccionados, la ventana de envío, la opción de horas activas y la configuración de zona horaria del flujo de trabajo saliente. Un punto de contacto con un retraso cero envía sin espera; cada uno de los demás puntos de contacto sigue su retraso configurado. Los posibles clientes no aprobados permanecen en **[!UICONTROL Listo para revisión]**.

## Compartir un flujo de trabajo saliente

Cada flujo de trabajo saliente tiene una configuración **[!UICONTROL Permissions]**. Los flujos de trabajo salientes son **[!UICONTROL Privados]** de manera predeterminada. El propietario puede seleccionar **[!UICONTROL Compartido con todos]** para que el equipo disponga de un flujo de trabajo saliente.

>[!CAUTION]
>
>Compartir es permanente. Después de establecer un flujo de trabajo saliente en **[!UICONTROL Compartido con todos]**, no se puede volver a cambiar a **[!UICONTROL Privado]**.

En un flujo de trabajo saliente compartido, los compañeros de equipo pueden inscribir a sus propios posibles clientes. Cada persona puede administrar o pausar solo los clientes potenciales en los que se ha inscrito, incluso cuando se utilizan acciones masivas. El propietario del flujo de trabajo saliente solo puede editar la configuración del nivel de plan, incluida la programación, la zona horaria, la cadencia y otras opciones. Esta configuración es de solo lectura para compañeros de equipo.

Utilice estos filtros para mantener centrados los flujos de trabajo salientes compartidos y los resultados:

* En **[!UICONTROL clientes potenciales comprometidos]** y **[!UICONTROL Rendimiento]**, use **[!UICONTROL Inscrito por]** para filtrar los posibles clientes por la persona que los inscribió. El filtro toma como valor predeterminado los posibles clientes que ha inscrito.
* En la ficha **[!UICONTROL Examinar]**, use el filtro para compartir para seleccionar **[!UICONTROL Compartido por mí]**, **[!UICONTROL Compartido conmigo]**, **[!UICONTROL Privado]** o **[!UICONTROL Todos]**.

## Administración de respuestas fuera de la oficina

Cuando un cliente potencial responde con un mensaje fuera de la oficina, el flujo de trabajo saliente lo gestiona automáticamente.

* **Reanudación automática**: activada de forma predeterminada. Si la respuesta fuera de la oficina incluye una fecha de retorno, el flujo de trabajo saliente reanuda la cadencia en esa fecha. Si no se indica ninguna fecha de retorno, el flujo de trabajo saliente se reanuda después de un búfer de reanudación después de que su equipo pueda configurar.
* **Opciones manuales**: un representante aún puede seleccionar **[!UICONTROL Reanudar ahora]** o programar una fecha de reanudación específica. Ver [Administrar flujos de trabajo salientes existentes](#manage-existing-outbound-workflows).

## Administrar flujos de trabajo salientes existentes

En la página **[!UICONTROL Flujos de trabajo salientes]**, la pestaña **[!UICONTROL Examinar]** muestra todos los flujos de trabajo salientes que tiene disponibles. Cada tarjeta muestra el objetivo, los puntos de contacto configurados y las métricas de rendimiento. Utilice esta vista para monitorizar flujos de trabajo salientes, revisar borradores o agregar clientes potenciales.

## Bandeja de salida de correo

La [Bandeja de salida de correo electrónico](email-outbox.md) enumera los mensajes de correo electrónico automatizados enviados en su nombre y las respuestas.

## Reserva de reuniones

Al conectar el calendario, Sales Qualifier genera un vínculo de reserva personal que los posibles clientes pueden utilizar para programar el tiempo con usted.

* **Vínculos de reserva**: configure la conexión y disponibilidad del calendario en [Configuración del perfil](profile-settings.md). Añada el vínculo de reserva a su firma de correo electrónico para que aparezca en los correos electrónicos salientes.
* **Colocación de cadencia**: Sales Qualifier inserta el vínculo de reserva en los puntos relevantes de una cadencia. Puede cambiar su ubicación.
* **Pausa para reservas**: cuando un cliente potencial reserva una reunión, **[!UICONTROL Pausa para reservas de reuniones]** detiene más seguimientos. Consulte [Paso 4: Configurar los parámetros de flujo de trabajo de salida](#step-4-configure-outbound-workflow-settings).

Rastrear resultados de reservas en la página [Rendimiento de salida](performance.md).

## Prácticas recomendadas de flujo de trabajo saliente

* **Definir una meta específica.** El direccionamiento, la cadencia y los correos electrónicos se derivan del objetivo. Indique el resultado que desea que alcance el flujo de trabajo saliente.
* **Finalizar mensajes de punto de contacto antes de la generación por cliente potencial.** Después de la generación masiva, los cambios se suelen realizar de un cliente potencial a la vez.
* **Usar razonamiento como comprobación de calidad.** Si se enfatiza la señal incorrecta o falta una señal relevante, edite el correo electrónico o revise el mensaje del punto de contacto y vuelva a generar la cadencia.
* **Hacer coincidir la herramienta de edición con el cambio.** Utilice ediciones directas para la redacción y el tono. Use **[!UICONTROL Generar con IA]** para reestructurar o reformular.
* **Aprobar solo lo que ha revisado.** Amplíe los puntos de contacto, lea el contenido y perfeccione lo que necesite antes de inscribirse.

>[!MORELIKETHIS]
>
>* [Tareas](tasks.md)
>* [Centro de conocimientos](knowledge-center.md)
>* [Rendimiento de salida](performance.md)
