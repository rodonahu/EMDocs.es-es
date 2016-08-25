---
title: "Protección de los datos adjuntos de correo electrónico de la empresa"
description: "Proteja el contenido del correo electrónico y los datos adjuntos de este mediante las directivas de administración de aplicaciones móviles (MAM)."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: a1e630c1-7190-4ba9-b71d-ed9c2e93a6cc
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 55a3dbe32e3b5e10e21a6d99bc101ec76fc51f5e
ms.openlocfilehash: 3a3631e454323226958b2f1db003883d1ace562e


---

# Impedir el filtrado de datos de correo electrónico y datos adjuntos
En [Protección de documentos y del correo electrónico corporativos](protect-corporate-email-documents.md), se describe cómo puede asegurarse de que solo los dispositivos admitidos puedan acceder al correo electrónico corporativo. Sin embargo, el contenido del correo electrónico y los datos adjuntos no está protegido al proteger el acceso. El contenido se puede copiar, mover, guardar en una ubicación diferente o compartir con otro usuario. EMS soluciona este problema mediante directivas de administración de aplicaciones móviles.

Las aplicaciones administradas son aplicaciones que implementa el Administrador de TI que cumplen los requisitos de seguridad de las empresas. Con estas aplicaciones, el departamento de TI tiene control directo sobre la implementación, la administración continua, como el inventario o las actualizaciones, y la eliminación selectiva de las aplicaciones y los datos asociados. Asimismo, a través de un conjunto de directivas de administración de aplicaciones móviles (MAM), Intune permite modificar la funcionalidad de las aplicaciones y restringir los datos que se comparten. Ofrece la posibilidad de realizar, por ejemplo, lo siguiente:

-   Copiar y pegar en bloque o impedir la transferencia de datos desde una aplicación administrada a una aplicación sin directiva MAM.

-   Evitar la copia de seguridad en el almacenamiento en nube personal, la opción Guardar como, etc.

-   Proteger el acceso a la aplicación al requerir el PIN o código de acceso o credenciales corporativas en una aplicación protegida con MAM.

-   Configurar la aplicación para que abra todos los vínculos web dentro del explorador administrado de Intune.

-   Borrar selectivamente solo los datos asociados con la aplicación administrada. Cuando un dispositivo se pierde o roba, o ya no lo administra el departamento de TI, una eliminación selectiva puede quitar todos los datos corporativos de las aplicaciones, dejando sólo los datos personales de la aplicación. Esto se conoce como multiidentidad.

Con [Azure Rights Management Services](https://docs.microsoft.com/rights-management/understand-explore/what-is-azure-rms), puede ampliar la protección de correo electrónico de las maneras siguientes:

-   Los mensajes de correo electrónico pueden cifrarse de manera que solo los usuarios deseados puedan leer o ver el contenido dentro o fuera de la empresa.

-   Los usuarios pueden proteger los mensajes de correo electrónico y el destinatario puede leer y utilizar los mensajes de correo electrónico protegidos que se le envían.

-   Un administrador puede establecer reglas para:

    -   Aplicar las reglas automáticamente a un grupo específico de destinatarios o crear plantillas para departamentos concretos.

    -   Detectar y aplicar reglas a los mensajes de correo electrónico con contenido confidencial automáticamente. La regla puede basarse en el remitente, destinatario, asunto del mensaje o contenido.

    -   Detectar contenido confidencial y avisar al remitente para que aplique las reglas de protección antes de enviar el correo electrónico.

## Componentes de aplicaciones administradas

-   **Microsoft Intune** es el lugar en el que se configuran las directivas, se asocian con la aplicación o se usa la herramienta de ajuste de aplicaciones para permitir que una aplicación interna use directivas de administración de aplicaciones móviles.

-   El**Portal de empresa** es una aplicación que se ejecuta de forma nativa en cada dispositivo o está basada en el explorador. El departamento de TI implementa las aplicaciones administradas para los usuarios o dispositivos, y los usuarios finales pueden instalar la aplicación desde el portal. Las directivas asociadas con las aplicaciones se transfieren al dispositivo con las aplicaciones.

![Gráfico que muestra cómo se gestionan las directivas dirigidas a aplicaciones administradas a través del portal de empresa y Microsoft Intune](./media/ProtectEmail/CADataSheet-Diagram-Apps.png)

## La experiencia de administración de TI:
El Administrador de TI crea las directivas de administración de aplicaciones móviles, asocia la directiva a la aplicación y distribuye a los usuarios o dispositivos. Cuando la aplicación administrada se instala en el dispositivo, se aplican las restricciones de la aplicación. Crear e implementar aplicaciones administradas supone poco o ningún esfuerzo adicional:

-   Hay aplicaciones existentes que ya tienen el SDK de aplicación que permite aplicar restricciones a la aplicación. No requieren ningún otro procesamiento: basta con agregar un vínculo a una tienda de aplicaciones, como iTunes o Google Play. Lea [este artículo](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) para ver la lista de aplicaciones administradas.

-   Si quiere administrar las aplicaciones creadas internamente, puede volver a empaquetar las aplicaciones con la herramienta de ajuste de aplicaciones de Microsoft Intune. La herramienta vuelve a empaquetar la aplicación, lo que le permite aplicar restricciones a la aplicación.

## Experiencia del usuario final
Los usuarios finales pueden instalar aplicaciones administradas y usarlas para hacer su trabajo. Sólo podrán mover o compartir datos entre aplicaciones administradas. Se bloqueará cualquier intento de mover datos fuera del ecosistema de aplicaciones administradas.

## Próximos pasos
Ahora que sabe cómo [proteger documentos y correo electrónico corporativos](protect-corporate-email-documents.md), así como datos adjuntos de correo, puede conocer cómo [implementar una solución para proteger el correo electrónico empresarial](implement-solution.md).



<!--HONumber=Aug16_HO1-->


