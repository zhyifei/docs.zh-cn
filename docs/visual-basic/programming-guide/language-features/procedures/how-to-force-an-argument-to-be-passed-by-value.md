---
title: 如何：强制通过值传递自变量 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: adc58c34150030eb0fc82050576bfecc453e21ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651072"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>如何：强制通过值传递自变量 (Visual Basic)
过程声明确定的传递机制。 如果在声明参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，Visual Basic 期望通过引用传递相应的自变量。 这允许更改基础中调用代码的自变量的编程元素的值的过程。 如果你想要防止此类更改基础元素，则可以重写`ByRef`过程中的传递机制调用的自变量名称括在括号中。 除了括号之外的自变量列表的调用中，则这些括号。  
  
 调用的代码不能重写[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)机制。  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>若要强制通过值传递自变量  
  
-   如果声明的相应参数`ByVal`在过程中，不需要执行任何其他步骤。 Visual Basic 已希望按值传递自变量。  
  
-   如果声明的相应参数`ByRef`在过程中，将括在过程调用中的括号中的自变量。  
  
## <a name="example"></a>示例  
 下面的示例重写`ByRef`参数声明。 强制的调用中`ByVal`，请注意两个级别的括号。  
  
 [!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 当`str`用自变量列表中的额外括号括起来`setNewString`过程不能更改在调用代码中，其值和`MsgBox`显示"无法替换如果传递 ByVal"。 当`str`不括在额外的括号内，则过程可以更改它，和`MsgBox`显示"This is inString 参数的一个新值"。  
  
## <a name="compiling-the-code"></a>编译代码  
 当通过引用传递的变量时，你必须使用`ByRef`关键字来指定此机制。  
  
 Visual Basic 中的默认值是通过值传递自变量。 但是，很好的编程做法包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字后跟每个声明的参数。 这使得你的代码易于阅读。  
  
## <a name="robust-programming"></a>可靠编程  
 如果过程声明参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，正确的执行代码的可能依赖于能够更改中调用代码的基础元素。 如果调用代码重写此调用的机制，通过将实参括在括号内，或者如果它通过不可修改自变量，该过程不能更改基础元素。 这可能会产生意外的结果，调用代码中。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 允许一个过程来更改基础中调用代码的自变量的值始终没有潜在风险。 请确保您希望此值可更改，并做好准备，然后再使用它的有效性检查它。  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [如何：将自变量传递给过程](./how-to-pass-arguments-to-a-procedure.md)  
 [按值和按引用传递自变量](./passing-arguments-by-value-and-by-reference.md)  
 [可修改和不可修改自变量之间的差异](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [通过值传递自变量和通过引用传递自变量之间的差异](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [如何：更改过程自变量的值](./how-to-change-the-value-of-a-procedure-argument.md)  
 [如何：防止过程自变量的值被更改](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [按位置和按名称传递自变量](./passing-arguments-by-position-and-by-name.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
