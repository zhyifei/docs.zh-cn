---
title: "&#39;集 &#39;访问器的属性 &#39;&lt;propertyname&gt;&#39; 不可访问"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords: BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9256a09b719ad3890e1d7c2cc23ffb0d40eec62f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39set39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a>&#39;集 &#39;访问器的属性 &#39;&lt;propertyname&gt;&#39; 不可访问
语句试图存储属性的值，如果它不具有对该属性的访问`Set`过程。  
  
 如果[Set 语句](../../../visual-basic/language-reference/statements/set-statement.md)标记具有限制性更强的访问权限级别比其[属性语句](../../../visual-basic/language-reference/statements/property-statement.md)，尝试设置的属性值在以下情况可能会失败：  
  
-   `Set`语句被标记为[私有](../../../visual-basic/language-reference/modifiers/private.md)，但调用代码以外的类或结构在其中定义该属性。  
  
-   `Set`语句被标记为[受保护](../../../visual-basic/language-reference/modifiers/protected.md)，调用代码不在类或结构在其中定义该属性，也不派生类中。  
  
-   `Set`语句被标记为[友元](../../../visual-basic/language-reference/modifiers/friend.md)而调用的代码不在同一程序集在其中定义该属性。  
  
 **错误 ID:** BC31102  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果已定义属性的源代码管理，请考虑声明`Set`属性本身的相同访问级别的过程。  
  
-   如果你不能定义属性，对源代码的控制或必须限制`Set`过程访问级别限制性比强属性自身，尝试移动到具有更好地访问的代码区域设置的属性值的语句属性。  
  
## <a name="see-also"></a>另请参阅  
 [属性过程](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [如何：声明具有混合访问级别的属性](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
