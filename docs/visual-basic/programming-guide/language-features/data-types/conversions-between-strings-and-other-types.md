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
ms.openlocfilehash: 40a28d664bc6ed3d094ccc7c342d6411fe88fd7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>字符串和其他类型之间的转换 (Visual Basic)
你可以将转换数字， `Boolean`，或日期/时间值到`String`。 你还可以将按反方向转换 — 从为数字、 字符串值`Boolean`，或`Date`-提供字符串的内容可以解释为有效的目标数据类型的值。 如果它们不能出现运行时错误。  
  
 所有这些分配，在任一方向的转换收缩转换。 应使用类型转换关键字 (`CBool`， `CByte`， `CDate`， `CDbl`， `CDec`， `CInt`， `CLng`， `CSByte`， `CShort`， `CSng`， `CStr`，`CUInt`， `CULng`， `CUShort`，和`CType`)。 <xref:Microsoft.VisualBasic.Strings.Format%2A>和<xref:Microsoft.VisualBasic.Conversion.Val%2A>函数可为你提供其他控制字符串和数字之间的转换。  
  
 如果已定义类或结构，你可以定义类型之间的转换运算符`String`和你的类或结构的类型。 有关详细信息，请参阅[如何： 定义转换运算符](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)。  
  
## <a name="conversion-of-numbers-to-strings"></a>数字转换为字符串  
 你可以使用`Format`函数将数字转换为格式字符串，其中可以包括不仅相应的数字，但格式化符号，如货币符号 (如`$`)，千位分隔符或*数字分组符号*(如`,`)，和小数点分隔符 (如`.`)。 `Format` 会自动使用根据相应的符号**区域选项**Windows 中指定的设置**控制面板**。  
  
 请注意，串联 (`&`) 运算符可以转换为字符串的数字隐式，如以下示例所示。  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>字符串转换为数字  
 你可以使用`Val`函数来显式转换为数字的字符串中的数字。 `Val` 读取字符串，直到它遇到之外的其他数字、 空格、 选项卡、 换行符或句点字符。 序列"& O"和"& H"alter 数字系统的基数并终止扫描。 在停止读取之前,`Val`将所有合适的字符转换为数字值。 例如，以下语句返回的值`141.825`。  
  
 `Val("   14   1.825 miles")`  
  
 当 Visual Basic 将字符串转换为数字值时，它会使用**区域选项**Windows 中指定的设置**控制面板**解释千位分隔符、 小数分隔符和货币符号。 这意味着转换可能会成功下一个但不是能是其他设置。 例如，`"$14.20"`是可接受的英语 （美国） 区域设置中但不是在任何法语的区域设置。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [隐式转换和显式转换](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [如何： 将对象转换为在 Visual Basic 中的另一种类型](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [数组转换](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [类型转换函数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [基于 .NET Framework 的国际应用程序简介](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
