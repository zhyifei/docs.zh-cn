---
title: Shadows
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: e9a423fa69ad1dcd8c1d4a5b7085e5b5da548f93
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351267"
---
# <a name="shadows-visual-basic"></a>Shadows (Visual Basic)

指定已声明的编程元素重新声明并隐藏基类中具有相同名称的元素或重载元素集。

## <a name="remarks"></a>备注

隐藏（也称为*按名称隐藏*）的主要目的是保留类成员的定义。 基类可能会发生更改，该更改将创建一个与已定义的元素同名的元素。 如果发生这种情况，则 `Shadows` 修饰符强制将通过类的引用解析为你定义的成员，而不是新的基类元素。

隐藏和重写操作都可重新定义继承的元素，但这两种方法之间又具有很大的差异。 有关详细信息，请参阅[Visual Basic 中的隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。

## <a name="rules"></a>规则

- **声明上下文。** 只能在类级别使用 `Shadows`。 这意味着 `Shadows` 元素的声明上下文必须是类，且不能是源文件、命名空间、接口、模块、结构或过程。

  只能在单个声明语句中声明一个隐藏元素。

- **组合修饰符。** 不能在同一声明中同时指定 `Shadows` 与 `Overloads`、`Overrides`或 `Static`。

- **元素类型。** 可以与任何其他类型一起隐藏任何类型的已声明元素。 如果使用另一个属性或过程来隐藏属性或过程，则参数和返回类型不必与基类属性或过程中的相同。

- **访问.** 通常，基类中隐藏的元素在隐藏它的派生类中不可用。 不过，请注意以下事项。

  - 如果不能从引用它的代码访问隐藏元素，则会将引用解析为隐藏的元素。 例如，如果 `Private` 元素隐藏了基类元素，则没有权限访问 `Private` 元素的代码将改为访问基类元素。

  - 如果隐藏元素，仍然可以通过使用基类的类型声明的对象访问隐藏的元素。 还可以通过 `MyBase`来访问它。

`Shadows` 修饰符可用于下面的上下文中：

- [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)

- [Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)

- [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Delegate 语句](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)

- [Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)

- [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)

- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)

- [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)

- [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)

- [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)

- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>另请参阅

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Static](../../../visual-basic/language-reference/modifiers/static.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Me、My、MyBase 和 MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [继承的基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MyBase](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Visual Basic 中的阴影](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
