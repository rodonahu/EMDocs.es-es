---
title: "Clasificación de datos"
description: "En este artículo se proporciona un conjunto de consideraciones de diseño para la clasificación de datos que debe usarse en un escenario de administración de dispositivos móviles."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f3486381-66d5-469a-93a3-013eaaa17c07
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 94c02152e553bdeba1bd1568c409d816ac078e9a


---

# <a name="data-classification"></a>Clasificación de datos

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

La mayoría de las empresas ya disponen de una directiva de [clasificación de datos](http://blogs.microsoft.com/cybertrust/2014/01/28/the-importance-of-data-classification/) en su lugar, por lo que tendrá que comprender cómo la implementación de una solución de administración de dispositivos móviles afectará a esta directiva. Si su empresa no tiene una directiva de clasificación de datos actual, debe introducir esta capacidad junto con la planificación de la solución de administración de dispositivos móviles. Algunas organizaciones realizan una clasificación de datos local en el nivel de servidor de archivos con [Active Directory Rights Management Services (ADRMS)](https://technet.microsoft.com/windowsserver/dd448611.aspx). Otra herramienta que usan algunas empresas es el [kit de herramientas de clasificación de datos de Microsoft](http://www.microsoft.com/download/details.aspx?id=27123), que ayuda a las organizaciones a identificar, clasificar y proteger los datos de sus servidores de archivos.

Office 365 proporciona una clasificación automática de los datos de correo electrónico que puede ayudar a la información confidencial superficial que debe protegerse. Office 365 usa reglas de transporte incorporadas en el procesamiento de flujo de correo para detectar la información confidencial. A continuación, la [característica DLP](http://blogs.office.com/2013/10/28/office-365-compliance-controls-data-loss-prevention/) realiza un análisis profundo del contenido a través de coincidencias de palabras clave, coincidencias de diccionario, evaluaciones de expresiones regulares, funciones internas como la suma de comprobación de números de tarjeta de crédito y otros exámenes de contenido para detectar tipos de contenido específico dentro del cuerpo del mensaje o los archivos adjuntos.

Intune y Configuration Manager no tienen una clasificación de datos integrada, por lo que se basan en la clasificación basada en la nube con Azure RMS o de manera local mediante ADRMS. Otra opción consiste en usar [Enterprise Mobility + Security (EMS)](http://www.microsoft.com/server-cloud/enterprise-mobility/overview.aspx) como solución MDM. Con EMS, dispondrá de acceso a [Azure AD Premium](https://msdn.microsoft.com/library/azure/dn532272.aspx) y [Azure RMS](https://technet.microsoft.com/library/jj585026.aspx), que puede utilizarse para clasificar datos. La clasificación de datos mediante Azure RMS puede integrarse con una solución de administración local en un entorno híbrido.

Intune permite al departamento de TI cumplir las directivas mediante directivas de cumplimiento, que es un conjunto de reglas y configuración que debe satisfacer un dispositivo para las políticas de acceso condicional lo consideren conforme. Las directivas de cumplimiento también se pueden usar para supervisar y corregir problemas de compatibilidad con dispositivos independientemente del acceso condicional. Consulte [Directivas de cumplimiento de dispositivos en Microsoft Intune](/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) para más información.

Utilice la siguiente tabla como referencia para ayudarle a elegir la opción de MDM que mejor se adapte a los requisitos de *clasificación de datos* de su organización.

## <a name="intune-standalone"></a>Intune (independiente)

**Ventajas**

- No disponible

**Desventajas**

- No disponible

## <a name="mdm-for-office-365"></a>MDM para Office 365

**Ventajas**

- Las reglas de transporte de Exchange pueden utilizarse para detectar información confidencial.
- Aprovecha la directiva de [prevención de pérdida de datos (DLP)](https://technet.microsoft.com/library/ms.o365.cc.DLPLandingPage.aspx) en el centro de cumplimiento para identificar información confidencial en numerosas ubicaciones.

**Desventajas**

- La clasificación de datos no se realiza con el propio archivo. Una vez que el archivo se encuentra en el dispositivo móvil, se puede utilizar sin restricciones

## <a name="hybrid-intune-with-configmgr"></a>Híbridas (Intune con Configuration Manager)

**Ventajas**

- No disponible

**Desventajas**

- No disponible

## <a name="enterprise-mobility-security"></a>Enterprise Mobility + Security

**Ventajas**

- Aprovecha Azure RMS para realizar la clasificación de datos.
- La suscripción a Azure RMS se incluye con EMS.
- No requiere una infraestructura local para la clasificación de datos
- Se puede integrar con soluciones AD RMS locales existentes.
- La protección se encuentra en el propio archivo, lo que significa que el archivo mantendrá su clasificación incluso si se ha guardado en una ubicación diferente

**Desventajas**

- No está disponible para los clientes que no estén adoptando soluciones basadas en la nube



<!--HONumber=Nov16_HO4-->


