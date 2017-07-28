---
title: "Rol de Azure Information Protection en la protección de datos | Microsoft Docs"
description: "En este artículo se describe el rol de Azure Information Protection para proteger los datos de la organización."
author: yuridio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: solution
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 2f906e2e-3d99-40e6-b5cc-8d903fcda444
ms.reviewer: v-craic
ms.suite: ems
ms.openlocfilehash: 267a69648014d53307d255533f64ee579f4141fa
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="the-role-of-azure-information-protection-in-securing-data"></a>Rol de Azure Information Protection en la protección de datos

[Azure Information Protection (AIP)](/information-protection/understand-explore/what-is-information-protection) ofrece a los clientes la capacidad de clasificar sus datos, etiquetarlos y protegerlos mediante cifrado. Azure Information Protection permite a los administradores de TI hacer lo siguiente:

- Clasificar automáticamente los correos electrónicos y los documentos en función de reglas predefinidas.
- Agregar marcadores a contenido, como encabezados personalizados, pies de página y marcas de agua.
- Proteger archivos confidenciales de la empresa con Rights Management, lo que les permite:
    - Usar claves de 2048 bits de RSA para la criptografía de claves públicas y SHA 256 para operaciones de firma.
    - Cifrar los archivos para un conjunto específico de destinatarios tanto dentro como fuera de la organización.
    - Aplicar un conjunto específico de permisos para restringir la facilidad de uso del archivo.    
    - Descifrar el contenido en función de la identidad y la autorización del usuario en la directiva de permisos.

Estas funciones permiten a las empresas tener un mayor control de extremo a extremo sobre sus datos. En este contexto, Azure Information Protection tiene un rol importante en la protección de los datos de la empresa.

> [!IMPORTANT]
> Para más información sobre cómo funciona Azure Information Protection, lea [¿Cómo funciona Azure RMS? En segundo plano](/information-protection/understand-explore/how-does-it-work).

## <a name="the-state-of-enterprise-protection-today"></a>El estado de la protección de las empresas hoy en día

Actualmente, muchas empresas no aplican ninguna tecnología de protección. Los documentos y los correos electrónicos se comparten en texto no cifrado y los administradores de datos no saben claramente qué usuarios tienen acceso a contenido con privilegios. Las tecnologías de protección como SMIME son complicadas y las ACL no se transfieren necesariamente con los correos electrónicos y los documentos.

![Sin protección de documentos](./media/azure-information-protection-securing-data/aip-securing-data-fig1.png)

En un entorno en gran medida desprotegido, Azure Information Protection proporciona una medida de seguridad que no estaba disponible anteriormente. Aunque la seguridad no deja de evolucionar y ninguna organización puede garantizar una protección del 100 % en todo momento, Azure Information Protection aumenta el nivel de seguridad de una organización cuando se implementa correctamente.

## <a name="security-principles-for-sharing-content"></a>Principios de seguridad para compartir contenido

Cuando se usa Azure Information Protection en una organización, los administradores de TI tienen un control total sobre el dispositivo de cliente y sobre la administración de identidades de usuario, lo que genera una plataforma de confianza adecuada para el uso compartido dentro de la organización. El envío de información fuera de la organización es intrínsecamente menos confiable. Al considerar el enfoque de protección de la información, hay algunos principios que se deben tener en cuenta al realizar una evaluación de riesgos. Para llevar a cabo dicha evaluación de riesgos, tenga en cuenta lo siguiente:

- El destinatario tiene acceso físico a un dispositivo no administrado y, por tanto, controla todo lo que ocurre en el dispositivo.
- El destinatario se autentica con un grado de confianza vinculado a la no suplantación.

En una situación en la que el administrador de TI no controla el dispositivo o la identidad, el departamento de TI no puede controlar lo que ocurre con la información protegida. Una vez que un usuario se autentique y abra información protegida, usted ya no controla esa información. A partir de ese momento, debe confiar en que el destinatario respete las directivas aplicadas al contenido.

No es posible detener por completo a un destinatario externo malintencionado con acceso autorizado al contenido protegido. Azure Information Protection ayuda a establecer límites éticos y, con el uso de aplicaciones inteligentes, ayuda a que los usuarios sean honrados en lo que respecta a la manera en que tienen acceso a los documentos. Azure Information Protection resulta de ayuda cuando hay una confianza implícita dentro del límite de acceso definido en función de la identidad.

Pero la detección y la mitigación del acceso futuro son más sencillas. La característica Seguimiento de documentos del servicio Azure Information Protection puede realizar un seguimiento del acceso, lo que permite actuar a la organización, ya sea revocando el acceso al documento específico o revocando el acceso del usuario.

Si el contenido es altamente confidencial y la organización no puede confiar en el destinatario, es fundamental aplicar seguridad adicional al contenido. Se recomienda dar preferencia a la seguridad y colocar controles de acceso en el documento.

## <a name="identity-based-security"></a>Seguridad basada en identidad

En las secciones siguientes se tratan tres escenarios principales de ataques a contenido protegido y se describe cómo se puede usar una combinación de controles de entorno y Azure Information Protection para mitigar el acceso malintencionado al contenido.

### <a name="attacks-by-unauthorized-users"></a>Ataques de usuarios no autorizados

La protección de Azure Information Protection se fundamenta en que el acceso a contenido protegido se basa en la identidad autenticada y la autorización. Como resultado, en Azure Information Protection, *sin autenticación* o *sin autorización* *no hay acceso*. Este es el motivo principal para implementar Azure Information Protection, ya que permite que las empresas pasen de un estado de acceso sin restricciones a un estado en el que el acceso a la información se basa en la autenticación del usuario y la autorización.

Mediante el uso de esta función de Azure Information Protection, las empresas pueden compartimentar la información. Por ejemplo, pueden hacer que la información confidencial del departamento de recursos humanos (RR. HH.) se guarde aislada dentro del departamento, y pueden hacer que los datos del departamento financiero estén restringidos a dicho departamento. Azure Information Protection proporciona *acceso basado en la identidad, en lugar de nada en absoluto*.

En el diagrama siguiente se muestra un ejemplo en el que un usuario (Bob) envía un documento a Tom. En este caso, Bob trabaja en el departamento financiero y Tom, en el de ventas. Tom no puede tener acceso al documento si no se le conceden permisos.

![Sin acceso](./media/azure-information-protection-securing-data/aip-securing-data-fig2.png)

La conclusión principal de este escenario es que Azure Information Protection puede detener los ataques de usuarios no autorizados. Para más información sobre los controles criptográficos de Azure Information Protection, lea [Controles criptográficos usados por Azure RMS: longitudes de clave y algoritmos](/information-protection/understand-explore/how-does-it-work).

### <a name="access-by-malicious-programs-on-behalf-of-users"></a>Acceso mediante programas malintencionados en nombre de usuarios

A menudo, los programas malintencionados que obtienen acceso en nombre del usuario lo hacen sin que el usuario lo sepa. Los troyanos, los virus y otro malware son ejemplos clásicos de programas malintencionados que pueden actuar en nombre del usuario. Si uno de estos programas suplanta la identidad del usuario o aprovecha los privilegios del usuario para realizar una acción, puede usar el [SDK de Azure Information Protection](/information-protection/develop/developers-guide) para descifrar contenido en nombre de un usuario involuntario. Dado que esta acción tiene lugar en el contexto del usuario, no existe una manera sencilla de evitar este ataque.

![Programas malintencionados](./media/azure-information-protection-securing-data/aip-securing-data-fig3.png)

El objetivo es mejorar la seguridad de la identidad del usuario, ya que esto ayudará a mitigar la posibilidad de que aplicaciones no autorizadas ataquen la identidad del usuario. Azure Active Directory ofrece varias soluciones que pueden ayudar a proteger la identidad del usuario, por ejemplo, la autenticación en dos fases. Además, existen otras funciones incluidas como parte de Azure Active Directory Identity Protection que deben explorarse para proteger la identidad del usuario.

La protección de las identidades queda fuera del ámbito de Azure Information Protection y es responsabilidad del administrador.

> [!IMPORTANT]
> También es importante centrarse en un entorno “administrado” para eliminar la presencia de programas malintencionados. Esto se explicará en el escenario siguiente.

### <a name="malicious-users-with-authorization"></a>Usuarios malintencionados con autorización

Básicamente, el acceso por parte de un usuario malintencionado pone en peligro la confianza. El habilitador de este escenario debe ser un programa diseñado para aumentar los privilegios del usuario, ya que, a diferencia del escenario anterior, este usuario proporciona voluntariamente credenciales para infringir la confianza.

![Usuarios malintencionados](./media/azure-information-protection-securing-data/aip-securing-data-fig4.png)

Azure Information Protection se ha diseñado de modo que las aplicaciones del dispositivo de cliente se encarguen de aplicar los permisos asociados al documento. Sin duda, en la actualidad el punto débil de la seguridad del contenido protegido es el dispositivo de cliente, donde el contenido está visible para el usuario final en texto sin formato. Las aplicaciones cliente como Microsoft Office respetan los permisos, por lo que un usuario malintencionado no puede usar estas aplicaciones para escalar privilegios. Pero con el SDK de Azure Information Protection, un atacante motivado puede crear aplicaciones que no respeten los permisos, y esta es la esencia de un *programa malintencionado*.

El objetivo de este escenario es proteger el dispositivo y las aplicaciones cliente para que no se puedan usar aplicaciones malintencionadas. A continuación se indican algunos de los pasos que puede realizar el administrador de TI:

- Usar [Windows AppLocker](https://technet.microsoft.com/library/dd759117(v=ws.11).aspx) para ayudar a garantizar que no se puedan ejecutar programas no deseados.
- Usar [Intune](https://docs.microsoft.com/intune/) y [System Center Configuration Manager](https://docs.microsoft.com/sccm/) para ayudar a garantizar que el dispositivo esté “sano”.
- Garantizar que el antivirus del dispositivo esté actualizado.
- Usar aplicaciones que admitan [agentes de identidad de Microsoft](https://technet.microsoft.com/library/ms166045(v=sql.105).aspx) para la autenticación y [SSO](https://azure.microsoft.com/resources/videos/overview-of-single-sign-on/).

Una conclusión importante de este escenario es que la protección de las máquinas y las aplicaciones cliente es una parte fundamental de la confianza en la que se basa Azure Information Protection.

## <a name="summary"></a>Resumen

La seguridad total va más allá de una tecnología. A través de diversos medios interdependientes, un administrador de TI puede reducir la superficie expuesta a ataques del contenido protegido en el mundo real.

- **Azure Information Protection**: impide el acceso no autorizado al contenido.
- **Microsoft Intune, System Center Configuration Manager y otros productos de administración de dispositivos**: permiten un entorno administrado y controlado sin aplicaciones malintencionadas.
- **Windows AppLocker**: permite un entorno administrado y controlado sin aplicaciones malintencionadas.
- **Azure AD Identity Protection**: mejora la confianza en la identidad del usuario.
- **Acceso condicional de EMS**: mejora la confianza en el dispositivo y la identidad.

## <a name="additional-resources"></a>Recursos adicionales

Los escenarios siguientes contienen más detalles sobre la manera en que Azure Information Protection puede ayudar a proteger los datos:

- [Proteger los datos mediante la clasificación, el etiquetado y la protección](infoprotect-secure-classify-scenario.md)
- [Uso compartido de datos confidenciales interna y externamente](share-sensitive-data.md)
- [Realizar un seguimiento del uso de datos compartidos y responder ante un abuso de datos](infoprotect-track-usage-scenario.md)
