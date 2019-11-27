---
title: 如何：隐藏与您的变量同名的变量
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: 0915adbbabb778b1bdd3b6b30e56725a7e74867c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345358"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a>如何：隐藏与您的变量同名的变量 (Visual Basic)

您可以通过隐藏变量来*隐藏该变量*，也就是说，使用同一名称的变量重新定义该变量即可。 您可以通过两种方式隐藏要隐藏的变量：

- **通过范围隐藏。** 可以通过范围将其隐藏，方法是在包含要隐藏的变量的区域的子区域内重新声明。

- **通过继承隐藏。** 如果要隐藏的变量是在类级别定义的，可以通过继承将其隐藏，方法是使用派生类中的[Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)关键字对其进行重新声明。

## <a name="two-ways-to-hide-a-variable"></a>用于隐藏变量的两种方法

#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a>通过使用范围隐藏变量来隐藏变量

1. 确定定义要隐藏的变量的区域，并确定要将其与变量一起重新定义的子区域。

    |变量的区域|允许用于重新定义的子区域|
    |-----------------------|-------------------------------------------|
    |模块|模块内的类|
    |实例|类中的子类<br /><br /> 类中的过程|

    不能在该过程中的块内重新定义过程变量，例如，在 `If``End If` 构造或 `For` 循环中。

2. 如果子区域尚不存在，则创建它。

3. 在子区域内，编写声明隐藏变量的[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)。

    当子区域内的代码引用变量名时，编译器解析对隐藏变量的引用。

    下面的示例说明了通过范围进行的隐藏，以及跳过隐藏的引用。

    ```vb
    Module shadowByScope
        ' The following statement declares num as a module-level variable.
        Public num As Integer
        Sub show()
            ' The following statement declares num as a local variable.
            Dim num As Integer
            ' The following statement sets the value of the local variable.
            num = 2
            ' The following statement displays the module-level variable.
            MsgBox(CStr(shadowByScope.num))
        End Sub
        Sub useModuleLevelNum()
            ' The following statement sets the value of the module-level variable.
            num = 1
            show()
        End Sub
    End Module
    ```

    前面的示例在模块级和过程级别（在过程 `show`中）声明变量 `num`。 局部变量 `num` 在 `show`内隐藏模块级变量 `num`，因此本地变量设置为2。 但是，在 `useModuleLevelNum` 过程中，不存在用于隐藏 `num` 的本地变量。 因此，`useModuleLevelNum` 将模块级变量的值设置为1。

    `show` 中的 `MsgBox` 调用通过使用模块名称限定 `num`，绕过隐藏机制。 因此，它会显示模块级变量，而不是局部变量。

#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a>通过继承隐藏变量来隐藏变量

1. 确保要隐藏的变量是在类中声明，在类级别（在任何过程之外）声明。 否则，不能通过继承将其隐藏起来。

2. 定义派生自变量的类的类（如果尚不存在）。

3. 在派生类中，编写声明变量的 `Dim` 语句。 在声明中包含[Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)关键字。

    当派生类中的代码引用变量名时，编译器会将对变量的引用解析为。

    下面的示例演示通过继承进行的隐藏。 它创建两个引用，一个用于访问隐藏变量，另一个用于绕过隐藏。

    ```vb
    Public Class shadowBaseClass
        Public shadowString As String = "This is the base class string."
    End Class
    Public Class shadowDerivedClass
        Inherits shadowBaseClass
        Public Shadows shadowString As String = "This is the derived class string."
        Public Sub showStrings()
            Dim s As String = "Unqualified shadowString: " & shadowString &
                 vbCrLf & "MyBase.shadowString: " & MyBase.shadowString
            MsgBox(s)
        End Sub
    End Class
    ```

    前面的示例声明了基类中 `shadowString` 的变量，并在派生类中隐藏了该变量。 派生类中的过程 `showStrings` 在名称 `shadowString` 不限定时显示字符串的隐藏版本。 然后，在用 `MyBase` 关键字限定 `shadowString` 时，它会显示隐藏的版本。

## <a name="robust-programming"></a>可靠的编程

隐藏引入了一个具有相同名称的变量的多个版本。 当代码语句引用变量名时，编译器解析引用的版本取决于一些因素，如代码语句的位置和符合条件的字符串的状态。 这可能会增加引用隐藏变量的意外版本的风险。 您可以通过完全限定对隐藏变量的所有引用来降低风险。

## <a name="see-also"></a>另请参阅

- [对已声明元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Visual Basic 中的阴影](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [隐藏和重写之间的差异](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [如何：隐藏继承的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [如何：访问被派生类隐藏的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [继承的基础知识](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
