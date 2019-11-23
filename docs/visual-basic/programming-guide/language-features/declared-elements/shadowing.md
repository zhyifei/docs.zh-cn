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
ms.openlocfilehash: 30c02cf367c461c3896a01538d03380627de294f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004865"
---
# <a name="shadowing-in-visual-basic"></a>Visual Basic 中的隐藏
当两个编程元素共享同一名称时，其中一个元素可以*隐藏或隐藏*另一个。 在这种情况下，隐藏的元素不可用于引用;相反，当你的代码使用元素名称时，Visual Basic 编译器会将其解析为隐藏元素。  
  
## <a name="purpose"></a>目的  
 隐藏的主要目的是保护类成员的定义。 基类可能会发生更改，该更改将创建一个与已定义的元素同名的元素。 如果发生这种情况，则 `Shadows` 修饰符强制将通过类的引用解析为你定义的成员，而不是新的基类元素。  
  
## <a name="types-of-shadowing"></a>隐藏类型  
 元素可通过两种不同的方式隐藏其他元素。 可以在包含隐藏元素的区域的子区域内声明隐藏元素，在这种情况下，隐藏是*通过范围*实现的。 或派生类可以重新定义基类的成员，在这种情况下，将*通过继承*来完成隐藏。  
  
### <a name="shadowing-through-scope"></a>通过范围隐藏  
 同一模块、类或结构中的编程元素可以具有相同的名称，但范围不同。 如果以这种方式声明了两个元素，而代码引用了它们共享的名称，则范围较窄的元素将隐藏另一个元素（块范围是最窄的）。  
  
 例如，模块可以定义一个名为 `temp`的 `Public` 变量，并且该模块中的一个过程可以声明同样名为 `temp`的局部变量。 在过程中对 `temp` 的引用将访问本地变量，而从外部对 `temp` 的引用将访问 `Public` 变量。 在这种情况下，过程变量 `temp` 隐藏模块变量 `temp`。  
  
 下图显示了两个变量，两者都命名 `temp`。 本地变量 `temp` 在从其自己的过程 `p`内访问成员变量 `temp`。 但 `MyClass` 关键字会绕过隐藏并访问成员变量。  
  
 ![显示通过范围隐藏的图形。](./media/shadowing/shadow-scope-diagram.gif)
  
 有关通过范围进行隐藏的示例，请参阅[如何：隐藏与您的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)同名的变量。  
  
### <a name="shadowing-through-inheritance"></a>通过继承隐藏  
 如果派生类重定义了从基类继承的编程元素，则重定义元素将隐藏原始元素。 可以用任何其他类型隐藏任何类型的已声明元素或重载元素集。 例如，`Integer` 变量可以隐藏 `Function` 过程。 如果使用另一个过程来隐藏过程，则可以使用不同的参数列表和不同的返回类型。  
  
 下图显示了一个基类 `b` 和从 `b`继承的派生类 `d`。 基类定义了一个名为 `proc`的过程，派生类将使用另一个同名的过程来隐藏该过程。 第一个 `Call` 语句访问派生类中的隐藏 `proc`。 但 `MyBase` 关键字会绕过隐藏并访问基类中的隐藏过程。  
  
 ![通过继承进行隐藏示意图](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 有关通过继承进行隐藏的示例，请参阅[如何：隐藏与您的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)同名的变量和[如何：隐藏继承的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)。  
  
#### <a name="shadowing-and-access-level"></a>隐藏和访问级别  
 不能始终使用派生类从代码访问隐藏元素。 例如，它可能已 `Private`声明。 在这种情况下，隐藏会失效，如果没有隐藏，编译器将解析对同一元素的任何引用。 此元素是可访问的元素，它是从隐藏类向后 derivational 的最少步骤。 如果隐藏的元素是一个过程，则将其解析为具有相同名称、参数列表和返回类型的最接近的可访问版本。  
  
 下面的示例显示了三个类的继承层次结构。 每个类都定义一个 `Sub` 过程 `display`，每个派生类都会在其基类中隐藏 `display` 过程。  
  
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
  
 在前面的示例中，派生类 `secondClass` 与 `Private` 过程 `display` 阴影。 当模块 `callDisplay` 在 `secondClass`调用 `display` 时，调用代码在 `secondClass` 外部，因此无法访问私有 `display` 过程。 隐藏会失效，编译器会将对基类的引用解析 `display` 过程中。  
  
 但是，更进一步的派生类 `thirdClass` 将 `display` 声明为 `Public`，因此 `callDisplay` 中的代码可以访问它。  
  
## <a name="shadowing-and-overriding"></a>隐藏和重写  
 不要将隐藏与重写混淆。 当派生类从基类继承时，同时使用这两种方法，并将一个声明的元素重定义为另一个。 但两者之间存在重大差异。 有关比较，请参阅[隐藏和重写之间的差异](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)。  
  
## <a name="shadowing-and-overloading"></a>隐藏和重载  
 如果在派生类中隐藏具有多个元素的同一个基类元素，则隐藏元素将成为该元素的重载版本。 有关更多信息，请参见 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)。  
  
## <a name="accessing-a-shadowed-element"></a>访问隐藏的元素  
 从派生类访问某个元素时，通常通过该派生类的当前实例执行此操作，方法是使用 `Me` 关键字限定元素名称。 如果派生类隐藏了基类中的元素，则可以通过使用 `MyBase` 关键字来限定它来访问基类元素。  
  
 有关访问隐藏的元素的示例，请参阅[如何：访问由派生类隐藏的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)。  
  
### <a name="declaration-of-the-object-variable"></a>对象变量的声明  
 创建对象变量的方式还会影响派生类是访问隐藏元素还是访问隐藏的元素。 下面的示例从派生类创建两个对象，但一个对象声明为基类，另一个对象作为派生类。  
  
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
  
 在前面的示例中，变量 `basObj` 声明为基类。 将 `dervCls` 对象分配给它构成了扩大转换，因此是有效的。 但是，基类无法访问派生类中的变量 `z` 的隐藏版本，因此编译器会将 `basObj.z` 解析为原始基类值。  
  
## <a name="see-also"></a>另请参阅

- [对已声明元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [范围 Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [继承的基础知识](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
