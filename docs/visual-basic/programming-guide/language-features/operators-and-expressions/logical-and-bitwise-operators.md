---
title: 逻辑运算符和位运算符
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
ms.openlocfilehash: 55a246c0d56501a409ebbc7d0d0aa39ae9fa1770
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343593"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Visual Basic 中的逻辑运算符和位运算符
逻辑运算符比较 `Boolean` 表达式并返回 `Boolean` 结果。 `And`、`Or`、`AndAlso`、`OrElse`和 `Xor` 运算符是*二进制*的，因为它们采用两个操作数，而 `Not` 运算符是*一元*运算符，因为它采用单个操作数。 其中一些运算符还可以对整数值执行按位逻辑运算。  
  
## <a name="unary-logical-operator"></a>一元逻辑运算符  
 [Not 运算符](../../../../visual-basic/language-reference/operators/not-operator.md)对 `Boolean` 表达式执行逻辑非*运算*。 它生成其操作数的逻辑相反。 如果表达式的计算结果为 `True`，则 `Not` 返回 `False`;如果表达式的计算结果为 `False`，则 `Not` 返回 `True`。 下面的示例对此进行了演示。  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>二元逻辑运算符  
 [And 运算符](../../../../visual-basic/language-reference/operators/and-operator.md)对两个 `Boolean` 表达式执行逻辑与*运算*。 如果两个表达式的计算结果都为 `True`，则 `And` 返回 `True`。 如果至少有一个表达式的计算结果为 `False`，则 `And` 返回 `False`。  
  
 [Or 运算符](../../../../visual-basic/language-reference/operators/or-operator.md)对两个 `Boolean` 表达式执行*逻辑或* *运算*。 如果两个表达式的计算结果都为 `True`，或都计算为 `True`，则 `Or` 返回 `True`。 如果两个表达式的计算结果都不为 `True`，`Or` 返回 `False`。  
  
 [Xor 运算符](../../../../visual-basic/language-reference/operators/xor-operator.md)对两个 `Boolean` 表达式执行逻辑*异*运算。 如果恰好一个表达式的计算结果为 `True`，而不是同时计算，则 `Xor` 返回 `True`。 如果两个表达式的计算结果都为 `True` 或都计算为 `False`，则 `Xor` 返回 `False`。  
  
 下面的示例演示了 `And`、`Or`和 `Xor` 运算符。  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>短路逻辑运算  
 [AndAlso 运算符](../../../../visual-basic/language-reference/operators/andalso-operator.md)与 `And` 运算符非常类似，因为它还对两个 `Boolean` 表达式执行逻辑与运算。 二者之间的主要区别在于 `AndAlso` 展示*短路*行为。 如果 `AndAlso` 表达式中的第一个表达式的计算结果为 `False`，则不会计算第二个表达式，因为它不能更改最终结果，`AndAlso` 返回 `False`。  
  
 同样， [OrElse 运算符](../../../../visual-basic/language-reference/operators/orelse-operator.md)对两个 `Boolean` 表达式执行短路逻辑析取。 如果 `OrElse` 表达式中的第一个表达式的计算结果为 `True`，则不会计算第二个表达式，因为它不能更改最终结果，`OrElse` 返回 `True`。  
  
### <a name="short-circuiting-trade-offs"></a>短路权衡  
 短路可以通过不计算无法更改逻辑操作结果的表达式来提高性能。 但是，如果该表达式执行其他操作，则短路将跳过这些操作。 例如，如果表达式包含对 `Function` 过程的调用，则在表达式为短路，则不会调用该过程，并且 `Function` 中包含的任何其他代码都不会运行。 因此，该函数可能会偶尔运行，并且可能无法正确测试。 或程序逻辑可能依赖于 `Function`中的代码。  
  
 下面的示例说明 `And`、`Or`和其短路对应项之间的差异。  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 在前面的示例中，请注意，当调用短路时，不会运行 `checkIfValid()` 中的一些重要代码。 即使 `12 > 45` 返回 `False`，第一个 `If` 语句也会调用 `checkIfValid()`，因为 `And` 不会短路。 第二个 `If` 语句不调用 `checkIfValid()`，因为 `12 > 45` 返回 `False`时，`AndAlso` 第二个表达式。 即使 `12 < 45` 返回 `True`，第三个 `If` 语句也会调用 `checkIfValid()`，因为 `Or` 不会短路。 第四个 `If` 语句不调用 `checkIfValid()`，因为 `12 < 45` 返回 `True`时，`OrElse` 第二个表达式。  
  
## <a name="bitwise-operations"></a>按位运算  
 按位运算以二进制（以2为底）形式计算两个整数值。 它们比较相应位置上的位，然后基于比较分配值。 下面的示例演示 `And` 运算符。  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 前面的示例将 `x` 的值设置为1。 出现这种情况的原因如下：  
  
- 值被视为 binary：  
  
     二进制格式的 3 = 011  
  
     二进制格式的 5 = 101  
  
- `And` 运算符比较二进制表示形式，一次比较一个二进制位置（位）。 如果给定位置处的两个位均为1，则将1置于结果中的该位置。 如果任一位为0，则将0放入结果中的该位置。 在前面的示例中，此过程如下所示：  
  
     011（二进制格式的3）  
  
     101（二进制格式的5）  
  
     001（二进制格式的结果）  
  
- 结果被视为 decimal。 值001是1的二进制表示形式，因此 `x` = 1。  
  
 按位 `Or` 运算类似，不同之处在于如果两个比较位中有一个或两个均为1，则将1分配给结果位。 如果某个比较位（不是两者）为1，则 `Xor` 将1赋给结果位。 `Not` 采用单个操作数并反转所有位（包括符号位），并将该值分配给结果。 这意味着，对于有符号的正数，`Not` 始终返回负值，对于负数，`Not` 始终返回正值或零值。  
  
 `AndAlso` 和 `OrElse` 运算符不支持按位运算。  
  
> [!NOTE]
> 只能对整数类型执行按位运算。 必须先将浮点值转换为整数类型，然后才能继续执行位运算。  
  
## <a name="see-also"></a>另请参阅

- [逻辑/按位运算符（Visual Basic）](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [布尔表达式](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Visual Basic 中的算术运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Visual Basic 中的比较运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Visual Basic 中的串联运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [运算符的有效组合](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
