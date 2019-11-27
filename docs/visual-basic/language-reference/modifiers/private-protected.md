---
title: Private Protected
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 265141f77f4a61a61414a07214830feaa8a1ab05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351348"
---
# <a name="private-protected-visual-basic"></a>私有受保护（Visual Basic）

`Private Protected` 关键字组合是一种成员访问修饰符。 `Private Protected` 成员可以由其包含类中的所有成员访问，也可由派生自包含类的类型访问，但前提是在它的包含程序集内找到。

只能在类的成员上指定 `Private Protected`;无法将 `Private Protected` 应用到结构的成员，因为结构不能继承。

Visual Basic 15.5 及更高版本支持 `Private Protected` 访问修饰符。 若要使用它，可以将以下元素添加到 Visual Basic 项目（\*.vbproj）文件。 只要您的系统上安装了 Visual Basic 15.5 或更高版本，就可以利用 Visual Basic 编译器最新版本支持的所有语言功能：

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

有关详细信息，请参阅[设置 Visual Basic 语言版本](../../language-reference/configure-language-version.md)。

> [!NOTE]
> 在 Visual Studio 中，选择 `private protected` 上的 F1 帮助为[私有](private.md)或[受保护](protected.md)的提供帮助。 IDE 将选取光标下的单个标记，而不是组合词。

## <a name="rules"></a>规则

- **声明上下文。** 只能在类级别使用 `Private Protected`。 这意味着 `Protected` 元素的声明上下文必须是类，且不能是源文件、命名空间、接口、模块、结构或过程。

## <a name="behavior"></a>行为

- **访问级别。** 类中的所有代码都可以访问其元素。 派生自基类并包含在同一程序集中的任何类中的代码都可以访问该基类的所有 `Private Protected` 元素。 但是，任何派生自基类的类中的代码都包含在不同的程序集中，因此无法访问基类 `Private Protected` 元素。

- **访问修饰符。** 指定访问级别的关键字称为*访问修饰符*。 有关访问修饰符的比较，请参阅[Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。

`Private Protected` 修饰符可用于下面的上下文中：

- 嵌套类的[Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)

- [Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)

- [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)

- 嵌套在类中的委托的[委托语句](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)

- 嵌套在类中的枚举的[枚举语句](../../../visual-basic/language-reference/statements/enum-statement.md)

- [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)

- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)

- 嵌套在类中的接口的[接口语句](../../../visual-basic/language-reference/statements/interface-statement.md)

- [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)

- 嵌套在类中的结构的[结构语句](../../../visual-basic/language-reference/statements/structure-statement.md)

- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>另请参阅

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Protected Friend](./protected-friend.md)
- [Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
