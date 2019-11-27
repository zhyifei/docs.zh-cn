---
title: New
ms.date: 07/20/2015
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
ms.openlocfilehash: dc6a153a604fd0e5cee9d7d46ebcd63294f33628
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351484"
---
# <a name="mustoverride-visual-basic"></a>MustOverride (Visual Basic)
指定在此类中未实现的属性或过程，并且在使用之前必须在派生类中重写该属性或过程。  
  
## <a name="remarks"></a>备注  
 只能在属性或过程声明语句中使用 `MustOverride`。 指定 `MustOverride` 的属性或过程必须是类的成员，并且该类必须标记为[MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)。  
  
## <a name="rules"></a>规则  
  
- **不完整声明。** 当指定 `MustOverride`时，您不会为该属性或过程（甚至 `End Function`、`End Property`或 `End Sub` 语句）提供任何其他代码行。  
  
- **组合修饰符。** 不能在同一声明中同时指定 `MustOverride` 与 `NotOverridable`、`Overridable`或 `Shared`。  
  
- **隐藏和重写。** 隐藏和重写操作都可重新定义继承的元素，但这两种方法之间又具有很大的差异。 有关详细信息，请参阅[Visual Basic 中的隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。  
  
- **替代条款。** 除了在重写中外，不能使用的元素有时称为*纯虚拟*元素。  
  
 `MustOverride` 修饰符可用于下面的上下文中：  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>另请参阅

- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [关键字](../../../visual-basic/language-reference/keywords/index.md)
- [Visual Basic 中的阴影](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
