---
# required metadata

title: Opciones de administración de aplicaciones
description:
keywords:
author: robmazz
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 1f77eba2-8e27-4e08-b2f2-e71e3d776cf4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Opciones de administración de aplicaciones

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Las directivas de administración de aplicaciones móviles (MAM) ayudan a evitar que los datos corporativos se filtren a las aplicaciones o los servicios de los consumidores de dispositivos móviles. Normalmente, estas directivas solo se aplican en el dispositivo inscrito en una solución de administración de dispositivos móviles. Intune ha ampliado su funcionalidad de MAM para incluir los dispositivos que se administran mediante otras soluciones de administración de dispositivos móviles y dispositivos que no están inscritos en cualquier sistema de administración de dispositivos.

Tal y como se muestra en la ilustración siguiente, si ya dispone de una solución MDM, las directivas MAM de Intune pueden ayudarle a administrar y proteger las aplicaciones de Office y los datos de Office 365 sin necesidad de anular la inscripción de dispositivos de empleados y de volver a inscribirlos en la funcionalidad MDM de Intune en un escenario de coexistencia o de migración:

![Información general de separación de la administración de aplicaciones para dispositivos móviles mediante directivas MAM de Intune](./media/Intune_without_enrollment.png)

**Información general de separación de la administración de aplicaciones para dispositivos móviles mediante directivas MAM de Intune**

Las características de MAM no sustituyen por completo a las soluciones MDM. El protocolo MDM se requiere para los escenarios de administración exhaustiva de dispositivos, como VPN, Wi-Fi, administración de certificados, implementación de aplicaciones y configuración de seguridad de nivel de dispositivo.

Para implementaciones híbridas con Configuration Manager e Intune, las directivas de administración de aplicaciones móviles pueden utilizarse para proteger las aplicaciones en dispositivos que no se administran mediante Intune. Con esta nueva capacidad, puede aplicar directivas de administración de aplicaciones móviles en aplicaciones que se conecten a los servicios de Office 365. Esto no se admite en aplicaciones que se conecten a Exchange o SharePoint local. Para usar esta funcionalidad, debe utilizar el portal de vista previa de Azure.

Según como haya respondido a las preguntas del paso 1, podrá determinar cómo quiere que sus aplicaciones se administren en la solución de administración de dispositivos móviles. En las siguientes listas se muestran las ventajas y desventajas de cada opción de administración de aplicaciones.

## Intune (independiente)

**Ventajas**

- Admite la administración de aplicaciones en dispositivos inscritos en Intune y en otras soluciones de administración, o bien en dispositivos no inscritos en cualquier solución de administración
- Aísla los datos corporativos de los datos personales de consumidores en aplicaciones habilitadas para Intune. Entre ellas se encuentran las aplicaciones de Office Mobile, las aplicaciones de terceros que han adoptado el SDK de Intune o las aplicaciones de línea de negocio ajustadas con Intune.
- Los datos corporativos se pueden compartir con las características de cortar, copiar y pegar entre las aplicaciones de empresa, a la vez que se evita el uso compartido de datos corporativos en aplicaciones personales.
- Directivas de prevención de pérdida de datos clave como PIN por aplicación, controles de "guardar como" y uso compartido de datos administrados entre aplicaciones.
- Admite estas funcionalidades en Microsoft Word, Excel, PowerPoint, Outlook, OneNote y OneDrive para la Empresa.
- Administración de aplicaciones de iOS adquiridas a través del Programa de Compras por Volumen de Apple para empresas.
- Compatible con dispositivos iOS y Android.

**Desventajas**

- No se admite en dispositivos Windows Phone.

## MDM para Office 365

- No se admite actualmente

## Híbridas (Intune con Configuration Manager)

**Ventajas**

- Todas las ventajas de Intune independiente.

**Desventajas**

- Requiere opciones de configuración adicionales para conectar Intune con la infraestructura de Configuration Manager local.
- Para las organizaciones que no tienen una infraestructura de Configuration Manager en estos momentos, habrá que planificarla, instalarla y configurarla antes de su integración con Intune.

Obtenga información sobre las opciones de administración de aplicaciones móviles revisando el siguiente artículo de Intune y Configuration Manager: Proteger datos mediante las directivas de administración de aplicaciones móviles con Microsoft Intune. Además, no se olvide de consultar la lista de aplicaciones de Microsoft que se pueden utilizar con las directivas MAM de Intune, así como de expandir la lista de aplicaciones para socios compatibles de Intune.

<!--HONumber=Apr16_HO2-->


