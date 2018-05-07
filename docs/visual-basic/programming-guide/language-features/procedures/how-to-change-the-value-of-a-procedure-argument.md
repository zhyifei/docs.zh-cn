---
title: 如何：更改过程自变量的值 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
ms.openlocfilehash: 118dd3389804794801d39e7d67b68ab195bbad3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>如何：更改过程自变量的值 (Visual Basic)
当调用过程时，你提供每个自变量对应于在过程中定义的参数之一。 在某些情况下，该过程代码可以更改基础中调用代码的自变量的值。 在其他情况下，该过程只可以更改其本地副本的自变量。  
  
 Visual Basic 在调用过程时，使每个自变量传递的本地副本[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)。 对于每个自变量传递[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，Visual Basic 使该过程代码中调用代码的实参的编程元素直接引用。  
  
 如果调用代码中的基础元素是可修改的元素，并传递自变量`ByRef`，过程代码可以使用的直接引用来更改调用代码中的元素的值。  
  
## <a name="changing-the-underlying-value"></a>更改基础值  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>若要更改过程自变量调用的代码中的基础值  
  
1.  在过程声明中，指定[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)对应于参数的参数。  
  
2.  在调用代码中，将作为参数传递的可修改的编程元素。  
  
3.  在调用代码中，不要将括在参数列表中的括号中的自变量。  
  
4.  在过程代码中，使用参数名称分配给调用代码中的基础元素的值。  
  
 请参阅示例进一步向下的演示。  
  
## <a name="changing-local-copies"></a>更改本地副本  
 如果调用代码中的基础元素是不可修改的元素，或者如果传递参数`ByVal`，过程将无法更改其调用的代码中的值。 但是，该过程可以更改其本地副本的这类参数。  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>若要更改在过程代码中的过程自变量的副本  
  
1.  在过程声明中，指定[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)对应于参数的参数。  
  
     -或-  
  
     在调用代码中，将括在参数列表中的括号中的自变量。 这将强制 Visual Basic 能够按值传递自变量，即使相应的参数指定`ByRef`。  
  
2.  在过程代码中，使用参数名称的自变量的本地副本分配一个值。 调用代码中的基础值不会更改。  
  
## <a name="example"></a>示例  
 下面的示例演示对其元素的两个过程可采用一个数组变量并运行。 `increase`过程只需添加一个对每个元素。 `replace`过程将一个新数组分配给参数`a()`，然后添加一个用于每个元素。  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 第一个`MsgBox`调用显示"后 increase(n): 11、 21、 31、 41"。 因为数组`n`是引用类型，`replace`可以更改的成员，即使的传递机制`ByVal`。  
  
 第二个`MsgBox`调用显示"后 replace(n): 101、 201、 301"。 因为`n`传递`ByRef`，`replace`可以修改变量`n`中调用代码并将赋给它的新数组。 因为`n`是引用类型，`replace`还可以更改其成员。  
  
 你可以修改调用代码中的变量本身阻止过程。 请参阅[如何： 防止过程自变量的值更改](./how-to-protect-a-procedure-argument-against-value-changes.md)。  
  
## <a name="compiling-the-code"></a>编译代码  
 当通过引用传递的变量时，你必须使用`ByRef`关键字来指定此机制。  
  
 Visual Basic 中的默认值是通过值传递自变量。 但是，很好的编程做法包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字后跟每个声明的参数。 这使得你的代码易于阅读。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 允许一个过程来更改基础中调用代码的自变量的值始终没有潜在风险。 请确保您希望此值可更改，并做好准备，然后再使用它的有效性检查它。  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [如何：将自变量传递给过程](./how-to-pass-arguments-to-a-procedure.md)  
 [按值和按引用传递自变量](./passing-arguments-by-value-and-by-reference.md)  
 [可修改和不可修改自变量之间的差异](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [通过值传递自变量和通过引用传递自变量之间的差异](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [如何：防止过程自变量的值被更改](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [如何：强制通过值传递自变量](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [按位置和按名称传递自变量](./passing-arguments-by-position-and-by-name.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
