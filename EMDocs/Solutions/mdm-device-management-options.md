---
title: "Opciones de administración de dispositivos"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: a25f7407-92a0-4588-b5f7-a7bad9cdd070
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ef523f44cd9d51e59fc8d94bbb8d7aa388120945
ms.openlocfilehash: 3393393abd35b0f61e371325c3e15f67123599f6


---

# Opciones de administración de dispositivos

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Administración de dispositivos móviles con centros de Intune y Configuration Manager alrededor de las directivas de administración. Las directivas definen grupos de configuraciones para dispositivos móviles y pueden crearse a partir de plantillas o personalizarse para grupos, usuarios o dispositivos específicos. La práctica de administración recomendada es crear directivas de administración antes de que los dispositivos móviles se inscriba en la solución de administración. Esto garantiza que los dispositivos se administren de inmediato de acuerdo con las directivas y procesos definidos en su estrategia de TI. Ambas soluciones permiten configurar los siguientes tipos de directivas:

- Directivas de configuración: las directivas de configuración se utilizan para definir la configuración general de organización para cada dispositivo móvil inscrito. Esto puede incluir la contraseña del dispositivo, la aplicación, la directiva en la nube y la configuración de cifrado, pero puede incluir **[muchas otras configuraciones de dispositivo](https://technet.microsoft.com/library/dn743712.aspx)** para áreas de administración distintas. Además, las directivas de configuración se aplican y configuran de forma diferente para distintos tipos de sistemas operativos de dispositivos móviles mediante el uso de perfiles de inscripción de dispositivos.

>[!TIP]
>Cuando se crean directivas diferentes para distintos tipos de dispositivos, usuarios o grupos es muy fácil tener una configuración de directiva en conflicto aplicada al mismo dispositivo. Asegúrese de que comprende **[cómo se aplican las configuraciones de directivas en conflicto](https://technet.microsoft.com/library/dn743712.aspx)**.

- **Directivas de cumplimiento**: las directivas de cumplimiento aplican requisitos de su organización para dispositivos móviles con el fin de obtener acceso (o denegarlo) a servicios o recursos de la compañía. Esto también puede incluir la configuración de cifrado y contraseña del dispositivo, así como la determinación de si el dispositivo móvil se ha descifrado ("desbloqueado"). Al igual que con las directivas de configuración, las opciones de directivas de cumplimiento de Intune y [Configuration Manager](https://technet.microsoft.com/library/dn376523.aspx) también varían según el tipo de sistema operativo del dispositivo móvil. Si crea directivas de cumplimiento en Configuration Manager, es importante tener en cuenta que puede configurarse una granularidad incrementada como parte de un proceso de varias partes:

 1. Creación de [elementos de configuración](https://technet.microsoft.com/library/gg712331.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT)
 2. Creación de [líneas base de configuración](https://technet.microsoft.com/library/gg712268.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT)
 3. Implementación de las [líneas base de configuración](https://technet.microsoft.com/library/hh219289.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT) a colecciones de usuario o dispositivo de Configuration Manager

- **Directivas de acceso condicional**: las directivas de acceso condicional definen cómo se administra el acceso al correo electrónico y se pueden utilizar por separado o junto con directivas de cumplimiento. Las conexiones al servicio Exchange Server o Exchange Online local deben estar configuradas en [Intune](/Intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) o en [Configuration Manager](https://technet.microsoft.com/library/dn919655.aspx) para que las directivas de acceso condicional puedan implementarse. También puede configurarse el acceso condicional en los servicios de Office 365 y SharePoint Online.

Las respuestas a las preguntas del paso 1 pueden ayudarle a determinar cómo desea que los dispositivos se inscriban en la solución de administración de dispositivos móviles. Las listas siguientes le ayudarán a comprender las ventajas y desventajas de cada escenario de administración.

## Intune (independiente)

**Ventajas**

- Admite el control de directivas simplificado para la administración de usuarios y dispositivos, ahora separados por la plataforma de dispositivos.
- Admite las plataformas Windows Phone, Android, iOS, [Windows 10](https://technet.microsoft.com/library/mt147406.aspx) y Windows 8.x, así como Exchange ActiveSync.
- Proporciona una consola de administración basada en la web sencilla a la que puede obtenerse acceso desde cualquier ubicación
- Admite directivas basadas en grupos, lo que facilita la administración de grandes cantidades y diversos tipos de dispositivos móviles
- Admite funcionalidades y características de cumplimiento de dispositivos móviles avanzadas, que incluyen la detección del descifrado o el descodificado del dispositivo.
- Permite el borrado selectivo o el restablecimiento de fábrica completo para todos los dispositivos móviles
- Incluye un portal de empresa personalizable, lo que permite una distribución segura y administrada de las aplicaciones móviles internas y de terceros
- Implementación de certificados en dispositivos móviles
- Permite a las organizaciones evitar las funciones de cortar/copiar/pegar en las aplicaciones móviles
- Admite la exigencia del uso de exploradores administrados
- Admite el uso de números IMEI de dispositivos para identificar y etiquetar los dispositivos corporativos para separar las asignaciones de directivas de dispositivos personales.

**Desventajas**

- Requisitos de licencia adicionales y costes para dispositivos de inscripción de cuentas de usuario en el servicio de Intune.

## MDM para Office 365

**Ventajas**

- Consola de administración y administración basada en web integrada en los inquilinos de Office 365
- Admite directivas basadas en grupos, lo que facilita la administración de grandes cantidades y diversos tipos de dispositivos móviles
- Admite funcionalidades y características de cumplimiento de dispositivos móviles avanzadas, que incluyen la detección del descifrado o el descodificado del dispositivo.
- Permite el borrado selectivo o el restablecimiento de fábrica completo para todos los dispositivos móviles

**Desventajas**

- No se admiten las características de administración avanzadas de dispositivos móviles, incluidas las siguientes:
 - Aprovisionamiento y administración de perfiles inalámbricos, VPN, correo electrónico y certificados
 - Inscripción y administración de colecciones de dispositivos
- No se admiten algunas funcionalidades y características de administración de aplicaciones móviles:
 - Implementación de aplicaciones de la línea de negocio a dispositivos móviles
 - Habilitación del acceso seguro de datos a las aplicaciones móviles de Office
 - Ampliación de los datos corporativos de forma segura a la línea de aplicaciones empresariales para dispositivos móviles
 - Exploradores administrados u otras aplicaciones de visualización de contenido

## Híbridas (Intune con Configuration Manager)

**Ventajas**

- Todas las ventajas de Intune independiente, además de las siguientes:
 - Proporciona un único panel de vista de vidrio para administrar el estado corporativo, incluida la flexibilidad para la administración basada en roles y el scripting (a través de PowerShell)

**Desventajas**

- Requiere opciones de configuración adicionales para conectar Intune con la infraestructura de Configuration Manager local.
- Para las organizaciones que no tienen una infraestructura de Configuration Manager en estos momentos, habrá que planificarla, instalarla y configurarla antes de su integración con Intune.
- Actualmente no se admiten los perfiles de VPN y correo electrónico para dispositivos Android
- Los exploradores administrados no son compatibles actualmente


<!--HONumber=Jul16_HO3-->


