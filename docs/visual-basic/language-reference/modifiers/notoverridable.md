---
title: NotOverridable
ms.date: 07/20/2015
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
ms.openlocfilehash: c55d57bb3008b2825fe5382844908ea32f0d500c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351446"
---
# <a name="notoverridable-visual-basic"></a>NotOverridable (Visual Basic)
指定不能在派生类中重写属性或过程。  
  
## <a name="remarks"></a>备注  
 `NotOverridable` 修饰符可防止在派生类中重写属性或方法。  可[重写](../../../visual-basic/language-reference/modifiers/overridable.md)的修饰符允许在派生类中重写类中的属性或方法。 有关详细信息，请参阅[继承基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)。  
  
 如果未指定 `Overridable` 或 `NotOverridable` 修饰符，则默认设置取决于属性或方法是重写基类属性还是重写方法。 如果属性或方法重写基类属性或方法，则默认设置为 `Overridable`;否则，`NotOverridable`。  
  
 不能重写的元素有时称为*密封*元素。  
  
 只能在属性或过程声明语句中使用 `NotOverridable`。 只能在替代另一个属性或过程的属性或过程上指定 `NotOverridable`，也就是说，只能与 `Overrides`结合使用。  
  
## <a name="combined-modifiers"></a>组合修饰符  
 不能为 `Private` 方法指定 `Overridable` 或 `NotOverridable`。  
  
 不能在同一声明中同时指定 `NotOverridable` 与 `MustOverride`、`Overridable`或 `Shared`。  
  
## <a name="usage"></a>用法  
 `NotOverridable` 修饰符可用于下面的上下文中：  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>另请参阅

- [修饰符](../../../visual-basic/language-reference/modifiers/index.md)
- [继承的基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MyBase](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [关键字](../../../visual-basic/language-reference/keywords/index.md)
- [Visual Basic 中的阴影](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
