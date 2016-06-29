---
# required metadata

title: Implementación de una solución para proteger los documentos y correos electrónicos de su empresa
description:
keywords:
author: karthikaraman
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: edc744d8-97d9-42e0-8906-6f0dedd8d629

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Implementación de una solución para proteger los datos adjuntos y correos electrónicos
Este artículo le ayuda a preparar el proceso y, después, implementar una solución para proteger los datos adjuntos y el contenido de correo electrónico de la empresa.

## ¿Qué debe considerar al planear la implementación?

-   **Compatibilidad con las plataformas de los dispositivos**: debe tener en cuenta si desea permitir el acceso al correo electrónico a aquellas plataformas que no son compatibles con Intune. La administración de dispositivos móviles de Intune admite los siguientes sistemas operativos:

    -   Apple iOS 7.1 y versiones posteriores (los dispositivos iOS 6.0 y 7.0 inscritos previamente permanecen inscritos, pero no se pueden inscribir nuevos dispositivos)

    -   Google Android 2.3.4 y versiones posteriores (incluye Samsung KNOX)

    -   Windows Phone 8.0 y versiones posteriores

    -   Windows RT y versiones posteriores

    -   Equipos de Windows 8.1 y versiones posteriores

-   **Tipos de aplicaciones de correo electrónico**: la solución de EMS admite actualmente clientes que usan el protocolo EAS y aplicaciones de Outlook (anteriormente, Accompli en iOS y Android).

-   **Directivas**: la solución de EMS y sus componentes tienen varias directivas que se usan para administrar la seguridad y el acceso. Determine qué directivas debe configurar el Administrador de TI. Las tres directivas clave que se usarán para la investigación y planificación al proteger el acceso al correo electrónico y los datos de correo electrónico son:

    -   **Directivas de cumplimiento del dispositivo**: determine qué significa “cumplimiento” para su empresa. Intune incluye varias reglas que puede establecer, pero todas esas reglas pueden o no aplicarse a la empresa. Puede cambiar las directivas en cualquier momento, pero se recomienda
        determinar un conjunto básico de directivas para su empresa. Las directivas de cumplimiento van dirigidas a grupos de dispositivos y de usuarios de Intune.

    -   **Directivas de acceso condicional**: las directivas de acceso condicional están dirigidas a grupos de seguridad de Azure AD. Determine a qué usuarios se dirigirán las directivas y si hay usuarios que deben estar exentos. El acceso condicional es compatible con la solución basada en la nube y la implementación híbrida.

    -   **Administración de aplicaciones móviles**: determine qué aplicaciones deben administrarse y qué directivas MAM se deben aplicar a estas aplicaciones.

-   **Consideraciones sobre la administración de dispositivos**: seleccione la opción de administración de dispositivos que mejor satisfaga las necesidades de la empresa antes de implementar la solución. Hay dos opciones:

    -   Unificar System Center Configuration Manager con Microsoft Intune para administrar todos los dispositivos a través de una única consola. Esto se denomina *Implementación híbrida*. Ventajas de este enfoque:

        -   Una única consola de administración con controles de administración de derechos enriquecidos para administrar equipos locales y dispositivos móviles

        -   Amplias funciones de implementación y orientación

        -   Gran escala para grandes empresas

    -   Administre los dispositivos móviles a través de Microsoft Intune independientemente de los dispositivos locales con System Center Configuration Manager. Esto se denomina "*Implementación independiente de Intune*". Ventajas de este enfoque:

        -   Consola basada en web sencilla diseñada específicamente para la administración de dispositivos móviles

        -   Acceso rápido a las características más recientes

    Aunque la migración siempre es posible, es muy recomendable tomar esta decisión antes de la implementación, puesto que influirá en muchas de las decisiones del proceso de aplicación.

-   **Entorno de Exchange**:

    -   La implementación de los conectores de Exchange y cómo se conectan cuando se implementan los equilibradores de carga de red.

    -   Exchange Online: ¿es multiempresa o dedicado? Si es dedicado, averigüe en qué arquitectura se basa el inquilino. Esto determinará si se puede utilizar el acceso condicional basado en Azure AD o si se necesita un conector local.

-   **Sincronización de Azure AD y Servicios federados de Active Directory (AD FS), o bien otro servicio federado de terceros**:

    -   El acceso condicional está diseñado para funcionar para los clientes que tengan federado su servicio de identidad con ADFS. Generalmente, todavía se aplicarán las reglas de acceso de cliente, sin embargo, se recomienda que se realice una prueba completa. Los requisitos para la sincronización de directorios y ADFS no son diferentes de los de Office 365.

    -   Los servicios de federación de terceros, como Ping, también deberían funcionar. Se recomienda realizar pruebas antes de la implementación.

## Implementación local
Si tiene una implementación existente de System Center Configuration Manager, Active Directory o Exchange Server, puede ampliar la infraestructura existente mediante la integración con Intune, Azure AD y Office 365. Con esta implementación híbrida, puede proporcionar una experiencia de administración coherente entre dispositivos locales y en la nube. Intune y el Administrador de configuración ofrecen un conjunto similar de funciones para permitir el acceso restringido al correo electrónico en función del estado del dispositivo.

Para implementaciones de Exchange Online dedicadas, si puede aprovechar la solución en la nube descrita anteriormente o la implementación híbrida depende del aspecto de la implementación actual. Hable con su equipo de cuentas para determinar qué implicará la implementación.

## Operaciones y respuesta a incidencias
Una vez implementada la solución, debe administrar el entorno e identificar posibles riesgos de seguridad. Intune y Azure AD tienen funciones de supervisión y notificación que pueden ayudar a supervisar y responder rápidamente en caso de incidentes de seguridad.

Estas son algunas de las funciones de notificación:

-   Las alertas e informes de Intune le ayudarán a supervisar el estado de los dispositivos que administra Intune.

-   Azure AD tiene registros de actividades y auditoría. Puede supervisar elementos tales como cambios de contraseña y administración de usuarios. Azure Active Directory premium incluye alertas e informes de seguridad de anomalías avanzados. Estas alertas se basan en informes de aprendizaje automático detallados que muestran la actividad de inicio de sesión, los patrones de acceso incoherentes y las áreas de amenazas potenciales.

## Próximos pasos
Para obtener instrucciones detalladas sobre cómo implementar una solución para proteger los datos adjuntos y el contenido de correo electrónico de la empresa, consulte uno de estos temas, en función de su entorno:

- [Uso del acceso condicional con Microsoft Intune](conditional-access-intune.md)
- [Uso del acceso condicional con Microsoft Intune y Configuration Manager](conditional-access-intune-configmgr.md)


<!--HONumber=Apr16_HO4-->


