---
title: "字符串和其他类型 (Visual Basic 中) 之间的转换 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data type conversion, string
- conversions, type
- string conversion
- conversions, data type
- type conversion, string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 34eb32cb6e640d681db6853aaa164d84acca7e4f
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="81fc4-102">字符串和其他类型之间的转换 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81fc4-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>
<span data-ttu-id="81fc4-103">您可以将数值转换`Boolean`，或日期/时间值到`String`。</span><span class="sxs-lookup"><span data-stu-id="81fc4-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="81fc4-104">您也可以反向执行转换，从为数字、 字符串值`Boolean`，或`Date`— 字符串的内容可以被解释为目标数据类型的有效值。</span><span class="sxs-lookup"><span data-stu-id="81fc4-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="81fc4-105">如果无法转换，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="81fc4-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="81fc4-106">所有这些分配，在任一方向的转换收缩转换。</span><span class="sxs-lookup"><span data-stu-id="81fc4-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="81fc4-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span><span class="sxs-lookup"><span data-stu-id="81fc4-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="81fc4-108"><xref:Microsoft.VisualBasic.Strings.Format%2A>和<xref:Microsoft.VisualBasic.Conversion.Val%2A>函数为您提供更多控制权字符串和数字之间的转换。</xref:Microsoft.VisualBasic.Conversion.Val%2A> </xref:Microsoft.VisualBasic.Strings.Format%2A></span><span class="sxs-lookup"><span data-stu-id="81fc4-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="81fc4-109">如果已定义的类或结构，您可以定义类型之间的转换运算符`String`和类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="81fc4-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="81fc4-110">有关详细信息，请参阅[如何︰ 定义转换运算符](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="81fc4-110">For more information, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="81fc4-111">数字转换为字符串</span><span class="sxs-lookup"><span data-stu-id="81fc4-111">Conversion of Numbers to Strings</span></span>  
 <span data-ttu-id="81fc4-112">您可以使用`Format`函数将数字转换为带格式的字符串，其中可以包括不仅相应的数字，但格式化符号，如货币符号 (如`$`)，千位分隔符或*数字分组符号*(如`,`)，和小数点分隔符 (如`.`)。</span><span class="sxs-lookup"><span data-stu-id="81fc4-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="81fc4-113">`Format`根据相应的符号将自动使用**区域选项**Windows 中指定的设置**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="81fc4-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="81fc4-114">请注意，串联 (`&`) 运算符可以将数字转换为字符串隐式，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="81fc4-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="81fc4-115">字符串转换为数字</span><span class="sxs-lookup"><span data-stu-id="81fc4-115">Conversion of Strings to Numbers</span></span>  
 <span data-ttu-id="81fc4-116">您可以使用`Val`函数来显式转换为数字的字符串中的数字。</span><span class="sxs-lookup"><span data-stu-id="81fc4-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="81fc4-117">`Val`读取字符串，直到它遇到数字、 空格、 选项卡上，换行符或句点以外的字符。</span><span class="sxs-lookup"><span data-stu-id="81fc4-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="81fc4-118">序列"< O"和"< H"alter 数字系统的基数和终止扫描。</span><span class="sxs-lookup"><span data-stu-id="81fc4-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="81fc4-119">在停止读取，直到`Val`将所有合适的字符转换为数字值。</span><span class="sxs-lookup"><span data-stu-id="81fc4-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="81fc4-120">例如，下面的语句返回的值`141.825`。</span><span class="sxs-lookup"><span data-stu-id="81fc4-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="81fc4-121">当[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]将字符串转换为数字值，它使用**区域选项**Windows 中指定的设置**控制面板**来解释千位分隔符、 小数分隔符和货币符号。</span><span class="sxs-lookup"><span data-stu-id="81fc4-121">When [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="81fc4-122">这意味着转换可能成功下一项但不是能是其他设置。</span><span class="sxs-lookup"><span data-stu-id="81fc4-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="81fc4-123">例如，`"$14.20"`是可以接受的英语 （美国） 区域设置中但不是在法语区域设置。</span><span class="sxs-lookup"><span data-stu-id="81fc4-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81fc4-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81fc4-124">See Also</span></span>  
 <span data-ttu-id="81fc4-125">[在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="81fc4-125">[Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="81fc4-126"> [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="81fc4-126"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span></span>  
<span data-ttu-id="81fc4-127"> [隐式和显式转换](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="81fc4-127"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="81fc4-128"> [如何︰ 将对象转换为另一种类型在 Visual Basic 中](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span><span class="sxs-lookup"><span data-stu-id="81fc4-128"> [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span></span>  
<span data-ttu-id="81fc4-129"> [数组转换](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="81fc4-129"> [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md) </span></span>  
<span data-ttu-id="81fc4-130"> [数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="81fc4-130"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="81fc4-131"> [类型转换函数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="81fc4-131"> [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="81fc4-132"> [基于 .NET Framework 的国际应用程序简介](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)</span><span class="sxs-lookup"><span data-stu-id="81fc4-132"> [Introduction to International Applications Based on the .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)</span></span>
