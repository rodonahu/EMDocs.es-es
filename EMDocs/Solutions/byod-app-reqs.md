---
title: Requisitos de las aplicaciones
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 8/1/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0c1313b9-361f-4732-a92c-23d0dac07733
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e51462f1b238f7e3b518a7a9c8042ff3ad78a5a5
ms.openlocfilehash: a5669564a8fe7c9d6c44aa02c889c939eeaaf566


---

# Requisitos de las aplicaciones

Cada organización utiliza diversas funcionalidades técnicas para permitir que sus recursos lleven a cabo sus tareas de forma optimizada. En la mayoría de los casos, la herramienta principal para lograrlo es una aplicación. Estas funcionalidades se pueden combinar en un enfoque multiplataforma en el que se usen diferentes tecnologías para alcanzar un determinado objetivo, o se puede crear una aplicación personalizada capaz de realizar una tarea o automatizar ciertos procesos. Es importante tener en cuenta las aplicaciones a la hora de diseñar la estrategia de BYOD. Los usuarios utilizarán diversos factores de forma para consumir las aplicaciones. Por eso, debe tener en cuenta la variedad de funcionalidades que deben admitir las aplicaciones. En la figura siguiente se muestra cómo los usuarios y los dispositivos usan aplicaciones para consumir datos, así como los aspectos que se deben tener en cuenta para cada componente del subdominio Aplicaciones.

![Requisitos de las aplicaciones](./media/BYOD_Figure5.png)

En la sección siguiente, se incluyen preguntas sobre los requisitos de las aplicaciones. Deberá responder a ellas para formular los requisitos del diseño de la solución.

## Preguntas

Los requisitos de las aplicaciones se clasifican en seis áreas:

- Experiencia
- Plataforma
- Implementación
- Almacenamiento
- Red
- Seguridad


### Experiencia

- ¿Tiene pensado conservar la misma experiencia del usuario, sean cuales sean los dispositivos en los que se ejecutarán las aplicaciones?
- ¿Las aplicaciones requieren que se acceda a Internet desde los dispositivos de los usuarios?
- ¿Las aplicaciones requieren la entrada de datos con el teclado?
- ¿Las aplicaciones recopilan algún dato del usuario como, por ejemplo, la ubicación geográfica?
    - Si es así, ¿las aplicaciones informan a los usuarios sobre las cuestiones de privacidad y la recopilación de datos al instalarse?
- ¿Las aplicaciones requieren integración con servicios en la nube?
- ¿Qué tipos de aplicaciones tiene pensado poner a disposición de los usuarios de BYOD (por ejemplo, aplicaciones web y aplicaciones modernas)?
- ¿Las aplicaciones se desarrollaron para ejecutarse en un sistema operativo en concreto o se pueden ejecutar en cualquier sistema operativo?
- ¿Tiene pensado permitir que los usuarios utilicen aplicaciones con Escritorio remoto desde sus propios dispositivos?
- ¿Las aplicaciones requieren acceso a tiempo completo a los recursos corporativos o se pueden ejecutar en modo sin conexión?
- ¿Las aplicaciones tienen algún tipo de integración con redes sociales?


### Plataforma

- ¿Qué tipo de plataforma back-end es necesaria para que se ejecuten estas aplicaciones?
- ¿Prevé que, al adoptar BYOD, se producirá algún aumento en la actividad que requiera la actualización de la plataforma back-end para las aplicaciones que piensa permitir que utilicen los usuarios remotos?
- ¿La plataforma back-end que admitirá las aplicaciones está ubicada en la misma infraestructura que los demás servidores?
- ¿La plataforma que admitirá estas aplicaciones es totalmente local o tiene también servidores ubicados en la nube?


### Implementación

- ¿Sabe qué aplicaciones estarán disponibles para los usuarios de BYOD?
- ¿Cómo tiene pensado implementar estas aplicaciones en los dispositivos de los usuarios?
- ¿Cuáles son las opciones de implementación de estas aplicaciones?
- ¿Los requisitos de instalación varían según el dispositivo de destino o son iguales en todos los casos?
- ¿Las aplicaciones requieren algún tipo de administración de dispositivos móviles (MDM) para funcionar correctamente?
- ¿Usará la Tienda Windows o alguna otra tienda de aplicaciones para implementar estas aplicaciones?
- ¿Las aplicaciones instalan algún certificado digital durante la implementación?
    - Si lo hacen, ¿qué entidad de certificación se usará (privada o pública)?
- ¿Los usuarios tienen que estar conectados físicamente a la red corporativa para realizar la instalación o pueden instalar la aplicación por Internet?

### Almacenamiento

- ¿Cuánto espacio es necesario tener en el dispositivo de destino para instalar cada aplicación?
- ¿Las aplicaciones cifran los datos ubicados en el almacenamiento de los dispositivos?
- ¿Es posible instalar las aplicaciones en el almacenamiento externo de un dispositivo de destino?
- ¿Prevé que, al adoptar BYOD, se producirá algún aumento en la actividad de almacenamiento del servidor de aplicaciones back-end?
    - Si es así, ¿tiene pensado ampliar la capacidad de almacenamiento del servidor de aplicaciones?
- ¿Los datos los consumen aplicaciones ubicadas en el almacenamiento local, en la nube o en ambas ubicaciones?
- ¿Los datos los consumen aplicaciones cifradas en el almacenamiento del centro de datos o en la nube?

### Red

- ¿Qué requisitos de red tienen las aplicaciones que piensa implementar para los usuarios de BYOD?
- ¿Las aplicaciones cifran los datos antes de transmitirlos por la red desde los dispositivos de los usuarios hasta el servidor de aplicaciones del back-end?
    - Si lo hacen, ¿qué método de cifrado usan las aplicaciones?
- ¿Prevé que, al adoptar BYOD, se producirá algún aumento en la actividad de red?
- ¿Las aplicaciones requieren conectividad de red total para funcionar?
- ¿Las aplicaciones funcionan en redes de latencia baja?
- ¿Las aplicaciones se pueden desinstalar de forma remota a través de la red o es necesario desinstalarlas con las consolas de los dispositivos?

### Seguridad

- ¿Las aplicaciones se desarrollaron con algún método de desarrollo de seguridad?
- ¿Las aplicaciones proporcionan funcionalidades de autenticación?
    - Si lo hacen, ¿qué método de autenticación usan las aplicaciones?
- ¿El método de autenticación saca provecho de los servicios en la nube?
- ¿Las aplicaciones proporcionan funcionalidades de autorización?
    - Si lo hacen, ¿qué niveles de autorización proporcionan las aplicaciones?
- ¿Las aplicaciones sacan provecho de la infraestructura existente para administrar la autorización?
- ¿Las aplicaciones proporcionan funcionalidades de registro?
    - Si lo hacen, ¿qué datos registran? ¿Se puede controlar el nivel de registro?
- ¿Las aplicaciones proporcionan validación de entrada?
- ¿Las directivas de la compañía tienen normas específicas para la administración y la validación de entrada?
    - Si es así, ¿las aplicaciones cumplirán esos requisitos?
- ¿Hay algún subsistema de inmunización o validación de entrada común que procese los datos de fuera del sistema?
- ¿Las aplicaciones consumirán alguna biblioteca externa como, por ejemplo, la biblioteca JavaScript?
    - Si es así, ¿realizó una evaluación de riesgos de seguridad de estas llamadas externas?
- ¿Las aplicaciones se han validado con el método [STRIDE](https://msdn.microsoft.com/library/ee823878.aspx) (suplantación de identidad, alteración de datos, rechazo, divulgación de información, denegación de servicio y elevación de privilegios)?
- ¿Las aplicaciones controlarán datos de identificación personal?
- ¿Realizó algún análisis de privacidad de estas aplicaciones?
- ¿Las aplicaciones usarán Live Tiles?
    - Si es así, ¿las Live Tiles podrían causar la divulgación de información no intencionada?




<!--HONumber=Aug16_HO1-->


