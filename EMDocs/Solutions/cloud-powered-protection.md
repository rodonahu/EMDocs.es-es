---
title: "Protección con tecnología de nube"
description: "Este artículo describe cómo Enterprise Mobility + Security puede utilizarse para proporcionar un conjunto completo de herramientas de seguridad para ayudar a la identidad de forma proactiva y responder a amenazas de seguridad de su organización mediante el aprovechamiento de herramientas dentro de Azure Active Directory."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/24/2016
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: 
ms.assetid: 46654ab0-0d0a-47ad-8715-b149a1092a37
ROBOTS: 
ms.reviewer: atkladak, jsnow
ms.suite: ems
ms.openlocfilehash: 0ed7704a832f3567f14c6eec5ae7da9ea5e9f22a
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="cloud-powered-protection"></a>Protección con tecnología de nube
Microsoft se ha dedicado a la protección de identidades basadas en la nube durante más de una década y, con Azure Active Directory, pone estos sistemas de protección a disposición de los clientes empresariales, para asegurar la responsabilidad de los usuarios y de los administradores con una mejor seguridad y control.

## <a name="how-can-enterprise-mobility--security-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security?
Enterprise Mobility + Security (EMS) es la única solución en la nube integral que protege de forma nativa los datos corporativos en el propio dispositivo y más allá con cuatro niveles de protección en las identidades, los dispositivos, las aplicaciones y los datos. EMS le ayuda a resolver uno de los desafíos clave en el mundo que da prioridad a los dispositivos móviles y la nube: cómo proporcionar un completo conjunto de herramientas de seguridad para ayudar proactivamente a la identidad y responder a amenazas de seguridad de su organización:
- Control de acceso a recursos
- Protección de autenticación del usuario
- Respuesta a amenazas avanzadas con directivas basadas en riesgos y supervisión
- Mitigación de los riesgos administrativos
- Control de identidades locales y en la nube

Azure Active Directory Identity Protection es exclusivo. Utiliza Machine Learning para analizar más de 10 TB de datos contextuales y de comportamiento cada día, lo que proporciona visibilidad sobre la actividad sospechosa y le permite tomar acciones inmediatas si es necesario.

Además, las reglas de acceso condicional de Azure AD permiten a los clientes controlar el acceso a servicios en línea, en función de atributos como la ubicación de red o el cumplimiento del dispositivo. A continuación, es posible distinguir:
- Acceso condicional basado en MFA de Azure AD
- Acceso condicional basado en ubicación de Azure AD
- Acceso condicional basado en dispositivo de Azure AD


## <a name="recommended-solution"></a>Solución recomendada
### <a name="azure-active-directory-identity-protection"></a>Azure Active Directory Identity Protection

Azure AD Identity Protection es un servicio de seguridad que proporciona una vista consolidada de eventos de riesgos y posibles vulnerabilidades que afectan a las identidades de su organización:
- Respuesta a amenazas avanzadas con directivas basadas en riesgos y supervisión (Azure AD Identity Protection)
- Mitigación del riesgo de administrador (identidad con privilegios)
- Control de identidad

En un mundo en el que se produce un aumento de las incidencias de robo de identidad, actores no válidos persistentes e infracciones de seguridad frecuentes, Azure Active Directory Identity Protection es un componente indispensable.

El panel de Azure AD Identity Protection proporciona acceso a informes, como usuarios marcados para el riesgo, eventos de riesgos y vulnerabilidades. También proporciona opciones, como la configuración de su registro de autenticación multifactor, las notificaciones y las directivas de seguridad.
### <a name="azure-ad-conditional-access"></a>Acceso condicional de Azure AD
El movimiento a servicios en la nube y una necesidad siempre creciente de movilidad están impulsando a las organizaciones a buscar soluciones que protejan los datos además de mejorar la flexibilidad del dispositivo y la productividad del usuario. Los clientes requieren la capacidad de controlar el acceso a Office 365 según distintos atributos, como la ubicación de red o el cumplimiento de MFA. Esto es especialmente importante para los clientes regulados como los clientes financieros y del gobierno.

Puesto que ya no es suficiente la protección de datos en la red perimetral, las organizaciones también requieren la capacidad de controlar el acceso del usuario según otros factores, como el cumplimiento del dispositivo.

Las reglas de acceso condicional de Azure AD se aplican según la aplicación y están disponibles para que los clientes controlen el acceso basado en condiciones diferentes. Con Mobile Device Management (MDM) para Office 365 o Intune, los clientes deben ser capaces de restringir el acceso a Office 365 únicamente a aquellos usuarios que utilizan un dispositivo de la empresa o que han inscrito sus dispositivos personales para la administración.

Por ejemplo, los clientes pueden configurar reglas de acceso condicional para aplicar controles tales como:
- Solo permitir el acceso desde dispositivos que están unidos al dominio o compatibles
- Aplicar MFA para todo el acceso a los servicios de Exchange Online
- Impedir el acceso a SharePoint Online para un cliente fuera de la red corporativa.

## <a name="how-to-implement-these-solutions"></a>¿Cómo implementar estas soluciones?

Hablemos sobre los pasos necesarios para empezar a utilizar Azure AD Identity Protection y el acceso condicional. Esta sección también proporciona artículos de procedimientos que le proporcionarán más detalles para obtener pasos específicos.

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection
Azure AD Identity Protection está disponible con la oferta Azure AD Premium 2, en combinación con la administración de identidades con privilegios de Azure AD para proporcionar capacidades de directiva de acceso condicional sin problemas.

Puede habilitar la protección de identidad de Azure AD yendo a Azure Marketplace y buscando: "protección de identidad". Después puede hacer clic en el mosaico de protección de identidad de Azure AD, que abrirá el panel con una vista consolidada de los datos de riesgo para el inquilino. Vamos a destacar algunos ejemplos de cómo la protección de identidades puede ayudar a su organización con amenazas de seguridad de la cuenta.

#### <a name="risk-events"></a>Eventos de riesgo
Los eventos de riesgo son eventos que se han marcado como sospechosos por la protección de identidad e indican que se ha comprometido una identidad.

Microsoft seguirá invirtiendo en este espacio y planea mejorar continuamente la precisión de la detección de los eventos de riesgo existentes y agregar nuevos tipos de evento de riesgo de forma continuada. Por ejemplo, le permite investigar el evento de riesgo de viajes imposibles.

Puede encontrar más detalles en la [Guía de Azure AD Identity](https://azure.microsoft.com/en-us/documentation/articles/active-directory-identityprotection-playbook/).

Este es un ejemplo de algunos eventos de riesgo en el panel de Identity Protection:

![Captura de pantalla que muestra algunos eventos de riesgo que aparecen en el panel de Azure AD Identity Protection.](./media/cloud-powered-protection/cloud-powered-protection-fig1.png)

#### <a name="impossible-travels-risk"></a>Riesgo de viaje imposible
Dentro de la hoja de viaje imposible, se muestran todos los incidentes marcados de ubicaciones de inicio de sesión 1ª y 2ª y el tiempo de cada inicio de sesión que se ha producido.

![Captura de pantalla del panel de Azure AD Identity Protection que muestra las ubicaciones de eventos de riesgo de "viajes imposibles".](./media/cloud-powered-protection/cloud-powered-protection-fig2.png)

Puede encontrar más detalles sobre los [tipos de eventos de riesgo detectados por Azure Active Directory Identity Protection](https://azure.microsoft.com/en-us/documentation/articles/active-directory-identityprotection-risk-events-types/).

#### <a name="remediation"></a>Corrección
Además de la solución de incidentes individualmente, Azure AD Identity Protection ofrece la capacidad de resolver los problemas posibles a través de un enfoque proactivo configurando una directiva de corrección de riesgos de usuario. Dentro de la configuración de la directiva, tiene la capacidad de dirigirse a usuarios individuales, grupos o todos los usuarios. También es posible establecer las condiciones específicas, que activarán la directiva.

![Captura de pantalla que muestra cómo solucionar los eventos de riesgo que aparecen en el panel de Azure AD Identity Protection.](./media/cloud-powered-protection/cloud-powered-protection-fig3.png)

Por último, tiene la opción de bloquear totalmente el acceso o permitir el acceso, pero con los requisitos de:
- Multi-factor Authentication
- Registro de Azure MFA
- Cambio de contraseña

Puede encontrar más detalles sobre [Azure AD Identity Protection](https://azure.microsoft.com/en-us/documentation/articles/active-directory-identityprotection/), y sobre esta [movilidad empresarial y la entrada de blog de seguridad](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/07/azuread-identity-protection-azure-ad-privileged-identity-management-and-azure-ad-premium-p2-will-be-generally-available-sept-15th/).

### <a name="azure-ad-conditional-access"></a>Acceso condicional de Azure AD
Los vínculos siguientes proporcionan información para usar el acceso condicional de Azure AD basado en Multi-factor authentication (MFA), la ubicación y las directivas de dispositivo.
- Obtenga información acerca de [cómo implementar el acceso condicional de Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access/).
- Obtenga más información sobre [MFA y directivas de ubicación](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-azuread-connected-apps/).
- Obtenga más información sobre [directivas basadas en el dispositivo](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/).
