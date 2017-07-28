---
title: "Introducción al uso de Enterprise Mobility + Security | Microsoft Docs"
description: 
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 6/7/2017
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: 
ms.assetid: 1df56825-c0d1-48ac-a294-5ebd1667bc38
ms.reviewer: mhamerof
ms.suite: ems
ms.custom: advanced-threat-analytics,cloud-app-security,information-protection,microsoft-identity-manager,microsoft-intune,rights-management
ms.openlocfilehash: a0252f0ea933bdc6398de47ff5bf49d9a2ea69d4
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="start-using-enterprise-mobility--security"></a>Introducción al uso de Enterprise Mobility + Security

Las organizaciones que pasan por una transformación digital deben protegerse frente a nuevas amenazas y retos, y el departamento de TI se ve obligado continuamente a impulsar la eficiencia y hacer más con menos. Además, en un mundo que da prioridad a los dispositivos móviles y la nube, los usuarios esperan ser productivos desde cualquier lugar y en cualquier dispositivo. Con EMS, obtendrá soluciones globales que le ayudarán a:

- **Controlar la identidad y el acceso en la nube**. Administre centralmente las identidades y proteja el inicio de sesión único en los dispositivos, el centro de datos y la nube.
- **Obtener seguridad basada en identidad**. Obtenga protección inteligente y completa contra los avanzados ataques de hoy en día.
- **Administrar dispositivos móviles y aplicaciones**. Administre de forma segura aplicaciones y datos en iOS, Android y Windows desde un único lugar.
- **Proteger la información**. Proteja de forma inteligente los datos corporativos y permita la colaboración segura.

Siga leyendo para obtener información sobre la manera en que EMS ayuda al departamento de TI a ofrecer la productividad segura y sin límites que tanto les gusta a los usuarios. Estos escenarios de ejemplo le ayudarán a empezar a trabajar con EMS mientras realice la transición de un entorno local a la nube, aprovechar la seguridad y la protección en la nube y, por último, proporcionar un servicio de TI completo desde la nube.

## <a name="transition-from-on-premises-to-the-cloud"></a>Transición de un entorno local a la nube
EMS está formado por muchos servicios y características que puede usar según sus necesidades empresariales a medida que se familiarice con sus funciones.

### <a name="establish-azure-ad-identity"></a>Establecer la identidad de Azure AD
Todo comienza con la identidad en la nube, por lo que lo primero que debe hacer para empezar a trabajar es establecer la presencia de [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/) de su organización. Puede hacerlo desde la nube o [sincronizar sus objetos actuales de Windows Server Active Directory con Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) para aprovechar sus inversiones actuales en la administración de identidades local.

### <a name="protect-your-organization-at-the-front-door"></a>Proteger el acceso principal de la organización
Las soluciones de seguridad tradicionales solían ser suficientes para proteger una empresa. Pero esto era así antes de que el sector de la movilidad creciese y generase un panorama de ataque más grande, y antes de que la transición a la nube hiciese más complejas las interacciones de los empleados con otros usuarios, dispositivos, aplicaciones y datos. Ahora, para proteger realmente la empresa, debe [adoptar un enfoque más innovador e integral para la seguridad](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-front-door), que pueda proteger, detectar y responder a amenazas de todo tipo localmente y en la nube.

### <a name="start-managing-devices"></a>Empezar a administrar dispositivos
Para un departamento tradicional de TI, puede ser todo un reto asegurarse de que los datos corporativos estén protegidos y los costos administrativos sean bajos, al mismo tiempo que administra la complejidad de dispositivos de la empresa. EMS facilita la compatibilidad con numerosos escenarios diferentes de administración de dispositivos, desde dispositivos corporativos Choose Your Own Device (CYOD) hasta dispositivos personales Bring Your Own Device (BYOD) usados en el trabajo.

- **Emitir dispositivos de propiedad corporativa**. Intune ofrece soluciones de aprovisionamiento masivo y administración para ayudarle a [emitir dispositivos de propiedad corporativa](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices) en la organización que se integren con las plataformas de administración de dispositivos corporativos más importantes del mercado de hoy día, incluidos el Programa de inscripción de dispositivos de Apple y la plataforma de seguridad móvil Samsung KNOX.
- **Habilitar una solución de dispositivos compartidos de uso limitado**. Los trabajadores de tareas usan las tecnologías móviles cada vez más. Tanto si se usan para procesar una venta o comprobar el inventario de forma inmediata, las tabletas que solo pueden ejecutar una única aplicación de línea de negocio suelen entregarse a los empleados en un modo de uso limitado. Intune permite aprovisionar de forma masiva, proteger y administrar centralmente estas tabletas de iOS y Android compartidas que pueden configurarse para funcionar en este modo de uso limitado.
- **Habilitar un programa BYOD en su organización**. BYOD es cada vez más popular entre las organizaciones como forma de reducir los gastos de hardware o de aumentar las opciones de productividad móvil de los empleados. A medida que las empresas se alejan del modelo tradicional de dispositivos corporativos, deben [decidir cómo implementar un programa BYOD](https://docs.microsoft.com/enterprise-mobility-security/solutions/byod-design-considerations-guide) que permita a los empleados usar sus dispositivos personales para realizar ciertas tareas.
- **Alinear una implementación de Windows 10 y una estrategia de administración con las necesidades empresariales, del usuario final y del departamento de TI**. Windows 10 proporciona nuevas funciones de implementación, escenarios y herramientas basadas en tecnologías incluidas en Windows 7 y Windows 8.1, al mismo tiempo que incorpora nuevos conceptos de Windows como servicio para mantener actualizado el sistema operativo. Este conjunto de cambios le obligan a [replantearse el proceso de implementación tradicional](https://technet.microsoft.com/itpro/windows/plan/windows-10-deployment-considerations). Después de implementar Windows 10, deberá [determinar la mejor manera de administrar equipos con Windows 10](https://docs.microsoft.com/intune/get-started/choose-how-to-manage-devices). Para ello, use Intune a fin de satisfacer sus necesidades empresariales y de productividad del usuario final. Tiene dos opciones: inscribir el equipo con Windows 10 como un dispositivo móvil o instalar el cliente de software de Intune para administrar el dispositivo como un equipo.

### <a name="manage-and-protect-company-data"></a>Administrar y proteger los datos de la empresa
En la actualidad, la mayoría de los trabajadores de la información está en constante movimiento, por lo que la productividad de los dispositivos móviles es esencial para ser competitivos. Estos empleados necesitan un acceso ininterrumpido a todas las aplicaciones y datos empresariales, en cualquier momento y desde cualquier lugar. EMS facilita esta tarea, tanto en un entorno local como en la nube.
- **Proteger los datos empresariales locales**. La mayoría de las estrategias de movilidad empresarial empiezan con un plan para permitir el acceso seguro al correo electrónico para los empleados con dispositivos móviles desde Internet, pero también es necesario tener un [acceso seguro a los datos empresariales locales](https://docs.microsoft.com/enterprise-mobility-security/solutions/conditional-access-intune-exchange) desde dispositivos móviles. Por ejemplo, muchas organizaciones todavía tienen datos y servidores de aplicaciones locales, como Microsoft Exchange, hospedados en la red corporativa.
- **Proteger los datos empresariales de Office 365**. [La protección de los datos empresariales de Office 365 (correo electrónico, documentos, mensajes instantáneos, etc.)](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-office365-data-with-intune) no podría ser más sencilla o transparente para los usuarios. Office 365 y EMS proporcionan una solución de acceso condicional integrada de forma única que garantiza que ningún usuario, aplicación o dispositivo puede tener acceso a los datos de Office 365 a menos que reúna los requisitos de cumplimiento de la empresa (como puede ser realizar una autenticación multifactor, inscribirse en Intune, usar una aplicación administrada, una versión de sistema operativo compatible, un PIN de dispositivo, un perfil de usuario bajo riesgo, etc.).
- **Proteger el acceso a Office 365 y los datos en dispositivos no administrados**. Una práctica de implementación común de Office 365 consiste en exigir que los dispositivos se inscriban en la administración, pero esto no siempre es necesario. Si solo es necesario tener acceso a los documentos y el correo electrónico de la empresa (lo que suele ser el caso de los dispositivos personales), puede usar las aplicaciones móviles de Office ([regidas por directivas de restricción de aplicaciones](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)) y no será preciso inscribir el dispositivo.

## <a name="leverage-cloud-security-and-protection"></a>Aprovechar la seguridad y la protección en la nube
EMS proporciona una solución de seguridad basada en identidad que ofrece un enfoque integral a los desafíos de seguridad de este mundo que da prioridad a los dispositivos móviles y la nube. Con EMS, no solo puede proteger los datos compartidos de la organización, sino que también puede identificar infracciones de seguridad antes de que causen daños.

### <a name="securely-share-data"></a>Compartir datos de forma segura
En la actualidad se produce un uso compartido de la información desde varios dispositivos y entre distintas organizaciones. Las empresas se enfrentan al desafío de identificar los datos que necesitan protección y los que no. Para lograrlo, puede [clasificar, etiquetar y proteger los datos confidenciales](https://docs.microsoft.com/enterprise-mobility-security/solutions/infoprotect-secure-classify-scenario) con [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) para asegurarse de que los datos empresariales importantes no corran peligro cuando se permite a los usuarios compartir lo que consideran importante para hacer su trabajo.

### <a name="identify-and-protect-against-threats"></a>Identificar las amenazas y protegerse contra ellas
<!-- Detect advanced threats on-premises and in the cloud (ATA, Azure AD, Cloud App Security) -->
Ahora que cada vez más organizaciones dan por supuesto que se producen infracciones, EMS ayuda a identificar los atacantes de la organización. Para ello, usa innovadores análisis de comportamiento y tecnologías de detección de anomalías, ya sea de manera local con [Microsoft Advanced Threat Analytics](http://www.microsoft.com/ata) como en la nube con [Azure Active Directory](http://www.microsoft.com/identity) y [Cloud App Security](http://www.microsoft.com/cloudappsecurity). Se ha mejorado la información sobre las amenazas gracias al gráfico de seguridad inteligente de Microsoft, que está basado en conjuntos de datos grandes y el aprendizaje automático en la nube.

## <a name="full-service-it-from-the-cloud"></a>Servicio de TI completo desde la nube
Cuando las organizaciones finalicen su transformación digital, el servicio de TI completo desde la nube se convertirá en lo más habitual. Las empresas con implementaciones en la nube consolidadas aprovecharán las funciones proporcionadas por EMS para habilitar escenarios de protección de datos e identidades a largo plazo y de un extremo a otro.

### <a name="identity-management-from-hire-to-retire"></a>Administración de identidades desde la contratación hasta la jubilación
Microsoft se ha dedicado a la protección de identidades basada en la nube durante más de una década y con Azure Active Directory, Microsoft está poniendo a disposición estos mismos sistemas de protección a los clientes empresariales, para asegurar la responsabilidad del usuario y del administrador con una mejor seguridad y control.
- **Miles de aplicaciones, una identidad**. Azure AD es una solución de administración de identidades y acceso en la nube que proporciona a las organizaciones acceso a todo lo que necesitan desde cualquier lugar. Azure Active Directory (Azure AD) hace que los usuarios sean más productivos, ya que [proporciona una identidad común para los usuarios de aplicaciones de software como servicio (SaaS)](https://docs.microsoft.com/enterprise-mobility-security/solutions/thousands-apps-one-identity) que obtienen acceso a los recursos locales y en la nube.
- **Permitir un negocio sin fronteras**. Las organizaciones necesitan [capacitar a sus empleados para tener acceso a todos sus datos y aplicaciones desde todos los dispositivos y todas las ubicaciones](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-business-without-borders). Los usuarios necesitan colaborar entre sí y con los partners y conectarse con los clientes.
- **Administrar el acceso a escala**. Azure AD proporciona un conjunto de herramientas para automatizar la [administración avanzada del ciclo de vida del usuario](https://docs.microsoft.com/enterprise-mobility-security/solutions/manage-access-at-scale) al aprovechar las reglas de pertenencia a grupos dinámicos y las funciones de administración de aplicaciones.
- **Protección con tecnología de nube**. Azure AD Identity Protection es un servicio de seguridad que proporciona una [vista consolidada de eventos de riesgo y posibles vulnerabilidades](https://docs.microsoft.com/enterprise-mobility-security/solutions/cloud-powered-protection) que afectan a las identidades de su organización.

### <a name="protect-shared-files-and-saas-apps-with-policies-and-tracking"></a>Proteger archivos compartidos y aplicaciones SaaS con directivas y seguimiento
EMS integra sin problemas la protección de datos de empresa avanzada en su rutina laboral para que sea fácil proteger la información empresarial frente a pérdidas de datos intencionadas y accidentales.
- **Compartir datos confidenciales interna y externamente**. Aunque muchas de las infracciones de datos son debido a ciberataques, los expertos están de acuerdo en que muchos son el resultado del error humano, conocido también como momentos "¡vaya!" que se producen cuando los empleados pierden accidentalmente datos empresariales confidenciales. [Con la información de seguridad adecuada y la aplicación de protocolos de prevención de pérdida de datos](https://docs.microsoft.com/enterprise-mobility-security/solutions/share-sensitive-data), casi todos estos tipos de infracciones son evitables.
- **Realizar un seguimiento del uso de datos compartidos y responder ante un abuso de datos**. [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) es una solución basada en la nube que ayuda a una organización a clasificar, etiquetar y proteger sus documentos y correos electrónicos. Esto puede realizarse automáticamente por administradores que definen reglas y condiciones, manualmente por los usuarios o una combinación en la que los usuarios reciben recomendaciones.
- **Administrar los datos a su manera con una implementación flexible y opciones de administración de claves**. En lugar de que Microsoft administre su clave de inquilino (opción predeterminada), podría [administrar por su cuenta la clave de inquilino de Azure Information Protection](https://docs.microsoft.com/en-us/information-protection/plan-design/plan-implement-tenant-key) para cumplir con las normas específicas que se aplican a su organización. La administración de su propia clave de inquilino también se conoce aportar su propia clave, o BYOK, por sus siglas del inglés.
- **Autorizar y administrar aplicaciones SaaS para los empleados**. Use [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) para autorizar o no aplicaciones, aplicar la prevención de pérdida de datos (DLP), controlar los permisos y el uso compartido, y generar alertas e informes personalizados.
- **Proteger los datos frente a errores de los usuarios**. Proporcionamos una gran visibilidad de la actividad del usuario y de los datos para que pueda [proteger la empresa si los usuarios toman decisiones poco recomendables](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-data-user-mistake) mientras trabajan con datos importantes de la empresa. Microsoft Cloud App Security proporciona visibilidad y controles para aplicaciones en la nube, incluido Office 365. Con Azure Information Protection, hemos combinado la clasificación y el etiquetado con la protección de datos persistentes para permitir un uso compartido seguro de archivos, tanto interna como externamente.


### <a name="learn-more"></a>Obtener más información

[Visitar la página de Microsoft Enterprise Mobility + Security](http://go.microsoft.com/fwlink/?LinkId=816837)

[Información sobre Enterprise Mobility + Security](learn-about-ems.md)

[Pruebe EMS de forma gratuita](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-security-trial)
