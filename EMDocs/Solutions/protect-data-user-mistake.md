---
title: "Protección de datos frente a errores de los usuarios | Protección de la información de Azure Active Directory"
description: "Un escenario que describe cómo se puede utilizar Enterprise Mobility + Security para proteger los datos corporativos de los errores de usuario y evitar la pérdida de datos aprovechando las capacidades de Cloud App Security y Azure Information Protection."
author: yuridio
ms.author: yurid
manager: swadhwa
ms.date: 10/24/2016
ms.topic: solution
ms.prod: 
ms.service: cloud-app-security
ms.technology: techgroup-identity
ms.assetid: 0af3894c-7b0e-4c0c-8874-31e041d81300
ms.reviewer: v-craic
ms.suite: ems
ms.custom: information-protection
translationtype: Human Translation
ms.sourcegitcommit: 02b0e611805ad2214b1b108b8c466590aad7999a
ms.openlocfilehash: 669042461511939695717de1d5d22c14c071923c


---

# <a name="protect-data-against-user-mistakes"></a>Protección de datos frente a errores de los usuarios

Mientras que la transición a la nube y la movilidad aumentó sustancialmente la productividad de los empleados, la interacción compleja entre los usuarios, dispositivos, aplicaciones y datos locales, y en la nube, han generado nuevos puntos ciegos para los equipos de TI. Aunque las organizaciones pueden no adoptar esta transición, ya son empleados. Como las interacciones entre estos componentes y la sofisticación de aumenta de vectores de ataque aumenta, la seguridad sigue siendo un desafío para las empresas. El personal de TI lucha por mantener la visibilidad, control y protección de datos corporativos.

Los recursos de control de datos que protegen los datos corporativos de los errores de usuario y evitan la pérdida de datos son pasos importantes para proteger los recursos a la vez que permite a los usuarios ser productivos.

## <a name="how-can-enterprise-mobility-security-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security?

Enterprise Mobility + Security (EMS) permite al departamento de TI obtener una visibilidad más profunda de usuario, dispositivo y actividad de datos locales y en la nube.  Con EMS, el departamento de TI puede proteger los datos corporativos de los errores de usuario con un cumplimiento y controles más sólidos.  El departamento de TI podrá supervisar detección de riesgos mediante informes y análisis eficaces de los usuarios, el tráfico de carga y descarga, los patrones de uso y las transacciones para aplicaciones detectadas.

## <a name="recommended-solution"></a>Solución recomendada

Para satisfacer los requisitos de este escenario, EMS usa [Cloud App Security](https://technet.microsoft.com/library/mt489024.aspx) y [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection). Al implementar estas tecnologías, las organizaciones podrán disponer de lo siguiente:

- Visibilidad completa de uso de aplicaciones en la nube del empleado y TI en la sombra
- Directivas de control y datos de nivel granular para la protección de datos continua en aplicaciones en la nube
- Clasificación de datos persistente y protección que garantiza que los datos están protegidos en todo momento, independientemente de dónde estén almacenados o con quién se compartan
- Capacidad de compartir datos de forma segura con personas dentro y fuera de su organización
- Controles intuitivos para la clasificación y la protección de los datos
- Visibilidad y control de los datos compartidos para usuarios y TI

En el diagrama siguiente se resumen las funciones implicadas en este escenario y su uso para proteger los recursos:

![Gráfico que muestra cómo funcionan conjuntamente Cloud App Security y Azure Information Protection para proteger los datos localmente y en la nube.](./media/protect-data-user-mistake/protect-data-user-mistake-fig1-1.png)

## <a name="how-to-implement-this-solution"></a>Cómo implementar esta solución

Siga estos pasos para implementar [Cloud App Security](https://technet.microsoft.com/library/mt668458.aspx) y [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection):

- Paso 1: Detectar aplicaciones en la nube en uso y controlarlas con la directiva
- Paso 2: Proteger datos a nivel local o en la nube

## <a name="how-to-protect-data-against-user-mistakes"></a>Cómo proteger datos frente a errores de los usuarios

La mayoría de las empresas de hoy en día usan aplicaciones en la nube y pronto habrá un momento en el que se almacenen más datos corporativos en la nube que localmente. Muchas veces, los usuarios utilizarán las aplicaciones SaaS desde sus dispositivos sin consentimiento ni conocimiento de la empresa, lo que provocará un aumento en el uso de TI en la sombra de la nube. Esta conclusión procede de estudio que demuestra que el 80 % de los empleados admitieron usar aplicaciones SaaS no aprobadas para uso corporativo. [Cloud App Security](https://technet.microsoft.com/library/mt657567.aspx) ofrece una descripción detallada de todas las aplicaciones en la nube que se usan en la organización. Identifica todos los usuarios y direcciones IP que tienen acceso a una aplicación. También lleva a cabo una evaluación de riesgos más de 13.000 aplicaciones en la nube y proporciona una puntuación de riesgo automatizada para cada aplicación basada en más de 60 parámetros.

Siga el paso 1 para detectar las aplicaciones en la nube en su entorno e implementar directivas para controlar estas aplicaciones. La segunda fase de esta solución implementará [Azure Information Protection](https://docs.microsoft.com/en-us/information-protection/get-started/requirements) para proteger y clasificar datos, lo que puede reducir el uso incorrecto de datos y errores de los usuarios.

### <a name="step-1-discover-cloud-apps-in-use-and-control-them-with-policy"></a>Paso 1: Detectar aplicaciones en la nube en uso y controlarlas con la directiva

El primer paso para utilizar Cloud App Security es [detectar las aplicaciones](https://technet.microsoft.com/en-us/library/mt657567.aspx). Si omite este paso, no habrá ninguna aplicación para analizar y para restringir el uso de directivas. Si no inició el proceso de detección, la opción de detección del panel de Cloud App Security mostrará el mensaje siguiente:

![Captura de pantalla muestra el mensaje de que el usuario todavía no ha cargado un registro de Cloud Discovery.](./media/protect-data-user-mistake/protect-data-user-mistake-fig2-1.png)

La detección de qué aplicaciones están en uso en la organización es el primer paso para asegurarse de que se protegen los datos corporativos confidenciales. Una vez que finalice el proceso de detección, podrá ver una lista de las aplicaciones que se han detectado en el panel de [Cloud Discovery](https://technet.microsoft.com/en-us/library/mt727946.aspx).

![Captura de pantalla que muestra el panel de Cloud Discovery y una lista de aplicaciones que se detectaron.](./media/protect-data-user-mistake/protect-data-user-mistake-fig3.png)

Cada aplicación tiene una puntuación que representa la credibilidad y la confiabilidad de las aplicaciones en la nube. Al obtener acceso a la jerarquía de la aplicación, observará que hay tres categorías que se utilizan para crear este rango: general, seguridad y cumplimiento normativo. Cada categoría tiene ciertos atributos que se comprueban durante el proceso de detección. Si un atributo no es totalmente compatible, se mostrará como parcial y puede tener acceso a los detalles de ese atributo para entender por qué se muestra como parcial.

![Captura de pantalla que muestra detalles del atributo "Encabezados de seguridad HTTP".](./media/protect-data-user-mistake/protect-data-user-mistake-fig4.png)

El siguiente paso es controlar el comportamiento de las aplicaciones que se detectaron mediante directivas. Esta capacidad permite al departamento de TI optimizar las aplicaciones detectadas y el nivel de riesgo asociado para su organización. Hay diferentes tipos de directivas; la que debe crear en primer lugar depende de los requisitos empresariales de su organización. De forma predeterminada, la Directiva de detección de anomalías está habilitada, por lo que no es necesario configurar una nueva directiva para que funcione. Sin embargo, puede ajustar los tipos de anomalías que desea recibir alertas acerca de la directiva predeterminada.

![Captura de pantalla que muestra cómo puede seleccionar un tipo de directiva que crear.](./media/protect-data-user-mistake/protect-data-user-mistake-fig5.png)

Una vez configurada la directiva, puede investigar posibles infracciones en la directiva que estén actualmente en su lugar. En este escenario concreto, desea comprobar si hay cualquier información personal identificable (PII) compartida en la nube. La información acerca de este tipo de actividad está disponible a través de la directiva de archivo. La directiva de nivel de archivo que se observará es la directiva de cumplimiento de PII. El propósito de esta directiva es identificar los archivos que contienen información de identificación personal que se comparten públicamente y también proporcionan opciones para la investigación y corrección.

![Captura de pantalla que muestra cómo investigar el tipo de directiva de archivo para posibles infracciones.](./media/protect-data-user-mistake/protect-data-user-mistake-fig6.png)

En este caso, hay tres coincidencias para esta directiva, lo que significa que hay tres archivos que coinciden con esta directiva. Puede hacer clic en uno para investigar el nombre de archivo y su ubicación.

### <a name="step-2-protect-data-on-premises-or-in-the-cloud"></a>Paso 2: Proteger datos a nivel local o en la nube

Antes de implementar esta solución, revise los requisitos de Azure Information Protection y asegúrese de que Azure Rights Management esté activado.

La protección de la información de Microsoft Azure le ayuda a clasificar y etiquetar los datos en el momento de creación. La protección (cifrado, autenticación y derechos de uso) puede aplicarse a los datos confidenciales. La protección y las etiquetas de clasificación son persistentes, viajan con los datos, por lo que son identificables y cuentan con protección en todo momento, independientemente de donde se almacenen o con quién se compartan. Cuando planee implementar directivas y etiquetas de protección de información, siga estas indicaciones:



- Clasifique los datos según su confidencialidad.
- Empiece por los datos más confidenciales.
- El departamento de TI puede establecer reglas automáticas, pero los usuarios pueden complementarlas.
- Asocie acciones, como distintivos visuales y protección.

Azure Information Protection incluye etiquetas predeterminadas, pero puede personalizarlas y también puede crear sus propias etiquetas o subetiquetas que los usuarios verán en la barra de Information Protection.

> [!NOTE]
> Las etiquetas son metadatos que se escriben en los documentos. Las etiquetas contienen texto no cifrado para que otros sistemas puedan leerlas, como un motor DLP.

En el ejemplo siguiente, verá que se han creado subetiquetas personalizadas bajo la etiqueta Secret:

![Captura de pantalla que muestra las subetiquetas personalizadas creadas bajo la etiqueta "Secret". ](./media/protect-data-user-mistake/protect-data-user-mistake-fig7.png)


Una vez que haya definido cómo va a usar las etiquetas (predeterminadas o personalizadas), [configure una etiqueta para aplicar la protección de Rights Management](https://docs.microsoft.com/en-us/rights-management/information-protection/configure-policy-protection#to-configure-a-label-to-apply-rights-management-protection).

Con Azure Information Protection, la clasificación de los datos y los controles de protección se integran en Office y otras aplicaciones comunes. Esta integración proporciona opciones sencillas con un solo clic para proteger los datos con los que trabajen los usuarios. En Azure Portal, un administrador aplicar patrones predefinidos, como “números de tarjeta de crédito” o “números del seguro social de EE. UU.”, como condición para la clasificación automática. Como alternativa, pueden usar patrones de texto y expresiones regulares para definir una cadena o patrón personalizados.

Al configurar las condiciones de una etiqueta, puede asignar automáticamente una etiqueta a un documento o correo electrónico, o bien puede pedirles a los usuarios que seleccionen la etiqueta que recomienda. Consulte [How to configure conditions for automatic and recommended classification for Azure Information Protection](https://docs.microsoft.com/en-us/rights-management/information-protection/configure-policy-classification) (Cómo configurar las condiciones para la clasificación automática y recomendada en Azure Information Protection) para obtener más información sobre cómo realizar esta configuración.

> [!NOTE]
> Para más información sobre la protección y clasificación de datos, lea [Seguridad de los datos mediante la clasificación, el etiquetado y la protección](https://docs.microsoft.com/en-us/enterprise-mobility-security/solutions/infoprotect-secure-classify-scenario).



<!--HONumber=Dec16_HO2-->


