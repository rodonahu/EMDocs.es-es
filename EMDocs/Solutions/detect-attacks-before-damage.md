---
title: "Detectar ataques antes de que produzcan daños | Microsoft Docs"
description: "Escenario que describe cómo Enterprise Mobility + Security puede usarse para proteger los datos corporativos de ataques antes de que produzcan daños aprovechándose de Advanced Threats Analytics, Cloud App Security y Azure Active Directory Premium."
author: yuridio
ms.author: yurid
manager: swadhwa
ms.date: 01/23/2017
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: 
ms.assetid: de0a7e70-008b-45c1-bba8-f033b1f62194
ms.reviewer: v-craic
ms.suite: ems
ms.custom: advanced-threat-analytics, cloud-app-security
ms.openlocfilehash: 420df3bfcc0fca07bf4f7b068f4d49015ace048f
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2017
---
# <a name="detect-attacks-before-they-cause-damage"></a>Detectar ataques antes de que produzcan daños
Una posición de seguridad sólida necesita disponer de un sistema de detección avanzada para poder identificar amenazas antes de que provoquen daños importantes. Las organizaciones pueden aprovechar perfectamente la inteligencia de seguridad de Microsoft para detectar actividades sospechosas locales y en la nube.

Un sistema de detección sólido debe revelar cualquier actividad sospechosa y amenazas de punto de anclaje con una visibilidad profunda y un análisis de comportamiento en curso. Esto permite que TI adopte acciones inmediatas contra los ataques detectados y optimice la recuperación con un soporte sólido.


## <a name="how-can-enterprise-mobility--security-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security?
Microsoft Enterprise Mobility + Security permite que TI identifique a los atacantes de su organización con un análisis de comportamiento innovador y tecnologías de detección de anomalías, en un entorno local y en la nube.  Ayudará a TI a detectar los ataques malintencionados conocidos y las vulnerabilidades de seguridad conocidas en sus sistemas.

## <a name="recommended-solution"></a>Solución recomendada
Para atender los requisitos de este escenario, EMS usa [Advanced Threats Analytics](https://docs.microsoft.com/en-us/advanced-threat-analytics/), [Cloud App Security](https://docs.microsoft.com/en-us/cloud-app-security/what-is-cloud-app-security) y [Azure Active Directory Premium](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-get-started-premium). Al implementar estas tecnologías, las organizaciones podrán:

- Detectar o identificar un comportamiento anómalo con un análisis de comportamiento innovador y tecnologías de detección de anomalías aprovechando el aprendizaje automático
- Detectar ataques malintencionados conocidos (es decir, pass-the-hash, pass-the-ticket) y vulnerabilidades de seguridad conocidas
- Centrarse en lo que es importante rápidamente y en la información de ataques relevante
- Identificar anomalías e infracciones de directivas que pueden indicar una infracción de seguridad

En el diagrama siguiente se resumen las funciones implicadas en este escenario y su uso para proteger los recursos:

![Gráfico que muestra las capacidades de cada solución de producto y cómo funcionan para protegerse contra los ataques.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig1.png)

# <a name="how-to-detect-attacks-before-they-cause-damage"></a>Cómo detectar ataques antes de que produzcan daños
Tradicionalmente, las inversiones de seguridad se han centrado solo en la protección. En cambio, hoy en día es imprescindible tener también una respuesta y una detección correctas. Las organizaciones de TI deben centrarse en un enfoque que busque la manera de proteger, detectar y responder a las amenazas.

![Gráfico que muestra el proceso en curso de protección, detección y respuesta a las amenazas.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig2.png)

El equipo de TI debe buscar la manera de proteger correctamente la identidad, los datos, las aplicaciones, los dispositivos y la infraestructura; en un entorno local y en la nube.  Esto requiere un enfoque de la seguridad que considere todos los puntos finales, desde sensores al centro de datos. En el pasado, los administradores de TI se basaban en firmas de malware para reconocer amenazas.

Las herramientas de seguridad de TI tradicionales proporcionan una protección limitada contra los sofisticados ataques de seguridad cibernética cuando se roban las credenciales de usuario. La configuración inicial, la creación de reglas y el ajuste preciso son complicados y pueden tardar años. Cada día, recibe varios informes repletos de falsos positivos. La mayoría de las veces, no tiene los recursos para revisar esta información y, aunque los tuviera, puede que no tenga las respuestas, ya que estas herramientas están diseñadas para proteger el perímetro, impidiendo primero a los atacantes que obtengan acceso. Hoy en día, los ataques complejos de seguridad cibernética requieren un enfoque diferente.

Para mitigar las amenazas actuales en este nuevo escenario de ataques de seguridad cibernética, el equipo de TI necesita soluciones innovadoras de detección de amenazas aprovechando los análisis de comportamiento y las tecnologías de aprendizaje automático para que puedan reconocer completamente nuevas amenazas con rapidez.  Aprovechando ATA y Cloud App Security para detectar ataques locales y en la nube, TI puede responder rápidamente a los incidentes antes de que provoquen daños importantes en el entorno.

Lea [Planeamiento de la capacidad de ATA](https://docs.microsoft.com/en-us/advanced-threat-analytics/plan-design/ata-capacity-planning) antes de implementar ATA de manera local, así como [Requisitos previos de ATA](https://docs.microsoft.com/en-us/advanced-threat-analytics/plan-design/ata-prerequisites) para obtener consideraciones generales antes de instalar ATA. Use la [lista de comprobación previa a la instalación](https://docs.microsoft.com/en-us/advanced-threat-analytics/deploy-use/preinstall-ata) para validar si la infraestructura está preparada para recibir ATA. Una vez que termine esta fase de planeación y validación, estará preparado para [implementar ATA](https://docs.microsoft.com/en-us/advanced-threat-analytics/deploy-use/install-ata-step1). Cuando ATA se haya implementado en el entorno, la configuración es mínima y se iniciará inmediatamente para obtener información sobre el entorno y desencadenar alertas si encuentra ataques malintencionados conocidos. Siga el paso 1 para usar [ATA](https://docs.microsoft.com/en-us/advanced-threat-analytics/understand-explore/what-is-ata) para identificar cualquier actividad sospechosa en el entorno local.

Para detectar amenazas en las aplicaciones en la nube, este escenario usa [Cloud App Security](https://docs.microsoft.com/en-us/cloud-app-security/what-is-cloud-app-security). Asegúrese de seguir las [instrucciones generales de instalación](https://docs.microsoft.com/en-us/cloud-app-security/general-setup) para instalar Cloud App Security y use la opción [Cloud Discovery](https://docs.microsoft.com/en-us/cloud-app-security/set-up-cloud-discovery) para analizar los registros de tráfico en el catálogo de aplicaciones en la nube de Cloud App Security. Siga el paso 2 para usar Cloud App Security para detectar amenazas e infracciones de cumplimiento.

## <a name="how-to-implement-this-solution"></a>Cómo implementar esta solución
Siga estos pasos para implementar [Advanced Threats Analytics](https://docs.microsoft.com/en-us/advanced-threat-analytics/) y [Cloud App Security](https://docs.microsoft.com/en-us/cloud-app-security/what-is-cloud-app-security):

- Paso 1: usar Advanced Threat Analytics (ATA) para detectar cualquier actividad sospechosa en el entorno local
- Paso 2: usar Cloud App Security para detectar amenazas e infracciones de cumplimiento para las aplicaciones en la nube  

### <a name="step-1-using-ata-to-detect-suspicious-activity"></a>Paso 3: usar ATA para detectar cualquier actividad sospechosa
Los informes constantes de las herramientas de seguridad tradicionales y examinarlos con ellas para localizar las alertas importantes y pertinentes puede resultar abrumador. En su lugar, ATA proporciona un informe fácil de usar, sencillo de clasificar y con un suministro similar a las redes sociales para ayudar a TI a centrarse en lo importante rápidamente. Presentar esta cantidad de datos como una escala de tiempo le proporciona el poder de la perspectiva, e información sobre quién está teniendo acceso a qué datos, cuándo están teniendo acceso y cómo están accediendo a estos.

Cuando abre la [escala de tiempo de ataques](https://docs.microsoft.com/en-us/advanced-threat-analytics/deploy-use/working-with-suspicious-activities) en ATA, ve un informe completo con actividades sospechosas que muestran las [entidades](https://docs.microsoft.com/en-us/advanced-threat-analytics/plan-design/ata-architecture) que se han visto involucradas en esta actividad y cuáles son las recomendaciones:

![Captura de pantalla de la escala de tiempo de ataques con un informe de las actividades sospechosas.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig3.png)

En este ejemplo, existe un evento que indica la sospecha de robo de identidad mediante un ataque del tipo "pass-the-ticket". También tiene una lista de recomendaciones que pueden usarse para los pasos de corrección inicial. En este ejemplo, ATA ha proporcionado una alerta ya que el vale Kerberos del administrador se ha robado del servidor SHAREDADMIN-SRV a EXTVENDOR-TS y se ha usado para tener acceso a DC01. Puede ir más allá en el proceso de investigación haciendo clic en cualquier objeto de este evento. Por ejemplo, al hacer clic en el proveedor externo Terminal Server (EXTVENDOR-TS), tendrá acceso a todas las [actividades sospechosas](https://docs.microsoft.com/en-us/advanced-threat-analytics/deploy-use/working-with-suspicious-activities) en las que este servidor se ha visto implicado.

ATA usa el aprendizaje automático en sus motores de detección y deterministas para establecer y comprender los patrones normales de comportamiento de usuarios y entidades, y es esa capacidad única la que nos permite proporcionar alertas precisas y oportunas en una gran variedad de vectores de ataque.


### <a name="step-2-using-cloud-app-security-to-detect-threats-and-policy-violations-for-cloud-apps"></a>Paso 2: usar Cloud App Security para detectar amenazas e infracciones de directiva para las aplicaciones en la nube

Cada vez más organizaciones están adoptando aplicaciones de SaaS, no solo para reducir costos si no también para desbloquear ventajas competitivas como una mejora del tiempo de comercialización y una mejor colaboración. Aunque su empresa no use aplicaciones en la nube, sus empleados probablemente sí lo hagan. Según la investigación, más del 80 % de los empleados admiten usar aplicaciones de SaaS no aprobadas en sus trabajos.

Con esta rápida transición a las aplicaciones en la nube, sabemos que puede estar preocupado sobre el almacenamiento de sus datos corporativos en la nube y sobre cómo hacer que estén accesibles para los usuarios en cualquier lugar sin una completa visibilidad, auditoría y controles. Las soluciones de seguridad heredadas no están diseñadas para proteger datos en aplicaciones de SaaS. Las soluciones tradicionales de seguridad de red, como firewalls y direcciones IP, no ofrecen visibilidad en las transacciones que son únicas a cada aplicación ni tráfico fuera del entorno local, incluido cómo se usan y almacenan los datos. Los controles clásicos no pueden proporcionar protección a las aplicaciones en la nube, ya que solo supervisan un pequeño subconjunto de tráfico de nube y tienen un entendimiento limitado de las actividades en el nivel de aplicación.

Entonces, ¿cómo puede mantener la visibilidad, el control y la protección de sus aplicaciones en la nube? Tenemos la solución:

Microsoft Cloud App Security es un servicio completo que proporciona una visibilidad más profunda, controles completos y una protección mejorada para sus aplicaciones en la nube. Cloud App Security está diseñado para ayudarle a ampliar la visibilidad, la auditoría y el control que tiene en el entorno local de sus aplicaciones en la nube.

Cloud App Security proporciona no solo visibilidad y control, sino también una protección contra amenazas eficaz para sus aplicaciones en la nube, mejorada con una amplia investigación e inteligencia de amenazas de Microsoft. Puede identificar el uso de alto riesgo e incidentes de seguridad, y detectar un comportamiento anómalo de usuarios para evitar amenazas.

Al acceder al panel de Cloud App Security, tiene una vista completa del estado de seguridad de sus aplicaciones en la nube, incluida una sección dedicada a las alertas:

![Captura de pantalla del panel de Cloud App Security que incluye alertas abiertas.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig6.png)

Puede hacer clic en el menú Alertas para tener acceso al [centro de alertas](https://docs.microsoft.com/en-us/cloud-app-security/monitor-alerts). El centro de alertas recopila alertas de una amplia variedad de categorías, incluidas la detección de amenazas, las cuentas con privilegios y las infracciones de cumplimiento.

![Captura de pantalla del centro de alertas que muestra una lista de cada alerta.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig5.png)

El centro de alertas recopila todas las marcas rojas que Cloud App Security ha identificado, incluidas las infracciones de cumplimiento de detección de amenazas y anomalías y las cuentas con privilegios. La heurística de aprendizaje automático avanzado de Cloud App Security obtiene información sobre cómo interactúa cada usuario con cada aplicación en la nube y, a través de un análisis de comportamiento, evalúa el riesgo de cada transacción.

Cuando está investigando una alerta, puede hacer clic en el nombre de la alerta para obtener más información sobre esta. En el siguiente ejemplo, la alerta se está refiriendo a una coincidencia en la [directiva de archivos](https://docs.microsoft.com/en-us/cloud-app-security/data-protection-policies) *Archivos confidenciales públicos compartidos*, que se considera de alta prioridad ya que puede provocar una pérdida de datos.   

![Captura de pantalla de los detalles específicos de una de las alertas.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig7.png)

Aunque el ejemplo anterior se basaba en una infracción de directiva, Cloud App Security también puede [detectar anomalías](https://docs.microsoft.com/en-us/cloud-app-security/anomaly-detection-policy#anomaly-detection-policy-reference). Cloud App Security tiene un período de aprendizaje inicial de 7 días, durante el cual no marca ningún usuario nuevo, actividad, dispositivos o ubicaciones como erróneos. Transcurrido este tiempo, cada sesión se compara con la actividad, los momentos en que los usuarios estaban activos, las direcciones IP, los dispositivos, etc., que se detectaron durante el mes anterior y se asigna una puntuación de riesgo a estas actividades. La descripción de este tipo de alerta se denomina Detección de anomalías general y, una vez que hace clic en ella, verá una pantalla similar a la siguiente:

![Captura de pantalla que muestra anomalías que se han detectado mediante Cloud App Security.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig8.png)

En esta página, puede ver qué usuario ha desencadenado la alerta, la dirección IP, la pertenencia a grupos del usuario y más información sobre el comportamiento sospechoso. Puede ver más detalles sobre esta actividad, que incluye los intentos de inicio de sesión con errores, la ubicación dónde se ha originado el inicio de sesión y la aplicación que se ha usado para realizar el intento de inicio de sesión.
