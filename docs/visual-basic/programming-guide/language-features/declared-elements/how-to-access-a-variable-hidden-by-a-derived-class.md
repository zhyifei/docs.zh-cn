---
title: 如何：访问被派生类隐藏的变量 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 8dd59dff5b8123331237db905432bbb4e94d62ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648042"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>如何：访问被派生类隐藏的变量 (Visual Basic)
当在派生类中的代码访问的变量时，编译器通常将到最接近的可访问版本，即的可访问版本引用解析派生步骤最少向后从访问的类。 如果变量在派生类中定义的则代码通常会访问该定义。  
  
 如果派生的类变量隐藏基类中的变量，它会隐藏基类版本。 但是，可以通过限定其与访问基类变量`MyBase`关键字。  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>若要访问由派生类隐藏的基类变量  
  
-   在表达式或赋值语句中，变量名称前面加`MyBase`关键字和一个句点 (`.`)。  
  
     编译器将解析对变量的基类版本的引用。  
  
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
 要降低引用隐藏的变量的非预期版本的风险，则可以完全限定到隐藏的变量的所有引用。 隐藏引入了多个版本具有相同名称的变量。 当代码语句引用的变量的名称时，编译器将该引用解析的版本取决于因素，如代码语句的位置和限定字符串的状态。 这会增加到了错误版本的该变量引用的风险。  
  
## <a name="see-also"></a>请参阅  
 [对已声明元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [在 Visual Basic 中隐藏](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [隐藏和重写之间的差异](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [如何：隐藏与你的变量同名的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [如何：隐藏继承的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [继承的基础知识](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
