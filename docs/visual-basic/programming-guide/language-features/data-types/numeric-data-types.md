---
title: 数值型数据类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- integral types [Visual Basic], Visual Basic
- Short data type [Visual Basic], numeric data types
- Double data type [Visual Basic], numeric data types
- Long data type [Visual Basic], Visual Basic numeric data types
- numbers [Visual Basic], whole
- fractions
- numbers
- whole numbers
- integer numbers
- numbers [Visual Basic], integer
- fractional data types [Visual Basic]
- mantissas, of fractional numbers
- mantissas
- data types [Visual Basic], numeric
- Integer data type [Visual Basic], numeric data types
- exponent, of fractional numbers
- integers [Visual Basic]
- numeric data types [Visual Basic], Visual Basic
- Single data type [Visual Basic], numeric types
- Decimal data type [Visual Basic], numeric data types
ms.assetid: a27bd4d0-7e14-43eb-9cc4-b42eaab323c9
ms.openlocfilehash: 8fa88172c9914a071e1b24e959c9030e6d219a30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="numeric-data-types-visual-basic"></a>数值型数据类型 (Visual Basic)
Visual Basic 提供几个*数值数据类型*来处理在各种表示形式之间的数字。 *整型*类型只表示整数 （正数、 负数和零），和*nonintegral*类型带有整数和小数部分表示的数字。  
  
 显示 Visual Basic 数据类型的并排显示比较的表，请参阅[数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)。  
  
## <a name="integral-numeric-types"></a>整型数值类型  
 *整数数据类型*是指那些表示只有其中没有小数部分的数字。  
  
 *签名*整数数据类型是[SByte 数据类型](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)（8 位）、 [Short 数据类型](../../../../visual-basic/language-reference/data-types/short-data-type.md)（16 位）、[整数数据类型](../../../../visual-basic/language-reference/data-types/integer-data-type.md)（32-位） 和[Long 数据类型](../../../../visual-basic/language-reference/data-types/long-data-type.md)（64 位）。 如果某个变量总是存储整数而不是小数数字，将其声明为这些类型之一。  
  
 *无符号*整型[Byte 数据类型](../../../../visual-basic/language-reference/data-types/byte-data-type.md)（8 位）、 [UShort 数据类型](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)（16 位）、 [UInteger 数据类型](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)（32-位） 和[ULong 数据类型](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)（64 位）。 如果变量包含二进制数据或未知的性质的数据，将其声明为这些类型之一。  
  
### <a name="performance"></a>性能  
 算术运算是更快于整数类型比其他数据类型。 它们是使用最快`Integer`和`UInteger`Visual Basic 中的类型。  
  
### <a name="large-integers"></a>大整数  
 如果你需要存储的整数大于`Integer`可以容纳的数据类型，则可以使用`Long`数据类型。 `Long` 变量可以存储从-9223372036854775808 到 9223372036854775807 数字。 操作`Long`时速度稍慢比使用`Integer`。  
  
 如果你需要更大的值，则可以使用[十进制数据类型](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)。 你可以按住从-79228162514264337593543950335 到 79228162514264337593543950335 的数字`Decimal`变量，如果不使用任何小数位数。 但是，与操作`Decimal`的数字是显著变慢于与任何其他数值数据类型。  
  
### <a name="small-integers"></a>小整数  
 如果你不需要的完整范围的`Integer`数据类型，则可以使用`Short`数据类型，它可以包含从-32768 到 32767 的整数。 对于最小的整数范围，`SByte`数据类型包含从-128 到 127。 如果你有大量的变量包含小整数，公共语言运行时可以有时存储你`Short`和`SByte`变量更有效地，以节省内存消耗。 但是，与操作`Short`和`SByte`稍慢一些比使用`Integer`。  
  
### <a name="unsigned-integers"></a>无符号的整数  
 如果你知道你的变量永远不需要保存为负数，则可以使用*无符号类型*`Byte`， `UShort`， `UInteger`，和`ULong`。 上述每种数据类型可以存储的正整数大小的两倍作为其相应的有符号类型 (`SByte`， `Short`， `Integer`，和`Long`)。 就性能来说，每个无符号的类型是效率其相应的有符号类型一样。 具体而言，`UInteger`与共享`Integer`都被认为最有效的所有基本数值数据类型。  
  
## <a name="nonintegral-numeric-types"></a>非整型数值类型  
 *非整型数据类型*是表示整数和小数部分的数字。  
  
 非整型的数值数据类型是`Decimal`（128 位固定点）[单一数据类型](../../../../visual-basic/language-reference/data-types/single-data-type.md)（32 位浮点） 和[Double 数据类型](../../../../visual-basic/language-reference/data-types/double-data-type.md)（64 位浮点数）。 它们是已全部签名的类型。 如果变量可以包含一小部分，将其声明为这些类型之一。  
  
 `Decimal` 不是浮点数据类型。 `Decimal` 数字具有二进制整数值和一个指定值的哪些部分是小数部分的整数缩放因子。  
  
 你可以使用`Decimal`货币值的变量。 优点是值的精度。 `Double`数据类型速度更快，需要较少的内存，但它可能会发生舍入误差。 `Decimal`数据类型将保留完整精确到 28 位小数。  
  
 浮点 (`Single`和`Double`) 的数字会更大范围比`Decimal`数字，但可能会出现舍入误差。 浮点类型支持有效位比`Decimal`但可以表示更大的值。  
  
 非整型的数字值可以表示为 mmmEeee，在 mmm 即*尾数*（有效位数） 和电气是*指数*（10 的幂）。 非整型类型的最高正值是为 7.9228162514264337593543950335 e + 28 `Decimal`，3.4028235 e + 38 个`Single`，1.79769313486231570 e + 308 `Double`。  
  
### <a name="performance"></a>性能  
 `Double` 是效率最高的小数部分组成的数据类型中，因为在当前平台上的处理器执行以双精度浮点运算。 但是，与操作`Double`速度与整数类型，例如`Integer`。  
  
### <a name="small-magnitudes"></a>小量值  
 对于具有可能的最小大小 （接近 0），数字`Double`变量可以存储的数字越小越-4.94065645841246544 e-324 负值和最大 4.94065645841246544 e-324 的正值。  
  
### <a name="small-fractional-numbers"></a>小的小数数字  
 如果你不需要的完整范围的`Double`数据类型，则可以使用`Single`数据类型，它包含从-3.4028235 e + 38 到 3.4028235 e + 38 浮点数。 最小最小量值为`Single`变量为-1.401298 e-为负值，1.401298 e 45-45 正值。 如果你有大量的存储小的浮点数的变量，公共语言运行时可以有时存储你`Single`变量更有效地，以节省内存消耗。  
  
## <a name="see-also"></a>请参阅  
 [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [字符数据类型](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [杂项数据类型](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)  
 [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [如何：调用采用无符号类型的 Windows 函数](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
