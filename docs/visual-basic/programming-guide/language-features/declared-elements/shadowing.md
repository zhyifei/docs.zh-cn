---
title: 阴影操作
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
ms.openlocfilehash: 20a33478f622fca6d3183772f53dcb3e72f79409
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266880"
---
# <a name="shadowing-in-visual-basic"></a>Visual Basic 中的隐藏
当两个编程元素共享相同的名称时，其中一个元素可以隐藏或*隐藏*另一个。 在这种情况下，阴影元素不能供参考;相反，当代码使用元素名称时，Visual Basic 编译器会将其解析为隐藏元素。  
  
## <a name="purpose"></a>目的  
 阴影的主要目的是保护类成员的定义。 基类可能会经历一个更改，该更改创建与已定义的元素同名的元素。 如果发生这种情况，`Shadows`修改器将强制通过类的引用解析为您定义的成员，而不是新的基类元素。  
  
## <a name="types-of-shadowing"></a>阴影类型  
 元素可以通过两种不同的方式隐藏另一个元素。 阴影元素可以在包含阴影元素的区域的次区域内声明，在这种情况下，阴影*是通过作用域*完成的。 或者派生类可以重新定义基类的成员，在这种情况下，阴影*是通过继承*来完成的。  
  
### <a name="shadowing-through-scope"></a>阴影范围  
 同一模块、类或结构中的编程元素可以具有相同的名称但范围不同。 以这种方式声明两个元素并且代码引用它们共享的名称时，具有较窄范围的元素会阴影另一个元素（块作用域是最窄的）。  
  
 例如，模块可以定义名为 的`Public``temp`变量，模块中的过程可以声明也命名为 的`temp`局部变量。 从过程`temp`内部对的引用访问局部变量，而从过程外部`temp`的引用访问`Public`该变量。 在这种情况下，过程变量`temp`对模块变量`temp`进行阴影。  
  
 下图显示了两个变量，这两个变量`temp`都命名为 。 当从其`temp`自己的过程中`p`访问成员`temp`变量时，局部变量将隐藏成员变量。 但是，`MyClass`关键字绕过阴影并访问成员变量。  
  
 ![显示阴影范围的图形。](./media/shadowing/shadow-scope-diagram.gif)
  
 有关在作用域中隐藏的示例，请参阅[如何：隐藏与变量同名的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)。  
  
### <a name="shadowing-through-inheritance"></a>通过继承进行阴影  
 如果派生类重新定义从基类继承的编程元素，则重新定义元素将隐藏原始元素。 可以使用任何其他类型隐藏任何类型的声明元素或一组重载元素。 例如，`Integer`变量可以隐藏`Function`过程。 如果使用另一个过程对过程进行阴影，则可以使用不同的参数列表和不同的返回类型。  
  
 下图显示了从`b``b`继承的基类和派生类`d`。 基类定义名为 的过程`proc`，派生类使用另一个同名过程来隐藏它。 第一`Call`个语句访问派生类中的`proc`阴影。 但是，`MyBase`关键字绕过阴影并访问基类中的隐藏过程。  
  
 ![通过继承进行隐藏示意图](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 有关通过继承进行阴影的示例，请参阅[如何：隐藏与变量同名的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)以及如何[：隐藏继承变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)。  
  
#### <a name="shadowing-and-access-level"></a>阴影和访问级别  
 使用派生类的代码并不总是可以访问阴影元素。 例如，它可能声明`Private`。 在这种情况下，阴影将失败，编译器解析对如果没有阴影时的相同元素的任何引用。 此元素是从阴影类向后派生最少的可访问元素。 如果隐藏元素是过程，则分辨率是最接近的可访问版本，具有相同的名称、参数列表和返回类型。  
  
 下面的示例显示了三个类的继承层次结构。 每个类定义一个`Sub`过程`display`，每个派生类在其基类`display`中隐藏该过程。  
  
```vb  
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
  
 在前面的示例中，派生类`secondClass`阴影`display`带有一个`Private`过程。 当模块`callDisplay`调用`display``secondClass`时，调用代码位于外部`secondClass`，因此无法访问私有`display`过程。 隐藏将失败，编译器解析对基类`display`过程的引用。  
  
 但是，进一步的派生`thirdClass`类声明`display`为`Public`，因此 中`callDisplay`的代码可以访问它。  
  
## <a name="shadowing-and-overriding"></a>阴影和覆盖  
 不要混淆阴影和重写。 当派生类从基类继承时，两者都使用，并且都与另一个类重新定义一个声明的元素。 但两者之间存在显著差异。 有关比较，请参阅[阴影和覆盖之间的差异](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)。  
  
## <a name="shadowing-and-overloading"></a>阴影和重载  
 如果对派生类中具有多个元素的同一基类元素进行阴影，则阴影元素将成为该元素的重载版本。 有关更多信息，请参见 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)。  
  
## <a name="accessing-a-shadowed-element"></a>访问隐藏元素  
 当您从派生类访问元素时，通常通过派生类的当前实例，通过`Me`用 关键字限定元素名称来执行此操作。 如果派生类对基类中的元素造成阴影，则可以通过使用`MyBase`关键字限定基类元素来访问该元素元素。  
  
 有关访问隐藏元素的示例，请参阅[如何：访问派生类隐藏的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)。  
  
### <a name="declaration-of-the-object-variable"></a>对象变量的声明  
 创建对象变量的方式还可以影响派生类是访问阴影元素还是隐影元素。 下面的示例从派生类创建两个对象，但一个对象声明为基类，另一个对象声明为派生类。  
  
```vb  
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
  
 在前面的示例中，变量`basObj`声明为基类。 向其分配`dervCls`对象构成扩大转换，因此有效。 但是，基类无法访问派生类中变量`z`的隐藏版本，因此编译器解析`basObj.z`为原始基类值。  
  
## <a name="see-also"></a>另请参阅

- [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Visual Basic 中的范围](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [重写](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [继承的基础知识](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
