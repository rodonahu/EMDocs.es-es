---
title: Uso compartido de datos confidenciales interna y externamente | Microsoft Docs
description: "Escenario en el que se describe cómo se puede usar Enterprise Mobility + Security para compartir datos confidenciales interna y externamente los datos mediante el aprovechamiento de las funciones de Microsoft Azure Information Protection."
author: yuridio
ms.author: yurid
manager: swadhwa
ms.date: 01/23/2017
ms.topic: solution
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: a996fbf8-ece4-40bc-b866-d4606c230027
ms.reviewer: v-craic
ms.suite: ems
ms.openlocfilehash: 3d84bbe6d252976e1a3152f65003787e37d408c8
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="share-sensitive-data-internally-and-externally"></a>Uso compartido de datos confidenciales interna y externamente

Aunque muchas de las infracciones de datos son debido a ciberataques, los expertos están de acuerdo en que muchos son el resultado del error humano, conocido también como momentos "¡vaya!" que se producen cuando los empleados pierden accidentalmente datos empresariales confidenciales. Con la información de seguridad adecuadas y los protocolos de prevención de pérdida de datos en su lugar, casi todos estos tipos de infracciones son evitables.

Para los usuarios y empresas, el uso compartido de datos es inevitable y cuando es necesario, también se genera uno de los mayores desafíos del sector, que es: ¿cómo habilitar el uso compartido de datos en los diferentes dispositivos a la vez que se reduce la fuga de datos compartidos con otras personas? El panorama de amenazas es incluso más amplio cuando necesite compartir información confidencial con orígenes externos, como partners, clientes y otros.

![Diagrama](./media/share-sensitive-data/share-sensitive-data-fig1.png)

En este contexto, es un escenario común para las empresas tener proyectos donde tengan que permitir que los empleados colaboren internamente en silos de datos y externamente con los proveedores de terceros, y alinear los protocolos de seguridad con el comportamiento del usuario empresarial y la influencia de los procesos de clasificación y protección de datos.

## <a name="how-can-enterprise-mobility--security-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security?

Enterprise Mobility + Security (EMS) es la única solución en la nube integral que protege de forma nativa los datos corporativos en el propio dispositivo y más allá con cuatro niveles de protección en las identidades, los dispositivos, las aplicaciones y los datos. EMS le ayuda a resolver uno de los principales retos de un mundo que prioriza la movilidad y la nube, es decir, cómo proporcionar un correo electrónico seguro a los empleados con movilidad. Con EMS, podrá permitir que los empleados colaboren de forma segura dentro y fuera de la organización. EMS permite a los administradores de TI aprovechar la plantilla de la directiva de [Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms) para el uso de correo electrónico. Los derechos de uso están asociados al propio mensaje, por lo que la protección se produce en línea y sin conexión, además de dentro y fuera del firewall de la organización.

## <a name="recommended-solution"></a>Solución recomendada

Mediante la integración de Azure Rights Management con Rights Management en Exchange Online, EMS permite a las organizaciones proteger los datos que deja la organización a través de correo electrónico. Puede implementar esta solución para servidores de Exchange que se encuentran localmente y para Exchange Online (Office 365). Tanto Information Rights Management como [Cifrado de mensajes de Office 365](https://technet.microsoft.com/library/dn569285.aspx) son directivas basadas y diseñadas para trabajar con el motor de reglas de transporte de Exchange. Esto significa que Microsoft Azure Rights Management le permite configurar las restricciones de directiva complejas fácilmente, con solo una única acción.

A continuación se describen algunas de las capacidades disponibles con estas soluciones:

- Ayude a proteger los correos electrónicos contra accesos no autorizados mediante la aplicación de diferentes opciones de IRM a los mensajes de correo electrónico.
- Ayude a mantener su información segura, en línea o sin conexión, porque los archivos están protegidos si se visualizan con Office Online o se descargan en un equipo local.
- La integración perfecta con todos los documentos de Office ayuda a proteger la propiedad intelectual de su organización.
- Aplique plantillas personalizadas según sus necesidades empresariales, además de usar plantillas de Rights Management Services de forma predeterminada.


## <a name="how-to-implement-this-solution"></a>Cómo implementar esta solución

Para configurar Exchange Online para que sea compatible con Azure RMS, debe configurar el servicio Information Rights Management (IRM) para Exchange Online. Siga estos pasos para implementar esta solución:

1. Integración con Exchange:
    - Exchange Online: Habilitación de Exchange Online para usar Azure RMS
    - Exchange local: Implementación del conector de Azure Rights Management
2. Envío de un documento de Office protegido con Exchange

## <a name="how-to-share-sensitive-data-internally-and-externally"></a>Cómo compartir datos confidenciales interna y externamente

Las empresas tienen que permitir que los empleados colaboren internamente en silos de datos y externamente con los proveedores de terceros, y alinear los protocolos de seguridad con el comportamiento del usuario empresarial y la influencia de los procesos de clasificación y protección de datos. Los recursos compartidos de datos se convierten en una parte fundamental del proceso y las organizaciones deben habilitarse mientras disminuye la probabilidad de privacidad de los datos y la integridad se ve comprometida.

### <a name="step-1-integration-with-exchange"></a>Paso 1: Integración con Exchange

La protección de Rights Management se aplica al correo electrónico mediante la aplicación de una plantilla de directiva de Azure Rights Management a un mensaje de correo electrónico. El primer paso para habilitar la integración para que se produzca variará en función de dónde se encuentra Exchange: en la nube (Exchange Online) o local.

#### <a name="enable-rights-management-integration-with-exchange-online"></a>Habilitación de la integración de Rights Management con Exchange Online

Para configurar Exchange Online para que sea compatible con Azure RMS, debe configurar el servicio Information Rights Management (IRM) para Exchange Online. En el artículo [Office 365: Configuración para clientes y servicios en línea](https://docs.microsoft.com/rights-management/deploy-use/configure-office365), siga los pasos de la sección [Exchange Online: configuración de IRM](https://docs.microsoft.com/rights-management/deploy-use/configure-office365#exchange-online-irm-configuration) para configurar Exchange Online para IRM.

El último paso debe ser la prueba final para validar la configuración y debe ver un resultado similar al mostrado en la siguiente pantalla:

![PowerShell](./media/share-sensitive-data/share-sensitive-data-fig2.png)

#### <a name="enable-rights-management-integration-with-exchange-on-premises"></a>Habilitación de la integración de Rights Management con Exchange local

Para configurar la integración de Rights Management con Exchange local, debe configurar el conector de Microsoft Rights Management (RMS). Este conector habilitará servidores Exchange locales existentes para usar su funcionalidad de Information Rights Management (IRM) con el servicio Rights Management de Microsoft basado en la nube (Azure RMS). Puede usar este conector incluso si algunos de los usuarios se conectan a servicios en línea, en un escenario híbrido.

Revise los [requisitos previos para instalar el conector RMS](https://docs.microsoft.com/rights-management/deploy-use/deploy-rms-connector#prerequisites-for-the-rms-connector) y siga los cinco pasos disponibles en el artículo [Instalación y configuración del conector de Azure Rights Management](https://docs.microsoft.com/rights-management/deploy-use/install-configure-rms-connector).

### <a name="step-2-send-a-protected-document-using-exchange"></a>Paso 2: Envío de un documento protegido con Exchange

Siga el paso 3 del escenario [Protección de datos mediante la clasificación y el etiquetado](infoprotect-secure-classify-scenario.md) para instalar la aplicación RMS Sharing. Si necesita admitir distintos tipos de clientes, consulte el artículo [Aplicación de uso compartido de Rights Management: Instalación y configuración para clientes](https://docs.microsoft.com/rights-management/deploy-use/configure-sharing-app) para obtener más detalles sobre cómo instalar la aplicación RMS Sharing.

Si desea compartir un documento de Office, por ejemplo directamente desde Word, puede usar simplemente el icono de uso compartido protegido de la cinta de opciones como se muestra en la siguiente imagen:

![ShareProtect](./media/share-sensitive-data/share-sensitive-data-fig3.png)

Tras hacer clic en esta opción debería ver el cuadro de diálogo de recurso compartido protegido con más detalles acerca de cómo desea compartir este documento tal como se muestra en la siguiente imagen:

![Compartir](./media/share-sensitive-data/share-sensitive-data-fig4.png)

En esta ventana debe escribir el correo electrónico del usuario de destino y seleccionar el tipo de acceso que desea proporcionar para este usuario. En la parte inferior de esta ventana, también puede controlar la fecha de expiración del documento y habilitar la opción para recibir un correo electrónico cada vez que alguien intente abrir este documento. Después de finalizar de realizar las selecciones adecuadas, haga clic en Enviar y se abrirá Outlook con un nuevo mensaje como se muestra en la siguiente pantalla:

![Correo electrónico](./media/share-sensitive-data/share-sensitive-data-fig5.png)

> [!IMPORTANT]
> Consulte la presentación [Colaboración de forma segura mediante Azure Information Protection](https://myignite.microsoft.com/videos/49947) desde Microsoft Ignite para obtener más información sobre este escenario.
