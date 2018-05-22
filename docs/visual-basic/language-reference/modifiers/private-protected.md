---
title: 私有受保护 (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 23fd6583182a1fee544d0458dc3fc390aed86b9f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="private-protected-visual-basic"></a>私有受保护 (Visual Basic)

`Private Protected`关键字组合都是成员访问修饰符。 A`Private Protected`成员是否可访问由其包含的类中的所有成员以及类型派生自包含的类，但仅当它们位于其包含的程序集。 

你可以指定`Private Protected`仅能对成员的类; 不能应用`Private Protected`结构的成员由于结构不能被继承。

`Private Protected`由 Visual Basic 15.5 和更高版本提供支持访问修饰符。 若要使用它，可以将下面的元素添加到 Visual Basic 项目 (*.vbproj) 文件。 如你系统上安装了 Visual Basic 15.5 作为长或更高版本，它允许您充分利用最新版本的 Visual Basic 编译器支持的语言功能：

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> 在 Visual Studio 中，选择 F1 帮助上`private protected`提供为帮助[私有](private.md)或[保护](protected.md)。 IDE 选取下光标，而不是复合 word 单个标记。

## <a name="rules"></a>规则

- **声明上下文。** 你可以使用`Private Protected`只能在类级别。 这意味着的声明上下文`Protected`元素必须是类，并且不能为源文件、 命名空间、 接口、 模块、 结构或过程。

## <a name="behavior"></a>行为

- **访问级别。** 类中的所有代码可以都访问其元素。 中的任何类都派生自的基类，并且包含在同一程序集代码可以访问所有`Private Protected`元素的基类。 但是，在任何类中派生自的基类和其他程序集中包含的代码不能访问的基类`Private Protected`元素。

- **访问修饰符。** 指定的访问级别的关键字称为*访问修饰符*。 访问修饰符的比较，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。
  
 `Private Protected` 修饰符可用于下面的上下文中：  
  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)的嵌套类  
  
 [Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate 语句](../../../visual-basic/language-reference/statements/delegate-statement.md)委托的嵌套类中  
  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)eumeration 的嵌套类中 
  
 [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)接口的嵌套类中 
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [结构语句](../../../visual-basic/language-reference/statements/structure-statement.md)结构的嵌套类中 
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>请参阅

[Public](../../../visual-basic/language-reference/modifiers/public.md)  
[Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
[友元](friend.md)   
[Private](../../../visual-basic/language-reference/modifiers/private.md)  
[受保护的友元](./protected-friend.md)   
[在 Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
