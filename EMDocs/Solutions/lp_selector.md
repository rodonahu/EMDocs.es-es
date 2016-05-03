---
# required metadata

title: Cómo crear selectores
description:
keywords:
author: 
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: bc085933-c33a-470b-b018-509afdc3e576

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

Don't think we need the H1, so I've removed it here, strictly for testing purposes.

Aquí vemos un selector unidireccional:

> [AZURE.SELECTOR]
- [Opción de selector 1](lp-selector1.md)
- [Opción de selector 2](lp-selector2.md)

En el caso de que usemos el método Azure.

Esta es la forma "sucia":
<ul class="document-ui">
  <li>
    <div class="dropdown-container">
      <label for="dropdown">Seleccione una opción</label>
      <div class="dropdown">
        <select>
          <option value="option-a">Opción A</option>
          <option value="option-b">Opción B</option>
        </select>
      </div>
</li>
</ul>

No obstante, con la forma "sucia" no se indica cómo cambiar el contenido en función de la opción elegida.

<!--HONumber=Apr16_HO2-->


