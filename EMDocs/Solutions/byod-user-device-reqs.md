---
# required metadata

title: Requisitos de usuarios y dispositivos
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 69020f79-4ce2-4984-b127-4520503fb729

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Requisitos de usuarios y dispositivos

Antes de permitir que los usuarios accedan a los recursos de la compañía desde sus dispositivos, responda a las preguntas de las secciones siguientes. Para ello, colabore con los consumidores de estos recursos de su entorno y con el departamento de TI. En la ilustración 2, se muestran las interacciones entre usuarios y dispositivos, con el objetivo final de acceder a los datos y consumirlos. Tenga en cuenta que el diagrama no representa la ubicación geográfica. Aunque la ubicación geográfica es un aspecto importante (y se explicará más adelante en este documento), el propósito de la ilustración 2 es representar los componentes principales de los usuarios y los dispositivos. Para que se produzca esta comunicación, se deben tener en cuenta ciertas cuestiones de diseño.

![Usuarios, dispositivos y datos](./media/BYOD_Figure2.png)

El resultado de este proceso es una definición clara de la funcionalidad que se debe proporcionar. La sección siguiente contiene preguntas sobre los usuarios y los dispositivos. Deberá responderlas para formular los requisitos del diseño de la solución.

## Preguntas

Los requisitos de usuarios y dispositivos se clasifican en tres áreas:

- Perfil
- Dispositivo
- Red

### Perfil

- ¿Qué tipos de perfiles de usuario hay en la compañía? (Por ejemplo, trabajadores remotos, personas que viajan ocasionalmente y personas que trabajan desde casa a tiempo completo).
- ¿Todos los usuarios tienen los mismos requisitos para realizar sus trabajos?
- ¿Tiene alguna matriz que establezca las necesidades de los usuarios de acuerdo con sus trabajos o roles?


### Dispositivos

- ¿Qué tipos de dispositivos traerán los usuarios? (Por ejemplo, smartphones, tabletas y portátiles).
- ¿Tiene pensado proporcionar la funcionalidad de borrado remoto a todos los tipos de dispositivos?
- ¿Tiene pensado administrar los dispositivos de los usuarios?
- ¿Hay algún escenario en el que no sea necesario administrar el dispositivo, pero tenga que realizar un seguimiento de quién es el propietario del dispositivo?
- ¿Tiene pensado autenticar los dispositivos de acuerdo con los usuarios que trajeron los dispositivos a la compañía?
- ¿La compañía sigue algún requisito de cumplimiento normativo que se deba aplicar a todos los dispositivos que puedan tener acceso a los datos de la compañía?
- ¿La compañía aplica alguna directiva para procesar los dispositivos robados?

### Red

- ¿La compañía tiene algún recurso en la nube al que se podrá acceder por Internet desde los dispositivos de los usuarios?
- ¿La compañía tiene restricciones de directivas para los usuarios que acceden a los datos de la compañía desde distintas ubicaciones geográficas?
- ¿Tiene pensado proporcionar cifrado de red para permitir que los usuarios accedan a los recursos de la empresa desde sus dispositivos?
    - Si es así, ¿la lista actual de dispositivos compatibles admite el protocolo de cifrado que se usará?
- ¿Aplican segmentación de red?
    - Si es así, ¿tendrá los dispositivos de todos los usuarios conectados a una red independiente para aislarlos de la red de producción?


<!--HONumber=Apr16_HO2-->

