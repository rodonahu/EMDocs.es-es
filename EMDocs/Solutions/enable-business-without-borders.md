---
title: "Consecución de un negocio sin fronteras"
description: "Este artículo describe cómo Enterprise Mobility + Security puede utilizarse para proporcionar una identidad única que funciona a través de activos locales y en la nube y mantiene la mayor productividad posible de los usuarios mediante el aprovechamiento de herramientas en Azure Active Directory."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 12/07/2016
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: 
ms.assetid: 38e9802b-d8c0-4f5c-b89d-8ce1e04f7387
ROBOTS: 
ms.reviewer: atkladak, jsnow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fdb0852611551daaa2aad7d3839a3431abd8b445
ms.openlocfilehash: 8f79e391813c7a15e522f07ff27a2f6abd8536cc


---

# <a name="enable-business-without-borders"></a>Consecución de un negocio sin fronteras
No es bueno disponer de identidad: es el núcleo de un personal eficaz. Las organizaciones necesitan capacitar a sus empleados para tener acceso a todos sus datos y aplicaciones desde todos los dispositivos y todas las ubicaciones. Los usuarios necesitan colaborar entre sí y con los partners y conectarse con los clientes. Las herramientas que usan no se encuentran ya en un entorno protegido y controlado; se pueden encontrar en cualquier nube pública.

Este nuevo mundo presenta desafíos y amenazas avanzadas que no se pueden mitigar con las herramientas tradicionales. No hay ningún punto de protección, solo la red mientras el nuevo límite es el usuario. La clave para ser productivos y estar protegidos en este entorno es una solución de identidad sólida.

## <a name="how-can-enterprise-mobility-security-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security?
Enterprise Mobility + Security (EMS) es la única solución en la nube integral que protege de forma nativa los datos corporativos en el propio dispositivo y más allá con cuatro niveles de protección en las identidades, los dispositivos, las aplicaciones y los datos. EMS le ayuda a resolver uno de los desafíos claves en un mundo que da prioridad a los dispositivos móviles y la nube: cómo proporcionar una identidad única que funciona en recursos en la nube y locales y conseguir la máxima productividad de los usuarios.

### <a name="access-to-single-sign-on-applications"></a>Acceso a las aplicaciones de inicio de sesión único
Con la federación de identidades y el inicio de sesión único, los usuarios tienen un conjunto de credenciales de inicio de sesión y contraseñas, y el departamento de TI puede administrar más eficientemente la identidad del usuario.
### <a name="multi-factor-authentication"></a>Multi-factor Authentication
Los usuarios también tienen la capacidad de llevar nuevos dispositivos a la empresa, pero el departamento de TI puede validar que los dispositivos que se conectan a la red son propiedad de las personas con las credenciales adecuadas y están controladas por ellas. Multi-factor authentication (MFA) ayuda a proporcionar una capa de protección.
### <a name="self-service-group-management"></a>Administración de grupos de autoservicio
Cuando los usuarios olvidan las contraseñas, tienen la capacidad de restablecer sus propias contraseñas, reduciendo la carga de TI y haciendo que el usuario sea más eficiente al ser capaz de resolver el problema rápidamente.
### <a name="cross-organization-collaboration"></a>Colaboración entre organizaciones
La colaboración de negocio a negocio es importante para el 97 % de los clientes de Microsoft, que lo consideran un requisito clave para trabajar con los partners. La colaboración B2B (de negocio a negocio) de Azure Active Directory es compatible con las relaciones entre empresas, ya que permite a los partners obtener acceso de forma selectiva a los datos y las aplicaciones empresariales mediante identidades autoadministradas.

## <a name="recommended-solution"></a>Solución recomendada
La [colaboración B2B (de negocio a negocio) de Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-b2b-what-is-azure-ad-b2b/) es la solución recomendada que proporciona a las organizaciones acceso a todo lo que necesitan en todas partes, de manera segura y productiva, en colaboración con las inversiones existentes en las herramientas tradicionales.
- Los profesionales de TI proporcionan acceso a los datos y aplicaciones de la organización para colaboradores y organizaciones de partners.
- Los usuarios de partners que actúan "en nombre de", como representantes o empleados de su organización.
- Las revisiones de acceso, la comprobación de correo electrónico, las listas de permisos, las listas de denegación, etc. controlan el acceso para los recursos y aplicaciones de host.
- Los usuarios asociados son reconocibles y pueden ver a otros usuarios de su propia organización (sujeto a la directiva).

### <a name="how-azure-ad-b2b-collaboration-works"></a>Cómo funciona la colaboración B2B de Azure AD

La colaboración B2B de Azure AD se basa en un modelo de invitación y canje, que usa las direcciones de correo electrónico de los partners con los que quiere que funcione y las aplicaciones respectivas que quiere usar.

1. El administrador inicia sesión en Azure Portal e invita a los usuarios asociados mediante la importación de un archivo CSV que contiene información de usuario del partner.
2. Azure Portal envía mensajes de correo electrónico a los partners.
3. Los partners hacen clic en el vínculo en el correo electrónico que reciben desde Azure Portal. Si el usuario asociado está ya en Azure AD, le pedirá que escriba sus credenciales de trabajo; de lo contrario, será necesario el usuario asociado se registre como un usuario de colaboración de Azure AD B2B.
4. Usuario del asociado se redirige automáticamente a la aplicación en la que se invitó a colaborar.

![Gráfico que muestra el proceso en el que se invita a un usuario asociado a través de Azure AD B2B.](./media/enable-business-without-borders/enable-business-without-borders-fig1.png)

## <a name="how-to-implement-this-solution"></a>Cómo implementar esta solución
En los pasos siguientes se describe cómo implementar cada tipo de colaboración B2B de Azure AD indicado anteriormente. Cada vínculo representa un conjunto diferente de artículos con una serie diferente de instrucciones/pasos que se va a implementar en su organización:
- Obtenga información sobre [cómo usar la colaboración B2B de Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-b2b-detailed-walkthrough/).
- Obtenga información acerca de [cómo utilizar el archivo CSV para especificar información de usuario de partner](https://azure.microsoft.com/en-us/documentation/articles/active-directory-b2b-references-csv-file-format/).



<!--HONumber=Dec16_HO2-->


