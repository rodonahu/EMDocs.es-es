---
title: "Opciones de administración de certificados"
description: "En este artículo se proporcionan puntos de decisión sobre cómo planear y diseñar una infraestructura de certificados para admitir el aprovisionamiento de certificados con Microsoft Intune independiente e híbrido."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c3d350b5-4437-4f3d-907f-57ce6a819a74
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 7d9c38008b5b47ea41ff331f1de763de5c119c5e
ms.openlocfilehash: 2f0d445b35c6a7aea29684a0488decd92784c2ab


---

# <a name="certificate-management-options"></a>Opciones de administración de certificados

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

El uso de la administración de certificados digitales y de perfiles de certificados es compatible con escenarios de implementaciones de [Intune](/Intune/deploy-use/secure-resource-access-with-certificate-profiles) independientes e [híbridas](https://technet.microsoft.com/library/dn261202.aspx). Estas características le permiten implementar certificados raíz de confianza para dispositivos móviles, así como los perfiles basados en el Protocolo de inscripción de certificados simple (SCEP) que ordenan a los dispositivos móviles que obtengan certificados adicionales desde un servidor NDES en su organización.

Puesto que iOS, Windows 10 y 8.1, y Windows Phone 10 y 8.1 admiten SCEP de forma nativa y también es compatible a través de la aplicación del Portal de empresa de Microsoft Intune para Android, usar este protocolo de inscripción tiene la ventaja de tener la clave privada generada directamente en el dispositivo móvil. La clave privada nunca se genera ni almacena en caché o mediante Configuration Manager o Intune, lo que ayuda a mantener la seguridad de los dispositivos móviles.

En la siguiente ilustración se muestra cómo Intune y Configuration Manager utilizan NDES para proporcionar un aprovisionamiento de certificados seguros para dispositivos móviles mediante SCEP:

![Aprovisionamiento de certificados seguros](./media/MDM_Figure_07.png)

**Aprovisionamiento de certificados seguros**

1. Se crea una directiva que incluye las propiedades del certificado para la inscripción de SCEP en el servicio de Intune.
2. Intune convierte la directiva en un protocolo de administración de dispositivos móviles de plataforma (por ejemplo, OMA DM para Windows 10 y Windows 8.1) y lo envía al dispositivo.
3. El dispositivo móvil recibe la directiva e inicia una solicitud de inscripción desde NDES
4. NDES reenvía la solicitud a Configuration Manager.
5. Configuration Manager compara los atributos de la solicitud de SCEP para una coincidencia de autenticación y envía de nuevo la confirmación a NDES.
6. NDES envía una solicitud de emisión de certificados a la CA y envía el certificado al rol NDES.
7. El rol NDES envía el certificado al dispositivo.

Según como haya respondido a las preguntas de Tarea 3, podrá determinar cómo quiere que sus certificados se administren en la solución de administración de dispositivos móviles. Actualmente, MDM para Office 365 no es compatible con los perfiles de certificado de administración de dispositivos móviles. 

La lista siguiente le ayudará a comprender las ventajas y desventajas de la administración de perfiles de certificado para el escenario de implementaciones de Intune e híbridas de Intune con Configuration Manager:

## <a name="intune-standalone"></a>Intune (independiente)

**Ventajas**

- Admite los perfiles de certificados para todos los sistemas operativos de dispositivos móviles principales (Android, iOS, Windows 10, Windows 8.x y Windows Phone)
- La plataforma es compatible con el Protocolo de inscripción de certificados simple (SCEP)
- Los perfiles de certificado pueden configurar automáticamente dispositivos móviles de manera que pueda obtenerse acceso a los recursos de la compañía sin tener que instalar los certificados manualmente o usar un proceso de seguridad no aprobado
- Los certificados se pueden revocar automáticamente cuando el dispositivo se retira de la administración, se borra selectivamente o se bloquea desde la jerarquía de administración

**Desventajas**

- Para utilizar perfiles de certificado, la infraestructura local existente debe estar en su lugar. Debe integrar la siguiente infraestructura local con Intune:
 - Un servidor que ejecute el Servicio de inscripción de dispositivos de red
 - Una entidad de certificación empresarial
 - El conector NDES para Intune, que se instala en el servidor que ejecuta NDES

## <a name="mdm-for-office-365"></a>MDM para Office 365

- No se admiten perfiles de certificado con MDM para Office 365.

## <a name="hybrid-intune-with-configmgr"></a>Híbridas (Intune con Configuration Manager)

**Ventajas**

- Todas las ventajas de Intune independiente, además de las siguientes:
 - También admite la administración de certificados para dispositivos que no son móviles

**Desventajas**

- Para utilizar perfiles de certificado, la infraestructura local existente debe estar en su lugar. 
- Debe integrar la siguiente infraestructura local con Intune:
 - Un servidor que ejecute el Servicio de inscripción de dispositivos de red
 - Una entidad de certificación empresarial
 - El conector NDES para Intune, que se instala en el servidor que ejecuta NDES

Para obtener más detalles sobre las opciones de administración de certificados de dispositivos móviles, consulte cómo [habilitar perfiles de certificado](/Intune/deploy-use/secure-resource-access-with-certificate-profiles) en Intune y compare estos requisitos y procedimientos con la [habilitación de perfiles de certificado](https://technet.microsoft.com/library/dn261202.aspx) en System Center 2012 R2 Configuration Manager.



<!--HONumber=Nov16_HO4-->


