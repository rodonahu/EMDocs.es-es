---
# required metadata

title: Guía de arquitectura para proteger los documentos y correos electrónicos de la empresa
description:
keywords:
author: karthikaraman
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: fc9c7d79-d2ca-4cb2-8456-c7a88cbbf6fd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Guía de arquitectura para proteger los documentos y correos electrónicos de la empresa
Este tema comienza con una visión general de cómo puede proteger los datos de su empresa y garantizar que la experiencia del usuario final sea sencilla y que no afecte a la productividad. A continuación, nos centraremos específicamente en cómo puede proporcionar un acceso seguro al correo electrónico de su empresa y en cómo proteger los datos de la empresa que aparezcan en correos electrónicos y en archivos adjuntos mediante la solución de Microsoft Enterprise Mobility Suite.

En esta sección se trata la arquitectura para proteger los documentos y correos electrónicos de la empresa. Consulte [Learn more about how to deploy a solution for protecting company email and documents](learn-how-to-deploy-a-solution-for-protecting-company-email-and-documents.md) (Aprenda a implementar una solución para proteger los documentos y correos electrónicos de su empresa) para obtener instrucciones sobre cómo implementar una solución.

> [!TIP]
> Obtenga una copia descargable de este tema completo en la [Galería TechNet](https://gallery.technet.microsoft.com/Managing-Access-and-Help-b7a05d0d/file/140056/1/Managing%20Access%20and%20Help%20Protect%20Corporate%20Email%20Data%20on%20Mobile%20Devices.pdf).

Los empleados quieren poder usar sus propios dispositivos para tener acceso a recursos y herramientas de productividad de la empresa. El departamento de TI debe asegurarse de que los empleados tienen esta capacidad, pero se protegen los datos confidenciales de la empresa. El paradigma BYOD, o [Bring Your Own Device](byod-design-considerations-guide.md), supone un desafío específico: separar los datos personales de los profesionales en dispositivos personales, además de evitar el hecho de compartir, de forma intencionada o involuntaria, datos de la empresa.

**Los estudios han demostrado que:**

-   El 37 % de los recursos de todo el mundo son móviles.

-   El 53 % de todo el correo electrónico se abrió en un teléfono móvil o tableta en el tercer trimestre de 2014.

-   El 61 % de los trabajadores combina tareas personales y profesionales en sus dispositivos.

Considere lo siguiente:

-   El correo electrónico suele ser la aplicación más utilizada en cualquier dispositivo.

-   El contenido del correo electrónico y los datos adjuntos del correo electrónico se puede copiar, compartir o mover a otras ubicaciones fuera del alcance del departamento de TI, lo que puede poner en peligro la seguridad de la empresa.

Puesto que los usuarios finales quieren trabajar con sus propios dispositivos personales y el correo electrónico es la aplicación que más se utiliza, el primer paso para el departamento de TI es asegurarse de que los usuarios finales puedan acceder al correo electrónico corporativo en sus dispositivos y asegurarse de que los datos confidenciales del correo electrónico no se vean comprometidos.

## Información general
Microsoft ofrece Enterprise Mobility Suite (EMS), una solución completa para la administración de identidades, dispositivos móviles y aplicaciones, así como para la protección de datos. EMS proporciona un modelo de seguridad por capas que permite al departamento de TI administrar el acceso al correo electrónico, datos y aplicaciones corporativas desde casi cualquier dispositivo.

EMS se compone de los siguientes servicios en la nube:

![Gráfico que muestra los servicios en la nube que forman parte de EMS: Microsoft Azure AD Premium, Microsoft Intune y Microsoft Azure Rights Management](./media/ProtectEmail/Enterprise-Mobility-Suite.png)

Con EMS, los datos están protegidos dentro y fuera de la red corporativa:

-   Los empleados tienen acceso al correo electrónico corporativo, las aplicaciones relacionadas con el trabajo y los datos de la empresa en el dispositivo que elijan sin preocuparse por poner en peligro la información confidencial de la empresa.

-   Los datos de la empresa se protegen a todos los niveles: usuario, dispositivo, aplicación y, finalmente, en el nivel de los datos en sí.

-   El administrador de TI puede asegurarse de que solo acceden a los datos corporativos los usuarios de confianza desde dispositivos compatibles y administrados y en el contexto de las aplicaciones administradas.

Las aplicaciones administradas de Intune incluyen las aplicaciones móviles de Office, que son esenciales para esta solución. Con las aplicaciones móviles de Office, podrá contribuir a maximizar la productividad de los empleados y evitar la filtración de datos. Por ejemplo, los administradores de TI pueden configurar directivas que impidan la copia de datos de la empresa al almacenamiento personal en la nube, por ejemplo, en Dropbox.

Cuando los empleados mueven o cambian trabajos o pierden su dispositivo, EMS proporciona la opción de borrar los datos corporativos del dispositivo de forma selectiva y remota. Puede hacerlo el usuario final o el administrador de TI.

## Cómo puede ayudar a proteger los datos EMS
El modelo de seguridad de 4 niveles de identidad, dispositivos, aplicaciones y datos consiste en asegurarse de que solo accede a los recursos de la empresa el usuario designado, desde un dispositivo que cumpla un conjunto de directivas de cumplimiento configuradas por el usuario y dentro de los límites de las aplicaciones administradas.

![Gráfico que muestra el modelo de seguridad de cuatro niveles para identidades, dispositivos, aplicaciones y datos](./media/ProtectEmail/Protecting_your_data.png)

La protección de los datos comienza con el establecimiento y la validación de la identidad del usuario. *Azure AD*, una herramienta de administración de accesos e identidades empresarial, ofrece inicio de sesión único, autenticación multifactor, contraseñas de autoservicio, etc. Proporciona la funcionalidad para la **capa de identidad** del modelo de seguridad.

A partir de la línea de base de identidad, el administrador de TI puede usar *Microsoft Intune* para asegurarse de que los dispositivos móviles se inscriben, administran y cumplen con las directivas corporativas. Esta es la **capa de dispositivo**.

La tercera capa es la de **administración de aplicaciones**, con el ecosistema de aplicaciones administradas con Intune. Este ecosistema, al tiempo que permite a los usuarios ser productivos y usar las herramientas que necesitan y conocen, como Office, también permite al departamento de TI mantener los datos confidenciales dentro del ecosistema de aplicaciones administradas.

*Azure Rights Management (Azure RMS)* completa el modelo de seguridad al proteger los datos en el nivel de archivo. Las directivas de seguridad que se aplican a los datos viajan con los datos, ayudan a proteger los datos en tránsito y en dispositivos, independientemente del dispositivo que se use para acceder a ellos. Esta es la **capa de datos** del modelo de seguridad.

## Próximos pasos
- [Mire](https://www.youtube.com/watch?v=ltcZvm4VOFU) este vídeo para obtener información sobre cómo registrarse para obtener una cuenta de prueba y comenzar.

- Consulte la [Guía de consideraciones de diseño de administración de dispositivos móviles](mdm-design-considerations-guide.md) para comprender mejor los requisitos de diseño de la administración de dispositivos móviles.

- También puede consultar [Learn more about how to deploy a solution for protecting company email and documents](learn-how-to-deploy-a-solution-for-protecting-company-email-and-documents.md) (Aprenda a implementar una solución para proteger los documentos y correos electrónicos de su empresa).

Además, si quiere obtener más información sobre EMS y Azure Active Directory, puede obtener más información de cualquiera de estos artículos:
- [Arquitectura de EMS](https://azure.microsoft.com/en-us/documentation/infographics/enterprise-mobility/)

- [Qué es Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-whatis/)

- [¿Cómo admite Azure Active Directory Office 365, Microsoft Intune y otros servicios de Microsoft?](https://azure.microsoft.com/en-us/documentation/articles/active-directory-administer/#what-is-an-azure-ad-tenant)

- [¿Cómo ayuda Azure Active Directory a administrar identidades?](https://azure.microsoft.com/en-us/documentation/articles/active-directory-administer/)

- [¿Qué es Azure Rights Management?](https://technet.microsoft.com/en-us/library/jj585026.aspx)

- [¿Cómo admiten las aplicaciones Azure Rights Management?](https://technet.microsoft.com/en-us/library/jj585004.aspx)


<!--HONumber=Apr16_HO4-->


