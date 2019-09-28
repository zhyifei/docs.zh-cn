---
title: 类型转换函数 (Visual Basic)
ms.date: 10/24/2018
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
ms.openlocfilehash: 6b448fa23368f7a0848c44362337b0ccc70b6162
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592077"
---
# <a name="type-conversion-functions-visual-basic"></a>类型转换函数 (Visual Basic)
这些函数是内联编译的，这意味着转换代码是用于计算表达式的代码的一部分。 有时不会调用过程来完成转换，从而提高性能。 每个函数都将表达式强制转换为特定的数据类型。  
  
## <a name="syntax"></a>语法  
  
```vb  
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
  
## <a name="return-value-data-type"></a>返回值数据类型  
 函数名称确定它返回的值的数据类型，如下表所示。  
  
|功能名称|返回数据类型|@No__t-0 参数的范围|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[Boolean 数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|任何有效 `Char` 或 @no__t 或数值表达式。|  
|`CByte`|[Byte 数据类型](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte.MinValue?displayProperty=nameWithType> （0）到 <xref:System.Byte.MaxValue?displayProperty=nameWithType> （255）（无符号）;小数部分被舍入。<sup>1</sup><br/><br/>从 Visual Basic 15.8 开始，Visual Basic 通过 @no__t 的函数优化浮点到字节转换的性能;有关详细信息，请参阅 "[备注](#remarks)" 部分。 有关示例，请参阅[CInt 示例](#cint-example)部分。|  
|`CChar`|[Char 数据类型](../../../visual-basic/language-reference/data-types/char-data-type.md)|任何有效 `Char` 或 `String` 表达式;只转换 `String` 的第一个字符;值可以为0到65535（无符号）。|  
|`CDate`|[Date 数据类型](../../../visual-basic/language-reference/data-types/date-data-type.md)|任何有效的日期和时间表示形式。|  
|`CDbl`|[Double 数据类型](../../../visual-basic/language-reference/data-types/double-data-type.md)|-1.79769313486231570 e + 308 到-4.94065645841246544 E-324 for 负值;4.94065645841246544 e-324 到 1.79769313486231570 E + 308 的正值。|  
|`CDec`|[Decimal 数据类型](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|对于零缩放数字，为 +/-79228162514264337593543950335，即无小数位的数字。 对于包含28位小数位数的数字，范围为 +/-7.9228162514264337593543950335。 可能的最小非零数字为0.0000000000000000000000000001 （+/-1E-28）。|  
|`CInt`|[Integer 数据类型](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32.MinValue?displayProperty=nameWithType> （-2147483648）到 <xref:System.Int32.MaxValue?displayProperty=nameWithType> （2147483647）;小数部分被舍入。<sup>1</sup> <br/><br/>从 Visual Basic 15.8 开始，Visual Basic 通过 @no__t 的函数优化浮点到整数的转换性能;有关详细信息，请参阅 "[备注](#remarks)" 部分。 有关示例，请参阅[CInt 示例](#cint-example)部分。 |  
|`CLng`|[Long 数据类型](../../../visual-basic/language-reference/data-types/long-data-type.md)|<xref:System.Int64.MinValue?displayProperty=nameWithType> （-9223372036854775808）到 <xref:System.Int64.MaxValue?displayProperty=nameWithType> （9223372036854775807）;小数部分被舍入。<sup>1</sup><br/><br/>从 Visual Basic 15.8 开始，Visual Basic 通过 @no__t 的函数优化浮点到64位整数转换的性能;有关详细信息，请参阅 "[备注](#remarks)" 部分。 有关示例，请参阅[CInt 示例](#cint-example)部分。|  
|`CObj`|[Object 数据类型](../../../visual-basic/language-reference/data-types/object-data-type.md)|任何有效表达式。|  
|`CSByte`|[SByte 数据类型](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte.MinValue?displayProperty=nameWithType> （-128）到 <xref:System.SByte.MaxValue?displayProperty=nameWithType> （127）;小数部分被舍入。<sup>1</sup><br/><br/>从 Visual Basic 15.8 开始，Visual Basic 通过 @no__t 的函数优化浮点到带符号字节转换的性能;有关详细信息，请参阅 "[备注](#remarks)" 部分。 有关示例，请参阅[CInt 示例](#cint-example)部分。|  
|`CShort`|[Short 数据类型](../../../visual-basic/language-reference/data-types/short-data-type.md)|<xref:System.Int16.MinValue?displayProperty=nameWithType> （-32768）到 <xref:System.Int16.MaxValue?displayProperty=nameWithType> （32767）;小数部分被舍入。<sup>1</sup><br/><br/>从 Visual Basic 15.8 开始，Visual Basic 通过 @no__t 的函数优化浮点到16位整数转换的性能;有关详细信息，请参阅 "[备注](#remarks)" 部分。 有关示例，请参阅[CInt 示例](#cint-example)部分。|  
|`CSng`|[Single 数据类型](../../../visual-basic/language-reference/data-types/single-data-type.md)|-3.402823 e + 38 到-1.401298 E-45 for 负值;1.401298 e-45 到 3.402823 E + 38 表示正值。|  
|`CStr`|[String 数据类型](../../../visual-basic/language-reference/data-types/string-data-type.md)|@No__t 返回，具体取决于 `expression` 参数。 请参阅[CStr 函数的返回值](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)。|  
|`CUInt`|[UInteger 数据类型](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32.MinValue?displayProperty=nameWithType> （0）到 <xref:System.UInt32.MaxValue?displayProperty=nameWithType> （4294967295）（无符号）;小数部分被舍入。<sup>1</sup><br/><br/>从 Visual Basic 15.8 开始，Visual Basic 通过 @no__t 的函数优化浮点到无符号整数转换的性能;有关详细信息，请参阅 "[备注](#remarks)" 部分。 有关示例，请参阅[CInt 示例](#cint-example)部分。|  
|`CULng`|[ULong 数据类型](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64.MinValue?displayProperty=nameWithType> （0）到 @no__t （18446744073709551615）（无符号）;小数部分被舍入。<sup>1</sup><br/><br/>从 Visual Basic 15.8 开始，Visual Basic 通过 @no__t 的函数优化浮点到无符号长整数转换的性能;有关详细信息，请参阅 "[备注](#remarks)" 部分。 有关示例，请参阅[CInt 示例](#cint-example)部分。|  
|`CUShort`|[UShort 数据类型](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16.MinValue?displayProperty=nameWithType> （0）到 <xref:System.UInt16.MaxValue?displayProperty=nameWithType> （65535）（无符号）;小数部分被舍入。<sup>1</sup><br/><br/>从 Visual Basic 15.8 开始，Visual Basic 通过 @no__t 的函数优化浮点到无符号16位整数转换的性能;有关详细信息，请参阅 "[备注](#remarks)" 部分。 有关示例，请参阅[CInt 示例](#cint-example)部分。|  
  
 <sup>1</sup>小数部分可服从一种特殊类型的舍入，称为 "*银行家舍入*"。 有关详细信息，请参阅 "备注"。  
  
## <a name="remarks"></a>备注  
 作为一种规则，应优先使用 Visual Basic 类型转换函数，以便在 @no__t 1 类上或单个类型结构或类 .NET Framework 方法（如 `ToString()`）。 Visual Basic 函数旨在实现与 Visual Basic 代码的最佳交互，并使源代码更简单、更易于阅读。 此外，.NET Framework 转换方法不会始终产生与 Visual Basic 函数相同的结果，例如，在将 @no__t 0 转换为 `Integer` 时。 有关详细信息，请参阅[数据类型疑难解答](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。  

从 Visual Basic 15.8 开始，当你将以下方法返回的 @no__t 或 <xref:System.Double> 值传递到整数转换函数之一（`CByte`，`CShort`，`CInt`）时，将优化浮点到整数转换的性能 @no__t-sql，@no__t 6，`CUShort`，`CUInt`，`CULng`）：

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

此优化允许执行大量整数转换的代码最多运行两次。 下面的示例阐释了这些优化的浮点到整数转换：

```vb
Dim s As Single = 173.7619
Dim d As Double = s 

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a>行为  
  
- **强制.** 通常，可以使用数据类型转换函数将操作的结果强制转换为特定的数据类型，而不是默认的数据类型。 例如，在通常会发生单精度、双精度或整数运算的情况下，使用 `CDec` 来强制进行十进制运算。  
  
- **转换失败。** 如果传递到函数的 @no__t 0 超出要转换的数据类型的范围，则会出现 @no__t。  
  
- **小数部分。** 将非整数值转换为整型类型时，将删除小数部分，并将值舍入到最接近的整数，@no__t 0，`CInt`，`CLng`，`CSByte`，`CShort`，`CULng`，和 `CUShort`）。  
  
     如果小数部分正好为0.5，则整数转换函数会将其舍入到最接近的偶数。 例如，0.5 舍入为0，1.5 和2.5 都舍入到2。 这有时称为 "*银行家舍入*"，它的目的是为了弥补在一起添加多个这类数字时可能累积的偏差。  
  
     `CInt` 和 `CLng` 与 <xref:Microsoft.VisualBasic.Conversion.Int%2A> 和 @no__t 3 函数不同，这两个函数截断，而不是舍入数字的小数部分。 此外，@no__t 0 和 `Int` 总是返回与传入的数据类型相同的值。  
  
- **日期/时间转换。** 使用 <xref:Microsoft.VisualBasic.Information.IsDate%2A> 函数确定是否可将值转换为日期和时间。 `CDate` 识别日期文本和时间文本，而不是数值。 若要将 Visual Basic 6.0 `Date` 值转换为 Visual Basic 2005 或更高版本中的 @no__t 值，可以使用 @no__t 方法。  
  
- **非特定日期/时间值。** [日期数据类型](../../../visual-basic/language-reference/data-types/date-data-type.md)始终包含日期和时间信息。 出于类型转换的目的，Visual Basic 将1/1/0001 （第1年1月1日）视为日期的*非特定值*，00:00:00 （午夜）为时间的非特定值。 如果将 @no__t 0 值转换为字符串，`CStr` 不在生成的字符串中包含非特定值。 例如，如果将 `#January 1, 0001 9:30:00#` 转换为字符串，则结果为 "9:30:00 AM";禁止显示日期信息。 但是，日期信息仍存在于原始 @no__t 0 值中，可以通过函数（如 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> 函数）进行恢复。  
  
- **区分区域性。** 涉及字符串的类型转换函数根据应用程序的当前区域性设置执行转换。 例如，`CDate` 根据系统的区域设置识别日期格式。 必须以正确的顺序为你的区域设置提供日期、月份和年份，否则可能无法正确解释日期。 如果长日期格式包含一周内的字符串（如 "星期三"），则不能识别该格式。  
  
     如果需要转换为或从值的字符串表示形式转换而不是由区域设置指定的格式，则不能使用 Visual Basic 类型转换函数。 为此，请使用该值的类型的 `ToString(IFormatProvider)` 和 @no__t 方法。 例如，将字符串转换为 @no__t @no__t 时，请使用-0，并在将 `Double` 类型的值转换为字符串时使用 <xref:System.Double.ToString%2A?displayProperty=nameWithType>。  
  
## <a name="ctype-function"></a>CType Function  
 [CType 函数](../../../visual-basic/language-reference/functions/ctype-function.md)使用第二个参数 `typename`，并将 @no__t 强制转换为 `typename`，其中 `typename` 可以是存在有效转换的任何数据类型、结构、类或接口。  
  
 有关 `CType` 与其他类型转换关键字的比较，请参阅[DirectCast operator](../../../visual-basic/language-reference/operators/directcast-operator.md) And [TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)。  
  
## <a name="cbool-example"></a>CBool 示例  
 下面的示例使用 `CBool` 函数将表达式转换为 @no__t 值。 如果表达式的计算结果为非零值，`CBool` 返回 `True`;否则，它将返回 @no__t 2。  
  
 [!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]  
  
## <a name="cbyte-example"></a>CByte 示例  
 下面的示例使用 `CByte` 函数将表达式转换为 @no__t。  
  
 [!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]  
  
## <a name="cchar-example"></a>CChar 示例  
 下面的示例使用 `CChar` 函数将 @no__t 表达式的第一个字符转换为 @no__t 类型。  
  
 [!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]  
  
 @No__t-0 的输入参数的数据类型必须为 `Char` 或 `String`。 不能使用 `CChar` 将数字转换为字符，因为 @no__t 不能接受数字数据类型。 下面的示例获取一个表示码位（字符代码）的数字，并将其转换为相应的字符。 它使用 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> 函数获取数字的字符串，`CInt` 以将字符串转换为类型 `Integer`，将 `ChrW` 转换为类型 @no__t。  
  
 [!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]  
  
## <a name="cdate-example"></a>CDate 示例  
 下面的示例使用 `CDate` 函数将字符串转换为 `Date` 值。 通常，不建议将日期和时间作为字符串进行硬编码（如本示例所示）。 改为使用日期文本和时间文本（如 #Feb 12、1969 # 和 #4： 45:23 PM #）。  
  
 [!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]  
  
## <a name="cdbl-example"></a>CDbl 示例  
 [!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]  
  
## <a name="cdec-example"></a>CDec 示例  
 下面的示例使用 `CDec` 函数将数值转换为 `Decimal`。  
  
 [!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]  
  
## <a name="cint-example"></a>CInt 示例  
 下面的示例使用 `CInt` 函数将值转换为 `Integer`。  
  
 [!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]  

## <a name="clng-example"></a>CLng 示例
 下面的示例使用 `CLng` 函数将值转换为 `Long`。  
  
 [!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]  
  
## <a name="cobj-example"></a>CObj 示例  
 下面的示例使用 `CObj` 函数将数值转换为 `Object`。 @No__t 0 变量本身只包含一个四字节指针，该指针指向分配给它的 @no__t 1 值。  
  
 [!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]  
  
## <a name="csbyte-example"></a>CSByte 示例  
 下面的示例使用 `CSByte` 函数将数值转换为 `SByte`。  
  
 [!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]  
  
## <a name="cshort-example"></a>CShort 示例  
 下面的示例使用 `CShort` 函数将数值转换为 `Short`。  
  
 [!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]  
  
## <a name="csng-example"></a>CSng 示例  
 下面的示例使用 `CSng` 函数将值转换为 `Single`。  
  
 [!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]  
  
## <a name="cstr-example"></a>CStr 示例  
 下面的示例使用 `CStr` 函数将数值转换为 `String`。  
  
 [!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]  
  
 下面的示例使用 `CStr` 函数将 @no__t 值转换为 @no__t 值。  
  
 [!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]  
  
 `CStr` 始终以标准短格式呈现当前区域设置的 @no__t 值，例如 "6/15/2003 4:35:47 PM"。 不过，`CStr` 会将日期和00:00:00 的*非特定值*取消为1/1/0001。  
  
 有关 @no__t 返回的值的更多详细信息，请参阅[CStr 函数的返回值](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)。  
  
## <a name="cuint-example"></a>CUInt 示例  
 下面的示例使用 `CUInt` 函数将数值转换为 `UInteger`。  
  
 [!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]  
  
## <a name="culng-example"></a>CULng 示例  
 下面的示例使用 `CULng` 函数将数值转换为 `ULong`。  
  
 [!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]  
  
## <a name="cushort-example"></a>CUShort 示例  
 下面的示例使用 `CUShort` 函数将数值转换为 `UShort`。  
  
 [!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [转换函数](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [Visual Basic 中的类型转换](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
