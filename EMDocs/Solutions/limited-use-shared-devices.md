---
title: "Habilitar una solución de dispositivos compartidos de uso limitado | Microsoft Docs"
description: 
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 6/7/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d78e2b94-8ad3-4703-b7f0-db070288a20b
ms.reviewer: vlpetros
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: d4362764cad9264c513ca745c45b96590b18928f
ms.openlocfilehash: 98efafde6981fa8cb0c49c4b22729c64c8386754
ms.contentlocale: es-es
ms.lasthandoff: 03/24/2017


---
# <a name="enable-a-limited-use-shared-device-solution-with-intune"></a>Habilitar una solución de dispositivos compartidos de uso limitado con Intune
A veces, los empleados necesitan compartir dispositivos para acceder a aplicaciones y datos de la empresa con el fin de completar el trabajo de tarea básica en el que solo se requieren opciones de configuración y aplicaciones específicas. Esto suele suceder en los sectores de comercio al por menor, fabricación y transporte. Otras veces, no son los empleados, sino los clientes quienes necesitan acceder interactivamente a recursos mediante dispositivos de acceso público en ubicaciones tales como conferencias, hoteles, escuelas o bibliotecas. En algún caso, puede que solo tenga que mostrar una presentación autoejecutable u ofrecer información estática a transeúntes.

Puede realizar una ejecución de pantalla completa de aplicación sin ninguna otra opción para ofrecer una experiencia interactiva y segura de usuario de pantalla completa al tiempo que protege los activos de su empresa de actividades de usuario sospechosas. Esta posibilidad permite al equipo de TI ofrecer mayor seguridad junto con una experiencia personalizable que mantenga productivos a los empleados y satisfaga las necesidades del cliente.

## <a name="how-can-enterprise-mobility--security-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security?
EMS le permite ofrecer capacidades y experiencias que creen un área de trabajo productivo y satisfaga las necesidades de los clientes en cualquier lugar. Tanto si se usan dispositivos iOS, Mac OS, Android como Windows Mobile propiedad de la empresa, Microsoft Intune puede ayudarle a ofrecer productividad a su personal al tiempo que se protegen los datos de la empresa.

### <a name="recommended-solution"></a>Solución recomendada
Con Intune, puede aprovechar las opciones de configuración de la directiva de configuración de pantalla completa para dispositivos móviles iOS o Android y el acceso asignado para teléfonos móviles de Windows con el fin de bloquear un dispositivo de manera tal que solo determinadas aplicaciones o características funcionen. Las directivas de configuración de Microsoft Intune son grupos de opciones de configuración que controlan características en equipos y dispositivos móviles. Las directivas se crean con plantillas que contienen configuraciones recomendadas o personalizadas, y se implementan en grupos de dispositivos o usuarios. Por ejemplo, puede implementar directivas de configuración de pantalla completa en dispositivos que les permitan ejecutar solo una aplicación administrada que se especifique o puede deshabilitar los botones de volumen de un dispositivo. Esta configuración podría usarse para un modelo de demostración de un dispositivo o para un dispositivo que está dedicado a realizar solo una función, como un dispositivo de punto de venta.

### <a name="how-to-implement-this-solution"></a>Cómo implementar esta solución
El resto de esta solución se divide en las secciones siguientes, que muestran cómo configurar:
- **Pantalla completa para iOS**. En esta sección se muestra cómo bloquear dispositivos iOS mediante opciones de configuración de directivas de configuración de pantalla completa de Intune.
- **Pantalla completa para Android**. En esta sección se muestra cómo bloquear dispositivos Android mediante opciones de configuración de directivas de configuración de pantalla completa de Intune para dispositivos Samsung KNOX.
- **Directivas de acceso asignado para Windows**. En esta sección se describe cómo se usa el proveedor del servicio de configuración (CSP) EnterpriseAssignedAccess para bloquear dispositivos Windows 10 Mobile a fin de ofrecer una experiencia de acceso asignado.

## <a name="kiosk-mode-for-ios"></a>Pantalla completa para iOS
Intune proporciona una gama de opciones de configuración general integradas que pueden configurarse en dispositivos iOS, entre las que se incluyen opciones de configuración de pantalla completa que le permiten bloquear dispositivos iOS administrados.  

Para poder configurar un dispositivo iOS (8.0 y versiones posteriores) en pantalla completa, debe usar primero la herramienta [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) en un dispositivo Mac o implementar un perfil de inscripción para [inscribir dispositivos iOS que se compren a través del Programa de inscripción de dispositivos Apple (DEP)](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) para poner el dispositivo en modo supervisado. Una vez hecho esto, puede implementar opciones de configuración de pantalla completa para controlar la configuración de aplicación y dispositivo mediante una directiva de configuración de Intune.

En la consola de administrador de Intune, simplemente desplácese hasta el nodo de directiva de la consola de administración de Intune y luego, en iOS, cree otra directiva de **configuración general de iOS (iOS 8.0 y versiones posteriores)** y defina la configuración de pantalla completa. Lo más importante de esta configuración es definir la aplicación administrada que se permitirá ejecutar cuando el dispositivo se coloque en pantalla completa.

![Opciones de configuración de la directiva de pantalla completa de iOS](..\Solutions\media\limited-use-devices\kiosk-mode-policy.png)

Puede especificar una aplicación administrada o una aplicación de App Store de Apple, pero no se podrá ejecutar ninguna otra aplicación en el dispositivo una vez aplicada la directiva de pantalla completa. Recuerde también que cuando se implemente, la directiva solo tendrá efecto en dispositivos iOS en modo supervisado.

> [!NOTE]
> Si la aplicación que especifique se instala después de implementar la directiva de configuración, el dispositivo no pasará a pantalla completa hasta que se reinicie.

## <a name="kiosk-mode-for-android"></a>Pantalla completa para Android
El bloqueo de dispositivos Android KNOX Standard (4.0 y versiones posteriores) es similar a poner dispositivos iOS en pantalla completa. En la consola de administrador de Intune, simplemente desplácese hasta el nodo de directiva de la consola de administración de Intune y luego, en Android, cree otra directiva de **configuración general (Android 4 y versiones posteriores, Samsung KNOX Standard 4.0 y versiones posteriores)** y defina la configuración de pantalla completa.

Hay menos opciones disponibles que configurar con dispositivos Android KNOX, pero la más importante sigue siendo la aplicación administrada que se permitirá ejecutar mientras se esté en pantalla completa. Las aplicaciones de la tienda no son compatibles con estos dispositivos y la directiva que implemente se ejecutará en cualquier dispositivo Samsung KNOX en el que se reciba, incluidos los dispositivos personales BYOD si no tiene cuidado. Por ello, solo debe implementar la configuración de pantalla completa en dispositivos Android para la persona que administra la inscripción masiva de los dispositivos de propiedad corporativa que haya que administrar como dispositivos de pantalla completa.

> [!NOTE]
> Si la aplicación que especifique se instala después de implementar la directiva de configuración, el dispositivo no pasará a pantalla completa hasta que se reinicie.

## <a name="assigned-access-policies-for-windows"></a>Directivas de acceso asignado para Windows
Los dispositivos Windows 10 Mobile (versión 1511 y versiones posteriores) también se pueden configurar como dispositivos de pantalla completa, pero en lugar de una directiva de configuración general, se usa una directiva de configuración personalizada de Windows. Estos tipos de directivas le permiten aprovechar la [configuración OMA-URI de Windows 10](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) para administrar opciones de configuración de dispositivos con Intune.

> [!TIP]
> Los [proveedores de servicios de configuración (CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) exponen las opciones de configuración de dispositivos OMR-URI de Windows 10.

El [CSP EnterpriseAssignedAccess](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/enterpriseassignedaccess-csp) se usa para bloquear dispositivos Windows 10 a fin de ofrecer una experiencia de acceso asignado. También se puede usar ese CSP para configurar otras opciones, como idioma y temas, o configurar diseños personalizados en un dispositivo.

Si desea crear la directiva para dispositivos Windows, tiene que ir al nodo de directiva de la consola de administración de Intune y luego, en Windows, crear una directiva **Configuración personalizada (Windows 10 Escritorio y Windows 10 Mobile, y versiones posteriores)**. A partir de entonces, tendrá que proporcionar la información de CSP e importar un archivo XML válido que defina la configuración que se va a aplicar a los dispositivos Windows a los que se destina la implementación de esta directiva.  

![Configuración de OMA-URI](..\Solutions\media\limited-use-devices\settings.png)

Para crear una directiva de acceso sencilla, especifique los metadatos básicos de nombre y descripción, establezca el tipo de datos en **Cadena (XML)** y escriba **./Vendor/MSFT/EnterpriseAssignedAccess/AssignedAccess/AssignedAccessXml** para el valor OMA-URI *con distinción de mayúsculas y minúsculas*. En el ejemplo .XML siguiente, el dispositivo se bloqueará de manera que solo las aplicaciones especificadas en la lista de permitidas (Microsoft Edge en este caso) estén disponibles para su uso en el dispositivo. Las aplicaciones no identificadas con sus [identificadores de producto de la aplicación Windows 10 Mobile](https://msdn.microsoft.com/en-us/windows/hardware/commercialize/customize/mdm/enterpriseassignedaccess-csp#productid) en la lista de permitidas permanecen instaladas en el dispositivo, pero están ocultas a la vista y tienen bloqueado el inicio. Para especificar los datos .XML necesarios, basta con importar un nuevo archivo .XML que contenga la siguiente información de muestra o copiar y pegar esta información como XML con formato de línea única en el área de texto **Valor**:


> [!IMPORTANT]
> Al pegar la muestra de XML con formato proporcionada en el cuadro de valores, asegúrese de que todo el XML tiene formato de línea única.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<HandheldLockdown version="1.0">
   <Default>
      <ActionCenter enabled="false" />
      <Apps>
         <!-- Microsoft Edge -->
         <Application productId="{395589FB-5884-4709-B9DF-F7D558663FFD}" autoRun="true">
            <PinToStart>
               <Size>Medium</Size>
               <Location>
                  <LocationX>0</LocationX>
                  <LocationY>0</LocationY>
               </Location>
            </PinToStart>
         </Application>
      </Apps>
      <Buttons>
         <ButtonLockdownList>
            <!-- Lockdown all buttons -->
            <Button name="Search">
               <ButtonEvent name="Press" />
               <ButtonEvent name="PressAndHold" />
            </Button>
            <Button name="Camera">
               <ButtonEvent name="Press" />
               <ButtonEvent name="PressAndHold" />
            </Button>
         </ButtonLockdownList>
         <ButtonRemapList />
      </Buttons>
      <MenuItems>
         <DisableMenuItems />
      </MenuItems>
      <Settings>
         <System name="Microsoft.WiFi" />
         <System name="Microsoft.About" />
         <System name="Microsoft.Feedback" />
         <System name="Microsoft.CompanyAccount" />
         <System name="Microsoft.VPN" />
      </Settings>
      <StartScreenSize>Small</StartScreenSize>
   </Default>
</HandheldLockdown>

```
Una vez creada la directiva, impleméntela en un grupo de dispositivos Windows que quiera configurar como dispositivos de pantalla completa.

> [!IMPORTANT]
> Asegúrese de que la directiva de acceso asignado se implementa en el grupo correcto. La única forma de revertir una directiva de acceso asignado es restableciendo la configuración de fábrica del dispositivo.

### <a name="learn-more"></a>Obtener más información
[Introducción al uso de Enterprise Mobility + Security](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)

