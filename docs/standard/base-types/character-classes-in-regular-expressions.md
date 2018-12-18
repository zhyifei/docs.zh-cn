---
title: .NET 正则表达式中的字符类
description: 了解如何使用字符类表示 .NET 正则表达式中的一组字符。
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- character classes
- regular expressions, character classes
- characters, matching syntax
- .NET Framework regular expressions, character classes
ms.assetid: 0f8bffab-ee0d-4e0e-9a96-2b4a252bb7e4
author: rpetrusha
ms.author: ronpet
ms.custom: seodec18
ms.openlocfilehash: c82d4aac75fb31ec7741338fde046daefc754394
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131464"
---
# <a name="character-classes-in-regular-expressions"></a><span data-ttu-id="f2a64-103">正则表达式中的字符类</span><span class="sxs-lookup"><span data-stu-id="f2a64-103">Character Classes in Regular Expressions</span></span>
<a name="Top"></a><span data-ttu-id="f2a64-104">一个字符类定义一组字符，其中的任一字符均可出现在输入字符串中以便成功匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-104">A character class defines a set of characters, any one of which can occur in an input string for a match to succeed.</span></span> <span data-ttu-id="f2a64-105">.NET 中的正则表达式语言支持以下字符类：</span><span class="sxs-lookup"><span data-stu-id="f2a64-105">The regular expression language in .NET supports the following character classes:</span></span>  
  
-   <span data-ttu-id="f2a64-106">正字符组。</span><span class="sxs-lookup"><span data-stu-id="f2a64-106">Positive character groups.</span></span> <span data-ttu-id="f2a64-107">输入字符串中的字符必须匹配一组指定的字符中的某个字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-107">A character in the input string must match one of a specified set of characters.</span></span> <span data-ttu-id="f2a64-108">有关详细信息，请参阅[正字符组](#PositiveGroup)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-108">For more information, see [Positive Character Group](#PositiveGroup).</span></span>  
  
-   <span data-ttu-id="f2a64-109">负字符组。</span><span class="sxs-lookup"><span data-stu-id="f2a64-109">Negative character groups.</span></span> <span data-ttu-id="f2a64-110">输入字符串中的字符不得匹配一组指定的字符中的某个字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-110">A character in the input string must not match one of a specified set of characters.</span></span> <span data-ttu-id="f2a64-111">有关详细信息，请参阅[负字符组](#NegativeGroup)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-111">For more information, see [Negative Character Group](#NegativeGroup).</span></span>  
  
-   <span data-ttu-id="f2a64-112">任意字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-112">Any character.</span></span> <span data-ttu-id="f2a64-113">正则表达式中的 `.`（圆点或句点）字符是匹配除 `\n` 之外的任何字符的通配符字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-113">The `.` (dot or period) character in a regular expression is a wildcard character that matches any character except `\n`.</span></span> <span data-ttu-id="f2a64-114">有关详细信息，请参阅[任意字符](#AnyCharacter)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-114">For more information, see [Any Character](#AnyCharacter).</span></span>  
  
-   <span data-ttu-id="f2a64-115">通用 Unicode 类别或命名块。</span><span class="sxs-lookup"><span data-stu-id="f2a64-115">A general Unicode category or named block.</span></span> <span data-ttu-id="f2a64-116">输入字符串中的字符必须为特定 Unicode 类别的成员，或必须位于一系列连续的 Unicode 字符中才能成功匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-116">A character in the input string must be a member of a particular Unicode category or must fall within a contiguous range of Unicode characters for a match to succeed.</span></span> <span data-ttu-id="f2a64-117">有关详细信息，请参阅 [Unicode 类别或 Unicode 块](#CategoryOrBlock)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-117">For more information, see [Unicode Category or Unicode Block](#CategoryOrBlock).</span></span>  
  
-   <span data-ttu-id="f2a64-118">负通用 Unicode 类别或命名块。</span><span class="sxs-lookup"><span data-stu-id="f2a64-118">A negative general Unicode category or named block.</span></span> <span data-ttu-id="f2a64-119">输入字符串中的字符不得为特定 Unicode 类别的成员，也不得位于一系列连续的 Unicode 字符中以便成功匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-119">A character in the input string must not be a member of a particular Unicode category or must not fall within a contiguous range of Unicode characters for a match to succeed.</span></span> <span data-ttu-id="f2a64-120">有关详细信息，请参阅[负 Unicode 类别或 Unicode 块](#NegativeCategoryOrBlock)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-120">For more information, see [Negative Unicode Category or Unicode Block](#NegativeCategoryOrBlock).</span></span>  
  
-   <span data-ttu-id="f2a64-121">单词字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-121">A word character.</span></span> <span data-ttu-id="f2a64-122">输入字符串中的字符可以属于适合单词中字符的任何 Unicode 类别。</span><span class="sxs-lookup"><span data-stu-id="f2a64-122">A character in the input string can belong to any of the Unicode categories that are appropriate for characters in words.</span></span> <span data-ttu-id="f2a64-123">有关详细信息，请参阅[单词字符](#WordCharacter)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-123">For more information, see [Word Character](#WordCharacter).</span></span>  
  
-   <span data-ttu-id="f2a64-124">非单词字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-124">A non-word character.</span></span> <span data-ttu-id="f2a64-125">输入字符串中的字符可以属于作为非单词字符的任何 Unicode 类别。</span><span class="sxs-lookup"><span data-stu-id="f2a64-125">A character in the input string can belong to any Unicode category that is not a word character.</span></span> <span data-ttu-id="f2a64-126">有关详细信息，请参阅[非单词字符](#NonWordCharacter)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-126">For more information, see [Non-Word Character](#NonWordCharacter).</span></span>  
  
-   <span data-ttu-id="f2a64-127">空白字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-127">A white-space character.</span></span> <span data-ttu-id="f2a64-128">输入字符串中的字符可以是任何 Unicode 分隔符字符以及众多控制字符中的任一字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-128">A character in the input string can be any Unicode separator character, as well as any one of a number of control characters.</span></span> <span data-ttu-id="f2a64-129">有关详细信息，请参阅[空白字符](#WhitespaceCharacter)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-129">For more information, see [White-Space Character](#WhitespaceCharacter).</span></span>  
  
-   <span data-ttu-id="f2a64-130">非空白字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-130">A non-white-space character.</span></span> <span data-ttu-id="f2a64-131">输入字符串中的字符可以是作为非空白字符的任何字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-131">A character in the input string can be any character that is not a white-space character.</span></span> <span data-ttu-id="f2a64-132">有关详细信息，请参阅[非空白字符](#NonWhitespaceCharacter)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-132">For more information, see [Non-White-Space Character](#NonWhitespaceCharacter).</span></span>  
  
-   <span data-ttu-id="f2a64-133">十进制数字。</span><span class="sxs-lookup"><span data-stu-id="f2a64-133">A decimal digit.</span></span> <span data-ttu-id="f2a64-134">输入字符串中的字符可以是归类为 Unicode 十进制数字的众多字符中的任一字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-134">A character in the input string can be any of a number of characters classified as Unicode decimal digits.</span></span> <span data-ttu-id="f2a64-135">有关详细信息，请参阅[十进制数字字符](#DigitCharacter)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-135">For more information, see [Decimal Digit Character](#DigitCharacter).</span></span>  
  
-   <span data-ttu-id="f2a64-136">非十进制数字。</span><span class="sxs-lookup"><span data-stu-id="f2a64-136">A non-decimal digit.</span></span> <span data-ttu-id="f2a64-137">输入字符串中的字符可以是任何非 Unicode 十进制数字。</span><span class="sxs-lookup"><span data-stu-id="f2a64-137">A character in the input string can be anything other than a Unicode decimal digit.</span></span> <span data-ttu-id="f2a64-138">有关详细信息，请参阅[十进制数字字符](#NonDigitCharacter)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-138">For more information, see [Decimal Digit Character](#NonDigitCharacter).</span></span>  
  
 <span data-ttu-id="f2a64-139">.NET 支持字符类减法表达式，通过该表达式可以定义一组字符作为从一个字符类中排除另一字符类的结果。</span><span class="sxs-lookup"><span data-stu-id="f2a64-139">.NET supports character class subtraction expressions, which enables you to define a set of characters as the result of excluding one character class from another character class.</span></span> <span data-ttu-id="f2a64-140">有关详细信息，请参阅[字符类减法](#CharacterClassSubtraction)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-140">For more information, see [Character Class Subtraction](#CharacterClassSubtraction).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2a64-141">按类别匹配字符的字符类（如用于匹配字词字符的 [\w](#WordCharacter)，或用于匹配 Unicode 类别的 [\p{}](#CategoryOrBlock)）依赖 <xref:System.Globalization.CharUnicodeInfo> 类提供字符类别信息。</span><span class="sxs-lookup"><span data-stu-id="f2a64-141">Character classes that match characters by category, such as [\w](#WordCharacter) to match word characters or [\p{}](#CategoryOrBlock) to match a Unicode category, rely on the <xref:System.Globalization.CharUnicodeInfo> class to provide information about character categories.</span></span>  <span data-ttu-id="f2a64-142">从 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 开始，字符类别基于 [Unicode 标准 8.0.0 版](https://www.unicode.org/versions/Unicode8.0.0/)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-142">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], character categories are based on [The Unicode Standard, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/).</span></span> <span data-ttu-id="f2a64-143">在 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 到 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 之间，字符类别基于 [Unicode 标准 6.3.0 版](https://www.unicode.org/versions/Unicode6.3.0/)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-143">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] through the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], they are based on [The Unicode Standard, Version 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/).</span></span>  
  
<a name="PositiveGroup"></a>   
## <a name="positive-character-group--"></a><span data-ttu-id="f2a64-144">正字符组：[ ]</span><span class="sxs-lookup"><span data-stu-id="f2a64-144">Positive Character Group: [ ]</span></span>  
 <span data-ttu-id="f2a64-145">正字符组指定一个字符列表，其中的任何一个字符可出现在输入字符串中以便进行匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-145">A positive character group specifies a list of characters, any one of which may appear in an input string for a match to occur.</span></span> <span data-ttu-id="f2a64-146">此字符列表可以单独指定和/或作为范围指定。</span><span class="sxs-lookup"><span data-stu-id="f2a64-146">This list of characters may be specified individually, as a range, or both.</span></span>  
  
 <span data-ttu-id="f2a64-147">用于指定各个字符列表的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="f2a64-147">The syntax for specifying a list of individual characters is as follows:</span></span>  
  
 <span data-ttu-id="f2a64-148">[character_group]</span><span class="sxs-lookup"><span data-stu-id="f2a64-148">[*character_group*]</span></span>  
  
 <span data-ttu-id="f2a64-149">其中，*character_group* 是单个字符的列表，这些字符可出现在输入字符串中以便成功匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-149">where *character_group* is a list of the individual characters that can appear in the input string for a match to succeed.</span></span> <span data-ttu-id="f2a64-150">character_group 可以包含一个或多个文本字符、[转义字符](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md)或字符类的任意组合。</span><span class="sxs-lookup"><span data-stu-id="f2a64-150">*character_group* can consist of any combination of one or more literal characters, [escape characters](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md), or character classes.</span></span>  
  
 <span data-ttu-id="f2a64-151">用于指定字符范围的语法如下：</span><span class="sxs-lookup"><span data-stu-id="f2a64-151">The syntax for specifying a range of characters is as follows:</span></span>  
  
```  
[firstCharacter-lastCharacter]  
```  
  
 <span data-ttu-id="f2a64-152">其中，*firstCharacter* 是范围的开始字符，*lastCharacter* 是范围的结束字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-152">where *firstCharacter* is the character that begins the range and *lastCharacter* is the character that ends the range.</span></span> <span data-ttu-id="f2a64-153">字符范围是通过以下方式定义的一系列连续字符：指定系列中的第一个字符，连字符 (-)，然后指定系列中的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-153">A character range is a contiguous series of characters defined by specifying the first character in the series, a hyphen (-), and then the last character in the series.</span></span> <span data-ttu-id="f2a64-154">如果两个字符具有相邻的 Unicode 码位，则这两个字符是连续的。</span><span class="sxs-lookup"><span data-stu-id="f2a64-154">Two characters are contiguous if they have adjacent Unicode code points.</span></span>  
  
 <span data-ttu-id="f2a64-155">下表列出了一些常见的包含正字符类的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="f2a64-155">Some common regular expression patterns that contain positive character classes are listed in the following table.</span></span>  
  
|<span data-ttu-id="f2a64-156">模式</span><span class="sxs-lookup"><span data-stu-id="f2a64-156">Pattern</span></span>|<span data-ttu-id="f2a64-157">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-157">Description</span></span>|  
|-------------|-----------------|  
|`[aeiou]`|<span data-ttu-id="f2a64-158">匹配所有元音。</span><span class="sxs-lookup"><span data-stu-id="f2a64-158">Match all vowels.</span></span>|  
|`[\p{P}\d]`|<span data-ttu-id="f2a64-159">匹配所有标点符号和十进制数字字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-159">Match all punctuation and decimal digit characters.</span></span>|  
|`[\s\p{P}]`|<span data-ttu-id="f2a64-160">匹配所有空白和标点符号。</span><span class="sxs-lookup"><span data-stu-id="f2a64-160">Match all white space and punctuation.</span></span>|  
  
 <span data-ttu-id="f2a64-161">下面的示例定义包含字符“a”和“e”的正字符组，以使输入字符串必须包含单词“grey”或“gray”且后跟另一个单词以便进行匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-161">The following example defines a positive character group that contains the characters "a" and "e" so that the input string must contain the words "grey" or "gray" followed by another word for a match to occur.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/positivecharclasses.cs#1)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/positivecharclasses.vb#1)]  
  
 <span data-ttu-id="f2a64-162">按以下方式定义正则表达式 `gr[ae]y\s\S+?[\s|\p{P}]`：</span><span class="sxs-lookup"><span data-stu-id="f2a64-162">The regular expression `gr[ae]y\s\S+?[\s|\p{P}]` is defined as follows:</span></span>  
  
|<span data-ttu-id="f2a64-163">模式</span><span class="sxs-lookup"><span data-stu-id="f2a64-163">Pattern</span></span>|<span data-ttu-id="f2a64-164">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-164">Description</span></span>|  
|-------------|-----------------|  
|`gr`|<span data-ttu-id="f2a64-165">匹配文本字符“gr”。</span><span class="sxs-lookup"><span data-stu-id="f2a64-165">Match the literal characters "gr".</span></span>|  
|`[ae]`|<span data-ttu-id="f2a64-166">匹配“a”或“e”。</span><span class="sxs-lookup"><span data-stu-id="f2a64-166">Match either an "a" or an "e".</span></span>|  
|`y\s`|<span data-ttu-id="f2a64-167">匹配后跟空白字符的文本字符“y”。</span><span class="sxs-lookup"><span data-stu-id="f2a64-167">Match the literal character "y" followed by a white-space character.</span></span>|  
|`\S+?`|<span data-ttu-id="f2a64-168">匹配一个或多个非空白字符（但尽可能少）。</span><span class="sxs-lookup"><span data-stu-id="f2a64-168">Match one or more non-white-space characters, but as few as possible.</span></span>|  
|`[\s\p{P}]`|<span data-ttu-id="f2a64-169">匹配空白字符或标点符号。</span><span class="sxs-lookup"><span data-stu-id="f2a64-169">Match either a white-space character or a punctuation mark.</span></span>|  
  
 <span data-ttu-id="f2a64-170">下面的示例匹配以任何大写字母开头的单词。</span><span class="sxs-lookup"><span data-stu-id="f2a64-170">The following example matches words that begin with any capital letter.</span></span> <span data-ttu-id="f2a64-171">它使用子表达式 `[A-Z]` 表示从 A 到 Z 的大写字母范围。</span><span class="sxs-lookup"><span data-stu-id="f2a64-171">It uses the subexpression `[A-Z]` to represent the range of capital letters from A to Z.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/range.cs#3)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/range.vb#3)]  
  
 <span data-ttu-id="f2a64-172">正则表达式 `\b[A-Z]\w*\b` 的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="f2a64-172">The regular expression `\b[A-Z]\w*\b` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="f2a64-173">模式</span><span class="sxs-lookup"><span data-stu-id="f2a64-173">Pattern</span></span>|<span data-ttu-id="f2a64-174">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-174">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="f2a64-175">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="f2a64-175">Start at a word boundary.</span></span>|  
|`[A-Z]`|<span data-ttu-id="f2a64-176">匹配从 A 到 Z 的所有大写字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-176">Match any uppercase character from A to Z.</span></span>|  
|`\w*`|<span data-ttu-id="f2a64-177">匹配零个或多个单词字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-177">Match zero or more word characters.</span></span>|  
|`\b`|<span data-ttu-id="f2a64-178">与字边界匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-178">Match a word boundary.</span></span>|  
  
 [<span data-ttu-id="f2a64-179">返回页首</span><span class="sxs-lookup"><span data-stu-id="f2a64-179">Back to Top</span></span>](#Top)  
  
<a name="NegativeGroup"></a>   
## <a name="negative-character-group-"></a><span data-ttu-id="f2a64-180">负字符组：[^]</span><span class="sxs-lookup"><span data-stu-id="f2a64-180">Negative Character Group: [^]</span></span>  
 <span data-ttu-id="f2a64-181">负字符组指定一个字符列表，这些字符不得出现在输入字符串中以便进行匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-181">A negative character group specifies a list of characters that must not appear in an input string for a match to occur.</span></span> <span data-ttu-id="f2a64-182">此字符列表可以单独指定和/或作为范围指定。</span><span class="sxs-lookup"><span data-stu-id="f2a64-182">The list of characters may be specified individually, as a range, or both.</span></span>  
  
 <span data-ttu-id="f2a64-183">用于指定各个字符列表的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="f2a64-183">The syntax for specifying a list of individual characters is as follows:</span></span>  
  
 <span data-ttu-id="f2a64-184">[^character_group]</span><span class="sxs-lookup"><span data-stu-id="f2a64-184">[*^character_group*]</span></span>  
  
 <span data-ttu-id="f2a64-185">其中，*character_group* 是单个字符的列表，这些字符不可出现在输入字符串中以便成功匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-185">where *character_group* is a list of the individual characters that cannot appear in the input string for a match to succeed.</span></span> <span data-ttu-id="f2a64-186">character_group 可以包含一个或多个文本字符、[转义字符](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md)或字符类的任意组合。</span><span class="sxs-lookup"><span data-stu-id="f2a64-186">*character_group* can consist of any combination of one or more literal characters, [escape characters](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md), or character classes.</span></span>  
  
 <span data-ttu-id="f2a64-187">用于指定字符范围的语法如下：</span><span class="sxs-lookup"><span data-stu-id="f2a64-187">The syntax for specifying a range of characters is as follows:</span></span>  
  
 <span data-ttu-id="f2a64-188">[^firstCharacter-lastCharacter]</span><span class="sxs-lookup"><span data-stu-id="f2a64-188">[^*firstCharacter*-*lastCharacter*]</span></span>  
  
 <span data-ttu-id="f2a64-189">其中，*firstCharacter* 是范围的开始字符，*lastCharacter* 是范围的结束字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-189">where *firstCharacter* is the character that begins the range, and *lastCharacter* is the character that ends the range.</span></span> <span data-ttu-id="f2a64-190">字符范围是通过以下方式定义的一系列连续字符：指定系列中的第一个字符，连字符 (-)，然后指定系列中的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-190">A character range is a contiguous series of characters defined by specifying the first character in the series, a hyphen (-), and then the last character in the series.</span></span> <span data-ttu-id="f2a64-191">如果两个字符具有相邻的 Unicode 码位，则这两个字符是连续的。</span><span class="sxs-lookup"><span data-stu-id="f2a64-191">Two characters are contiguous if they have adjacent Unicode code points.</span></span>  
  
 <span data-ttu-id="f2a64-192">可以连接两个或更多字符范围。</span><span class="sxs-lookup"><span data-stu-id="f2a64-192">Two or more character ranges can be concatenated.</span></span> <span data-ttu-id="f2a64-193">例如，若要指定从“0”至“9”的十进制数范围、从“a”至“f”的小写字母范围，以及从“A”至“F”的大写字母范围，请使用 `[0-9a-fA-F]`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-193">For example, to specify the range of decimal digits from "0" through "9", the range of lowercase letters from "a" through "f", and the range of uppercase letters from "A" through "F", use `[0-9a-fA-F]`.</span></span>  
  
 <span data-ttu-id="f2a64-194">负字符组中的前导符 (`^`) 是强制的，指示字符组为负字符组，而不是正字符组。</span><span class="sxs-lookup"><span data-stu-id="f2a64-194">The leading carat character (`^`) in a negative character group is mandatory and indicates the character group is a negative character group instead of a positive character group.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f2a64-195">较大正则表达式模式中的负字符组不是零宽度断言。</span><span class="sxs-lookup"><span data-stu-id="f2a64-195">A negative character group in a larger regular expression pattern is not a zero-width assertion.</span></span> <span data-ttu-id="f2a64-196">也就是说，在评估负字符组后，正则表达式引擎会在输入字符串中提升一个字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-196">That is, after evaluating the negative character group, the regular expression engine advances one character in the input string.</span></span>  
  
 <span data-ttu-id="f2a64-197">下表列出了一些常见的包含负字符组的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="f2a64-197">Some common regular expression patterns that contain negative character groups are listed in the following table.</span></span>  
  
|<span data-ttu-id="f2a64-198">模式</span><span class="sxs-lookup"><span data-stu-id="f2a64-198">Pattern</span></span>|<span data-ttu-id="f2a64-199">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-199">Description</span></span>|  
|-------------|-----------------|  
|`[^aeiou]`|<span data-ttu-id="f2a64-200">匹配除元音以外的所有字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-200">Match all characters except vowels.</span></span>|  
|`[^\p{P}\d]`|<span data-ttu-id="f2a64-201">匹配标点符号和十进制数字字符以外的所有字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-201">Match all characters except punctuation and decimal digit characters.</span></span>|  
  
 <span data-ttu-id="f2a64-202">下面的示例匹配以字符“th”开头且后面不跟“o”的任何单词。</span><span class="sxs-lookup"><span data-stu-id="f2a64-202">The following example matches any word that begins with the characters "th" and is not followed by an "o".</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/negativecharclasses.cs#2)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/negativecharclasses.vb#2)]  
  
 <span data-ttu-id="f2a64-203">正则表达式 `\bth[^o]\w+\b` 的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="f2a64-203">The regular expression `\bth[^o]\w+\b` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="f2a64-204">模式</span><span class="sxs-lookup"><span data-stu-id="f2a64-204">Pattern</span></span>|<span data-ttu-id="f2a64-205">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-205">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="f2a64-206">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="f2a64-206">Start at a word boundary.</span></span>|  
|`th`|<span data-ttu-id="f2a64-207">匹配文本字符“th”。</span><span class="sxs-lookup"><span data-stu-id="f2a64-207">Match the literal characters "th".</span></span>|  
|`[^o]`|<span data-ttu-id="f2a64-208">与不是“o”的任何字符匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-208">Match any character that is not an "o".</span></span>|  
|`\w+`|<span data-ttu-id="f2a64-209">匹配一个或多个单词字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-209">Match one or more word characters.</span></span>|  
|`\b`|<span data-ttu-id="f2a64-210">在字边界结束。</span><span class="sxs-lookup"><span data-stu-id="f2a64-210">End at a word boundary.</span></span>|  
  
 [<span data-ttu-id="f2a64-211">返回页首</span><span class="sxs-lookup"><span data-stu-id="f2a64-211">Back to Top</span></span>](#Top)  
  
<a name="AnyCharacter"></a>   
## <a name="any-character-"></a><span data-ttu-id="f2a64-212">任意字符：.</span><span class="sxs-lookup"><span data-stu-id="f2a64-212">Any Character: .</span></span>  
 <span data-ttu-id="f2a64-213">句点字符 (.) 匹配除 `\n`（换行符 \u000A）之外的任何字符，有以下两个限制：</span><span class="sxs-lookup"><span data-stu-id="f2a64-213">The period character (.) matches any character except `\n` (the newline character, \u000A), with the following two qualifications:</span></span>  
  
-   <span data-ttu-id="f2a64-214">如果通过 <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> 选项修改正则表达式模式，或者通过 `.` 选项修改包含 `s` 字符类的模式的部分，则 `.` 可匹配任何字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-214">If a regular expression pattern is modified by the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option, or if the portion of the pattern that contains the `.` character class is modified by the `s` option, `.` matches any character.</span></span> <span data-ttu-id="f2a64-215">有关详细信息，请参阅 [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-215">For more information, see [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
     <span data-ttu-id="f2a64-216">下面的示例阐释了默认情况下以及使用 `.` 选项的情况下 <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> 字符类的不同的行为。</span><span class="sxs-lookup"><span data-stu-id="f2a64-216">The following example illustrates the different behavior of the `.` character class by default and with the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option.</span></span> <span data-ttu-id="f2a64-217">正则表达式 `^.+` 在字符串开头开始并匹配每个字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-217">The regular expression `^.+` starts at the beginning of the string and matches every character.</span></span> <span data-ttu-id="f2a64-218">默认情况下，匹配在第一行的结尾结束；正则表达式模式匹配回车符、`\r` 或 \u000D，但不匹配 `\n`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-218">By default, the match ends at the end of the first line; the regular expression pattern matches the carriage return character, `\r` or \u000D, but it does not match `\n`.</span></span> <span data-ttu-id="f2a64-219">由于 <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> 选项将整个输入字符串解释为单行，因此它匹配输入字符串中的每个字符，包括 `\n`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-219">Because the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option interprets the entire input string as a single line, it matches every character in the input string, including `\n`.</span></span>  
  
     [!code-csharp[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any2.cs#5)]
     [!code-vb[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any2.vb#5)]  
  
> [!NOTE]
>  <span data-ttu-id="f2a64-220">由于它匹配除 `\n` 之外的任何字符，因此 `.` 字符类也匹配 `\r`（回车符 \u000D）。</span><span class="sxs-lookup"><span data-stu-id="f2a64-220">Because it matches any character except `\n`, the `.` character class also matches `\r` (the carriage return character, \u000D).</span></span>  
  
-   <span data-ttu-id="f2a64-221">正字符组或负字符组中的句点字符将被视为原义句点字符，而非字符类。</span><span class="sxs-lookup"><span data-stu-id="f2a64-221">In a positive or negative character group, a period is treated as a literal period character, and not as a character class.</span></span> <span data-ttu-id="f2a64-222">有关详细信息，请参阅本主题前面部分的[正字符组](#PositiveGroup)和[负字符组](#NegativeGroup)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-222">For more information, see [Positive Character Group](#PositiveGroup) and [Negative Character Group](#NegativeGroup) earlier in this topic.</span></span> <span data-ttu-id="f2a64-223">下面的示例通过定义包括句点字符 (`.`) 的正则表达式作为字符类和正字符组的成员来进行这方面的演示。</span><span class="sxs-lookup"><span data-stu-id="f2a64-223">The following example provides an illustration by defining a regular expression that includes the period character (`.`) both as a character class and as a member of a positive character group.</span></span> <span data-ttu-id="f2a64-224">正则表达式 `\b.*[.?!;:](\s|\z)` 在字边界处开始，匹配任何字符直到遇到五个标点符号标记之一（包括句点），然后匹配空白字符或字符串的末尾。</span><span class="sxs-lookup"><span data-stu-id="f2a64-224">The regular expression `\b.*[.?!;:](\s|\z)` begins at a word boundary, matches any character until it encounters one of five punctuation marks, including a period, and then matches either a white-space character or the end of the string.</span></span>  
  
     [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any1.cs#4)]
     [!code-vb[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any1.vb#4)]  
  
> [!NOTE]
>  <span data-ttu-id="f2a64-225">由于它匹配任何字符，因此当正则表达式模式尝试多次匹配任何字符时，`.` 语言元素通常会与惰性限定符一起使用。</span><span class="sxs-lookup"><span data-stu-id="f2a64-225">Because it matches any character, the `.` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any character multiple times.</span></span> <span data-ttu-id="f2a64-226">有关更多信息，请参见 [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-226">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 [<span data-ttu-id="f2a64-227">返回页首</span><span class="sxs-lookup"><span data-stu-id="f2a64-227">Back to Top</span></span>](#Top)  
  
<a name="CategoryOrBlock"></a>   
## <a name="unicode-category-or-unicode-block-p"></a><span data-ttu-id="f2a64-228">Unicode 类别或 Unicode 块：\p{}</span><span class="sxs-lookup"><span data-stu-id="f2a64-228">Unicode Category or Unicode Block: \p{}</span></span>  
 <span data-ttu-id="f2a64-229">Unicode 标准为每个常规类别分配一个字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-229">The Unicode standard assigns each character a general category.</span></span> <span data-ttu-id="f2a64-230">例如，特定字符可以是大写字母（由 `Lu` 类别表示），十进制数字（`Nd` 类别）、数学符号（`Sm` 类别）或段落分隔符（`Zl` 类别）。</span><span class="sxs-lookup"><span data-stu-id="f2a64-230">For example, a particular character can be an uppercase letter (represented by the `Lu` category), a decimal digit (the `Nd` category), a math symbol (the `Sm` category), or a paragraph separator (the `Zl` category).</span></span> <span data-ttu-id="f2a64-231">Unicode 标准中的特定字符集也占据连续码位的特定区域或块。</span><span class="sxs-lookup"><span data-stu-id="f2a64-231">Specific character sets in the Unicode standard also occupy a specific range or block of consecutive code points.</span></span> <span data-ttu-id="f2a64-232">例如，可在 \u0000 和 \u007F 之间找到基本拉丁字符集，并可在 \u0600 和 \u06FF 之间找到阿拉伯语字符集。</span><span class="sxs-lookup"><span data-stu-id="f2a64-232">For example, the basic Latin character set is found from \u0000 through \u007F, while the Arabic character set is found from \u0600 through \u06FF.</span></span>  
  
 <span data-ttu-id="f2a64-233">正则表达式构造</span><span class="sxs-lookup"><span data-stu-id="f2a64-233">The regular expression construct</span></span>  
  
 <span data-ttu-id="f2a64-234">`\p{` *name* `}`</span><span class="sxs-lookup"><span data-stu-id="f2a64-234">`\p{` *name* `}`</span></span>  
  
 <span data-ttu-id="f2a64-235">匹配属于 Unicode 常规类别或命名块的任何字符，其中，name 是类别缩写或命名块的名称。</span><span class="sxs-lookup"><span data-stu-id="f2a64-235">matches any character that belongs to a Unicode general category or named block, where *name* is the category abbreviation or named block name.</span></span> <span data-ttu-id="f2a64-236">有关类别缩写的列表，请参阅本主题稍后的[支持的 Unicode 常规类别](#SupportedUnicodeGeneralCategories)部分。</span><span class="sxs-lookup"><span data-stu-id="f2a64-236">For a list of category abbreviations, see the [Supported Unicode General Categories](#SupportedUnicodeGeneralCategories) section later in this topic.</span></span> <span data-ttu-id="f2a64-237">有关命名块的列表，请参阅本主题稍后的[支持的命名块](#SupportedNamedBlocks)部分。</span><span class="sxs-lookup"><span data-stu-id="f2a64-237">For a list of named blocks, see the [Supported Named Blocks](#SupportedNamedBlocks) section later in this topic.</span></span>  
  
 <span data-ttu-id="f2a64-238">下面的示例使用 `\p{`名称`}` 构造以匹配 Unicode 常规类别（在该示例中为 `Pd` 或“标点，短划线”类别）和命名块（`IsGreek` 和 `IsBasicLatin` 命名块）。</span><span class="sxs-lookup"><span data-stu-id="f2a64-238">The following example uses the `\p{`*name*`}` construct to match both a Unicode general category (in this case, the `Pd`, or Punctuation, Dash category) and a named block (the `IsGreek` and `IsBasicLatin` named blocks).</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/category1.cs#6)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/category1.vb#6)]  
  
 <span data-ttu-id="f2a64-239">正则表达式 `\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` 的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="f2a64-239">The regular expression `\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="f2a64-240">模式</span><span class="sxs-lookup"><span data-stu-id="f2a64-240">Pattern</span></span>|<span data-ttu-id="f2a64-241">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-241">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="f2a64-242">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="f2a64-242">Start at a word boundary.</span></span>|  
|`\p{IsGreek}+`|<span data-ttu-id="f2a64-243">匹配一个或多个希腊语字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-243">Match one or more Greek characters.</span></span>|  
|`(\s)?`|<span data-ttu-id="f2a64-244">匹配零个或一个空白字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-244">Match zero or one white-space character.</span></span>|  
|`(\p{IsGreek}+(\s)?)+`|<span data-ttu-id="f2a64-245">匹配一个或多个希腊语字符后跟零个或一个空白字符的模式一次或多次。</span><span class="sxs-lookup"><span data-stu-id="f2a64-245">Match the pattern of one or more Greek characters followed by zero or one white-space characters one or more times.</span></span>|  
|`\p{Pd}`|<span data-ttu-id="f2a64-246">匹配“标点，短划线”字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-246">Match a Punctuation, Dash character.</span></span>|  
|`\s`|<span data-ttu-id="f2a64-247">与空白字符匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-247">Match a white-space character.</span></span>|  
|`\p{IsBasicLatin}+`|<span data-ttu-id="f2a64-248">匹配一个或多个基本拉丁字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-248">Match one or more basic Latin characters.</span></span>|  
|`(\s)?`|<span data-ttu-id="f2a64-249">匹配零个或一个空白字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-249">Match zero or one white-space character.</span></span>|  
|`(\p{IsBasicLatin}+(\s)?)+`|<span data-ttu-id="f2a64-250">匹配一个或多个基本拉丁字符后跟零个或一个空白字符的模式一次或多次。</span><span class="sxs-lookup"><span data-stu-id="f2a64-250">Match the pattern of one or more basic Latin characters followed by zero or one white-space characters one or more times.</span></span>|  
  
 [<span data-ttu-id="f2a64-251">返回页首</span><span class="sxs-lookup"><span data-stu-id="f2a64-251">Back to Top</span></span>](#Top)  
  
<a name="NegativeCategoryOrBlock"></a>   
## <a name="negative-unicode-category-or-unicode-block-p"></a><span data-ttu-id="f2a64-252">负 Unicode 类别或 Unicode 块：\P{}</span><span class="sxs-lookup"><span data-stu-id="f2a64-252">Negative Unicode Category or Unicode Block: \P{}</span></span>  
 <span data-ttu-id="f2a64-253">Unicode 标准为每个常规类别分配一个字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-253">The Unicode standard assigns each character a general category.</span></span> <span data-ttu-id="f2a64-254">例如，特定字符可以是大写字母（由 `Lu` 类别表示），十进制数字（`Nd` 类别）、数学符号（`Sm` 类别）或段落分隔符（`Zl` 类别）。</span><span class="sxs-lookup"><span data-stu-id="f2a64-254">For example, a particular character can be an uppercase letter (represented by the `Lu` category), a decimal digit (the `Nd` category), a math symbol (the `Sm` category), or a paragraph separator (the `Zl` category).</span></span> <span data-ttu-id="f2a64-255">Unicode 标准中的特定字符集也占据连续码位的特定区域或块。</span><span class="sxs-lookup"><span data-stu-id="f2a64-255">Specific character sets in the Unicode standard also occupy a specific range or block of consecutive code points.</span></span> <span data-ttu-id="f2a64-256">例如，可在 \u0000 和 \u007F 之间找到基本拉丁字符集，并可在 \u0600 和 \u06FF 之间找到阿拉伯语字符集。</span><span class="sxs-lookup"><span data-stu-id="f2a64-256">For example, the basic Latin character set is found from \u0000 through \u007F, while the Arabic character set is found from \u0600 through \u06FF.</span></span>  
  
 <span data-ttu-id="f2a64-257">正则表达式构造</span><span class="sxs-lookup"><span data-stu-id="f2a64-257">The regular expression construct</span></span>  
  
 <span data-ttu-id="f2a64-258">`\P{` *name* `}`</span><span class="sxs-lookup"><span data-stu-id="f2a64-258">`\P{` *name* `}`</span></span>  
  
 <span data-ttu-id="f2a64-259">匹配不属于 Unicode 常规类别或命名块的任何字符，其中，name是类别缩写或命名块的名称。</span><span class="sxs-lookup"><span data-stu-id="f2a64-259">matches any character that does not belong to a Unicode general category or named block, where *name* is the category abbreviation or named block name.</span></span> <span data-ttu-id="f2a64-260">有关类别缩写的列表，请参阅本主题稍后的[支持的 Unicode 常规类别](#SupportedUnicodeGeneralCategories)部分。</span><span class="sxs-lookup"><span data-stu-id="f2a64-260">For a list of category abbreviations, see the [Supported Unicode General Categories](#SupportedUnicodeGeneralCategories) section later in this topic.</span></span> <span data-ttu-id="f2a64-261">有关命名块的列表，请参阅本主题稍后的[支持的命名块](#SupportedNamedBlocks)部分。</span><span class="sxs-lookup"><span data-stu-id="f2a64-261">For a list of named blocks, see the [Supported Named Blocks](#SupportedNamedBlocks) section later in this topic.</span></span>  
  
 <span data-ttu-id="f2a64-262">下面的示例使用 `\P{`name`}`构造来删除数字字符串中的任何货币符号（在该示例中为 `Sc` 或“符号，货币”类别）。</span><span class="sxs-lookup"><span data-stu-id="f2a64-262">The following example uses the `\P{`*name*`}` construct to remove any currency symbols (in this case, the `Sc`, or Symbol, Currency category) from numeric strings.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/notcategory1.cs#7)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/notcategory1.vb#7)]  
  
 <span data-ttu-id="f2a64-263">正则表达式模式 `(\P{Sc})+` 匹配不为货币符号的一个或多个字符；它有效地从结果字符串中抽出任何货币符号。</span><span class="sxs-lookup"><span data-stu-id="f2a64-263">The regular expression pattern `(\P{Sc})+` matches one or more characters that are not currency symbols; it effectively strips any currency symbol from the result string.</span></span>  
  
 [<span data-ttu-id="f2a64-264">返回页首</span><span class="sxs-lookup"><span data-stu-id="f2a64-264">Back to Top</span></span>](#Top)  
  
<a name="WordCharacter"></a>   
## <a name="word-character-w"></a><span data-ttu-id="f2a64-265">单词字符：\w</span><span class="sxs-lookup"><span data-stu-id="f2a64-265">Word Character: \w</span></span>  
 <span data-ttu-id="f2a64-266">`\w` 与任何单词字符匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-266">`\w` matches any word character.</span></span> <span data-ttu-id="f2a64-267">单词字符是下表中列出的任何 Unicode 类别的成员。</span><span class="sxs-lookup"><span data-stu-id="f2a64-267">A word character is a member of any of the Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="f2a64-268">类别</span><span class="sxs-lookup"><span data-stu-id="f2a64-268">Category</span></span>|<span data-ttu-id="f2a64-269">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-269">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="f2a64-270">Ll</span><span class="sxs-lookup"><span data-stu-id="f2a64-270">Ll</span></span>|<span data-ttu-id="f2a64-271">字母，小写</span><span class="sxs-lookup"><span data-stu-id="f2a64-271">Letter, Lowercase</span></span>|  
|<span data-ttu-id="f2a64-272">Lu</span><span class="sxs-lookup"><span data-stu-id="f2a64-272">Lu</span></span>|<span data-ttu-id="f2a64-273">字母，大写</span><span class="sxs-lookup"><span data-stu-id="f2a64-273">Letter, Uppercase</span></span>|  
|<span data-ttu-id="f2a64-274">Lt</span><span class="sxs-lookup"><span data-stu-id="f2a64-274">Lt</span></span>|<span data-ttu-id="f2a64-275">字母，首字母大写</span><span class="sxs-lookup"><span data-stu-id="f2a64-275">Letter, Titlecase</span></span>|  
|<span data-ttu-id="f2a64-276">Lo</span><span class="sxs-lookup"><span data-stu-id="f2a64-276">Lo</span></span>|<span data-ttu-id="f2a64-277">字母，其他</span><span class="sxs-lookup"><span data-stu-id="f2a64-277">Letter, Other</span></span>|  
|<span data-ttu-id="f2a64-278">Lm</span><span class="sxs-lookup"><span data-stu-id="f2a64-278">Lm</span></span>|<span data-ttu-id="f2a64-279">字母，修饰符</span><span class="sxs-lookup"><span data-stu-id="f2a64-279">Letter, Modifier</span></span>|  
|<span data-ttu-id="f2a64-280">Mn</span><span class="sxs-lookup"><span data-stu-id="f2a64-280">Mn</span></span>|<span data-ttu-id="f2a64-281">标记，非间距</span><span class="sxs-lookup"><span data-stu-id="f2a64-281">Mark, Nonspacing</span></span>|  
|<span data-ttu-id="f2a64-282">Nd</span><span class="sxs-lookup"><span data-stu-id="f2a64-282">Nd</span></span>|<span data-ttu-id="f2a64-283">数字，十进制数</span><span class="sxs-lookup"><span data-stu-id="f2a64-283">Number, Decimal Digit</span></span>|  
|<span data-ttu-id="f2a64-284">Pc</span><span class="sxs-lookup"><span data-stu-id="f2a64-284">Pc</span></span>|<span data-ttu-id="f2a64-285">标点，连接符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-285">Punctuation, Connector.</span></span> <span data-ttu-id="f2a64-286">此类别包含 10 个字符，最常用的字符是 LOWLINE 字符 (_)，u+005F。</span><span class="sxs-lookup"><span data-stu-id="f2a64-286">This category includes ten characters, the most commonly used of which is the LOWLINE character (_), u+005F.</span></span>|  
  
 <span data-ttu-id="f2a64-287">如果指定了符合 ECMAScript 的行为，则 `\w` 等效于 `[a-zA-Z_0-9]`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-287">If ECMAScript-compliant behavior is specified, `\w` is equivalent to `[a-zA-Z_0-9]`.</span></span> <span data-ttu-id="f2a64-288">有关 ECMAScript 正则表达式的信息，请参阅[正则表达式选项](../../../docs/standard/base-types/regular-expression-options.md)中的“ECMAScript 匹配行为”部分。</span><span class="sxs-lookup"><span data-stu-id="f2a64-288">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2a64-289">由于它匹配任何单词字符，因此当正则表达式模式尝试多次匹配任何单词字符且后跟特定单词字符时，`\w` 语言元素通常会与惰性限定符一起使用。</span><span class="sxs-lookup"><span data-stu-id="f2a64-289">Because it matches any word character, the `\w` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any word character multiple times, followed by a specific word character.</span></span> <span data-ttu-id="f2a64-290">有关更多信息，请参见 [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-290">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="f2a64-291">下面的示例使用 `\w` 语言元素来匹配单词中的重复字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-291">The following example uses the `\w` language element to match duplicate characters in a word.</span></span> <span data-ttu-id="f2a64-292">该示例定义可按如下方式解释的正则表达式模式 `(\w)\1`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-292">The example defines a regular expression pattern, `(\w)\1`, which can be interpreted as follows.</span></span>  
  
|<span data-ttu-id="f2a64-293">元素</span><span class="sxs-lookup"><span data-stu-id="f2a64-293">Element</span></span>|<span data-ttu-id="f2a64-294">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-294">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2a64-295">(\w)</span><span class="sxs-lookup"><span data-stu-id="f2a64-295">(\w)</span></span>|<span data-ttu-id="f2a64-296">匹配单词字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-296">Match a word character.</span></span> <span data-ttu-id="f2a64-297">这是第一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="f2a64-297">This is the first capturing group.</span></span>|  
|<span data-ttu-id="f2a64-298">\1</span><span class="sxs-lookup"><span data-stu-id="f2a64-298">\1</span></span>|<span data-ttu-id="f2a64-299">匹配第一次捕获的值。</span><span class="sxs-lookup"><span data-stu-id="f2a64-299">Match the value of the first capture.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/wordchar1.cs#8)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/wordchar1.vb#8)]  
  
 [<span data-ttu-id="f2a64-300">返回页首</span><span class="sxs-lookup"><span data-stu-id="f2a64-300">Back to Top</span></span>](#Top)  
  
<a name="NonWordCharacter"></a>   
## <a name="non-word-character-w"></a><span data-ttu-id="f2a64-301">非单词字符：\W</span><span class="sxs-lookup"><span data-stu-id="f2a64-301">Non-Word Character: \W</span></span>  
 <span data-ttu-id="f2a64-302">`\W` 匹配任何非单词字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-302">`\W` matches any non-word character.</span></span> <span data-ttu-id="f2a64-303">\W 语言元素等效于以下字符类：</span><span class="sxs-lookup"><span data-stu-id="f2a64-303">The \W language element is equivalent to the following character class:</span></span>  
  
```  
[^\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]  
```  
  
 <span data-ttu-id="f2a64-304">换言之，它与下表列出的 Unicode 类别中的字符以外的任何字符匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-304">In other words, it matches any character except for those in the Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="f2a64-305">类别</span><span class="sxs-lookup"><span data-stu-id="f2a64-305">Category</span></span>|<span data-ttu-id="f2a64-306">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-306">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="f2a64-307">Ll</span><span class="sxs-lookup"><span data-stu-id="f2a64-307">Ll</span></span>|<span data-ttu-id="f2a64-308">字母，小写</span><span class="sxs-lookup"><span data-stu-id="f2a64-308">Letter, Lowercase</span></span>|  
|<span data-ttu-id="f2a64-309">Lu</span><span class="sxs-lookup"><span data-stu-id="f2a64-309">Lu</span></span>|<span data-ttu-id="f2a64-310">字母，大写</span><span class="sxs-lookup"><span data-stu-id="f2a64-310">Letter, Uppercase</span></span>|  
|<span data-ttu-id="f2a64-311">Lt</span><span class="sxs-lookup"><span data-stu-id="f2a64-311">Lt</span></span>|<span data-ttu-id="f2a64-312">字母，首字母大写</span><span class="sxs-lookup"><span data-stu-id="f2a64-312">Letter, Titlecase</span></span>|  
|<span data-ttu-id="f2a64-313">Lo</span><span class="sxs-lookup"><span data-stu-id="f2a64-313">Lo</span></span>|<span data-ttu-id="f2a64-314">字母，其他</span><span class="sxs-lookup"><span data-stu-id="f2a64-314">Letter, Other</span></span>|  
|<span data-ttu-id="f2a64-315">Lm</span><span class="sxs-lookup"><span data-stu-id="f2a64-315">Lm</span></span>|<span data-ttu-id="f2a64-316">字母，修饰符</span><span class="sxs-lookup"><span data-stu-id="f2a64-316">Letter, Modifier</span></span>|  
|<span data-ttu-id="f2a64-317">Mn</span><span class="sxs-lookup"><span data-stu-id="f2a64-317">Mn</span></span>|<span data-ttu-id="f2a64-318">标记，非间距</span><span class="sxs-lookup"><span data-stu-id="f2a64-318">Mark, Nonspacing</span></span>|  
|<span data-ttu-id="f2a64-319">Nd</span><span class="sxs-lookup"><span data-stu-id="f2a64-319">Nd</span></span>|<span data-ttu-id="f2a64-320">数字，十进制数</span><span class="sxs-lookup"><span data-stu-id="f2a64-320">Number, Decimal Digit</span></span>|  
|<span data-ttu-id="f2a64-321">Pc</span><span class="sxs-lookup"><span data-stu-id="f2a64-321">Pc</span></span>|<span data-ttu-id="f2a64-322">标点，连接符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-322">Punctuation, Connector.</span></span> <span data-ttu-id="f2a64-323">此类别包含 10 个字符，最常用的字符是 LOWLINE 字符 (_)，u+005F。</span><span class="sxs-lookup"><span data-stu-id="f2a64-323">This category includes ten characters, the most commonly used of which is the LOWLINE character (_), u+005F.</span></span>|  
  
 <span data-ttu-id="f2a64-324">如果指定了符合 ECMAScript 的行为，则 `\W` 等效于 `[^a-zA-Z_0-9]`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-324">If ECMAScript-compliant behavior is specified, `\W` is equivalent to `[^a-zA-Z_0-9]`.</span></span> <span data-ttu-id="f2a64-325">有关 ECMAScript 正则表达式的信息，请参阅[正则表达式选项](../../../docs/standard/base-types/regular-expression-options.md)中的“ECMAScript 匹配行为”部分。</span><span class="sxs-lookup"><span data-stu-id="f2a64-325">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2a64-326">由于它匹配任何非单词字符，因此当正则表达式模式尝试多次匹配任何非单词字符且后跟特定非单词字符时，`\W` 语言元素通常会与惰性限定符一起使用。</span><span class="sxs-lookup"><span data-stu-id="f2a64-326">Because it matches any non-word character, the `\W` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any non-word character multiple times followed by a specific non-word character.</span></span> <span data-ttu-id="f2a64-327">有关更多信息，请参见 [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-327">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="f2a64-328">下面的示例阐释 `\W` 字符类。</span><span class="sxs-lookup"><span data-stu-id="f2a64-328">The following example illustrates the `\W` character class.</span></span>  <span data-ttu-id="f2a64-329">它定义正则表达式模式 `\b(\w+)(\W){1,2}`，该模式匹配后跟一个或两个非单词字符（例如，空白或标点符号）的单词。</span><span class="sxs-lookup"><span data-stu-id="f2a64-329">It defines a regular expression pattern, `\b(\w+)(\W){1,2}`, that matches a word followed by one or two non-word characters, such as white space or punctuation.</span></span> <span data-ttu-id="f2a64-330">正则表达式模式可以解释为下表中所示内容。</span><span class="sxs-lookup"><span data-stu-id="f2a64-330">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="f2a64-331">元素</span><span class="sxs-lookup"><span data-stu-id="f2a64-331">Element</span></span>|<span data-ttu-id="f2a64-332">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-332">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2a64-333">\b</span><span class="sxs-lookup"><span data-stu-id="f2a64-333">\b</span></span>|<span data-ttu-id="f2a64-334">在单词边界处开始匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-334">Begin the match at a word boundary.</span></span>|  
|<span data-ttu-id="f2a64-335">(\w+)</span><span class="sxs-lookup"><span data-stu-id="f2a64-335">(\w+)</span></span>|<span data-ttu-id="f2a64-336">匹配一个或多个单词字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-336">Match one or more word characters.</span></span> <span data-ttu-id="f2a64-337">这是第一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="f2a64-337">This is the first capturing group.</span></span>|  
|<span data-ttu-id="f2a64-338">(\W){1,2}</span><span class="sxs-lookup"><span data-stu-id="f2a64-338">(\W){1,2}</span></span>|<span data-ttu-id="f2a64-339">匹配非单词字符一次或两次。</span><span class="sxs-lookup"><span data-stu-id="f2a64-339">Match a non-word character either one or two times.</span></span> <span data-ttu-id="f2a64-340">这是第二个捕获组。</span><span class="sxs-lookup"><span data-stu-id="f2a64-340">This is the second capturing group.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwordchar1.cs#9)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwordchar1.vb#9)]  
  
 <span data-ttu-id="f2a64-341">由于第二个捕获组的 <xref:System.Text.RegularExpressions.Group> 对象仅包含单个捕获的非单词字符，因此该示例将从 <xref:System.Text.RegularExpressions.CaptureCollection> 属性返回的 <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> 对象中检索所有捕获的非单词字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-341">Because the <xref:System.Text.RegularExpressions.Group> object for the second capturing group contains only a single captured non-word character, the example retrieves all captured non-word characters from the <xref:System.Text.RegularExpressions.CaptureCollection> object that is returned by the <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> property.</span></span>  
  
 [<span data-ttu-id="f2a64-342">返回页首</span><span class="sxs-lookup"><span data-stu-id="f2a64-342">Back to Top</span></span>](#Top)  
  
<a name="WhitespaceCharacter"></a>   
## <a name="white-space-character-s"></a><span data-ttu-id="f2a64-343">空白字符：\s</span><span class="sxs-lookup"><span data-stu-id="f2a64-343">White-Space Character: \s</span></span>  
 <span data-ttu-id="f2a64-344">`\s` 匹配任何空白字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-344">`\s` matches any white-space character.</span></span> <span data-ttu-id="f2a64-345">它等效于下表中列出的转义序列和 Unicode 类别。</span><span class="sxs-lookup"><span data-stu-id="f2a64-345">It is equivalent to the escape sequences and Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="f2a64-346">类别</span><span class="sxs-lookup"><span data-stu-id="f2a64-346">Category</span></span>|<span data-ttu-id="f2a64-347">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-347">Description</span></span>|  
|--------------|-----------------|  
|`\f`|<span data-ttu-id="f2a64-348">窗体换页符，\u000C。</span><span class="sxs-lookup"><span data-stu-id="f2a64-348">The form feed character, \u000C.</span></span>|  
|`\n`|<span data-ttu-id="f2a64-349">换行符，\u000A。</span><span class="sxs-lookup"><span data-stu-id="f2a64-349">The newline character, \u000A.</span></span>|  
|`\r`|<span data-ttu-id="f2a64-350">回车符，\u000D。</span><span class="sxs-lookup"><span data-stu-id="f2a64-350">The carriage return character, \u000D.</span></span>|  
|`\t`|<span data-ttu-id="f2a64-351">制表符，\u0009。</span><span class="sxs-lookup"><span data-stu-id="f2a64-351">The tab character, \u0009.</span></span>|  
|`\v`|<span data-ttu-id="f2a64-352">垂直制表符，\u000B。</span><span class="sxs-lookup"><span data-stu-id="f2a64-352">The vertical tab character, \u000B.</span></span>|  
|`\x85`|<span data-ttu-id="f2a64-353">省略号或 NEXT LINE (NEL) 字符 (…)，\u0085。</span><span class="sxs-lookup"><span data-stu-id="f2a64-353">The ellipsis or NEXT LINE (NEL) character (…), \u0085.</span></span>|  
|`\p{Z}`|<span data-ttu-id="f2a64-354">匹配任何分隔符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-354">Matches any separator character.</span></span>|  
  
 <span data-ttu-id="f2a64-355">如果指定了符合 ECMAScript 的行为，则 `\s` 等效于 `[ \f\n\r\t\v]`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-355">If ECMAScript-compliant behavior is specified, `\s` is equivalent to `[ \f\n\r\t\v]`.</span></span> <span data-ttu-id="f2a64-356">有关 ECMAScript 正则表达式的信息，请参阅[正则表达式选项](../../../docs/standard/base-types/regular-expression-options.md)中的“ECMAScript 匹配行为”部分。</span><span class="sxs-lookup"><span data-stu-id="f2a64-356">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="f2a64-357">下面的示例阐释 `\s` 字符类。</span><span class="sxs-lookup"><span data-stu-id="f2a64-357">The following example illustrates the `\s` character class.</span></span> <span data-ttu-id="f2a64-358">它定义正则表达式模式 `\b\w+(e)?s(\s|$)`，该模式匹配以“s”或“es”结尾且后跟一个空白字符或输入字符串末尾的单词。</span><span class="sxs-lookup"><span data-stu-id="f2a64-358">It defines a regular expression pattern, `\b\w+(e)?s(\s|$)`, that matches a word ending in either "s" or "es" followed by either a white-space character or the end of the input string.</span></span> <span data-ttu-id="f2a64-359">正则表达式模式可以解释为下表中所示内容。</span><span class="sxs-lookup"><span data-stu-id="f2a64-359">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="f2a64-360">元素</span><span class="sxs-lookup"><span data-stu-id="f2a64-360">Element</span></span>|<span data-ttu-id="f2a64-361">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-361">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2a64-362">\b</span><span class="sxs-lookup"><span data-stu-id="f2a64-362">\b</span></span>|<span data-ttu-id="f2a64-363">在单词边界处开始匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-363">Begin the match at a word boundary.</span></span>|  
|<span data-ttu-id="f2a64-364">\w+</span><span class="sxs-lookup"><span data-stu-id="f2a64-364">\w+</span></span>|<span data-ttu-id="f2a64-365">匹配一个或多个单词字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-365">Match one or more word characters.</span></span>|  
|<span data-ttu-id="f2a64-366">(e)?</span><span class="sxs-lookup"><span data-stu-id="f2a64-366">(e)?</span></span>|<span data-ttu-id="f2a64-367">匹配“e”零次或一次。</span><span class="sxs-lookup"><span data-stu-id="f2a64-367">Match an "e" either zero or one time.</span></span>|  
|<span data-ttu-id="f2a64-368">s</span><span class="sxs-lookup"><span data-stu-id="f2a64-368">s</span></span>|<span data-ttu-id="f2a64-369">匹配“s”。</span><span class="sxs-lookup"><span data-stu-id="f2a64-369">Match an "s".</span></span>|  
|<span data-ttu-id="f2a64-370">(\s&#124;$)</span><span class="sxs-lookup"><span data-stu-id="f2a64-370">(\s&#124;$)</span></span>|<span data-ttu-id="f2a64-371">匹配空白字符或输入字符串的末尾。</span><span class="sxs-lookup"><span data-stu-id="f2a64-371">Match either a white-space character or the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/whitespace1.cs#10)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/whitespace1.vb#10)]  
  
 [<span data-ttu-id="f2a64-372">返回页首</span><span class="sxs-lookup"><span data-stu-id="f2a64-372">Back to Top</span></span>](#Top)  
  
<a name="NonWhitespaceCharacter"></a>   
## <a name="non-white-space-character-s"></a><span data-ttu-id="f2a64-373">非空白字符：\S</span><span class="sxs-lookup"><span data-stu-id="f2a64-373">Non-White-Space Character: \S</span></span>  
 <span data-ttu-id="f2a64-374">`\S` 匹配任何非空白字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-374">`\S` matches any non-white-space character.</span></span> <span data-ttu-id="f2a64-375">它等效于 `[^\f\n\r\t\v\x85\p{Z}]` 正则表达式模式或与等效于 `\s` 的正则表达式模式（与空白字符匹配）相反。</span><span class="sxs-lookup"><span data-stu-id="f2a64-375">It is equivalent to the `[^\f\n\r\t\v\x85\p{Z}]` regular expression pattern, or the opposite of the regular expression pattern that is equivalent to `\s`, which matches white-space characters.</span></span> <span data-ttu-id="f2a64-376">有关详细信息，请参阅[空白字符：\s](#WhitespaceCharacter)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-376">For more information, see [White-Space Character: \s](#WhitespaceCharacter).</span></span>  
  
 <span data-ttu-id="f2a64-377">如果指定了符合 ECMAScript 的行为，则 `\S` 等效于 `[^ \f\n\r\t\v]`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-377">If ECMAScript-compliant behavior is specified, `\S` is equivalent to  `[^ \f\n\r\t\v]`.</span></span> <span data-ttu-id="f2a64-378">有关 ECMAScript 正则表达式的信息，请参阅[正则表达式选项](../../../docs/standard/base-types/regular-expression-options.md)中的“ECMAScript 匹配行为”部分。</span><span class="sxs-lookup"><span data-stu-id="f2a64-378">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="f2a64-379">下面的示例阐释 `\S` 语言元素。</span><span class="sxs-lookup"><span data-stu-id="f2a64-379">The following example illustrates the `\S` language element.</span></span> <span data-ttu-id="f2a64-380">正则表达式模式 `\b(\S+)\s?` 匹配由空白字符分隔的字符串。</span><span class="sxs-lookup"><span data-stu-id="f2a64-380">The regular expression pattern `\b(\S+)\s?` matches strings that are delimited by white-space characters.</span></span> <span data-ttu-id="f2a64-381">匹配项的 <xref:System.Text.RegularExpressions.GroupCollection> 对象中的第二个元素包含匹配的字符串。</span><span class="sxs-lookup"><span data-stu-id="f2a64-381">The second element in the match's <xref:System.Text.RegularExpressions.GroupCollection> object contains the matched string.</span></span> <span data-ttu-id="f2a64-382">正则表达式可按下表中的方式解释。</span><span class="sxs-lookup"><span data-stu-id="f2a64-382">The regular expression can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="f2a64-383">元素</span><span class="sxs-lookup"><span data-stu-id="f2a64-383">Element</span></span>|<span data-ttu-id="f2a64-384">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-384">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="f2a64-385">在单词边界处开始匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-385">Begin the match at a word boundary.</span></span>|  
|`(\S+)`|<span data-ttu-id="f2a64-386">匹配一个或多个非空白字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-386">Match one or more non-white-space characters.</span></span> <span data-ttu-id="f2a64-387">这是第一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="f2a64-387">This is the first capturing group.</span></span>|  
|`\s?`|<span data-ttu-id="f2a64-388">匹配零个或一个空白字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-388">Match zero or one white-space character.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwhitespace1.cs#11)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwhitespace1.vb#11)]  
  
 [<span data-ttu-id="f2a64-389">返回页首</span><span class="sxs-lookup"><span data-stu-id="f2a64-389">Back to Top</span></span>](#Top)  
  
<a name="DigitCharacter"></a>   
## <a name="decimal-digit-character-d"></a><span data-ttu-id="f2a64-390">十进制数字字符：\d</span><span class="sxs-lookup"><span data-stu-id="f2a64-390">Decimal Digit Character: \d</span></span>  
 <span data-ttu-id="f2a64-391">`\d` 匹配任何十进制数字。</span><span class="sxs-lookup"><span data-stu-id="f2a64-391">`\d` matches any decimal digit.</span></span> <span data-ttu-id="f2a64-392">它等效于 `\p{Nd}` 正则表达式模式，该模式包含标准的十进制数字 0-9 以及众多其他字符集的十进制数字。</span><span class="sxs-lookup"><span data-stu-id="f2a64-392">It is equivalent to the `\p{Nd}` regular expression pattern, which includes the standard decimal digits 0-9 as well as the decimal digits of a number of other character sets.</span></span>  
  
 <span data-ttu-id="f2a64-393">如果指定了符合 ECMAScript 的行为，则 `\d` 等效于 `[0-9]`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-393">If ECMAScript-compliant behavior is specified, `\d` is equivalent to  `[0-9]`.</span></span> <span data-ttu-id="f2a64-394">有关 ECMAScript 正则表达式的信息，请参阅[正则表达式选项](../../../docs/standard/base-types/regular-expression-options.md)中的“ECMAScript 匹配行为”部分。</span><span class="sxs-lookup"><span data-stu-id="f2a64-394">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="f2a64-395">下面的示例阐释 `\d` 语言元素。</span><span class="sxs-lookup"><span data-stu-id="f2a64-395">The following example illustrates the `\d` language element.</span></span> <span data-ttu-id="f2a64-396">它测试输入字符串是否表示美国和加拿大的有效电话号码。</span><span class="sxs-lookup"><span data-stu-id="f2a64-396">It tests whether an input string represents a valid telephone number in the United States and Canada.</span></span> <span data-ttu-id="f2a64-397">正则表达式模式 `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` 的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="f2a64-397">The regular expression pattern `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="f2a64-398">元素</span><span class="sxs-lookup"><span data-stu-id="f2a64-398">Element</span></span>|<span data-ttu-id="f2a64-399">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-399">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="f2a64-400">从输入字符串的开头部分开始匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-400">Begin the match at the beginning of the input string.</span></span>|  
|`\(?`|<span data-ttu-id="f2a64-401">匹配零个或一个“(”文本字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-401">Match zero or one literal "(" character.</span></span>|  
|`\d{3}`|<span data-ttu-id="f2a64-402">匹配三个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="f2a64-402">Match three decimal digits.</span></span>|  
|`\)?`|<span data-ttu-id="f2a64-403">匹配零个或一个“)”文本字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-403">Match zero or one literal ")" character.</span></span>|  
|`[\s-]`|<span data-ttu-id="f2a64-404">匹配连字符或空白字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-404">Match a hyphen or a white-space character.</span></span>|  
|`(\(?\d{3}\)?[\s-])?`|<span data-ttu-id="f2a64-405">匹配后跟三个十进制数字的可选左括号、可选右括号和空白字符或连字符零次或一次。</span><span class="sxs-lookup"><span data-stu-id="f2a64-405">Match an optional opening parenthesis followed by three decimal digits, an optional closing parenthesis, and either a white-space character or a hyphen zero or one time.</span></span> <span data-ttu-id="f2a64-406">这是第一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="f2a64-406">This is the first capturing group.</span></span>|  
|`\d{3}-\d{4}`|<span data-ttu-id="f2a64-407">匹配后跟连字符和四个以上的十进制数字的三个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="f2a64-407">Match three decimal digits followed by a hyphen and four more decimal digits.</span></span>|  
|`$`|<span data-ttu-id="f2a64-408">匹配输入字符串的末尾部分。</span><span class="sxs-lookup"><span data-stu-id="f2a64-408">Match the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/digit1.cs#12)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/digit1.vb#12)]  
  
 [<span data-ttu-id="f2a64-409">返回页首</span><span class="sxs-lookup"><span data-stu-id="f2a64-409">Back to Top</span></span>](#Top)  
  
<a name="NonDigitCharacter"></a>   
## <a name="non-digit-character-d"></a><span data-ttu-id="f2a64-410">非数字字符：\D</span><span class="sxs-lookup"><span data-stu-id="f2a64-410">Non-Digit Character: \D</span></span>  
 <span data-ttu-id="f2a64-411">`\D` 匹配任何非数字字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-411">`\D` matches any non-digit character.</span></span> <span data-ttu-id="f2a64-412">它等效于 `\P{Nd}` 正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="f2a64-412">It is equivalent to the `\P{Nd}` regular expression pattern.</span></span>  
  
 <span data-ttu-id="f2a64-413">如果指定了符合 ECMAScript 的行为，则 `\D` 等效于 `[^0-9]`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-413">If ECMAScript-compliant behavior is specified, `\D` is equivalent to  `[^0-9]`.</span></span> <span data-ttu-id="f2a64-414">有关 ECMAScript 正则表达式的信息，请参阅[正则表达式选项](../../../docs/standard/base-types/regular-expression-options.md)中的“ECMAScript 匹配行为”部分。</span><span class="sxs-lookup"><span data-stu-id="f2a64-414">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="f2a64-415">下面的示例阐释了 \D 语言元素。</span><span class="sxs-lookup"><span data-stu-id="f2a64-415">The following example illustrates the \D language element.</span></span> <span data-ttu-id="f2a64-416">它测试部件号等字符串是否包含适当的十进制和非十进制数字字符的组合。</span><span class="sxs-lookup"><span data-stu-id="f2a64-416">It tests whether a string such as a part number consists of the appropriate combination of decimal and non-decimal characters.</span></span> <span data-ttu-id="f2a64-417">正则表达式模式 `^\D\d{1,5}\D*$` 的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="f2a64-417">The regular expression pattern `^\D\d{1,5}\D*$` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="f2a64-418">元素</span><span class="sxs-lookup"><span data-stu-id="f2a64-418">Element</span></span>|<span data-ttu-id="f2a64-419">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-419">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="f2a64-420">从输入字符串的开头部分开始匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-420">Begin the match at the beginning of the input string.</span></span>|  
|`\D`|<span data-ttu-id="f2a64-421">匹配非数字字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-421">Match a non-digit character.</span></span>|  
|`\d{1,5}`|<span data-ttu-id="f2a64-422">匹配一到五个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="f2a64-422">Match from one to five decimal digits.</span></span>|  
|`\D*`|<span data-ttu-id="f2a64-423">匹配零个、一个或多个非十进制字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-423">Match zero, one, or more non-decimal characters.</span></span>|  
|`$`|<span data-ttu-id="f2a64-424">匹配输入字符串的末尾部分。</span><span class="sxs-lookup"><span data-stu-id="f2a64-424">Match the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nondigit1.cs#13)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nondigit1.vb#13)]  
  
 [<span data-ttu-id="f2a64-425">返回页首</span><span class="sxs-lookup"><span data-stu-id="f2a64-425">Back to Top</span></span>](#Top)  
  
<a name="SupportedUnicodeGeneralCategories"></a>   
## <a name="supported-unicode-general-categories"></a><span data-ttu-id="f2a64-426">支持的 Unicode 常规类别</span><span class="sxs-lookup"><span data-stu-id="f2a64-426">Supported Unicode General Categories</span></span>  
 <span data-ttu-id="f2a64-427">Unicode 定义下表列出的常规类别。</span><span class="sxs-lookup"><span data-stu-id="f2a64-427">Unicode defines the general categories listed in the following table.</span></span> <span data-ttu-id="f2a64-428">有关详细信息，请参阅 [Unicode 字符数据库](https://www.unicode.org/reports/tr44/)中的“UCD 文件格式”和“常规类别值”子主题。</span><span class="sxs-lookup"><span data-stu-id="f2a64-428">For more information, see the "UCD File Format" and "General Category Values" subtopics at the [Unicode Character Database](https://www.unicode.org/reports/tr44/).</span></span>  
  
|<span data-ttu-id="f2a64-429">类别</span><span class="sxs-lookup"><span data-stu-id="f2a64-429">Category</span></span>|<span data-ttu-id="f2a64-430">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-430">Description</span></span>|  
|--------------|-----------------|  
|`Lu`|<span data-ttu-id="f2a64-431">字母，大写</span><span class="sxs-lookup"><span data-stu-id="f2a64-431">Letter, Uppercase</span></span>|  
|`Ll`|<span data-ttu-id="f2a64-432">字母，小写</span><span class="sxs-lookup"><span data-stu-id="f2a64-432">Letter, Lowercase</span></span>|  
|`Lt`|<span data-ttu-id="f2a64-433">字母，首字母大写</span><span class="sxs-lookup"><span data-stu-id="f2a64-433">Letter, Titlecase</span></span>|  
|`Lm`|<span data-ttu-id="f2a64-434">字母，修饰符</span><span class="sxs-lookup"><span data-stu-id="f2a64-434">Letter, Modifier</span></span>|  
|`Lo`|<span data-ttu-id="f2a64-435">字母，其他</span><span class="sxs-lookup"><span data-stu-id="f2a64-435">Letter, Other</span></span>|  
|`L`|<span data-ttu-id="f2a64-436">所有字母字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-436">All letter characters.</span></span> <span data-ttu-id="f2a64-437">这包括 `Lu`、`Ll`、`Lt`、`Lm` 和 `Lo` 字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-437">This includes the `Lu`, `Ll`, `Lt`, `Lm`, and `Lo` characters.</span></span>|  
|`Mn`|<span data-ttu-id="f2a64-438">标记，非间距</span><span class="sxs-lookup"><span data-stu-id="f2a64-438">Mark, Nonspacing</span></span>|  
|`Mc`|<span data-ttu-id="f2a64-439">标记，间距组合</span><span class="sxs-lookup"><span data-stu-id="f2a64-439">Mark, Spacing Combining</span></span>|  
|`Me`|<span data-ttu-id="f2a64-440">标记，封闭</span><span class="sxs-lookup"><span data-stu-id="f2a64-440">Mark, Enclosing</span></span>|  
|`M`|<span data-ttu-id="f2a64-441">所有音调符号标记。</span><span class="sxs-lookup"><span data-stu-id="f2a64-441">All diacritic marks.</span></span> <span data-ttu-id="f2a64-442">这包括 `Mn`、`Mc` 和 `Me` 类别。</span><span class="sxs-lookup"><span data-stu-id="f2a64-442">This includes the `Mn`, `Mc`, and `Me` categories.</span></span>|  
|`Nd`|<span data-ttu-id="f2a64-443">数字，十进制数</span><span class="sxs-lookup"><span data-stu-id="f2a64-443">Number, Decimal Digit</span></span>|  
|`Nl`|<span data-ttu-id="f2a64-444">数字，字母</span><span class="sxs-lookup"><span data-stu-id="f2a64-444">Number, Letter</span></span>|  
|`No`|<span data-ttu-id="f2a64-445">数字，其他</span><span class="sxs-lookup"><span data-stu-id="f2a64-445">Number, Other</span></span>|  
|`N`|<span data-ttu-id="f2a64-446">所有数字。</span><span class="sxs-lookup"><span data-stu-id="f2a64-446">All numbers.</span></span> <span data-ttu-id="f2a64-447">这包括 `Nd`、`Nl` 和 `No` 类别。</span><span class="sxs-lookup"><span data-stu-id="f2a64-447">This includes the `Nd`, `Nl`, and `No` categories.</span></span>|  
|`Pc`|<span data-ttu-id="f2a64-448">标点，连接符</span><span class="sxs-lookup"><span data-stu-id="f2a64-448">Punctuation, Connector</span></span>|  
|`Pd`|<span data-ttu-id="f2a64-449">标点，短划线</span><span class="sxs-lookup"><span data-stu-id="f2a64-449">Punctuation, Dash</span></span>|  
|`Ps`|<span data-ttu-id="f2a64-450">标点，开始</span><span class="sxs-lookup"><span data-stu-id="f2a64-450">Punctuation, Open</span></span>|  
|`Pe`|<span data-ttu-id="f2a64-451">标点，结束</span><span class="sxs-lookup"><span data-stu-id="f2a64-451">Punctuation, Close</span></span>|  
|`Pi`|<span data-ttu-id="f2a64-452">标点，前引号（根据具体使用情况，作用可能像 Ps 或 Pe）</span><span class="sxs-lookup"><span data-stu-id="f2a64-452">Punctuation, Initial quote (may behave like Ps or Pe depending on usage)</span></span>|  
|`Pf`|<span data-ttu-id="f2a64-453">标点，后引号（根据具体使用情况，作用可能像 Ps 或 Pe）</span><span class="sxs-lookup"><span data-stu-id="f2a64-453">Punctuation, Final quote (may behave like Ps or Pe depending on usage)</span></span>|  
|`Po`|<span data-ttu-id="f2a64-454">标点，其他</span><span class="sxs-lookup"><span data-stu-id="f2a64-454">Punctuation, Other</span></span>|  
|`P`|<span data-ttu-id="f2a64-455">所有标点字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-455">All punctuation characters.</span></span> <span data-ttu-id="f2a64-456">这包括 `Pc`、`Pd`、`Ps`, `Pe`、`Pi`、`Pf` 和 `Po` 类别。</span><span class="sxs-lookup"><span data-stu-id="f2a64-456">This includes the `Pc`, `Pd`, `Ps`, `Pe`, `Pi`, `Pf`, and `Po` categories.</span></span>|  
|`Sm`|<span data-ttu-id="f2a64-457">符号，数学</span><span class="sxs-lookup"><span data-stu-id="f2a64-457">Symbol, Math</span></span>|  
|`Sc`|<span data-ttu-id="f2a64-458">符号，货币</span><span class="sxs-lookup"><span data-stu-id="f2a64-458">Symbol, Currency</span></span>|  
|`Sk`|<span data-ttu-id="f2a64-459">符号，修饰符</span><span class="sxs-lookup"><span data-stu-id="f2a64-459">Symbol, Modifier</span></span>|  
|`So`|<span data-ttu-id="f2a64-460">符号，其他</span><span class="sxs-lookup"><span data-stu-id="f2a64-460">Symbol, Other</span></span>|  
|`S`|<span data-ttu-id="f2a64-461">所有符号。</span><span class="sxs-lookup"><span data-stu-id="f2a64-461">All symbols.</span></span> <span data-ttu-id="f2a64-462">这包括 `Sm`、`Sc`、`Sk` 和 `So` 类别。</span><span class="sxs-lookup"><span data-stu-id="f2a64-462">This includes the `Sm`, `Sc`, `Sk`, and `So` categories.</span></span>|  
|`Zs`|<span data-ttu-id="f2a64-463">分隔符，空白</span><span class="sxs-lookup"><span data-stu-id="f2a64-463">Separator, Space</span></span>|  
|`Zl`|<span data-ttu-id="f2a64-464">分隔符，行</span><span class="sxs-lookup"><span data-stu-id="f2a64-464">Separator, Line</span></span>|  
|`Zp`|<span data-ttu-id="f2a64-465">分隔符，段落</span><span class="sxs-lookup"><span data-stu-id="f2a64-465">Separator, Paragraph</span></span>|  
|`Z`|<span data-ttu-id="f2a64-466">所有分隔符字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-466">All separator characters.</span></span> <span data-ttu-id="f2a64-467">这包括 `Zs`、`Zl` 和 `Zp` 类别。</span><span class="sxs-lookup"><span data-stu-id="f2a64-467">This includes the `Zs`, `Zl`, and `Zp` categories.</span></span>|  
|`Cc`|<span data-ttu-id="f2a64-468">其他，控制</span><span class="sxs-lookup"><span data-stu-id="f2a64-468">Other, Control</span></span>|  
|`Cf`|<span data-ttu-id="f2a64-469">其他，格式</span><span class="sxs-lookup"><span data-stu-id="f2a64-469">Other, Format</span></span>|  
|`Cs`|<span data-ttu-id="f2a64-470">其他，代理项</span><span class="sxs-lookup"><span data-stu-id="f2a64-470">Other, Surrogate</span></span>|  
|`Co`|<span data-ttu-id="f2a64-471">其他，私用</span><span class="sxs-lookup"><span data-stu-id="f2a64-471">Other, Private Use</span></span>|  
|`Cn`|<span data-ttu-id="f2a64-472">其他，未赋值（任何字符都不具有此属性）</span><span class="sxs-lookup"><span data-stu-id="f2a64-472">Other, Not Assigned (no characters have this property)</span></span>|  
|`C`|<span data-ttu-id="f2a64-473">所有控制字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-473">All control characters.</span></span> <span data-ttu-id="f2a64-474">这包括 `Cc`、`Cf`、`Cs`、`Co` 和 `Cn` 类别。</span><span class="sxs-lookup"><span data-stu-id="f2a64-474">This includes the `Cc`, `Cf`, `Cs`, `Co`, and `Cn` categories.</span></span>|  
  
 <span data-ttu-id="f2a64-475">可以通过将任何特定字符传递到 <xref:System.Char.GetUnicodeCategory%2A> 方法来确定该字符的 Unicode 类别。</span><span class="sxs-lookup"><span data-stu-id="f2a64-475">You can determine the Unicode category of any particular character by passing that character to the <xref:System.Char.GetUnicodeCategory%2A> method.</span></span> <span data-ttu-id="f2a64-476">下面的示例使用 <xref:System.Char.GetUnicodeCategory%2A> 方法来确定包含所选拉丁字符的数组中的每个元素的类别。</span><span class="sxs-lookup"><span data-stu-id="f2a64-476">The following example uses the <xref:System.Char.GetUnicodeCategory%2A> method to determine the category of each element in an array that contains selected Latin characters.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/getunicodecategory1.cs#14)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/getunicodecategory1.vb#14)]  
  
 [<span data-ttu-id="f2a64-477">返回页首</span><span class="sxs-lookup"><span data-stu-id="f2a64-477">Back to Top</span></span>](#Top)  
  
<a name="SupportedNamedBlocks"></a>   
## <a name="supported-named-blocks"></a><span data-ttu-id="f2a64-478">支持的命名块</span><span class="sxs-lookup"><span data-stu-id="f2a64-478">Supported Named Blocks</span></span>  
 <span data-ttu-id="f2a64-479">.NET 提供下表中所列的命名块。</span><span class="sxs-lookup"><span data-stu-id="f2a64-479">.NET provides the named blocks listed in the following table.</span></span> <span data-ttu-id="f2a64-480">该组支持的命名块基于 Unicode 4.0 和 Perl 5.6。</span><span class="sxs-lookup"><span data-stu-id="f2a64-480">The set of supported named blocks is based on Unicode 4.0 and Perl 5.6.</span></span>  
  
|<span data-ttu-id="f2a64-481">码位范围</span><span class="sxs-lookup"><span data-stu-id="f2a64-481">Code point range</span></span>|<span data-ttu-id="f2a64-482">块名称</span><span class="sxs-lookup"><span data-stu-id="f2a64-482">Block name</span></span>|  
|----------------------|----------------|  
|<span data-ttu-id="f2a64-483">0000 - 007F</span><span class="sxs-lookup"><span data-stu-id="f2a64-483">0000 - 007F</span></span>|`IsBasicLatin`|  
|<span data-ttu-id="f2a64-484">0080 - 00FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-484">0080 - 00FF</span></span>|`IsLatin-1Supplement`|  
|<span data-ttu-id="f2a64-485">0100 - 017F</span><span class="sxs-lookup"><span data-stu-id="f2a64-485">0100 - 017F</span></span>|`IsLatinExtended-A`|  
|<span data-ttu-id="f2a64-486">0180 - 024F</span><span class="sxs-lookup"><span data-stu-id="f2a64-486">0180 - 024F</span></span>|`IsLatinExtended-B`|  
|<span data-ttu-id="f2a64-487">0250 - 02AF</span><span class="sxs-lookup"><span data-stu-id="f2a64-487">0250 - 02AF</span></span>|`IsIPAExtensions`|  
|<span data-ttu-id="f2a64-488">02B0 - 02FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-488">02B0 - 02FF</span></span>|`IsSpacingModifierLetters`|  
|<span data-ttu-id="f2a64-489">0300 - 036F</span><span class="sxs-lookup"><span data-stu-id="f2a64-489">0300 - 036F</span></span>|`IsCombiningDiacriticalMarks`|  
|<span data-ttu-id="f2a64-490">0370 - 03FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-490">0370 - 03FF</span></span>|`IsGreek`<br /><br /> <span data-ttu-id="f2a64-491">- 或 -</span><span class="sxs-lookup"><span data-stu-id="f2a64-491">-or-</span></span><br /><br /> `IsGreekandCoptic`|  
|<span data-ttu-id="f2a64-492">0400 - 04FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-492">0400 - 04FF</span></span>|`IsCyrillic`|  
|<span data-ttu-id="f2a64-493">0500 - 052F</span><span class="sxs-lookup"><span data-stu-id="f2a64-493">0500 - 052F</span></span>|`IsCyrillicSupplement`|  
|<span data-ttu-id="f2a64-494">0530 - 058F</span><span class="sxs-lookup"><span data-stu-id="f2a64-494">0530 - 058F</span></span>|`IsArmenian`|  
|<span data-ttu-id="f2a64-495">0590 - 05FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-495">0590 - 05FF</span></span>|`IsHebrew`|  
|<span data-ttu-id="f2a64-496">0600 - 06FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-496">0600 - 06FF</span></span>|`IsArabic`|  
|<span data-ttu-id="f2a64-497">0700 - 074F</span><span class="sxs-lookup"><span data-stu-id="f2a64-497">0700 - 074F</span></span>|`IsSyriac`|  
|<span data-ttu-id="f2a64-498">0780 - 07BF</span><span class="sxs-lookup"><span data-stu-id="f2a64-498">0780 - 07BF</span></span>|`IsThaana`|  
|<span data-ttu-id="f2a64-499">0900 - 097F</span><span class="sxs-lookup"><span data-stu-id="f2a64-499">0900 - 097F</span></span>|`IsDevanagari`|  
|<span data-ttu-id="f2a64-500">0980 - 09FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-500">0980 - 09FF</span></span>|`IsBengali`|  
|<span data-ttu-id="f2a64-501">0A00 - 0A7F</span><span class="sxs-lookup"><span data-stu-id="f2a64-501">0A00 - 0A7F</span></span>|`IsGurmukhi`|  
|<span data-ttu-id="f2a64-502">0A80 - 0AFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-502">0A80 - 0AFF</span></span>|`IsGujarati`|  
|<span data-ttu-id="f2a64-503">0B00 - 0B7F</span><span class="sxs-lookup"><span data-stu-id="f2a64-503">0B00 - 0B7F</span></span>|`IsOriya`|  
|<span data-ttu-id="f2a64-504">0B80 - 0BFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-504">0B80 - 0BFF</span></span>|`IsTamil`|  
|<span data-ttu-id="f2a64-505">0C00 - 0C7F</span><span class="sxs-lookup"><span data-stu-id="f2a64-505">0C00 - 0C7F</span></span>|`IsTelugu`|  
|<span data-ttu-id="f2a64-506">0C80 - 0CFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-506">0C80 - 0CFF</span></span>|`IsKannada`|  
|<span data-ttu-id="f2a64-507">0D00 - 0D7F</span><span class="sxs-lookup"><span data-stu-id="f2a64-507">0D00 - 0D7F</span></span>|`IsMalayalam`|  
|<span data-ttu-id="f2a64-508">0D80 - 0DFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-508">0D80 - 0DFF</span></span>|`IsSinhala`|  
|<span data-ttu-id="f2a64-509">0E00 - 0E7F</span><span class="sxs-lookup"><span data-stu-id="f2a64-509">0E00 - 0E7F</span></span>|`IsThai`|  
|<span data-ttu-id="f2a64-510">0E80 - 0EFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-510">0E80 - 0EFF</span></span>|`IsLao`|  
|<span data-ttu-id="f2a64-511">0F00 - 0FFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-511">0F00 - 0FFF</span></span>|`IsTibetan`|  
|<span data-ttu-id="f2a64-512">1000 - 109F</span><span class="sxs-lookup"><span data-stu-id="f2a64-512">1000 - 109F</span></span>|`IsMyanmar`|  
|<span data-ttu-id="f2a64-513">10A0 - 10FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-513">10A0 - 10FF</span></span>|`IsGeorgian`|  
|<span data-ttu-id="f2a64-514">1100 - 11FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-514">1100 - 11FF</span></span>|`IsHangulJamo`|  
|<span data-ttu-id="f2a64-515">1200 - 137F</span><span class="sxs-lookup"><span data-stu-id="f2a64-515">1200 - 137F</span></span>|`IsEthiopic`|  
|<span data-ttu-id="f2a64-516">13A0 - 13FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-516">13A0 - 13FF</span></span>|`IsCherokee`|  
|<span data-ttu-id="f2a64-517">1400 - 167F</span><span class="sxs-lookup"><span data-stu-id="f2a64-517">1400 - 167F</span></span>|`IsUnifiedCanadianAboriginalSyllabics`|  
|<span data-ttu-id="f2a64-518">1680 - 169F</span><span class="sxs-lookup"><span data-stu-id="f2a64-518">1680 - 169F</span></span>|`IsOgham`|  
|<span data-ttu-id="f2a64-519">16A0 - 16FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-519">16A0 - 16FF</span></span>|`IsRunic`|  
|<span data-ttu-id="f2a64-520">1700 - 171F</span><span class="sxs-lookup"><span data-stu-id="f2a64-520">1700 - 171F</span></span>|`IsTagalog`|  
|<span data-ttu-id="f2a64-521">1720 - 173F</span><span class="sxs-lookup"><span data-stu-id="f2a64-521">1720 - 173F</span></span>|`IsHanunoo`|  
|<span data-ttu-id="f2a64-522">1740 - 175F</span><span class="sxs-lookup"><span data-stu-id="f2a64-522">1740 - 175F</span></span>|`IsBuhid`|  
|<span data-ttu-id="f2a64-523">1760 - 177F</span><span class="sxs-lookup"><span data-stu-id="f2a64-523">1760 - 177F</span></span>|`IsTagbanwa`|  
|<span data-ttu-id="f2a64-524">1780 - 17FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-524">1780 - 17FF</span></span>|`IsKhmer`|  
|<span data-ttu-id="f2a64-525">1800 - 18AF</span><span class="sxs-lookup"><span data-stu-id="f2a64-525">1800 - 18AF</span></span>|`IsMongolian`|  
|<span data-ttu-id="f2a64-526">1900 - 194F</span><span class="sxs-lookup"><span data-stu-id="f2a64-526">1900 - 194F</span></span>|`IsLimbu`|  
|<span data-ttu-id="f2a64-527">1950 - 197F</span><span class="sxs-lookup"><span data-stu-id="f2a64-527">1950 - 197F</span></span>|`IsTaiLe`|  
|<span data-ttu-id="f2a64-528">19E0 - 19FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-528">19E0 - 19FF</span></span>|`IsKhmerSymbols`|  
|<span data-ttu-id="f2a64-529">1D00 - 1D7F</span><span class="sxs-lookup"><span data-stu-id="f2a64-529">1D00 - 1D7F</span></span>|`IsPhoneticExtensions`|  
|<span data-ttu-id="f2a64-530">1E00 - 1EFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-530">1E00 - 1EFF</span></span>|`IsLatinExtendedAdditional`|  
|<span data-ttu-id="f2a64-531">1F00 - 1FFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-531">1F00 - 1FFF</span></span>|`IsGreekExtended`|  
|<span data-ttu-id="f2a64-532">2000 - 206F</span><span class="sxs-lookup"><span data-stu-id="f2a64-532">2000 - 206F</span></span>|`IsGeneralPunctuation`|  
|<span data-ttu-id="f2a64-533">2070 - 209F</span><span class="sxs-lookup"><span data-stu-id="f2a64-533">2070 - 209F</span></span>|`IsSuperscriptsandSubscripts`|  
|<span data-ttu-id="f2a64-534">20A0 - 20CF</span><span class="sxs-lookup"><span data-stu-id="f2a64-534">20A0 - 20CF</span></span>|`IsCurrencySymbols`|  
|<span data-ttu-id="f2a64-535">20D0 - 20FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-535">20D0 - 20FF</span></span>|`IsCombiningDiacriticalMarksforSymbols`<br /><br /> <span data-ttu-id="f2a64-536">或</span><span class="sxs-lookup"><span data-stu-id="f2a64-536">-or-</span></span><br /><br /> `IsCombiningMarksforSymbols`|  
|<span data-ttu-id="f2a64-537">2100 - 214F</span><span class="sxs-lookup"><span data-stu-id="f2a64-537">2100 - 214F</span></span>|`IsLetterlikeSymbols`|  
|<span data-ttu-id="f2a64-538">2150 - 218F</span><span class="sxs-lookup"><span data-stu-id="f2a64-538">2150 - 218F</span></span>|`IsNumberForms`|  
|<span data-ttu-id="f2a64-539">2190 - 21FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-539">2190 - 21FF</span></span>|`IsArrows`|  
|<span data-ttu-id="f2a64-540">2200 - 22FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-540">2200 - 22FF</span></span>|`IsMathematicalOperators`|  
|<span data-ttu-id="f2a64-541">2300 - 23FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-541">2300 - 23FF</span></span>|`IsMiscellaneousTechnical`|  
|<span data-ttu-id="f2a64-542">2400 - 243F</span><span class="sxs-lookup"><span data-stu-id="f2a64-542">2400 - 243F</span></span>|`IsControlPictures`|  
|<span data-ttu-id="f2a64-543">2440 - 245F</span><span class="sxs-lookup"><span data-stu-id="f2a64-543">2440 - 245F</span></span>|`IsOpticalCharacterRecognition`|  
|<span data-ttu-id="f2a64-544">2460 - 24FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-544">2460 - 24FF</span></span>|`IsEnclosedAlphanumerics`|  
|<span data-ttu-id="f2a64-545">2500 - 257F</span><span class="sxs-lookup"><span data-stu-id="f2a64-545">2500 - 257F</span></span>|`IsBoxDrawing`|  
|<span data-ttu-id="f2a64-546">2580 - 259F</span><span class="sxs-lookup"><span data-stu-id="f2a64-546">2580 - 259F</span></span>|`IsBlockElements`|  
|<span data-ttu-id="f2a64-547">25A0 - 25FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-547">25A0 - 25FF</span></span>|`IsGeometricShapes`|  
|<span data-ttu-id="f2a64-548">2600 - 26FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-548">2600 - 26FF</span></span>|`IsMiscellaneousSymbols`|  
|<span data-ttu-id="f2a64-549">2700 - 27BF</span><span class="sxs-lookup"><span data-stu-id="f2a64-549">2700 - 27BF</span></span>|`IsDingbats`|  
|<span data-ttu-id="f2a64-550">27C0 - 27EF</span><span class="sxs-lookup"><span data-stu-id="f2a64-550">27C0 - 27EF</span></span>|`IsMiscellaneousMathematicalSymbols-A`|  
|<span data-ttu-id="f2a64-551">27F0 - 27FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-551">27F0 - 27FF</span></span>|`IsSupplementalArrows-A`|  
|<span data-ttu-id="f2a64-552">2800 - 28FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-552">2800 - 28FF</span></span>|`IsBraillePatterns`|  
|<span data-ttu-id="f2a64-553">2900 - 297F</span><span class="sxs-lookup"><span data-stu-id="f2a64-553">2900 - 297F</span></span>|`IsSupplementalArrows-B`|  
|<span data-ttu-id="f2a64-554">2980 - 29FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-554">2980 - 29FF</span></span>|`IsMiscellaneousMathematicalSymbols-B`|  
|<span data-ttu-id="f2a64-555">2A00 - 2AFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-555">2A00 - 2AFF</span></span>|`IsSupplementalMathematicalOperators`|  
|<span data-ttu-id="f2a64-556">2B00 - 2BFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-556">2B00 - 2BFF</span></span>|`IsMiscellaneousSymbolsandArrows`|  
|<span data-ttu-id="f2a64-557">2E80 - 2EFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-557">2E80 - 2EFF</span></span>|`IsCJKRadicalsSupplement`|  
|<span data-ttu-id="f2a64-558">2F00 - 2FDF</span><span class="sxs-lookup"><span data-stu-id="f2a64-558">2F00 - 2FDF</span></span>|`IsKangxiRadicals`|  
|<span data-ttu-id="f2a64-559">2FF0 - 2FFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-559">2FF0 - 2FFF</span></span>|`IsIdeographicDescriptionCharacters`|  
|<span data-ttu-id="f2a64-560">3000 - 303F</span><span class="sxs-lookup"><span data-stu-id="f2a64-560">3000 - 303F</span></span>|`IsCJKSymbolsandPunctuation`|  
|<span data-ttu-id="f2a64-561">3040 - 309F</span><span class="sxs-lookup"><span data-stu-id="f2a64-561">3040 - 309F</span></span>|`IsHiragana`|  
|<span data-ttu-id="f2a64-562">30A0 - 30FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-562">30A0 - 30FF</span></span>|`IsKatakana`|  
|<span data-ttu-id="f2a64-563">3100 - 312F</span><span class="sxs-lookup"><span data-stu-id="f2a64-563">3100 - 312F</span></span>|`IsBopomofo`|  
|<span data-ttu-id="f2a64-564">3130 - 318F</span><span class="sxs-lookup"><span data-stu-id="f2a64-564">3130 - 318F</span></span>|`IsHangulCompatibilityJamo`|  
|<span data-ttu-id="f2a64-565">3190 - 319F</span><span class="sxs-lookup"><span data-stu-id="f2a64-565">3190 - 319F</span></span>|`IsKanbun`|  
|<span data-ttu-id="f2a64-566">31A0 - 31BF</span><span class="sxs-lookup"><span data-stu-id="f2a64-566">31A0 - 31BF</span></span>|`IsBopomofoExtended`|  
|<span data-ttu-id="f2a64-567">31F0 - 31FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-567">31F0 - 31FF</span></span>|`IsKatakanaPhoneticExtensions`|  
|<span data-ttu-id="f2a64-568">3200 - 32FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-568">3200 - 32FF</span></span>|`IsEnclosedCJKLettersandMonths`|  
|<span data-ttu-id="f2a64-569">3300 - 33FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-569">3300 - 33FF</span></span>|`IsCJKCompatibility`|  
|<span data-ttu-id="f2a64-570">3400 - 4DBF</span><span class="sxs-lookup"><span data-stu-id="f2a64-570">3400 - 4DBF</span></span>|`IsCJKUnifiedIdeographsExtensionA`|  
|<span data-ttu-id="f2a64-571">4DC0 - 4DFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-571">4DC0 - 4DFF</span></span>|`IsYijingHexagramSymbols`|  
|<span data-ttu-id="f2a64-572">4E00 - 9FFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-572">4E00 - 9FFF</span></span>|`IsCJKUnifiedIdeographs`|  
|<span data-ttu-id="f2a64-573">A000 - A48F</span><span class="sxs-lookup"><span data-stu-id="f2a64-573">A000 - A48F</span></span>|`IsYiSyllables`|  
|<span data-ttu-id="f2a64-574">A490 - A4CF</span><span class="sxs-lookup"><span data-stu-id="f2a64-574">A490 - A4CF</span></span>|`IsYiRadicals`|  
|<span data-ttu-id="f2a64-575">AC00 - D7AF</span><span class="sxs-lookup"><span data-stu-id="f2a64-575">AC00 - D7AF</span></span>|`IsHangulSyllables`|  
|<span data-ttu-id="f2a64-576">D800 - DB7F</span><span class="sxs-lookup"><span data-stu-id="f2a64-576">D800 - DB7F</span></span>|`IsHighSurrogates`|  
|<span data-ttu-id="f2a64-577">DB80 - DBFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-577">DB80 - DBFF</span></span>|`IsHighPrivateUseSurrogates`|  
|<span data-ttu-id="f2a64-578">DC00 - DFFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-578">DC00 - DFFF</span></span>|`IsLowSurrogates`|  
|<span data-ttu-id="f2a64-579">E000 - F8FF</span><span class="sxs-lookup"><span data-stu-id="f2a64-579">E000 - F8FF</span></span>|<span data-ttu-id="f2a64-580">`IsPrivateUse` 或 `IsPrivateUseArea`</span><span class="sxs-lookup"><span data-stu-id="f2a64-580">`IsPrivateUse` or `IsPrivateUseArea`</span></span>|  
|<span data-ttu-id="f2a64-581">F900 - FAFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-581">F900 - FAFF</span></span>|`IsCJKCompatibilityIdeographs`|  
|<span data-ttu-id="f2a64-582">FB00 - FB4F</span><span class="sxs-lookup"><span data-stu-id="f2a64-582">FB00 - FB4F</span></span>|`IsAlphabeticPresentationForms`|  
|<span data-ttu-id="f2a64-583">FB50 - FDFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-583">FB50 - FDFF</span></span>|`IsArabicPresentationForms-A`|  
|<span data-ttu-id="f2a64-584">FE00 - FE0F</span><span class="sxs-lookup"><span data-stu-id="f2a64-584">FE00 - FE0F</span></span>|`IsVariationSelectors`|  
|<span data-ttu-id="f2a64-585">FE20 - FE2F</span><span class="sxs-lookup"><span data-stu-id="f2a64-585">FE20 - FE2F</span></span>|`IsCombiningHalfMarks`|  
|<span data-ttu-id="f2a64-586">FE30 - FE4F</span><span class="sxs-lookup"><span data-stu-id="f2a64-586">FE30 - FE4F</span></span>|`IsCJKCompatibilityForms`|  
|<span data-ttu-id="f2a64-587">FE50 - FE6F</span><span class="sxs-lookup"><span data-stu-id="f2a64-587">FE50 - FE6F</span></span>|`IsSmallFormVariants`|  
|<span data-ttu-id="f2a64-588">FE70 - FEFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-588">FE70 - FEFF</span></span>|`IsArabicPresentationForms-B`|  
|<span data-ttu-id="f2a64-589">FF00 - FFEF</span><span class="sxs-lookup"><span data-stu-id="f2a64-589">FF00 - FFEF</span></span>|`IsHalfwidthandFullwidthForms`|  
|<span data-ttu-id="f2a64-590">FFF0 - FFFF</span><span class="sxs-lookup"><span data-stu-id="f2a64-590">FFF0 - FFFF</span></span>|`IsSpecials`|  
  
 [<span data-ttu-id="f2a64-591">返回页首</span><span class="sxs-lookup"><span data-stu-id="f2a64-591">Back to Top</span></span>](#Top)  
  
<a name="CharacterClassSubtraction"></a>   
## <a name="character-class-subtraction-basegroup---excludedgroup"></a><span data-ttu-id="f2a64-592">字符类减法: [base_group - [excluded_group]]</span><span class="sxs-lookup"><span data-stu-id="f2a64-592">Character Class Subtraction: [base_group - [excluded_group]]</span></span>  
 <span data-ttu-id="f2a64-593">一个字符类定义一组字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-593">A character class defines a set of characters.</span></span> <span data-ttu-id="f2a64-594">字符类减法将产生一组字符，该组字符是从一个字符类中排除另一个字符类中的字符的结果。</span><span class="sxs-lookup"><span data-stu-id="f2a64-594">Character class subtraction yields a set of characters that is the result of excluding the characters in one character class from another character class.</span></span>  
  
 <span data-ttu-id="f2a64-595">字符类减法表达式具有以下形式：</span><span class="sxs-lookup"><span data-stu-id="f2a64-595">A character class subtraction expression has the following form:</span></span>  
  
 <span data-ttu-id="f2a64-596">`[` base_group `-[` excluded_group `]]`</span><span class="sxs-lookup"><span data-stu-id="f2a64-596">`[` *base_group* `-[` *excluded_group* `]]`</span></span>  
  
 <span data-ttu-id="f2a64-597">方括号 (`[]`) 和连字符 (`-`) 是强制的。</span><span class="sxs-lookup"><span data-stu-id="f2a64-597">The square brackets (`[]`) and hyphen (`-`) are mandatory.</span></span> <span data-ttu-id="f2a64-598">base_group 是[正字符组](#PositiveGroup)或[负字符组](#NegativeGroup)。</span><span class="sxs-lookup"><span data-stu-id="f2a64-598">The *base_group* is a [positive character group](#PositiveGroup) or a [negative character group](#NegativeGroup).</span></span> <span data-ttu-id="f2a64-599">*excluded_group* 部分是另一个正字符组或负字符组，或者是另一个字符类减法表达式（即，可以嵌套字符类减法表达式）。</span><span class="sxs-lookup"><span data-stu-id="f2a64-599">The *excluded_group* component is another positive or negative character group, or another character class subtraction expression (that is, you can nest character class subtraction expressions).</span></span>  
  
 <span data-ttu-id="f2a64-600">例如，假设你有一个由从“a”至“z”范围内的字符组成的基本组。</span><span class="sxs-lookup"><span data-stu-id="f2a64-600">For example, suppose you have a base group that consists of the character range from "a" through "z".</span></span> <span data-ttu-id="f2a64-601">若要定义由除字符“m”之外的基本组组成的字符集，请使用 `[a-z-[m]]`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-601">To define the set of characters that consists of the base group except for the character "m", use `[a-z-[m]]`.</span></span> <span data-ttu-id="f2a64-602">若要定义由除字符集“d”、“j”和“p”之外的基本组组成的字符集，请使用 `[a-z-[djp]]`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-602">To define the set of characters that consists of the base group except for the set of characters "d", "j", and "p", use `[a-z-[djp]]`.</span></span> <span data-ttu-id="f2a64-603">若要定义由除从“m”至“p”字符范围之外的基本组组成的字符集，请使用 `[a-z-[m-p]]`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-603">To define the set of characters that consists of the base group except for the character range from "m" through "p", use `[a-z-[m-p]]`.</span></span>  
  
 <span data-ttu-id="f2a64-604">可考虑使用嵌套字符类减法表达式 `[a-z-[d-w-[m-o]]]`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-604">Consider the nested character class subtraction expression, `[a-z-[d-w-[m-o]]]`.</span></span> <span data-ttu-id="f2a64-605">该表达式由最里面的字符范围向外计算。</span><span class="sxs-lookup"><span data-stu-id="f2a64-605">The expression is evaluated from the innermost character range outward.</span></span> <span data-ttu-id="f2a64-606">首先，在从“d”至“w”的字符范围中减去从“m”至“o”的字符范围，这将产生从“d”至“l”和从“p”至“w”的字符集。</span><span class="sxs-lookup"><span data-stu-id="f2a64-606">First, the character range from "m" through "o" is subtracted from the character range "d" through "w", which yields the set of characters from "d" through "l" and "p" through "w".</span></span> <span data-ttu-id="f2a64-607">然后，在从“a”至“z”的字符范围中减去该集合，这将产生字符集 `[abcmnoxyz]`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-607">That set is then subtracted from the character range from "a" through "z", which yields the set of characters `[abcmnoxyz]`.</span></span>  
  
 <span data-ttu-id="f2a64-608">可以将任何字符类用于字符类减法。</span><span class="sxs-lookup"><span data-stu-id="f2a64-608">You can use any character class with character class subtraction.</span></span> <span data-ttu-id="f2a64-609">若要定义字符集，且该字符集包括除空白字符 (`\s`)、标点通用类别中的字符 (`\p{P}`)、`IsGreek` 命名块中的字符 (`\p{IsGreek}`) 以及 Unicode NEXT LINE 控制字符 (\x85) 之外的所有从 \u0000 至 \uFFFF 的 Unicode 字符，请使用 `[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]`。</span><span class="sxs-lookup"><span data-stu-id="f2a64-609">To define the set of characters that consists of all Unicode characters from \u0000 through \uFFFF except white-space characters (`\s`), the characters in the punctuation general category (`\p{P}`), the characters in the `IsGreek` named block (`\p{IsGreek}`), and the Unicode NEXT LINE control character (\x85), use `[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]`.</span></span>  
  
 <span data-ttu-id="f2a64-610">为字符类减法表达式选择将会产生有用结果的字符类。</span><span class="sxs-lookup"><span data-stu-id="f2a64-610">Choose character classes for a character class subtraction expression that will yield useful results.</span></span> <span data-ttu-id="f2a64-611">避免使用产生空字符集的表达式，这将无法匹配任何内容，同时避免使用等效于初始基本组的表达式。</span><span class="sxs-lookup"><span data-stu-id="f2a64-611">Avoid an expression that yields an empty set of characters, which cannot match anything, or an expression that is equivalent to the original base group.</span></span> <span data-ttu-id="f2a64-612">例如，表达式 `[\p{IsBasicLatin}-[\x00-\x7F]]` 从 `IsBasicLatin` 常规类别中减去 `IsBasicLatin` 字符范围内的所有字符，其结果为空集合。</span><span class="sxs-lookup"><span data-stu-id="f2a64-612">For example, the empty set is the result of the expression `[\p{IsBasicLatin}-[\x00-\x7F]]`, which subtracts all characters in the `IsBasicLatin` character range from the `IsBasicLatin` general category.</span></span> <span data-ttu-id="f2a64-613">类似地，表达式 `[a-z-[0-9]]` 的结果为初始基本组。</span><span class="sxs-lookup"><span data-stu-id="f2a64-613">Similarly, the original base group is the result of the expression `[a-z-[0-9]]`.</span></span>  <span data-ttu-id="f2a64-614">这是因为，基本组（它是从“a”至“z”的字母组成的字符范围）不包含排除组（它是从“0”至“9”的十进制数组成的字符范围）中的任何字符。</span><span class="sxs-lookup"><span data-stu-id="f2a64-614">This is because the base group, which is the character range of letters from "a" through "z", does not contain any characters in the excluded group, which is the character range of decimal digits from "0" through "9".</span></span>  
  
 <span data-ttu-id="f2a64-615">下面的示例定义正则表达式 `^[0-9-[2468]]+$`，该表达式匹配输入字符串中的零和奇数。</span><span class="sxs-lookup"><span data-stu-id="f2a64-615">The following example defines a regular expression, `^[0-9-[2468]]+$`, that matches zero and odd digits in an input string.</span></span>  <span data-ttu-id="f2a64-616">正则表达式模式可以解释为下表中所示内容。</span><span class="sxs-lookup"><span data-stu-id="f2a64-616">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="f2a64-617">元素</span><span class="sxs-lookup"><span data-stu-id="f2a64-617">Element</span></span>|<span data-ttu-id="f2a64-618">说明</span><span class="sxs-lookup"><span data-stu-id="f2a64-618">Description</span></span>|  
|-------------|-----------------|  
|^|<span data-ttu-id="f2a64-619">从输入字符串的开头处开始进行匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-619">Begin the match at the start of the input string.</span></span>|  
|`[0-9-[2468]]+`|<span data-ttu-id="f2a64-620">匹配任意字符（从 0 到 9，除了 2、4、6 和 8 之外）的一个或多个匹配项。</span><span class="sxs-lookup"><span data-stu-id="f2a64-620">Match one or more occurrences of any character from 0 to 9 except for 2, 4, 6, and 8.</span></span> <span data-ttu-id="f2a64-621">换句话说，匹配零或奇数的一个或多个匹配项。</span><span class="sxs-lookup"><span data-stu-id="f2a64-621">In other words, match one or more occurrences of zero or an odd digit.</span></span>|  
|$|<span data-ttu-id="f2a64-622">在输入字符串末尾结束匹配。</span><span class="sxs-lookup"><span data-stu-id="f2a64-622">End the match at the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/classsubtraction1.cs#15)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/classsubtraction1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="f2a64-623">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2a64-623">See also</span></span>

- <xref:System.Char.GetUnicodeCategory%2A>  
- [<span data-ttu-id="f2a64-624">正则表达式语言 - 快速参考</span><span class="sxs-lookup"><span data-stu-id="f2a64-624">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
- [<span data-ttu-id="f2a64-625">正则表达式选项</span><span class="sxs-lookup"><span data-stu-id="f2a64-625">Regular Expression Options</span></span>](../../../docs/standard/base-types/regular-expression-options.md)
