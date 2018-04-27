---
title: 算术运算符 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators [Visual Basic]
- bit-shift operators [Visual Basic]
- zero, division by zero
- operators [Visual Basic], arithmetic
- division [Visual Basic], by zero
- Visual Basic code, operators
- arithmetic operators [Visual Basic], about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cef1e3610d885a0f3a2bae718641f7b8ca1062dc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="arithmetic-operators-in-visual-basic"></a>算术运算符 (Visual Basic)
算术运算符用于执行很多熟悉的算术运算，涉及计算的文本、 变量、 其他表达式、 函数和属性调用和常量所表示的数字值。 算术运算符也属于是移位运算符，它们充当级别的单个位进行运算的操作数和向左或向右移动其位模式。  
  
## <a name="arithmetic-operations"></a>算术运算  
 你可以添加两个值一起使用的表达式中[+ 运算符](../../../../visual-basic/language-reference/operators/addition-operator.md)，或从另一个具有减去 1 [-运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md)，如下面的示例所示。  
  
 [!code-vb[VbVbalrOperators#57](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]  
  
 求反也使用[-运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md)，但只带一个操作数，如下面的示例所示。  
  
 [!code-vb[VbVbalrOperators#58](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]  
  
 乘法和除法使用[* 运算符](../../../../visual-basic/language-reference/operators/multiplication-operator.md)和[/ 运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md)分别，如以下示例所示。  
  
 [!code-vb[VbVbalrOperators#59](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]  
  
 求幂使用[^ 运算符](../../../../visual-basic/language-reference/operators/exponentiation-operator.md)，如下面的示例所示。  
  
 [!code-vb[VbVbalrOperators#60](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]  
  
 整数除法执行使用[\ 运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md)。 整数除法返回的商，即表示的次数的整数除数可以将划分为而无需考虑的任何其余部分被除数。 除数和被除数必须是整数类型 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`，和`ULong`) 为此运算符。 必须首先将所有其他类型转换为整数类型。 下面的示例演示整数除法。  
  
 [!code-vb[VbVbalrOperators#61](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]  
  
 使用执行取模算术[Mod 运算符](../../../../visual-basic/language-reference/operators/mod-operator.md)。 此运算符返回余数除数除以除数后的整数的次数。 如果除数和被除数是整型类型，则返回的值是整数。 如果除数和被除数是浮点类型，返回的值也是浮点。 下面的示例演示此行为。  
  
 [!code-vb[VbVbalrOperators#62](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]  
  
 [!code-vb[VbVbalrOperators#63](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]  
  
### <a name="attempted-division-by-zero"></a>尝试的除数为零  
 被零除会得到不同的结果，具体取决于涉及的数据类型。 整型部门中 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`， `ULong`)，则[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]引发<xref:System.DivideByZeroException>异常。 在除法运算`Decimal`或`Single`数据类型，[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]也会引发<xref:System.DivideByZeroException>异常。  
  
 涉及的浮点部门中`Double`数据类型，不会引发异常，并且结果是表示的类成员<xref:System.Double.NaN>， <xref:System.Double.PositiveInfinity>，或<xref:System.Double.NegativeInfinity>，取决于被除数。 下表汇总了尝试将划分的各种结果`Double`被零的值。  
  
|被除数数据类型|除数数据类型|被除数的值|结果|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN> （不是数学上定义的数字）|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 当捕获<xref:System.DivideByZeroException>异常，你可以使用其成员来帮助你处理它。 例如，<xref:System.Exception.Message%2A>属性包含异常的消息文本。 有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。  
  
## <a name="bit-shift-operations"></a>移位运算  
 移位操作对位模式执行算术移位运算。 而右侧操作数中指定的位置，若要将切换模式数，在左侧，操作数中包含模式。 你可以向与右上移模式[>> 运算符](../../../../visual-basic/language-reference/operators/right-shift-operator.md)或左侧[<< 运算符](../../../../visual-basic/language-reference/operators/left-shift-operator.md)。  
  
 模式操作数的数据类型必须是`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`，或`ULong`。 Shift 量操作数的数据类型必须是`Integer`或必须扩大到`Integer`。  
  
 算术移位不是循环，这意味着移出结果的一个 end 的数位另一端不重新移入。 因 shift 空出的位设置，如下所示：  
  
-   算术左移位运算的 0  
  
-   0 表示算术右移位运算的正数值  
  
-   0 表示无符号的数据类型的算术右移位 (`Byte`， `UShort`， `UInteger`， `ULong`)  
  
-   1 表示负数算术右移位 (`SByte`， `Short`， `Integer`，或`Long`)  
  
 下面的示例会转而`Integer`值左侧和右侧。  
  
 [!code-vb[VbVbalrOperators#64](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]  
  
 算术移位永远不会生成溢出异常。  
  
## <a name="bitwise-operations"></a>按位运算  
 除了成为逻辑运算符， `Not`， `Or`， `And`，和`Xor`还执行按位算术运算在数值中使用时。 有关详细信息，请参阅"按位运算"[逻辑和按位运算符在 Visual Basic 中](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)。  
  
## <a name="type-safety"></a>类型安全  
 操作数通常应是类型的相同。 例如，如果你正在添加`Integer`变量，你应将其添加到另一个`Integer`变量，并且你应将结果赋给变量的类型`Integer`以及。  
  
 一种方法以确保良好的类型安全编码做法是使用[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)。 如果你设置`Option Strict On`，Visual Basic 会自动执行*类型安全*转换。 例如，如果你尝试添加`Integer`变量`Double`变量并将值赋给`Double`变量，该操作将正常进行，因为`Integer`值可以转换为`Double`而不会丢失数据。 类型不安全的转换，另一方面，导致编译器错误与`Option Strict On`。 例如，如果你尝试添加`Integer`变量`Double`变量并将值赋给`Integer`变量，会导致编译器错误，因为`Double`变量不能隐式转换为类型`Integer`。  
  
 如果你设置`Option Strict Off`，但是，Visual Basic 将允许隐式收缩转换完成，尽管它们会导致意外丢失数据或精度。 为此，我们建议你使用`Option Strict On`编写生产代码时。 有关详细信息，请参阅 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。  
  
## <a name="see-also"></a>请参阅  
 [算术运算符](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [移位运算符](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [在 Visual Basic 中的比较运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [在 Visual Basic 中的串联运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [在 Visual Basic 中的逻辑和按位运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [运算符的有效组合](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
