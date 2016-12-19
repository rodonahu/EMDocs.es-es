---
title: Administrar el acceso a escala
description: "Este artículo describe cómo puede utilizarse Enterprise Mobility + Security para autorizar a una organización con la administración de acceso de identidades mediante el aprovechamiento de herramientas de Azure Active Directory."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 12/07/2016
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: 
ms.assetid: 0292919a-af10-4a25-8916-c704aed643f6
ROBOTS: 
ms.reviewer: atkladak, jsnow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fdb0852611551daaa2aad7d3839a3431abd8b445
ms.openlocfilehash: fa2795fb578c0d278d55cbff9f44c19ca2e13309


---

# <a name="manage-access-at-scale"></a>Administrar el acceso a escala
Desde que existe, Microsoft ha ayudado a las organizaciones a trabajar con eficiencia. Microsoft proporciona no solo una identidad que puede llevarle a todas partes, sino también ofrece un conjunto de herramientas para automatizar, proteger y administrar TI dentro de la organización. Incluso tras la llegada de la informática en la nube, sigue habiendo demanda para administrar y controlar tareas de TI, como llamadas al departamento de soporte técnico para el restablecimiento de contraseñas de usuario, la administración de grupos de usuarios y las solicitudes de aplicaciones.

## <a name="how-enterprise-mobility--security-can-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security?
Enterprise Mobility + Security (EMS) es la única solución en la nube integral que ayuda a proteger de forma nativa los datos corporativos en el propio dispositivo y más allá con cuatro niveles de protección en las identidades, los dispositivos, las aplicaciones y los datos. EMS le ayuda a resolver uno de los principales retos de un mundo que prioriza la movilidad y la nube, es decir, cómo proporcionar un conjunto completo de herramientas en Azure Active Directory (Azure AD) que le ayude en lo siguiente:
- Administración avanzada del ciclo de vida del usuario
- Bajo costo y sobrecarga de TI
- Supervisión del puente de identidad

## <a name="recommended-solution"></a>Solución recomendada
Azure AD Premium es la solución recomendada para ofrecerle a su organización la capacidad de administración de identidad y acceso.

### <a name="advanced-user-lifecycle-management"></a>Administración avanzada del ciclo de vida del usuario
Azure AD proporciona una administración avanzada automatizada del ciclo de vida del usuario mediante el uso de las reglas de pertenencia a grupos dinámicos y las funciones de administración de aplicaciones. A continuación se describe con más detalle:

- En el caso de organizaciones con RR. HH. locales, Microsoft Identity Manager establece las identidades de los usuarios en Windows Server Active Directory.
- En el caso de organizaciones con RR. HH. proporcionados mediante software como servicio (SaaS), Azure AD se integra actualmente con Workday.
- Azure AD Connect sincroniza los usuarios y los grupos entre Windows Server Active Directory y Azure AD.
- Azure AD proporciona la concesión de licencias automatizada basada en grupos para Office 365 y otros servicios en línea de Microsoft.

![Gráfico en el que se muestra la manera en que Azure AD Connect sincroniza los usuarios y los grupos entre Windows Server Active Directory y Azure Active Directory.](./media/manage-access-at-scale/manage-access-at-scale-fig1.png)

### <a name="application-management"></a>Administración de aplicaciones
¿A cuántos usuarios les gusta recordar las contraseñas de todas las aplicaciones que usan a diario? El [inicio de sesión único](https://azure.microsoft.com/en-us/documentation/articles/active-directory-appssoaccess-whatis/) resuelve este problema común, ya que puede iniciar sesión en varias aplicaciones SaaS mediante una sola cuenta de usuario y una contraseña. El inicio de sesión único se puede aprovisionar automáticamente para todas las aplicaciones de la organización. Esta función está disponible para aplicaciones en la nube de Microsoft, como Office 365, y para aplicaciones de terceros, como Salesforce, ServiceNow y Workday.

A continuación se describe con más detalle el inicio de sesión único:

 - Funciona en la nube, por lo que puede ahorrar tiempo y dinero. Las soluciones locales requieren la configuración y el mantenimiento de redes perimetrales, servidores perimetrales u otras infraestructuras complejas.
 - Esta función es más fácil de configurar y proteger que las soluciones locales, ya que no tiene que abrir ninguna conexión entrante a través del firewall.
 - Ofrece gran seguridad. Al publicar las aplicaciones mediante el Proxy de aplicación de Azure AD, puede aprovechar los controles de autorización y el análisis de seguridad de Azure. Esto significa que obtiene funciones avanzadas de seguridad para todas las aplicaciones existentes sin necesidad de cambiar ninguna aplicación.
 - Proporciona a los usuarios una experiencia de autenticación coherente. El inicio de sesión único permite que los usuarios tengan acceso a todas las aplicaciones que necesitan para ser productivos con una sola contraseña.

### <a name="low-it-overhead-and-cost"></a>Bajo costo y sobrecarga de TI
Azure AD Premium ofrece autoservicio para el restablecimiento de contraseñas, administración de grupos y funciones de administración de aplicaciones para impulsar la productividad del departamento de TI y del usuario en la organización. No es necesario que los usuarios llamen por teléfono al departamento de soporte técnico para proporcionar numerosos datos con el fin de obtener una contraseña temporal, que se les enviará por correo electrónico o se compartirá con ellos de manera no segura durante la llamada.

A continuación se describe con más detalle el restablecimiento de contraseña:

- Funciona con federación, sincronización de contraseñas o cuentas de usuario solo en la nube. Además, aplica todas las directivas locales de contraseñas.
- Todo el tráfico se cifra con una clave específica del inquilino y a través de HTTPS.
- Los usuarios pueden actualizar su contraseña de AD o desbloquear sus propias cuentas de AD en tiempo real.
- Se envían notificaciones en tiempo real a los usuarios y los administradores.

![Gráfico en el que se muestra la manera en que Azure Active Directory funciona en el entorno local y en la nube para proporcionar funciones de autoservicio de restablecimiento de contraseña a los usuarios finales.](./media/manage-access-at-scale/manage-access-at-scale-fig2.png)

### <a name="monitor-your-identity-bridge"></a>Supervisión del puente de identidad
Azure AD Connect Health ayuda a las organizaciones a supervisar y comprender mejor su infraestructura de identidad local y los servicios de sincronización. También ayuda a las organizaciones a mantener una conexión confiable con Office 365 y Microsoft Online Services al proporcionar funciones de supervisión para los componentes clave de identidad. Estos componentes incluyen servidores de Servicios de federación de Active Directory (AD FS), servidores de Azure AD Connect y controladores de dominio de Active Directory.

A continuación se describe con más detalle Azure AD Health:

- Auditoría y cumplimiento con un solo clic mediante Azure Portal.
- Análisis forense e investigación: ayuda a los administradores de TI a responder a la pregunta "¿Quién hizo qué, dónde y cuándo?".
- Informes de actividades: proporcionan auditoría, inicios de sesión, autoservicio de restablecimiento de contraseña, actividad del grupo, actividad de la aplicación, aprovisionamiento de aplicaciones, etc.
- Informes de seguridad: proporcionan mitigación y resolución de anomalías de seguridad mediante Identity Protection.

![Gráfico en el que se muestra la manera en que Azure AD Connect Health ayuda a las organizaciones a supervisar sus componentes clave de identidad, como servidores de AD FS, servidores de Azure AD Connect y controladores de dominio de Active Directory.](./media/manage-access-at-scale/manage-access-at-scale-fig3.png)

## <a name="how-to-implement-an-advanced-user-lifecycle-management"></a>Cómo implementar la administración avanzada del ciclo de vida de un usuario
Analicemos algunos ejemplos y los pasos que se pueden seguir para implementar esta solución:

1. En un escenario real, su organización contrata a un profesional y agrega su usuario al sistema de RR. HH. como miembro del equipo de marketing.
2.  Suponiendo que ya haya integrado la instancia local de Active Directory con Azure AD mediante la sincronización de directorios, Azure AD Connect local sincroniza la cuenta de usuario con Azure AD.
3.  Después de que la cuenta de usuario aparezca en Azure AD, puede crear una regla de pertenencia a grupos dinámicos que automáticamente le asigne usuarios de marketing.
4.  Una vez que el grupo de marketing se haya rellenado automáticamente con los usuarios, puede usar la concesión de licencias selectiva basada en grupos. Este tipo de concesión de licencias permite agregar usuarios a un grupo de licencias determinado, como Azure AD Premium u Office 365 Enterprise E5.
    En este ejemplo, esto proporciona acceso a los usuarios a todas las aplicaciones de Office 365 que necesitan para realizar su trabajo, así como a Azure AD Premium para llevar a cabo otras tareas automatizadas.

Si un empleado abandona la empresa, puede quitarlo del sistema de RR. HH. De este modo, se eliminará automáticamente el acceso desde todas las aplicaciones y los recursos que el empleado tenía aprovisionados. Si el empleado solo cambia de departamento, las reglas de pertenencia a grupos dinámicos automáticamente eliminarán el acceso desde las aplicaciones de marketing y agregarán acceso a las aplicaciones de otro departamento cuando se quite el usuario del equipo de marketing y se agregue al grupo dinámico del departamento nuevo.

## <a name="how-to-manage-cloud-and-on-premises-applications"></a>Cómo administrar aplicaciones en la nube y locales
Estos son los pasos que puede seguir para agregar, implementar y administrar aplicaciones SaaS de Microsoft y de terceros con Azure AD:
- Obtenga más información sobre cómo [integrar Azure AD con aplicaciones](https://azure.microsoft.com/documentation/articles/active-directory-integrating-applications-getting-started/).
- Obtenga más información sobre cómo [habilitar el inicio de sesión único en aplicaciones SaaS](https://azure.microsoft.com/documentation/articles/active-directory-sso-integrate-saas-apps/).
- Obtenga más información sobre cómo [administrar el acceso a aplicaciones](https://azure.microsoft.com/documentation/articles/active-directory-managing-access-to-apps/).

## <a name="how-to-implement-password-reset-self-service-portal"></a>Cómo implementar el Portal de autoservicio de restablecimiento de contraseña
De forma predeterminada, Azure AD incluye una característica gratuita que permite a cada administrador el autoservicio de restablecimiento de contraseña.

Al usar Azure AD Premium, puede ir más allá que los administradores de TI y proporcionar a los usuarios funciones de Portal de autoservicio de restablecimiento de contraseña. Puede habilitar rápidamente directivas de restablecimiento de contraseñas de usuario que extienden las mismas funciones de administración a todos los usuarios de su directorio.

Obtenga más información sobre los [requisitos previos, la habilitación y la configuración del Portal de autoservicio de contraseña](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/) en su inquilino de Azure AD.

## <a name="how-to-use-azure-ad-connect-health"></a>Cómo usar Azure AD Connect Health
Puede comprobar la [documentación relativa a Azure AD Connect Health](https://azure.microsoft.com/en-in/documentation/articles/active-directory-aadconnect-health/) para recopilar más información sobre la herramienta, sus funciones y los pasos necesarios para empezar a usarla en la organización.

Azure AD Connect Health está disponible en [Azure Portal](https://ms.portal.azure.com) y requiere la instalación de un Agente de mantenimiento en los controladores de dominio locales que quiera supervisar. Obtenga más información sobre [cómo instalar el Agente de mantenimiento](https://azure.microsoft.com/en-in/documentation/articles/active-directory-aadconnect-health-agent-install/).

El panel **Controladores de dominio** proporciona una vista única del mantenimiento y el estado operativo del entorno. Allí, el administrador puede encontrar fácilmente los controladores de dominio que son propietarios del rol de Operaciones de maestro único flexible (FSMO), los que tienen alertas activas y los que son catálogos globales. Otras columnas son **PDC accesible**, **GC accesible** y **Estado de SYSVOL**.

![Captura de pantalla en la que se muestra el panel de controladores de dominio con información sobre el controlador de dominio seleccionado.](./media/manage-access-at-scale/manage-access-at-scale-fig4.png)

Además, los controladores de dominio se pueden agrupar por su dominio correspondiente, o bien el administrador puede agruparlos por sitio.

![Captura de pantalla en la que se muestran los controladores de dominio agrupados por sitio.](./media/manage-access-at-scale/manage-access-at-scale-fig5.png)

En el panel de **estado de replicación** se muestra el aspecto de la topología de replicación en el entorno, junto con información sobre el último intento de replicación para cada contexto de nomenclatura.

![Captura de pantalla en la que se muestra el panel de estado de replicación con información sobre el último intento de replicación.](./media/manage-access-at-scale/manage-access-at-scale-fig6.png)

Los detalles de una alerta tienen más información sobre el problema que la ha provocado, la corrección necesaria y un vínculo a recursos adicionales para la solución de problemas.

![Captura de pantalla en la que se muestran detalles sobre una alerta específica.](./media/manage-access-at-scale/manage-access-at-scale-fig7.png)

La supervisión de rendimiento de AD Connect Health permite comparar fácilmente el rendimiento de los controladores de dominio supervisados entre sí, así como diversas métricas de interés.

![Captura de pantalla en la que se muestra la supervisión de rendimiento de los controladores de dominio seleccionados.](./media/manage-access-at-scale/manage-access-at-scale-fig8.png)



<!--HONumber=Dec16_HO2-->


