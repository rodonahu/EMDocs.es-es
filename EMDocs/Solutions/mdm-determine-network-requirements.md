---
# required metadata

title: Determinación de los requisitos de red
description:
keywords:
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 77e7cab9-2fae-4857-be5d-2b6f57e981be

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Determinación de los requisitos de red

>[!NOTE]
>Este tema forma parte de una guía de consideraciones de diseño más extensa. Si desea comenzar por el principio de la guía, consulte el [tema principal](mdm-design-considerations-guide.md). Para obtener una copia descargable de toda esta guía, visite la [Galería de TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

La habilitación de acceso administrado seguro a una amplia variedad de recursos corporativos mediante dispositivos móviles es una característica importante de una solución de administración de dispositivos móviles. Aunque estos recursos normalmente se encuentran en redes locales, ahroa es más frecuente que los recursos se hospeden además en redes externas y servicios web basados en la nube.</para><para>La forma en la que los dispositivos móviles se conectan a plataformas de correo electrónico corporativas, redes privadas virtuales (VPN) y redes inalámbricas corporativas (Wi-Fi) tiene un papel importante en la conservación de los datos corporativos y otros recursos protegidos del acceso no autorizado. Igualmente importante es conseguir que sea conveniente y fácil para que los usuarios de dispositivos móviles tengan acceso seguro a estos recursos para evitar que los usuarios encuentren un método más conveniente pero no seguro de almacenar recursos u obtener acceso a ellos.</para></content>


## Administración de correo electrónico
El correo electrónico corporativo es normalmente el recurso de datos principal que la mayoría de los usuarios necesita para obtener acceso a la red corporativa, ya sea un dispositivo móvil de propiedad personal o de la compañía. El acceso al correo electrónico es normalmente la conexión que activa la inscripción de dispositivos móviles inicial. Permite administrar el acceso de correo electrónico para dispositivos móviles en la solución de administración de dispositivos que no son móviles existentes y la solución de administración de dispositivos móviles, lo que le ayuda a evitar espacios de cobertura en el dispositivo y aumenta la protección de los datos almacenados en servidores de correo electrónico.

Las mayoría de las soluciones de administración de dispositivos móviles proporcionan una protección de acceso a correo electrónico mediante una de las siguientes características o ambas:

- **Perfiles de correo electrónico**: cuando se configuran e implementan perfiles de correo electrónico, los administradores pueden configurar automáticamente dispositivos móviles con información del servidor de correo electrónico adecuada para que los usuarios se conecten a sus buzones de correo electrónico. Esto ayuda a los usuarios a conectarse al servidor de correo electrónico correcto sin tener que recordar los nombres del extremo de servidor de correo electrónico o las direcciones de red adecuados. Además, cuando se quita un perfil de correo electrónico, los administradores pueden quitar el correo electrónico desde los dispositivos como parte del proceso de borrado selectivo o restablecimiento del dispositivo. La administración de perfiles de correo electrónico puede ser una característica de una solución de administración de dispositivos que no son móviles o se puede integrar con una solución de administración de dispositivos móviles.
- **Acceso condicional de correo electrónico**: el acceso condicional de correo electrónico o acceso de correo electrónico "administrado", se centra normalmente en la seguridad y el cumplimiento para obtener acceso al correo electrónico en un dispositivo móvil en lugar de en el punto de conexión al que se conecta el dispositivo móvil. Con el acceso condicional de correo electrónico, se define una directiva de conformidad y se asigna a dispositivos o usuarios individuales, o a grupos de usuarios o dispositivos. La directiva describe los requisitos previos que deben estar en su lugar para que un dispositivo móvil pueda conectarse a un recurso de correo electrónico; por ejemplo, podría solicitarse un PIN en el dispositivo. Normalmente, la directiva se aplica cuando se realiza la inscripción en el dispositivo por primera vez, pero permanece en el lugar y se activa siempre que el dispositivo móvil se inscriba en el sistema de administración de dispositivos móviles.

###Preguntas de planeación de la administración de correo electrónico

 Responda a las siguientes preguntas de planificación sobre la administración de correo electrónico:

- ¿Cómo se conectarán los dispositivos móviles a su sistema de correo electrónico hospedado en la nube o local existente?
- ¿Los administradores o usuarios (o una combinación de ambos) serán responsables de la conexión de dispositivos móviles a su sistema de correo electrónico? Si los usuarios van a conectar dispositivos móviles en el sistema de correo electrónico, cómo realizarán las siguientes tareas:
 - ¿Elegir el punto de conexión adecuado para obtener acceso a su buzón de correo electrónico?
 - ¿Elegir el método de conexión o el protocolo de conexión adecuados?
- ¿Los dispositivos móviles deben cumplir determinados estándares de seguridad y cumplimiento antes y mientras permanecen conectados al sistema de correo electrónico?
- ¿Necesita la capacidad de crear directivas de conexión de seguridad y cumplimiento del correo electrónico personalizadas? Si es así, ¿cuáles son los requisitos específicos?
- ¿Necesita la capacidad de importar o exportar las directivas de conexión de seguridad y cumplimiento de correo electrónico?
- ¿Cómo debe administrar las conexiones con el sistema de correo electrónico?
 - ¿Mediante el usuario del dispositivo?
 - ¿Mediante el tipo de dispositivo?
 - ¿Mediante el sistema operativo del dispositivo?
 - ¿Mediante el rol o grupo de usuario?
- Cuando es necesario desconectar un dispositivo móvil de su sistema de correo electrónico, ¿cómo se eliminarán los datos de correo electrónico del dispositivo móvil?
- ¿Los administradores y usuarios necesitarán la capacidad de eliminar datos de correo electrónico o la conexión con el sistema de correo electrónico?
- ¿Cómo se comprobará o ratificará la confirmación de la eliminación de datos de correo electrónico?
- Si utiliza un sistema de correo electrónico basado en la nube y local, ¿cómo se integran con la solución de administración de dispositivos móviles? 
- ¿Los perfiles de correo electrónico o las directivas de acceso administrado se administran de igual o diferente forma desde la perspectiva de TI? ¿Es la experiencia de conexión de correo electrónico del usuario la misma o diferente en el lugar en el que se hospeda la bandeja de correo?

## Administración de la conectividad de red

Los dispositivos móviles se suelen conectar a recursos y redes corporativas mediante las siguientes tecnologías de acceso:

- **Wi-Fi**: el acceso inalámbrico a los recursos corporativos se proporciona normalmente como un servicio de extensión de la red local para los dispositivos que están físicamente cerca de la red local. Normalmente, esto implica permitir que los dispositivos móviles se conecten a recursos de red a medida que los usuarios se mueven de una ubicación a otra en una oficina local, como salas de reuniones y conferencias, distintas oficinas u otras áreas locales. También puede incluir acceso inalámbrico desde ubicaciones remotas a través de puntos de acceso de red inalámbrica administrados no corporativos como la red doméstica del usuario o un punto de acceso inalámbrico público. Para simplificar las conexiones a redes inalámbricas, los administradores suelen administrar estas conexiones mediante perfiles inalámbricos que indican la configuración específica que deben tener los dispositivos móviles en su lugar antes de para poder conectarse a la red inalámbrica. Esto puede incluir la configuración automática de un nombre de red personalizado, el identificador de conjunto de servicios (SSID), la configuración de seguridad, el proxy de red, y si el dispositivo se debe conectar automáticamente o no a la red inalámbrica cuando el dispositivo está en el intervalo.
- **Red privada virtual (VPN)**: el acceso remoto seguro a recursos corporativos a menudo incluye el uso de un tipo de conexión VPN definido desde el dispositivo móvil. Suele ser específica del proveedor e incluye la instalación de una aplicación de VPN en el dispositivo móvil. Además, estas aplicaciones de VPN utilizan a menudo certificados digitales o credenciales de cuenta de usuario administradas por separado para autenticar la conexión VPN. Para simplificar las conexiones a VPN, los administradores pueden administrar normalmente estas conexiones con perfiles de VPN o las herramientas de administración de VPN incluidas con la solución VPN. Dependiendo de la compatibilidad con la integración, la administración de las conexiones VPN con la solución de administración de dispositivos móviles puede o no ser una opción con algunas plataformas VPN.

>[!NOTE]
>Puede que desee disponer de otros recursos web, como SharePoint, que aprovechen el acceso seguro a través de la Capa de sockets seguros (SSL) o la Seguridad de la capa de transporte (TLS). Asegúrese de comprender cómo los dispositivos móviles dispondrán de acceso a estos recursos con métodos de acceso seguros o VPN independientes.

### Preguntas de planeación de la administración de conectividad de red

Responda a las siguientes preguntas de planeación de la administración de la conectividad de red:
 
- ¿Qué tipo de plataforma de VPN ha implementado en su red local?
- ¿La plataforma de VPN es compatible o puede integrarse con la solución de administración de dispositivos móviles?
- Si la plataforma de VPN ya está integrada o si es compatible con una solución de administración de dispositivos que no son móviles existente, ¿la solución de administración de dispositivos móviles se integra con ambos sistemas?
- ¿La infraestructura de Wi-Fi requerirá la actualización para dar cabida a más conexiones de dispositivos y una mayor demanda de ancho de banda?
- ¿Cómo se conectarán los dispositivos móviles a su plataforma de VPN o inalámbrica local existente?
- Si los dispositivos móviles están ya conectados a su plataforma de VPN o inalámbrica existente, ¿qué tipo de conexión o protocolo utilizan los dispositivos para conectarse?
- ¿Los cambios realizados en estas conexiones serán necesarios si los dispositivos se inscriben en una solución de administración de dispositivos móviles?
- ¿Los administradores o usuarios (o una combinación de ambos) serán responsables de la conexión de dispositivos móviles a su plataforma de VPN o inalámbrica? Si los usuarios van a conectar dispositivos móviles a la plataforma de VPN o inalámbrica, cómo realizarán las siguientes tareas:
 - ¿Elegir el punto de conexión adecuado para obtener acceso a su red corporativa?
 - ¿Elegir el método de conexión o el protocolo de conexión adecuados?
 - ¿Elegir el certificado digital adecuado para el método de conexión?
- ¿Desea configurar automáticamente la configuración y las propiedades de la conexión VPN e inalámbrica en los dispositivos móviles del usuario?
 - ¿Necesita proporcionar diferentes configuraciones de seguridad o configuraciones de red inalámbrica para distintos tipos de usuarios, dispositivos, sistemas operativos de dispositivos o roles y grupos de usuarios?
 - ¿Necesita la capacidad de importar o exportar directivas de conexión de seguridad o configuración VPN o inalámbrica?

## Administración de certificados

Los certificados digitales, ya sean autofirmados o emitidos por una entidad de certificación de terceros, pueden utilizarse para autenticar dispositivos móviles en las conexiones de red o recursos de red específicos. Para simplificar la administración de certificados digitales, los administradores suelen administrar certificados mediante perfiles de certificado. Esto permite un método uniforme y centralizado para la administración de certificados, incluido el modo de creación, emisión y renovación. Esto también ayuda a los usuarios conectarse a recursos corporativos sin tener que solicitar e instalar certificados manualmente o mediante un proceso de seguridad no aprobado.</para><para>Sin embargo, el uso de certificados para este tipo de autenticación a menudo requiere requisitos de infraestructura locales adicionales. Esto puede incluir todos o algunos de los siguientes componentes de red, dependiendo del nivel de integración compatible con la solución de administración de dispositivos móviles:

- **Servicios de directorio**: los servicios de directorio, como Microsoft Active Directory, son normalmente necesarios para conectarse y administrar todos los demás componentes de red de forma segura.
- **Servidor de la entidad de certificación (CA)**: si está emitiendo certificados autofirmados para su organización, necesitará una entidad de certificación para crear, emitir, administrar y renovar certificados digitales.
- **Servidor del Servicio de inscripción de dispositivos de red (NDES)**: este servidor permite que los dispositivos móviles y el software obtengan certificados basados en el Protocolo de inscripción de certificados simple (SCEP).
- **Servidor proxy**: según la configuración de red local, puede que necesite un servidor proxy que permita que los dispositivos móviles reciban certificados mediante una conexión a Internet y sin necesidad de conectarse directamente a la red corporativa interna.

### Preguntas de planeación de la administración de certificados

Responda a las siguientes preguntas de planificación de la administración de certificados:

- ¿Su organización ya requiere o utiliza certificados digitales para autenticar el acceso a los recursos de red?
- ¿Tiene una infraestructura de clave pública empresarial (PKI) existente?
- ¿Necesita emitir automáticamente certificados digitales a los dispositivos móviles?
- ¿Cómo se crean, emiten, renuevan o revocan los certificados digitales desde dispositivos móviles?
- ¿Los certificados digitales se administran centralmente mediante una entidad de certificación CA) de terceros o local?
- ¿Necesita tener diferentes certificados asignados para el acceso a distintos servicios de red? ¿Esto depende del tipo de dispositivo móvil que obtiene acceso a la red?

>[!TIP]
>Asegúrese de que toma las notas de cada respuesta y de que comprende la lógica subyacente en la respuesta. Más adelante, las tareas tratarán las opciones disponibles, y las ventajas y desventajas de cada opción.  Responder a estas preguntas le ayudará a seleccionar la opción que mejor se adapte a sus necesidades empresariales.

<!--HONumber=Jun16_HO1-->


