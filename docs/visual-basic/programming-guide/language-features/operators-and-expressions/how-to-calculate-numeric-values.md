---
title: 如何：计算数值 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: cf24d7259ac04f6901497c81558a4d59b340eec7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>如何：计算数值 (Visual Basic)
您可以计算通过数值表达式使用的数字值。 A*数值表达式*会包含文本、 常量和变量表示数字值的表达式并处理这些值的运算符。  
  
## <a name="calculating-numeric-values"></a>计算数值  
  
#### <a name="to-calculate-a-numeric-value"></a>若要计算的数字值  
  
-   将一个或多个数值的文本、 常量和变量组合到一个数值表达式。 下面的示例显示了一些有效的数值表达式。  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     前三个行显示文本、 常量和变量。 每个单独构成有效的数值表达式。 最后一行显示了具有两个文本的变量的组合。  
  
     请注意数值表达式本身并不构成一个完整的 Visual Basic 语句。 作为一个完整的语句的一部分，必须使用表达式。  
  
#### <a name="to-store-a-numeric-value"></a>若要存储的数字值  
  
-   赋值语句可用于分配给一个变量，一个数值表达式所表示的值，如以下示例所示。  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     在前面的示例中，相等运算符右侧的表达式的值 (`=`) 分配给变量`j`运算符，左侧以便`j`计算结果为 276。  
  
     有关详细信息，请参阅[语句](../../../../visual-basic/language-reference/statements/index.md)。  
  
## <a name="multiple-operators"></a>多个运算符  
 如果数值的表达式包含多个运算符，将计算它们的顺序由运算符优先级规则确定。 若要覆盖的运算符优先顺序规则，则将表达式括在括号，如下所示上面的示例;首先计算括起来的表达式。  
  
#### <a name="to-override-normal-operator-precedence"></a>若要重写正常运算符优先级  
  
-   使用括号括住你想要首先执行的操作。 下面的示例演示具有相同的操作数和运算符的两个不同的结果。  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     在前面的示例中，针对的计算`j`执行加法运算符 (`+`) 第一个因为两边的括号`(67 + i)`重写正常优先级和分配给值`j`为 276 (4 次 69)。 对计算`k`执行运算符在其正常优先 (`*`之前`+`)，和的值分配给`k`为 270 （268 加 2）。  
  
     有关详细信息，请参阅[Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)。  
  
## <a name="see-also"></a>请参阅  
 [运算符和表达式](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [值的比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [语句](../../../../visual-basic/language-reference/statements/index.md)  
 [Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [算术运算符](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [运算符的有效组合](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
