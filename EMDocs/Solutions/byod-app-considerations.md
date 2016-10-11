---
title: Consideraciones sobre las aplicaciones
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 4b871c74-fec8-45e2-8b45-6ef0e62f7cc6
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 0808c833aa2b6f36baa8d8f48ce797cc9f18aafa
ms.openlocfilehash: 2340a5578d01f52e672a3b399ec1200dcff9373d


---


# Consideraciones sobre las aplicaciones

Las consideraciones sobre las aplicaciones para BYOD pueden variar según los recursos, las restricciones y los objetivos de la compañía. Las empresas deben evaluar sus aplicaciones actuales, las tecnologías empleadas para desarrollar las aplicaciones, los requisitos para que las aplicaciones se ejecuten en cualquier dispositivo y las aplicaciones esenciales para que los usuarios puedan acceder desde cualquier ubicación. Aunque los recursos consumidos en el aprovisionamiento y la implementación de aplicaciones modernas son inferiores a los de las aplicaciones basadas en Windows, sigue habiendo un costo asociado a su desarrollo y mantenimiento.

Hay patrones para las aplicaciones desarrolladas específicamente para los escenarios BYOD, y debe evaluar si las aplicaciones actuales tienen estos patrones y decidir si va a adaptar estas aplicaciones a un escenario BYOD o proporcionar una experiencia heredada para que los usuarios puedan acceder a ellas desde sus dispositivos. Puede usar la siguiente lista para identificar estos patrones:

- Comprender al usuario: ¿qué problema está intentando resolver con esta aplicación? ¿El problema es relevante para el usuario? Lo principal que hay que tener en cuenta es la experiencia del usuario con la aplicación y qué es lo que quiere lograr con ella.
- Simplicidad: los usuarios deben sentirse cómodos aprendiendo a usar las aplicaciones de forma autónoma y con las guías mínimas. Los usuarios deben poder navegar a través de las opciones sin perderse.
- Agilidad en las actualizaciones: la estrategia para las aplicaciones móviles es dar a los usuarios la posibilidad de utilizarlas inmediatamente y enviar comentarios para mejorar las aplicaciones. Ofrecer una aplicación perfecta en la primera versión no es factible para las aplicaciones móviles. Debe hacer que el ciclo de versiones sea más ágil y responda rápidamente a los comentarios. Proporciónela ahora y haga cambios continuos a lo largo del ciclo de vida de la aplicación.
- Rendimiento: aunque las aplicaciones tradicionales basadas en Windows pueden ser más eficaces porque se ejecutan en equipos, los usuarios dan por sentado que las aplicaciones basadas en Windows usan más recursos. Las aplicaciones móviles deben estar diseñadas para ahorrar recursos. Debe centrarse en lo que necesita ofrecer al usuario para que tenga la mejor experiencia posible.

Para obtener más información sobre consideraciones generales a la hora de crear aplicaciones móviles, lea [10 considerations when creating mobile apps for business](https://www.microsoft.com/en-gb/developers/articles/week01jan14/10-considerations-when-creating-mobile-apps-for-business) (Diez consideraciones sobre la creación de aplicaciones móviles para empresas).

## Experiencia

Para mejorar la experiencia de usuario según la plataforma en la que se ejecutarán las aplicaciones y la estrategia de implementación, la empresa debe identificar qué aplicaciones se publicarán y cómo lo hará. Si se identifica que hay un entorno heterogéneo y que algunos dispositivos serán compatibles en la empresa, una estrategia podría consistir en publicar las aplicaciones a través del Portal de la empresa. En última instancia, las decisiones empresariales dirigirían las consideraciones de la experiencia del usuario. ¿Está dispuesta la empresa a desarrollar aplicaciones que proporcionarán la misma experiencia independientemente de la plataforma? De lo contrario, ¿la empresa ofrecerá cursos a los usuarios para aprender a usar estas aplicaciones en distintas plataformas sin tener la misma experiencia?
Tenga en cuenta el costo y el rendimiento de la inversión de cada caso mencionado en el párrafo anterior. Puede ser factible consolidar todas las aplicaciones en una página de portal web principal que proporcione la misma experiencia, pero las aplicaciones se comportarían de forma diferente según la plataforma.

Tendrá que limitar las opciones a las aplicaciones basadas en web y las aplicaciones modernas, dado que las aplicaciones para los usuarios remotos deben ejecutarse en más de una plataforma, deben ser lo más ligeras posible y deben requerir un acceso mínimo a los dispositivos de los usuarios. La sección siguiente lo ayudará a determinar la experiencia de aplicación que se debe utilizar para la solución.

### Opciones de experiencias de aplicación: ventajas y desventajas

Mediante la siguiente lista, podrá conocer las ventajas y desventajas de las opciones de experiencias de aplicación:

- Basada en Web
    - Ventajas
        - Se encuentra ampliamente disponible en numerosas plataformas.
        - Cuenta con cifrado mediante el protocolo HTTPS.
        - Dispone de una tecnología consolidada.
        - Su uso resulta sencillo.
        - No se requiere la instalación en los dispositivos de los usuarios.
    - Desventajas
        - No cuenta con la apariencia nativa de una aplicación móvil.
        - Puede requerir la instalación de componentes de terceros (por ejemplo, Flash) en los dispositivos de los usuarios.
        - Es susceptible a las vulnerabilidades del navegador.
- Moderno
    - Ventajas
        - Presenta una apariencia moderna.
            - Ofrece una experiencia más enriquecida para los usuarios finales.
            - El desarrollador establece los controles de seguridad.
            - Aprovecha las API del sistema operativo local.
            - Puede ejecutarse en distintas plataformas.
            - No se basa en el navegador web para funcionar.
    - Desventajas
        - Debe instalarse en los dispositivos de los usuarios.
        - Requiere una infraestructura back-end para implementar aplicaciones en los dispositivos de los usuarios.
        - Es posible que los desarrolladores deban optimizar sus conocimientos para desarrollar aplicaciones mediante este formato nuevo.


### Requisitos de las aplicaciones: consideraciones

Evalúe las aplicaciones que se ajustarán para que las usen los usuarios remotos desde sus dispositivos, y asegúrese de que se presenten estos requisitos a los usuarios. A continuación, encontrará una lista con requisitos de las aplicaciones y consideraciones relativas a cada uno de ellos:

- **Acceso a Internet / acceso a servicios en la nube** Si las aplicaciones precisan de conexión a Internet para funcionar, tenga en cuenta los siguientes aspectos:
    - Las aplicaciones deben poder transferir datos cifrados.
    - Las aplicaciones deben consumir un ancho de banda mínimo.
    - Evalúe la posibilidad de usar los servicios de notificaciones push de Windows para las actualizaciones.
    - Las aplicaciones deben poder interactuar con un servidor proxy en el caso de que la empresa use este tipo de tecnología para permitir el acceso a Internet.
    - Las aplicaciones deben poder usar la conexión Wi-Fi de los dispositivos móviles.
- **Recopilación de información de los usuarios** si las aplicaciones requieren la recopilación de información de los usuarios para funcionar, tenga en cuenta los siguientes aspectos:
    - Las aplicaciones deben indicar detalladamente la información que se recopilará de los usuarios, y estos deben estar de acuerdo con esta recopilación.
    - Si se va a transferir información privada, asegúrese de que los datos estén cifrados.
    - Si se va a almacenar información privada en los dispositivos de los usuarios, asegúrese de que los datos estén cifrados.
- **Integración con redes sociales** Si las aplicaciones precisan de la integración con redes sociales para funcionar, tenga en cuenta los siguientes aspectos:
    - Evalúe el método de autenticación que se usará para permitir que las aplicaciones se autentiquen con las redes sociales.
    - Compruebe el nivel de integración con las redes sociales para evitar la pérdida de datos en un público más amplio.
    - Asegúrese de que las aplicaciones indiquen detalladamente la información que compartirá el usuario en la red social en cuestión.
    - Asegúrese de que los datos enviados al proveedor de red social estén cifrados.

Para mejorar la experiencia del usuario también debe clasificar todas las aplicaciones en función de los estándares de su equipo de desarrollo para evitar que los usuarios deban desplazarse por centenares de aplicaciones.

## Plataforma

Al tratar con la experiencia del usuario, es normal que se evalúen distintas plataformas y se determine a qué está dispuesta la empresa a dar soporte. Muchas veces, el hecho de permitir que los usuarios usen sus propios dispositivos significa tener un ecosistema heterogéneo, y es posible que TI no esté preparado para admitir dicho ecosistema.

Cada plataforma tiene distintos requisitos para registrar y publicar aplicaciones, lo que afecta directamente a los recursos de TI porque TI necesita evaluar todo el ciclo de vida de las aplicaciones que se ejecutan en una plataforma específica. También debe acceder a los requisitos de la plataforma de las aplicaciones para las soluciones de infraestructura BYOD. En la siguiente sección, se incluyen consideraciones clave sobre los requisitos de la plataforma de aplicaciones.

### Requisitos de la plataforma de aplicaciones: consideraciones

A continuación, encontrará una lista con requisitos de las plataformas de las aplicaciones y consideraciones relativas a cada uno de ellos:

- Infraestructura de back-end
    - Determine si la ampliación de las aplicaciones para que las usen los usuarios remotos afectará al rendimiento global del servidor de las aplicaciones.
    - En función de esta evaluación, compruebe la necesidad de actualizar los servidores, aumente el número de servidores o virtualice los servidores.
- Compatibilidad
    - Defina las plataformas compatibles con la empresa (como Windows, iOS y Android).
        - Si la empresa decide adoptar todas las plataformas, defina los límites de compatibilidad para cada plataforma.
    - Establezca los escenarios compatibles y no compatibles con la empresa. Por ejemplo: su empresa podría decidir no admitir los dispositivos con jailbreak.
- Plataforma del sistema operativo
    - Defina las restricciones de cada sistema operativo para ejecutar las aplicaciones de la empresa.
    - Defina los requisitos mínimos de las aplicaciones en cada sistema que la empresa decida admitir.
    - Pruebe las aplicaciones en cada sistema operativo para comprobar si las aplicaciones tienen un comportamiento similar en cada uno de ellos. Documentar las diferencias.

Como parte de la estrategia para admitir varias plataformas debe definir cómo consumirán las plataformas estas aplicaciones. Con Microsoft Intune, puede permitir que los usuarios utilicen las aplicaciones mediante el [portal de empresa](http://apps.microsoft.com/windows/app/company-portal/4b1dff1a-e76f-4fdd-a993-9c59048c3768). Esta posibilidad no solo se encuentra disponible para Windows, sino también para otras [plataformas](http://blogs.technet.com/b/windowsintune/archive/2013/11/25/windows-intune-company-portals-for-ios-and-android-now-available.aspx). Al planear las aplicaciones a las que podrán acceder los usuarios a través del Portal de la empresa, tenga en cuenta los dos tipos de aplicaciones que pueden estar disponibles a través del Portal de la empresa:

- Aplicaciones de prueba instaladas: aplicaciones LOB modernas desarrolladas y publicadas en el Portal de la empresa, donde se hospeda el contenido.
- Aplicaciones de vínculo profundo: vínculos a aplicaciones de Microsoft Store (o del Marketplace de Apple para las aplicaciones de iOS) que se almacenan en Configuration Manager, a los que los usuarios acceden a través del Portal de la empresa.

Las aplicaciones de vínculo profundo pueden reducir la sobrecarga administrativa redirigiendo a los usuarios a la Tienda Windows para buscar la versión más reciente, en lugar de tener que administrar y publicar las actualizaciones en el Portal de la empresa. El uso de Microsoft Store para implementar aplicaciones también puede originar algunas preguntas, como por ejemplo:

- ¿Se puede usar la infraestructura actual para implementar estas aplicaciones a través de la Tienda Windows?
- ¿Qué función desempeña la Tienda Windows en el proceso de implementación de aplicaciones?
- ¿Deben proceder todas las aplicaciones de la Tienda Windows?

Las respuestas variarán en función del estado actual de la estrategia de implementación de la compañía y de cómo se desarrollarán estas necesidades si elige usar la Tienda Windows. Tenga en cuenta que la Tienda Windows es un sistema de distribución digital y la plataforma de distribución principal de las aplicaciones actuales de Windows 10, Windows 8.1, Windows 8 y Windows RT. Sin embargo, se puede usar la Tienda Windows para enumerar aplicaciones de escritorio certificadas para que se ejecuten en dispositivos basados en Windows 8. Para obtener más información acerca de las aplicaciones transferidas localmente, consulte [Pruébelo: Carga de prueba de aplicaciones de la Tienda Windows](https://technet.microsoft.com/windows/jj874388.aspx).

## Implementación

Para tratar las consideraciones sobre las aplicaciones que se implementarán en los usuarios debe comprender los requisitos relativos al acceso a la empresa. Los escenarios de implementación incluyen las aplicaciones que siempre deben estar conectadas a los recursos de la empresa, aunque los usuarios no necesiten acceder a otros recursos corporativos o no necesiten acceso completo a todos los recursos corporativos mientras se encuentren dentro de la red corporativa. Compruebe las opciones de implementación de cada aplicación y determine qué método es el más adecuado para su empresa. En la siguiente sección, se incluyen las opciones de implementación más comunes que puede usar como punto de referencia para tomar una decisión.

### Opciones de implementación: ventajas y desventajas

Mediante la siguiente lista, podrá conocer las ventajas y desventajas de las opciones de implementación:

- Basado en una ubicación local
    - Ventajas
        - Todos los controles de seguridad se encuentran físicamente en el entorno local, de modo que el departamento de TI dispone de un control total.
        - El equipo de TI puede llevar a cabo la protección del servidor que tiene el rol de implementación.
        - Se proporcionan funciones de auditoría, registro e informes más pormenorizados.
    - Desventajas
        - El coste de mantenimiento es superior al de una solución en la nube.
        - Carece de la integración con los servicios en la nube.
        - Resulta difícil implementar aplicaciones en dispositivos no administrados.
        - Resulta complicado controlar las opciones de implementación en los dispositivos que no se encuentren en el entorno local.
- Basado en la nube
    - Ventajas
        - Las aplicaciones pueden instalarse desde cualquier lugar.
        - Existe la posibilidad de implementación de varias plataformas.
        - Resulta más sencillo implementar aplicaciones en dispositivos no administrados que con una solución local.
    - Desventajas
        - Las funciones de informes se encuentran limitadas para los dispositivos locales que usan aplicaciones.
        - Falta una administración y un control de la implementación centralizados.
- Híbrido (parte local y parte en la nube)
    - Ventajas
        - Más fácil de implementar aplicaciones en dispositivos no gestionados que una solución local.
        - TI aún tiene un control total sobre la parte local de la función de la implementación.
        - Integración entre dispositivos locales y dispositivos administrados en la nube en una sola ubicación.
        - Más fácil de controlar las opciones de implementación en varias plataformas que una solución local.
    - Desventajas
        - Normalmente requiere una suscripción a un servicio de nube.
        - La integración con la solución de implementación local puede variar según el servicio de nube.

### Requisitos de implementación de aplicaciones: consideraciones

También debe acceder a los requisitos de implementación de las aplicaciones para las soluciones de infraestructura BYOD. En la siguiente lista, se incluyen algunas consideraciones clave relativas a la implementación de aplicaciones:

- Permisos
    - Asegúrese de que el nivel de permisos que deben tener los usuarios para instalar aplicaciones no sea invasivo. Por ejemplo, no tiene que requerir que un usuario sea el administrador de un dispositivo para instalar aplicaciones.
    - Si una aplicación usa archivos o carpetas temporales, asegúrese de que no requiera permisos de nivel administrativo para administrar dichos objetos.
- Certificado
    - Si la implementación de aplicaciones requiere un certificado en los dispositivos de los usuarios, asegúrese de que los dispositivos puedan acceder a la lista de revocación de certificados (CRL) para validar la autenticidad del certificado.
    - Si se instala un certificado durante el proceso de instalación de la aplicación, asegúrese de que los usuarios son conscientes de ello y se les ha solicitado su consentimiento.
    - Defina qué certificado se usará. Si el certificado se ha emitido a través de una entidad de certificación interna (CA), asegúrese de que los dispositivos de los usuarios tienen instalado primero el certificado de CA y, a continuación, instale los certificados de las aplicaciones. Si el certificado se ha emitido a través de una CA pública de terceros, asegúrese de que el dispositivo pueda validar el certificado a través de Internet. Si se produce un error en la validación, asegúrese de que los usuarios sepan por qué se ha producido el error y evite la instalación por motivos de seguridad.
- Agente de administración de dispositivos móviles (MDM)
    - Si las aplicaciones requieren que se instale un agente MDM en los dispositivos de los usuarios antes de instalar las aplicaciones, asegúrese de que los usuarios son conscientes de ello y se les ha solicitado su consentimiento.
    - Si se debe instalar el agente MDM, asegúrese de que el proceso de instalación es fácil de seguir y de que usará los recursos mínimos del sistema.

Con System Center 2012 R2 Configuration Manager, el departamento de TI puede identificar y dar permiso a usuarios específicos mediante la función de detección de usuarios de Configuration Manager y, a continuación, agregarlos a una colección personalizada que sincronizará estas cuentas de usuario con Microsoft Intune. Esto también ayudará a la implementación de estas aplicaciones.
La actualización de las aplicaciones también debe incluirse en las consideraciones de la implementación de aplicaciones. Una vez instaladas las aplicaciones, se deben detectar automáticamente las actualizaciones de las aplicaciones y los usuarios deben recibir una notificación en la aplicación de la Tienda Windows. System Center 2012 R2 ofrece capacidades para que las empresas dispongan de su propia tienda de aplicaciones empresariales y permitan que los usuarios puedan instalar aplicaciones LOB desde esta tienda. Para obtener más información acerca de la tienda de aplicaciones de empresa, consulte el artículo en el que se trata un caso práctico de diseño de una aplicación de la Tienda Windows correspondiente a la línea de negocio empresarial.

Se pueden usar las [VPN desencadenadas automáticamente en Windows 10](http://blogs.technet.com/b/canitpro/archive/2016/01/26/step-by-step-enabling-apps-to-auto-trigger-vpns-in-windows-10.aspx) para permitir que las aplicaciones puedan acceder a los recursos corporativos. Esta característica permite a TI establecer una lista de aplicaciones predefinidas para conectarse automáticamente a las redes corporativas abriendo una conexión VPN al iniciarse la aplicación. Puede definir las aplicaciones que quiere que estén disponibles para el desencadenamiento automático y para restringir el acceso remoto en función de la identidad del usuario y la identidad del equipo desde el que el usuario accede al recurso. Para obtener más información sobre VPN desencadenadas automáticamente, consulte [Novedades de acceso remoto en Windows Server 2012 R2](https://technet.microsoft.com/library/dn383589.aspx).

Si su empresa va a adoptar Windows Phone y quiere que los usuarios puedan usar las aplicaciones LOB para esta plataforma, en primer lugar debe conocer el proceso de inscripción de la aplicación. Las empresas deben seguir algunos pasos para establecer una cuenta de empresa, inscribir dispositivos y distribuir aplicaciones en los dispositivos inscritos. Para obtener más información sobre la implementación de aplicaciones de Windows Phone, consulte [Company app distribution for Windows Phone](https://msdn.microsoft.com/library/windowsphone/develop/jj206943(v=vs.105).aspx) (Distribución de aplicaciones de empresa para Windows Phone).

## Almacenamiento y red

Las consideraciones de almacenamiento y de aplicaciones de red pueden afectar a los servidores y a los dispositivos de las aplicaciones. Surgirán las siguientes preguntas cuando se plantee estos dos componentes principales para las aplicaciones:

- ¿Almacenarán algo las aplicaciones en el almacenamiento de los usuarios?
    - Si es así, ¿cuáles son los requisitos de almacenamiento de las aplicaciones al almacenar información en los dispositivos de los usuarios? ¿Los datos se cifran a través de las aplicaciones o del sistema operativo?
- ¿Controlarán las aplicaciones información confidencial al transmitirse por la red cableada o inalámbrica?
    - Si es así, ¿se cifrarán los datos?

En la siguiente sección, se incluyen consideraciones clave sobre los requisitos de almacenamiento y red de las aplicaciones.

### Requisitos de almacenamiento y red de las aplicaciones: consideraciones

Mediante la siguiente lista, podrá conocer las ventajas y desventajas de los requisitos y consideraciones en cuanto a almacenamiento y red de las aplicaciones:

- Espacio en disco
    - Si el proceso de implementación de la aplicación necesita más espacio que el que necesita la aplicación (debido a los archivos temporales), asegúrese de que esté bien documentado, de que los usuarios sean conscientes de ello y de que se les ha solicitado su consentimiento.
    - Asegúrese de que se eliminen todos los archivos y carpetas temporales almacenados en los dispositivos de almacenamiento de los usuarios durante el proceso de implementación después de instalar una aplicación.
- Privacidad de los datos
    - Si una aplicación almacena información privada de la empresa o del usuario en el almacenamiento de dispositivos de los usuarios, asegúrese de que los usuarios son conscientes y se les ha solicitado el consentimiento.
        - Si la aplicación almacena información privada, asegúrese de que los archivos estén cifrados en los dispositivos de los usuarios.
    - Si las aplicaciones transfieren información privada de la empresa o de los usuarios a través de la red, asegúrese de que el proceso de transferencia esté cifrado.
- Copia de seguridad
    - Si las aplicaciones almacenan archivos temporales en el almacenamiento de dispositivos de los usuarios durante el funcionamiento normal para posteriormente remitirse a la base de datos del servidor, asegúrese de que exista un mecanismo de copia de seguridad para guardar los archivos en caso de que se bloqueen las aplicaciones, se desconecte el dispositivo y que se hayan efectuado las tareas preparatorias para cualquier otra circunstancia desconocida que podría dar lugar a la pérdida de datos.
    - Asegúrese de que los datos de la copia de seguridad también estén protegidos frente a los usuarios o procesos no autorizados.
    - Si la red de usuario pierde la conexión con el servidor de las aplicaciones, asegúrese de que las aplicaciones tienen un proceso de copia de seguridad para evitar la pérdida de datos.
- Infraestructura de back-end
    - Evalúe las necesidades para actualizar, expandir o virtualizar los servidores de almacenamiento back-end.
    - Asegúrese de que la infraestructura back-end tiene varias rutas de red para acceder a los dispositivos de los usuarios.
    - Asegúrese de que la innovadora solución local sea capaz de administrar varios ISP para evitar que los usuarios que provienen de la nube pierdan la conectividad con los servidores de aplicaciones locales.

Al considerar las aplicaciones que se usarán en su infraestructura BYOD, también puede aprovechar la Infraestructura de Escritorio Virtual (VDI) de Windows Server 2012 R2. Los usuarios pueden ejecutar remotamente las aplicaciones de Windows 8 como si se ejecutaran en su dispositivo local, como por ejemplo aplicaciones de clips de vídeo, películas, vídeos de streaming y aplicaciones intensivas gráficamente. La experiencia del usuario puede mejorar en Windows Server 2012 R2 con Microsoft RemoteFX. Windows Server 2012 R2 incluye mejoras relativas a los códecs y a la transmisión por secuencias de multimedia, y ofrece la mejor experiencia de usuario posible en diferentes condiciones de red, compensando la resolución de la experiencia con el ancho de banda disponible cuando sea necesario. Además, con la aplicación de escritorio remoto de Microsoft, los usuarios pueden conectarse a sus datos corporativos y a las aplicaciones desde una gran variedad de plataformas, como Windows, Windows RT, iOS, Mac OS X y Android.

Si tiene pensado usar VDI para permitir que los usuarios de BYOD puedan acceder a aplicaciones de empresa, primero debe conocer los tipos de implementaciones disponibles para VDI:

- Basado en máquina virtual: máquinas virtuales de Windows 8 que se ejecutan en una infraestructura de Hyper-V. En este caso, use los servicios de escritorio remoto para proporcionar a los usuarios conectividad remota a las máquinas virtuales. Puede usar el escenario de implementación basado en máquina virtual con colecciones de máquinas virtuales personales o agrupadas.
- Basado en sesión: los usuarios se conectan a los servicios de escritorio remoto (RDS) en Windows Server 2012 R2 y ejecutan sus aplicaciones en las sesiones de Windows Server 2012 R2. Solo se necesita RDS para este tipo de implementación.
Se ha mejorado la experiencia de almacenamiento de VDI en Windows Server 2012 R2 con niveles de almacenamiento y desduplicación de datos en línea. Esta funcionalidad permite a TI crear volúmenes de almacenamiento que optimizan automáticamente las ubicaciones de los datos en los discos y buscan los bloques de datos a los que se ha accedido con más frecuencia en los discos de mayor rendimiento. También puede aprovechar las siguientes funcionalidades de almacenamiento en Windows Server 2012 R2 para VDI:
- Varias opciones de almacenamiento: admite el almacenamiento conectado directamente, conectado a la red, en clúster o almacenamiento SAN de máquinas virtuales; usa la desduplicación de discos en línea para reducir considerablemente los requisitos de almacenamiento.
- Distribución equilibrada: distribuye dinámicamente el ancho de banda, la CPU y el uso de disco por otras máquinas virtuales y sesiones, garantizando que ninguna máquina virtual o sesión monopolice los recursos o disminuya la experiencia de otros usuarios en el sistema.


Para obtener más información sobre VDI en Windows Server 2012 R2, consulte [Novedades en los Servicios de Escritorio remoto de Windows Server 2012 R2](https://technet.microsoft.com/library/dn283323.aspx).

La decisión de elegir la implementación de aplicación y la experiencia que se usarán para el diseño de la infraestructura BYOD debe equilibrarse con el costo total de propiedad (TCO). Para comprender mejor el TCO de la adopción de VDI, se recomienda leer [VDI TCO Analysis for Office Worker Environments (Análisis del TCO de VDI para entornos de trabajo de Office)](http://www.intel.in/content/www/in/en/data-center-efficiency/data-center-efficiency-vdi-tco-analysis-for-office-worker-environments-report.html).

## Seguridad

Plantéese usar un ciclo de vida de desarrollo de seguridad para todas las aplicaciones que utilizarán los usuarios que usen sus propios dispositivos. La seguridad debe incluirse en todas las fases del proceso de desarrollo y deben tenerse en cuenta todas las amenazas potenciales. [STRIDE](https://msdn.microsoft.com/magazine/cc163519.aspx) y otras estrategias de seguridad se pueden incorporar al ciclo de vida de desarrollo mediante el [ciclo de vida de desarrollo de seguridad (SDL) de Microsoft](https://www.microsoft.com/security/sdl/process/requirements.aspx). Es un aspecto importante la manera en que se integrará la infraestructura actual con la estrategia de seguridad global para BYOD. ¿Es capaz de proporcionar el entorno actual una base segura para las aplicaciones? ¿Necesita adquirir la empresa soluciones seguras de terceros para mitigar cualquier vulnerabilidad potencial que cree esta nueva adopción?

Las consideraciones de seguridad son importantes para las aplicaciones que usarán los usuarios con sus propios dispositivos. Se recomienda que use colecciones personalizadas en función de los grupos de seguridad de Active Directory para limitar los usuarios de destino para algunas aplicaciones con requisitos de acceso específicos, limitando los usuarios que pueden instalarlas. También se puede aprovechar la seguridad para mejorar la experiencia de los usuarios permitiéndoles acceder a los recursos corporativos con el mismo nombre de usuario y contraseña, algo que se puede conseguir mediante AD FS. La seguridad también es importante al diseñar la implementación para estas aplicaciones. Debe adquirir e implementar certificados y claves de instalación de prueba para poder habilitar la inscripción del usuario. Trabaje conjuntamente con otros equipos para optimizar el proceso de certificación de aplicaciones.



<!--HONumber=Oct16_HO1-->


