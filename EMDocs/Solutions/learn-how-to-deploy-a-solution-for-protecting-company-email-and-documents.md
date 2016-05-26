---
# required metadata

title: Aprenda a implementar una solución para proteger los documentos y correos electrónicos de su empresa
description:
keywords:
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 2e10af43-3138-45c0-b2f7-14a1d2bfb237

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Aprenda a implementar una solución para proteger los documentos y correos electrónicos de su empresa
Las empresas, cada vez con más frecuencia, permiten que sus empleados obtengan acceso al correo electrónico, los documentos y los recursos de la empresa a través de sus dispositivos móviles para así aumentar su productividad. Sin embargo, la cantidad de información confidencial que existe en los documentos y los mensajes de correo electrónico corporativos representa un riesgo de seguridad importante para las empresas.

Con esta guía, esperamos que los profesionales de TI puedan determinar e implementar las mejores soluciones para su empresa y aplicar la directiva de acceso condicional en una de las configuraciones, tal como se describe a continuación. Gracias a ello, los empleados podrán usar sus dispositivos móviles para acceder a los mensajes de correo electrónico de su empresa a la vez que se mantienen los datos protegidos.

En esta sección se trata el proceso para implementar una solución que permita proteger los documentos y correos electrónicos de su empresa. Para obtener más información sobre la arquitectura de estas soluciones, consulte [Guía de arquitectura para proteger los documentos y correos electrónicos de la empresa](architecture-guidance-for-protecting-company-email-and-documents).

> [!TIP]
> Obtenga una copia descargable de este tema completo en la [Galería de TechNet](https://gallery.technet.microsoft.com/Deploying-Enterprise-16499404).

## Introducción
Proteger los datos de su empresa es de vital importancia y supone un desafío que no deja de aumentar en complejidad, ya que cada vez más empleados usan sus dispositivos móviles para obtener acceso a recursos de la empresa como el correo electrónico y sus datos adjuntos. Como administrador de TI, debe asegurarse de que los datos de la empresa están protegidos incluso cuando los dispositivos móviles no están dentro de la ubicación física de la empresa.

El servicio Microsoft Enterprise Mobility Suite (EMS) le ofrece una solución para este desafío, ya que le otorga protección completa de documentos y de correos electrónicos corporativos en cuatro niveles: identidad, dispositivos, aplicaciones y datos. Entre otras funciones, EMS le garantiza que los empleados solo podrán obtener acceso al correo electrónico corporativo desde aquellos dispositivos que estén administrados por Microsoft Intune y que cumplan las directivas de TI.

La protección del correo electrónico corporativo implica dos objetivos principales:

-   **Permitir solo a aquellos dispositivos que cumplan las directivas acceder al correo electrónico de la empresa:** un paso importante para proteger los datos corporativos es restringir el acceso a los dispositivos que no utilizan una contraseña segura, que no tengan jailbreak o que estén sin cifrar.  Microsoft Intune le ofrece la capacidad de establecer las condiciones que los usuarios deben cumplir para obtener acceso a los recursos de la empresa. Esto se conoce como acceso condicional.

-   **Proteger el contenido de los correos electrónicos y los datos adjuntos:** aunque la directiva de acceso condicional le permite asegurarse de que solo los dispositivos que cumplen los requisitos tengan acceso al correo electrónico, siempre queda la cuestión de proteger el contenido del correo electrónico y de los datos adjuntos.  El contenido se puede copiar, mover, guardar en una ubicación diferente o compartir con otro usuario.  EMS soluciona este problema mediante directivas de administración de aplicaciones móviles.

    Las aplicaciones administradas son aplicaciones que tienen directivas de administración de aplicaciones móviles que las hacen compatibles con los requisitos de seguridad de su empresa. Con estas aplicaciones, tendrá control directo sobre las implementaciones, la administración continua (como el inventario o las actualizaciones) y el borrado selectivo de aplicaciones y sus datos asociados. Asimismo, a través de un conjunto de directivas de administración de aplicaciones móviles (MAM), Intune le permite modificar la funcionalidad de las aplicaciones y restringir los datos que se comparten. Para obtener más detalles sobre el funcionamiento de esta solución, incluidos los detalles de la arquitectura, consulte [Proteger documentos y correo electrónico corporativos](architecture-guidance-for-protecting-company-email-and-documents).

    > [!NOTE]
    > Puede crear y distribuir un perfil de correo electrónico para, a continuación, establecer una directiva de cumplimiento que especifique que los perfiles de correo electrónico deben administrarse mediante Intune (recomendado). Esto le ofrece la posibilidad de borrar correos electrónicos desde dispositivos retirados y le garantiza que, para iOS, los datos adjuntos solo se puedan abrir en aplicaciones administradas por Intune. Vea [Paso 5: cree directivas de cumplimiento y distribúyalas a los usuarios](conditional-access-intune-configmgr-exchange.md). para obtener más información.

### Soluciones que se examinan en este artículo
Esta sección proporciona información general de cada solución: Configuration Manager con implementación de Intune, Intune por sí solo, la administración de aplicaciones móviles y el servicio Azure Rights Management.

-   **Administrar el acceso al correo electrónico mediante la directiva de acceso condicional**: puede usar una combinación de Configuration Manager con Intune, o simplemente usar Intune con Exchange Online o el servicio local Exchange Server, para administrar y aplicar la directiva de acceso condicional en todos los tipos de equipos y dispositivos móviles, independientemente de su ubicación. Si aplica la directiva de acceso condicional en este tipo de entorno, podrá permitir que los usuarios sean más productivos mientras mantiene seguros los datos de la empresa.

-   **Proteger los datos adjuntos de los correos electrónicos mediante la solución MAM**: puede aplicar directivas de administración de aplicaciones móviles (MAM) en Intune para modificar la funcionalidad de las aplicaciones que se implementan en su empresa. Por ejemplo, puede limitar las operaciones de cortar, copiar y pegar dentro de una aplicación administrada, o configurar una aplicación para abrir todos los vínculos web dentro de un explorador administrado. Esto garantiza que esas aplicaciones estén en consonancia con las directivas de cumplimiento y seguridad de la empresa.

-   **Directivas de prevención de pérdida de datos del servicio Azure Rights Management**: el servicio Azure Rights Management (Azure RMS) usa directivas de autorización, identidad y cifrado para ayudarle a proteger los archivos y correos electrónicos en varios dispositivos, como teléfonos, tabletas y equipos. Puede mantener protegida la información tanto dentro como fuera de la empresa, ya que los datos permanecen protegidos incluso si el usuario sale de los límites de la empresa.

### Evaluar la implementación
Con todas las opciones de diseño y configuración diferentes que existen para administrar dispositivos móviles, es difícil determinar cuál es la combinación que mejor se adapta a las necesidades de su empresa. La [Guía de consideraciones de diseño de administración de dispositivos móviles](mdm-design-considerations-guide.md) le ayudará a comprender los requisitos de diseño de la administración de dispositivos móviles y le proporcionará detalles para seguir una serie de pasos y tareas que le ayudarán a diseñar la solución que mejor se adapte a las necesidades tecnológicas y de negocio de su empresa.

### Experiencia de alto nivel del usuario final
Después de implementar la solución, los usuarios finales solo podrán obtener acceso al correo de la empresa mediante dispositivos administrados **y** que cumplan los requisitos establecidos. Una vez que tengan acceso al correo electrónico en sus dispositivos, los datos de la empresa estarán protegidos y se guardarán en el ecosistema de la aplicación, por lo que solo estarán disponibles para ciertos usuarios. El acceso se puede revocar en cualquier momento si el dispositivo no cumple con los requisitos establecidos.

En concreto, las directivas de acceso condicional de Intune garantizan que los dispositivos solo puedan tener acceso al correo electrónico si cumplen con las directivas de cumplimiento establecidas. Acciones tales como copiar y pegar o guardar datos en servicios personales en la nube, pueden restringirse mediante directivas de administración de aplicaciones móviles. El servicio Azure Rights Managements puede usarse para garantizar que solo los destinatarios puedan leer los datos de los correos electrónicos confidenciales y los datos adjuntos reenviados. La experiencia del usuario final se describe con más detalle en [Experiencia de acceso condicional del usuario final](end-user-experience-conditional-access.md).

### Próximos pasos
Ahora que ha leído este tema, puede obtener más información cómo implementar una solución específica para la protección del correo electrónico y los documentos de la empresa en función del entorno:

- [Uso del acceso condicional con Microsoft Intune](conditional-access-intune.md)
- [Uso del acceso condicional con Microsoft Intune y Configuration Manager](conditional-access-intune-configmgr.md)


<!--HONumber=Apr16_HO4-->


