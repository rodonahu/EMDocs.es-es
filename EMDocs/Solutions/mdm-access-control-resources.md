---
# required metadata

title: Control de acceso a los recursos
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 5967876b-3c08-4498-a0a6-0225b562d35f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Control de acceso a los recursos

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Las organizaciones que ya utilizan Active Directory para autenticar usuarios y autorizarlos ya administran el control de acceso a recursos específicos mediante el uso de grupos en Active Directory con el fin de segmentar y controlar el acceso a los recursos.  

Para administrar el control a recursos específicos, primero autentica y autoriza el acceso del usuario y, a continuación, valida el tipo de control que el usuario posee en el recurso de destino. En la ilustración de abajo, se muestra este proceso para el usuario Bob que está accediendo a una carpeta.

![Flujo de autenticación](./media/MDM_Figure_13.png)

## Flujo básico de autenticación y autorización

La lista de control de acceso (ACL) tradicional es muy limitada y no tiene en cuenta otros aspectos del estado del usuario, como el lugar en el que se encuentra cuando intenta obtener acceso a este recurso. Si su organización necesita incluir más variables antes de conceder acceso a un recurso, puede usar el [control de acceso dinámico](https://technet.microsoft.com/library/dn408191.aspx), que está disponible de forma nativa en Windows Server 2012. Windows 10 admite la característica de atestación de estado, lo que ayuda al departamento de TI a controlar el estado del dispositivo antes de proporcionar acceso a los datos. El servicio de atestación de estado remoto realiza una serie de comprobaciones en las medidas. Valida los puntos de datos relacionados con la seguridad, incluidos el estado de arranque (Arranque seguro, Modo de depuración etc.) y el estado de los componentes que administran la seguridad (BitLocker, Device Guard, etc.). Luego, transmite el estado del dispositivo enviando un blob cifrado de estado al dispositivo. Consulte [Control the health of Windows 10-based devices](https://technet.microsoft.com/en-us/library/mt592023.aspx) (Control del estado de dispositivos basados en Windows 10) para obtener más información.

Los administradores de Intune ahora pueden ver el estado de la característica Atestación de estado de dispositivo de Windows 10 en la [consola de administración de Intune](/intune/deploy/introduction-to-device-compliance-policies-in-microsoft-intune). La atestación de estado del dispositivo permite al administrador garantizar que los equipos cliente tienen configuraciones BIOS, TPM y de arranque de software de confianza. Para admitir la atestación de estado de los dispositivos, los dispositivos cliente deben ejecutar Windows 10 con TPM 2 habilitado. 

Con muchas empresas que actúan por sí mismas como un proveedor de la nube mediante tecnologías que permiten que tengan una nube privada, otra opción es usar el control de acceso basado en roles (RBAC). [Azure AD permite al departamento de TI utilizar RBAC](http://azure.microsoft.com/documentation/articles/role-based-access-control-configure/) para controlar el acceso a los recursos. Como Azure AD puede integrarse con su instancia de Active Directory local, puede utilizarlos juntos para determinar cómo los usuarios accederán a los recursos.

Un recurso puede ser también una aplicación, lo que significa que para implementar el control de acceso a los recursos, la solución MDM también debe ser capaz de controlar la forma en la que se instalan las aplicaciones y cómo se obtiene acceso a ellas. Las [directivas de administración de aplicaciones móviles en Intune](/intune/deployuse/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) permiten modificar la funcionalidad de las aplicaciones que implementa para garantizar que estén en consonancia con las directivas de seguridad y cumplimiento de la compañía. 

Utilice la tabla siguiente como referencia para ayudarle a elegir la opción de MDM que mejor se adapte a los requisitos de control de acceso de la organización.

## Intune (independiente)

**Ventajas**

- Control de acceso para las aplicaciones (instalación y administración) para aplicaciones
- Acceso condicional con el servicio de atestación de estado.

**Desventajas**

- La falta de integración con la plataforma MDM local actual incorporará una interfaz de administración adicional que podrá usar
- Puede que algunas directivas no estén disponibles para algunas plataformas móviles
 
## MDM para Office 365

**Ventajas**

- Control de acceso a correo electrónico, Office Mobile, las aplicaciones de Office y OneDrive para la Empresa.

**Desventajas**

- Solo se permite un reducido subconjunto de control de acceso a recursos.
- La falta de integración con la plataforma MDM local actual incorporará una interfaz de administración adicional que podrá usar
- Puede que algunas directivas no estén disponibles para algunas plataformas móviles

## Híbridas (Intune con Configuration Manager)

**Ventajas**

- Control de acceso para las aplicaciones (instalación y administración) para aplicaciones
- Acceso condicional con el servicio de atestación de estado.

**Desventajas**

- El servicio en la nube de Azure AD no se incluye al adquirir una suscripción a Intune.

## Enterprise Mobility Suite

**Ventajas**

- Control de acceso para las aplicaciones (instalación y administración) para aplicaciones
- Aprovecha Azure AD Premium para proporcionar el control de acceso basado en RBAC.
- Acceso condicional con el servicio de atestación de estado.

**Desventajas**

- Si la organización no dispone de una infraestructura de Configuration Manager local en estos momentos, habrá que planificar, instalar y configurar esta plataforma antes de la integración.


<!--HONumber=Apr16_HO2-->


