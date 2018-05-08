---
title: Visual Basic 中的隐藏
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], shadowing
- overriding, and shadowing
- shadowing
- duplicate names [Visual Basic]
- shadowing, by inheritance
- declared elements [Visual Basic], referencing
- shadowing, by scope
- declared elements [Visual Basic], hiding
- naming conflicts, shadowing
- declared elements [Visual Basic], shadowing
- shadowing, and overriding
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic], about
- objects [Visual Basic], names
- names [Visual Basic], shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
ms.openlocfilehash: fde6259b67a8d963ed8c30b87c94029fb2658664
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="shadowing-in-visual-basic"></a>Visual Basic 中的隐藏
当两个编程元素共享相同的名称时，可以隐藏其中一个，或*卷影*，另一个。 在这种情况下，隐藏的元素也无法供引用;相反，当你的代码使用的元素名称时，Visual Basic 编译器将其解析为隐藏的元素。  
  
## <a name="purpose"></a>目标  
 隐藏的主要目的是保护类成员的定义。 基类可能会经历创建具有与一个已定义同名的元素的更改。 如果发生这种情况，`Shadows`修饰符强制就会通过引用您的类将解析为成员你定义，而不是到新的基类元素。  
  
## <a name="types-of-shadowing"></a>隐藏类型  
 元素可以两种不同方式隐藏另一个元素。 隐藏的元素可以声明包含隐藏的元素，在这种情况下隐藏来完成的区域的子区域内*通过作用域*。 派生类可以重新定义的基类，这种情况下隐藏来完成成员或者*通过继承*。  
  
### <a name="shadowing-through-scope"></a>通过范围进行隐藏  
 很可能导致编程中相同的模块、 类或结构具有相同名称但不同的范围内的元素。 范围较窄的元素后，在这种方式中，声明了两个元素的代码引用它们共享的名称，隐藏的其他元素 （块作用域是范围最小）。  
  
 例如，可以定义模块`Public`变量名为`temp`，该模块内的一个过程可以声明一个也名为的本地变量`temp`。 引用`temp`内过程访问局部变量，而对引用`temp`从外部过程访问`Public`变量。 在此情况下，过程变量`temp`隐藏模块变量`temp`。  
  
 下图显示了两个变量、 命名`temp`。 本地变量`temp`隐藏了成员变量`temp`时从其自己的过程内访问`p`。 但是，`MyClass`关键字绕开隐藏和访问的成员变量。  
  
 ![通过范围进行隐藏示意图](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")  
通过范围进行隐藏  
  
 通过范围进行隐藏的示例，请参阅[如何： 隐藏与您变量同名的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)。  
  
### <a name="shadowing-through-inheritance"></a>通过继承进行隐藏  
 如果派生的类重新定义了一个编程元素，该元素从基类继承，重定义的元素将隐藏的原始元素。 你可以与任何其他类型一起隐藏任何类型的声明的元素或重载元素集。 例如，`Integer`变量可以隐藏`Function`过程。 如果你隐藏与另一个过程的过程，你可以使用不同的参数列表和其他的返回类型。  
  
 下图显示了基类`b`和派生的类`d`继承自`b`。 该基类定义名为的过程`proc`，然后用相同名称的另一个过程的派生的类隐藏它。 第一个`Call`语句访问该隐藏`proc`派生类中。 但是，`MyBase`关键字绕开隐藏和访问基类中隐藏的过程。  
  
 ![通过继承进行隐藏示意图](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")  
通过继承进行隐藏  
  
 通过继承进行隐藏的示例，请参阅[如何： 隐藏与您变量同名的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)和[如何： 隐藏继承变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)。  
  
#### <a name="shadowing-and-access-level"></a>隐藏和访问级别  
 隐藏元素并不总是可以从使用派生的类的代码访问。 例如，可能会声明`Private`。 在这种情况下，隐藏是失效，则编译器将解析对则必须在同一元素的任何引用如果没有过没有隐藏。 此元素是最少派生自隐藏类向后步骤的可访问元素。 如果隐藏的元素是一个过程，解决方法是到最接近的可访问版本具有相同的名称，参数列表和返回类型。  
  
 下面的示例演示三个类的继承层次结构。 每个类定义`Sub`过程`display`，并且每个派生类阴影`display`其基类中的过程。  
  
```  
Public Class firstClass  
    Public Sub display()  
        MsgBox("This is firstClass")  
    End Sub  
End Class  
Public Class secondClass  
    Inherits firstClass  
    Private Shadows Sub display()  
        MsgBox("This is secondClass")  
    End Sub  
End Class  
Public Class thirdClass  
    Inherits secondClass  
    Public Shadows Sub display()  
        MsgBox("This is thirdClass")  
    End Sub  
End Class  
Module callDisplay  
    Dim first As New firstClass  
    Dim second As New secondClass  
    Dim third As New thirdClass  
    Public Sub callDisplayProcedures()  
        ' The following statement displays "This is firstClass".  
        first.display()  
        ' The following statement displays "This is firstClass".  
        second.display()  
        ' The following statement displays "This is thirdClass".  
        third.display()  
    End Sub  
End Module  
```  
  
 在前面的示例中，派生类`secondClass`阴影`display`与`Private`过程。 当模块`callDisplay`调用`display`中`secondClass`，调用代码是外部`secondClass`，因此不能访问私有`display`过程。 隐藏失败，并且编译器将解析对基类的引用`display`过程。  
  
 但是，进一步派生类`thirdClass`声明`display`作为`Public`，因此中的代码`callDisplay`可以访问它。  
  
## <a name="shadowing-and-overriding"></a>隐藏和重写  
 不要混淆隐藏和重写。 在派生的类继承自基类，并同时重新定义与另一个声明的元素时，将使用它们。 但是，这两者之间的重大差异。 比较，请参阅[差异之间隐藏和重写](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)。  
  
## <a name="shadowing-and-overloading"></a>隐藏和重载  
 如果你在派生类中隐藏了多个元素具有的相同基类元素，隐藏的元素将变为该元素的重载的版本。 有关详细信息，请参阅[过程重载](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)。  
  
## <a name="accessing-a-shadowed-element"></a>访问隐藏的元素  
 当你从派生类访问的元素时，你通常要通过该派生类的当前实例限定元素名称与`Me`关键字。 如果派生的类隐藏基类中的元素，则可以通过限定其与访问基类元素`MyBase`关键字。  
  
 访问隐藏的元素的示例，请参阅[如何： 访问被派生类变量隐藏](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)。  
  
### <a name="declaration-of-the-object-variable"></a>对象变量的声明  
 如何创建对象变量还会影响是否派生的类访问隐藏的元素或隐藏的元素。 下面的示例创建两个对象从派生类，但一个对象被声明为类的基类和派生类作为其他。  
  
```  
Public Class baseCls  
    ' The following statement declares the element that is to be shadowed.  
    Public z As Integer = 100  
End Class  
Public Class dervCls  
    Inherits baseCls  
    ' The following statement declares the shadowing element.  
    Public Shadows z As String = "*"  
End Class  
Public Class useClasses  
    ' The following statement creates the object declared as the base class.  
    Dim basObj As baseCls = New dervCls()  
    ' Note that dervCls widens to its base class baseCls.  
    ' The following statement creates the object declared as the derived class.  
    Dim derObj As dervCls = New dervCls()  
    Public Sub showZ()   
    ' The following statement outputs 100 (the shadowed element).  
        MsgBox("Accessed through base class: " & basObj.z)  
    ' The following statement outputs "*" (the shadowing element).  
        MsgBox("Accessed through derived class: " & derObj.z)  
    End Sub  
End Class  
```  
  
 在前面的示例中，变量`basObj`声明为类的基类。 分配`dervCls`构成一个的扩大转换，因此有效到它的对象。 但是，基类不能访问该变量的隐藏版本`z`在派生类中，因此编译器将解析`basObj.z`到原始的基类值。  
  
## <a name="see-also"></a>请参阅  
 [对已声明元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [继承的基础知识](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
