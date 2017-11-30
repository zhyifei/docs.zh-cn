---
title: NotOverridable (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6fc5fb006b36cda1b6ad0e128604bc3bb427fd94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="notoverridable-visual-basic"></a>NotOverridable (Visual Basic)
指定的属性或过程不能重写派生类中。  
  
## <a name="remarks"></a>备注  
 `NotOverridable`修饰符防止属性或方法被重写派生类中。  [可重写](../../../visual-basic/language-reference/modifiers/overridable.md)修饰符在派生类中重写的类中允许的属性或方法。 有关详细信息，请参阅[继承基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)。  
  
 如果`Overridable`或`NotOverridable`修饰符未指定，则默认设置取决于是否属性或方法重写基类属性或方法。 如果属性或方法重写基类属性或方法，默认设置是`Overridable`; 否则为它是`NotOverridable`。  
  
 不能重写元素有时称为*密封*元素。  
  
 只能在属性或过程声明语句中使用 `NotOverridable`。 你可以指定`NotOverridable`只会在属性或另一个属性或过程，也就是说，仅在中重写与结合使用的过程`Overrides`。  
  
## <a name="combined-modifiers"></a>组合的修饰符  
 不能指定`Overridable`或`NotOverridable`为`Private`方法。  
  
 不能指定`NotOverridable`连同`MustOverride`， `Overridable`，或`Shared`同一声明中。  
  
## <a name="usage"></a>用法  
 `NotOverridable` 修饰符可用于下面的上下文中：  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>另请参阅  
 [修饰符](../../../visual-basic/language-reference/modifiers/index.md)  
 [继承的基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)  
 [在 Visual Basic 中隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
