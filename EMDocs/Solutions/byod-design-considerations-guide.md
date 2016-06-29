---
# required metadata

title: Guía de consideraciones de diseño para BYOD
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: ed940ba8-866c-477f-a59b-beb620300a79

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Guía de consideraciones de diseño para BYOD

Con la proliferación de dispositivos usados por los empleados, la mayoría de las empresas se enfrentan a un gran dilema: ¿cómo permitir a los usuarios utilizar sus propios dispositivos, a la par que proteger los datos corporativos que residen en dichos dispositivos? Las empresas están empezando a abandonar el modelo tradicional, en el que poseen y proporcionan dispositivos a sus empleados, a favor de un modelo en el que los empleados usan sus dispositivos personales para algunas de sus tareas. A menudo, este modelo se conoce como [Bring Your Own Device (BYOD)](https://technet.microsoft.com/library/dn645493.aspx). En este modelo, los empleados pueden utilizar sus dispositivos personales para algunas tareas de trabajo, pero solo si los empleados permiten que la empresa administre algunos aspectos de sus dispositivos para garantizar la seguridad de los datos corporativos. A menudo, esto significa que los usuarios permiten a la compañía aplicar directivas personalizadas, realizar la consolidación de la seguridad de los dispositivos o estandarizar el sistema operativo establecido por la directiva de la compañía. Los ejecutivos y los responsables de la toma de decisiones que leen el documento de [CIO considerations for workstyle transformation](http://download.microsoft.com/download/5/3/A/53A96632-02E3-416C-B209-D8725AA80AFE/CIO%20Considerations%20for%20Workstyle%20Transformation2.pdf) (Consideraciones de CIO para la transformación del estilo de trabajo) de Microsoft también pueden identificar las ventajas de adoptar un modelo en el que los usuarios puedan usar sus dispositivos para ser productivos en el trabajo.

Aunque la protección de los datos y el acceso a estos es uno de los desafíos principales de BYOD, otros desafíos requieren resolver el problema con un enfoque más amplio:

- Usuarios y dispositivos: ¿cómo pueden habilitarse los usuarios para utilizar sus propios dispositivos y seguir siendo al mismo tiempo compatibles con las directivas de la compañía?
- Administración: ¿cómo administrará el departamento de TI los dispositivos incorporados?
- Aplicaciones: ¿cómo se accederá a las aplicaciones de línea de negocio (LOB) desde los dispositivos de los usuarios?

Este análisis está determinado por los requisitos, capacidades y consideraciones de diseño de una infraestructura de administración de dispositivos. Las tecnologías de Microsoft se mencionan en el contexto de los requisitos y capacidades, y no al revés. Esperamos que este enfoque tenga una mayor efecto en los arquitectos y diseñadores que estén interesados en los problemas que se deben resolver y los métodos disponibles para resolver estos problemas. Solo entonces el análisis tecnológico es relevante.

Esta guía proporciona al arquitecto de sistemas y al diseñador de sistemas un conjunto de indicaciones cruciales sobre el esquema que hay que considerar antes de diseñar una infraestructura BYOD (Bring Your Own Device), la cual permite a los empleados utilizar sus propios dispositivos y proteger los datos de la compañía.

## Público al que está dirigido

Esta guía está dirigida principalmente a los arquitectos y diseñadores de sistemas interesados en comprender los problemas que deben tenerse en cuenta para implementar una infraestructura de BYOD. Otros usuarios interesados en esta guía pueden ser los implementadores de TI, los especialistas de seguridad de la empresa y los especialistas en administración de dispositivos.</para>
    
## Finalidad
  
El objetivo de esta guía es:

1. Proporcionar al arquitecto o al diseñador de sistemas una serie de problemas y preguntas a los que debe responder. Las respuestas a dichas preguntas pueden actuar como requisitos para un diseño de infraestructura BYOD.
2. Proporcionar al arquitecto o al diseñador de sistemas una serie de opciones de diseño que se pueden evaluar y elegir en función de requisitos identificados. 

Aunque puede formular las preguntas a cualquier proveedor, los ejemplos de las opciones disponibles se centrarán en las funciones de Windows Server 2012 R2, System Center 2012 R2 y Windows Intune.

Además, esta guía incluye:

- Consideraciones de diseño independientes de los proveedores para adaptar una infraestructura para habilitar el modelo BYOD. 
- Consideraciones de diseño para usuarios, dispositivos, plataformas de administración, aplicaciones y acceso a datos y su protección.

Antes de embarcarse en un modelo BYOD en un entorno de producción, deben tenerse en cuenta los problemas de seguridad, la disponibilidad, el rendimiento y la escalabilidad en las áreas de identidad, cálculo, almacenamiento y redes. Existe la tendencia a adoptar BYOD antes de realizar un análisis concreto del entorno actual y establecer qué debe hacerse para habilitar con seguridad a los usuarios para que trabajen desde cualquier dispositivo en cualquier parte.

Esta guía *no* tiene como finalidad:

- Proporcionar una línea base de rendimiento para los componentes de la infraestructura de un modelo de BYOD. 
- Proporcionar un ajuste de rendimiento y procedimientos recomendados para los componentes de la infraestructura de BYOD.
- Proporcionar una guía de desarrollo de aplicaciones para dispositivos móviles.
- Ofrecer procedimientos recomendados de desarrollo de aplicaciones para dispositivos móviles.
- Proporcionar una guía y procedimientos recomendados para componentes de terceros.

## Definición del problema

Los siguientes problemas o dificultades son los que normalmente encuentran las compañías cuando intentan adoptar BYOD:

- La plataforma de administración existente no deja que los usuarios lleven sus propios dispositivos y tengan acceso a los recursos de la compañía.
- La estrategia de seguridad en vigor no trata los problemas de seguridad que BYOD introduce en el entorno.
- Los usuarios adoptan nuevas tecnologías y requieren acceso a los recursos de la compañía para realizar sus tareas.
- Los responsables de toma de decisiones entienden las ventajas que aporta BYOD para el negocio, principalmente en la productividad del usuario que puede reducir el costo de la operación. Sin embargo, dudan sobre cómo deben adoptar BYOD y seguir respetando al mismo tiempo las reglas y la normativa.

Las organizaciones con una gran infraestructura necesitan, por una parte, determinar los requisitos antes de pasar de administrar ellos mismos los dispositivos, lo que supone que el departamento de TI tiene un control total sobre los dispositivos, a un modelo en el que dicho departamento debe asumir que tiene menos control sobre los dispositivos. Por otra parte, también deben abordar las necesidades de los usuarios de acceder a los datos corporativos. Esto se considera a menudo como un cambio desde una situación de centralización en torno al dispositivo a una situación de TI centrado en las personas. Los mismos requisitos y consideraciones deben también planificarse cuidadosamente para las aplicaciones nuevas y existentes, o para mover las aplicaciones existentes a un entorno de nube. La figura 1 incluye un diagrama conceptual del dominio del problema BYOD y las áreas que se tratarán en esta guía.

![Dominio del problema](./media/BYOD_Figure1.png)



<!--HONumber=Apr16_HO4-->


