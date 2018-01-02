---
title: Directivas recomendadas para proteger documentos - Microsoft 365 Enterprise | Microsoft Docs
description: Se explican las directivas recomendadas por Microsoft para proteger el acceso a archivos de SharePoint.
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: ba69fe607fef9cdf6065f6a5b586770b87c771a9
ms.sourcegitcommit: d8588b191a4f9daea73698426dd632e7997140dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2017
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Recomendaciones de directivas para la protección de sitios y archivos de SharePoint
Las siguientes recomendaciones *complementan* a las [recomendaciones comunes de directivas de acceso e identidad](identity-access-policies.md) y a las [recomendaciones de directivas para proteger el correo electrónico](secure-email-recommended-policies.md). Para proteger archivos de SharePoint Online se deben crear nuevas directivas y modificar las existentes, como se explica aquí.

Las siguientes recomendaciones se basan en tres niveles diferentes de seguridad y protección de archivos de SharePoint que se pueden aplicar en función de la granularidad de las necesidades: **base de referencia**, **confidencial** y **extremadamente regulado**. Puede aprender más sobre estos niveles de seguridad y los sistemas operativos de cliente recomendados, a los que hacen referencia estas recomendaciones, en la [introducción a las directivas y configuraciones de seguridad recomendadas](microsoft-365-policies-configurations.md).

>[!NOTE]
>Todos los grupos de seguridad creados como parte de estas recomendaciones deben crearse con las características de Office habilitadas. Esto es especialmente importante para la implementación de AIP al proteger documentos en SharePoint.
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
Para crear una nueva directiva de acceso condicional de Intune para SharePoint Online, inicie sesión en el [portal de administración de Microsoft](http://manage.microsoft.com) con las credenciales de administrador y luego vaya a **Directiva** > **Acceso condicional** > **Directiva de SharePoint Online**.

![Directiva de SharePoint Online](./media/secure-docs/sharepoint-online-policy.png)

Debe establecer una directiva de acceso condicional específicamente para SharePoint Online en el portal de administración de Intune para exigir un dispositivo compatible o unido a dominio.
| Category|Tipo|Propiedades|Valores|Notas|
|:-----|:-----|:-----|:-----|:-----|
|**Acceso a la aplicación**|OneDrive para la Empresa y otras aplicaciones que usan autenticación moderna|Todas las plataformas|True|Seleccionado|
|     |     |Windows debe cumplir el siguiente requisito|El dispositivo debe estar unido a dominio o ser compatible|Seleccionado (lista)|
|     |     |Plataformas específicas|False||
|     |Acceso del explorador a SharePoint y OneDrive para la Empresa |Bloquear dispositivos no compatibles en la misma plataforma que OneDrive para la Empresa|True|Check|
|**Implementación de directiva**|Grupos destinatarios|Seleccionar los grupos de seguridad de Active Directory a los que se dirige esta directiva|     |     |
|     |     |Todos los usuarios|False|     |
|     |     |Grupos de seguridad seleccionados|True|Seleccionado|
|     |     |Modificar|Seleccione un grupo de seguridad específico que contiene usuarios de destino.|     |
|     |Excluir grupos|Seleccione los grupos de Active Directory que se van a excluir de esta directiva (reemplaza a los miembros de la lista Grupos destinatarios).|     |     |    
|     |     |No hay usuarios exentos|True|Seleccionado|
|     |     |Grupos de seguridad seleccionados|False|     |

### <a name="mobile-application-management-conditional-access-for-sharepoint-online"></a>Acceso condicional para la administración de aplicaciones móviles para SharePoint Online

Debe establecer una directiva de acceso condicional específicamente para SharePoint Online en el portal de administración de Intune para administrar aplicaciones móviles.

Para administrar aplicaciones móviles, inicie sesión en Microsoft Azure Portal con las credenciales de administrador y luego vaya a **Intune App Protection** > **Configuración** > **Acceso condicional** > **SharePoint Online**.

| Category|Tipo|Propiedades|Valores|Notas|
|:-----|:-----|:-----|:-----|:-----|
|**Acceso de la aplicación**|Aplicaciones permitidas|Permitir el acceso de las aplicaciones|Permitir aplicaciones que admiten las directivas de aplicación de Intune|Seleccionado (lista): da como resultado una lista de combinaciones de aplicaciones o plataformas compatibles con las directivas de aplicación de Intune.|
|**Acceso de usuario**|     |Grupos de usuarios restringidos|Agregar usuarios o grupos: selección de un grupo de seguridad específico que contiene usuarios de destino.|Comience con el grupo de seguridad que incluye usuarios de prueba.|
|     |     |Grupos de usuarios exentos|Grupos de seguridad de excepción|     |

### <a name="apply-to"></a>Aplicar a

Una vez que se ha completado el proyecto de prueba, se deben aplicar estas directivas a todos los usuarios de la organización.

## <a name="sensitive"></a>Confidencial

### <a name="low-and-above-risk-requires-mfa"></a>El riesgo bajo y superior exige MFA

Realice los cambios siguientes en la directiva de control de acceso existente creada al aplicar las [recomendaciones de directivas para proteger el correo electrónico](secure-email-recommended-policies.md):

| Category|Tipo|Propiedades|Valores|Notas|
|:-----|:-----|:-----|:-----|:-----|
|Assignments|Aplicaciones en la nube|Incluir|Seleccionar aplicaciones:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|Seleccionar ambos|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir un dispositivo compatible o unido a dominio

(Vea las instrucciones de base de referencia)

### <a name="mobile-application-management-conditional-access-for-sharepoint-online"></a>Acceso condicional para la administración de aplicaciones móviles para SharePoint Online

(Vea las instrucciones de base de referencia)

## <a name="highly-regulated"></a>Extremadamente regulado

### <a name="mfa-required"></a>MFA obligatorio

Realice los cambios siguientes en la directiva de control de acceso existente creada al aplicar las [recomendaciones de directivas para proteger el correo electrónico](secure-email-recommended-policies.md):

| Category|Tipo|Propiedades|Valores|Notas|
|:-----|:-----|:-----|:-----|:-----|
|Assignments|Aplicaciones en la nube|Incluir|Seleccionar aplicaciones:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|Seleccionar ambos|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir un dispositivo compatible o unido a dominio
(Vea las instrucciones de base de referencia)

### <a name="mobile-application-management-conditional-access-for-sharepoint-online"></a>Acceso condicional para la administración de aplicaciones móviles para SharePoint Online
(Vea las instrucciones de base de referencia)

## <a name="additional-configurations"></a>Configuraciones adicionales
Además de las directivas anteriores, también debe bloquear protocolos heredados que no admitan la autenticación moderna.

### <a name="lock-down-legacy-protocols"></a>Bloquear protocolos heredados
Las directivas de acceso condicional protegen el acceso a través de flujos del explorador y aplicaciones que usan autenticación moderna, como Office 2016 y las aplicaciones de la lista de plataformas compatibles. En aplicaciones de escritorio de Office más antiguas, como Office 2010, la directiva de acceso condicional no se aplica.

Se pueden bloquear las aplicaciones más antiguas que no usan la autenticación moderna [mediante el portal de administración de OneDrive](https://support.office.com/article/Control-access-based-on-network-location-or-app-59b83701-cefd-4bf8-b4d1-d4659b60da08). El cmdlet de PowerShell de administración de SharePoint también puede usarse para deshabilitar protocolos heredados de SharePoint. Para usar PowerShell, simplemente ejecute el [cmdlet Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) y establezca **- LegacyAuthProtocolsEnabled** en **$false**.  Una vez establecido, se deshabilita la compatibilidad con el protocolo heredado y se bloquea el acceso a SharePoint con aplicaciones cliente más antiguas.

## <a name="next-steps"></a>Pasos siguientes
[Más información sobre servicios de Microsoft 365](index.md)
