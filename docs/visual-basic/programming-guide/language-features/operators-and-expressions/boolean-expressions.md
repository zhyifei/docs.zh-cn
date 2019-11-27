---
title: 布尔表达式
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
ms.openlocfilehash: 1000ec6e4b35d0cb2c6232b50f9a9551cb0dfdcd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350814"
---
# <a name="boolean-expressions-visual-basic"></a>布尔表达式 (Visual Basic)
*布尔表达式*是计算结果为[布尔数据类型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)的值的表达式： `True` 或 `False`。 `Boolean` 表达式可以采用多种形式。 最简单的方式是将 `Boolean` 变量的值直接与 `Boolean` 文本进行比较，如下面的示例中所示。  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a>= 运算符的两种含义  
 请注意，赋值语句 `newCustomer = True` 看起来与前面示例中的表达式相同，但它执行不同的函数并以不同的方式使用。 在前面的示例中，表达式 `newCustomer = True` 表示一个布尔值，`=` 符号被解释为比较运算符。 在独立语句中，`=` 符号被解释为赋值运算符，并将右侧的值赋给左侧的变量。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 有关详细信息，请参阅[值比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)和[语句](../../../../visual-basic/language-reference/statements/index.md)。  
  
## <a name="comparison-operators"></a>比较运算符  
 比较运算符（例如 `=`、`<`、`>`、`<>`、`<=`和 `>=`）通过将运算符左侧的表达式与运算符右侧的表达式进行比较，并将结果计算为 `True` 或 `False`来产生布尔表达式。 下面的示例阐释了这一点。  
  
 `42 < 81`  
  
 因为42小于81，所以前面的示例中的布尔表达式的计算结果为 `True`。 有关此类表达式的详细信息，请参阅[值比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)。  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>与逻辑运算符组合在一起的比较运算符  
 可以使用逻辑运算符组合比较表达式以生成更复杂的布尔表达式。 下面的示例演示如何结合使用比较运算符和逻辑运算符。  
  
 `x > y And x < 1000`  
  
 在前面的示例中，整个表达式的值取决于 `And` 运算符两侧的表达式的值。 如果两个表达式都 `True`，则整个表达式的计算结果为 `True`。 如果 `False`其中一个表达式，则整个表达式的计算结果为 `False`。  
  
## <a name="short-circuiting-operators"></a>短路运算符  
 逻辑运算符 `AndAlso` 和 `OrElse` 表现称为 "*短路*" 的行为。 短路运算符首先计算左操作数。 如果左操作数确定整个表达式的值，则程序执行将继续，而不计算正确的表达式。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 在前面的示例中，运算符计算左侧表达式 `45 < 12`。 由于左侧表达式的计算结果为 `False`，因此整个逻辑表达式的计算结果必须为 `False`。 因此，程序执行会跳过 `If` 块中代码的执行，而不计算右侧的表达式 `testFunction(3)`。 此示例不调用 `testFunction()`，因为左侧表达式 falsifies 整个表达式。  
  
 同样，如果使用 `OrElse` 的逻辑表达式中的左侧表达式的计算结果为 `True`，则执行将继续执行下一行代码，而不计算正确的表达式，因为左侧表达式已经验证了整个表达式。  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>与非短路运算符的比较  
 相反，当使用逻辑运算符 `And` 和 `Or` 时，将计算逻辑运算符的两侧。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 前面的示例调用 `testFunction()`，即使左侧表达式的计算结果为 `False`。  
  
## <a name="parenthetical-expressions"></a>括号中的表达式  
 您可以使用括号来控制布尔表达式的计算顺序。 用括号括起来的表达式首先计算。 对于多个级别的嵌套，将优先顺序授予最深层嵌套的表达式。 在括号内，计算按照运算符优先级的规则进行。 有关详细信息，请参阅[Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)。  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 中的逻辑运算符和位运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [值的比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [语句](../../../../visual-basic/programming-guide/language-features/statements.md)
- [比较运算符](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [运算符的有效组合](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Boolean 数据类型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
