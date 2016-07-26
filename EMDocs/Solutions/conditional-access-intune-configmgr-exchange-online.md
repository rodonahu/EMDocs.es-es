---
title: Uso del acceso condicional con Exchange Online, Microsoft Intune y Configuration Manager
description: "Use Configuration Manager, Exchange Online e Intune para administrar el acceso al correo electrónico y proteger los datos del correo electrónico en dispositivos móviles."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 06921361-9475-46e6-9368-3cc44c84b22f
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7c389de59d0ca6b33fbd4d872cb77236930d55bf
ms.openlocfilehash: e87f189128279a2f12da202dd0b9022a967fc5c2


---

# Implementación de Exchange Online con Microsoft Intune y Configuration Manager
Ahora que ha leído la [Guía de arquitectura para proteger los documentos y correos electrónicos de la empresa](architecture-guidance-for-protecting-company-email-and-documents.md), ya puede continuar con la implementación de una solución.

Si ya usa System Center Configuration Manager y Exchange Online, puede incorporar Intune para administrar el acceso al correo electrónico y proteger los datos de correo electrónico en dispositivos móviles. El proceso de alto nivel para implementar esta solución es la siguiente:

-   Cree las directivas de cumplimiento que definen las reglas y los valores de configuración que un dispositivo debe cumplir para que se considere conforme a las directivas de acceso condicional.

-   Para empezar, aplique el acceso condicional.

-   Opcionalmente, configure el conector de Exchange Server para Exchange Online. Este conector solo se necesita con fines informativos. No es necesario para habilitar el acceso condicional.

## Flujo de control de acceso condicional para Exchange Online
Este diagrama muestra el flujo de control para los clientes que intentan obtener acceso al correo electrónico en Exchange Online. A y B pueden realizarse antes de aplicar el acceso condicional.

![Diagrama de flujo del control de acceso condicional en Configuration Manager con Intune y Exchange Online](./media/ProtectEmail/Hybrid-Exchange-Online-CA-architecture.png)

-   Microsoft Intune: administra las directivas de acceso condicional y de cumplimiento para el dispositivo

-   Microsoft Azure Active Directory: autentica al usuario y ofrece el estado de cumplimiento del dispositivo

-   Configuration Manager: administra la inscripción de dispositivos y ofrece informes, si se habilita esa opción

-   Exchange Online: aplica el acceso al correo electrónico según el estado del dispositivo

## Antes de comenzar
Asegúrese de que su entorno incluya estos requisitos para implementar esta solución.

-   Instale y asigne los servicios de Exchange en un [certificado digital válido ](https://technet.microsoft.com/library/dd351044.aspx) adquirido en una entidad de certificación pública de confianza.

-   Compruebe que está ejecutando System Center 2012 R2 Configuration Manager SP1 con actualización acumulativa 1 o posterior.

-   Configure una cuenta (administrador local o de dominio) con permisos para ejecutar los siguientes cmdlets de Exchange Server:

    Clear-ActiveSyncDevice

    Get-ActiveSyncDevice

    Get-ActiveSyncDeviceAccessRule

    Get-ActiveSyncDeviceStatistics

    Get-ActiveSyncMailboxPolicy

    Get-ActiveSyncOrganizationSettings

    Get-ExchangeServer

    Get-Recipient

    Set-ADServerSettings

    Set-ActiveSyncDeviceAccessRule

    Set-ActiveSyncMailboxPolicy

    Set-CASMailbox

    New-ActiveSyncDeviceAccessRule

    New-ActiveSyncMailboxPolicy

    Remove-ActiveSyncDevice

## Pasos de implementación
Siga estos pasos para implementar la solución Exchange Online:

### Paso 1: cree directivas de cumplimiento e impleméntelas a los usuarios.
Las directivas de cumplimiento definen las reglas y los valores de configuración que un dispositivo debe cumplir para que se le considere conforme a las directivas de acceso condicional. Siga los pasos de [Directivas de cumplimiento en Configuration Manager](https://technet.microsoft.com/en-us/library/mt131417.aspx) para crear directivas de cumplimiento.

Si quiere tener la capacidad de quitar todos los mensajes de correo corporativo de un dispositivo iOS cuando este deje de formar parte de la empresa, tiene que crear e implementar un perfil de correo electrónico. Luego, establezca una directiva de cumplimiento que especifique que Intune administra los perfiles de correo electrónico. Debe implementar el perfil de correo electrónico en el mismo conjunto de usuarios al que va dirigido esta directiva de cumplimiento.

![Captura de pantalla que muestra la página "Reglas" del Asistente para crear directivas de cumplimiento, donde puede especificar que un perfil de correo electrónico debe administrarse mediante Intune](./media/ProtectEmail/Hybrid-Onprem-ExchSrvr-Wizard6.PNG)

Si se especifica esta directiva de cumplimiento, un usuario que ya haya configurado su cuenta de correo electrónico tendrá que eliminarla manualmente y, luego, Intune la agregará de nuevo en el proceso de registro descrito en [Experiencia de acceso condicional del usuario final](end-user-experience-conditional-access.md).

Después de crear la directiva de cumplimiento, seleccione el nombre de dicha directiva en la lista y haga clic en **Implementar**.

### Paso 2: configure la directiva de acceso condicional.
En primer lugar, decida cómo y cuándo desea aplicar el acceso condicional y los empleados que se verán afectados. Luego, siga los pasos descritos en [Acceso condicional para correo electrónico de Exchange en Configuration Manager](https://technet.microsoft.com/en-us/library/mt131421.aspx) para habilitar la directiva de acceso condicional para Exchange Online.

> [!NOTE]
> Debe configurar la directiva de acceso condicional en la consola de Intune. Los siguientes pasos empiezan por el acceso a la consola de Intune a través de Configuration Manager. Si se le solicita, inicie sesión con las mismas credenciales que usó para configurar el conector entre Configuration Manager e Intune.

### Paso 3: (*Opcional*) instale y configure un conector de Exchange Server.
Configuration Manager solo admite un conector en una organización de Exchange.

> [!IMPORTANT]
> Antes de instalar el conector de Exchange Server, confirme que Configuration Manager es compatible con la versión de Microsoft Exchange que está usando. Para más información, vea [Configuraciones compatibles en Configuration Manager](https://technet.microsoft.com/en-us/library/gg682077.aspx).

Siga los pasos de [Cómo administrar dispositivos móviles con Configuration Manager y Exchange](https://technet.microsoft.com/en-us/library/gg682001.aspx) para instalar y configurar el conector de Exchange Server.

## Pasos de comprobación
Si ha configurado el conector opcional de Exchange Server para esta solución, puede usar la herramienta de registro de seguimiento de Configuration Manager para abrir el archivo EasDisc.log (que se encuentra en la carpeta Microsoft Configuration Manager/Logs donde se ha instalado Configuration Manager). Busque el archivo de registro del "Conector de Exchange" para obtener información sobre si se está ejecutando el conector de Exchange y cuántos dispositivos están conectados.

![Captura de pantalla que muestra el archivo EasDisc.log abierto en la herramienta de registro de seguimiento de Configuration Manager](./media/ProtectEmail/Hybrid-Onprem-Eas-DiscLog-Sample.PNG)

La herramienta de registro de seguimiento de Configuration Manager se incluye en el [kit de herramientas de System Center 2012 R2 Configuration Manager](https://www.microsoft.com/en-us/download/details.aspx?id=50012).

## Generación de informes
Si ha configurado el conector opcional de Exchange Server, puede usar la consola de Configuration Manager para ver información específica sobre los dispositivos detectados por el conector de Exchange. Para los dispositivos a los que se aplica el acceso condicional, puede ver el estado actual de cada dispositivo, la última conexión del dispositivo con el servidor de Exchange, etc.

En la consola de Configuration Manager, haga clic en **Activos y compatibilidad** y en **Dispositivos**. Puede ver el estado actual de cada dispositivo (En cuarentena o permitido) en la columna **Estado de acceso de Exchange** . Agregue esta columna si aún no aparece al hacer clic con el botón secundario en el área de la barra de título de la columna. También puede ver la hora de la última sincronización correcta para cada dispositivo, indicada por Exchange, agregando la columna **Hora de última sincronización correcta con Exchange Server** .

![Captura de pantalla muestra una lista de dispositivos en la consola de Configuration Manager](./media/ProtectEmail/Hybrid-Onprem-Verify-Devices-State.png)

Si está ejecutando SQL Server Reporting Services (SSRS), puede ver un informe de acceso condicional que muestre el estado de cumplimiento de los dispositivos, si hay un conector de Exchange instalado y activo, y el estado de acceso de EAS. También ofrecerá información sobre el registro de Active Directory, la activación de EAS y el propietario del dispositivo.

![Captura de pantalla muestra un ejemplo de un informe de SQL Server Reporting Services](./media/ProtectEmail/Hybrid-Reports-CA.png)

Para ver los informes de SSRS, debe tener un rol de informes instalado en el servidor principal:

1.  En Configuration Manager, haga clic en **Administración &gt; Configuración de jerarquía &gt; Configuración del sitio &gt; Servidores y roles del sistema de sitios**.

2.  Seleccione un servidor y haga clic en **Agregar rol de sistema de sitio** para abrir el asistente Agregar rol de sistema de sitio.

3.  En la página Selección de rol de sistema, active la casilla **Punto de servicios de informes** . El punto de servicios de informes muestra los informes relacionados con la administración de cliente.

4.  Haga clic en **Siguiente**.

A continuación, se muestra el estado de implementación de la directiva de configuración:

![Captura de pantalla que muestra el estado de implementación de la directiva de configuración](./media/ProtectEmail/Hybrid-Reports-Deployment-Status.png)

### Latencia
A los dispositivos que usan la autenticación moderna se les aplica de inmediato el acceso condicional. Para dispositivos que se conectan a través del protocolo EAS, puede haber un intervalo de tiempo de seis horas antes de que se aplique el acceso condicional, según la configuración predeterminada. Durante ese tiempo, un dispositivo podría considerarse conforme.

## Próximos pasos
Cuando haya implementado una solución para proteger el correo electrónico corporativo y los datos de correo electrónico de los dispositivos móviles, puede obtener más información sobre la [experiencia de acceso condicional del usuario final](end-user-experience-conditional-access.md). Esto le ayudará a prepararse para problemas que podrían surgir al inscribir sus dispositivos específicos.



<!--HONumber=Jul16_HO3-->


