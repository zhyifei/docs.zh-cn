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
ms.openlocfilehash: 1e42fca7800a76cab10fd60058e34d31ae8b8830
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821650"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="fe550-102">字符串和其他类型之间的转换 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe550-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>
<span data-ttu-id="fe550-103">可以将转换一个数字`Boolean`，或日期/时间值到`String`。</span><span class="sxs-lookup"><span data-stu-id="fe550-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="fe550-104">您还可以将按反向执行转换 — 从为数字、 字符串值`Boolean`，或`Date`— 该字符串的内容可以被解释为有效的目标数据类型的值。</span><span class="sxs-lookup"><span data-stu-id="fe550-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="fe550-105">如果它们不能但将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="fe550-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="fe550-106">所有这些分配，在任一方向的转换收缩转换。</span><span class="sxs-lookup"><span data-stu-id="fe550-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="fe550-107">应使用类型转换关键字 (`CBool`， `CByte`， `CDate`， `CDbl`， `CDec`， `CInt`， `CLng`， `CSByte`， `CShort`， `CSng`， `CStr`，`CUInt`， `CULng`， `CUShort`，和`CType`)。</span><span class="sxs-lookup"><span data-stu-id="fe550-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="fe550-108"><xref:Microsoft.VisualBasic.Strings.Format%2A>和<xref:Microsoft.VisualBasic.Conversion.Val%2A>函数为您提供更多控制权字符串和数字之间的转换。</span><span class="sxs-lookup"><span data-stu-id="fe550-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="fe550-109">如果已定义的类或结构，可以定义类型之间的转换运算符`String`和类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="fe550-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="fe550-110">有关详细信息，请参阅[如何：定义转换运算符](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="fe550-110">For more information, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="fe550-111">数字转换为字符串</span><span class="sxs-lookup"><span data-stu-id="fe550-111">Conversion of Numbers to Strings</span></span>  
 <span data-ttu-id="fe550-112">可以使用`Format`函数将数字转换为带格式字符串，其中可以包含不只是相应的位，但还设置格式符号，例如货币符号 (如`$`)，千位分隔符或*数字分组符号*(如`,`)，和十进制分隔符 (如`.`)。</span><span class="sxs-lookup"><span data-stu-id="fe550-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="fe550-113">`Format` 根据相应的符号将自动使用**区域选项**在 Windows 中指定的设置**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="fe550-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="fe550-114">请注意，串联 (`&`) 运算符可以将数字转换为字符串隐式，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="fe550-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="fe550-115">字符串转换为数字</span><span class="sxs-lookup"><span data-stu-id="fe550-115">Conversion of Strings to Numbers</span></span>  
 <span data-ttu-id="fe550-116">可以使用`Val`函数显式转换为数字的字符串中的数字。</span><span class="sxs-lookup"><span data-stu-id="fe550-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="fe550-117">`Val` 读取字符串，直到它遇到之外的其他数字、 空格、 选项卡中，换行符或句点字符。</span><span class="sxs-lookup"><span data-stu-id="fe550-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="fe550-118">序列"& O"和"& H"alter 数字系统的基数和终止扫描。</span><span class="sxs-lookup"><span data-stu-id="fe550-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="fe550-119">它将停止读取，直到`Val`将所有合适的字符转换为数字值。</span><span class="sxs-lookup"><span data-stu-id="fe550-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="fe550-120">例如，以下语句返回值`141.825`。</span><span class="sxs-lookup"><span data-stu-id="fe550-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="fe550-121">当 Visual Basic 将字符串转换为数字值时，它使用**区域选项**在 Windows 中指定的设置**控制面板**来解释千位分隔符、 小数分隔符和货币符号。</span><span class="sxs-lookup"><span data-stu-id="fe550-121">When Visual Basic converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="fe550-122">这意味着转换可能成功之一但不是能是其他设置。</span><span class="sxs-lookup"><span data-stu-id="fe550-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="fe550-123">例如，`"$14.20"`是可接受的英语 （美国） 区域设置但不是法语区域设置。</span><span class="sxs-lookup"><span data-stu-id="fe550-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe550-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe550-124">See also</span></span>

- [<span data-ttu-id="fe550-125">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="fe550-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="fe550-126">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="fe550-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="fe550-127">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="fe550-127">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="fe550-128">如何：将对象转换为 Visual Basic 中的另一种类型</span><span class="sxs-lookup"><span data-stu-id="fe550-128">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="fe550-129">数组转换</span><span class="sxs-lookup"><span data-stu-id="fe550-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="fe550-130">数据类型</span><span class="sxs-lookup"><span data-stu-id="fe550-130">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="fe550-131">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="fe550-131">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="fe550-132">基于 .NET Framework 的国际应用程序简介</span><span class="sxs-lookup"><span data-stu-id="fe550-132">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
