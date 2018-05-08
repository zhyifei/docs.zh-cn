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
ms.openlocfilehash: 371d28629b39fb2808ca018ea69da3306a31f50c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Visual Basic 中的逻辑运算符和位运算符
逻辑运算符比较`Boolean`表达式，并返回`Boolean`结果。 `And`， `Or`， `AndAlso`， `OrElse`，和`Xor`运算符是*二进制*由于它们采用两个操作数，而`Not`运算符是*一元*因为它采用一个操作数。 某些这些运算符还可以执行对整数值的按位逻辑运算。  
  
## <a name="unary-logical-operator"></a>一元逻辑运算符  
 [Not 运算符](../../../../visual-basic/language-reference/operators/not-operator.md)执行逻辑*求反*上`Boolean`表达式。 它将产生其操作数的逻辑相反。 如果表达式计算结果为`True`，然后`Not`返回`False`; 如果表达式计算结果为`False`，然后`Not`返回`True`。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbalrOperators#77](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_1.vb)]  
  
## <a name="binary-logical-operators"></a>二进制逻辑运算符  
 [And 运算符](../../../../visual-basic/language-reference/operators/and-operator.md)执行逻辑*一起*对两个`Boolean`表达式。 如果两个表达式的计算结果为`True`，然后`And`返回`True`。 如果至少一个表达式计算结果为`False`，然后`And`返回`False`。  
  
 [或运算符](../../../../visual-basic/language-reference/operators/or-operator.md)执行逻辑*析取*或*包含*对两个`Boolean`表达式。 如果其中任何一个表达式的计算结果为`True`，或两者的计算结果`True`，然后`Or`返回`True`。 如果表达式都不计算结果为`True`，`Or`返回`False`。  
  
 [异或运算符](../../../../visual-basic/language-reference/operators/xor-operator.md)执行逻辑*排除*对两个`Boolean`表达式。 如果只有一个表达式的计算结果为`True`，但不是两个`Xor`返回`True`。 如果两个表达式的计算结果为`True`或两者的计算结果`False`，`Xor`返回`False`。  
  
 下面的示例演示`And`， `Or`，和`Xor`运算符。  
  
 [!code-vb[VbVbalrOperators#78](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_2.vb)]  
  
## <a name="short-circuiting-logical-operations"></a>短路逻辑操作  
 [AndAlso 运算符](../../../../visual-basic/language-reference/operators/andalso-operator.md)非常类似于`And`运算符，在于它还执行逻辑与对两个`Boolean`表达式。 两者之间的主要区别在于`AndAlso`表现出*短路*行为。 如果中的第一个表达式`AndAlso`表达式计算结果为`False`，则因为它不会改变最终结果，不会计算第二个表达式和`AndAlso`返回`False`。  
  
 同样， [OrElse 运算符](../../../../visual-basic/language-reference/operators/orelse-operator.md)执行短路逻辑或运算，对两个`Boolean`表达式。 如果中的第一个表达式`OrElse`表达式计算结果为`True`，则因为它不会改变最终结果，不会计算第二个表达式和`OrElse`返回`True`。  
  
### <a name="short-circuiting-trade-offs"></a>短路权衡  
 短路可以通过不计算表达式，无法更改逻辑操作的结果中提高性能。 但是，如果该表达式执行其他操作，则短路将跳过这些操作。 例如，如果表达式包含对的调用`Function`过程，如果表达式是短路，和中包含的任何其他代码不调用过程`Function`不会运行。 因此，该函数仅偶尔可能会运行，并可能未正确测试。 程序逻辑可能依赖于中的代码或`Function`。  
  
 下面的示例演示之间的差异`And`， `Or`，与其短路副本。  
  
 [!code-vb[VbVbalrOperators#81](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_3.vb)]  
  
 [!code-vb[VbVbalrOperators#80](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_4.vb)]  
  
 [!code-vb[VbVbalrOperators#79](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_5.vb)]  
  
 在前面的示例中，请注意，在一些重要代码`checkIfValid()`调用短路时不会运行。 第一个`If`语句也会调用`checkIfValid()`即使`12 > 45`返回`False`，这是因为`And`不会短路。 第二个`If`语句不会调用`checkIfValid()`，因为当`12 > 45`返回`False`，`AndAlso`会使短路第二个表达式。 第三个`If`语句也会调用`checkIfValid()`即使`12 < 45`返回`True`，这是因为`Or`不会短路。 第四个`If`语句不会调用`checkIfValid()`，因为当`12 < 45`返回`True`，`OrElse`会使短路第二个表达式。  
  
## <a name="bitwise-operations"></a>按位运算  
 按位运算的计算结果在二进制 (基数为 2) 窗体中的两个整数值。 它们比较相应位置处的位，然后分配基于比较的值。 下面的示例演示`And`运算符。  
  
 [!code-vb[VbVbalrConcepts#2](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/logical-and-bitwise-operators_6.vb)]  
  
 前面的示例设置的值`x`为 1。 由于以下原因发生这种情况：  
  
-   以二进制形式处理值：  
  
     以二进制形式的 3 = 011  
  
     以二进制形式的 5 = 101  
  
-   `And`运算符比较二进制表示形式，一次的一个二进制位置 （位）。 如果位于给定位置两个位均为 1，1 都放在结果中的此位置。 如果其中一个位是 0，0 被置于结果中的此位置。 在前面的示例正常，如下所示：  
  
     011 (3 以二进制形式)  
  
     101 (5 以二进制形式)  
  
     001 （以二进制形式，结果）  
  
-   结果将被视为小数。 001 的值是 1，二进制表示形式，因此`x`= 1。  
  
 按位`Or`操作非常相似，只不过 1 分配给结果位，如果一个或两个比较位为 1。 `Xor` 如果完全之一 （不是两者） 的比较位是 1，1 赋给结果位。 `Not` 采用单个操作数和反转所有位，包括符号位，并将该值赋给结果。 这意味着，对于有符号正数，`Not`始终返回一个负值，而对于负数，`Not`始终返回一个值为正或零值。  
  
 `AndAlso`和`OrElse`运算符不支持按位运算。  
  
> [!NOTE]
>  只能对整型，可以执行按位运算。 按位运算可以继续操作之前，必须为整型转换浮点值。  
  
## <a name="see-also"></a>请参阅  
 [逻辑/按位运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [布尔表达式](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [在 Visual Basic 中的算术运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [在 Visual Basic 中的比较运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [在 Visual Basic 中的串联运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [运算符的有效组合](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
