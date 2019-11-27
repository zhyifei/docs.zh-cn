---
title: 字符串函数
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 2608159e28ee63a0fdb10c82054fd65efe79ac62
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349983"
---
# <a name="string-functions-visual-basic"></a><span data-ttu-id="073c4-102">字符串函数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="073c4-102">String Functions (Visual Basic)</span></span>

<span data-ttu-id="073c4-103">下表列出了在 <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> 类中 Visual Basic 提供的用于搜索和操作字符串的函数。</span><span class="sxs-lookup"><span data-stu-id="073c4-103">The following table lists the functions that Visual Basic provides in the <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> class to search and manipulate strings.</span></span> <span data-ttu-id="073c4-104">它们可以视为 Visual Basic 内部函数;也就是说，您不必将它们作为类的显式成员进行调用，如示例所示。</span><span class="sxs-lookup"><span data-stu-id="073c4-104">They can be regarded as Visual Basic intrinsic functions; that is, you do not have to call them as explicit members of a class, as the examples show.</span></span> <span data-ttu-id="073c4-105">在某些情况下，附加方法（在某些情况下为互补方法）在 <xref:System.String?displayProperty=nameWithType> 类中提供。</span><span class="sxs-lookup"><span data-stu-id="073c4-105">Additional methods, and in some cases complementary methods, are available in the <xref:System.String?displayProperty=nameWithType> class.</span></span>

|<span data-ttu-id="073c4-106">.NET Framework 方法</span><span class="sxs-lookup"><span data-stu-id="073c4-106">.NET Framework method</span></span>|<span data-ttu-id="073c4-107">说明</span><span class="sxs-lookup"><span data-stu-id="073c4-107">Description</span></span>|
|---------------------------|-----------------|
|<span data-ttu-id="073c4-108"><xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="073c4-108"><xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A></span></span>|<span data-ttu-id="073c4-109">返回一个 `Integer` 值，该值表示与某个字符相对应的字符代码。</span><span class="sxs-lookup"><span data-stu-id="073c4-109">Returns an `Integer` value representing the character code corresponding to a character.</span></span>|
|<span data-ttu-id="073c4-110"><xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A></span><span class="sxs-lookup"><span data-stu-id="073c4-110"><xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A></span></span>|<span data-ttu-id="073c4-111">返回与指定字符代码关联的字符。</span><span class="sxs-lookup"><span data-stu-id="073c4-111">Returns the character associated with the specified character code.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|<span data-ttu-id="073c4-112">返回一个从零开始的数组，其中包含基于指定筛选条件的 `String` 数组的子集。</span><span class="sxs-lookup"><span data-stu-id="073c4-112">Returns a zero-based array containing a subset of a `String` array based on specified filter criteria.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|<span data-ttu-id="073c4-113">返回根据格式 `String` 表达式中包含的指令设置格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="073c4-113">Returns a string formatted according to instructions contained in a format `String` expression.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|<span data-ttu-id="073c4-114">返回使用系统控制面板中定义的货币符号格式化为货币值的表达式。</span><span class="sxs-lookup"><span data-stu-id="073c4-114">Returns an expression formatted as a currency value using the currency symbol defined in the system control panel.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|<span data-ttu-id="073c4-115">返回表示日期/时间值的字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="073c4-115">Returns a string expression representing a date/time value.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|<span data-ttu-id="073c4-116">返回格式化为数字的表达式。</span><span class="sxs-lookup"><span data-stu-id="073c4-116">Returns an expression formatted as a number.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|<span data-ttu-id="073c4-117">返回以 % 字符结尾的百分比格式的表达式（即乘以 100）。</span><span class="sxs-lookup"><span data-stu-id="073c4-117">Returns an expression formatted as a percentage (that is, multiplied by 100) with a trailing % character.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|<span data-ttu-id="073c4-118">返回一个整数，该整数指定一个字符串在另一个字符串中首次出现的开始位置。</span><span class="sxs-lookup"><span data-stu-id="073c4-118">Returns an integer specifying the start position of the first occurrence of one string within another.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|<span data-ttu-id="073c4-119">返回一个字符串在另一个字符串中的第一个匹配项的位置（从字符串的右侧开始）。</span><span class="sxs-lookup"><span data-stu-id="073c4-119">Returns the position of the first occurrence of one string within another, starting from the right side of the string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|<span data-ttu-id="073c4-120">返回通过联接数组中包含的多个子字符串而创建的字符串。</span><span class="sxs-lookup"><span data-stu-id="073c4-120">Returns a string created by joining a number of substrings contained in an array.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|<span data-ttu-id="073c4-121">返回转换为小写形式的字符串或字符。</span><span class="sxs-lookup"><span data-stu-id="073c4-121">Returns a string or character converted to lowercase.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|<span data-ttu-id="073c4-122">返回一个字符串，该字符串包含从字符串左侧开始的指定数量的字符。</span><span class="sxs-lookup"><span data-stu-id="073c4-122">Returns a string containing a specified number of characters from the left side of a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|<span data-ttu-id="073c4-123">返回一个整数，该整数包含字符串中的字符数。</span><span class="sxs-lookup"><span data-stu-id="073c4-123">Returns an integer that contains the number of characters in a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|<span data-ttu-id="073c4-124">返回一个左对齐字符串，该字符串包含调整为指定长度的指定字符串。</span><span class="sxs-lookup"><span data-stu-id="073c4-124">Returns a left-aligned string containing the specified string adjusted to the specified length.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|<span data-ttu-id="073c4-125">返回一个字符串，该字符串包含不带前导空格的指定字符串的副本。</span><span class="sxs-lookup"><span data-stu-id="073c4-125">Returns a string containing a copy of a specified string with no leading spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|<span data-ttu-id="073c4-126">返回一个字符串，该字符串包含字符串中指定数目的字符。</span><span class="sxs-lookup"><span data-stu-id="073c4-126">Returns a string containing a specified number of characters from a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|<span data-ttu-id="073c4-127">返回一个字符串，其中指定的子字符串已替换为指定次数的另一个子字符串。</span><span class="sxs-lookup"><span data-stu-id="073c4-127">Returns a string in which a specified substring has been replaced with another substring a specified number of times.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|<span data-ttu-id="073c4-128">返回一个字符串，该字符串包含从字符串的右侧开始的指定数量的字符。</span><span class="sxs-lookup"><span data-stu-id="073c4-128">Returns a string containing a specified number of characters from the right side of a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|<span data-ttu-id="073c4-129">返回一个右对齐字符串，该字符串包含调整为指定长度的指定字符串。</span><span class="sxs-lookup"><span data-stu-id="073c4-129">Returns a right-aligned string containing the specified string adjusted to the specified length.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|<span data-ttu-id="073c4-130">返回一个字符串，该字符串包含不带尾随空格的指定字符串的副本。</span><span class="sxs-lookup"><span data-stu-id="073c4-130">Returns a string containing a copy of a specified string with no trailing spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|<span data-ttu-id="073c4-131">返回由指定数量的空格组成的字符串。</span><span class="sxs-lookup"><span data-stu-id="073c4-131">Returns a string consisting of the specified number of spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|<span data-ttu-id="073c4-132">返回包含指定数量子字符串的从零开始的一维数组。</span><span class="sxs-lookup"><span data-stu-id="073c4-132">Returns a zero-based, one-dimensional array containing a specified number of substrings.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|<span data-ttu-id="073c4-133">基于字符串比较的结果，返回-1、0或1。</span><span class="sxs-lookup"><span data-stu-id="073c4-133">Returns -1, 0, or 1, based on the result of a string comparison.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|<span data-ttu-id="073c4-134">返回根据指定进行转换的字符串。</span><span class="sxs-lookup"><span data-stu-id="073c4-134">Returns a string converted as specified.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|<span data-ttu-id="073c4-135">返回由指定字符重复指定次数而构成的字符串或对象。</span><span class="sxs-lookup"><span data-stu-id="073c4-135">Returns a string or object consisting of the specified character repeated the specified number of times.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|<span data-ttu-id="073c4-136">返回指定字符串的字符顺序相反的字符串。</span><span class="sxs-lookup"><span data-stu-id="073c4-136">Returns a string in which the character order of a specified string is reversed.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|<span data-ttu-id="073c4-137">返回一个字符串，该字符串包含不带前导空格或尾随空格的指定字符串的副本。</span><span class="sxs-lookup"><span data-stu-id="073c4-137">Returns a string containing a copy of a specified string with no leading or trailing spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|<span data-ttu-id="073c4-138">返回包含转换为大写的指定字符串的字符串或字符。</span><span class="sxs-lookup"><span data-stu-id="073c4-138">Returns a string or character containing the specified string converted to uppercase.</span></span>|

<span data-ttu-id="073c4-139">您可以使用[Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)语句来设置是使用不区分大小写的文本排序顺序来比较字符串，而不区分大小写的文本排序顺序由系统的区域设置（`Text`）或字符的内部二进制表示形式（`Binary`）确定。</span><span class="sxs-lookup"><span data-stu-id="073c4-139">You can use the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) statement to set whether strings are compared using a case-insensitive text sort order determined by your system's locale (`Text`) or by the internal binary representations of the characters (`Binary`).</span></span> <span data-ttu-id="073c4-140">默认的文本比较方法是 `Binary`。</span><span class="sxs-lookup"><span data-stu-id="073c4-140">The default text comparison method is `Binary`.</span></span>

## <a name="example-ucase"></a><span data-ttu-id="073c4-141">示例： UCase</span><span class="sxs-lookup"><span data-stu-id="073c4-141">Example: UCase</span></span>

<span data-ttu-id="073c4-142">此示例使用 `UCase` 函数返回字符串的大写形式。</span><span class="sxs-lookup"><span data-stu-id="073c4-142">This example uses the `UCase` function to return an uppercase version of a string.</span></span>
[!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]

## <a name="example-ltrim"></a><span data-ttu-id="073c4-143">示例： LTrim</span><span class="sxs-lookup"><span data-stu-id="073c4-143">Example: LTrim</span></span>

<span data-ttu-id="073c4-144">此示例使用 `LTrim` 函数去除前导空格，并使用 `RTrim` 函数去除字符串变量中的尾随空格。</span><span class="sxs-lookup"><span data-stu-id="073c4-144">This example uses the `LTrim` function to strip leading spaces and the `RTrim` function to strip trailing spaces from a string variable.</span></span> <span data-ttu-id="073c4-145">它使用 `Trim` 函数来去除这两种类型的空格。</span><span class="sxs-lookup"><span data-stu-id="073c4-145">It uses the `Trim` function to strip both types of spaces.</span></span>

[!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]

## <a name="example-mid"></a><span data-ttu-id="073c4-146">示例： Mid</span><span class="sxs-lookup"><span data-stu-id="073c4-146">Example: Mid</span></span>

<span data-ttu-id="073c4-147">此示例使用 `Mid` 函数从字符串返回指定数目的字符。</span><span class="sxs-lookup"><span data-stu-id="073c4-147">This example uses the `Mid` function to return a specified number of characters from a string.</span></span>

[!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]

## <a name="example-len"></a><span data-ttu-id="073c4-148">示例： Len</span><span class="sxs-lookup"><span data-stu-id="073c4-148">Example: Len</span></span>

<span data-ttu-id="073c4-149">此示例使用 `Len` 返回字符串中的字符数。</span><span class="sxs-lookup"><span data-stu-id="073c4-149">This example uses `Len` to return the number of characters in a string.</span></span>

[!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]

## <a name="example-instr"></a><span data-ttu-id="073c4-150">示例： InStr</span><span class="sxs-lookup"><span data-stu-id="073c4-150">Example: InStr</span></span>

<span data-ttu-id="073c4-151">此示例使用 `InStr` 函数返回一个字符串在另一个字符串中的第一个匹配项的位置。</span><span class="sxs-lookup"><span data-stu-id="073c4-151">This example uses the `InStr` function to return the position of the first occurrence of one string within another.</span></span>

[!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]

## <a name="example-format"></a><span data-ttu-id="073c4-152">示例：格式</span><span class="sxs-lookup"><span data-stu-id="073c4-152">Example: Format</span></span>

<span data-ttu-id="073c4-153">此示例演示 `Format` 函数使用 `String` 格式和用户定义格式设置值格式的各种用法。</span><span class="sxs-lookup"><span data-stu-id="073c4-153">This example shows various uses of the `Format` function to format values using both `String` formats and user-defined formats.</span></span> <span data-ttu-id="073c4-154">对于日期分隔符（`/`）、时间分隔符（`:`）以及 AM/PM 指示符（`t` 和 `tt`），系统显示的实际格式输出取决于代码所使用的区域设置。</span><span class="sxs-lookup"><span data-stu-id="073c4-154">For the date separator (`/`), time separator (`:`), and the AM/PM indicators (`t` and `tt`), the actual formatted output displayed by your system depends on the locale settings the code is using.</span></span> <span data-ttu-id="073c4-155">当在开发环境中显示时间和日期时，将使用代码区域设置的短时间格式和短日期格式。</span><span class="sxs-lookup"><span data-stu-id="073c4-155">When times and dates are displayed in the development environment, the short time format and short date format of the code locale are used.</span></span>

> [!NOTE]
> <span data-ttu-id="073c4-156">对于使用24小时制的区域设置，AM/PM 指示符（`t` 和 `tt`）不显示任何内容。</span><span class="sxs-lookup"><span data-stu-id="073c4-156">For locales that use a 24-hour clock, the AM/PM indicators (`t` and `tt`) display nothing.</span></span>

[!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]

## <a name="see-also"></a><span data-ttu-id="073c4-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="073c4-157">See also</span></span>

- [<span data-ttu-id="073c4-158">关键字</span><span class="sxs-lookup"><span data-stu-id="073c4-158">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="073c4-159">Visual Basic 运行库成员</span><span class="sxs-lookup"><span data-stu-id="073c4-159">Visual Basic Runtime Library Members</span></span>](../../../visual-basic/language-reference/runtime-library-members.md)
- [<span data-ttu-id="073c4-160">字符串操作摘要</span><span class="sxs-lookup"><span data-stu-id="073c4-160">String Manipulation Summary</span></span>](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
- [<span data-ttu-id="073c4-161">System.string 类方法</span><span class="sxs-lookup"><span data-stu-id="073c4-161">System.String class methods</span></span>](xref:System.String#methods)
