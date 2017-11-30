---
title: "如何：隐藏与您的变量同名的变量 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af031f3ef134b2a509922e6ada28aa5b2b80d641
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a>如何：隐藏与您的变量同名的变量 (Visual Basic)
可以隐藏由变量*隐藏*也就是说，它通过将它重新定义具有相同名称的变量。 你可以隐藏你想要在两种方式中隐藏的变量：  
  
-   **通过范围进行隐藏。** 你可以通过范围隐藏隐藏包含你想要隐藏的变量的区域的子区域内。  
  
-   **通过继承进行隐藏。** 如果你想要隐藏的变量在类级别定义的可以隐藏它通过继承隐藏其与[阴影](../../../../visual-basic/language-reference/modifiers/shadows.md)派生类中的关键字。  
  
## <a name="two-ways-to-hide-a-variable"></a>两种方法来隐藏的变量  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a>若要隐藏变量通过范围进行隐藏  
  
1.  确定定义你想要隐藏，的变量的区域，并确定要对其重新定义与你的变量在其中一个子区域。  
  
    |变量的区域|为重新定义它的允许子区域|  
    |-----------------------|-------------------------------------------|  
    |模块|该模块中的类|  
    |类|中的类的子类<br /><br /> 一个类中的过程|  
  
     不能例如重新在该过程中，块中的过程变量定义在`If`...`End If`构造或`For`循环。  
  
2.  如果不存在，请创建子区域。  
  
3.  在子区域内，编写[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)声明隐藏的变量。  
  
     当子区域内的代码引用的变量的名称时，编译器将解析对隐藏的变量的引用。  
  
     下面的示例演示通过作用域，以及绕开隐藏的引用进行隐藏。  
  
    ```  
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
  
     前面的示例声明了变量`num`在模块级别和过程级别 (在过程中`show`)。 本地变量`num`隐藏模块级变量`num`内`show`，因此本地变量设置为 2。 但是，没有任何局部变量为卷影`num`中`useModuleLevelNum`过程。 因此，`useModuleLevelNum`模块级变量的值设置为 1。  
  
     `MsgBox`内调用`show`隐藏机制将绕过通过限定`num`使用模块名称。 因此，它显示模块级变量，而不是本地的变量。  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a>若要通过隐藏通过继承隐藏的变量  
  
1.  请确保你想要隐藏的变量声明在类中，并在类级别 （之外任何过程）。 否则不能通过继承隐藏它。  
  
2.  定义派生自变量的类，如果尚不存在的类。  
  
3.  在派生类中，编写`Dim`语句声明您的变量。 包括[阴影](../../../../visual-basic/language-reference/modifiers/shadows.md)声明中的关键字。  
  
     当在派生类中的代码引用的变量的名称时，编译器将解析对你的变量的引用。  
  
     下面的示例演示通过继承进行隐藏。 它使两个引用，一个访问隐藏的变量，一个绕开隐藏。  
  
    ```  
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
  
     前面的示例声明了变量`shadowString`中的基类和派生类中隐藏它。 该过程`showStrings`派生类中显示隐藏版本的字符串时名称`shadowString`未限定。 然后，它显示隐藏的版本时`shadowString`是用限定`MyBase`关键字。  
  
## <a name="robust-programming"></a>可靠编程  
 隐藏引入了多个版本具有相同名称的变量。 当代码语句引用的变量的名称时，编译器将该引用解析的版本取决于因素，如代码语句的位置和限定字符串的状态。 这会增加引用隐藏的变量的非预期版本的风险。 你可以通过完全限定到隐藏的变量的所有引用来降低该风险。  
  
## <a name="see-also"></a>另请参阅  
 [对已声明元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [在 Visual Basic 中隐藏](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [隐藏和重写之间的差异](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [如何：隐藏继承的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [如何：访问被派生类隐藏的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [继承的基础知识](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
