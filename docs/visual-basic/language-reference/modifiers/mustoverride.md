---
title: MustOverride (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a2f7bdba4b01bd307e0c52802509669f772b5eb5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="mustoverride-visual-basic"></a>MustOverride (Visual Basic)
指定属性或过程中此类未实现，并且必须重写派生类中才可以使用。  
  
## <a name="remarks"></a>备注  
 只能在属性或过程声明语句中使用 `MustOverride`。 属性或过程的指定`MustOverride`必须是类的成员并且类必须加以标记[MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)。  
  
## <a name="rules"></a>规则  
  
-   **不完整的声明。** 当指定`MustOverride`，不会不提供任何其他代码行的属性或过程，即使`End Function`， `End Property`，或`End Sub`语句。  
  
-   **组合的修饰符。** 不能指定`MustOverride`连同`NotOverridable`， `Overridable`，或`Shared`同一声明中。  
  
-   **隐藏和重写。** 隐藏和重写操作都可重新定义继承的元素，但这两种方法之间又具有很大的差异。 有关详细信息，请参阅[Visual Basic 中的隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。  
  
-   **替换术语。** 除不能用作重写中的元素有时称为*纯虚拟*元素。  
  
 `MustOverride` 修饰符可用于下面的上下文中：  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>另请参阅  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)  
 [在 Visual Basic 中隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
