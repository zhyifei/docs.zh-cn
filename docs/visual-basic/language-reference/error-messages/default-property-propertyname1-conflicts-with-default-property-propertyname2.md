---
title: 默认属性&#39; &lt;propertyname1&gt; &#39;默认属性与冲突&#39; &lt;propertyname2&gt; &#39;在&#39; &lt;classname&gt; &#39;，因此应声明&#39;Shadows&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 3099467fa3c5a162c13c9235fb8d55375953ba3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521421"
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a>默认属性&#39; &lt;propertyname1&gt; &#39;默认属性与冲突&#39; &lt;propertyname2&gt; &#39;在&#39; &lt;classname&gt; &#39;，因此应声明&#39;Shadows&#39;
使用与基类中定义的属性相同的名称声明属性。 在这种情况下，在此类的属性应隐藏基类属性。  
  
 此消息是一个警告。 默认假定`Shadows` 。 若要深入了解如何隐藏警告或将警告视为错误，请参阅 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC40007  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   添加`Shadows`关键字为声明或将更改正在声明的属性的名称。  
  
## <a name="see-also"></a>请参阅
- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [在 Visual Basic 中隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
