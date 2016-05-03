---
# required metadata

title: Previsión de la solución de infraestructura BYOD
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 9596531a-2eef-4c91-af11-091088c52929

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

#Previsión de la solución de infraestructura para BYOD

Después de definir claramente el problema de BYOD que está tratando de resolver, puede empezar a definir una solución para el problema y los requisitos detallados de la solución.

## Definición de la solución

Para solucionar los problemas que identificamos antes y para ayudar a las organizaciones a que animen a los usuarios a traer sus propios dispositivos al trabajo y acceder a los datos corporativos con sus dispositivos, la compañía debe pasar de un enfoque de TI centrado en los dispositivos a uno centrado en las personas. Cuando defina su propia solución de infraestructura BYOD, podrá usar los conceptos de diseño incluidos en este documento para: 

- Proporcionar a los usuarios la flexibilidad necesaria para que accedan a los datos y las aplicaciones empresariales con sus propios dispositivos.
- Administrar los dispositivos que acceden a los recursos corporativos de forma local y desde la nube.
- Permitir que un departamento de TI proteja los datos corporativos almacenados en los dispositivos con cifrado y administración de derechos para protegerlos del acceso local no autorizado, y borrar los datos corporativos de forma remota por Internet cuando se pierda o se deseche un dispositivo o al finalizar el contrato de un empleado.
- Proporcionar a los usuarios una identidad común con la que acceder a los recursos de forma local y desde la nube.
- Permitir que las TI administren varias identidades y mantengan la información sincronizada entre diferentes entornos.
- Habilitar servicios de autenticación empresariales, como la autenticación multifactor y el inicio de sesión único.
- Permitir que se realicen actividades de cumplimiento normativo y seguridad de la información, como la atestación de cumplimiento normativo.

## Requisitos de la solución

Antes de permitir que los usuarios traigan sus propios dispositivos y accedan a los recursos de una compañía, se deben revisar las funcionalidades técnicas de la infraestructura existente. El objetivo de esta revisión es comprender si ya están presentes los requisitos de la solución de este nuevo modelo o si, por el contrario, se deben introducir nuevas tecnologías para resolver el problema. Primero debe definir una serie de requisitos para hacerlo, además de las restricciones del entorno. Algunos requisitos y restricciones se definen de acuerdo con los consumidores de las funcionalidades. Otros se definen según su entorno existente: las funcionalidades técnicas, los servicios, las directivas y los procesos existentes.

El proceso de determinar los requisitos, las restricciones y el diseño para permitir que los usuarios tengan acceso a los recursos de la compañía desde sus dispositivos administrados es fundamental. Es posible que los requisitos iniciales, unidos a las restricciones de su entorno, produzcan un diseño inicial que no pueda cumplir todos los requisitos iniciales. Si esto ocurre, puede que sea necesario realizar cambios en los requisitos iniciales y en el diseño posterior. Es necesario realizar varias iteraciones por la definición de los requisitos y el diseño de la solución antes de dar por finalizados los requisitos y el diseño. Por esto, no espere poder recorrer este documento una sola vez. Tal vez observe que las decisiones que realizó en las primeras fases del proceso excluyen otras opciones más adecuadas que se le ofrecen en etapas posteriores del proceso.

Las respuestas que dé a las preguntas de las siguientes secciones generarán una lista completa de los requisitos necesarios para permitir que los usuarios accedan a los recursos de la compañía desde sus dispositivos. El departamento de TI puede administrar estos dispositivos sin que los datos dejen de estar protegidos. Estas preguntas no varían con cada proveedor y se pueden aplicar a cualquier solución de infraestructura BYOD.

Los aspectos relacionados con el dominio del problema de BYOD que se presenta en esta guía se dividirán en subdominios. Cada subdominio tendrá una colección de componentes. Se presenta un conjunto de requisitos para cada uno de los subdominios incluidos en esta guía:

- Requisitos de usuarios y dispositivos
- Requisitos de acceso a datos y protección de datos
- Requisitos de administración
- Requisitos de aplicaciones



<!--HONumber=Apr16_HO2-->

