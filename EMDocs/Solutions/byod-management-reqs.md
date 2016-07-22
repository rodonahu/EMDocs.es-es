---
title: "Requisitos de administración"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: bf0d4210-5edc-4ad7-bcb5-372099049630
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 31ba2bb9bf95d3b21ba08f7874f12cae790f9af0
ms.openlocfilehash: 81d49611ffe8cadcbf7b69df0b4cbb322faee2ee


---

# Requisitos de administración

La administración de dispositivos es una de las bases de toda estrategia que se centre en las personas y se debe evaluar comparándola con los requisitos de la compañía. Según el nivel de madurez de la compañía, es posible que ya se esté aplicando un sistema de administración y que sea necesario ampliarlo para abarcar los escenarios de BYOD que va a adoptar la compañía. La figura siguiente muestra las interacciones de administración que se producen al administrar usuarios, dispositivos y datos. Se deben tener en cuenta determinados aspectos de cada componente del subdominio de administración.

![Requisitos de administración](./media/BYOD_Figure4.png)

A la hora de analizar cuáles son los requisitos de las funcionalidades de administración, debe empezar por plantearse las preguntas de la sección siguiente.

## Preguntas

Las preguntas sobre los requisitos de administración se clasifican en siete áreas:

- Seguimiento
- Generación de informes
- Configuración
- Proceso
- Almacenamiento
- Automatización
- Implementación y aprovisionamiento


### Seguimiento

- ¿La compañía necesita supervisar la configuración de cumplimiento normativo como, por ejemplo, la contraseña, la cámara y el cifrado de los dispositivos de los usuarios?
- ¿La compañía quiere distinguir si el propietario del dispositivo es la compañía o un usuario?
- ¿La compañía quiere permitir que los usuarios restablezcan las contraseñas de sus propios dispositivos?
- ¿La compañía necesita tener la funcionalidad de registro integrada en el sistema de administración?
- ¿La compañía necesita tener las funcionalidades de auditoría integradas en el sistema de administración?
- ¿La compañía agrega este tipo de registros en un solo repositorio?

### Generación de informes

- ¿La compañía necesita las funcionalidades de creación de informes para su modelo de BYOD?
    - Si es así, ¿qué tipos de informes necesitará? (Por ejemplo, actualizaciones, software instalado e inventario).
- ¿El sistema de administración actual tiene estos requisitos de creación de informes?
    - Si es así, ¿se pueden personalizar?
- ¿Hay alguna diferencia entre los requisitos de creación de informes de los dispositivos unidos al dominio y los que no están unidos al dominio?
    - Si es así, ¿cuáles son los requisitos de cada escenario?

### Configuración

- ¿La compañía necesita un sistema de administración que requiera que los dispositivos de los usuarios estén unidos al dominio para poder administrarlos?
- ¿La compañía necesita un sistema de administración que se integre con el directorio actual?
- ¿La compañía necesita un sistema de administración que administre solamente las aplicaciones, o debe administrar también el sistema operativo que se ejecuta en los dispositivos de los usuarios?
- ¿La compañía necesita un sistema de administración que pueda exigir directivas en los dispositivos de los usuarios?
- ¿La compañía necesita un sistema de administración que pueda integrarse con servicios en la nube?
- ¿La compañía tiene pensado realizar borrados selectivos si un usuario deja de tener que acceder a las aplicaciones que se instalaron?
    - Si es así, ¿el sistema de administración actual admite la funcionalidad de borrado selectivo?

### Proceso

- ¿Qué recursos informáticos son necesarios para ejecutar el sistema de administración en los servidores back-end?
- ¿Qué recursos informáticos son necesarios para ejecutar el sistema de administración en los dispositivos de los usuarios?
- ¿El sistema de administración permite sacar provecho de la funcionalidad de nube para expandir los recursos informáticos locales?

### Almacenamiento

- ¿Cuáles son los requisitos de almacenamiento necesarios para ejecutar el sistema de administración en los servidores back-end?
- ¿Cuáles son los requisitos de almacenamiento necesarios para ejecutar el sistema de administración en los dispositivos de los usuarios?
- ¿El sistema de administración permite sacar provecho de las funcionalidades de la nube para expandir los recursos de almacenamiento locales?
- ¿La compañía necesita administrar las unidades de almacenamiento externo que se agregan a los dispositivos de los usuarios?
- ¿La compañía necesita un sistema de administración que pueda también integrarse con el almacenamiento en la nube?

### Automatización

- ¿Qué operaciones tiene pensado automatizar la compañía para los escenarios de BYOD?
- ¿Cuáles son los requisitos de automatización necesarios para el sistema de administración que tiene pensado adoptar la compañía?
- ¿El sistema de administración actual admite la automatización integrada de scripts o de línea de comandos?
- ¿La compañía tiene un sistema de administración que se integre con los servicios en la nube y proporcione funcionalidades de automatización?

### Implementación y aprovisionamiento

- ¿Cuáles son los requisitos de implementación del agente de administración para su sistema de administración actual?
- ¿Se ofrecerá algún servicio a los usuarios remotos que pueda aprovisionarse de forma instantánea con un portal?
- ¿Es el departamento de TI quien registra los dispositivos personales con la compañía, o se registran personalmente?
- ¿Se pondrá en práctica algún plan para permitir que los usuarios aprovisionen servicios con sus propios dispositivos?
    - Si es así, ¿el sistema de administración permite de forma nativa que los usuarios realicen esta operación desde sus dispositivos?




<!--HONumber=Jul16_HO3-->


