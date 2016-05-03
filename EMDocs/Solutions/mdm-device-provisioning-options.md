---
# required metadata

title: Opciones de aprovisionamiento de dispositivos
description:
keywords:
author: robmazz
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 991cd722-089c-4e8c-80b9-b82e405cc891

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Opciones de aprovisionamiento de dispositivos

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Cuando un usuario puede usar e inscribir su propio dispositivo, esto aumenta los requisitos para el usuario y la TI, y afecta a varias áreas. Por ejemplo, la siguiente ilustración muestra una visión general del proceso de inscripción para una organización que usa Intune y Configuration Manager. En este ejemplo se describe el certificado, la aplicación web y las consideraciones de sincronización que debe tener en cuenta cuando planifique la solución:

![Información general del proceso de inscripción para dispositivos móviles Configuration Manager e Intune híbrido](./media/MDM_Figure_04.png)

**Información general del proceso de inscripción para dispositivos móviles Configuration Manager e Intune híbrido**

1. Con <token>Windows Server 2012 R2, se ha introducido un nuevo concepto conocido como "registro de dispositivos".  Los usuarios pueden registrar sus dispositivos para el inicio de sesión único y obtener acceso a datos corporativos mediante la unión al área de trabajo.  Como parte de este proceso de registro, se instala un certificado en el dispositivo. A cambio de registrar su dispositivo y hacer que la solución de administración de dispositivos lo conozca, el usuario obtiene acceso a los recursos corporativos que antes no estaban disponibles fuera de sus PC unidos al dominio.
2. Los usuarios pueden inscribir dispositivos que configuren el dispositivo para la administración mediante el [uso del portal de empresa](/Intune/deployuse/enroll-devices-in-microsoft-intune), y, luego, utilizar Portal de empresa de Microsoft Intune para facilitar el acceso a aplicaciones corporativas y datos para ser capaces de administrar sus propios dispositivos y realizar tareas como el borrado remoto del dispositivo en el caso pérdida, robo o reemplazo.
3. Puede publicar el acceso a los recursos corporativos con la capacidad incorporada disponible en Windows Server 2012 R2 denominada [Proxy de aplicación web](https://technet.microsoft.com/library/dn584107.aspx) según el reconocimiento de dispositivos (es decir, se registra) y la identidad de los usuarios. Si utiliza Enterprise Mobility Suite, también puede publicar aplicaciones mediante el Proxy de aplicación de Azure AD. Se puede utilizar la autenticación multifactor mediante la [autenticación activa de Azure](https://azure.microsoft.com/documentation/articles/multi-factor-authentication-get-started-cloud/).
4. Para proporcionar a los administradores una vista unificada del entorno completo, los datos de Intune se sincronizan con Configuration Manager, que permite una administración unificada de forma local y en la nube.
5. Como parte del proceso de inscripción, se crea un nuevo objeto de dispositivo en Active Directory.  Este objeto de dispositivo establece un vínculo entre el usuario y su dispositivo, lo que hace que la solución de administración de dispositivos lo conozca y permite que el dispositivo se autentique a través de una autenticación de dos factores sin problemas y efectiva.

Según como haya respondido a las preguntas del paso 1, podrá determinar cómo quiere que sus dispositivos se administren en la solución de administración de dispositivos móviles. La lista siguiente muestra a continuación las ventajas y desventajas de cada opción de aprovisionamiento.

## Intune (independiente)

**Ventajas**

- Admite el aprovisionamiento y la inscripción de todos los sistemas operativos de dispositivos móviles principales (Android, iOS, Windows 10, Windows 8.x y Windows Phone)
- Los dispositivos móviles de servicios basados en la nube pueden inscribirse desde cualquier ubicación con acceso a Internet
- Los dispositivos pueden inscribirse a través de un portal de empresa personalizable y centralizado
- Opciones de aprovisionamiento de dispositivos avanzadas para dispositivos móviles

**Desventajas**

- Interfaz de administración adicional para el aprovisionamiento de dispositivos móviles (solo) si se usa una plataforma de administración local para dispositivos que no son móviles
- Directivas de seguridad y cumplimiento de dispositivo independiente para la plataforma de administración local y de servicio basado en la nube 

## MDM para Office 365

**Ventajas**

- Ofrece una integración con inquilinos de Office 365, lo que proporciona una consola de administración única para dispositivos móviles y servicios de inquilinos de Office 365 (SharePoint Online y Skype Empresarial).
- Admite el aprovisionamiento y la inscripción de todos los sistemas operativos de dispositivos móviles principales (Android, iOS, Windows 10, Windows 8.1 y Windows Phone)
- Opciones de aprovisionamiento de dispositivos básicas para dispositivos móviles

**Desventajas**

- Interfaz de administración adicional para el aprovisionamiento de dispositivos móviles (solo) si se usa una plataforma de administración local para dispositivos que no son móviles
- Directivas de seguridad y cumplimiento de dispositivo independiente para la plataforma de administración local y de servicio basado en la nube
- Opciones de aprovisionamiento de dispositivos menos avanzadas

## Híbridas (Intune con Configuration Manager)

**Ventajas**

- Integración nativa entre Intune (servicio de administración de dispositivos basada en la nube) con System Center 2012 Configuration Manager y System Center 2012 R2 Configuration Manager (plataformas de administración de dispositivos locales).
- Admite la inscripción y el aprovisionamiento de todos los sistemas operativos de dispositivos móviles importantes (Android, iOS y Windows Phone) e incluye el aprovisionamiento para todos los sistemas operativos de dispositivos que no son móviles importantes
- Admite opciones de aprovisionamiento de dispositivos avanzadas para dispositivos móviles a través de la conectividad de Intune.

**Desventajas**

- Para las organizaciones que no tienen una infraestructura de Configuration Manager en estos momentos, habrá que planificarla, instalarla y configurarla antes de su integración con Intune.
- Requiere opciones de configuración adicionales para conectar Intune con la infraestructura de Configuration Manager local.

Para obtener más detalles acerca de las opciones de aprovisionamiento e inscripción de dispositivos móviles, asegúrese de revisar cómo [habilitar las inscripciones en dispositivos móviles](/Intune/deployuse/enroll-devices-in-microsoft-intune) en y comparar estos requisitos y procedimientos para [habilitar las inscripciones en dispositivos móviles](https://technet.microsoft.com/library/jj884158.aspx) en Configuration Manager y MDM para Office 365.

<!--HONumber=Apr16_HO2-->


