---
title: Overrides
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 04f1cb27d6a8366c2dd13f8fdc1d975d382f1cfd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351384"
---
# <a name="overrides-visual-basic"></a>Overrides (Visual Basic)

指定某一属性或过程可重写从基类中继承的具有相同名称的属性或过程。

## <a name="rules"></a>规则

- **Declaration Context.** You can use `Overrides` only in a property or procedure declaration statement.

- **Combined Modifiers.** You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration. 由于重写元素是隐式可重写的，因此不能将 `Overridable` 与 `Overrides` 组合到一起。

- **Matching Signatures.** The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides. 这意味着参数列表必须具有相同数量的参数，并且排序顺序和数据类型都必须完全相同。

  除签名外，重写的声明还必须完全匹配以下项：

  - 访问级别

  - 返回类型（如有）

- **Generic Signatures.** 对于泛型过程，签名包括类型参数的数量。 因此，重写的声明必须在这方面与基类版本匹配。

- **Additional Matching.** 除匹配基类版本的签名外，此声明还必须在以下方面与其匹配：

  - Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))

  - Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))

  - 泛型过程的每个类型参数的约束列表

- **Shadowing and Overriding.** 隐藏和重写操作都可重新定义继承的元素，但这两种方法之间又具有很大的差异。 For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).

如果使用 `Overrides`，编译器将隐式添加 `Overloads`，以便库 API 更轻松地使用 C#。

`Overrides` 修饰符可用于下面的上下文中：

- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)

- [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)

- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>请参阅

- [New](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [关键字](../../../visual-basic/language-reference/keywords/index.md)
- [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [类型列表](../../../visual-basic/language-reference/statements/type-list.md)
