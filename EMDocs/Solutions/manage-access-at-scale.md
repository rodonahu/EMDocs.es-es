---
title: Administrar el acceso a escala
description: Administrar el acceso a escala
keywords: 
author: andredm7
manager: swadhwa
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 0292919a-af10-4a25-8916-c704aed643f6
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c20f69b821a2acfbf2fa399b960b60fc31dbf502
ms.openlocfilehash: 28b83995ab2689cffa048cbf2ccdd53a3d9b1421


---

# Administrar el acceso a escala
Desde que existe, Microsoft ha ayudado a las organizaciones a trabajar con eficiencia. Microsoft no solo proporciona una identidad que puede llevarle a todas partes, sino que también ofrece un conjunto de herramientas para automatizar, proteger y administrar TI dentro de la organización. Incluso tras la llegada de la informática en la nube, sigue habiendo demanda para administrar y controlar operaciones de TI, como llamadas al departamento de soporte técnico para el restablecimiento de contraseñas de usuario, la administración de grupos de usuarios y las solicitudes de aplicaciones.

## ¿Cómo puede ayudarle Enterprise Mobility + Security?
Enterprise Mobility + Security (EMS) es la única solución en la nube integral que protege de forma nativa los datos corporativos en el propio dispositivo y más allá con cuatro niveles de protección en las identidades, los dispositivos, las aplicaciones y los datos. EMS le ayuda a resolver uno de los principales retos de un mundo que prioriza la movilidad y la nube, es decir, cómo proporcionar un conjunto completo de herramientas en Azure Active Directory (Azure AD) que le ayude en lo siguiente:
- Administración avanzada del ciclo de vida del usuario
- Bajo costo y sobrecarga de TI
- Supervisión del puente de identidad


### Solución recomendada
Azure AD Premium es la solución recomendada para ofrecerle a su organización la capacidad de administración de identidad y acceso.
#### Administración avanzada del ciclo de vida del usuario
Azure AD proporciona una administración avanzada automatizada del ciclo de vida del usuario al aprovechar las reglas de pertenencia a grupos dinámicos y las funciones de administración de aplicaciones.

- En el caso de organizaciones con RR. HH. locales, Microsoft Identity Manager establece las identidades de los usuarios en Windows Server Active Directory.
- En el caso de organizaciones con RR. HH. proporcionados mediante software como servicio (SaaS), Azure AD se integra actualmente con Workday y, en el futuro, se integrará con más aplicaciones.
- Azure AD Connect sincroniza los usuarios y los grupos entre Windows Server Active Directory y Azure AD.
- Azure AD proporciona la concesión de licencias automatizada basada en grupos para Office 365 y otros servicios en línea de Microsoft.

![Gráfico en el que se muestra la manera en que Azure AD Connect sincroniza los usuarios y los grupos entre Windows Server Active Directory y Azure Active Directory.](./media/ManageAccessAtScale/fig1.png)
#### Administración de aplicaciones
¿A cuántos usuarios les gusta recordar las contraseñas de todas las aplicaciones que usan a diario? El [inicio de sesión único](https://azure.microsoft.com/en-us/documentation/articles/active-directory-appssoaccess-whatis/) resuelve este problema común, ya que puede iniciar sesión en varias aplicaciones SaaS mediante una sola cuenta de usuario y una contraseña, que se pueden aprovisionar automáticamente para todas las aplicaciones de la organización. Esta función está disponible para aplicaciones en la nube de Microsoft, como Office 365, y para aplicaciones de terceros, como Salesforce, ServiceNow y Workday.

 También está disponible para las aplicaciones locales a través del [Proxy de aplicación de Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), que ofrece una solución simple, segura y rentable de acceso remoto como servicio para todas las aplicaciones locales. Los empleados remotos pueden acceder a los recursos locales sin limitarse a la red corporativa y sin necesidad de solicitar al departamento de TI que implemente una VPN, un entorno de red perimetral o servidores proxy inversos.

 - Funciona en la nube, por lo que puede ahorrar tiempo y dinero. Las soluciones locales requieren la configuración y el mantenimiento de redes perimetrales, servidores perimetrales u otras infraestructuras complejas.
 - Esta función es más fácil de configurar y proteger que las soluciones locales, ya que no tiene que abrir ninguna conexión entrante a través del firewall.
 - Ofrece gran seguridad. Al publicar las aplicaciones mediante el Proxy de aplicación de Azure AD, puede aprovechar los controles de autorización enriquecidos y el análisis de seguridad de Azure. Esto significa que obtiene funciones avanzadas de seguridad para todas las aplicaciones existentes sin necesidad de cambiar ninguna aplicación.
 - Proporciona a los usuarios una experiencia de autenticación coherente. El inicio de sesión único permite que los usuarios finales tengan un acceso fácil y sencillo a todas las aplicaciones que necesitan para ser productivos con una sola contraseña.

#### Bajo costo y sobrecarga de TI
Azure AD Premium también ofrece autoservicio para el restablecimiento de contraseñas, administración de grupos y funciones de administración de aplicaciones para impulsar la productividad del departamento de TI y del usuario final en la organización. No es necesario que los usuarios llamen por teléfono al departamento de soporte técnico y pierdan el tiempo en una llamada para proporcionar numerosos datos con el fin de obtener una contraseña temporal, que se les enviará por correo electrónico o se compartirá con ellos de manera no segura durante la llamada.
- Funciona con federación, sincronización de contraseñas o cuentas de usuario solo en la nube. Además, aplica todas las directivas locales de contraseñas.
- Todo el tráfico se cifra con la clave específica del inquilino y a través de HTTPS.
- Los usuarios pueden actualizar su contraseña de AD o desbloquear sus propias cuentas de AD en tiempo real.
- Se envían notificaciones en tiempo real a los usuarios y los administradores.

![Gráfico en el que se muestra la manera en que Azure Active Directory funciona de forma segura en el entorno local y en la nube para proporcionar funciones de autoservicio de restablecimiento de contraseña a los usuarios finales.  ](./media/ManageAccessAtScale/fig2.png)

#### Supervisión del puente de identidad
Azure AD Connect Health ayuda a las organizaciones a supervisar y comprender mejor su infraestructura de identidad local y los servicios de sincronización, así como a mantener una conexión confiable con Office 365 y Microsoft Online Services, ya que proporciona funciones de supervisión para los componentes clave de identidad, como servidores de AD FS, servidores de Azure AD Connect y controladores de dominio de Active Directory.

- Auditoría y cumplimiento con un solo clic mediante Azure Portal.
- Análisis forense e investigación: ayuda a los administradores de TI a responder a la pregunta “¿Quién hizo qué, dónde y cuándo?”.
- Informes de actividades: proporcionan auditoría, inicios de sesión, autoservicio de restablecimiento de contraseña, actividad del grupo, actividad de la aplicación, aprovisionamiento de aplicaciones, etc.
- Informes de seguridad: proporcionan mitigación y resolución de anomalías de seguridad mediante Identity Protection.

![Gráfico en el que se muestra la manera en que Azure AD Connect Health ayuda a las organizaciones a supervisar sus componentes clave de identidad, como servidores de AD FS, servidores de Azure AD Connect y controladores de dominio de Active Directory. ](./media/ManageAccessAtScale/fig3.png)

## Cómo implementar la administración avanzada del ciclo de vida de un usuario
Analicemos algunos ejemplos y los pasos que puede seguir para implementar esta solución:
1. En un escenario real, su organización contrata a un profesional y agrega su usuario al sistema de RR. HH. como miembro del equipo de marketing.
2.  Suponiendo que ya ha integrado Active Directory local con Azure AD mediante la sincronización de directorios, Azure AD Connect local sincroniza la cuenta de usuario con Azure AD.
3.  Después de que la cuenta de usuario aparezca en Azure AD, puede crear una regla de pertenencia a grupos dinámicos que automáticamente le asigne usuarios de marketing.
4.  Una vez que el grupo de marketing se haya rellenado automáticamente con los usuarios, puede aprovechar la concesión de licencias selectiva basada en grupos, que permite agregar usuarios a un grupo de licencias determinado, como Azure AD Premium u Office 365 Enterprise E5.
  - En este ejemplo, esto proporciona acceso a los usuarios a todas las aplicaciones de Office 365 que necesitan para realizar su trabajo, así como a Azure AD Premium para realizar otras tareas automatizadas.

Si por alguna razón un empleado deja la empresa, puede quitarlo del sistema de RR. HH., con lo que automáticamente se eliminará el acceso desde todas las aplicaciones y los recursos que tenía aprovisionados. Si el empleado solo cambia de departamento, las reglas de pertenencia a grupos dinámicos automáticamente eliminarán el acceso desde las aplicaciones de marketing y agregarán acceso a las aplicaciones de otro departamento cuando se quite el usuario del equipo de marketing y se agregue al grupo dinámico del departamento nuevo.

### Cómo administrar aplicaciones en la nube y locales
Estos son los pasos que puede seguir para agregar, implementar y administrar aplicaciones SaaS de Microsoft y de terceros con Azure AD.
- Obtenga más información sobre cómo [integrar Azure AD con aplicaciones](https://azure.microsoft.com/documentation/articles/active-directory-integrating-applications-getting-started/).
- Obtenga más información sobre cómo [habilitar el inicio de sesión único en aplicaciones SaaS](https://azure.microsoft.com/documentation/articles/active-directory-sso-integrate-saas-apps/).
- Obtenga más información sobre cómo [administrar el acceso a aplicaciones](https://azure.microsoft.com/documentation/articles/active-directory-managing-access-to-apps/).

## Cómo implementar el Portal de autoservicio de restablecimiento de contraseña
De forma predeterminada, Azure AD incluye una característica gratuita que permite a cada administrador el autoservicio de restablecimiento de contraseña.

Al usar Azure AD Premium, puede ir más allá que los administradores de TI y proporcionar a los usuarios funciones de Portal de autoservicio de restablecimiento de contraseña. Puede habilitar rápidamente directivas de restablecimiento de contraseñas de usuario que extienden las mismas funciones de administración enriquecidas a todos los usuarios de su directorio.

Obtenga más información sobre los [requisitos previos, la habilitación y la configuración del Portal de autoservicio de contraseña](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/) en su inquilino de Azure AD.

## Cómo implementar Azure AD Connect Health
Puede comprobar la [documentación relativa a Azure AD Connect Health](https://azure.microsoft.com/en-in/documentation/articles/active-directory-aadconnect-health/) para recopilar más información sobre la herramienta, sus funciones y los pasos necesarios para empezar a usarla en la organización.

Azure AD Connect Health está disponible en [Azure Portal](https://ms.portal.azure.com) y requiere la instalación de un Agente de mantenimiento en los controladores de dominio locales que quiera supervisar. Obtenga más información sobre [cómo instalar el Agente de mantenimiento](https://azure.microsoft.com/en-in/documentation/articles/active-directory-aadconnect-health-agent-install/).

El panel de controladores de dominio proporciona un punto de vista del mantenimiento y del estado operativo del entorno, donde el administrador puede encontrar fácilmente los controladores de dominio que son propietarios del rol FSMO, tienen alertas activas y son catálogos globales, junto con columnas adicionales como “PDC accesible”, “GC accesible”, “Estado de Sysvol” y demás:

![Captura de pantalla en la que se muestra el panel de controladores de dominio con información sobre el controlador de dominio seleccionado. ](./media/ManageAccessAtScale/fig4.png)

Además, los controladores de dominio se pueden agrupar por su dominio correspondiente, o bien el administrador puede agruparlos por sitio:

![Captura de pantalla en la que se muestran los controladores de dominio agrupados por sitio. ](./media/ManageAccessAtScale/fig5.png)

En el panel de estado de replicación se muestra el aspecto de la topología de replicación en el entorno, junto con información sobre el último intento de replicación para cada contexto de nomenclatura:

![Captura de pantalla en la que se muestra el panel de estado de replicación con información sobre el último intento de replicación. ](./media/ManageAccessAtScale/fig6.png)

Los detalles de una alerta contienen más información sobre el problema que provoca la alerta, la corrección necesaria y un vínculo a recursos adicionales para la solución de problemas:

![Captura de pantalla en la que se muestran detalles sobre una alerta específica. ](./media/ManageAccessAtScale/fig7.png)

La supervisión de rendimiento de AD Connect Health permite comparar fácilmente el rendimiento de los controladores de dominio supervisados entre sí, así como diversas métricas de interés:

![Captura de pantalla en la que se muestra la supervisión de rendimiento de los controladores de dominio seleccionados. ](./media/ManageAccessAtScale/fig8.png)



<!--HONumber=Oct16_HO3-->


