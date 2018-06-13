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
ms.openlocfilehash: c2e94a80e83becf25bf47ef7837362f0ebf441a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605428"
---
# <a name="data-types-of-operator-results-visual-basic"></a>运算符结果的数据类型 (Visual Basic)
Visual Basic 确定基于操作数的数据类型的操作的结果数据类型。 在某些情况下这可能是更大的范围比两个操作数的数据类型。  
  
## <a name="data-type-ranges"></a>数据类型范围  
 范围的相关数据类型，从最小到最大值的顺序如下所示：  
  
-   [布尔](../../../visual-basic/language-reference/data-types/boolean-data-type.md)-两个可能值  
  
-   [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)，[字节](../../../visual-basic/language-reference/data-types/byte-data-type.md)-256 个可能的整数值  
  
-   [短](../../../visual-basic/language-reference/data-types/short-data-type.md)， [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) -65,536 (6.5 … E + 4) 可能的整数值  
  
-   [整数](../../../visual-basic/language-reference/data-types/integer-data-type.md)， [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) -4294967296 (4.2 … E + 9) 可能的整数值  
  
-   [长](../../../visual-basic/language-reference/data-types/long-data-type.md)， [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) -18446744073709551615 (1.8 … E + 19) 可能的整数值  
  
-   [十进制](../../../visual-basic/language-reference/data-types/decimal-data-type.md)-1.5 … E + 29 可能整数的值，最大范围 7.9 … E + 28 （绝对值）  
  
-   [单个](../../../visual-basic/language-reference/data-types/single-data-type.md)-最大范围向...3.4 E + 38 （绝对值）  
  
-   [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) -最大范围向...1.7 E + 308 （绝对值）  
  
 Visual Basic 数据类型的详细信息，请参阅[数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md)。  
  
 如果操作数的计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)，Visual Basic 算术运算符将其视为零。  
  
## <a name="decimal-arithmetic"></a>十进制算术运算  
 请注意，[十进制](../../../visual-basic/language-reference/data-types/decimal-data-type.md)数据类型既不是浮点也整数。  
  
 如果其中一个操作数的`+`， `–`， `*`， `/`，或`Mod`操作`Decimal`和另一个则不`Single`或`Double`，Visual Basic 扩大到另一个操作数`Decimal`. 它执行中的操作`Decimal`，并且结果数据类型是`Decimal`。  
  
## <a name="floating-point-arithmetic"></a>浮点运算  
 Visual Basic 执行中的大多数浮点算术[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)，这是最有效的数据类型对于这类操作。 但是，如果一个操作数是[单个](../../../visual-basic/language-reference/data-types/single-data-type.md)和另一个则不`Double`中的操作，Visual Basic 执行`Single`。 它将根据操作之前, 的适当的数据类型的每个操作数扩展和结果也为该数据类型。  
  
### <a name="-and--operators"></a>/ 和 ^ 运算符  
 `/`运算符仅为定义[十进制](../../../visual-basic/language-reference/data-types/decimal-data-type.md)，[单个](../../../visual-basic/language-reference/data-types/single-data-type.md)，和[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)数据类型。 Visual Basic 扩大根据操作之前, 的适当的数据类型的每个操作数和结果也为该数据类型。  
  
 下表显示结果的数据类型`/`运算符。 请注意，此表是对称;为给定操作数数据类型的组合，结果数据类型是而不考虑操作数的顺序相同。  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|任何整数类型|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|任何整数类型|Decimal|Single|Double|Double|  
  
 `^`运算符仅为定义`Double`数据类型。 Visual Basic 将根据需要向每个操作数扩展`Double`之前此操作，并且结果数据类型为始终`Double`。  
  
## <a name="integer-arithmetic"></a>整数算法  
 整数运算的结果数据类型取决于操作数的数据类型。 一般情况下，Visual Basic 使用以下策略用于确定的结果数据类型：  
  
-   如果二元运算符的两个操作数具有相同的数据类型，结果也为该数据类型。 例外情况是`Boolean`，这将其强制转换为`Short`。  
  
-   如果无符号的操作数加入的有符号的操作数，结果与带符号的类型至少尽可能大范围与具有其中一个操作数。  
  
-   否则，结果通常具有较大的两个操作数数据类型。  
  
 请注意结果数据类型不可能任一操作数数据类型。  
  
> [!NOTE]
>  结果数据类型并不总是足够大以保存操作产生的所有可能的值。 <xref:System.OverflowException>如果值太大的结果数据类型，则可能出现异常。  
  
### <a name="unary--and--operators"></a>一元 + 和-运算符  
 下表显示结果数据类型的两个一元运算符，`+`和`–`。  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|一元 `+`|Short|SByte|Byte|Short|UShort|整数|UInteger|Long|ULong|  
|一元 `–`|Short|SByte|Short|Short|Integer|整数|Long|Long|Decimal|  
  
### <a name="-and--operators"></a><\< 和 >> 运算符  
 下表显示结果数据类型的两个移位运算符，`<<`和`>>`。 Visual Basic 视为其左操作数 （要移动的位模式） 的一元运算符将每个移位运算符。  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|整数|UInteger|Long|ULong|  
  
 如果左的操作数是`Decimal`， `Single`， `Double`，或`String`，尝试将其转换为 Visual Basic`Long`之前此操作，并且结果数据类型为`Long`。 右操作数 （要位移的位位置数） 必须`Integer`或类型扩大到`Integer`。  
  
### <a name="binary----and-mod-operators"></a>二进制 +，-，*，和 Mod 运算符  
 下表显示结果来生成二进制文件的数据类型`+`和`–`运算符和`*`和`Mod`运算符。 请注意，此表是对称;为给定操作数数据类型的组合，结果数据类型是而不考虑操作数的顺序相同。  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|整数|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|Integer|整数|Long|Long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|整数|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|整数|Long|Long|Decimal|  
|`UShort`|整数|整数|UShort|整数|UShort|整数|UInteger|Long|ULong|  
|`Integer`|整数|整数|整数|整数|整数|整数|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>\ 运算符  
 下表显示结果的数据类型`\`运算符。 请注意，此表是对称;为给定操作数数据类型的组合，结果数据类型是而不考虑操作数的顺序相同。  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|整数|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Integer|整数|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|整数|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|整数|Long|Long|Long|  
|`UShort`|整数|整数|UShort|整数|UShort|整数|UInteger|Long|ULong|  
|`Integer`|整数|整数|整数|整数|整数|整数|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 如果其中一个操作数的`\`运算符是[十进制](../../../visual-basic/language-reference/data-types/decimal-data-type.md)，[单个](../../../visual-basic/language-reference/data-types/single-data-type.md)，或[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)，尝试将其转换为 Visual Basic[长时间](../../../visual-basic/language-reference/data-types/long-data-type.md)之前此操作，并且结果数据类型为`Long`。  
  
## <a name="relational-and-bitwise-comparisons"></a>关系和按位比较  
 关系操作的结果数据类型 (`=`， `<>`， `<`， `>`， `<=`， `>=`) 始终`Boolean`[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)。 同样适用于逻辑运算 (`And`， `AndAlso`， `Not`， `Or`， `OrElse`， `Xor`) 上`Boolean`操作数。  
  
 按位逻辑运算的结果数据类型取决于操作数的数据类型。 请注意，`AndAlso`和`OrElse`仅为定义`Boolean`，和 Visual Basic 将根据需要向每个操作数转换`Boolean`之前执行该操作。  
  
### <a name="-----and--operators"></a>= <>， \<，>， \<=、 和 > = 运算符  
 如果这两个操作数都是`Boolean`，Visual Basic 将`True`要小于`False`。 如果与数值类型进行比较`String`，Visual Basic 尝试转换`String`到`Double`操作之前。 A`Char`或`Date`操作数可以仅与相同的数据类型的另一个操作数进行比较。 结果数据类型始终是`Boolean`。  
  
### <a name="bitwise-not-operator"></a>按位 Not 运算符  
 下表显示结果的按位数据类型`Not`运算符。  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolean|SByte|Byte|Short|UShort|整数|UInteger|Long|ULong|  
  
 如果操作数是`Decimal`， `Single`， `Double`，或`String`，尝试将其转换为 Visual Basic`Long`之前此操作，并且结果数据类型为`Long`。  
  
### <a name="bitwise-and-or-and-xor-operators"></a>按位，或者，和 Xor 运算符  
 下表显示结果的按位数据类型`And`， `Or`，和`Xor`运算符。 请注意，此表是对称;为给定操作数数据类型的组合，结果数据类型是而不考虑操作数的顺序相同。  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Boolean|SByte|Short|Short|Integer|整数|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Integer|整数|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|整数|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|整数|Long|Long|Long|  
|`UShort`|整数|整数|UShort|整数|UShort|整数|UInteger|Long|ULong|  
|`Integer`|整数|整数|整数|整数|整数|整数|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 如果一个操作数为`Decimal`， `Single`， `Double`，或`String`，尝试将其转换为 Visual Basic`Long`之前操作，并且结果数据类型是否相同如果已经过该操作数的`Long`。  
  
## <a name="miscellaneous-operators"></a>其他运算符  
 `&`运算符定义仅的串联`String`操作数。 Visual Basic 将根据需要向每个操作数转换`String`之前此操作，并且结果数据类型为始终`String`。 为了`&`运算符、 到的所有转换`String`被视为扩大转换，即使`Option Strict`是`On`。  
  
 `Is`和`IsNot`运算符需要两个操作数为引用类型。 `TypeOf`...`Is`表达式要求第一个操作数是引用类型，第二个操作数是数据类型的名称。 在所有这些情况下结果数据类型是`Boolean`。  
  
 `Like`运算符仅为模式匹配的定义`String`操作数。 Visual Basic 尝试将根据需要向每个操作数转换`String`操作之前。 结果数据类型始终是`Boolean`。  
  
## <a name="see-also"></a>请参阅  
 [数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [在 Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [在 Visual Basic 中的比较运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [运算符](../../../visual-basic/language-reference/operators/index.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [比较运算符](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)
