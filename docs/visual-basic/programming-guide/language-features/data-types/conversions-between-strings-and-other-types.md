---
title: 字符串和其他类型之间的转换 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: e1530c1772808249546b453294fc848c31c1e581
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582936"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>字符串和其他类型之间的转换 (Visual Basic)
您可以将数字、`Boolean` 或日期/时间值转换为 `String`。 还可以反向转换（从字符串值转换为数字、`Boolean` 或 `Date`），前提是字符串的内容可以解释为目标数据类型的有效值。 如果无法运行，则会发生运行时错误。  
  
 所有这些分配的转换均为任意方向，均为收缩转换。 应使用类型转换关键字（`CBool`、`CByte`、`CDate`、`CDbl`、`CDec`、`CInt`、`CLng`、`CSByte`、`CShort`、`CSng`、0、1、2、3 和 4）。 @No__t_0 和 <xref:Microsoft.VisualBasic.Conversion.Val%2A> 函数使你可以更进一步控制字符串和数字之间的转换。  
  
 如果已定义类或结构，则可以定义 `String` 与类或结构的类型之间的类型转换运算符。 有关更多信息，请参见 [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)。  
  
## <a name="conversion-of-numbers-to-strings"></a>将数字转换为字符串  
 您可以使用 `Format` 函数将数字转换为带格式的字符串，该字符串不仅可以包含适当的数字，还可以包含格式符号，如货币符号（如 `$`）、千位分隔符或*数字分组符号*（如 `,`）和十进制分隔符（如 `.`）。 `Format` 根据 Windows**控制面板**中指定的**区域选项**设置自动使用适当的符号。  
  
 请注意，串联（`&`）运算符可以隐式地将数字转换为字符串，如下面的示例所示。  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>将字符串转换为数字  
 您可以使用 `Val` 函数将字符串中的数字显式转换为数字。 `Val` 读取字符串，直到遇到数字、空格、制表符、换行符或句点以外的字符。 序列 "& O" 和 "& H" 改变数值系统的基数，并终止扫描。 在停止读取之前，`Val` 会将所有合适的字符都转换为数值。 例如，下面的语句返回 `141.825` 的值。  
  
 `Val("   14   1.825 miles")`  
  
 当 Visual Basic 将字符串转换为数值时，它将使用 Windows**控制面板**中指定的 "**区域选项**" 设置来解释千位分隔符、小数点分隔符和货币符号。 这意味着，转换可能会在一个设置中失败，而不是另一个设置。 例如，`"$14.20"` 在英语（美国）区域设置中是可接受的，而不是任何法语区域设置。  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [隐式转换和显式转换](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [如何：在 Visual Basic 中将对象转换为另一种类型](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [数组转换](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [数据类型](../../../../visual-basic/language-reference/data-types/index.md)
- [类型转换函数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [基于 .NET Framework 的国际应用程序简介](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
