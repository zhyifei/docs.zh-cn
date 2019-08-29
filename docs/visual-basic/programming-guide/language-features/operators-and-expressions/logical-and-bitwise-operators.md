---
title: Visual Basic 中的逻辑运算符和位运算符
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
ms.openlocfilehash: 40076b2ad6606b4c565bcd39dbeea9e55da47211
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963316"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Visual Basic 中的逻辑运算符和位运算符
逻辑运算符比较`Boolean`表达式并`Boolean`返回结果。 `And` 、`Or`、 `Not` 、和`OrElse`运算符都是二进制, 因为运算符采用两个操作数, 而运算符是*一元*, 因为它采用单个操作数。 `AndAlso` `Xor` 其中一些运算符还可以对整数值执行按位逻辑运算。  
  
## <a name="unary-logical-operator"></a>一元逻辑运算符  
 [Not 运算符](../../../../visual-basic/language-reference/operators/not-operator.md)对`Boolean`表达式执行逻辑非*运算*。 它生成其操作数的逻辑相反。 如果表达式的计算结果`True`为, `Not`则`False`返回`False` `Not` ;`True`如果表达式的计算结果为, 则返回。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>二元逻辑运算符  
 [And 运算符](../../../../visual-basic/language-reference/operators/and-operator.md)对两个 `Boolean`表达式执行逻辑与运算。 如果两个表达式的`True`计算结果`And`都`True`为, 则返回。 如果至少有一个表达式的计算结果为`False`, 则`And`返回`False`。  
  
 [Or 运算符](../../../../visual-basic/language-reference/operators/or-operator.md)对两个 `Boolean`表达式执行逻辑或*运算*。 如果两个表达式的`True`计算结果为, 或`True`均为`Or`计算`True`结果, 则返回。 如果两个表达式的`True`计算`Or`结果`False`均为, 则返回。  
  
 [Xor 运算符](../../../../visual-basic/language-reference/operators/xor-operator.md)对两个 `Boolean`表达式执行逻辑异运算。 如果恰好一个表达式的计算`True`结果为, 而不`Xor`是`True`同时返回, 则返回。 如果两个表达式的`True`计算结果都为`False`, 或者`False`都为, `Xor`则返回。  
  
 下面的示例演示`And`了、 `Or`和`Xor`运算符。  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>短路逻辑运算  
 [AndAlso 运算符](../../../../visual-basic/language-reference/operators/andalso-operator.md)与`And`运算符非常类似, 因为它还对两个`Boolean`表达式执行逻辑与运算。 这两者`AndAlso`之间的主要区别在于表现*短路*行为。 如果`AndAlso`表达式中的第一个表达式的计算`False`结果为, 则不会计算第二个表达式, 因为它不能更改`AndAlso`最终`False`结果, 并返回。  
  
 同样, [OrElse 运算符](../../../../visual-basic/language-reference/operators/orelse-operator.md)对两个`Boolean`表达式执行短路逻辑析取。 如果`OrElse`表达式中的第一个表达式的计算`True`结果为, 则不会计算第二个表达式, 因为它不能更改`OrElse`最终`True`结果, 并返回。  
  
### <a name="short-circuiting-trade-offs"></a>短路权衡  
 短路可以通过不计算无法更改逻辑操作结果的表达式来提高性能。 但是, 如果该表达式执行其他操作, 则短路将跳过这些操作。 例如, 如果表达式包含对`Function`过程的调用, 则在表达式为短路时不会调用该过程, 并且中包含的`Function`任何其他代码都不会运行。 因此, 该函数可能会偶尔运行, 并且可能无法正确测试。 或程序逻辑可能依赖于中`Function`的代码。  
  
 下面的示例演示了、 `And` `Or`和其短路对应项之间的差异。  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 在前面的示例中, 请注意, 当调用`checkIfValid()`短路时, 中的一些重要代码不会运行。 即使`12 > 45`返回`If` `checkIfValid()` ,第`And`一条语句也会调用, 因为不会进行短路。 `False` 第二`If`个语句不调用`checkIfValid()`, 因为当`12 > 45`返回`False`时`AndAlso` , 会将第二个表达式短路。 即使`12 < 45`返回`If` `checkIfValid()` ,第`Or`三条语句也会调用, 因为不会进行短路。 `True` 第四`If`个语句不调用`checkIfValid()`, 因为当`12 < 45`返回`True`时`OrElse` , 会将第二个表达式短路。  
  
## <a name="bitwise-operations"></a>按位运算  
 按位运算以二进制 (以2为底) 形式计算两个整数值。 它们比较相应位置上的位, 然后基于比较分配值。 下面的示例阐释`And`运算符。  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 前面的示例将的`x`值设置为1。 出现这种情况的原因如下:  
  
- 值被视为 binary:  
  
     二进制格式的 3 = 011  
  
     二进制格式的 5 = 101  
  
- `And`运算符比较二进制表示形式, 一次比较一个二进制位置 (位)。 如果给定位置处的两个位均为 1, 则将1置于结果中的该位置。 如果任一位为 0, 则将0放入结果中的该位置。 在前面的示例中, 此过程如下所示:  
  
     011 (二进制格式的 3)  
  
     101 (二进制格式的 5)  
  
     001 (二进制格式的结果)  
  
- 结果被视为 decimal。 值001是1的二进制表示形式, 因此`x` = 1。  
  
 按位`Or`运算类似, 不同之处在于, 如果两个比较位中有一个或两个均为 1, 则将1分配给结果位。 `Xor`如果一个比较位 (不是两者) 为 1, 则将1指定给结果位。 `Not`采用单个操作数并反转所有位 (包括符号位), 并将该值分配给结果。 这意味着, 对于有符号正数, `Not`始终返回负值, 对于负数, `Not`始终返回正值或零值。  
  
 `AndAlso` 和`OrElse`运算符不支持按位运算。  
  
> [!NOTE]
> 只能对整数类型执行按位运算。 必须先将浮点值转换为整数类型, 然后才能继续执行位运算。  
  
## <a name="see-also"></a>请参阅

- [逻辑/按位运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [布尔表达式](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Visual Basic 中的算术运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Visual Basic 中的比较运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Visual Basic 中的串联运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [运算符的有效组合](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
