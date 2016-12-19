---
title: Desarrollar los requisitos de cifrado de datos
description: "En este tema se incluyen el cifrado de datos de las consideraciones de diseño en dispositivos móviles. Este tema forma parte de un conjunto mayor de artículos sobre las consideraciones de diseño de la administración de dispositivos móviles."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 1072858e-dc0a-44ad-a512-d938f20310b6
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 0eacdea52150bc8282df618ae73c96724cec26c5
ms.openlocfilehash: 9d6194247048242509f4306e34fc805bc0b41466


---

# Cifrado de datos

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Ahora que ha respondido a las preguntas de Tarea 1 con respecto a los requisitos del cifrado de datos en reposo y en tránsito, podrá evaluar a continuación las opciones disponibles para abordar cada requisito. Aunque los datos estén en reposo, pueden cifrarse de maneras diferentes, como se muestra en la siguiente ilustración.

![Disco del dispositivo móvil](./media/MDM_Figure_09.png)

## Diferentes niveles de cifrado

Puede usar el cifrado de disco completo o según los datos que administre una aplicación. [Configuration Manager](https://technet.microsoft.com/library/dn919655.aspx) permite aplicar directivas que llevarán a cabo el cifrado de archivos en dispositivos móviles. Aunque algunos dispositivos móviles, como los que ejecutan Windows Phone 8, se cifran automáticamente, otros solo cifran datos si hay alguna otra opción habilitada. Por ejemplo, en los dispositivos iOS, el cifrado se realiza automáticamente solo después de configurar la opción de requerir el uso de una contraseña en los dispositivos. 

Windows 10 Mobile usa el cifrado de dispositivo, que está basado en la tecnología de BitLocker, para cifrar todo el almacenamiento interno, incluido el sistema operativo y las particiones de almacenamiento de datos. El usuario puede activar el cifrado de dispositivo, o bien el departamento de TI puede activar y forzar el cifrado para dispositivos administrados por la empresa a través de herramientas MDM. Cuando se activa el cifrado de dispositivo, todos los datos almacenados en el teléfono se cifran automáticamente. Un dispositivo Windows 10 Mobile que tenga activado el cifrado ayuda a proteger la confidencialidad de los datos almacenados si el dispositivo se roba o pierde. Lea la guía de seguridad de Windows 10 Mobile para obtener más información.

>[!TIP] 
> Para más información sobre los dispositivos móviles en los que se puede habilitar el cifrado mediante Configuration Manager, lea [Configuración general para dispositivos móviles en Configuration Manager](https://technet.microsoft.com/library/dn376523.aspx).

En el caso de aplicaciones que están asociadas a una directiva de administración de aplicaciones móviles de Intune, Microsoft proporciona el cifrado. Los datos se cifran de forma sincrónica durante las operaciones de E/S de archivos según la configuración de la directiva de administración de aplicaciones móviles. En dispositivos Android, las aplicaciones administradas usan el cifrado de AES-128 en el modo de encadenamiento de bloques de cifrado (CBC) utilizando las bibliotecas de criptografía de la plataforma, que no cuentan con una certificación FIPS 140-2. 

Esta opción le permite especificar que se cifrarán todos los datos asociados con una aplicación determinada, incluidos los datos almacenados en medios externos, como tarjetas SD. También está disponible la misma capacidad con [MDM para Office 365](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx). 

Los servicios de almacenamiento en la nube pública, como OneDrive para la Empresa, también se pueden integrar con Intune independiente y también con [System Center 2012 R2 Configuration Manager SP1](https://technet.microsoft.com/library/mt131422.aspx). Puede implementar la aplicación OneDrive para la Empresa en el dispositivo del usuario y, a continuación, se cifrarán todos los documentos de la cuenta de OneDrive para la Empresa del usuario. 

La mayoría de soluciones MDM utilizan SSL para proteger los datos en tránsito, por lo que necesitará decidir si va a utilizar una PKI existente para emitir certificados o si va a usar una entidad de certificación (CA) de otros proveedores. La ventaja de usar una entidad de certificación de terceros es que los usuarios que usen sus propios dispositivos para obtener acceso a los recursos de la compañía confiarán automáticamente en una entidad de certificación pública reconocida. 

## Intune (independiente)

**Ventajas** 

- El cifrado de los datos asociados con las aplicaciones se controla mediante la directiva de administración de Intune.

**Desventajas** 

- No incluye el cifrado nativo para el almacenamiento del dispositivo móvil
- La falta de integración con la plataforma MDM local actual significa que debe usar una interfaz de administración adicional

## MDM de Office 365

**Ventajas**

- Cifrado de datos basado en la capacidad de la plataforma de dispositivos móviles

**Desventajas**

- Si la organización no dispone de una infraestructura de Configuration Manager local en estos momentos, habrá que planificar, instalar y configurar esta plataforma antes de la integración.

## Híbridas (Intune con Configuration Manager)

**Ventajas**

- El cifrado de los datos asociados con las aplicaciones se controla mediante la directiva de administración de Intune.
- Cifrado del almacenamiento de dispositivos móviles
- Proporciona un control más granular de lo que se puede cifrar en dispositivos móviles y cómo se realiza el cifrado, incluida la selección del algoritmo de cifrado

**Desventajas**

- Si la organización no dispone de una infraestructura de Configuration Manager local en estos momentos, habrá que planificar, instalar y configurar esta plataforma antes de la integración.

Para obtener más información sobre cómo combinar funcionalidades de Intune y Configuration Manager para mejorar la protección de datos y configurar el cifrado, lea [Managing Encryption on Mobile Devices with Configuration Manager and Intune](http://blogs.technet.com/b/pauljones/archive/2014/08/04/managing-encryption-on-mobile-devices-with-configuration-manager-and-intune.aspx) (Administración del cifrado en dispositivos móviles con Configuration Manager e Intune).



<!--HONumber=Nov16_HO2-->


