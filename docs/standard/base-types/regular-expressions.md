---
title: .NET Framework 正则表达式
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pattern-matching with regular expressions, about pattern-matching
- substrings
- searching with regular expressions, about regular expressions
- pattern-matching with regular expressions
- searching with regular expressions
- parsing text with regular expressions
- regular expressions [.NET Framework], about regular expressions
- regular expressions [.NET Framework]
- .NET Framework regular expressions, about
- characters [.NET Framework], regular expressions
- parsing text with regular expressions, overview
- .NET Framework regular expressions
- strings [.NET Framework], regular expressions
ms.assetid: 521b3f6d-f869-42e1-93e5-158c54a6895d
caps.latest.revision: ''
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 145e0c9a722afd9f49216058604936189c003f17
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="net-regular-expressions"></a><span data-ttu-id="57bbc-102">.NET 正则表达式</span><span class="sxs-lookup"><span data-stu-id="57bbc-102">.NET Regular Expressions</span></span>
<span data-ttu-id="57bbc-103">正则表达式提供了功能强大、灵活而又高效的方法来处理文本。</span><span class="sxs-lookup"><span data-stu-id="57bbc-103">Regular expressions provide a powerful, flexible, and efficient method for processing text.</span></span> <span data-ttu-id="57bbc-104">使用正则表达式的全面模式匹配表示法，可以快速分析大量文本，以找到特定的字符模式；验证文本以确保它匹配预定义模式（如电子邮件地址）；提取、编辑、替换或删除文本子字符串；将提取的字符串添加到集合以生成报告。</span><span class="sxs-lookup"><span data-stu-id="57bbc-104">The extensive pattern-matching notation of regular expressions enables you to quickly parse large amounts of text to find specific character patterns; to validate text to ensure that it matches a predefined pattern (such as an email address); to extract, edit, replace, or delete text substrings; and to add the extracted strings to a collection in order to generate a report.</span></span> <span data-ttu-id="57bbc-105">对于处理字符串或分析大文本块的许多应用程序而言，正则表达式是不可缺少的工具。</span><span class="sxs-lookup"><span data-stu-id="57bbc-105">For many applications that deal with strings or that parse large blocks of text, regular expressions are an indispensable tool.</span></span>  
  
## <a name="how-regular-expressions-work"></a><span data-ttu-id="57bbc-106">正则表达式的工作方式</span><span class="sxs-lookup"><span data-stu-id="57bbc-106">How Regular Expressions Work</span></span>  
 <span data-ttu-id="57bbc-107">使用正则表达式处理文本的中心构件是正则表达式引擎（由 .NET 中的 <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> 对象表示）。</span><span class="sxs-lookup"><span data-stu-id="57bbc-107">The centerpiece of text processing with regular expressions is the regular expression engine, which is represented by the <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> object in .NET.</span></span> <span data-ttu-id="57bbc-108">使用正则表达式处理文本至少要求向该正则表达式引擎提供以下两方面的信息：</span><span class="sxs-lookup"><span data-stu-id="57bbc-108">At a minimum, processing text using regular expressions requires that the regular expression engine be provided with the following two items of information:</span></span>  
  
-   <span data-ttu-id="57bbc-109">要在文本中标识的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="57bbc-109">The regular expression pattern to identify in the text.</span></span>  
  
     <span data-ttu-id="57bbc-110">在 .NET 中，正则表达式模式用特殊的语法或语言定义，该语法或语言与 Perl 5 正则表达式兼容，并添加了一些其他功能，例如从右到左匹配。</span><span class="sxs-lookup"><span data-stu-id="57bbc-110">In .NET, regular expression patterns are defined by a special syntax or language, which is compatible with Perl 5 regular expressions and adds some additional features such as right-to-left matching.</span></span> <span data-ttu-id="57bbc-111">有关更多信息，请参见[正则表达式语言 - 快速参考](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="57bbc-111">For more information, see [Regular Expression Language - Quick Reference](../../../docs/standard/base-types/regular-expression-language-quick-reference.md).</span></span>  
  
-   <span data-ttu-id="57bbc-112">要为正则表达式模式分析的文本。</span><span class="sxs-lookup"><span data-stu-id="57bbc-112">The text to parse for the regular expression pattern.</span></span>  
  
 <span data-ttu-id="57bbc-113"><xref:System.Text.RegularExpressions.Regex> 类的方法使你可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="57bbc-113">The methods of the <xref:System.Text.RegularExpressions.Regex> class let you perform the following operations:</span></span>  
  
-   <span data-ttu-id="57bbc-114">通过调用 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> 方法确定输入文本中是否具有正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="57bbc-114">Determine whether the regular expression pattern occurs in the input text by calling the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="57bbc-115">有关使用 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> 方法验证文本的示例，请参阅[如何：验证字符串是否采用有效的电子邮件格式](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)。</span><span class="sxs-lookup"><span data-stu-id="57bbc-115">For an example that uses the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method for validating text, see [How to: Verify that Strings Are in Valid Email Format](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md).</span></span>  
  
-   <span data-ttu-id="57bbc-116">通过调用 <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType> 或 <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> 方法检索匹配正则表达式模式的一个或所有文本匹配项。</span><span class="sxs-lookup"><span data-stu-id="57bbc-116">Retrieve one or all occurrences of text that matches the regular expression pattern by calling the <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType> or <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="57bbc-117">第一个方法返回提供有关匹配文本的信息的 <xref:System.Text.RegularExpressions.Match?displayProperty=nameWithType> 对象。</span><span class="sxs-lookup"><span data-stu-id="57bbc-117">The former method returns a <xref:System.Text.RegularExpressions.Match?displayProperty=nameWithType> object that provides information about the matching text.</span></span> <span data-ttu-id="57bbc-118">第二个方法返回 <xref:System.Text.RegularExpressions.MatchCollection> 对象，该对象对于在分析的文本中找到的每个匹配项包含一个 <xref:System.Text.RegularExpressions.Match?displayProperty=nameWithType> 对象。</span><span class="sxs-lookup"><span data-stu-id="57bbc-118">The latter returns a <xref:System.Text.RegularExpressions.MatchCollection> object that contains one <xref:System.Text.RegularExpressions.Match?displayProperty=nameWithType> object for each match found in the parsed text.</span></span>  
  
-   <span data-ttu-id="57bbc-119">通过调用 <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> 方法替换匹配正则表达式模式的文本。</span><span class="sxs-lookup"><span data-stu-id="57bbc-119">Replace text that matches the regular expression pattern by calling the <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="57bbc-120">有关使用 <xref:System.Text.RegularExpressions.Regex.Replace%2A> 方法更改日期格式和删除字符串中无效字符的示例，请参阅[如何：从字符串中剥离无效字符](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md)和[如何：更改日期格式](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md)。</span><span class="sxs-lookup"><span data-stu-id="57bbc-120">For examples that use the <xref:System.Text.RegularExpressions.Regex.Replace%2A> method to change date formats and remove invalid characters from a string, see [How to: Strip Invalid Characters from a String](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md) and [Example: Changing Date Formats](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md).</span></span>  
  
 <span data-ttu-id="57bbc-121">有关正则表达式对象模型的概述，请参见[正则表达式对象模型](../../../docs/standard/base-types/the-regular-expression-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="57bbc-121">For an overview of the regular expression object model, see [The Regular Expression Object Model](../../../docs/standard/base-types/the-regular-expression-object-model.md).</span></span>  
  
 <span data-ttu-id="57bbc-122">若要详细了解正则表达式语言，请参阅[正则表达式语言 - 快速参考](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)，或下载和打印下面的小册子之一：</span><span class="sxs-lookup"><span data-stu-id="57bbc-122">For more information about the regular expression language, see [Regular Expression Language - Quick Reference](../../../docs/standard/base-types/regular-expression-language-quick-reference.md) or download and print one of these brochures:</span></span>  
  
 [<span data-ttu-id="57bbc-123">快速参考（Word (.docx) 格式）</span><span class="sxs-lookup"><span data-stu-id="57bbc-123">Quick Reference in Word (.docx) format</span></span>](http://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)  
 [<span data-ttu-id="57bbc-124">快速参考（PDF (.pdf) 格式）</span><span class="sxs-lookup"><span data-stu-id="57bbc-124">Quick Reference in PDF (.pdf) format</span></span>](http://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)  
  
## <a name="regular-expression-examples"></a><span data-ttu-id="57bbc-125">正则表达式示例</span><span class="sxs-lookup"><span data-stu-id="57bbc-125">Regular Expression Examples</span></span>  
 <span data-ttu-id="57bbc-126"><xref:System.String> 类包括许多字符串搜索和替换方法，当你要在较大字符串中定位文本字符串时，可以使用这些方法。</span><span class="sxs-lookup"><span data-stu-id="57bbc-126">The <xref:System.String> class includes a number of string search and replacement methods that you can use when you want to locate literal strings in a larger string.</span></span> <span data-ttu-id="57bbc-127">当你希望在较大字符串中定位若干子字符串之一时，或者当你希望在字符串中标识模式时，正则表达式最有用，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="57bbc-127">Regular expressions are most useful either when you want to locate one of several substrings in a larger string, or when you want to identify patterns in a string, as the following examples illustrate.</span></span>  
  
### <a name="example-1-replacing-substrings"></a><span data-ttu-id="57bbc-128">示例 1：替换子字符串</span><span class="sxs-lookup"><span data-stu-id="57bbc-128">Example 1: Replacing Substrings</span></span>  
 <span data-ttu-id="57bbc-129">假设一个邮件列表包含一些姓名，这些姓名有时包括称谓（Mr.、Mrs.、Miss 或 Ms.）以及姓氏和名字。</span><span class="sxs-lookup"><span data-stu-id="57bbc-129">Assume that a mailing list contains names that sometimes include a title (Mr., Mrs., Miss, or Ms.) along with a first and last name.</span></span> <span data-ttu-id="57bbc-130">如果你从列表中生成信封标签时不希望包括称谓，则可以使用正则表达式移除称谓，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="57bbc-130">If you do not want to include the titles when you generate envelope labels from the list, you can use a regular expression to remove the titles, as the following example illustrates.</span></span>  
  
 [!code-csharp[Conceptual.Regex#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example1.cs#2)]
 [!code-vb[Conceptual.Regex#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example1.vb#2)]  
  
 <span data-ttu-id="57bbc-131">正则表达式模式 `(Mr\.? |Mrs\.? |Miss |Ms\.? )` 匹配任何"Mr"、"Mr."、"Mrs"、"Mrs."、"Miss"、"Ms 或"Ms."。</span><span class="sxs-lookup"><span data-stu-id="57bbc-131">The regular expression pattern`(Mr\.? |Mrs\.? |Miss |Ms\.? )` matches any occurrence of "Mr ", "Mr. ", "Mrs ", "Mrs. ", "Miss ", "Ms or "Ms. ".</span></span> <span data-ttu-id="57bbc-132">对 <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> 方法的调用会将匹配的字符串替换为 <xref:System.String.Empty?displayProperty=nameWithType>；换句话说，将其从原始字符串中移除。</span><span class="sxs-lookup"><span data-stu-id="57bbc-132">The call to the <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method replaces the matched string with <xref:System.String.Empty?displayProperty=nameWithType>; in other words, it removes it from the original string.</span></span>  
  
### <a name="example-2-identifying-duplicated-words"></a><span data-ttu-id="57bbc-133">示例 2：标识重复的单词</span><span class="sxs-lookup"><span data-stu-id="57bbc-133">Example 2: Identifying Duplicated Words</span></span>  
 <span data-ttu-id="57bbc-134">意外地重复单词是编写者常犯的错误。</span><span class="sxs-lookup"><span data-stu-id="57bbc-134">Accidentally duplicating words is a common error that writers make.</span></span> <span data-ttu-id="57bbc-135">可以使用正则表达式标识重复的单词，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="57bbc-135">A regular expression can be used to identify duplicated words, as the following example shows.</span></span>  
  
 [!code-csharp[Conceptual.Regex#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example2.cs#3)]
 [!code-vb[Conceptual.Regex#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example2.vb#3)]  
  
 <span data-ttu-id="57bbc-136">正则表达式模式 `\b(\w+?)\s\1\b` 的解释如下:</span><span class="sxs-lookup"><span data-stu-id="57bbc-136">The regular expression pattern `\b(\w+?)\s\1\b` can be interpreted as follows:</span></span>  
  
|||  
|-|-|  
|`\b`|<span data-ttu-id="57bbc-137">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="57bbc-137">Start at a word boundary.</span></span>|  
|<span data-ttu-id="57bbc-138">(\w+?)</span><span class="sxs-lookup"><span data-stu-id="57bbc-138">(\w+?)</span></span>|<span data-ttu-id="57bbc-139">匹配一个或多个单词字符，但字符要尽可能的少。</span><span class="sxs-lookup"><span data-stu-id="57bbc-139">Match one or more word characters, but as few characters as possible.</span></span> <span data-ttu-id="57bbc-140">它们一起构成可称为 `\1` 的组。</span><span class="sxs-lookup"><span data-stu-id="57bbc-140">Together, they form a group that can be referred to as `\1`.</span></span>|  
|`\s`|<span data-ttu-id="57bbc-141">与空白字符匹配。</span><span class="sxs-lookup"><span data-stu-id="57bbc-141">Match a white-space character.</span></span>|  
|`\1`|<span data-ttu-id="57bbc-142">与等于名为 `\1` 的组的子字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="57bbc-142">Match the substring that is equal to the group named `\1`.</span></span>|  
|`\b`|<span data-ttu-id="57bbc-143">与字边界匹配。</span><span class="sxs-lookup"><span data-stu-id="57bbc-143">Match a word boundary.</span></span>|  
  
 <span data-ttu-id="57bbc-144">通过将正则表达式选项设置为 <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType>，调用 <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="57bbc-144">The <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> method is called with regular expression options set to <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="57bbc-145">因此，匹配操作不区分大小写，此示例将子字符串“This this”标识为重复。</span><span class="sxs-lookup"><span data-stu-id="57bbc-145">Therefore, the match operation is case-insensitive, and the example identifies the substring "This this" as a duplication.</span></span>  
  
 <span data-ttu-id="57bbc-146">请注意，输入字符串包括子字符串“this?</span><span class="sxs-lookup"><span data-stu-id="57bbc-146">Note that the input string includes the substring "this?</span></span> <span data-ttu-id="57bbc-147">This”。</span><span class="sxs-lookup"><span data-stu-id="57bbc-147">This".</span></span> <span data-ttu-id="57bbc-148">但是，由于插入标点符号，该子字符串不被标识为重复。</span><span class="sxs-lookup"><span data-stu-id="57bbc-148">However, because of the intervening punctuation mark, it is not identified as a duplication.</span></span>  
  
### <a name="example-3-dynamically-building-a-culture-sensitive-regular-expression"></a><span data-ttu-id="57bbc-149">示例 3：动态生成区分区域性的正则表达式</span><span class="sxs-lookup"><span data-stu-id="57bbc-149">Example 3: Dynamically Building a Culture-Sensitive Regular Expression</span></span>  
 <span data-ttu-id="57bbc-150">下面的示例演示如何将正则表达式的功能与 .NET 的全球化功能所提供的灵活性结合在一起。</span><span class="sxs-lookup"><span data-stu-id="57bbc-150">The following example illustrates the power of regular expressions combined with the flexibility offered by .NET's globalization features.</span></span> <span data-ttu-id="57bbc-151">它使用 <xref:System.Globalization.NumberFormatInfo> 对象确定系统的当前区域性设置中货币值的格式。</span><span class="sxs-lookup"><span data-stu-id="57bbc-151">It uses the <xref:System.Globalization.NumberFormatInfo> object to determine the format of currency values in the system's current culture.</span></span> <span data-ttu-id="57bbc-152">然后使用该信息动态构造从文本提取货币值的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="57bbc-152">It then uses that information to dynamically construct a regular expression that extracts currency values from the text.</span></span> <span data-ttu-id="57bbc-153">对于每个匹配，它提取仅包含数字字符串的子组，将其转换为 <xref:System.Decimal> 值，然后计算累计值。</span><span class="sxs-lookup"><span data-stu-id="57bbc-153">For each match, it extracts the subgroup that contains the numeric string only, converts it to a <xref:System.Decimal> value, and calculates a running total.</span></span>  
  
 [!code-csharp[Conceptual.Regex#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example.cs#1)]
 [!code-vb[Conceptual.Regex#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example.vb#1)]  
  
 <span data-ttu-id="57bbc-154">在当前区域性设置为“英语 - 美国”(en-US) 的计算机上，该示例动态生成正则表达式 `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`。</span><span class="sxs-lookup"><span data-stu-id="57bbc-154">On a computer whose current culture is English - United States (en-US), the example dynamically builds the regular expression `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`.</span></span> <span data-ttu-id="57bbc-155">此正则表达式模式可以按以下方式解释：</span><span class="sxs-lookup"><span data-stu-id="57bbc-155">This regular expression pattern can be interpreted as follows:</span></span>  
  
|||  
|-|-|  
|`\$`|<span data-ttu-id="57bbc-156">在输入字符串中查找美元符号 ($) 的一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="57bbc-156">Look for a single occurrence of the dollar symbol ($) in the input string.</span></span> <span data-ttu-id="57bbc-157">正则表达式模式字符串包含一个反斜杠来指示按字面解释美元符号而非将其作为正则表达式定位点。</span><span class="sxs-lookup"><span data-stu-id="57bbc-157">The regular expression pattern string includes a backslash to indicate that the dollar symbol is to be interpreted literally rather than as a regular expression anchor.</span></span> <span data-ttu-id="57bbc-158">（单独的 $ 符号将指示正则表达式引擎应尝试在字符串的末尾开始匹配。）为了确保当前区域性设置的货币符号不被错误解释为正则表达式符号，该示例调用 <xref:System.Text.RegularExpressions.Regex.Escape%2A> 方法使该字符转义。</span><span class="sxs-lookup"><span data-stu-id="57bbc-158">(The $ symbol alone would indicate that the regular expression engine should try to begin its match at the end of a string.) To ensure that the current culture's currency symbol is not misinterpreted as a regular expression symbol, the example calls the <xref:System.Text.RegularExpressions.Regex.Escape%2A> method to escape the character.</span></span>|  
|`\s*`|<span data-ttu-id="57bbc-159">查找空白字符的零个或多个匹配项。</span><span class="sxs-lookup"><span data-stu-id="57bbc-159">Look for zero or more occurrences of a white-space character.</span></span>|  
|`[-+]?`|<span data-ttu-id="57bbc-160">查找正号或负号的零个或一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="57bbc-160">Look for zero or one occurrence of either a positive sign or a negative sign.</span></span>|  
|`([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`|<span data-ttu-id="57bbc-161">括起此表达式的外部括号将表达式定义为捕获组或子表达式。</span><span class="sxs-lookup"><span data-stu-id="57bbc-161">The outer parentheses around this expression define it as a capturing group or a subexpression.</span></span> <span data-ttu-id="57bbc-162">如果找到匹配项，则有关匹配字符串的此部分的信息可以从第二个 <xref:System.Text.RegularExpressions.Group> 对象中检索（该对象位于 <xref:System.Text.RegularExpressions.GroupCollection> 属性所返回的 <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> 对象中）。</span><span class="sxs-lookup"><span data-stu-id="57bbc-162">If a match is found, information about this part of the matching string can be retrieved from the second <xref:System.Text.RegularExpressions.Group> object in the <xref:System.Text.RegularExpressions.GroupCollection> object returned by the <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="57bbc-163">（集合中的第一个元素表示整个匹配。）</span><span class="sxs-lookup"><span data-stu-id="57bbc-163">(The first element in the collection represents the entire match.)</span></span>|  
|`[0-9]{0,3}`|<span data-ttu-id="57bbc-164">查找十进制数字 0 到 9 的零到三个匹配项。</span><span class="sxs-lookup"><span data-stu-id="57bbc-164">Look for zero to three occurrences of the decimal digits 0 through 9.</span></span>|  
|`(,[0-9]{3})*`|<span data-ttu-id="57bbc-165">查找后跟三个十进制数字的组分隔符的零个或多个匹配项。</span><span class="sxs-lookup"><span data-stu-id="57bbc-165">Look for zero or more occurrences of a group separator followed by three decimal digits.</span></span>|  
|`\.`|<span data-ttu-id="57bbc-166">查找小数分隔符的一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="57bbc-166">Look for a single occurrence of the decimal separator.</span></span>|  
|`[0-9]+`|<span data-ttu-id="57bbc-167">查找一个或多个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="57bbc-167">Look for one or more decimal digits.</span></span>|  
|`(\.[0-9]+)?`|<span data-ttu-id="57bbc-168">查找后跟至少一个十进制数字的小数分隔符的零个或一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="57bbc-168">Look for zero or one occurrence of the decimal separator followed by at least one decimal digit.</span></span>|  
  
 <span data-ttu-id="57bbc-169">如果在输入字符串中找到所有这些子模式，则匹配成功，并将包含有关匹配的信息的 <xref:System.Text.RegularExpressions.Match> 对象添加到 <xref:System.Text.RegularExpressions.MatchCollection> 对象。</span><span class="sxs-lookup"><span data-stu-id="57bbc-169">If each of these subpatterns is found in the input string, the match succeeds, and a <xref:System.Text.RegularExpressions.Match> object that contains information about the match is added to the <xref:System.Text.RegularExpressions.MatchCollection> object.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="57bbc-170">相关主题</span><span class="sxs-lookup"><span data-stu-id="57bbc-170">Related Topics</span></span>  
  
|<span data-ttu-id="57bbc-171">标题</span><span class="sxs-lookup"><span data-stu-id="57bbc-171">Title</span></span>|<span data-ttu-id="57bbc-172">描述</span><span class="sxs-lookup"><span data-stu-id="57bbc-172">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="57bbc-173">正则表达式语言 - 快速参考</span><span class="sxs-lookup"><span data-stu-id="57bbc-173">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)|<span data-ttu-id="57bbc-174">提供有关可用来定义正则表达式的字符集、运算符和构造的信息。</span><span class="sxs-lookup"><span data-stu-id="57bbc-174">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>|  
|[<span data-ttu-id="57bbc-175">正则表达式对象模型</span><span class="sxs-lookup"><span data-stu-id="57bbc-175">The Regular Expression Object Model</span></span>](../../../docs/standard/base-types/the-regular-expression-object-model.md)|<span data-ttu-id="57bbc-176">提供演示如何使用正则表达式类的信息和代码示例。</span><span class="sxs-lookup"><span data-stu-id="57bbc-176">Provides information and code examples that illustrate how to use the regular expression classes.</span></span>|  
|[<span data-ttu-id="57bbc-177">正则表达式行为的详细信息</span><span class="sxs-lookup"><span data-stu-id="57bbc-177">Details of Regular Expression Behavior</span></span>](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)|<span data-ttu-id="57bbc-178">介绍了 .NET 正则表达式的功能和行为。</span><span class="sxs-lookup"><span data-stu-id="57bbc-178">Provides information about the capabilities and behavior of .NET regular expressions.</span></span>|  
|[<span data-ttu-id="57bbc-179">正则表达式示例</span><span class="sxs-lookup"><span data-stu-id="57bbc-179">Regular Expression Examples</span></span>](../../../docs/standard/base-types/regular-expression-examples.md)|<span data-ttu-id="57bbc-180">提供演示正则表达式的典型用法的代码示例。</span><span class="sxs-lookup"><span data-stu-id="57bbc-180">Provides code examples that illustrate typical uses of regular expressions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="57bbc-181">参考</span><span class="sxs-lookup"><span data-stu-id="57bbc-181">Reference</span></span>  
 <xref:System.Text.RegularExpressions?displayProperty=nameWithType>  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>  
 [<span data-ttu-id="57bbc-182">正则表达式 - 快速参考（以 Word 格式下载）</span><span class="sxs-lookup"><span data-stu-id="57bbc-182">Regular Expressions - Quick Reference (download in Word format)</span></span>](http://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)  
 [<span data-ttu-id="57bbc-183">正则表达式 — 快速参考（以 PDF 格式下载）</span><span class="sxs-lookup"><span data-stu-id="57bbc-183">Regular Expressions - Quick Reference (download in PDF format)</span></span>](http://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)
