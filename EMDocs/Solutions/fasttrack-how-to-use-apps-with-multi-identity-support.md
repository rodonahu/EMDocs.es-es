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
ms.sourcegitcommit: e422a74e551753ddb579d98789670cd8c1811b80
ms.openlocfilehash: 491616d76dc6616a2abe059b699448bec0e06e75


---

# Cómo usar aplicaciones con compatibilidad con varias identidades

En este caso, usamos Microsoft Word como ejemplo. Puede aplicar estos mismos pasos a otras aplicaciones incluidas en Office 365.
1.  Abra la aplicación **Word** en su dispositivo. En este ejemplo, usamos un dispositivo iOS.
2.  Pulse **Nuevo** para crear un documento de Word.

  ![Captura de pantalla en la cual se muestra que el usuario selecciona "Nuevo" para comenzar a crear un documento de Word.](./media/ft-multiID-1-createDoc.png)

3.  Escriba la frase que quiera y pulse **Guardar**. Se ofrecerán dos opciones para guardar el documento: la ubicación personal y la ubicación de trabajo. Las directivas de aplicación no están activas en esta etapa, ya que todavía no hemos establecido si el documento es para uso profesional o personal.

  ![Captura de pantalla en la que se muestra que el usuario ha escrito una frase en el nuevo documento de Word.](./media/ft-multiID-2-saveDoc.png)

4.  Guarde el documento en su **ubicación de trabajo**, como OneDrive para la Empresa. Puesto que OneDrive para la Empresa se reconoce como la ubicación de trabajo, el documento se etiqueta como datos de empresa y se aplican las restricciones de directivas.
5.  Ahora, abra el documento que acaba de guardar en su ubicación de trabajo y copie el texto. Abra su cuenta personal de **Facebook** y pruebe a pegar el texto copiado. Verá que no puede pegar el contenido en la nueva publicación de Facebook. La opción Pegar no está atenuada, pero no ocurre nada al presionar **Pegar**. Esto se debe a que las restricciones de directivas impiden compartir datos corporativos en aplicaciones personales.

  ![Captura de pantalla en la que se muestra que el usuario está copiando texto del documento de Word. ](./media/ft-multiID-3-copyText.png)

  ![Captura de pantalla en la que se muestra que el usuario está intentando pegar el texto en Facebook sin éxito.](./media/ft-multiID-4-pasteInFB.png)
6.  Después, repita los pasos 2 y 3 para crear otro documento de Word. Escriba la frase que quiera y, esta vez, guárdelo en su ubicación personal, como **OneDrive: personal**. El documento se etiqueta como personal y no se aplican restricciones de directivas corporativas.

  ![Captura de pantalla en la que se muestra que el usuario ha escrito una frase en un nuevo documento de Word.](./media/ft-multiID-5-createDoc.png)

7.  Abra el documento que acaba de guardar en su ubicación personal y copie el texto. Vuelva a abrir **Facebook** y pegue el texto copiado. Dado que el documento está etiquetado como personal, debería poder pegar el contenido en una publicación de Facebook.

  ![Captura de pantalla en la que se muestra que el usuario puede pegar correctamente el texto en Facebook.](./media/ft-multiID-6-copyText.png)

### ¿Desea obtener más información?
Consulte [Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).



<!--HONumber=Oct16_HO2-->


