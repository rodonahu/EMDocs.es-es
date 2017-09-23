---
title: Microsoft 365 Enterprise | Microsoft docs
description: "Proporciona información general y describe los servicios de Microsoft 365 Enterprise."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/15/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 14f22a558e2e437f1491033eb33858b377eeca9d
ms.sourcegitcommit: d8588b191a4f9daea73698426dd632e7997140dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2017
---
# <a name="microsoft-365-enterprise-overview"></a>Información general de Microsoft 365 Enterprise
Microsoft 365 Enterprise está diseñado para organizaciones grandes e incorpora Office 365 Enterprise, Windows 10 Enterprise y Enterprise Mobility + Security (EMS) para ofrecer la posibilidad a todos los usuarios de ser creativos y trabajar juntos de forma segura. Microsoft 365 Enterprise incluye una edición empresarial de las aplicaciones de Windows 10 y Office a través de Office 365 ProPlus.

Tanto Windows 10 como Office 365 ProPlus proporcionan nuevas versiones de características a la empresa en marzo y septiembre a través del Canal semianual. Una versión de características del Canal semianual se admite durante 18 meses. Microsoft Intune y System Center Configuration Manager proporcionan funcionalidades para implementar y actualizar Windows 10 y Office 365 ProPlus.

En esta sección se proporciona información general sobre los servicios de EMS y Office 365 que incluye Microsoft 365 Enterprise. También se presentan los conceptos básicos necesarios para entender cómo aprovechar estas herramientas con el fin de satisfacer las necesidades de su organización. Estos servicios aportan capacidades que permiten a los administradores empresariales de Microsoft Cloud proteger la identidad y los dispositivos de los empleados, además de controlar el acceso a los datos en tránsito o en reposo de la empresa.

|Service|Descripción|
|-------|-----------|
|[Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)|Azure AD incluye un conjunto completo de capacidades de administración de la identidad, como la autenticación multifactor, el registro de dispositivos, la administración de contraseñas y grupos de autoservicio, el control de acceso basado en roles, la supervisión del uso de aplicaciones, la auditoría avanzada y la supervisión y los avisos de seguridad.|
|[Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)|Con este servicio, podrá detectar posibles vulnerabilidades que afecten a las identidades de su organización y configurar respuestas automáticas mediante directivas de acceso condicional para inicios de sesión y usuarios de riesgo bajo, medio o alto.|
|[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)|Gracias a este servicio, las organizaciones pueden minimizar el número de usuarios que tiene acceso permanente a operaciones privilegiadas. Azure AD Privileged Identity Management crea la figura del administrador temporal. Los administradores temporales deberían ser usuarios que necesiten disponer de acceso privilegiado de vez en cuando, pero no constantemente. Este rol está inactivo hasta que el usuario necesita acceso. Entonces, debe completar un proceso de activación para convertirse en administrador activo durante un período de tiempo predeterminado.|
|[Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)| Azure Information Protection es una solución basada en la nube que forma parte de EMS E5. Permite a las organizaciones clasificar, etiquetar y proteger sus documentos y correos electrónicos. Esto puede realizarse automáticamente por administradores que definen reglas y condiciones, manualmente por los usuarios o una combinación en la que los usuarios reciben recomendaciones. Use las etiquetas de Azure Information Protection para aplicar la clasificación a los documentos y correos electrónicos. Al hacer esto, la clasificación se puede identificar en cualquier momento, independientemente de dónde se almacenen los datos o con quién se compartan. <br><br>La configuración de directivas de Azure Information Protection está protegida por [Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms). De manera similar a las etiquetas que se aplican, la protección que se aplica mediante Rights Management permanece con los documentos y los correos electrónicos, independientemente de la ubicación, ya sea dentro o fuera de la organización, las redes, los servidores de archivos y las aplicaciones.|
|[Microsoft Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune es un servicio de administración de movilidad empresarial (EMM) basado en nube que ayuda a los empleados a ser productivos mientras mantiene protegidos los datos corporativos. Intune se integra estrechamente con Azure AD para controlar el acceso y la identidad. También se usa para administrar dispositivos y aplicaciones. Las capacidades de [administración de dispositivos de Intune](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) sirven para configurar y proteger los dispositivos de los usuarios, incluidos los PC Windows. <br><br>Las capacidades de administración de dispositivos de Intune admiten el método de inscripción [Bring Your Own Device (BYOD)](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod), que permite a los usuarios inscribir sus teléfonos, tabletas o equipos personales. También admite el método [Corporate-owned Device (COD)](https://docs.microsoft.com/enterprise-mobility-security/solutions/issue-corp-devices), que ofrece varios escenarios de administración, como la inscripción automática, los dispositivos compartidos o las configuraciones de requisitos de inscripción con autorización previa. Para mayor seguridad, incluso puede requerir MFA para inscribir un dispositivo. Una vez inscrito en el sistema de administración, Intune puede configurar las características y las opciones del dispositivo para habilitar el acceso seguro a los recursos de la compañía.|


Estas son las versiones más recientes de Windows 10, Office 365 ProPlus, Microsoft Intune y System Center Configuration Manager:

|     |**Canal semianual (destino)**|**Canal semianual **|
|:-----|:-----|:-----|
|**Windows 10**|Windows 10 Fall Creators Update (próximamente)|Versión 1703|
|**Office 365 ProPlus**|Versión 1708|Versión 1705|
|**Intune**|No aplicable|Versión 1708|
|**System Center Configuration Manager**|Technical Preview versión 1708|Versión 1706<sup>*</sup>|

<sup>*</sup> La actualización 1706 para la rama actual de System Center Configuration Manager está disponible como actualización en consola para sitios instalados previamente que ejecutan la versión 1606, 1610 o 1702.

> [!NOTE]
> Los servicios de Microsoft Azure también se actualizan de forma periódica, pero no se hace referencia a ellos mediante un número de versión. Para revisar las actualizaciones más recientes, y las que se proporcionarán próximamente, para los servicios de Azure, consulte la [guía básica de la plataforma en la nube](https://www.microsoft.com/cloud-platform/roadmap).

Para más información sobre las características disponibles en estas versiones, vea los siguientes artículos:
- [Novedades de Windows 10](https://docs.microsoft.com/windows/whats-new/)
- [Información sobre la versión de Windows 10](https://technet.microsoft.com/windows/release-info)
- [Historial de actualizaciones para Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history)
- [Versiones de canal de actualización de cliente de Office 365](https://technet.microsoft.com/office/mt465751)
- [Novedades de Microsoft Intune](https://docs.microsoft.com/intune/whats-new)
- [Novedades de System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-incremental-versions)
- [Capacidades de Technical Preview 1708 para System Center Configuration Manager](https://docs.microsoft.com/sccm/core/get-started/capabilities-in-technical-preview-1708)

## <a name="security-best-practices-and-recommendations"></a>Sugerencias y procedimientos recomendados de seguridad
Aunque no existe una sola recomendación ideal para todos los entornos de cliente, en el artículo [Recommended security policies and configurations](microsoft-365-policies-configurations.md) (Configuraciones y directivas de seguridad recomendadas) se presentan conceptos importantes sobre procedimientos recomendados de seguridad. En este artículo también se describen recomendaciones generales de Microsoft sobre cómo aplicar directivas y configuraciones en Microsoft Cloud para garantizar que sus empleados estén protegidos y sean productivos.


## <a name="deploy-windows-10-and-office-365-proplus"></a>Implementación de Windows 10 y Office 365 ProPlus
Obtenga información sobre cómo implementar Windows 10 y Office 365 ProPlus e integrar en Microsoft Azure Active Directory (Azure AD) o local Active Directory Domain Services (AD DS). Implemente Windows 10, Office 365 ProPlus y el resto de aplicaciones de línea de negocio en dispositivos nuevos o actualice dispositivos existentes a Windows 10 mediante Intune, System Center Configuration Manager y directiva de grupo para administrar los dispositivos.

Para obtener más información, vea los siguientes artículos:
- [Consideraciones de implementación para Windows 10](https://docs.microsoft.com/windows/deployment/planning/windows-10-deployment-considerations)
- [Guía de implementación para Office 365 ProPlus](https://support.office.com/article/f99f8cd0-e648-4834-8f45-f5637351899d)
- [Guía de procedimientos recomendados para implementar Office 365 ProPlus en un entorno empresarial](https://support.office.com/article/31a384ca-650c-4265-b76c-a87b414fd8b8)
- [Implementación de aplicaciones de Office 365 ProPlus a dispositivos Windows 10 con Intune](https://docs.microsoft.com/intune/apps-add-office365)

Para obtener ayuda para la implementación con Microsoft 365, [póngase en contacto FastTrack](https://fasttrack.microsoft.com/microsoft365).

## <a name="manage-updates-to-windows-10-and-office-365-proplus"></a>Administración de las actualizaciones a Windows 10 y Office 365 ProPlus
Los vínculos siguientes le muestran cómo obtener el máximo control sobre la calidad y las actualizaciones de características para Windows 10 y Office 365 ProPlus. Aprenda a controlar el uso de ancho de banda de forma eficaz y a mantener Windows y Office al día con las características, funcionalidades y actualizaciones de seguridad más recientes.

Para obtener más información, vea los siguientes artículos:
- [Información general de Windows como servicio](https://docs.microsoft.com/windows/deployment/update/waas-overview)
- [Información general sobre los canales de actualización de Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)
- [Administración de actualizaciones de software con Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure)
- [Implementar las actualizaciones de Windows 10 con System Center Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)<sup>*</sup>
- [Administración de Office 365 ProPlus con Configuration Manager](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates)

<sup>*</sup>Microsoft anima a las organizaciones que actualmente utilizan Configuration Manager para la administración de actualizaciones de Windows para continúen haciéndolo para equipos cliente Windows 10.

## <a name="next-steps"></a>Pasos siguientes
[Más información sobre los servicios de Microsoft 365 Enterprise](services-overview.md)

[Página del producto Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)

[Guía básica de la plataforma en la nube](https://www.microsoft.com/cloud-platform/roadmap)

