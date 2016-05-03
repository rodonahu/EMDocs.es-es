---
# required metadata

title: Autenticación y autorización
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 31b98333-5a3d-49ba-a25e-66447df68035

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Autenticación y autorización

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Antes de que pueda proteger adecuadamente los datos de su compañía, debe identificar quiénes son los usuarios y, a continuación, podrá comprobar que están autorizados para obtener acceso al recurso que están solicitando. Las organizaciones que ya tengan servicios de Active Directory locales deben aprovecharlos para autenticar y autorizar usuarios móviles. Todas las soluciones de administración de dispositivos móviles de Microsoft pueden usar una infraestructura de Active Directory existente para hacerlo. 

Otro punto de decisión con respecto a la autenticación y a la autorización es dónde se ubicarán los servicios de directorio. Aunque la mayoría de las organizaciones tendrán servicios de Active Directory locales, algunas organizaciones podrían estar considerando la posibilidad de extender sus servicios de directorio locales con un servicio de directorio en la nube como [Azure AD](http://azure.microsoft.com/documentation/articles/active-directory-whatis/). 

Configuration Manager puede integrarse con [Microsoft Passport for Work](https://technet.microsoft.com/library/mt488797.aspx), que es un método alternativo de inicio de sesión que usa Active Directory, o una cuenta de Azure Active Directory, para reemplazar una contraseña, una tarjeta inteligente o una tarjeta inteligente virtual en dispositivos que ejecutan Windows 10. En escenarios híbridos, se recomienda como alternativa integrar los dos directorios para aprovechar las funcionalidades de Azure AD, como las siguientes:

- **Administración de grupos de autoservicio:** permite a los usuarios crear grupos, solicitar acceso a otros grupos, delegar la propiedad del grupo para que otros puedan aprobar solicitudes y mantener su pertenencia a grupos.
- **SLA de Enterprise del 99,9 %**: garantizamos una disponibilidad del 99,9 % como mínimo del servicio Premium de Azure Active Directory.
- **Restablecimiento de contraseña mediante reescritura**: el restablecimiento de contraseña de autoservicio puede volver a escribirse en directorios locales.

Puede obtener más información acerca de las distintas opciones y capacidades en [Azure Active Directory](https://msdn.microsoft.com/library/azure/dn532272.aspx).
Requerir dos tipos de autenticación (la autenticación multifactor o MFA) es otra estrategia que hay que considerar incluir cuando se realice la planificación de una solución de administración de dispositivos móviles. Intune puede [integrar servicios de directorio con la autenticación multifactor (MFA)](https://technet.microsoft.com/library/dn889751.aspx), que agrega otro nivel de seguridad para el proceso de autenticación. 

Si su organización tiene una infraestructura de TI local que incluye un dominio de Active Directory con Servicios de federación de Active Directory (AD FS), puede configurar MFA en el servidor de federación y, después, habilitarla para la inscripción en Intune. Si configura MFA en el servidor de federación, pero no habilita MFA para la inscripción en Intune, los usuarios deberán usar MFA cada vez que dispongan de acceso a los recursos corporativos desde cualquier dispositivo. 

También puede usar Azure AD MFA para requerir MFA cada vez que los usuarios obtengan acceso a los recursos corporativos, y este requisito se puede habilitar en cada usuario. Azure AD MFA es un servicio en la nube que no requiere una infraestructura de TI local.

Utilice la tabla siguiente como referencia para ayudarle a elegir la opción de MDM que mejor se adapte a los requisitos de autenticación y autorización de su organización.

## Intune (independiente)

**Ventajas**

- Puede usar servicios de directorio locales, como Active Directory para la autenticación.
- Puede usar servicios de directorio basados en la nube, como Azure AD para la autenticación.
- Se puede integrar con la autenticación multifactor

**Desventajas**

- El servicio en la nube de Azure AD no se incluye al adquirir una suscripción a Intune.

## MDM para Office 365

**Ventajas**

- Puede usar el directorio local, como Active Directory para la autenticación.
- Puede usar el directorio basado en la nube, como Azure AD para la autenticación.
- Se puede integrar con la autenticación multifactor
- Puede aprovechar el centro de cumplimiento para utilizar el modelo de permisos de control de acceso basado en roles (RBAC).

**Desventajas**

- El servicio en la nube de Azure AD no se incluye al adquirir una suscripción a Office 365.

## Híbridas (Intune con Configuration Manager)

**Ventajas**

- Puede usar el directorio local, como Active Directory para la autenticación.
- Puede usar el directorio basado en la nube, como Azure AD para la autenticación.

**Desventajas**

- El servicio en la nube de Azure AD no se incluye al adquirir una suscripción a Intune.

## Enterprise Mobility Suite

**Ventajas**

- Aprovecha Azure AD Premium para proporcionar control de acceso.
- La licencia de Azure AD Premium ya se incluye con EMS.
- No requiere servicios de directorio locales
- Puede sincronizarse con los servicios de Active Directory locales.
- MFA está disponible de forma nativa con EMS.

**Desventajas**

- No está disponible para los clientes que no estén adoptando soluciones basadas en la nube.



<!--HONumber=Apr16_HO2-->


