---
title: '&#39;获取&#39;的属性访问器&#39; &lt;propertyname&gt; &#39;不可访问'
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: 0972c0909f8b07aa1c6700ec32d1a1ca55d00cc1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590200"
---
# <a name="39get39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a>&#39;获取&#39;的属性访问器&#39; &lt;propertyname&gt; &#39;不可访问
语句试图检索属性的值，如果它不具有对该属性的访问`Get`过程。  
  
 如果[Get 语句](../../../visual-basic/language-reference/statements/get-statement.md)标记具有限制性更强的访问权限级别比其[属性语句](../../../visual-basic/language-reference/statements/property-statement.md)，尝试读取属性值在以下情况可能会失败：  
  
-   `Get`语句被标记为[私有](../../../visual-basic/language-reference/modifiers/private.md)，但调用代码以外的类或结构在其中定义该属性。  
  
-   `Get`语句被标记为[受保护](../../../visual-basic/language-reference/modifiers/protected.md)，调用代码不在类或结构在其中定义该属性，也不派生类中。  
  
-   `Get`语句被标记为[友元](../../../visual-basic/language-reference/modifiers/friend.md)而调用的代码不在同一程序集在其中定义该属性。  
  
 **错误 ID:** BC31103  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果已定义属性的源代码管理，请考虑声明`Get`属性本身的相同访问级别的过程。  
  
-   如果你不能定义属性，对源代码的控制或必须限制`Get`过程访问级别的多个属性自身，尝试将读取对区域的代码具有更好地访问的属性值的语句属性。  
  
## <a name="see-also"></a>请参阅  
 [属性过程](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [如何：声明具有混合访问级别的属性](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
