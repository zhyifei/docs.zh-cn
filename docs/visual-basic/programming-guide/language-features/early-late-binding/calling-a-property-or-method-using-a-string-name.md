---
title: 使用字符串名调用属性或方法 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- passing operators [Visual Basic]
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls [Visual Basic], strings
- methods [Visual Basic], calling with string names
- calling methods [Visual Basic], string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
ms.openlocfilehash: 76be426049489bb58e50878822c03fa5cd5cca8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>使用字符串名调用属性或方法 (Visual Basic)
在大多数情况下，可以在设计时发现的属性和方法的对象，并编写代码来处理它们。 但是，在某些情况下你可能事先不知道有关对象的属性和方法，或者您可能只想启用最终用户可以指定属性或在运行时执行方法的灵活性。  
  
## <a name="callbyname-function"></a>CallByName 函数  
 例如，考虑通过将运算符传递给 COM 组件的用户输入的表达式的计算结果的客户端应用程序。 假设你要不断地将新的函数添加到需要新的运算符的组件。 当你使用标准的对象访问技术时，你必须重新编译并重新分发客户端应用程序，可以使用新的运算符之前。 若要避免此问题，可以使用`CallByName`函数新的运算符作为字符串来传递，而无需更改应用程序。  
  
 `CallByName`函数，你可以使用一个字符串以在运行时指定的属性或方法。 签名`CallByName`函数如下所示：  
  
 *结果* = `CallByName`(*对象*，*过程名称*， *CallType*，*参数*（)）  
  
 第一个参数，*对象*，将你想要执行操作的对象的名称。 *过程名称*参数接受包含要调用的方法或属性的过程的名称的字符串。 *CallType*参数采用一个常数，用于表示的过程调用的类型： 一种方法 (`Microsoft.VisualBasic.CallType.Method`)，读取的属性 (`Microsoft.VisualBasic.CallType.Get`)，或设置的属性 (`Microsoft.VisualBasic.CallType.Set`)。 *参数*自变量，这是可选的采用的类型数组`Object`包含到过程的任何自变量。  
  
 你可以使用`CallByName`中当前解决方案，但它的类是最常用于访问 COM 对象或对象从[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]程序集。  
  
 假设你添加对该程序集包含一个名为类的引用`MathClass`，它具有一个名为的新函数`SquareRoot`，如下面的代码中所示：  
  
 [!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 你的应用程序可以使用文本框控件对控件将调用哪个方法以及其自变量。 例如，如果`TextBox1`包含要计算的表达式和`TextBox2`是用于输入函数的名称，可以使用下面的代码来调用`SquareRoot`函数中的表达式上`TextBox1`:  
  
 [!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 如果在输入"64"`TextBox1`中的"SquareRoot" `TextBox2`，然后调用`CallMath`过程、 中的数字的平方根`TextBox1`计算。 示例中的代码时，将调用`SquareRoot`函数 （将包含要作为一个必需的参数计算的表达式的字符串），并返回"8"中`TextBox1`（64 的平方根）。 当然，如果用户输入中的无效字符串`TextBox2`，如果字符串包含而不是一种方法，属性的名称，或如果该方法具有一个其他的必需自变量，会发生运行时错误。 你必须添加可靠的错误处理代码，当你使用`CallByName`以应对预期的这些文件路径或任何其他错误。  
  
> [!NOTE]
>  虽然`CallByName`函数可能在某些情况下有用，您必须权衡的性能影响对其用途-使用`CallByName`来调用过程是比后期绑定调用稍慢。 如果正在调用的函数，重复调用，如循环内,`CallByName`会对性能产生严重。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>  
 [确定对象类型](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
