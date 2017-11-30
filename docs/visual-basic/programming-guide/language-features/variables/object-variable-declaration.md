---
title: "对象变量声明 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- early binding [Visual Basic]
- declarations [Visual Basic], class
- classes [Visual Basic], declaring
- binding [Visual Basic], late and early
- object variables [Visual Basic], declaring
- variables [Visual Basic], object
- declaring variables [Visual Basic], object variables
- declaring classes [Visual Basic]
- late binding [Visual Basic]
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cdca188d778e9884f918d97eba492a29c64af826
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="object-variable-declaration-visual-basic"></a>对象变量声明 (Visual Basic)
你可以使用正常的声明语句来声明对象变量。 对于数据类型中，你指定`Object`(即， [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)) 或更具体的类是要创建对象。  
  
 声明一个变量，作为`Object`等同于其声明为<xref:System.Object?displayProperty=nameWithType>。  
  
 在声明具有特定对象类的变量时，它可以访问所有方法和属性公开的类和它所继承的类。 如果声明的变量进行<xref:System.Object>，它可以访问的成员<xref:System.Object>类，除非你打开`Option Strict Off`以允许后期绑定。  
  
## <a name="declaration-syntax"></a>声明语法  
 使用以下语法来声明对象变量：  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 你还可以指定[公共](../../../../visual-basic/language-reference/modifiers/public.md)，[受保护](../../../../visual-basic/language-reference/modifiers/protected.md)，[友元](../../../../visual-basic/language-reference/modifiers/friend.md)， `Protected Friend`，[私有](../../../../visual-basic/language-reference/modifiers/private.md)，[共享](../../../../visual-basic/language-reference/modifiers/shared.md)，或[静态](../../../../visual-basic/language-reference/modifiers/static.md)声明中。 下面的示例声明为有效值：  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a>后期绑定和早期绑定  
 有时，你的代码运行时，才，也是未知的特定类。 在这种情况下，您必须声明对象变量`Object`数据类型。 这将创建常规指向任何类型的引用对象，并在运行时分配的特定类。 这称为*后期绑定*。 后期绑定需要更多的执行时间。 它还会限制你的代码的方法和属性的最近已将分配给它的类。 如果你的代码尝试访问不同类的成员，这可能导致运行时错误。  
  
 当在编译时知道特定的类时，应将声明为该类的对象变量。 这称为*早期绑定*。 早期绑定会改进性能，并可保证您对所有的方法和属性的特定类的代码访问权限。 在前面的示例声明中，如果变量`objA`使用仅类的对象<xref:System.Windows.Forms.Label?displayProperty=nameWithType>，应指定`As System.Windows.Forms.Label`其声明中。  
  
### <a name="advantages-of-early-binding"></a>早期绑定的优点  
 声明为特定类的对象变量为你提供几个优点：  
  
-   自动类型检查  
  
-   保证到特定的类的所有成员的访问  
  
-   Microsoft IntelliSense 支持在代码编辑器  
  
-   提高的代码的可读性  
  
-   在代码中减少错误  
  
-   处捕获的错误编译时间而不是运行时  
  
-   代码执行速度更快  
  
## <a name="access-to-object-variable-members"></a>对象变量成员的访问权限  
 当`Option Strict`处于打开状态`On`，仅的方法和属性与其声明的类，可以访问的对象变量。 下面的示例阐释了这一点。  
  
```vb  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 在此示例中， `p` 仅可使用 <xref:System.Object> 类的成员，这不包括 `Left` 属性。 另一方面， `q` 已声明为 <xref:System.Windows.Forms.Label>类型，因此它可以使用 <xref:System.Windows.Forms.Label> 命名空间中 <xref:System.Windows.Forms> 类的所有方法和属性。  
  
## <a name="flexibility-of-object-variables"></a>对象变量的灵活性  
 在使用继承层次结构中的对象，可以用来声明对象变量的类的选择。 在进行选择时，必须综合考虑针对的类成员访问的对象赋值的灵活性。 例如，考虑继承层次结构会导致<xref:System.Windows.Forms.Form?displayProperty=nameWithType>类：  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 假设你的应用程序定义一个名为的窗体类`specialForm`，它继承自类<xref:System.Windows.Forms.Form>。 你可以声明专门引用的对象变量`specialForm`，如下面的示例所示。  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 在前面的示例声明限制变量`nextForm`类的对象到`specialForm`，而且也使所有的方法和属性`specialForm`供`nextForm`，以及从其的所有类的所有成员`specialForm`继承。  
  
 你可以通过声明的类型，才能使对象变量更多常规<xref:System.Windows.Forms.Form>，如下面的示例所示。  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 在前面的示例声明，您可以分配到应用程序中的任何窗体`anyForm`。 但是，尽管`anyForm`可以访问的类的所有成员<xref:System.Windows.Forms.Form>，它不能使用任何其他方法或属性，如为特定窗体定义`specialForm`。  
  
 基类的所有成员都均可用于派生的类，但派生类的其他成员与基的类不可用。  
  
## <a name="see-also"></a>另请参阅  
 [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [对象变量赋值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [对象变量值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [如何： 声明对象变量并在 Visual Basic 中为其分配一个对象](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [如何：访问对象的成员](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)  
 [New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
