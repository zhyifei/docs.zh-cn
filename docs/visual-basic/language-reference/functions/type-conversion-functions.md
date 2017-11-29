---
title: "类型转换函数 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 117cd4ce038a533715bbc86558545f0f223dd149
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="type-conversion-functions-visual-basic"></a>类型转换函数 (Visual Basic)
这些函数已编译的内联，这意味着转换代码，计算表达式的代码的一部分。 有时是没有调用的过程，以完成转换，这将提高性能。 每个函数都强制转换为特定数据类型的表达式。  
  
## <a name="syntax"></a>语法  
  
```  
CBool(expression)  
CByte(expression)  
CChar(expression)  
CDate(expression)  
CDbl(expression)  
CDec(expression)  
CInt(expression)  
CLng(expression)  
CObj(expression)  
CSByte(expression)  
CShort(expression)  
CSng(expression)  
CStr(expression)  
CUInt(expression)  
CULng(expression)  
CUShort(expression)  
```  
  
## <a name="part"></a>部件  
 `expression`  
 必需。 源数据类型的任何表达式。  
  
## <a name="return-value-data-type"></a>返回值的数据类型  
 下表中所示，函数名称将确定它返回的值的数据类型。  
  
|函数名|返回数据类型|范围`expression`自变量|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[Boolean 数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|任何有效`Char`或`String`或数值表达式。|  
|`CByte`|[Byte 数据类型](../../../visual-basic/language-reference/data-types/byte-data-type.md)|0 到 255 （无符号）;小数部分舍入。<sup>1</sup>|  
|`CChar`|[Char 数据类型](../../../visual-basic/language-reference/data-types/char-data-type.md)|任何有效`Char`或`String`表达式; 仅第一个字符的`String`转换; 值可以是 0 到 65535 （无符号）。|  
|`CDate`|[Date 数据类型](../../../visual-basic/language-reference/data-types/date-data-type.md)|任何有效的表示形式的日期和时间。|  
|`CDbl`|[Double 数据类型](../../../visual-basic/language-reference/data-types/double-data-type.md)|-1.79769313486231570 e + 308 到-4.94065645841246544 e-324 负值;最大 4.94065645841246544 e-324 到 1.79769313486231570 e + 308 的正值。|  
|`CDec`|[Decimal 数据类型](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|+ /-79228162514264337593543950335 为零的数字，即，没有小数位的数字。 对于具有 28 位小数的数字，范围为 + /-7.9228162514264337593543950335。 可能的最小的非零值数为 0.0000000000000000000000000001 （+ /-1E-28)。|  
|`CInt`|[Integer 数据类型](../../../visual-basic/language-reference/data-types/integer-data-type.md)|-2147483648 到 2147483647;小数部分舍入。<sup>1</sup>|  
|`CLng`|[Long 数据类型](../../../visual-basic/language-reference/data-types/long-data-type.md)|-9223372036854775808 到 9223372036854775807;小数部分舍入。<sup>1</sup>|  
|`CObj`|[Object 数据类型](../../../visual-basic/language-reference/data-types/object-data-type.md)|任何有效表达式。|  
|`CSByte`|[SByte 数据类型](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|-128 到 127;小数部分舍入。<sup>1</sup>|  
|`CShort`|[Short 数据类型](../../../visual-basic/language-reference/data-types/short-data-type.md)|-32768 到 32767;小数部分舍入。<sup>1</sup>|  
|`CSng`|[Single 数据类型](../../../visual-basic/language-reference/data-types/single-data-type.md)|-3.402823 e + 38 到-1.401298 e-45 负值;1.401298 e-3.402823 e + 38 正值通过 45。|  
|`CStr`|[String 数据类型](../../../visual-basic/language-reference/data-types/string-data-type.md)|返回`CStr`依赖于`expression`自变量。 请参阅[CStr 函数的返回值](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)。|  
|`CUInt`|[UInteger 数据类型](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|0 到 4294967295 （无符号）;小数部分舍入。<sup>1</sup>|  
|`CULng`|[ULong 数据类型](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|0 到 18446744073709551615 （无符号）;小数部分舍入。<sup>1</sup>|  
|`CUShort`|[UShort 数据类型](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|0 到 65535 （无符号）;小数部分舍入。<sup>1</sup>|  
  
 <sup>1</sup>小数部分时可能会出现一个特殊类型的舍入调用*银行家舍入法*。 有关详细信息，请参阅"备注"。  
  
## <a name="remarks"></a>备注  
 一般来说，你应使用 Visual Basic 的类型转换函数的.NET Framework 方法优先如`ToString()`上,<xref:System.Convert>类或单个类型结构或类上。 Visual Basic 函数旨在用于与 Visual Basic 代码的最佳交互，并且它们还使你更短且更易读的源代码。 此外，.NET Framework 的转换方法不始终生成与 Visual Basic 函数，例如转换时相同的结果`Boolean`到`Integer`。 有关详细信息，请参阅[故障排除数据类型](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。  
  
## <a name="behavior"></a>行为  
  
-   **强制。** 通常情况下，你可以使用数据类型转换函数要强制转换到特定的数据类型，而不是默认数据类型的操作的结果。 例如，使用`CDec`强制执行在其中单精度、 双精度或整数算术将要通常发生的情况下的小数运算。  
  
-   **失败的转换。** 如果`expression`传递给函数是外部的数据类型范围它是要转换<xref:System.OverflowException>时发生。  
  
-   **小数部分。** 当将非整型的值转换为整数类型，整数转换函数 (`CByte`， `CInt`， `CLng`， `CSByte`， `CShort`， `CUInt`， `CULng`，和`CUShort`) 删除小数部分和舍入到最接近的整数值。  
  
     如果小数部分正好是 0.5，整数转换函数其舍入为接近的偶数整数。 例如，0.5 舍入为 0，1.5 和 2.5 舍入为 2。 这有时称为*银行家舍入法*，，其目的在于补偿时同时添加许多这样的数字可能会累积的偏差。  
  
     `CInt`和`CLng`与不同<xref:Microsoft.VisualBasic.Conversion.Int%2A>和<xref:Microsoft.VisualBasic.Conversion.Fix%2A>函数，它截断，而不是舍入，大量的小数部分。 此外，`Fix`和`Int`始终返回相同的数据类型的值，当你在通过。  
  
-   **日期/时间转换。** 使用<xref:Microsoft.VisualBasic.Information.IsDate%2A>函数来确定是否可以将一个值转换为日期和时间。 `CDate`识别的日期文本和时间文本，但不是数值。 要转换 Visual Basic 6.0`Date`值赋给`Date`在 Visual Basic 2005 中的值或更高版本，你可以使用<xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType>方法。  
  
-   **非特定日期/时间值。** [日期数据类型](../../../visual-basic/language-reference/data-types/date-data-type.md)始终包含日期和时间信息。 为进行类型转换，Visual Basic 将将 1/1/0001 (年 1 月 1 年 1) 对要*中性值*次要非特定值的日期，和 00:00:00 （午夜）。 如果你转换`Date`值为一个字符串，`CStr`不结果字符串中包括非特定值。 例如，如果你转换`#January 1, 0001 9:30:00#`为一个字符串，结果是"9:30:00 AM"; 取消显示的日期信息。 但是，日期信息是仍然存在于原始`Date`值，并可以使用函数如恢复<xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>函数。  
  
-   **区域性的敏感性。** 涉及到字符串的类型转换函数执行基于应用程序的当前区域性设置的转换。 例如，`CDate`识别根据你的系统区域设置的日期格式。 你必须提供日、 月和年正确顺序为你的区域设置，或可能不正确解释日期。 如果它包含一个星期的字符串，例如"Wednesday"无法识别的长日期格式。  
  
     如果你需要将转换为或从的字符串表示形式的格式不是由你的区域设置中的值，你无法使用 Visual Basic 的类型转换函数。 若要执行此操作，使用`ToString(IFormatProvider)`和`Parse(String, IFormatProvider)`该值的类型的方法。 例如，使用<xref:System.Double.Parse%2A?displayProperty=nameWithType>时将字符串转换`Double`，并使用<xref:System.Double.ToString%2A?displayProperty=nameWithType>转换类型的值时`Double`为字符串。  
  
## <a name="ctype-function"></a>CType Function  
 [CType 函数](../../../visual-basic/language-reference/functions/ctype-function.md)采用第二个自变量， `typename`，并将强制转换`expression`到`typename`，其中`typename`可以是任何数据类型、 结构、 类或接口到存在的有效转换。  
  
 有关的比较`CType`与其他类型转换关键字，请参阅[DirectCast 运算符](../../../visual-basic/language-reference/operators/directcast-operator.md)和[TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)。  
  
## <a name="cbool-example"></a>CBool 示例  
 下面的示例使用`CBool`函数将表达式转换为`Boolean`值。 如果表达式计算结果为非零值，`CBool`返回`True`; 否则为它将返回`False`。  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## <a name="cbyte-example"></a>CByte 示例  
 下面的示例使用`CByte`函数可将对表达式`Byte`。  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## <a name="cchar-example"></a>CChar 示例  
 下面的示例使用`CChar`函数将转换的第一个字符`String`表达式`Char`类型。  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 输入自变量到`CChar`的数据类型必须为`Char`或`String`。 不能使用`CChar`将数字转换为字符，因为`CChar`不能接受数值数据类型。 下面的示例获取表示的代码点 （字符代码） 的数字，并将其转换为对应的字符。 它使用<xref:Microsoft.VisualBasic.Interaction.InputBox%2A>函数来获取的数字，字符串`CInt`要转换的字符串类型`Integer`，和`ChrW`要转换的编号，以键入`Char`。  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## <a name="cdate-example"></a>CDate 示例  
 下面的示例使用`CDate`函数将字符串转换为`Date`值。 一般情况下，不建议硬编码的日期和时间作为字符串 （如本示例中所示）。 使用日期文本和时间的文本，如 #Feb 12，&#1969; 和 # 4:45:23 PM #，而是。  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## <a name="cdbl-example"></a>CDbl 示例  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## <a name="cdec-example"></a>CDec 示例  
 下面的示例使用`CDec`函数将转换为数字值`Decimal`。  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## <a name="cint-example"></a>CInt 示例  
 下面的示例使用`CInt`函数将值转换为`Integer`。  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  
  
## <a name="clng-example"></a>CLng 示例  
 下面的示例使用`CLng`函数以将值转换为`Long`。  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## <a name="cobj-example"></a>使用 CObj 示例  
 下面的示例使用`CObj`函数将转换为数字值`Object`。 `Object`变量本身包含仅一个四个字节的指针，用于指向`Double`分配给它的值。  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## <a name="csbyte-example"></a>CSByte 示例  
 下面的示例使用`CSByte`函数将转换为数字值`SByte`。  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## <a name="cshort-example"></a>CShort 示例  
 下面的示例使用`CShort`函数将转换为数字值`Short`。  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## <a name="csng-example"></a>CSng 示例  
 下面的示例使用`CSng`函数以将值转换为`Single`。  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## <a name="cstr-example"></a>CStr 示例  
 下面的示例使用`CStr`函数将转换为数字值`String`。  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 下面的示例使用`CStr`函数将转换`Date`值复制到`String`值。  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 `CStr`始终呈现`Date`采用当前区域设置，例如，标准短格式的值"6/15/2003年 4:35:47 PM"。 但是，`CStr`取消*中性值*1/1/0001 日期和时间的 00:00:00。  
  
 有关详细信息返回的值`CStr`，请参阅[CStr 函数的返回值](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)。  
  
## <a name="cuint-example"></a>CUInt 示例  
 下面的示例使用`CUInt`函数将转换为数字值`UInteger`。  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## <a name="culng-example"></a>CULng 示例  
 下面的示例使用`CULng`函数将转换为数字值`ULong`。  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## <a name="cushort-example"></a>CUShort 示例  
 下面的示例使用`CUShort`函数将转换为数字值`UShort`。  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 <xref:Microsoft.VisualBasic.Strings.Format%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Oct%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Str%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [转换函数](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [在 Visual Basic 中的类型转换](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
