---
title: Funciones de usuario y permisos
description: Descubra cómo los grupos de usuarios de Sales Qualifier controlan el acceso de la aplicación y la administración.
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
TQID: 'https://experienceleague.adobe.com/9X9DYGMvLGcPG--G6rHcDEk91hdT9-XYc9wbiL2Qoww'
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2: id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4bid: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8573d3891d5c8ec8a05637f160f120f933b0ec61
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 4%

---


# Funciones de usuario y permisos

Sales Qualifier utiliza dos grupos de usuarios necesarios para separar las tareas de ventas de la configuración de toda la organización.

## Grupos de usuarios requeridos

| Grupo | Quién pertenece | Qué concede |
| --- | --- | --- |
| `Sales Qualifier` | Todos los usuarios, incluidos los administradores | Acceso a la aplicación: clientes potenciales, cuentas, flujos de trabajo salientes, tareas, rendimiento y configuración de perfil. |
| `Sales Qualifier Admins` | Solo administradores, además del grupo `Sales Qualifier` | Acceso a **[!UICONTROL Configuración de administración]**, que controla las conexiones CRM, el Centro de conocimientos y la configuración de cumplimiento de normas para toda la organización. |

Los usuarios estándar solo necesitan el grupo `Sales Qualifier`. Los administradores necesitan pertenecer a ambos grupos. Ver [Introducción](getting-started.md) para crear estos grupos.

Las organizaciones también pueden crear un grupo `Sales Qualifier BDR managers` opcional. Los miembros pueden acceder a los informes de rendimiento del correo electrónico.

## Acceso de administrador

**[!UICONTROL Configuración de administración]** aparece en **[!UICONTROL Administración]** solo para los usuarios que pertenecen a ambos grupos requeridos. Los cambios en esta configuración se aplican a toda la organización.

## Qué controlan los administradores

| Configuración | Dónde se configura | Efecto |
| --- | --- | --- |
| Asignación de campos y conexión CRM | [Integraciones](integrations.md#map-crm-fields-inbound-mapping) | Determina qué campos CRM aparecen para un cliente potencial o una cuenta y qué campos están disponibles como filtros. |
| Exclusión de correo electrónico global | [Integraciones](integrations.md#configure-global-email-opt-out) | Agrega un pie de página para cancelar la suscripción a cada correo electrónico saliente. |
| Centro de conocimientos y guía | [Centro de conocimientos](knowledge-center.md) | Hace que el manual de la empresa esté disponible en mensajes salientes y [chat de IA](ai-assistant.md). |
| Sincronización de actividad | [Integraciones](integrations.md#configure-activity-sync-outbound-mapping) | Determina si las actividades de alcance de Sales Qualifier aparecen en CRM. |

Los usuarios estándar pueden utilizar esta configuración, pero no pueden cambiarla. Si falta un filtro, una referencia de manual o un campo CRM esperado, póngase en contacto con un administrador.

>[!MORELIKETHIS]
>
>* [Introducción](getting-started.md)
>* [Integraciones](integrations.md)
>* [Centro de conocimientos](knowledge-center.md)
