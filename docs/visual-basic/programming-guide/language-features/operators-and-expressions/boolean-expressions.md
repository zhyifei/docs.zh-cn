---
title: 布尔表达式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
ms.openlocfilehash: ff5843c815658468ac69fe5d62a9ea4cac2be830
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="boolean-expressions-visual-basic"></a>布尔表达式 (Visual Basic)
A*布尔表达式*是计算结果为的值的表达式[布尔数据类型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md):`True`或`False`。 `Boolean` 表达式可以采用多种形式。 最简单的是直接比较的值的`Boolean`变量`Boolean`文本，如下面的示例中所示。  
  
 [!code-vb[VbVbalrOperators#87](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_1.vb)]  
  
## <a name="two-meanings-of-the--operator"></a>两种含义 = 运算符  
 请注意，赋值语句`newCustomer = True`与在前面的示例中，该表达式看上去相同但它执行不同的功能，并以不同的使用。 在前面的示例中，表达式`newCustomer = True`表示布尔值，与`=`号解释为一个比较运算符。 在独立的语句中，`=`登录解释为赋值运算符，并将分配给左侧变量右侧的值。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbalrOperators#88](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_2.vb)]  
  
 有关详细信息，请参阅[值的比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)和[语句](../../../../visual-basic/language-reference/statements/index.md)。  
  
## <a name="comparison-operators"></a>比较运算符  
 比较运算符，如`=`， `<`， `>`， `<>`， `<=`，和`>=`通过比较运算符的表达式左侧的右侧表达式产生的 Boolean 表达式运算符和评估结果作为`True`或`False`。 下面的示例阐释了这一点。  
  
 `42 < 81`  
  
 由于 42 是小于 81，前面示例中的布尔表达式计算结果为`True`。 这种类型的表达式的详细信息，请参阅[值的比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)。  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>与逻辑运算符结合使用的比较运算符  
 可以使用逻辑运算符来生成更复杂的布尔表达式组合比较表达式。 下面的示例演示如何结合使用逻辑运算符的比较运算符的使用。  
  
 `x > y And x < 1000`  
  
 在前面的示例中，整个表达式的值取决于每一侧的表达式的值`And`运算符。 如果两个表达式均`True`，则整个表达式的计算结果为`True`。 如果其中任何一个表达式是`False`，则整个表达式的计算结果为`False`。  
  
## <a name="short-circuiting-operators"></a>短路运算符  
 逻辑运算符`AndAlso`和`OrElse`行为称为*短路*。 短路运算符首先计算左的操作数。 如果左的操作数确定整个表达式的值，程序执行过程而不计算右侧表达式。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbalrOperators#89](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_3.vb)]  
  
 在前面的示例中，在操作数的计算左侧的表达式， `45 < 12`。 因为左侧的表达式的计算结果为`False`，整个逻辑表达式的计算结果必须为`False`。 程序执行过程因此跳过执行中的代码`If`块而不计算右侧表达式， `testFunction(3)`。 此示例不会调用`testFunction()`因为左侧的表达式使整个表达式。  
  
 同样，如果左侧的表达式在逻辑表达式中使用`OrElse`计算结果为`True`，因为左侧的表达式已经证明整个，则执行将而不计算右侧表达式中，转到下一行代码表达式。  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>与非短路运算符比较  
 与此相反，计算逻辑运算符的两端时逻辑运算符`And`和`Or`使用。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbalrOperators#90](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_4.vb)]  
  
 前面的示例调用`testFunction()`即使左侧的表达式的计算结果为`False`。  
  
## <a name="parenthetical-expressions"></a>带括号的表达式  
 可以使用括号来控制布尔表达式的计算顺序。 首先计算用括号括起来的表达式。 针对多个级别的嵌套，优先授予嵌套最深的表达式。 在括号内，计算将继续按照运算符优先级规则。 有关详细信息，请参阅[Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Basic 中的逻辑和按位运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [值的比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [语句](../../../../visual-basic/programming-guide/language-features/statements.md)  
 [比较运算符](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [运算符的有效组合](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)  
 [Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Boolean 数据类型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
