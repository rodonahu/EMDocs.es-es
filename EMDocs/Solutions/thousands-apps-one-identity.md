---
title: Miles de aplicaciones, una identidad
description: "Este artículo describe cómo Enterprise Mobility + Security puede utilizarse para proporcionar una identidad única que funciona a través de aplicaciones basadas en la Web en el sector mediante el aprovechamiento de herramientas en Azure Active Directory."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 12/07/2016
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: 
ms.assetid: dd879a14-919e-431b-89b9-c035c83a6899
ROBOTS: 
ms.reviewer: atkladak, jsnow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fdb0852611551daaa2aad7d3839a3431abd8b445
ms.openlocfilehash: 27f71a706990997908a13b34477a1aa87ba698ab


---

# <a name="thousands-of-apps-one-identity"></a>Miles de aplicaciones, una identidad
Azure Active Directory (Azure AD) hace que los usuarios sean más productivos proporcionando una identidad común para los usuarios de aplicaciones de software como un servicio (SaaS) que obtienen acceso a los recursos locales y en la nube.

Azure AD se integra con muchas de las aplicaciones SaaS populares de hoy en día como Box, Twitter, ServiceNow, DocuSign, Workday y muchas más. Admite solo autenticación de inicio de sesión único (SSO) e identidad y protege la administración de acceso para aplicaciones desde cualquier dispositivo de forma segura y confiable.

## <a name="how-can-enterprise-mobility--security-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security?
Enterprise Mobility + Security (EMS) es la única solución en la nube integral que protege de forma nativa los datos corporativos en el propio dispositivo y más allá con cuatro niveles de protección en las identidades, los dispositivos, las aplicaciones y los datos. EMS le ayuda a resolver uno de los desafíos clave en un mundo que da prioridad a los dispositivos móviles y la nube: proporcione una identidad única que funciona a través de las aplicaciones basadas en web en el sector:
- Experiencia de autenticación directa conectada a la nube
- Inicio de sesión único para 1000 aplicaciones integradas previamente o sus propias aplicaciones
- Acceso remoto seguro a aplicaciones locales
- Compatibilidad para procesos de elevación y cambio en la nube


## <a name="recommended-solution"></a>Solución recomendada
Azure AD es una solución de administración de acceso e identidad en la nube que puede proporcionar a las organizaciones acceso a todo lo que necesitan en todas partes, de manera segura y productiva, en colaboración con las inversiones existentes en las herramientas tradicionales.
### <a name="access-to-single-sign-on-applications"></a>Acceso a las aplicaciones de inicio de sesión único

Antes del inicio de sesión único, los administradores de TI debían administrar distintos usuarios y contraseñas para las aplicaciones diferentes que las organizaciones tenían que admitir:

- Los usuarios escriben un nombre de usuario y contraseña en cada aplicación que usan
- Los usuarios administran demasiadas contraseñas
- La reutilización de contraseñas es común
- La revocación del acceso es muy difícil

Según una reciente investigación, el 63 % de los incumplimientos de datos confirmados se debían a contraseñas débiles, predeterminadas o robadas.

El Inicio de sesión único permite a los usuarios tener acceso a todas las aplicaciones y los recursos que necesitan para realizar las actividades empresariales iniciando sesión una sola vez usando una única cuenta de usuario. Cuando haya iniciado sesión, los usuarios pueden obtener acceso a todas las aplicaciones que necesitan sin que sea necesario autenticarse (por ejemplo, escriba una contraseña) una segunda vez.

Azure AD admite tres tipos de autenticación de inicio de sesión único:

- **Inicio de sesión único de Microsoft Azure AD:** esta opción utiliza el inicio de sesión federado para que los usuarios puedan iniciar sesión automáticamente en las aplicaciones de terceros, como Salesforce, con la información de cuenta de usuario de Azure AD.
- **Inicio de sesión único con contraseña:** esta opción permite a los usuarios iniciar sesión automáticamente en la aplicación SaaS de terceros en Azure AD utilizando la información de cuenta de usuario de terceros.
- **Inicio de sesión único existente:** esta opción es compatible con el inicio de sesión único en empresas de SaaS de terceros con Active Directory Federation Services (ADFS), u otro proveedor de inicio de sesión único de terceros.

### <a name="how-single-sign-on-works"></a>Funcionamiento del inicio de sesión único
Azure AD admite el inicio de sesión único con aplicaciones compatibles con cualquiera de estos protocolos estándar:
- SAML 2.0
- OAuth 2.0/OpenID Connect
- WS-Federation

Se configura una aplicación para usar Azure AD como su proveedor de identidades. Una vez configurada, la aplicación ya no requiere la entrada de nombre de usuario/contraseña directos y, en su lugar, se redirige al proveedor de identidades para la autenticación:

![Gráfico que muestra las relaciones de confianza establecidas entre Azure AD y aplicaciones diferentes.](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig1.png)


### <a name="do-i-still-need-azure-active-directory-federation-services-adfs"></a>¿Sigo necesitando Azure Active Directory Federation Services (ADFS)?
Sí. Una conexión de ADFS en Azure AD proporciona un inicio de sesión único sin problemas desde equipos unidos a un dominio:
- Los usuarios no ven ninguna página de inicio de sesión basado en web
- Las relaciones de confianza de cada aplicación se administran en Azure AD

![Gráfico que muestra cómo Azure Active Directory Federation Service se conecta a Azure AD para proporcionar un inicio de sesión único sin problemas para muchas aplicaciones.](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig2.png)

### <a name="what-if-an-app-doesnt-support-federated-single-sign-on"></a>¿Qué ocurre si una aplicación no admite el inicio de sesión federado?
SSO basado en contraseña es la mejor solución para las aplicaciones que no son compatibles con SAML/OpenID y solo son compatibles con la especificación de nombres de usuario y contraseñas en un formulario web.
- Permite conjuntos específicos de la aplicación de credenciales que se definen y almacenan en Azure AD
- Las credenciales se pueden asignar a usuarios o grupos de acceso compartido

### <a name="user-account-provisioning"></a>Aprovisionamiento de cuenta de usuario
El aprovisionamiento de cuenta de usuario es el acto de crear, actualizar o deshabilitar registros de cuentas de usuario en el almacén de perfiles de usuario local de la aplicación. La mayoría de aplicaciones SaaS almacenan los roles y permisos del usuario en su propio almacén de perfiles de usuarios local.

El servicio de aprovisionamiento de Azure AD se conecta a una API de administración de usuario de soap/rest proporcionada según la aplicación, que agrega, actualiza y deshabilita cuentas de usuario. Admite la sincronización de grupo y los perfiles y roles también se pueden importar desde la aplicación a Azure AD.

![Gráfico que muestra cómo el servicio de aprovisionamiento de Azure AD se conecta a la API de administración de usuario de soap y rest.](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig3.png)

### <a name="the-end-user-experience"></a>Experiencia del usuario final
El panel de acceso de aplicaciones es un portal entre dispositivos y exploradores accesible mediante iOS, Android, Mac y Windows. Para llegar al panel de acceso, los usuarios se autentican en Azure AD una vez. A continuación, consulte la lista de aplicaciones a las que tienen acceso y pueden iniciar la aplicación con un solo clic desde allí. Si el administrador configuró la aplicación para SSO, los usuarios no deben volver a autenticarse para obtener acceso a la aplicación: el inicio de sesión único se encargará de la autenticación automáticamente.

### <a name="bring-your-own-apps"></a>Traiga sus propias aplicaciones
La galería de aplicaciones de Azure AD ofrece miles de aplicaciones que puede agregar a su organización, pero si no se encuentra una aplicación de terceros, puede agregarla aún como una aplicación personalizada para que la use la organización.

Se puede incorporar cualquier aplicación basada en web que tenga un nombre de usuario y contraseña según el mecanismo de autenticación, si aparecen en la galería de aplicaciones de Azure o no.

![La captura de pantalla que muestra cómo utilizar la galería de aplicaciones de Azure AD para agregar una aplicación para su organización.](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig4.png)

### <a name="secure-remote-access-to-on-premises-apps"></a>Acceso remoto seguro a aplicaciones locales
[Proxy de aplicación de Azure AD](https://azure.microsoft.com/en-us/documentation/articles/active-directory-application-proxy-enable/) proporciona un inicio de sesión único (SSO) y acceso remoto seguro para aplicaciones web hospedadas en local. Esto puede incluir sitios de SharePoint, Outlook Web Access o cualquier otra aplicación web LOB que tenga. Estas aplicaciones de web locales se integran con Azure AD, la misma identidad y la plataforma de control que usa O365.

Los usuarios finales, a continuación, pueden obtener acceso a las aplicaciones locales del mismo modo que obtienen acceso a O365 y otras aplicaciones SaaS integradas con Azure AD, sin la necesidad de una VPN o de cambiar la infraestructura de red.

## <a name="how-to-implement-this-solution"></a>Cómo implementar esta solución
Los pasos siguientes describen cómo implementar cada capacidad de Azure AD tratada anteriormente. Cada vínculo representa un conjunto diferente de artículos con una serie diferente de instrucciones/pasos que se va a implementar en su organización:
1. [Habilitación del inicio de sesión único con el proxy de aplicación.](https://azure.microsoft.com/en-us/documentation/articles/active-directory-application-proxy-sso-using-kcd/)
- [Provisión de acceso remoto seguro a aplicaciones locales.](https://azure.microsoft.com/en-us/documentation/articles/active-directory-application-proxy-get-started/)
  - [Uso de dominios personalizados en el proxy de la aplicación de Azure AD.](https://azure.microsoft.com/en-us/documentation/articles/active-directory-application-proxy-custom-domains/)
  - [Uso de notificaciones de aplicaciones con reconocimiento de proxy de aplicación.](https://azure.microsoft.com/en-us/documentation/articles/active-directory-application-proxy-claims-aware-apps/)
  - [Uso de acceso condicional para aplicaciones publicadas mediante el proxy de aplicación.](https://azure.microsoft.com/en-us/documentation/articles/active-directory-application-proxy-conditional-access/)
- [Traiga sus propias aplicaciones a Azure AD.](https://blogs.technet.microsoft.com/enterprisemobility/2015/06/17/bring-your-own-app-with-azure-ad-self-service-saml-configuration-now-in-preview/)

## <a name="additional-resources"></a>Recursos adicionales
- **Galería de aplicaciones en Azure.com**
  - https://azure.microsoft.com/marketplace/active-directory/
- **Lista de aplicaciones SaaS** (con capacidades de integración)
  - https://aadappgallery.azurewebsites.net/M
- **Tutoriales de aplicaciones SaaS**
  - https://azure.microsoft.com/documentation/articles/active-directory-saas-tutorial-list/



<!--HONumber=Dec16_HO2-->


