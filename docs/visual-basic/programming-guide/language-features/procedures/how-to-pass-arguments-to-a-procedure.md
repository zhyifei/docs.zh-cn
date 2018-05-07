---
title: 如何：将自变量传递给过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
ms.openlocfilehash: f393f17f87c5920fb9bfa2a2097c09d48bebdc16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>如何：将自变量传递给过程 (Visual Basic)
当调用过程时，过程名后面加上括号中的参数列表。 你提供参数对应于每个所需的参数为过程所定义，并且 （可选） 可以提供自变量`Optional`参数。 如果未提供`Optional`调用中的参数，必须包含逗号来标记其位置自变量列表中的，如果你所提供的任何后续自变量。  
  
 如果你想要的自变量传递的数据类型不同于其对应的参数，如`Byte`到`String`，你可以设置类型检查开关 ([Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 到`Off`。 如果`Option Strict`是`On`，则必须使用扩大转换或显式转换关键字。 有关详细信息，请参阅[扩大和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)和[类型转换函数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)。  
  
 有关详细信息，请参阅[过程参数和自变量](./procedure-parameters-and-arguments.md)。  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>将一个或多个自变量传递给过程  
  
1.  在调用语句中，过程名后面加上括号。  
  
2.  在括号内，将自变量列表。 包括每个所需的参数的自变量为过程所定义，并且用逗号分隔参数。  
  
3.  请确保每个自变量是一个有效表达式，计算结果为一个数据类型可转换为类型过程定义的相应参数。  
  
4.  如果参数定义为[可选](../../../../visual-basic/language-reference/modifiers/optional.md)，您可以将其包含自变量列表中，也可以省略此参数。 如果省略此元素时，过程将使用为该参数定义的默认值。  
  
5.  如果省略的自变量`Optional`参数并且有另一个参数之后在参数列表中，可以将省略的自变量的位置标记的参数列表中的额外逗号。  
  
     下面的示例调用 Visual Basic<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>函数。  
  
     [!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     前面的示例提供了所需的第一个参数，这是要显示的消息字符串。 它省略了可选的第二个参数，它指定要在消息框上显示的按钮的自变量。 调用未提供一个值，因为`MsgBox`使用默认值， `MsgBoxStyle.OKOnly`，这将仅显示**确定**按钮。  
  
     在自变量列表中的第二个逗号将标记的位置省略第二个参数，并且最后一个的字符串传递给的可选第三个参数`MsgBox`，即在标题栏中显示的文本。  
  
## <a name="see-also"></a>请参阅

 [Sub 过程](./sub-procedures.md)  
 [Function 过程](./function-procedures.md)  
 [属性过程](./property-procedures.md)  
 [运算符过程](./operator-procedures.md)  
 [如何：为过程定义参数](./how-to-define-a-parameter-for-a-procedure.md)  
 [按值和按引用传递自变量](./passing-arguments-by-value-and-by-reference.md)  
 [递归过程](./recursive-procedures.md)  
 [过程重载](./procedure-overloading.md)  
 [对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [面向对象的编程 (Visual Basic)](../../concepts/object-oriented-programming.md)  
