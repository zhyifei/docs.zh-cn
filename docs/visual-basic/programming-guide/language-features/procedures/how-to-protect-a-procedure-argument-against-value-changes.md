---
title: 如何：防止过程自变量的值被更改 (Visual Basic)
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
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
ms.openlocfilehash: d2e131b770d8498a634d946a5900f9b373ca7e56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>如何：防止过程自变量的值被更改 (Visual Basic)
如果过程声明将参数作为[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，Visual Basic 使该过程代码中调用代码的实参的编程元素直接引用。 这允许更改基础中调用代码的自变量的值的过程。 在某些情况下调用的代码可能想要防止此类更改。  
  
 你可以始终保护自变量不被更改通过声明的相应参数[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)过程中。 如果你想要能够更改在某些情况下，而不是其他给定的自变量，可以将其声明`ByRef`并让调用代码确定在每次调用的传递机制。 此，它会将相应实参括在括号中以将其传递的值，或不将其括起来在括号中以通过引用传递。 有关详细信息，请参阅[如何： 强制通过值传递到自变量](./how-to-force-an-argument-to-be-passed-by-value.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示对其元素的两个过程可采用一个数组变量并运行。 `increase`过程只需添加一个对每个元素。 `replace`过程将一个新数组分配给参数`a()`，然后添加一个用于每个元素。 但是，重新分配不会影响调用代码中的基础数组变量。  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]  
  
 第一个`MsgBox`调用显示"后 increase(n): 11、 21、 31、 41"。 因为数组`n`是引用类型，`replace`可以更改的成员，即使的传递机制`ByVal`。  
  
 第二个`MsgBox`调用显示"后 replace(n): 11、 21、 31、 41"。 因为`n`传递`ByVal`，`replace`不能修改变量`n`通过向它分配一个新数组，调用代码中。 当`replace`创建新的数组实例`k`并将其分配到本地变量`a`，它将失去对引用`n`传递中调用代码。 当其更改的成员`a`，只有本地数组`k`受到影响。 因此，`replace`不会增加的数组值`n`调用代码中。  
  
## <a name="compiling-the-code"></a>编译代码  
 Visual Basic 中的默认值是通过值传递自变量。 但是，很好的编程做法包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字后跟每个声明的参数。 这使得你的代码易于阅读。  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [如何：将自变量传递给过程](./how-to-pass-arguments-to-a-procedure.md)  
 [按值和按引用传递自变量](./passing-arguments-by-value-and-by-reference.md)  
 [可修改和不可修改自变量之间的差异](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [通过值传递自变量和通过引用传递自变量之间的差异](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [如何：更改过程自变量的值](./how-to-change-the-value-of-a-procedure-argument.md)  
 [如何：强制通过值传递自变量](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [按位置和按名称传递自变量](./passing-arguments-by-position-and-by-name.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
