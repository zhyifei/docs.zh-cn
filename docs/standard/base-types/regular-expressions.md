---
title: ".NET 中的正则表达式"
description: ".NET 中的正则表达式"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d1a640cf-09ca-48f7-800c-a627a6d549c9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: ac26821819b22aa3ea47e6945bb5c8575dcd9807
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="regular-expressions-in-net"></a><span data-ttu-id="2e7d8-104">.NET 中的正则表达式</span><span class="sxs-lookup"><span data-stu-id="2e7d8-104">Regular expressions in .NET</span></span>

<span data-ttu-id="2e7d8-105">正则表达式提供了功能强大、灵活而又高效的方法来处理文本。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-105">Regular expressions provide a powerful, flexible, and efficient method for processing text.</span></span> <span data-ttu-id="2e7d8-106">正则表达式的全面模式匹配表示法使你可以快速分析大量文本以找到特定的字符模式；验证文本以确保它匹配预定义的模式（如电子邮件地址）；提取、编辑、替换或删除文本子字符串；将提取的字符串添加到集合以生成报告。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-106">The extensive pattern-matching notation of regular expressions enables you to quickly parse large amounts of text to find specific character patterns; to validate text to ensure that it matches a predefined pattern (such as an e-mail address); to extract, edit, replace, or delete text substrings; and to add the extracted strings to a collection in order to generate a report.</span></span> <span data-ttu-id="2e7d8-107">对于处理字符串或分析大文本块的许多应用程序而言，正则表达式是不可缺少的工具。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-107">For many applications that deal with strings or that parse large blocks of text, regular expressions are an indispensable tool.</span></span>

## <a name="how-regular-expressions-work"></a><span data-ttu-id="2e7d8-108">正则表达式的工作方式</span><span class="sxs-lookup"><span data-stu-id="2e7d8-108">How Regular Expressions Work</span></span>

<span data-ttu-id="2e7d8-109">使用正则表达式处理文本的中心构件是正则表达式引擎，该引擎在 .NET 中由 [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) 对象表示。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-109">The centerpiece of text processing with regular expressions is the regular expression engine, which is represented by the [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) object in .NET.</span></span> <span data-ttu-id="2e7d8-110">使用正则表达式处理文本至少要求向该正则表达式引擎提供以下两方面的信息：</span><span class="sxs-lookup"><span data-stu-id="2e7d8-110">At a minimum, processing text using regular expressions requires that the regular expression engine be provided with the following two items of information:</span></span>

* <span data-ttu-id="2e7d8-111">要在文本中标识的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-111">The regular expression pattern to identify in the text.</span></span> 
  
  <span data-ttu-id="2e7d8-112">在 .NET 中，正则表达式模式用特殊的语法或语言定义，该语法或语言与 Perl 5 正则表达式兼容，并添加了一些其他功能，例如从右到左匹配。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-112">In .NET, regular expression patterns are defined by a special syntax or language, which is compatible with Perl 5 regular expressions and adds some additional features such as right-to-left matching.</span></span> <span data-ttu-id="2e7d8-113">有关更多信息，请参见[正则表达式语言 - 快速参考](quick-ref.md)。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-113">For more information, see [Regular Expression Language - Quick Reference](quick-ref.md).</span></span>
  
* <span data-ttu-id="2e7d8-114">要为正则表达式模式分析的文本。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-114">The text to parse for the regular expression pattern.</span></span>

<span data-ttu-id="2e7d8-115">[Regex](xref:System.Text.RegularExpressions.Regex) 类的方法使你可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2e7d8-115">The methods of the [Regex](xref:System.Text.RegularExpressions.Regex) class let you perform the following operations:</span></span>

* <span data-ttu-id="2e7d8-116">通过调用 [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) 方法确定输入文本中是否具有正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-116">Determine whether the regular expression pattern occurs in the input text by calling the [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) method.</span></span> <span data-ttu-id="2e7d8-117">有关使用 [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) 方法验证文本的示例，请参见[如何：确认字符串是有效的电子邮件格式](verify-format.md)。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-117">For an example that uses the [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) method for validating text, see [How to: Verify that Strings Are in Valid Email Format](verify-format.md).</span></span>

* <span data-ttu-id="2e7d8-118">通过调用 [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) 或 [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) 方法检索匹配正则表达式模式的一个或所有文本匹配项。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-118">Retrieve one or all occurrences of text that matches the regular expression pattern by calling the [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) or [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) method.</span></span> <span data-ttu-id="2e7d8-119">第一个方法返回提供有关匹配文本的信息的 [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) 对象。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-119">The former method returns a [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) object that provides information about the matching text.</span></span> <span data-ttu-id="2e7d8-120">后者返回 [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) 对象，其中针对所分析的文本中找到的每个匹配项包含一个 [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) 对象。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-120">The latter returns a [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) object that contains one [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) object for each match found in the parsed text.</span></span> 

* <span data-ttu-id="2e7d8-121">通过调用 [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) 方法替换匹配正则表达式模式的文本。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-121">Replace text that matches the regular expression pattern by calling the [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method.</span></span> <span data-ttu-id="2e7d8-122">有关使用 [Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) 方法更改日期格式和删除字符串中的无效字符的示例，请参见[如何：从字符串中剥离无效字符](strip-characters.md)和[正则表达式示例：更改日期格式](changing-formats.md)。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-122">For examples that use the [Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method to change date formats and remove invalid characters from a string, see [How to: Strip Invalid Characters from a String](strip-characters.md) and [Regular Expression Example: Changing Date Formats](changing-formats.md).</span></span>

<span data-ttu-id="2e7d8-123">有关正则表达式对象模型的概述，请参见[正则表达式对象模型](object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-123">For an overview of the regular expression object model, see [The Regular Expression Object Model](object-model.md).</span></span>

<span data-ttu-id="2e7d8-124">有关正则表达式语言的更多信息，请参见[正则表达式语言 - 快速参考](quick-ref.md)。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-124">For more information about the regular expression language, see [Regular Expression Language - Quick Reference](quick-ref.md).</span></span>

## <a name="regular-expression-examples"></a><span data-ttu-id="2e7d8-125">正则表达式示例</span><span class="sxs-lookup"><span data-stu-id="2e7d8-125">Regular Expression Examples</span></span>

<span data-ttu-id="2e7d8-126">[String](xref:System.String) 类包括许多字符串搜索和替换方法，当你要在较大字符串中定位文本字符串时，可以使用这些方法。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-126">The [String](xref:System.String) class includes a number of string search and replacement methods that you can use when you want to locate literal strings in a larger string.</span></span> <span data-ttu-id="2e7d8-127">当你希望在较大字符串中定位若干子字符串之一时，或者当你希望在字符串中标识模式时，正则表达式最有用，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-127">Regular expressions are most useful either when you want to locate one of several substrings in a larger string, or when you want to identify patterns in a string, as the following examples illustrate.</span></span> 

### <a name="example-1-replacing-substrings"></a><span data-ttu-id="2e7d8-128">示例 1：替换子字符串</span><span class="sxs-lookup"><span data-stu-id="2e7d8-128">Example 1: Replacing Substrings</span></span>

<span data-ttu-id="2e7d8-129">假设一个邮件列表包含一些姓名，这些姓名有时包括称谓（Mr.、Mrs.、Miss 或 Ms.）以及姓氏和名字。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-129">Assume that a mailing list contains names that sometimes include a title (Mr., Mrs., Miss, or Ms.) along with a first and last name.</span></span> <span data-ttu-id="2e7d8-130">如果你从列表中生成信封标签时不希望包括称谓，则可以使用正则表达式移除称谓，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-130">If you do not want to include the titles when you generate envelope labels from the list, you can use a regular expression to remove the titles, as the following example illustrates.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "(Mr\\.? |Mrs\\.? |Miss |Ms\\.? )";
      string[] names = { "Mr. Henry Hunt", "Ms. Sara Samuels", 
                         "Abraham Adams", "Ms. Nicole Norris" };
      foreach (string name in names)
         Console.WriteLine(Regex.Replace(name, pattern, String.Empty));
   }
}
// The example displays the following output:
//    Henry Hunt
//    Sara Samuels
//    Abraham Adams
//    Nicole Norris
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(Mr\.? |Mrs\.? |Miss |Ms\.? )"
      Dim names() As String = { "Mr. Henry Hunt", "Ms. Sara Samuels", _
                                "Abraham Adams", "Ms. Nicole Norris" }
      For Each name As String In names
         Console.WriteLine(Regex.Replace(name, pattern, String.Empty))
      Next                                
   End Sub
End Module
' The example displays the following output:
'    Henry Hunt
'    Sara Samuels
'    Abraham Adams
'    Nicole Norris
```

<span data-ttu-id="2e7d8-131">正则表达式模式 `(Mr\.? |Mrs\.? |Miss |Ms\.? )` 可匹配任何“Mr”、“Mr.”、“Mrs”、“Mrs.”、“Miss”、“Ms”或“Ms.”。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-131">The regular expression pattern `(Mr\.? |Mrs\.? |Miss |Ms\.? )` matches any occurrence of "Mr ", "Mr. ", "Mrs ", "Mrs. ", "Miss ", "Ms or "Ms. ".</span></span> <span data-ttu-id="2e7d8-132">对 [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) 方法的调用会将匹配的字符串替换为 [String.Empty](xref:System.String.Empty)；换句话说，它从原始字符串中将其移除。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-132">The call to the [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method replaces the matched string with [String.Empty](xref:System.String.Empty); in other words, it removes it from the original string.</span></span>

### <a name="example-2-identifying-duplicated-words"></a><span data-ttu-id="2e7d8-133">示例 2：标识重复的单词</span><span class="sxs-lookup"><span data-stu-id="2e7d8-133">Example 2: Identifying Duplicated Words</span></span>

<span data-ttu-id="2e7d8-134">意外地重复单词是编写器常犯的错误。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-134">Accidentally duplicating words is a common error that writers make.</span></span> <span data-ttu-id="2e7d8-135">可以使用正则表达式标识重复的单词，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-135">A regular expression can be used to identify duplicated words, as the following example shows.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Class1
{
   public static void Main()
   {
      string pattern = @"\b(\w+?)\s\1\b";
      string input = "This this is a nice day. What about this? This tastes good. I saw a a dog.";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine("{0} (duplicates '{1}') at position {2}", 
                           match.Value, match.Groups[1].Value, match.Index);
   }
}
// The example displays the following output:
//       This this (duplicates 'This)' at position 0
//       a a (duplicates 'a)' at position 66
```

```vb
Imports System.Text.RegularExpressions

Module modMain
   Public Sub Main()
      Dim pattern As String = "\b(\w+?)\s\1\b"
      Dim input As String = "This this is a nice day. What about this? This tastes good. I saw a a dog."
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine("{0} (duplicates '{1}') at position {2}", _
                           match.Value, match.Groups(1).Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       This this (duplicates 'This)' at position 0
'       a a (duplicates 'a)' at position 66
```

<span data-ttu-id="2e7d8-136">正则表达式模式 `\b(\w+?)\s\1\b` 的解释如下:</span><span class="sxs-lookup"><span data-stu-id="2e7d8-136">The regular expression pattern `\b(\w+?)\s\1\b` can be interpreted as follows:</span></span>

<span data-ttu-id="2e7d8-137">语法</span><span class="sxs-lookup"><span data-stu-id="2e7d8-137">Syntax</span></span> | <span data-ttu-id="2e7d8-138">含义</span><span class="sxs-lookup"><span data-stu-id="2e7d8-138">Meaning</span></span>
------ | -------
`\b` | <span data-ttu-id="2e7d8-139">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-139">Start at a word boundary.</span></span>
`(\w+?)` | <span data-ttu-id="2e7d8-140">匹配一个或多个单词字符，但字符要尽可能的少。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-140">Match one or more word characters, but as few characters as possible.</span></span> <span data-ttu-id="2e7d8-141">它们一起构成可称为 `\1` 的组。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-141">Together, they form a group that can be referred to as `\1`.</span></span>
`\s` | <span data-ttu-id="2e7d8-142">与空白字符匹配。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-142">Match a white-space character.</span></span>
`\1` | <span data-ttu-id="2e7d8-143">与等于名为 `\1` 的组的子字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-143">Match the substring that is equal to the group named `\1`.</span></span>
`\b` | <span data-ttu-id="2e7d8-144">与字边界匹配。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-144">Match a word boundary.</span></span>

<span data-ttu-id="2e7d8-145">通过将正则表达式选项设置为 [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase)，调用 [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) 方法。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-145">The [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) method is called with regular expression options set to [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase).</span></span> <span data-ttu-id="2e7d8-146">因此，匹配操作不区分大小写，此示例将子字符串“This this”标识为重复。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-146">Therefore, the match operation is case-insensitive, and the example identifies the substring "This this" as a duplication.</span></span>

<span data-ttu-id="2e7d8-147">请注意，输入字符串包括子字符串“this?</span><span class="sxs-lookup"><span data-stu-id="2e7d8-147">Note that the input string includes the substring "this?</span></span> <span data-ttu-id="2e7d8-148">This”。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-148">This".</span></span> <span data-ttu-id="2e7d8-149">但是，由于插入标点符号，该子字符串不被标识为重复。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-149">However, because of the intervening punctuation mark, it is not identified as a duplication.</span></span>

### <a name="example-3-dynamically-building-a-culture-sensitive-regular-expression"></a><span data-ttu-id="2e7d8-150">示例 3：动态生成区分区域性的正则表达式</span><span class="sxs-lookup"><span data-stu-id="2e7d8-150">Example 3: Dynamically Building a Culture-Sensitive Regular Expression</span></span>

<span data-ttu-id="2e7d8-151">下面的示例演示如何将正则表达式的功能与 .NET 的全球化功能所提供的灵活性结合在一起。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-151">The following example illustrates the power of regular expressions combined with the flexibility offered by .NET's globalization features.</span></span> <span data-ttu-id="2e7d8-152">它使用 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 对象确定系统的当前区域性设置中货币值的格式。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-152">It uses the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object to determine the format of currency values in the system's current culture.</span></span> <span data-ttu-id="2e7d8-153">然后使用该信息动态构造从文本提取货币值的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-153">It then uses that information to dynamically construct a regular expression that extracts currency values from the text.</span></span> <span data-ttu-id="2e7d8-154">对于每个匹配，它提取仅包含数字字符串的子组，将其转换为 [Decimal](xref:System.Decimal) 值，然后计算累计值。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-154">For each match, it extracts the subgroup that contains the numeric string only, converts it to a [Decimal](xref:System.Decimal) value, and calculates a running total.</span></span> 

```csharp
using System;
using System.Collections.Generic;
using System.Globalization;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      // Define text to be parsed.
      string input = "Office expenses on 2/13/2008:\n" + 
                     "Paper (500 sheets)                      $3.95\n" + 
                     "Pencils (box of 10)                     $1.00\n" + 
                     "Pens (box of 10)                        $4.49\n" + 
                     "Erasers                                 $2.19\n" + 
                     "Ink jet printer                        $69.95\n\n" + 
                     "Total Expenses                        $ 81.58\n"; 

      // Get current culture's NumberFormatInfo object.
      NumberFormatInfo nfi = CultureInfo.CurrentCulture.NumberFormat;
      // Assign needed property values to variables.
      string currencySymbol = nfi.CurrencySymbol;
      bool symbolPrecedesIfPositive = nfi.CurrencyPositivePattern % 2 == 0;
      string groupSeparator = nfi.CurrencyGroupSeparator;
      string decimalSeparator = nfi.CurrencyDecimalSeparator;

      // Form regular expression pattern.
      string pattern = Regex.Escape( symbolPrecedesIfPositive ? currencySymbol : "") + 
                       @"\s*[-+]?" + "([0-9]{0,3}(" + groupSeparator + "[0-9]{3})*(" + 
                       Regex.Escape(decimalSeparator) + "[0-9]+)?)" + 
                       (! symbolPrecedesIfPositive ? currencySymbol : ""); 
      Console.WriteLine( "The regular expression pattern is:");
      Console.WriteLine("   " + pattern);      

      // Get text that matches regular expression pattern.
      MatchCollection matches = Regex.Matches(input, pattern, 
                                              RegexOptions.IgnorePatternWhitespace);               
      Console.WriteLine("Found {0} matches.", matches.Count); 

      // Get numeric string, convert it to a value, and add it to List object.
      List<decimal> expenses = new List<Decimal>();

      foreach (Match match in matches)
         expenses.Add(Decimal.Parse(match.Groups[1].Value));      

      // Determine whether total is present and if present, whether it is correct.
      decimal total = 0;
      foreach (decimal value in expenses)
         total += value;

      if (total / 2 == expenses[expenses.Count - 1]) 
         Console.WriteLine("The expenses total {0:C2}.", expenses[expenses.Count - 1]);
      else
         Console.WriteLine("The expenses total {0:C2}.", total);
   }  
}
// The example displays the following output:
//       The regular expression pattern is:
//          \$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)
//       Found 6 matches.
//       The expenses total $81.58.
```

```vb
Imports System.Collections.Generic
Imports System.Globalization
Imports System.Text.RegularExpressions

Public Module Example
   Public Sub Main()
      ' Define text to be parsed.
      Dim input As String = "Office expenses on 2/13/2008:" + vbCrLf + _
                            "Paper (500 sheets)                      $3.95" + vbCrLf + _
                            "Pencils (box of 10)                     $1.00" + vbCrLf + _
                            "Pens (box of 10)                        $4.49" + vbCrLf + _
                            "Erasers                                 $2.19" + vbCrLf + _
                            "Ink jet printer                        $69.95" + vbCrLf + vbCrLf + _
                            "Total Expenses                        $ 81.58" + vbCrLf
      ' Get current culture's NumberFormatInfo object.
      Dim nfi As NumberFormatInfo = CultureInfo.CurrentCulture.NumberFormat
      ' Assign needed property values to variables.
      Dim currencySymbol As String = nfi.CurrencySymbol
      Dim symbolPrecedesIfPositive As Boolean = CBool(nfi.CurrencyPositivePattern Mod 2 = 0)
      Dim groupSeparator As String = nfi.CurrencyGroupSeparator
      Dim decimalSeparator As String = nfi.CurrencyDecimalSeparator

      ' Form regular expression pattern.
      Dim pattern As String = Regex.Escape(CStr(IIf(symbolPrecedesIfPositive, currencySymbol, ""))) + _
                              "\s*[-+]?" + "([0-9]{0,3}(" + groupSeparator + "[0-9]{3})*(" + _
                              Regex.Escape(decimalSeparator) + "[0-9]+)?)" + _
                              CStr(IIf(Not symbolPrecedesIfPositive, currencySymbol, "")) 
      Console.WriteLine("The regular expression pattern is: ")
      Console.WriteLine("   " + pattern)      

      ' Get text that matches regular expression pattern.
      Dim matches As MatchCollection = Regex.Matches(input, pattern, RegexOptions.IgnorePatternWhitespace)               
      Console.WriteLine("Found {0} matches. ", matches.Count)

      ' Get numeric string, convert it to a value, and add it to List object.
      Dim expenses As New List(Of Decimal)

      For Each match As Match In matches
         expenses.Add(Decimal.Parse(match.Groups.Item(1).Value))      
      Next

      ' Determine whether total is present and if present, whether it is correct.
      Dim total As Decimal
      For Each value As Decimal In expenses
         total += value
      Next

      If total / 2 = expenses(expenses.Count - 1) Then
         Console.WriteLine("The expenses total {0:C2}.", expenses(expenses.Count - 1))
      Else
         Console.WriteLine("The expenses total {0:C2}.", total)
      End If   
   End Sub
End Module
' The example displays the following output:
'       The regular expression pattern is:
'          \$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)
'       Found 6 matches.
'       The expenses total $81.58.
```

<span data-ttu-id="2e7d8-155">在当前区域性设置为“英语 - 美国”(en-US) 的计算机上，该示例动态生成正则表达式 `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-155">On a computer whose current culture is English - United States (en-US), the example dynamically builds the regular expression `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`.</span></span> <span data-ttu-id="2e7d8-156">此正则表达式模式可以按以下方式解释：</span><span class="sxs-lookup"><span data-stu-id="2e7d8-156">This regular expression pattern can be interpreted as follows:</span></span>

<span data-ttu-id="2e7d8-157">语法</span><span class="sxs-lookup"><span data-stu-id="2e7d8-157">Syntax</span></span> | <span data-ttu-id="2e7d8-158">含义</span><span class="sxs-lookup"><span data-stu-id="2e7d8-158">Meaning</span></span>
------ | -------
`\$` | <span data-ttu-id="2e7d8-159">在输入字符串中查找美元符号 ($) 的一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-159">Look for a single occurrence of the dollar symbol ($) in the input string.</span></span> <span data-ttu-id="2e7d8-160">正则表达式模式字符串包含一个反斜杠来指示按字面解释美元符号而非将其作为正则表达式定位点。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-160">The regular expression pattern string includes a backslash to indicate that the dollar symbol is to be interpreted literally rather than as a regular expression anchor.</span></span> <span data-ttu-id="2e7d8-161">（单独的 $ 符号将指示正则表达式引擎应尝试在字符串的末尾开始匹配。）为了确保当前区域性的货币符号不错误地解释为正则表达式符号，该示例调用 [Escape](xref:System.Text.RegularExpressions.Regex.Escape(System.String)) 方法来对字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-161">(The $ symbol alone would indicate that the regular expression engine should try to begin its match at the end of a string.) To ensure that the current culture's currency symbol is not misinterpreted as a regular expression symbol, the example calls the [Escape](xref:System.Text.RegularExpressions.Regex.Escape(System.String)) method to escape the character.</span></span>
`\s*` | <span data-ttu-id="2e7d8-162">查找空白字符的零个或多个匹配项。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-162">Look for zero or more occurrences of a white-space character.</span></span>
`[-+]?` | <span data-ttu-id="2e7d8-163">查找正号或负号的零个或一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-163">Look for zero or one occurrence of either a positive sign or a negative sign.</span></span>
`([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)` | <span data-ttu-id="2e7d8-164">括起此表达式的外部括号将表达式定义为捕获组或子表达式。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-164">The outer parentheses around this expression define it as a capturing group or a subexpression.</span></span> <span data-ttu-id="2e7d8-165">如果找到匹配项，则有关匹配字符串的此部分的信息可以从第二个 [Group](xref:System.Text.RegularExpressions.Group) 对象中检索（该对象位于 [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) 属性所返回的 [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) 对象中）。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-165">If a match is found, information about this part of the matching string can be retrieved from the second [Group](xref:System.Text.RegularExpressions.Group) object in the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) object returned by the [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) property.</span></span> <span data-ttu-id="2e7d8-166">（集合中的第一个元素表示整个匹配。）</span><span class="sxs-lookup"><span data-stu-id="2e7d8-166">(The first element in the collection represents the entire match.)</span></span>
`[0-9]{0,3}` | <span data-ttu-id="2e7d8-167">查找十进制数字 0 到 9 的零到三个匹配项。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-167">Look for zero to three occurrences of the decimal digits 0 through 9.</span></span>
`(,[0-9]{3})*` | <span data-ttu-id="2e7d8-168">查找后跟三个十进制数字的组分隔符的零个或多个匹配项。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-168">Look for zero or more occurrences of a group separator followed by three decimal digits.</span></span>
`\.` | <span data-ttu-id="2e7d8-169">查找小数分隔符的一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-169">Look for a single occurrence of the decimal separator.</span></span>
`[0-9]+` | <span data-ttu-id="2e7d8-170">查找一个或多个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-170">Look for one or more decimal digits.</span></span>
`(\.[0-9]+)?` | <span data-ttu-id="2e7d8-171">查找后跟至少一个十进制数字的小数分隔符的零个或一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-171">Look for zero or one occurrence of the decimal separator followed by at least one decimal digit.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2e7d8-172">相关主题</span><span class="sxs-lookup"><span data-stu-id="2e7d8-172">Related Topics</span></span>

<span data-ttu-id="2e7d8-173">标题</span><span class="sxs-lookup"><span data-stu-id="2e7d8-173">Title</span></span> | <span data-ttu-id="2e7d8-174">描述</span><span class="sxs-lookup"><span data-stu-id="2e7d8-174">Description</span></span>
----- | -----------
[<span data-ttu-id="2e7d8-175">正则表达式语言 - 快速参考</span><span class="sxs-lookup"><span data-stu-id="2e7d8-175">Regular expression language - quick reference</span></span>](quick-ref.md) | <span data-ttu-id="2e7d8-176">提供有关可用来定义正则表达式的字符集、运算符和构造的信息。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-176">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
[<span data-ttu-id="2e7d8-177">正则表达式对象模型</span><span class="sxs-lookup"><span data-stu-id="2e7d8-177">The regular expression object model</span></span>](object-model.md) | <span data-ttu-id="2e7d8-178">提供演示如何使用正则表达式类的信息和代码示例。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-178">Provides information and code examples that illustrate how to use the regular expression classes.</span></span>
[<span data-ttu-id="2e7d8-179">正则表达式行为的详细信息</span><span class="sxs-lookup"><span data-stu-id="2e7d8-179">Details of regular expression behavior</span></span>](regex-behavior.md) | <span data-ttu-id="2e7d8-180">提供有关 .NET 正则表达式的功能和行为的信息。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-180">Provides information about the capabilities and behavior of .NETregular expressions.</span></span>
[<span data-ttu-id="2e7d8-181">正则表达式示例</span><span class="sxs-lookup"><span data-stu-id="2e7d8-181">Regular expression examples</span></span>](regex-examples.md) | <span data-ttu-id="2e7d8-182">提供演示正则表达式的典型用法的代码示例。</span><span class="sxs-lookup"><span data-stu-id="2e7d8-182">Provides code examples that illustrate typical uses of regular expressions.</span></span>


## <a name="reference"></a><span data-ttu-id="2e7d8-183">参考</span><span class="sxs-lookup"><span data-stu-id="2e7d8-183">Reference</span></span>

[<span data-ttu-id="2e7d8-184">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="2e7d8-184">System.Text.RegularExpressions</span></span>](xref:System.Text.RegularExpressions)

[<span data-ttu-id="2e7d8-185">System.Text.RegularExpressions.Regex</span><span class="sxs-lookup"><span data-stu-id="2e7d8-185">System.Text.RegularExpressions.Regex</span></span>](xref:System.Text.RegularExpressions.Regex)


