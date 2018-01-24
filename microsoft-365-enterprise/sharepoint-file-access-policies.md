---
title: Directivas recomendadas para proteger documentos - Microsoft 365 Enterprise | Microsoft Docs
description: Se explican las directivas recomendadas por Microsoft para proteger el acceso a archivos de SharePoint.
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 01/18/2018
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 3eabab5a19c99fe97d56ed3d802c026c0b0bc6ef
ms.sourcegitcommit: eb3521981c5dec164ce2a14b4d4d53830b5ba461
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2018
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Recomendaciones de directivas para la protección de sitios y archivos de SharePoint
Las siguientes recomendaciones *complementan* a las [recomendaciones comunes de directivas de acceso e identidad](identity-access-policies.md) y a las [recomendaciones de directivas para proteger el correo electrónico](secure-email-recommended-policies.md). Para proteger archivos de SharePoint Online se deben crear nuevas directivas y modificar las existentes, como se explica aquí.

Las siguientes recomendaciones se basan en tres capas diferentes de seguridad y protección para el correo electrónico que se pueden aplicar en función de la granularidad de sus necesidades:

- **Base de referencia**: Microsoft recomienda establecer un estándar mínimo para proteger los datos, así como las identidades y los dispositivos que acceden a los datos. Microsoft proporciona una protección segura de forma predeterminada que satisface las necesidades de la mayoría de las organizaciones. Algunas organizaciones requieren más funcionalidades para satisfacer los requisitos de su base de referencia.
- **Confidencial**: algunos clientes tienen un subconjunto de datos que deben disponer de mayor protección. Puede aplicar una mayor protección a conjuntos concretos en su entorno de Office 365. Microsoft recomienda proteger las identidades y los dispositivos que acceden a información confidencial con niveles de seguridad comparables. 
- **Extremadamente regulado**: algunas organizaciones pueden tener una cantidad muy pequeña de datos extremadamente clasificados, un secreto comercial o datos regulados. Microsoft proporciona capacidades para ayudar a las organizaciones a cumplir estos requisitos, incluida protección adicional para identidades y dispositivos.

Consulte el tema de [introducción a las directivas y configuraciones de seguridad recomendadas](microsoft-365-policies-configurations.md) para ver más detalles.

> [!IMPORTANT]
> Todos los grupos de seguridad creados como parte de estas recomendaciones deben crearse con las características de Office habilitadas. Esto es especialmente importante para la implementación de Azure Information Protection (AIP) al proteger documentos en SharePoint Online.
>
>![Características de Office habilitadas para grupos de seguridad](./media/security-group.png)
>

## <a name="baseline"></a>Línea de base

### <a name="medium-and-above-risk-requires-mfa"></a>El riesgo medio y superior exige MFA
Realice los cambios siguientes en la directiva de control de acceso existente creada al aplicar las [recomendaciones de directivas para proteger el correo electrónico](secure-email-recommended-policies.md):

| Category|Tipo|Propiedades|Valores|Notas|
|:-----|:-----|:-----|:-----|:-----|
|Assignments|Aplicaciones en la nube|Incluir|Seleccionar aplicaciones:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|Seleccionar ambos|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir un dispositivo compatible o unido a dominio

Para crear una directiva de acceso condicional para Exchange Online, haga lo siguiente:

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales. Después de iniciar sesión, verá el Panel de Azure.

2. En el menú de la izquierda, seleccione **Azure Active Directory**.

3. En la sección **Seguridad**, seleccione **Acceso condicional**.

4. Pulse **Nueva directiva**.

5. Escriba un nombre de directiva y seleccione los **Usuarios y grupos** a los que quiera que se aplique la directiva.

6. Seleccione **Aplicaciones en la nube**.

7. Elija **Seleccionar aplicaciones** y **Office 365 SharePoint Online** en la lista **Aplicaciones en la nube**. Después, haga clic en **Seleccionar**. Una vez que haya seleccionado la aplicación **Office 365 SharePoint Online**, haga clic en **Listo**.

8. Pulse **Conceder** en la sección **Controles de acceso**.

9. Seleccione **Conceder acceso**, seleccione **Requerir que el dispositivo esté marcado como compatible** y **Requerir dispositivo unido al dominio (Azure AD híbrido)** y, finalmente, haga clic en **Seleccionar**.

10. Haga clic en **Crear** para crear la directiva de acceso condicional de Exchange Online.

    > [!NOTE]
    > A partir de Intune en Azure, tiene que crear todas las directivas de acceso condicional en la carga de trabajo de Azure Active Directory. Intune proporciona un vínculo a la carga de trabajo de directivas de acceso condicional de Azure AD desde el portal para que sea más cómodo.

    > [!IMPORTANT]
    > Si necesita asistencia para migrar directivas de acceso condicional creadas anteriormente en el portal clásico de Intune a Intune en Azure Portal, vea el tema [Reasignar directivas de acceso condicional desde el Portal de Intune clásico a Azure Portal](https://docs.microsoft.com/intune/conditional-access-intune-reassign). 

### <a name="app-based-conditional-access-for-sharepoint-online"></a>Acceso condicional basado en la aplicación para SharePoint Online

Puede agregar una capa de seguridad adicional mediante el establecimiento de una directiva de acceso condicional basada en la aplicación para SharePoint Online en Intune en Azure Portal. Al aplicar un acceso condicional basado en la aplicación para SharePoint Online, requiere que los usuarios usen solo esta aplicación para acceder a recursos corporativos.

Para agregar una directiva de acceso condicional basado en la aplicación, siga estos pasos:

1. Vaya a [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales de Intune. Después de iniciar sesión, verá el Panel de Azure.

2. Seleccione **Más servicios** en el menú izquierdo y, luego, escriba **Intune**.

3. Elija **Protección de aplicaciones de Intune**.

4. En la hoja **Administración de aplicaciones móviles de Intune**, elija **Toda la configuración**.

5. Seleccione **Exchange Online** en la sección **Acceso condicional**.

6. Seleccione **Permitir aplicaciones que admiten las directivas de aplicación de Intune** y seleccione la aplicación (p. ej., Microsoft Outlook).

7. Seleccione **Grupos de usuarios restringidos**, **Seleccionar grupos**, elija el usuario o grupo al que quiera aplicar la directiva y haga clic en **Seleccionar**.

## <a name="sensitive"></a>Confidencial

### <a name="low-and-above-risk-requires-mfa"></a>El riesgo bajo y superior exige MFA

Realice los cambios siguientes en la directiva de control de acceso existente creada al aplicar las [recomendaciones de directivas para proteger el correo electrónico](secure-email-recommended-policies.md):

| Category|Tipo|Propiedades|Valores|Notas|
|:-----|:-----|:-----|:-----|:-----|
|Assignments|Aplicaciones en la nube|Incluir|Seleccionar aplicaciones:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|Seleccionar ambos|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir un dispositivo compatible o unido a dominio

(Vea las instrucciones de base de referencia)

### <a name="app-based-conditional-access-for-sharepoint-online"></a>Acceso condicional basado en la aplicación para SharePoint Online

(Vea las instrucciones de base de referencia)

## <a name="highly-regulated"></a>Extremadamente regulado

### <a name="mfa-required"></a>MFA obligatorio

Realice los cambios siguientes en la directiva de control de acceso existente creada al aplicar las [recomendaciones de directivas para proteger el correo electrónico](secure-email-recommended-policies.md):

| Category|Tipo|Propiedades|Valores|Notas|
|:-----|:-----|:-----|:-----|:-----|
|Assignments|Aplicaciones en la nube|Incluir|Seleccionar aplicaciones:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|Seleccionar ambos|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir un dispositivo compatible o unido a dominio
(Vea las instrucciones de base de referencia)

### <a name="app-based-conditional-access-for-sharepoint-online"></a>Acceso condicional basado en la aplicación para SharePoint Online
(Vea las instrucciones de base de referencia)

## <a name="additional-configurations"></a>Configuraciones adicionales
Además de las directivas anteriores, también debe bloquear protocolos heredados que no admitan la autenticación moderna.

### <a name="lock-down-legacy-protocols"></a>Bloquear protocolos heredados
Las directivas de acceso condicional protegen el acceso a través de flujos del explorador y aplicaciones que usan autenticación moderna, como Office 2016 y las aplicaciones de la lista de plataformas compatibles. En aplicaciones de escritorio de Office más antiguas, como Office 2010, la directiva de acceso condicional no se aplica.

Se pueden bloquear las aplicaciones más antiguas que no usan la autenticación moderna [mediante el portal de administración de OneDrive](https://support.office.com/article/Control-access-based-on-network-location-or-app-59b83701-cefd-4bf8-b4d1-d4659b60da08). El cmdlet de PowerShell de administración de SharePoint también puede usarse para deshabilitar protocolos heredados de SharePoint. Para usar PowerShell, simplemente ejecute el [cmdlet Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) y establezca **- LegacyAuthProtocolsEnabled** en **$false**.  Una vez establecido, se deshabilita la compatibilidad con el protocolo heredado y se bloquea el acceso a SharePoint con aplicaciones cliente más antiguas.

## <a name="next-steps"></a>Pasos siguientes
[Más información sobre servicios de Microsoft 365](index.md)
