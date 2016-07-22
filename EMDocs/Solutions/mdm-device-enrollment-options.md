---
title: "Opciones de inscripción de dispositivos"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 54082b94-1d21-44d5-9fba-af6e04397def
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a16e90093c7571f3c098ce815a2b70ae03c080e3
ms.openlocfilehash: 90604329992f8ecb881ac1b83358af16de5b65cb


---


# Opciones de inscripción de dispositivos

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Para inscribir dispositivos en Microsoft Intune, de forma independiente o cuando se conecta a System Center 2012 R2 Configuration Manager (ConfigMgr), hay que preparar el servicio para los dispositivos. La inscripción de dispositivos móviles en MDM para Office 365 también requiere que active MDM, configure los valores básicos e incluya todos los usuarios en una respuesta de la [directiva de seguridad](https://technet.microsoft.com/library/ms.o365.cc.newdevicepolicy.aspx) a un mensaje de inscripción la próxima vez que inicien sesión en Office 365 en su dispositivo móvil. Deben completar los pasos de inscripción y activación en cada dispositivo móvil que se vayan a usar para disponer de acceso a documentos y correos electrónicos de Office 365.

Intune independiente debe configurarse para definir la solución de entidad de administración de dispositivos móviles, que puede ser Intune o una infraestructura de Configuration Manager local. Esto significa simplemente "qué plataforma de administración desea utilizar para administrar dispositivos con inscripción a Intune *o* Configuration Manager?" Es *muy importante* entender el [impacto de elegir la mejor opción](/Intune/deploy-use/enroll-devices-in-microsoft-intune) para la organización, ya que la solución de administración no puede modificarse fácilmente una vez elegida. Si necesita cambiar esta configuración más adelante, tendrá que ponerse en contacto con el soporte técnico de Microsoft para obtener ayuda. Para los inquilinos de Office 365, puede designar y cambiar la entidad de MDM de forma más sencilla entre Intune y MDM para Office 365. Puede cambiar fácilmente la entidad de administración de nivel de usuario cambiando la asignación de licencias de un usuario. 

Para la mayoría de las organizaciones que ya utilicen Configuration Manager para administrar PC, servidores y otros dispositivos, conectar la solución local a Intune y los dispositivos de administración a Configuration Manager suele ser la mejor opción. Para asignar la entidad de administración de dispositivos móviles a Configuration Manager, hay que crear una [suscripción a Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) y seleccionar la opción para permitir que Configuration Manager administre los dispositivos con inscripción de Intune y la suscripción a Intune. La suscripción a Intune también se puede crear [desde la consola de Configuration Manager](https://technet.microsoft.com/library/jj884158.aspx).

Además, para poder inscribir ciertos tipos de dispositivos móviles que ejecutan diferentes tipos de sistemas operativos móviles, necesitará preparar el servicio de Intune o MDM para Office 365 con requisitos específicos de configuración. Por ejemplo, si va a inscribir dispositivos basados en Apple iOS, necesitará **[configurar Intune con un certificado de servicio de notificación de inserción de Apple (APN)](https://technet.microsoft.com/library/dn408185.aspx)** antes de la inscripción de dispositivos basados en iOS. Si esto no está configurado, Intune no puede comunicarse con el servicio APN y los dispositivos basados en iOS. Los dispositivos móviles que ejecutan los sistemas operativos **[Android](https://technet.microsoft.com/library/dn764960.aspx)** o **[Windows Phone](https://technet.microsoft.com/library/dn764959.aspx)** tienen requisitos de inscripción independientes.

Las respuestas a las preguntas del paso 1 le ayudarán a decidir cómo desea que los dispositivos se inscriban en la solución de administración de dispositivos móviles. La tabla siguiente compara las ventajas y desventajas de cada escenario de inscripción:

| Área  | Los administradores inscriben dispositivos. | Los usuarios inscriben los dispositivos ellos mismos. |
| ------------- | ------------- | ------------ |
| Costos | Se pueden reducir los costes del departamento de soporte técnico y ayuda, ya que los administradores experimentados realizan la inscripción del dispositivo. | Posible aumento de las llamadas del departamento de soporte técnico y costes de soporte técnico, los usuarios menos experimentados pueden necesitar ayuda personal con la inscripción |
| Comodidad  | Cada dispositivo está inscrito sin ninguna interacción del usuario, por lo que se reducen los errores de inscripción de dispositivos. Los usuarios deben acordar las horas de entrega y recogida de los dispositivos móviles con usted, lo que requiere un seguimiento y una programación de la inscripción del dispositivo.| Inscripción de dispositivos más rápida que un proceso de inscripción centralizada en la mayoría de los casos. Puede ser más cómodo y flexible para los propietarios y usuarios de los dispositivos. |
| Administration | Es más sencillo admitir procesos de inscripción de dispositivos altamente personalizados, en masa, automatizados y más complejos. Los administradores controlan estrechamente la inscripción de todos los dispositivos preseleccionando de forma eficaz cualquier dispositivo o usuario al principio del proceso de inscripción. | Descarga de tareas de administración relativamente sencillos a los usuarios, lo que permite ahorrar tiempo, programación, seguimiento y costes generales de administración. |
| Seguridad | Si se admite una estrategia BYOD, existe una mayor probabilidad de que los administradores puedan ver o exponer información personal de información confidencial del usuario si no se colocan los controles de seguridad apropiados en su lugar. | Los usuarios de dispositivos móviles modernos pueden considerar que esta centralización es engorrosa y supone un inconveniente, lo que provoca soluciones alternativas definidas por el usuario que pueden poner en peligro los procesos de seguridad y cumplimiento de la inscripción |

Puede que su organización desee permitir estos escenarios de inscripción adoptando un enfoque flexible para permitir diferentes métodos para distintos departamentos o situaciones. Si es así, la solución de administración de dispositivos móviles debe poder admitir ambos escenarios.


<!--HONumber=Jul16_HO3-->


