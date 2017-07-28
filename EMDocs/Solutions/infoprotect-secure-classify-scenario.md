---
title: "Proteger los datos mediante protección, clasificación y etiquetado | Microsoft Docs"
description: "Escenario en el que se describe cómo se puede usar Enterprise Mobility + Security para clasificar, etiquetar y proteger los datos mediante el aprovechamiento de las funciones de Microsoft Azure Information Protection."
author: yuridio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/17
ms.topic: solution
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 65409d5c-4f1b-4026-86e9-e65e1c4fe2b4
ms.reviewer: v-craic
ms.suite: ems
ms.openlocfilehash: 98bedbc50843cb7cfc284f5f29d40ca8b298f11a
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="secure-data-using-classification-labeling-and-protection"></a>Proteger los datos mediante la clasificación, el etiquetado y la protección

En la actualidad se produce un uso compartido de la información desde varios dispositivos y entre distintas organizaciones.  Es imprescindible garantizar que los datos corporativos fundamentales no corran peligro en este proceso, al mismo tiempo que se permite a los usuarios compartir de forma segura lo que es importante para la realización de sus tareas. Debido a tendencias actuales como la contratación de recursos externos, es posible que deba compartir los datos confidenciales de la empresa con contratistas y proveedores. Dado que no todo el contenido necesita la misma protección, las empresas se enfrentan al desafío de identificar qué datos necesitan protección y cuáles no.

Siga leyendo para obtener más información sobre cómo Enterprise Mobility + Security ayuda a abordar este escenario.

## <a name="how-can-enterprise-mobility--security-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security?

Enterprise Mobility + Security (EMS) es la única solución en la nube integral que protege los datos corporativos en el propio dispositivo y más allá con cuatro niveles de protección en las identidades, los dispositivos, las aplicaciones y los datos. EMS le ayuda a resolver uno de los principales retos de un mundo que prioriza la movilidad y la nube, es decir, cómo proporcionar datos seguros a los empleados con movilidad. Con EMS, podrá permitir que los empleados colaboren de forma segura dentro y fuera de la organización. EMS permite que los administradores de TI aprovechen Azure Information Protection para ayudar a proteger los datos corporativos en el nivel de archivo. Mediante esta funcionalidad, pueden estar seguros de que los datos siempre estarán protegidos, independientemente de dónde se almacenen, con quién se compartan, y si están en reposo o en tránsito.

## <a name="recommended-solution"></a>Solución recomendada

Azure Information Protection permite que las organizaciones clasifiquen, etiqueten y protejan los datos en el momento en que se crean o se modifican. Con Azure Information Protection, los usuarios pueden:

- Clasificar los datos según su confidencialidad y agregar etiquetas de forma manual o automática.
- Proteger los datos mediante cifrado, autenticación y derechos de uso.
- Habilitar una experiencia intuitiva y no invasiva para los usuarios finales.

La organización también tiene acceso a seguimiento e informes detallados para poder ver lo que ocurre con los datos compartidos y así administrarlos mejor. En el diagrama siguiente se resume el ciclo de vida de protección de la información:

![Ciclo de vida de protección de la información](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig1.png)

Vea en este breve vídeo una introducción rápida a la manera en que Azure Information Protection facilita la clasificación, el etiquetado y la protección de la información, incluso cuando sale de la organización.

<iframe src="https://channel9.msdn.com/Shows/Mechanics/An-Introduction-to-Microsoft-Azure-Information-Protection/player" width="560" height="315" allowFullScreen frameBorder="0"></iframe>

## <a name="how-to-implement-this-solution"></a>Cómo implementar esta solución

Siga estos pasos para implementar la clasificación, el etiquetado y la protección de los datos mediante Azure Information Protection:

- Paso 1: prepararse para la clasificación y la protección de los datos
- Paso 2: configurar directivas y etiquetas de protección de información
- Paso 3: implementar la clasificación automática basada en contenido
- Paso 4: configurar las condiciones para la clasificación automática y recomendada

## <a name="how-to-secure-data-using-classification-labeling-and-protection-with-azure-information-protection"></a>Cómo proteger los datos mediante la clasificación, el etiquetado y la protección con Azure Information Protection

Las empresas deben identificar qué datos necesitan protección y qué datos no necesitan el mismo nivel de protección. Los pasos siguientes le guiarán por las tareas principales que se deben llevar a cabo para permitir que el departamento de TI implemente Azure Information Protection.

### <a name="step-1-preparing-for-document-protection-and-content-classification"></a>Paso 1: prepararse para la protección de documentos y la clasificación de contenido

Antes de implementar esta solución, revise los [requisitos de Azure Information Protection](/information-protection/get-started/requirements) y asegúrese de que Azure Rights Management esté activado. Si está activado, verá la pantalla siguiente en Azure Portal:

![Portal de Azure](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig2.png)

Cuando activa Azure Rights Management, puede proteger datos importantes con aplicaciones y servicios que admiten esta solución de protección de información. También puede administrar y supervisar los correos electrónicos y archivos protegidos que posee su organización. Debe activar Azure Rights Management para poder empezar a usar las características de Rights Management en Office, SharePoint y Exchange para proteger los archivos confidenciales o con información importante.

### <a name="step-2-configure-information-protection-policies-and-labels"></a>Paso 2: configurar directivas y etiquetas de protección de información

Cuando planee implementar directivas y etiquetas de protección de información, siga estas indicaciones:

- Clasifique los datos según su confidencialidad.
- Empiece por los datos más confidenciales.
- El departamento de TI puede establecer reglas automáticas, pero los usuarios pueden complementarlas.
- Asocie acciones, como distintivos visuales y protección.

En el diagrama siguiente se incluye un ejemplo de cómo se puede implementar:

![Clasificación](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig3.png)

Azure Information Protection incluye etiquetas predeterminadas, pero puede [personalizarlas](/information-protection/deploy-use/configure-policy-new-label) y también puede crear sus propias etiquetas o subetiquetas que los usuarios verán en la barra de Information Protection.

> [!IMPORTANT]
> Las etiquetas son metadatos que se escriben en los documentos. Las etiquetas contienen texto no cifrado para que otros sistemas puedan leerlas, como un motor DLP.

En el ejemplo siguiente, verá que se han creado subetiquetas personalizadas bajo la etiqueta **Secret**:

![Etiqueta](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig4.png)

Una vez que haya definido cómo va a usar las etiquetas (predeterminadas o personalizadas), [configure una etiqueta para aplicar la protección de Rights Management](/information-protection/deploy-use/configure-policy-new-label).

### <a name="step-3-implement-content-based-automatic-classification"></a>Paso 3: implementar la clasificación automática basada en contenido

Con Azure Information Protection, la clasificación de los datos y los controles de protección se integran en Office y otras aplicaciones comunes. Esta integración proporciona opciones sencillas con un solo clic para proteger los datos con los que trabajen los usuarios. En Azure Portal, puede aplicar patrones predefinidos, como “números de tarjeta de crédito” o “números del seguro social de EE. UU.”, como condición para la clasificación automática. Como alternativa, puede usar patrones de texto y expresiones regulares para definir una cadena o patrón personalizados.

Al configurar las condiciones de una etiqueta, puede asignar automáticamente una etiqueta a un documento o correo electrónico, o bien puede pedirles a los usuarios que seleccionen la etiqueta que recomienda. Consulte [How to configure conditions for automatic and recommended classification for Azure Information Protection](/information-protection/deploy-use/configure-policy-classification) (Cómo configurar las condiciones para la clasificación automática y recomendada en Azure Information Protection) para obtener más información sobre cómo realizar esta configuración.


### <a name="step-4-configure-conditions-for-automatic-and-recommended-classification"></a>Paso 4: configurar las condiciones para la clasificación automática y recomendada

Los administradores de TI pueden establecer directivas para aplicar automáticamente a los datos la clasificación y la protección. Las directivas también pueden basarse en el contenido en el que esté trabajando y pueden configurarse para solicitar a los usuarios que usen la clasificación sugerida. Esta es la lista de condiciones integradas:

- Código SWIFT
- Número de la tarjeta de crédito
- Número de enrutamiento ABA
- Número de la Seguridad Social (SSN) de EE. UU.
- Número de cuenta bancaria internacional (IBAN)

Consulte [Information about the built-in conditions](/information-protection/deploy-use/configure-policy-classification#information-about-the-built-in-conditions) (Información sobre las condiciones integradas) para obtener más detalles sobre este tipo de implementación.
