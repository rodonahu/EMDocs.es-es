---
title: Proteger documentos de empresa que ejecutan complementos de Microsoft Office - Microsoft 365 Enterprise | Microsoft Docs
description: "Explica cómo usar WIP e Intune para proteger datos de empresa en documentos que ejecutan complementos de Office."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/14/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 5f43eba8b95b0eefaaef6e95bce6fd5d8c1f6695
ms.sourcegitcommit: d8588b191a4f9daea73698426dd632e7997140dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2017
---
# <a name="use-wip-and-intune-to-protect-enterprise-data-in-documents-running-office-add-ins"></a>Usar WIP e Intune para proteger datos de empresa en documentos que ejecutan complementos de Office
Cuando los usuarios de una organización usan complementos de Office para interactuar con datos de la organización, esto plantea el riesgo potencial de que algunos datos se filtren. Puede usar Windows Information Protection (WIP) y Microsoft Intune para proteger los datos de empresa cuando los usuarios ejecutan complementos de Office.

[WIP](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip), anteriormente conocido como Protección de datos de empresa (EDP), permite a las empresas proteger la propiedad intelectual y los datos corporativos. WIP ayuda a proteger los datos y las aplicaciones de empresa frente a filtraciones de datos accidentales en dispositivos propiedad de la empresa y personales que los empleados llevan al trabajo sin necesidad de realizar cambios en el entorno u otras aplicaciones.

[Intune](https://www.microsoft.com/cloud-platform/microsoft-intune) proporciona un conjunto diverso de herramientas para administrar el complejo entorno móvil. La combinación de Intune de opciones de administración de aplicaciones móviles y administración de dispositivos ofrece a los administradores de TI y a los usuarios finales flexibilidad para administrar y proteger la productividad móvil.

Puede usar Intune para [crear e implementar la directiva de WIP](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/overview-create-wip-policy). Con Intune, puede elegir las aplicaciones protegidas y el nivel de protección de WIP, así como buscar datos de empresa en la red.

Con WIP e Intune:

-   Las empresas pueden proporcionar una aplicación de directivas de datos corporativos razonable, incluso cuando se descargan los datos en dispositivos personales.

-   Las empresas pueden usar educación sobre directivas contextual para informar a los usuarios sobre cómo protegerse frente a la divulgación de datos accidental a servicios y aplicaciones no administrados.

-   Los usuarios finales pueden cumplir las directivas de datos corporativas sin interrumpir su flujo de trabajo habitual.

-   Los usuarios finales pueden realizar una transición sin problemas entre la productividad personal y laboral.

WIP e Intune se ejecutan de forma silenciosa en segundo plano y son prácticamente invisibles cuando los usuarios no mezclan contenido personal y empresarial.

Los [complementos de Office](https://dev.office.com/docs/add-ins/overview/office-add-ins) se basan en tecnologías web. Incorporan la eficacia y la información de Internet a las aplicaciones de Office. Los complementos interactúan con el contenido de una aplicación de Office a través de las API disponibles en Office.js. Los principios básicos de los complementos de Office incluyen:

-   **Seguridad**: la arquitectura de la plataforma JavaScript de Office garantiza que el código del complemento esté en un espacio aislado y se ejecuta en un proceso independiente con respecto a la aplicación host de Office. Esto permite a la plataforma tomar medidas correctivas cuando un complemento no cumple los estándares de rendimiento o es potencialmente malintencionado al notificar al usuario y, en algunos casos, deshabilitar el complemento. Esta arquitectura funciona en todas las plataformas que admiten complementos de Office.

-   **Resistencia**: la naturaleza "fuera de proceso" de la plataforma del complemento garantiza que el propio complemento no afecte a la experiencia del usuario ni al rendimiento de la aplicación host de Office. Esto es fundamental para que Office se muestre rápido y dinámico ante las acciones del usuario.

-   **Multiplataforma**: si se escribe una vez, se ejecuta allá donde se ejecute Office. Los complementos actualmente se admiten en Windows, Office Online, Mac e iPad. En breve se ofrecerá compatibilidad con complementos de Android y la plataforma Universal.

Los complementos de Office pueden trabajar con contenido de empresa y potencialmente confidencial de un documento. Como parte de la extensibilidad de la aplicación, los complementos heredan su acceso de la directiva de la aplicación host. Por ejemplo, si la configuración de WIP evita que Word acceda a contenido de empresa, los complementos no podrán acceder a contenido de empresa en un documento de Word.

Uno de los objetivos de los complementos es acabar con cualquier problema de bloqueo de los usuarios finales a la vez que garantizar que los administradores de empresa puedan bloquear los complementos en caso necesario. Los principios fundamentales de los complementos de Office con respecto a la habilitación de la protección de datos incluyen:

-   Proporcionar una manera de que los administradores de TI eviten la carga de los complementos.

-   Minimizar o eliminar el trabajo que deben realizar los administradores para que los complementos estén listos para la empresa.

-   Minimizar los mensajes para los usuarios finales mientras se usa el complemento.

-   Eliminar los mensajes para los usuarios finales cuando el documento y el complemento tienen el mismo contexto.

## <a name="add-ins-and-wip"></a>Complementos y WIP

Cuando se habilita WIP en el entorno, se pueden habilitar los siguientes escenarios para los complementos de Office:

-   Los complementos de Office se activan con el contexto del documento. En Outlook, el contexto del complemento se basa en el buzón activo actual. Los permisos del complemento se definen claramente en el mensaje Confianza antes de activar el complemento. El usuario decide si el complemento es adecuado en un documento concreto y si se permite ejecutarlo.

-   Los administradores pueden usar la directiva de grupo para bloquear todos los complementos de la Tienda Office o todos los complementos de Office. Esto significa que los usuarios pueden activar únicamente complementos de confianza de un [catálogo corporativo de Office 365 o SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog).

-   Los administradores pueden bloquear complementos en el nivel de firewall mediante la administración de dispositivos móviles (MDM). Tenga en cuenta que esto no funciona en escenarios móviles o Bring Your Own Device (BYOD).

-   Los complementos aplican la operación de copiar y pegar entre contextos personales y empresariales. Por ejemplo, cuando un usuario copia desde un complemento de contexto empresarial y pega en un documento personal, se muestra el mensaje predeterminado de copiar y pegar entre contextos.

En la tabla siguiente se muestra el comportamiento esperado del complemento en contextos y documentos personales y empresariales cuando WIP está habilitado.

> [!NOTE]
> - Las operaciones de cortar, copiar y pegar dentro y fuera de la aplicación host funcionan según lo previsto en todos los escenarios.
> - La transferencia de datos a servicios de complemento no está protegida en todos los escenarios.

|**Tipo de documento o buzón**|**Complemento en contexto personal**|**Complemento en contexto empresarial**|
|:----------------|:-------------------------------------------------|:---------------------------------------------------|
|**Personal**     |El complemento se carga en contexto personal.<br><br>No se permite la navegación a direcciones URL de la empresa (aunque estén en su propio dominio de aplicación).<br><br>Se permite la navegación a direcciones URL personales.|El complemento no se carga ni se activa.<br><br>Si se eleva el contexto del documento (por ejemplo, se almacena en una ubicación de empresa):<br><br>- Se permite la navegación a direcciones URL de empresa.<br><br>- Se permite la navegación a direcciones URL personales.|
|**Empresarial**   |El complemento se carga en contexto empresarial.<br><br>Se permite la navegación a direcciones URL de empresa.<br><br>Se permite la navegación a direcciones URL personales.|El complemento se carga en contexto empresarial.<br><br>Se permite la navegación a direcciones URL de empresa.<br><br>Se permite la navegación a direcciones URL personales.|
|**Sin guardar**      |El complemento se carga en contexto personal.<br><br>No se permite la navegación a direcciones URL de la empresa (aunque estén en su propio dominio de aplicación).<br><br>Se permite la navegación a direcciones URL personales.|El complemento se carga en contexto empresarial y el documento se convierte de forma silenciosa al contexto empresarial. Esto significa que el documento debe guardarse en una ubicación de empresa.<br><br>Se permite la navegación a direcciones URL de empresa. Se permite la navegación a direcciones URL personales.            |


## <a name="add-ins-and-intune"></a>Complementos e Intune

En Office para iPad, los complementos actualmente se admiten en Word, Excel y PowerPoint. Outlook en este momento admite complementos en iOS (iPad e iPhone). Los administradores de Outlook pueden desactivar los complementos de forma predeterminada, incluidos los complementos instalados por el desarrollador, y habilitar solo los complementos concretos aprobados por la organización. En la tabla siguiente se indica la compatibilidad de los escenarios de protección de datos con los complementos que se ejecutan en dispositivos de Office para iOS que usan las herramientas de Intune App Protection.

> [!NOTE]
> Para más información sobre los complementos de Outlook que se ejecutan en dispositivos iOS y Android, vea [Administrar el acceso del usuario a aplicaciones para Outlook](https://technet.microsoft.com/library/jj943757(v=exchg.150).aspx) y [Complementos para Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).

|**Tipo de documento o buzón**|**Complementos en contexto personal para iOS con Intune App Protection<sup>*</sup>**|**Complementos en contexto empresarial para iOS con Intune App Protection<sup>*</sup>**|
|:-----|:-----|:-----|
|**Personal**|El uso de complementos no se ve afectado por Intune App Protection en documentos personales.|El uso de complementos no se ve afectado por Intune App Protection en documentos personales.|
|**Empresarial**|Se pueden activar complementos personales.<br><br>Las directivas de Intune App Protection pueden proteger escenarios de cortar, copiar, pegar y transferencia de datos entre el complemento y otras aplicaciones del dispositivo.<br><br>La transferencia de datos a servicios de complemento no está protegida.|Se pueden activar complementos empresariales. Los administradores pueden controlar qué complementos se publican a través de las herramientas de administración de Office [(implementación centralizada de Office 365)](https://support.office.com/article/Deploy-Office-add-ins-in-the-Office-365-admin-center-737e8c86-be63-44d7-bf02-492fa7cd9c3f).<br><br>Las directivas de Intune App Protection pueden proteger escenarios de cortar, copiar, pegar y transferencia de datos entre el complemento y otras aplicaciones del dispositivo.<br><br>La transferencia de datos a servicios de complemento no está protegida.|

>**<sup>*</sup>** Los administradores pueden usar la [implementación centralizada de Office 365](https://support.office.com/article/Deploy-Office-add-ins-in-the-Office-365-admin-center-737e8c86-be63-44d7-bf02-492fa7cd9c3f) para implementar complementos de Word, Excel y PowerPoint en usuarios individuales, grupos o una organización directamente desde el centro de administración de Office 365 o mediante scripts de PowerShell. Cuando los usuarios abren una aplicación de Office en Windows, Mac u Office Online, el complemento se instala automáticamente en la cinta de opciones.

## <a name="summary"></a>Resumen

Dados los principios con respecto a los complementos de Office, WIP e Intune permiten a los administradores administrar los datos de empresa y proporcionar las herramientas que los usuarios finales necesitan para realizar su trabajo. Esto se traduce en la posibilidad de que datos empresariales se filtren fuera de los límites de la organización. Las API de JavaScript de Office no proporcionan de momento ninguna manera para que los desarrolladores reconozcan el tipo de datos que se transmiten entre el documento de Office y el complemento. Esto exige que los desarrolladores muestren varios mensajes para el usuario y, en algunos casos, provoca que se marquen erróneamente archivos personales como archivos de empresa, lo que puede tener un impacto negativo en la experiencia del usuario, además de no satisfacer los principios de protección de datos.

Microsoft está comprometido con la protección de los datos del cliente y va a seguir esforzándose por mejorar la experiencia y las tecnologías de Intune y WIP.

## <a name="learn-more"></a>Más información

-   [Instrucciones generales y procedimientos recomendados para Windows Information Protection (WIP)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/guidance-and-best-practices-wip)

-   [¿Qué es Intune?](https://docs.microsoft.com/intune/introduction-intune)

-   [Información general de los métodos de inscripción de dispositivos](https://docs.microsoft.com/sccm/mdm/plan-design/device-enrollment-methods)

-   [Cambio de la autoridad de MDM](https://docs.microsoft.com/sccm/mdm/deploy-use/change-mdm-authority)

-   [Preparativos para configurar directivas de protección de aplicaciones para Windows 10](https://docs.microsoft.com/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10)
