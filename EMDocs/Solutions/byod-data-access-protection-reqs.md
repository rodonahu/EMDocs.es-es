---
title: "Requisitos de acceso a datos y protección de datos"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 8/1/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29eddc34-5ca5-4169-89b6-8137b03ab7f0
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e51462f1b238f7e3b518a7a9c8042ff3ad78a5a5
ms.openlocfilehash: cf49009d8bb73ad49e47e34d8afa13ecf06036aa


---

# Requisitos de acceso a datos y protección de datos

Uno de los elementos más importantes al permitir que los usuarios accedan a los recursos de la compañía desde sus propios dispositivos es el de conservar los datos de la compañía y proteger esa información. Puede que su organización tenga que aplicar diversos requisitos de cumplimiento normativo para proteger los datos, estén donde estén. La ilustración siguiente muestra las interacciones que se producen entre los usuarios y los dispositivos al acceder a los datos, y los componentes que se deben tener en cuenta en este subdominio.

![Requisitos de protección del acceso a datos](./media/BYOD_Figure3.png)

En la sección siguiente, se incluyen preguntas sobre el acceso a datos y la protección de estos. Deberá responder a ellas para formular los requisitos del diseño de la solución.

## Preguntas

Las preguntas relativas a los requisitos en cuanto al acceso a datos y a la protección de estos se clasifican en seis áreas:

- Almacenamiento
- Red
- Directorio
- Autorización
- Directiva y cumplimiento

### Almacenamiento

- Mientras los datos están almacenados en el centro de datos, ¿tiene habilitado el cifrado?
- ¿La compañía proporcionará acceso sin conexión a los datos que se encuentran en el almacenamiento del centro de datos? (Es decir, ¿sincronizará datos con los dispositivos de los usuarios?)
    - Si es así, ¿la compañía quiere mantener el mismo formato de datos (cifrado o sin cifrar) en los dispositivos de los usuarios?
- Actualmente, ¿tiene implementada en el sistema alguna cuota de almacenamiento por usuario?
    - Si es así, ¿tiene pensado aumentar la cuota de los usuarios que disponen de autorización para utilizar sus propios dispositivos?
- ¿La directiva de la compañía permite que los usuarios utilicen unidades de almacenamiento externo en los equipos corporativos?
    - Si no, ¿tiene pensado ampliar esta directiva a los usuarios que accedan a los datos desde sus propios dispositivos?
- ¿La directiva de la compañía permite que los usuarios utilicen almacenamiento basado en la nube desde los equipos corporativos?
    - Si no, ¿tiene pensado ampliar esta directiva a los usuarios que accedan a los datos desde sus propios dispositivos?

### Red

- ¿Tiene algún tipo de cifrado de red local?
    - Si lo tiene, ¿está limitado a las comunicaciones entre servidores o toda la red está cifrada?
- ¿Tiene pensado establecer diferentes requisitos para el acceso a los datos cuando los usuarios están físicamente fuera de la red corporativa y cuando están físicamente dentro de la red corporativa?
    - Si es así, ¿cuáles son los requisitos?
- ¿Prevé algún aumento en la actividad de la red al permitir que los usuarios usen sus propios dispositivos en la red corporativa?
    - Si es así, ¿la capacidad de su red actual puede administrar el nuevo tráfico?
- ¿La compañía utiliza algún mecanismo de inspección de redes?
    - Si es así, ¿tiene pensado ampliar esta funcionalidad para los usuarios que traerán sus propios dispositivos y se conectarán a la red corporativa?

### Directorio

- ¿La compañía utiliza un solo directorio de usuarios o tiene varios proveedores?
- ¿El directorio de la compañía se encuentra en una ubicación local, en la nube o en ambas ubicaciones (híbrido)?
- Cuando los usuarios vayan a acceder a las aplicaciones desde sus dispositivos, ¿con qué directorio se autenticarán?
- ¿La compañía tiene pensado federar la autenticación entre los servicios locales y en la nube?

### Autenticación

- ¿Qué tipo de autenticación se usa actualmente en su entorno?
- ¿Tiene previsto conservar este método de autenticación o quiere mejorarlo antes de permitir que los usuarios usen sus propios dispositivos para acceder a los recursos de la compañía?
- ¿Está implementada la autenticación multifactor en el entorno actual?
- ¿Tiene pensado autenticar los dispositivos de los usuarios o solamente los usuarios?
- ¿Tiene pensado habilitar el inicio de sesión único para las aplicaciones a las que se accede desde los dispositivos de los usuarios?
- ¿Tiene pensado aprovechar los recursos de la nube para proporcionar un nivel adicional de autenticación a los usuarios remotos?

### Autorización

- En el entorno actual, una vez autenticados los usuarios, ¿tiene implementado algún otro control que permita comprobar si los usuarios tienen autorización para acceder a la información que solicitan?
- ¿Tiene pensado proporcionar acceso condicional a partir de un conjunto de reglas predefinidas para los usuarios remotos?
- ¿La compañía exige autorización para acceder a los datos locales o ubicados en la nube?
- ¿La compañía emplea el [principio de divulgación de información según sea necesaria](http://en.wikipedia.org/wiki/Need_to_know) para autorizar el acceso a los datos?

### Directiva y cumplimiento

- ¿La compañía aplica directivas para definir cómo se clasifica el acceso a los datos?
- ¿La compañía tiene que cumplir alguna norma de tratamiento y privacidad de datos?
    - Si es así, ¿cómo determinan estas normas las directivas de acceso a datos actuales que se aplican a los recursos locales?
- ¿La empresa aplica alguna directiva de [Administración de dispositivos móviles (MDM)](mdm-design-considerations-guide.md) y de [Administración de aplicaciones móviles (MAM)](https://blogs.technet.microsoft.com/cbernier/2016/01/05/microsoft-intune-mobile-application-management-mam-standalone/)?
- ¿La compañía aplica alguna directiva para la confiscación de dispositivos en caso de juicio o investigación de delitos?



<!--HONumber=Aug16_HO1-->


