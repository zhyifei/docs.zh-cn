---
title: 运算符结果的数据类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types [Visual Basic]
- operator result data types [Visual Basic]
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
ms.openlocfilehash: b0ebdb723df6bdb4f74e1558537c307ddb917f64
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923278"
---
# <a name="data-types-of-operator-results-visual-basic"></a>运算符结果的数据类型 (Visual Basic)
Visual Basic 根据操作数的数据类型确定操作的结果数据类型。 在某些情况下, 这可能是一种数据类型, 其范围比任一操作数大。  
  
## <a name="data-type-ranges"></a>数据类型范围  
 相关数据类型的范围从最小到最大的顺序如下所示:  
  
- [布尔](../../../visual-basic/language-reference/data-types/boolean-data-type.md)值-两个可能的值  
  
- [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md) -256 可能的整数值  
  
- [Short](../../../visual-basic/language-reference/data-types/short-data-type.md)、 [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) (65536 (6.5)) 可能的整数值  
  
- [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)、 [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) -4294967296 (4.2 ... E + 9) 可能的整数值  
  
- [Long](../../../visual-basic/language-reference/data-types/long-data-type.md)、 [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) -18446744073709551615 (1.8 ... E + 19) 可能的整数值  
  
- [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) -1.5 ... e + 29 个可能的整数值, 最大范围 7.9 ... E + 28 (绝对值)  
  
- [单](../../../visual-basic/language-reference/data-types/single-data-type.md)-最大范围 3.4 ... E + 38 (绝对值)  
  
- [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) –最大范围 1.7 ... E + 308 (绝对值)  
  
 有关 Visual Basic 数据类型的详细信息, 请参阅[数据类型](../../../visual-basic/language-reference/data-types/index.md)。  
  
 如果操作数的计算结果为[Nothing](../../../visual-basic/language-reference/nothing.md), 则 Visual Basic 算术运算符将其视为零。  
  
## <a name="decimal-arithmetic"></a>Decimal 算法  
 请注意, [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)数据类型既不是浮点数据类型, 也不是整数。  
  
 `+`如果`Single` `Double`、 、、`–`或`Decimal`运算的任一操作数为, 而另一个不是或, 则 Visual Basic 将其他操作数扩大到`Mod` `*` `/` `Decimal`. 它在中`Decimal`执行操作, 结果数据类型为`Decimal`。  
  
## <a name="floating-point-arithmetic"></a>浮点运算  
 Visual Basic 在[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)中执行大多数浮点运算, 这是此类操作的最有效的数据类型。 但是, 如果一个操作数为[Single](../../../visual-basic/language-reference/data-types/single-data-type.md) , 而另一个操作数`Double`为 not, 则 Visual Basic 在`Single`中执行该操作。 它在操作之前将每个操作数扩展为适当的数据类型, 并且结果具有该数据类型。  
  
### <a name="-and--operators"></a>/和 ^ 运算符  
 仅为[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)、 [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)和[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)数据类型定义运算符。`/` Visual Basic 在操作之前将每个操作数扩大为适当的数据类型, 并且结果具有该数据类型。  
  
 下表显示了`/`运算符的结果数据类型。 请注意, 此表为对称表;对于给定的操作数数据类型组合, 无论操作数的顺序如何, 结果数据类型都是相同的。  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|任何整数类型|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|任何整数类型|Decimal|Single|Double|Double|  
  
 仅对数据类型定义`^`运算符 `Double` 。 Visual Basic 在操作之前将每个`Double`操作数扩大到最前面, 结果数据类型始终`Double`为。  
  
## <a name="integer-arithmetic"></a>整数算法  
 整数运算的结果数据类型取决于操作数的数据类型。 一般情况下, Visual Basic 使用以下策略来确定结果数据类型:  
  
- 如果二元运算符的两个操作数具有相同的数据类型, 则结果将具有该数据类型。 异常是`Boolean` `Short`强制执行的。  
  
- 如果无符号操作数参与有符号操作数, 则结果将具有一个有符号的类型, 其中至少有一个操作数为同一范围。  
  
- 否则, 结果通常具有两个操作数数据类型中较大的一个。  
  
 请注意, 结果数据类型可能不与任一操作数数据类型相同。  
  
> [!NOTE]
> 结果数据类型并不总是足够大, 无法保存操作生成的所有可能值。 如果结果数据类型的值太大, 则会出现异常。<xref:System.OverflowException>  
  
### <a name="unary--and--operators"></a>一元 + and –运算符  
 下表显示了两个一元运算符的结果数据类型: `+`和。 `–`  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|运算符`+`|Short|SByte|Byte|Short|UShort|整数|UInteger|Long|ULong|  
|运算符`–`|Short|SByte|Short|Short|整数|整数|Long|Long|Decimal|  
  
### <a name="-and--operators"></a><\<和 > > 运算符  
 下表显示了两个移位运算符的结果数据类型: `<<`和。 `>>` Visual Basic 将每个位移位运算符视为其左操作数的一元运算符 (要移位的位模式)。  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`， `>>`|Short|SByte|Byte|Short|UShort|整数|UInteger|Long|ULong|  
  
 如果左`Decimal`操作数为`Single` `Long` 、、或`String`, 则 Visual Basic 尝试在操作之前将其转换为, 结果数据类型为`Long`。 `Double` 右操作数 (要移位的位数) 必须为`Integer`或扩展到`Integer`的类型。  
  
### <a name="binary----and-mod-operators"></a>Binary +、–、* 和 Mod 运算符  
 下表`+`显示了二元运算符和`–`运算符的结果数据类型以及`*`和`Mod`运算符。 请注意, 此表为对称表;对于给定的操作数数据类型组合, 无论操作数的顺序如何, 结果数据类型都是相同的。  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|整数|整数|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|整数|整数|Long|Long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|整数|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|整数|整数|Long|Long|Decimal|  
|`UShort`|整数|整数|UShort|整数|UShort|整数|UInteger|Long|ULong|  
|`Integer`|整数|整数|整数|整数|整数|整数|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>\ 运算符  
 下表显示了`\`运算符的结果数据类型。 请注意, 此表为对称表;对于给定的操作数数据类型组合, 无论操作数的顺序如何, 结果数据类型都是相同的。  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|整数|整数|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|整数|整数|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|整数|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|整数|整数|Long|Long|Long|  
|`UShort`|整数|整数|UShort|整数|UShort|整数|UInteger|Long|ULong|  
|`Integer`|整数|整数|整数|整数|整数|整数|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 如果`\`运算符的任一操作数为[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)、 [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)或[Double](../../../visual-basic/language-reference/data-types/double-data-type.md), 则 Visual Basic 尝试在运算前将其转换为[Long](../../../visual-basic/language-reference/data-types/long-data-type.md) , 结果数据类型为`Long`。  
  
## <a name="relational-and-bitwise-comparisons"></a>关系和按位比较  
 关系运算的结果数据类型 (`=`、 `<>`、 `<=` `>` `<`、、、 `>=`) 始终`Boolean`为[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)。 `And`对于操作数上`AndAlso` `Or` `OrElse` `Not`的逻辑运算 (、、 、`Xor`、、), 情况也是如此。 `Boolean`  
  
 按位逻辑运算的结果数据类型取决于操作数的数据类型。 请注意, `OrElse`仅为定义了`Boolean`和, `Boolean`并且 Visual Basic 在执行操作之前将每个操作数转换为所需的。 `AndAlso`  
  
### <a name="-----and--operators"></a>=、< >、 \<、>、 \<= 和 > = 运算符  
 如果两个操作数`Boolean`都为, `True`则 Visual Basic 视为小于`False`。 如果将数字类型与`String`进行比较, 则 Visual Basic 在操作之前尝试`String`将转换为。 `Double` `Char` 或`Date`操作数只能与相同数据类型的另一个操作数进行比较。 结果数据类型始终`Boolean`为。  
  
### <a name="bitwise-not-operator"></a>按位 Not 运算符  
 下表显示了按位`Not`运算符的结果数据类型。  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolean|SByte|Byte|Short|UShort|整数|UInteger|Long|ULong|  
  
 `Decimal`如果操作数为`Single` `Long` 、、或`String`, 则 Visual Basic 尝试在操作之前将其转换为, 结果数据类型为`Long`。 `Double`  
  
### <a name="bitwise-and-or-and-xor-operators"></a>按位 And、Or 和 Xor 运算符  
 下表显示了位`And`、 `Or`和`Xor`运算符的结果数据类型。 请注意, 此表为对称表;对于给定的操作数数据类型组合, 无论操作数的顺序如何, 结果数据类型都是相同的。  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Boolean|SByte|Short|Short|整数|整数|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|整数|整数|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|整数|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|整数|整数|Long|Long|Long|  
|`UShort`|整数|整数|UShort|整数|UShort|整数|UInteger|Long|ULong|  
|`Integer`|整数|整数|整数|整数|整数|整数|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 `Decimal`如果操作数为`Single` `Long`、、或`String`, 则 Visual Basic 尝试在操作之前将其`Long`转换为, 结果数据类型与该操作数已相同。 `Double`  
  
## <a name="miscellaneous-operators"></a>其他运算符  
 仅为`String`操作数的串联定义运算符。`&` Visual Basic 在操作`String`之前将每个操作数转换为必需的, 结果数据类型始终`String`为。 对于运算符, 所有`String`转换都视为扩大, 即使`Option Strict`是`On`。 `&`  
  
 `Is` 和`IsNot`运算符要求两个操作数均为引用类型。 `TypeOf`.。。`Is` expression 要求第一个操作数为引用类型, 第二个操作数为数据类型的名称。 在所有这些情况下, 结果数据类型`Boolean`为。  
  
 仅为操作数的`String`模式匹配定义运算符。`Like` Visual Basic 尝试在操作`String`之前将每个操作数转换为必需的。 结果数据类型始终`Boolean`为。  
  
## <a name="see-also"></a>请参阅

- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Visual Basic 中的比较运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [运算符](../../../visual-basic/language-reference/operators/index.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [比较运算符](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)
