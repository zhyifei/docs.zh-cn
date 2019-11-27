---
title: Overrides
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: 9c639665fd92a56de6fb6e5147cda873ef457b45
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351392"
---
# <a name="overridable-visual-basic"></a>Overridable (Visual Basic)
指定属性或过程可由派生类中具有相同名称的属性或过程重写。  
  
## <a name="remarks"></a>备注  
 `Overridable` 修饰符允许在派生类中重写类中的属性或方法。 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)修饰符防止在派生类中重写属性或方法。  有关详细信息，请参阅[继承基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)。  
  
 如果未指定 `Overridable` 或 `NotOverridable` 修饰符，则默认设置取决于属性或方法是重写基类属性还是重写方法。 如果属性或方法重写基类属性或方法，则默认设置为 `Overridable`;否则，`NotOverridable`。  
  
 您可以隐藏或重写来重新定义继承的元素，但这两种方法之间的差异很大。 有关详细信息，请参阅[Visual Basic 中的隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。  
  
 可以重写的元素有时称为*虚拟*元素。 如果可以重写，但不一定是，则有时也称为*具体*元素。  
  
 只能在属性或过程声明语句中使用 `Overridable`。  
  
## <a name="combined-modifiers"></a>组合修饰符  
 不能为 `Private` 方法指定 `Overridable` 或 `NotOverridable`。  
  
 不能在同一声明中同时指定 `Overridable` 与 `MustOverride`、`NotOverridable`或 `Shared`。  
  
 由于重写元素是隐式可重写的，因此不能将 `Overridable` 与 `Overrides` 组合到一起。  
  
## <a name="usage"></a>用法  
 `Overridable` 修饰符可用于下面的上下文中：  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>另请参阅

- [修饰符](../../../visual-basic/language-reference/modifiers/index.md)
- [继承的基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MyBase](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [关键字](../../../visual-basic/language-reference/keywords/index.md)
- [Visual Basic 中的阴影](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
