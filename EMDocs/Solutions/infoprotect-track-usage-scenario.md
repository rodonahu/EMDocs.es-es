---
title: Realizar un seguimiento del uso de datos compartidos y responder ante un abuso de datos | Microsoft Docs
description: Escenario que describe la manera en que se puede usar Enterprise Mobility + Security para realizar un seguimiento del uso de datos compartidos y responder ante un abuso de datos mediante las funciones de Azure Rights Management.
author: yuridio
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: solution
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: c7e6e01a-5796-4bd7-a0c5-847ecfc08a1e
ms.reviewer: v-craic
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: bc112d81a2b0e59f9ae67efe2a914b0c64ac76ba
ms.openlocfilehash: 81e6b6479dcca1a82b37cfc4c832f36e33ac1b7b
ms.contentlocale: es-es
ms.lasthandoff: 05/29/2017



---

# <a name="track-usage-of-shared-data-and-respond-to-data-abuse"></a>Realizar un seguimiento del uso de datos compartidos y responder ante un abuso de datos

Para realizar un seguimiento del uso o de un abuso de datos, es fundamental tener visibilidad y control de los datos compartidos. En la actualidad, el uso compartido de datos es cada vez más amplio y las organizaciones necesitan compartir datos fuera de su dominio para satisfacer sus necesidades empresariales.

En este contexto, es habitual que los usuarios no solo compartan documentos, sino que supervisen quién tiene acceso a ellos y revoquen el acceso cuando sea necesario. Los administradores de TI quieren poder disfrutar de una experiencia similar a la que se produce en la actualidad al compartir datos con un grupo de usuarios autorizados, es decir, quieren mantener el control y emprender las acciones adecuadas con respecto al uso de datos o a su abuso. Siga leyendo para obtener más información sobre cómo Enterprise Mobility + Security ayuda a abordar este escenario.

## <a name="how-can-enterprise-mobility--security-help-you"></a>¿Cómo puede ayudarle Enterprise Mobility + Security?
Enterprise Mobility + Security (EMS) es la única solución en la nube integral que protege los datos corporativos en el propio dispositivo y más allá con cuatro niveles de protección en las identidades, los dispositivos, las aplicaciones y los datos. EMS le ayuda a resolver uno de los principales desafíos en un mundo que da prioridad a los dispositivos móviles y la nube: cómo compartir datos y, al mismo tiempo, mantener el control y emprender acciones para solucionar rápidamente un problema. Con EMS, podrá permitir que los empleados colaboren de forma segura dentro y fuera de la organización. EMS permite que los propietarios de documentos y los administradores realicen un seguimiento de actividades en los archivos confidenciales que han compartido con otras personas. Pueden ver las actividades, por ejemplo, los destinatarios que abren el archivo o los usuarios no autorizados a los que se deniega el acceso a los archivos. Los usuarios también pueden ver las ubicaciones geográficas desde las que se accede a los archivos. Con un solo clic, los usuarios también pueden revocar el acceso a un archivo compartido.

### <a name="recommended-solution"></a>Solución recomendada
Mediante la integración de Azure Rights Management, puede realizar un seguimiento de la manera en que se usan los documentos protegidos. Si es necesario, también puede revocar el acceso a estos documentos cuando ya no desee seguir compartiéndolos. Esta función está disponible para aplicaciones de Office (Word, Excel, Outlook y PowerPoint) mediante el grupo de RMS, la opción de uso compartido protegido y el seguimiento del uso. En los sistemas Windows también puede usar el Explorador de archivos, mientras que en todos los demás dispositivos compatibles puede realizar un seguimiento del uso mediante el explorador web. El seguimiento y la revocación forman parte de la fase de supervisión y respuesta del ciclo de vida del documento, tal como se muestra en el diagrama siguiente:

![Gráfico en el que se muestra el ciclo de vida del documento en Azure Rights Management.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig1.png)

Vea este breve vídeo para obtener una introducción rápida de la manera en que Azure Information Protection facilita el seguimiento del uso de documentos.

<iframe width="675" height="480" src="https://sec.ch9.ms/ch9/76ac/35499c0a-859c-4a3e-9a5c-fa4e5d0e76ac/AzureRMSDocumentTrackingandRevocation_high.mp4 " frameborder="0" allowfullscreen></iframe>

#### <a name="how-to-implement-this-solution"></a>Cómo implementar esta solución
No es necesario que configure la función de seguimiento del uso de datos compartidos si ya siguió los pasos del escenario sobre el [uso compartido de datos confidenciales interna y externamente](https://docs.microsoft.com/enterprise-mobility-security/solutions/share-sensitive-data) para configurar Azure Rights Management y la aplicación cliente. Ahora solo debe elegir cómo quiere realizar el seguimiento de los documentos. Las opciones disponibles son las siguientes:

1. Realizar el seguimiento mediante Office
- Realizar el seguimiento mediante el explorador
- Revocar el acceso a un documento compartido

### <a name="how-to-track-usage-of-shared-data-and-respond-to-data-abuse"></a>Cómo realizar un seguimiento del uso de datos compartidos y responder ante un abuso de datos
En las secciones siguientes se indican las opciones disponibles para realizar un seguimiento del uso de datos compartidos según un escenario concreto.

#### <a name="scenario-1-track-usage-using-microsoft-office"></a>Escenario 1: realizar el seguimiento mediante Microsoft Office
Los usuarios que quieran obtener más información sobre el uso de documentos protegidos mediante aplicaciones de Office (Word, Excel y PowerPoint) pueden usar el grupo de RMS, seleccionar **Uso compartido protegido** y, después, hacer clic en **Hacer seguimiento de uso**, tal como se muestra en la imagen siguiente:

![Gráfico en el que se muestra cómo se establece la opción "Hacer seguimiento de uso" en aplicaciones de Office.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig2.png)

Consulte [Seguimiento y revocación de documentos cuando se utiliza la aplicación RMS sharing](https://docs.microsoft.com/information-protection/rms-client/sharing-app-track-revoke) para obtener más información sobre esta característica.

#### <a name="scenario-2-track-usage-using-browser"></a>Escenario 2: realizar el seguimiento mediante el explorador
En algunas circunstancias, puede darse que no tenga una aplicación de Office instalada en el dispositivo, pero que aun así necesite supervisar el uso de documentos. Desde un [explorador compatible](https://docs.microsoft.com/rights-management/rms-client/sharing-app-track-revoke), vaya al [sitio de seguimiento de documentos](http://go.microsoft.com/fwlink/?LinkId=529562) e inicie sesión con sus credenciales. Al seleccionar el documento del que quiera realizar un seguimiento, debería ver las estadísticas de uso, tal como se muestra en la pantalla siguiente:

![Gráfico en el que se muestran estadísticas generales del uso de documentos desde un explorador web.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig3.png)

En esta pantalla, puede ver el número de visualizaciones y el número de veces que se denegó el acceso durante los meses en los que se compartió el archivo. Aunque cada icono tiene un resumen en el que se muestran los usuarios que tuvieron acceso al archivo, puede hacer clic en el icono para obtener más información. En el ejemplo de la pantalla anterior, se muestra el resultado siguiente cuando se selecciona el acceso denegado:

![Gráfico en el que se muestran las estadísticas de acceso denegado a un documento desde un explorador web.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig4.png)

#### <a name="scenario-3-revoke-access-to-shared-document"></a>Escenario 3: revocar el acceso a un documento compartido

Cuando se supervisa un documento, el uso es un paso importante para comprender el comportamiento de un usuario. Su principal beneficio resulta evidente cuando se puede emprender una acción basada en lo que se detectó al supervisar el documento. Por ejemplo, después de leer el informe de uso, descubre que se le denegó el acceso a un usuario válido cuando intentaba acceder a un documento. En este momento, debe emprender una acción correctiva para resolver este problema.

En otros escenarios, tendrá que responder a un incidente de seguridad. Por ejemplo, se detecta que uno de los documentos que se compartieron ampliamente contenía información confidencial de la empresa y RR. HH. le solicita al departamento de TI que revoque el acceso a dicho documento. Al [revocar un documento](https://docs.microsoft.com/rights-management/rms-client/sharing-app-track-revoke), no se elimina el documento que se ha compartido, pero los usuarios autorizados ya no podrán abrirlo. Para revocar el acceso, simplemente debe hacer clic en **Revocar acceso**, que se encuentra en la página de seguimiento del uso. Verá un formulario similar al siguiente:

![Gráfico en el que se muestra el formulario Revocar acceso, que permite revocar el acceso a un documento.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig5.png)

Puede habilitar la opción para notificar a los destinatarios que se ha revocado el acceso a este documento. Además, puede incluir un mensaje con los motivos por los que se ha revocado.

