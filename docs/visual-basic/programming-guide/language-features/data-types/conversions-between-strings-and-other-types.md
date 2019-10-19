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
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="bdd01-102">字符串和其他类型之间的转换 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdd01-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>
<span data-ttu-id="bdd01-103">您可以将数字、`Boolean` 或日期/时间值转换为 `String`。</span><span class="sxs-lookup"><span data-stu-id="bdd01-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="bdd01-104">还可以反向转换（从字符串值转换为数字、`Boolean` 或 `Date`），前提是字符串的内容可以解释为目标数据类型的有效值。</span><span class="sxs-lookup"><span data-stu-id="bdd01-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="bdd01-105">如果无法运行，则会发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="bdd01-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="bdd01-106">所有这些分配的转换均为任意方向，均为收缩转换。</span><span class="sxs-lookup"><span data-stu-id="bdd01-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="bdd01-107">应使用类型转换关键字（`CBool`、`CByte`、`CDate`、`CDbl`、`CDec`、`CInt`、`CLng`、`CSByte`、`CShort`、`CSng`、0、1、2、3 和 4）。</span><span class="sxs-lookup"><span data-stu-id="bdd01-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="bdd01-108">@No__t_0 和 <xref:Microsoft.VisualBasic.Conversion.Val%2A> 函数使你可以更进一步控制字符串和数字之间的转换。</span><span class="sxs-lookup"><span data-stu-id="bdd01-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="bdd01-109">如果已定义类或结构，则可以定义 `String` 与类或结构的类型之间的类型转换运算符。</span><span class="sxs-lookup"><span data-stu-id="bdd01-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="bdd01-110">有关更多信息，请参见 [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="bdd01-110">For more information, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="bdd01-111">将数字转换为字符串</span><span class="sxs-lookup"><span data-stu-id="bdd01-111">Conversion of Numbers to Strings</span></span>  
 <span data-ttu-id="bdd01-112">您可以使用 `Format` 函数将数字转换为带格式的字符串，该字符串不仅可以包含适当的数字，还可以包含格式符号，如货币符号（如 `$`）、千位分隔符或*数字分组符号*（如 `,`）和十进制分隔符（如 `.`）。</span><span class="sxs-lookup"><span data-stu-id="bdd01-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="bdd01-113">`Format` 根据 Windows**控制面板**中指定的**区域选项**设置自动使用适当的符号。</span><span class="sxs-lookup"><span data-stu-id="bdd01-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="bdd01-114">请注意，串联（`&`）运算符可以隐式地将数字转换为字符串，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="bdd01-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="bdd01-115">将字符串转换为数字</span><span class="sxs-lookup"><span data-stu-id="bdd01-115">Conversion of Strings to Numbers</span></span>  
 <span data-ttu-id="bdd01-116">您可以使用 `Val` 函数将字符串中的数字显式转换为数字。</span><span class="sxs-lookup"><span data-stu-id="bdd01-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="bdd01-117">`Val` 读取字符串，直到遇到数字、空格、制表符、换行符或句点以外的字符。</span><span class="sxs-lookup"><span data-stu-id="bdd01-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="bdd01-118">序列 "& O" 和 "& H" 改变数值系统的基数，并终止扫描。</span><span class="sxs-lookup"><span data-stu-id="bdd01-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="bdd01-119">在停止读取之前，`Val` 会将所有合适的字符都转换为数值。</span><span class="sxs-lookup"><span data-stu-id="bdd01-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="bdd01-120">例如，下面的语句返回 `141.825` 的值。</span><span class="sxs-lookup"><span data-stu-id="bdd01-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="bdd01-121">当 Visual Basic 将字符串转换为数值时，它将使用 Windows**控制面板**中指定的 "**区域选项**" 设置来解释千位分隔符、小数点分隔符和货币符号。</span><span class="sxs-lookup"><span data-stu-id="bdd01-121">When Visual Basic converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="bdd01-122">这意味着，转换可能会在一个设置中失败，而不是另一个设置。</span><span class="sxs-lookup"><span data-stu-id="bdd01-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="bdd01-123">例如，`"$14.20"` 在英语（美国）区域设置中是可接受的，而不是任何法语区域设置。</span><span class="sxs-lookup"><span data-stu-id="bdd01-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd01-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdd01-124">See also</span></span>

- [<span data-ttu-id="bdd01-125">Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="bdd01-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="bdd01-126">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="bdd01-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="bdd01-127">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="bdd01-127">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="bdd01-128">如何：在 Visual Basic 中将对象转换为另一种类型</span><span class="sxs-lookup"><span data-stu-id="bdd01-128">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="bdd01-129">数组转换</span><span class="sxs-lookup"><span data-stu-id="bdd01-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="bdd01-130">数据类型</span><span class="sxs-lookup"><span data-stu-id="bdd01-130">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="bdd01-131">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="bdd01-131">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="bdd01-132">基于 .NET Framework 的国际应用程序简介</span><span class="sxs-lookup"><span data-stu-id="bdd01-132">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
