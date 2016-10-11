---
title: "Cómo usar aplicaciones con compatibilidad con varias identidades"
description: "Cómo usar aplicaciones con compatibilidad con varias identidades"
keywords: 
author: craigcaseyMSFT
manager: jeffgilb
ms.date: 09/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 586ecd93-b097-42a0-9229-bcf3b781021c
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c704180f9c607e39c27d75676eec30afa1a1730c
ms.openlocfilehash: a45bf5fe6c58c89d386f95cd26a1d2dac68b6c05


---

# Cómo usar aplicaciones con compatibilidad con varias identidades

En este caso, usamos Microsoft Word como ejemplo. Puede aplicar estos mismos pasos a otras aplicaciones incluidas en Office 365.
1.  Abra la aplicación **Word** en su dispositivo. En este ejemplo, usamos un dispositivo iOS.
2.  Pulse **Nuevo** para crear un documento de Word.

  ![TEXTO DESCRIPTIVO](./media/ft-multiID-1-createDoc.png)

3.  Escriba la frase que quiera y pulse **Guardar**. Se ofrecerán dos opciones para guardar el documento: la ubicación personal y la ubicación de trabajo. Las directivas de aplicación no están activas en esta etapa, ya que todavía no hemos establecido si el documento es para uso profesional o personal.
4.  Guarde el documento en su **ubicación de trabajo**, como OneDrive para la Empresa. Puesto que OneDrive para la Empresa se reconoce como la ubicación de trabajo, el documento se etiqueta como datos de empresa y se aplican las restricciones de directivas.

  ![TEXTO DESCRIPTIVO](./media/ft-multiID-2-saveDoc.png)

5.  Ahora, abra el documento que acaba de guardar en su ubicación de trabajo y copie el texto. Abra su cuenta personal de **Facebook** y pruebe a pegar el texto copiado. Verá que no puede pegar el contenido en la nueva publicación de Facebook. La opción Pegar no está atenuada, pero no ocurre nada al presionar **Pegar**. Esto se debe a que las restricciones de directivas impiden compartir datos corporativos en aplicaciones personales.

  ![TEXTO DESCRIPTIVO](./media/ft-multiID-3-copyText.png)

  ![TEXTO DESCRIPTIVO](./media/ft-multiID-4-pasteInFB.png)
6.  Después, repita los pasos 2 y 3 para crear otro documento de Word. Escriba la frase que quiera y, esta vez, guárdelo en su ubicación personal, como **OneDrive: personal**. El documento se etiqueta como personal y no se aplican restricciones de directivas corporativas.

  ![TEXTO DESCRIPTIVO](./media/ft-multiID-5-createDoc.png)

7.  Abra el documento que acaba de guardar en su ubicación personal y copie el texto. Vuelva a abrir **Facebook** y pegue el texto copiado. Dado que el documento está etiquetado como personal, debería poder pegar el contenido en una publicación de Facebook.

  ![TEXTO DESCRIPTIVO](./media/ft-multiID-6-copyText.png)

### ¿Desea obtener más información?
Consulte [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).



<!--HONumber=Sep16_HO4-->


