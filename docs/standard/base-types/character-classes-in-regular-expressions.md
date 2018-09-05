---
title: 正则表达式中的字符类
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
ms.openlocfilehash: 8a83f99faa5beaf0fd6a5a53f41cdcba5015fa27
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43405081"
---
# <a name="character-classes-in-regular-expressions"></a><span data-ttu-id="79ebf-102">正则表达式中的字符类</span><span class="sxs-lookup"><span data-stu-id="79ebf-102">Character Classes in Regular Expressions</span></span>
<a name="Top"></a><span data-ttu-id="79ebf-103">一个字符类定义一组字符，其中的任一字符均可出现在输入字符串中以便成功匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-103">A character class defines a set of characters, any one of which can occur in an input string for a match to succeed.</span></span> <span data-ttu-id="79ebf-104">.NET 中的正则表达式语言支持以下字符类：</span><span class="sxs-lookup"><span data-stu-id="79ebf-104">The regular expression language in .NET supports the following character classes:</span></span>  
  
-   <span data-ttu-id="79ebf-105">正字符组。</span><span class="sxs-lookup"><span data-stu-id="79ebf-105">Positive character groups.</span></span> <span data-ttu-id="79ebf-106">输入字符串中的字符必须匹配一组指定的字符中的某个字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-106">A character in the input string must match one of a specified set of characters.</span></span> <span data-ttu-id="79ebf-107">有关详细信息，请参阅[正字符组](#PositiveGroup)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-107">For more information, see [Positive Character Group](#PositiveGroup).</span></span>  
  
-   <span data-ttu-id="79ebf-108">负字符组。</span><span class="sxs-lookup"><span data-stu-id="79ebf-108">Negative character groups.</span></span> <span data-ttu-id="79ebf-109">输入字符串中的字符不得匹配一组指定的字符中的某个字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-109">A character in the input string must not match one of a specified set of characters.</span></span> <span data-ttu-id="79ebf-110">有关详细信息，请参阅[负字符组](#NegativeGroup)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-110">For more information, see [Negative Character Group](#NegativeGroup).</span></span>  
  
-   <span data-ttu-id="79ebf-111">任意字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-111">Any character.</span></span> <span data-ttu-id="79ebf-112">正则表达式中的 `.`（圆点或句点）字符是匹配除 `\n` 之外的任何字符的通配符字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-112">The `.` (dot or period) character in a regular expression is a wildcard character that matches any character except `\n`.</span></span> <span data-ttu-id="79ebf-113">有关详细信息，请参阅[任意字符](#AnyCharacter)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-113">For more information, see [Any Character](#AnyCharacter).</span></span>  
  
-   <span data-ttu-id="79ebf-114">通用 Unicode 类别或命名块。</span><span class="sxs-lookup"><span data-stu-id="79ebf-114">A general Unicode category or named block.</span></span> <span data-ttu-id="79ebf-115">输入字符串中的字符必须为特定 Unicode 类别的成员，或必须位于一系列连续的 Unicode 字符中才能成功匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-115">A character in the input string must be a member of a particular Unicode category or must fall within a contiguous range of Unicode characters for a match to succeed.</span></span> <span data-ttu-id="79ebf-116">有关详细信息，请参阅 [Unicode 类别或 Unicode 块](#CategoryOrBlock)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-116">For more information, see [Unicode Category or Unicode Block](#CategoryOrBlock).</span></span>  
  
-   <span data-ttu-id="79ebf-117">负通用 Unicode 类别或命名块。</span><span class="sxs-lookup"><span data-stu-id="79ebf-117">A negative general Unicode category or named block.</span></span> <span data-ttu-id="79ebf-118">输入字符串中的字符不得为特定 Unicode 类别的成员，也不得位于一系列连续的 Unicode 字符中以便成功匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-118">A character in the input string must not be a member of a particular Unicode category or must not fall within a contiguous range of Unicode characters for a match to succeed.</span></span> <span data-ttu-id="79ebf-119">有关详细信息，请参阅[负 Unicode 类别或 Unicode 块](#NegativeCategoryOrBlock)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-119">For more information, see [Negative Unicode Category or Unicode Block](#NegativeCategoryOrBlock).</span></span>  
  
-   <span data-ttu-id="79ebf-120">单词字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-120">A word character.</span></span> <span data-ttu-id="79ebf-121">输入字符串中的字符可以属于适合单词中字符的任何 Unicode 类别。</span><span class="sxs-lookup"><span data-stu-id="79ebf-121">A character in the input string can belong to any of the Unicode categories that are appropriate for characters in words.</span></span> <span data-ttu-id="79ebf-122">有关详细信息，请参阅[单词字符](#WordCharacter)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-122">For more information, see [Word Character](#WordCharacter).</span></span>  
  
-   <span data-ttu-id="79ebf-123">非单词字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-123">A non-word character.</span></span> <span data-ttu-id="79ebf-124">输入字符串中的字符可以属于作为非单词字符的任何 Unicode 类别。</span><span class="sxs-lookup"><span data-stu-id="79ebf-124">A character in the input string can belong to any Unicode category that is not a word character.</span></span> <span data-ttu-id="79ebf-125">有关详细信息，请参阅[非单词字符](#NonWordCharacter)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-125">For more information, see [Non-Word Character](#NonWordCharacter).</span></span>  
  
-   <span data-ttu-id="79ebf-126">空白字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-126">A white-space character.</span></span> <span data-ttu-id="79ebf-127">输入字符串中的字符可以是任何 Unicode 分隔符字符以及众多控制字符中的任一字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-127">A character in the input string can be any Unicode separator character, as well as any one of a number of control characters.</span></span> <span data-ttu-id="79ebf-128">有关详细信息，请参阅[空白字符](#WhitespaceCharacter)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-128">For more information, see [White-Space Character](#WhitespaceCharacter).</span></span>  
  
-   <span data-ttu-id="79ebf-129">非空白字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-129">A non-white-space character.</span></span> <span data-ttu-id="79ebf-130">输入字符串中的字符可以是作为非空白字符的任何字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-130">A character in the input string can be any character that is not a white-space character.</span></span> <span data-ttu-id="79ebf-131">有关详细信息，请参阅[非空白字符](#NonWhitespaceCharacter)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-131">For more information, see [Non-White-Space Character](#NonWhitespaceCharacter).</span></span>  
  
-   <span data-ttu-id="79ebf-132">十进制数字。</span><span class="sxs-lookup"><span data-stu-id="79ebf-132">A decimal digit.</span></span> <span data-ttu-id="79ebf-133">输入字符串中的字符可以是归类为 Unicode 十进制数字的众多字符中的任一字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-133">A character in the input string can be any of a number of characters classified as Unicode decimal digits.</span></span> <span data-ttu-id="79ebf-134">有关详细信息，请参阅[十进制数字字符](#DigitCharacter)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-134">For more information, see [Decimal Digit Character](#DigitCharacter).</span></span>  
  
-   <span data-ttu-id="79ebf-135">非十进制数字。</span><span class="sxs-lookup"><span data-stu-id="79ebf-135">A non-decimal digit.</span></span> <span data-ttu-id="79ebf-136">输入字符串中的字符可以是任何非 Unicode 十进制数字。</span><span class="sxs-lookup"><span data-stu-id="79ebf-136">A character in the input string can be anything other than a Unicode decimal digit.</span></span> <span data-ttu-id="79ebf-137">有关详细信息，请参阅[十进制数字字符](#NonDigitCharacter)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-137">For more information, see [Decimal Digit Character](#NonDigitCharacter).</span></span>  
  
 <span data-ttu-id="79ebf-138">.NET 支持字符类减法表达式，通过该表达式可以定义一组字符作为从一个字符类中排除另一字符类的结果。</span><span class="sxs-lookup"><span data-stu-id="79ebf-138">.NET supports character class subtraction expressions, which enables you to define a set of characters as the result of excluding one character class from another character class.</span></span> <span data-ttu-id="79ebf-139">有关详细信息，请参阅[字符类减法](#CharacterClassSubtraction)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-139">For more information, see [Character Class Subtraction](#CharacterClassSubtraction).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79ebf-140">按类别匹配字符的字符类（如用于匹配字词字符的 [\w](#WordCharacter)，或用于匹配 Unicode 类别的 [\p{}](#CategoryOrBlock)）依赖 <xref:System.Globalization.CharUnicodeInfo> 类提供字符类别信息。</span><span class="sxs-lookup"><span data-stu-id="79ebf-140">Character classes that match characters by category, such as [\w](#WordCharacter) to match word characters or [\p{}](#CategoryOrBlock) to match a Unicode category, rely on the <xref:System.Globalization.CharUnicodeInfo> class to provide information about character categories.</span></span>  <span data-ttu-id="79ebf-141">从 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 开始，字符类别基于 [Unicode 标准 8.0.0 版](https://www.unicode.org/versions/Unicode8.0.0/)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-141">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], character categories are based on [The Unicode Standard, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/).</span></span> <span data-ttu-id="79ebf-142">在 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 到 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 之间，字符类别基于 [Unicode 标准 6.3.0 版](https://www.unicode.org/versions/Unicode6.3.0/)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-142">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] through the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], they are based on [The Unicode Standard, Version 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/).</span></span>  
  
<a name="PositiveGroup"></a>   
## <a name="positive-character-group--"></a><span data-ttu-id="79ebf-143">正字符组：[ ]</span><span class="sxs-lookup"><span data-stu-id="79ebf-143">Positive Character Group: [ ]</span></span>  
 <span data-ttu-id="79ebf-144">正字符组指定一个字符列表，其中的任何一个字符可出现在输入字符串中以便进行匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-144">A positive character group specifies a list of characters, any one of which may appear in an input string for a match to occur.</span></span> <span data-ttu-id="79ebf-145">此字符列表可以单独指定和/或作为范围指定。</span><span class="sxs-lookup"><span data-stu-id="79ebf-145">This list of characters may be specified individually, as a range, or both.</span></span>  
  
 <span data-ttu-id="79ebf-146">用于指定各个字符列表的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="79ebf-146">The syntax for specifying a list of individual characters is as follows:</span></span>  
  
 <span data-ttu-id="79ebf-147">[character_group]</span><span class="sxs-lookup"><span data-stu-id="79ebf-147">[*character_group*]</span></span>  
  
 <span data-ttu-id="79ebf-148">其中，*character_group* 是单个字符的列表，这些字符可出现在输入字符串中以便成功匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-148">where *character_group* is a list of the individual characters that can appear in the input string for a match to succeed.</span></span> <span data-ttu-id="79ebf-149">character_group 可以包含一个或多个文本字符、[转义字符](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md)或字符类的任意组合。</span><span class="sxs-lookup"><span data-stu-id="79ebf-149">*character_group* can consist of any combination of one or more literal characters, [escape characters](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md), or character classes.</span></span>  
  
 <span data-ttu-id="79ebf-150">用于指定字符范围的语法如下：</span><span class="sxs-lookup"><span data-stu-id="79ebf-150">The syntax for specifying a range of characters is as follows:</span></span>  
  
```  
[firstCharacter-lastCharacter]  
```  
  
 <span data-ttu-id="79ebf-151">其中，*firstCharacter* 是范围的开始字符，*lastCharacter* 是范围的结束字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-151">where *firstCharacter* is the character that begins the range and *lastCharacter* is the character that ends the range.</span></span> <span data-ttu-id="79ebf-152">字符范围是通过以下方式定义的一系列连续字符：指定系列中的第一个字符，连字符 (-)，然后指定系列中的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-152">A character range is a contiguous series of characters defined by specifying the first character in the series, a hyphen (-), and then the last character in the series.</span></span> <span data-ttu-id="79ebf-153">如果两个字符具有相邻的 Unicode 码位，则这两个字符是连续的。</span><span class="sxs-lookup"><span data-stu-id="79ebf-153">Two characters are contiguous if they have adjacent Unicode code points.</span></span>  
  
 <span data-ttu-id="79ebf-154">下表列出了一些常见的包含正字符类的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="79ebf-154">Some common regular expression patterns that contain positive character classes are listed in the following table.</span></span>  
  
|<span data-ttu-id="79ebf-155">模式</span><span class="sxs-lookup"><span data-stu-id="79ebf-155">Pattern</span></span>|<span data-ttu-id="79ebf-156">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-156">Description</span></span>|  
|-------------|-----------------|  
|`[aeiou]`|<span data-ttu-id="79ebf-157">匹配所有元音。</span><span class="sxs-lookup"><span data-stu-id="79ebf-157">Match all vowels.</span></span>|  
|`[\p{P}\d]`|<span data-ttu-id="79ebf-158">匹配所有标点符号和十进制数字字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-158">Match all punctuation and decimal digit characters.</span></span>|  
|`[\s\p{P}]`|<span data-ttu-id="79ebf-159">匹配所有空白和标点符号。</span><span class="sxs-lookup"><span data-stu-id="79ebf-159">Match all white space and punctuation.</span></span>|  
  
 <span data-ttu-id="79ebf-160">下面的示例定义包含字符“a”和“e”的正字符组，以使输入字符串必须包含单词“grey”或“gray”且后跟另一个单词以便进行匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-160">The following example defines a positive character group that contains the characters "a" and "e" so that the input string must contain the words "grey" or "gray" followed by another word for a match to occur.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/positivecharclasses.cs#1)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/positivecharclasses.vb#1)]  
  
 <span data-ttu-id="79ebf-161">按以下方式定义正则表达式 `gr[ae]y\s\S+?[\s|\p{P}]`：</span><span class="sxs-lookup"><span data-stu-id="79ebf-161">The regular expression `gr[ae]y\s\S+?[\s|\p{P}]` is defined as follows:</span></span>  
  
|<span data-ttu-id="79ebf-162">模式</span><span class="sxs-lookup"><span data-stu-id="79ebf-162">Pattern</span></span>|<span data-ttu-id="79ebf-163">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-163">Description</span></span>|  
|-------------|-----------------|  
|`gr`|<span data-ttu-id="79ebf-164">匹配文本字符“gr”。</span><span class="sxs-lookup"><span data-stu-id="79ebf-164">Match the literal characters "gr".</span></span>|  
|`[ae]`|<span data-ttu-id="79ebf-165">匹配“a”或“e”。</span><span class="sxs-lookup"><span data-stu-id="79ebf-165">Match either an "a" or an "e".</span></span>|  
|`y\s`|<span data-ttu-id="79ebf-166">匹配后跟空白字符的文本字符“y”。</span><span class="sxs-lookup"><span data-stu-id="79ebf-166">Match the literal character "y" followed by a white-space character.</span></span>|  
|`\S+?`|<span data-ttu-id="79ebf-167">匹配一个或多个非空白字符（但尽可能少）。</span><span class="sxs-lookup"><span data-stu-id="79ebf-167">Match one or more non-white-space characters, but as few as possible.</span></span>|  
|`[\s\p{P}]`|<span data-ttu-id="79ebf-168">匹配空白字符或标点符号。</span><span class="sxs-lookup"><span data-stu-id="79ebf-168">Match either a white-space character or a punctuation mark.</span></span>|  
  
 <span data-ttu-id="79ebf-169">下面的示例匹配以任何大写字母开头的单词。</span><span class="sxs-lookup"><span data-stu-id="79ebf-169">The following example matches words that begin with any capital letter.</span></span> <span data-ttu-id="79ebf-170">它使用子表达式 `[A-Z]` 表示从 A 到 Z 的大写字母范围。</span><span class="sxs-lookup"><span data-stu-id="79ebf-170">It uses the subexpression `[A-Z]` to represent the range of capital letters from A to Z.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/range.cs#3)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/range.vb#3)]  
  
 <span data-ttu-id="79ebf-171">正则表达式 `\b[A-Z]\w*\b` 的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="79ebf-171">The regular expression `\b[A-Z]\w*\b` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="79ebf-172">模式</span><span class="sxs-lookup"><span data-stu-id="79ebf-172">Pattern</span></span>|<span data-ttu-id="79ebf-173">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-173">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="79ebf-174">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="79ebf-174">Start at a word boundary.</span></span>|  
|`[A-Z]`|<span data-ttu-id="79ebf-175">匹配从 A 到 Z 的所有大写字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-175">Match any uppercase character from A to Z.</span></span>|  
|`\w*`|<span data-ttu-id="79ebf-176">匹配零个或多个单词字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-176">Match zero or more word characters.</span></span>|  
|`\b`|<span data-ttu-id="79ebf-177">与字边界匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-177">Match a word boundary.</span></span>|  
  
 [<span data-ttu-id="79ebf-178">返回页首</span><span class="sxs-lookup"><span data-stu-id="79ebf-178">Back to Top</span></span>](#Top)  
  
<a name="NegativeGroup"></a>   
## <a name="negative-character-group-"></a><span data-ttu-id="79ebf-179">负字符组：[^]</span><span class="sxs-lookup"><span data-stu-id="79ebf-179">Negative Character Group: [^]</span></span>  
 <span data-ttu-id="79ebf-180">负字符组指定一个字符列表，这些字符不得出现在输入字符串中以便进行匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-180">A negative character group specifies a list of characters that must not appear in an input string for a match to occur.</span></span> <span data-ttu-id="79ebf-181">此字符列表可以单独指定和/或作为范围指定。</span><span class="sxs-lookup"><span data-stu-id="79ebf-181">The list of characters may be specified individually, as a range, or both.</span></span>  
  
 <span data-ttu-id="79ebf-182">用于指定各个字符列表的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="79ebf-182">The syntax for specifying a list of individual characters is as follows:</span></span>  
  
 <span data-ttu-id="79ebf-183">[^character_group]</span><span class="sxs-lookup"><span data-stu-id="79ebf-183">[*^character_group*]</span></span>  
  
 <span data-ttu-id="79ebf-184">其中，*character_group* 是单个字符的列表，这些字符不可出现在输入字符串中以便成功匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-184">where *character_group* is a list of the individual characters that cannot appear in the input string for a match to succeed.</span></span> <span data-ttu-id="79ebf-185">character_group 可以包含一个或多个文本字符、[转义字符](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md)或字符类的任意组合。</span><span class="sxs-lookup"><span data-stu-id="79ebf-185">*character_group* can consist of any combination of one or more literal characters, [escape characters](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md), or character classes.</span></span>  
  
 <span data-ttu-id="79ebf-186">用于指定字符范围的语法如下：</span><span class="sxs-lookup"><span data-stu-id="79ebf-186">The syntax for specifying a range of characters is as follows:</span></span>  
  
 <span data-ttu-id="79ebf-187">[^firstCharacter-lastCharacter]</span><span class="sxs-lookup"><span data-stu-id="79ebf-187">[^*firstCharacter*-*lastCharacter*]</span></span>  
  
 <span data-ttu-id="79ebf-188">其中，*firstCharacter* 是范围的开始字符，*lastCharacter* 是范围的结束字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-188">where *firstCharacter* is the character that begins the range, and *lastCharacter* is the character that ends the range.</span></span> <span data-ttu-id="79ebf-189">字符范围是通过以下方式定义的一系列连续字符：指定系列中的第一个字符，连字符 (-)，然后指定系列中的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-189">A character range is a contiguous series of characters defined by specifying the first character in the series, a hyphen (-), and then the last character in the series.</span></span> <span data-ttu-id="79ebf-190">如果两个字符具有相邻的 Unicode 码位，则这两个字符是连续的。</span><span class="sxs-lookup"><span data-stu-id="79ebf-190">Two characters are contiguous if they have adjacent Unicode code points.</span></span>  
  
 <span data-ttu-id="79ebf-191">可以连接两个或更多字符范围。</span><span class="sxs-lookup"><span data-stu-id="79ebf-191">Two or more character ranges can be concatenated.</span></span> <span data-ttu-id="79ebf-192">例如，若要指定从“0”至“9”的十进制数范围、从“a”至“f”的小写字母范围，以及从“A”至“F”的大写字母范围，请使用 `[0-9a-fA-F]`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-192">For example, to specify the range of decimal digits from "0" through "9", the range of lowercase letters from "a" through "f", and the range of uppercase letters from "A" through "F", use `[0-9a-fA-F]`.</span></span>  
  
 <span data-ttu-id="79ebf-193">负字符组中的前导符 (`^`) 是强制的，指示字符组为负字符组，而不是正字符组。</span><span class="sxs-lookup"><span data-stu-id="79ebf-193">The leading carat character (`^`) in a negative character group is mandatory and indicates the character group is a negative character group instead of a positive character group.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="79ebf-194">较大正则表达式模式中的负字符组不是零宽度断言。</span><span class="sxs-lookup"><span data-stu-id="79ebf-194">A negative character group in a larger regular expression pattern is not a zero-width assertion.</span></span> <span data-ttu-id="79ebf-195">也就是说，在评估负字符组后，正则表达式引擎会在输入字符串中提升一个字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-195">That is, after evaluating the negative character group, the regular expression engine advances one character in the input string.</span></span>  
  
 <span data-ttu-id="79ebf-196">下表列出了一些常见的包含负字符组的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="79ebf-196">Some common regular expression patterns that contain negative character groups are listed in the following table.</span></span>  
  
|<span data-ttu-id="79ebf-197">模式</span><span class="sxs-lookup"><span data-stu-id="79ebf-197">Pattern</span></span>|<span data-ttu-id="79ebf-198">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-198">Description</span></span>|  
|-------------|-----------------|  
|`[^aeiou]`|<span data-ttu-id="79ebf-199">匹配除元音以外的所有字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-199">Match all characters except vowels.</span></span>|  
|`[^\p{P}\d]`|<span data-ttu-id="79ebf-200">匹配标点符号和十进制数字字符以外的所有字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-200">Match all characters except punctuation and decimal digit characters.</span></span>|  
  
 <span data-ttu-id="79ebf-201">下面的示例匹配以字符“th”开头且后面不跟“o”的任何单词。</span><span class="sxs-lookup"><span data-stu-id="79ebf-201">The following example matches any word that begins with the characters "th" and is not followed by an "o".</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/negativecharclasses.cs#2)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/negativecharclasses.vb#2)]  
  
 <span data-ttu-id="79ebf-202">正则表达式 `\bth[^o]\w+\b` 的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="79ebf-202">The regular expression `\bth[^o]\w+\b` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="79ebf-203">模式</span><span class="sxs-lookup"><span data-stu-id="79ebf-203">Pattern</span></span>|<span data-ttu-id="79ebf-204">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-204">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="79ebf-205">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="79ebf-205">Start at a word boundary.</span></span>|  
|`th`|<span data-ttu-id="79ebf-206">匹配文本字符“th”。</span><span class="sxs-lookup"><span data-stu-id="79ebf-206">Match the literal characters "th".</span></span>|  
|`[^o]`|<span data-ttu-id="79ebf-207">与不是“o”的任何字符匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-207">Match any character that is not an "o".</span></span>|  
|`\w+`|<span data-ttu-id="79ebf-208">匹配一个或多个单词字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-208">Match one or more word characters.</span></span>|  
|`\b`|<span data-ttu-id="79ebf-209">在字边界结束。</span><span class="sxs-lookup"><span data-stu-id="79ebf-209">End at a word boundary.</span></span>|  
  
 [<span data-ttu-id="79ebf-210">返回页首</span><span class="sxs-lookup"><span data-stu-id="79ebf-210">Back to Top</span></span>](#Top)  
  
<a name="AnyCharacter"></a>   
## <a name="any-character-"></a><span data-ttu-id="79ebf-211">任意字符：.</span><span class="sxs-lookup"><span data-stu-id="79ebf-211">Any Character: .</span></span>  
 <span data-ttu-id="79ebf-212">句点字符 (.) 匹配除 `\n`（换行符 \u000A）之外的任何字符，有以下两个限制：</span><span class="sxs-lookup"><span data-stu-id="79ebf-212">The period character (.) matches any character except `\n` (the newline character, \u000A), with the following two qualifications:</span></span>  
  
-   <span data-ttu-id="79ebf-213">如果通过 <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> 选项修改正则表达式模式，或者通过 `.` 选项修改包含 `s` 字符类的模式的部分，则 `.` 可匹配任何字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-213">If a regular expression pattern is modified by the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option, or if the portion of the pattern that contains the `.` character class is modified by the `s` option, `.` matches any character.</span></span> <span data-ttu-id="79ebf-214">有关更多信息，请参见[正则表达式选项](../../../docs/standard/base-types/regular-expression-options.md)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-214">For more information, see [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
     <span data-ttu-id="79ebf-215">下面的示例阐释了默认情况下以及使用 `.` 选项的情况下 <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> 字符类的不同的行为。</span><span class="sxs-lookup"><span data-stu-id="79ebf-215">The following example illustrates the different behavior of the `.` character class by default and with the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option.</span></span> <span data-ttu-id="79ebf-216">正则表达式 `^.+` 在字符串开头开始并匹配每个字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-216">The regular expression `^.+` starts at the beginning of the string and matches every character.</span></span> <span data-ttu-id="79ebf-217">默认情况下，匹配在第一行的结尾结束；正则表达式模式匹配回车符、`\r` 或 \u000D，但不匹配 `\n`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-217">By default, the match ends at the end of the first line; the regular expression pattern matches the carriage return character, `\r` or \u000D, but it does not match `\n`.</span></span> <span data-ttu-id="79ebf-218">由于 <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> 选项将整个输入字符串解释为单行，因此它匹配输入字符串中的每个字符，包括 `\n`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-218">Because the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option interprets the entire input string as a single line, it matches every character in the input string, including `\n`.</span></span>  
  
     [!code-csharp[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any2.cs#5)]
     [!code-vb[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any2.vb#5)]  
  
> [!NOTE]
>  <span data-ttu-id="79ebf-219">由于它匹配除 `\n` 之外的任何字符，因此 `.` 字符类也匹配 `\r`（回车符 \u000D）。</span><span class="sxs-lookup"><span data-stu-id="79ebf-219">Because it matches any character except `\n`, the `.` character class also matches `\r` (the carriage return character, \u000D).</span></span>  
  
-   <span data-ttu-id="79ebf-220">正字符组或负字符组中的句点字符将被视为原义句点字符，而非字符类。</span><span class="sxs-lookup"><span data-stu-id="79ebf-220">In a positive or negative character group, a period is treated as a literal period character, and not as a character class.</span></span> <span data-ttu-id="79ebf-221">有关详细信息，请参阅本主题前面部分的[正字符组](#PositiveGroup)和[负字符组](#NegativeGroup)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-221">For more information, see [Positive Character Group](#PositiveGroup) and [Negative Character Group](#NegativeGroup) earlier in this topic.</span></span> <span data-ttu-id="79ebf-222">下面的示例通过定义包括句点字符 (`.`) 的正则表达式作为字符类和正字符组的成员来进行这方面的演示。</span><span class="sxs-lookup"><span data-stu-id="79ebf-222">The following example provides an illustration by defining a regular expression that includes the period character (`.`) both as a character class and as a member of a positive character group.</span></span> <span data-ttu-id="79ebf-223">正则表达式 `\b.*[.?!;:](\s|\z)` 在字边界处开始，匹配任何字符直到遇到五个标点符号标记之一（包括句点），然后匹配空白字符或字符串的末尾。</span><span class="sxs-lookup"><span data-stu-id="79ebf-223">The regular expression `\b.*[.?!;:](\s|\z)` begins at a word boundary, matches any character until it encounters one of five punctuation marks, including a period, and then matches either a white-space character or the end of the string.</span></span>  
  
     [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any1.cs#4)]
     [!code-vb[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any1.vb#4)]  
  
> [!NOTE]
>  <span data-ttu-id="79ebf-224">由于它匹配任何字符，因此当正则表达式模式尝试多次匹配任何字符时，`.` 语言元素通常会与惰性限定符一起使用。</span><span class="sxs-lookup"><span data-stu-id="79ebf-224">Because it matches any character, the `.` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any character multiple times.</span></span> <span data-ttu-id="79ebf-225">有关详细信息，请参阅[限定符](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-225">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 [<span data-ttu-id="79ebf-226">返回页首</span><span class="sxs-lookup"><span data-stu-id="79ebf-226">Back to Top</span></span>](#Top)  
  
<a name="CategoryOrBlock"></a>   
## <a name="unicode-category-or-unicode-block-p"></a><span data-ttu-id="79ebf-227">Unicode 类别或 Unicode 块：\p{}</span><span class="sxs-lookup"><span data-stu-id="79ebf-227">Unicode Category or Unicode Block: \p{}</span></span>  
 <span data-ttu-id="79ebf-228">Unicode 标准为每个常规类别分配一个字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-228">The Unicode standard assigns each character a general category.</span></span> <span data-ttu-id="79ebf-229">例如，特定字符可以是大写字母（由 `Lu` 类别表示），十进制数字（`Nd` 类别）、数学符号（`Sm` 类别）或段落分隔符（`Zl` 类别）。</span><span class="sxs-lookup"><span data-stu-id="79ebf-229">For example, a particular character can be an uppercase letter (represented by the `Lu` category), a decimal digit (the `Nd` category), a math symbol (the `Sm` category), or a paragraph separator (the `Zl` category).</span></span> <span data-ttu-id="79ebf-230">Unicode 标准中的特定字符集也占据连续码位的特定区域或块。</span><span class="sxs-lookup"><span data-stu-id="79ebf-230">Specific character sets in the Unicode standard also occupy a specific range or block of consecutive code points.</span></span> <span data-ttu-id="79ebf-231">例如，可在 \u0000 和 \u007F 之间找到基本拉丁字符集，并可在 \u0600 和 \u06FF 之间找到阿拉伯语字符集。</span><span class="sxs-lookup"><span data-stu-id="79ebf-231">For example, the basic Latin character set is found from \u0000 through \u007F, while the Arabic character set is found from \u0600 through \u06FF.</span></span>  
  
 <span data-ttu-id="79ebf-232">正则表达式构造</span><span class="sxs-lookup"><span data-stu-id="79ebf-232">The regular expression construct</span></span>  
  
 <span data-ttu-id="79ebf-233">`\p{` *name* `}`</span><span class="sxs-lookup"><span data-stu-id="79ebf-233">`\p{` *name* `}`</span></span>  
  
 <span data-ttu-id="79ebf-234">匹配属于 Unicode 常规类别或命名块的任何字符，其中，name 是类别缩写或命名块的名称。</span><span class="sxs-lookup"><span data-stu-id="79ebf-234">matches any character that belongs to a Unicode general category or named block, where *name* is the category abbreviation or named block name.</span></span> <span data-ttu-id="79ebf-235">有关类别缩写的列表，请参阅本主题稍后的[支持的 Unicode 常规类别](#SupportedUnicodeGeneralCategories)部分。</span><span class="sxs-lookup"><span data-stu-id="79ebf-235">For a list of category abbreviations, see the [Supported Unicode General Categories](#SupportedUnicodeGeneralCategories) section later in this topic.</span></span> <span data-ttu-id="79ebf-236">有关命名块的列表，请参阅本主题稍后的[支持的命名块](#SupportedNamedBlocks)部分。</span><span class="sxs-lookup"><span data-stu-id="79ebf-236">For a list of named blocks, see the [Supported Named Blocks](#SupportedNamedBlocks) section later in this topic.</span></span>  
  
 <span data-ttu-id="79ebf-237">下面的示例使用 `\p{`名称`}` 构造以匹配 Unicode 常规类别（在该示例中为 `Pd` 或“标点，短划线”类别）和命名块（`IsGreek` 和 `IsBasicLatin` 命名块）。</span><span class="sxs-lookup"><span data-stu-id="79ebf-237">The following example uses the `\p{`*name*`}` construct to match both a Unicode general category (in this case, the `Pd`, or Punctuation, Dash category) and a named block (the `IsGreek` and `IsBasicLatin` named blocks).</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/category1.cs#6)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/category1.vb#6)]  
  
 <span data-ttu-id="79ebf-238">正则表达式 `\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` 的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="79ebf-238">The regular expression `\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="79ebf-239">模式</span><span class="sxs-lookup"><span data-stu-id="79ebf-239">Pattern</span></span>|<span data-ttu-id="79ebf-240">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-240">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="79ebf-241">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="79ebf-241">Start at a word boundary.</span></span>|  
|`\p{IsGreek}+`|<span data-ttu-id="79ebf-242">匹配一个或多个希腊语字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-242">Match one or more Greek characters.</span></span>|  
|`(\s)?`|<span data-ttu-id="79ebf-243">匹配零个或一个空白字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-243">Match zero or one white-space character.</span></span>|  
|`(\p{IsGreek}+(\s)?)+`|<span data-ttu-id="79ebf-244">匹配一个或多个希腊语字符后跟零个或一个空白字符的模式一次或多次。</span><span class="sxs-lookup"><span data-stu-id="79ebf-244">Match the pattern of one or more Greek characters followed by zero or one white-space characters one or more times.</span></span>|  
|`\p{Pd}`|<span data-ttu-id="79ebf-245">匹配“标点，短划线”字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-245">Match a Punctuation, Dash character.</span></span>|  
|`\s`|<span data-ttu-id="79ebf-246">与空白字符匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-246">Match a white-space character.</span></span>|  
|`\p{IsBasicLatin}+`|<span data-ttu-id="79ebf-247">匹配一个或多个基本拉丁字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-247">Match one or more basic Latin characters.</span></span>|  
|`(\s)?`|<span data-ttu-id="79ebf-248">匹配零个或一个空白字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-248">Match zero or one white-space character.</span></span>|  
|`(\p{IsBasicLatin}+(\s)?)+`|<span data-ttu-id="79ebf-249">匹配一个或多个基本拉丁字符后跟零个或一个空白字符的模式一次或多次。</span><span class="sxs-lookup"><span data-stu-id="79ebf-249">Match the pattern of one or more basic Latin characters followed by zero or one white-space characters one or more times.</span></span>|  
  
 [<span data-ttu-id="79ebf-250">返回页首</span><span class="sxs-lookup"><span data-stu-id="79ebf-250">Back to Top</span></span>](#Top)  
  
<a name="NegativeCategoryOrBlock"></a>   
## <a name="negative-unicode-category-or-unicode-block-p"></a><span data-ttu-id="79ebf-251">负 Unicode 类别或 Unicode 块：\P{}</span><span class="sxs-lookup"><span data-stu-id="79ebf-251">Negative Unicode Category or Unicode Block: \P{}</span></span>  
 <span data-ttu-id="79ebf-252">Unicode 标准为每个常规类别分配一个字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-252">The Unicode standard assigns each character a general category.</span></span> <span data-ttu-id="79ebf-253">例如，特定字符可以是大写字母（由 `Lu` 类别表示），十进制数字（`Nd` 类别）、数学符号（`Sm` 类别）或段落分隔符（`Zl` 类别）。</span><span class="sxs-lookup"><span data-stu-id="79ebf-253">For example, a particular character can be an uppercase letter (represented by the `Lu` category), a decimal digit (the `Nd` category), a math symbol (the `Sm` category), or a paragraph separator (the `Zl` category).</span></span> <span data-ttu-id="79ebf-254">Unicode 标准中的特定字符集也占据连续码位的特定区域或块。</span><span class="sxs-lookup"><span data-stu-id="79ebf-254">Specific character sets in the Unicode standard also occupy a specific range or block of consecutive code points.</span></span> <span data-ttu-id="79ebf-255">例如，可在 \u0000 和 \u007F 之间找到基本拉丁字符集，并可在 \u0600 和 \u06FF 之间找到阿拉伯语字符集。</span><span class="sxs-lookup"><span data-stu-id="79ebf-255">For example, the basic Latin character set is found from \u0000 through \u007F, while the Arabic character set is found from \u0600 through \u06FF.</span></span>  
  
 <span data-ttu-id="79ebf-256">正则表达式构造</span><span class="sxs-lookup"><span data-stu-id="79ebf-256">The regular expression construct</span></span>  
  
 <span data-ttu-id="79ebf-257">`\P{` *name* `}`</span><span class="sxs-lookup"><span data-stu-id="79ebf-257">`\P{` *name* `}`</span></span>  
  
 <span data-ttu-id="79ebf-258">匹配不属于 Unicode 常规类别或命名块的任何字符，其中，name是类别缩写或命名块的名称。</span><span class="sxs-lookup"><span data-stu-id="79ebf-258">matches any character that does not belong to a Unicode general category or named block, where *name* is the category abbreviation or named block name.</span></span> <span data-ttu-id="79ebf-259">有关类别缩写的列表，请参阅本主题稍后的[支持的 Unicode 常规类别](#SupportedUnicodeGeneralCategories)部分。</span><span class="sxs-lookup"><span data-stu-id="79ebf-259">For a list of category abbreviations, see the [Supported Unicode General Categories](#SupportedUnicodeGeneralCategories) section later in this topic.</span></span> <span data-ttu-id="79ebf-260">有关命名块的列表，请参阅本主题稍后的[支持的命名块](#SupportedNamedBlocks)部分。</span><span class="sxs-lookup"><span data-stu-id="79ebf-260">For a list of named blocks, see the [Supported Named Blocks](#SupportedNamedBlocks) section later in this topic.</span></span>  
  
 <span data-ttu-id="79ebf-261">下面的示例使用 `\P{`name`}`构造来删除数字字符串中的任何货币符号（在该示例中为 `Sc` 或“符号，货币”类别）。</span><span class="sxs-lookup"><span data-stu-id="79ebf-261">The following example uses the `\P{`*name*`}` construct to remove any currency symbols (in this case, the `Sc`, or Symbol, Currency category) from numeric strings.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/notcategory1.cs#7)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/notcategory1.vb#7)]  
  
 <span data-ttu-id="79ebf-262">正则表达式模式 `(\P{Sc})+` 匹配不为货币符号的一个或多个字符；它有效地从结果字符串中抽出任何货币符号。</span><span class="sxs-lookup"><span data-stu-id="79ebf-262">The regular expression pattern `(\P{Sc})+` matches one or more characters that are not currency symbols; it effectively strips any currency symbol from the result string.</span></span>  
  
 [<span data-ttu-id="79ebf-263">返回页首</span><span class="sxs-lookup"><span data-stu-id="79ebf-263">Back to Top</span></span>](#Top)  
  
<a name="WordCharacter"></a>   
## <a name="word-character-w"></a><span data-ttu-id="79ebf-264">单词字符：\w</span><span class="sxs-lookup"><span data-stu-id="79ebf-264">Word Character: \w</span></span>  
 <span data-ttu-id="79ebf-265">`\w` 与任何单词字符匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-265">`\w` matches any word character.</span></span> <span data-ttu-id="79ebf-266">单词字符是下表中列出的任何 Unicode 类别的成员。</span><span class="sxs-lookup"><span data-stu-id="79ebf-266">A word character is a member of any of the Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="79ebf-267">类别</span><span class="sxs-lookup"><span data-stu-id="79ebf-267">Category</span></span>|<span data-ttu-id="79ebf-268">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-268">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="79ebf-269">Ll</span><span class="sxs-lookup"><span data-stu-id="79ebf-269">Ll</span></span>|<span data-ttu-id="79ebf-270">字母，小写</span><span class="sxs-lookup"><span data-stu-id="79ebf-270">Letter, Lowercase</span></span>|  
|<span data-ttu-id="79ebf-271">Lu</span><span class="sxs-lookup"><span data-stu-id="79ebf-271">Lu</span></span>|<span data-ttu-id="79ebf-272">字母，大写</span><span class="sxs-lookup"><span data-stu-id="79ebf-272">Letter, Uppercase</span></span>|  
|<span data-ttu-id="79ebf-273">Lt</span><span class="sxs-lookup"><span data-stu-id="79ebf-273">Lt</span></span>|<span data-ttu-id="79ebf-274">字母，首字母大写</span><span class="sxs-lookup"><span data-stu-id="79ebf-274">Letter, Titlecase</span></span>|  
|<span data-ttu-id="79ebf-275">Lo</span><span class="sxs-lookup"><span data-stu-id="79ebf-275">Lo</span></span>|<span data-ttu-id="79ebf-276">字母，其他</span><span class="sxs-lookup"><span data-stu-id="79ebf-276">Letter, Other</span></span>|  
|<span data-ttu-id="79ebf-277">Lm</span><span class="sxs-lookup"><span data-stu-id="79ebf-277">Lm</span></span>|<span data-ttu-id="79ebf-278">字母，修饰符</span><span class="sxs-lookup"><span data-stu-id="79ebf-278">Letter, Modifier</span></span>|  
|<span data-ttu-id="79ebf-279">Mn</span><span class="sxs-lookup"><span data-stu-id="79ebf-279">Mn</span></span>|<span data-ttu-id="79ebf-280">标记，非间距</span><span class="sxs-lookup"><span data-stu-id="79ebf-280">Mark, Nonspacing</span></span>|  
|<span data-ttu-id="79ebf-281">Nd</span><span class="sxs-lookup"><span data-stu-id="79ebf-281">Nd</span></span>|<span data-ttu-id="79ebf-282">数字，十进制数</span><span class="sxs-lookup"><span data-stu-id="79ebf-282">Number, Decimal Digit</span></span>|  
|<span data-ttu-id="79ebf-283">Pc</span><span class="sxs-lookup"><span data-stu-id="79ebf-283">Pc</span></span>|<span data-ttu-id="79ebf-284">标点，连接符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-284">Punctuation, Connector.</span></span> <span data-ttu-id="79ebf-285">此类别包含 10 个字符，最常用的字符是 LOWLINE 字符 (_)，u+005F。</span><span class="sxs-lookup"><span data-stu-id="79ebf-285">This category includes ten characters, the most commonly used of which is the LOWLINE character (_), u+005F.</span></span>|  
  
 <span data-ttu-id="79ebf-286">如果指定了符合 ECMAScript 的行为，则 `\w` 等效于 `[a-zA-Z_0-9]`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-286">If ECMAScript-compliant behavior is specified, `\w` is equivalent to `[a-zA-Z_0-9]`.</span></span> <span data-ttu-id="79ebf-287">有关 ECMAScript 正则表达式的信息，请参阅[正则表达式选项](../../../docs/standard/base-types/regular-expression-options.md)中的“ECMAScript 匹配行为”部分。</span><span class="sxs-lookup"><span data-stu-id="79ebf-287">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79ebf-288">由于它匹配任何单词字符，因此当正则表达式模式尝试多次匹配任何单词字符且后跟特定单词字符时，`\w` 语言元素通常会与惰性限定符一起使用。</span><span class="sxs-lookup"><span data-stu-id="79ebf-288">Because it matches any word character, the `\w` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any word character multiple times, followed by a specific word character.</span></span> <span data-ttu-id="79ebf-289">有关详细信息，请参阅[限定符](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-289">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="79ebf-290">下面的示例使用 `\w` 语言元素来匹配单词中的重复字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-290">The following example uses the `\w` language element to match duplicate characters in a word.</span></span> <span data-ttu-id="79ebf-291">该示例定义可按如下方式解释的正则表达式模式 `(\w)\1`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-291">The example defines a regular expression pattern, `(\w)\1`, which can be interpreted as follows.</span></span>  
  
|<span data-ttu-id="79ebf-292">元素</span><span class="sxs-lookup"><span data-stu-id="79ebf-292">Element</span></span>|<span data-ttu-id="79ebf-293">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-293">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="79ebf-294">(\w)</span><span class="sxs-lookup"><span data-stu-id="79ebf-294">(\w)</span></span>|<span data-ttu-id="79ebf-295">匹配单词字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-295">Match a word character.</span></span> <span data-ttu-id="79ebf-296">这是第一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="79ebf-296">This is the first capturing group.</span></span>|  
|<span data-ttu-id="79ebf-297">\1</span><span class="sxs-lookup"><span data-stu-id="79ebf-297">\1</span></span>|<span data-ttu-id="79ebf-298">匹配第一次捕获的值。</span><span class="sxs-lookup"><span data-stu-id="79ebf-298">Match the value of the first capture.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/wordchar1.cs#8)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/wordchar1.vb#8)]  
  
 [<span data-ttu-id="79ebf-299">返回页首</span><span class="sxs-lookup"><span data-stu-id="79ebf-299">Back to Top</span></span>](#Top)  
  
<a name="NonWordCharacter"></a>   
## <a name="non-word-character-w"></a><span data-ttu-id="79ebf-300">非单词字符：\W</span><span class="sxs-lookup"><span data-stu-id="79ebf-300">Non-Word Character: \W</span></span>  
 <span data-ttu-id="79ebf-301">`\W` 匹配任何非单词字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-301">`\W` matches any non-word character.</span></span> <span data-ttu-id="79ebf-302">\W 语言元素等效于以下字符类：</span><span class="sxs-lookup"><span data-stu-id="79ebf-302">The \W language element is equivalent to the following character class:</span></span>  
  
```  
[^\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]  
```  
  
 <span data-ttu-id="79ebf-303">换言之，它与下表列出的 Unicode 类别中的字符以外的任何字符匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-303">In other words, it matches any character except for those in the Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="79ebf-304">类别</span><span class="sxs-lookup"><span data-stu-id="79ebf-304">Category</span></span>|<span data-ttu-id="79ebf-305">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-305">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="79ebf-306">Ll</span><span class="sxs-lookup"><span data-stu-id="79ebf-306">Ll</span></span>|<span data-ttu-id="79ebf-307">字母，小写</span><span class="sxs-lookup"><span data-stu-id="79ebf-307">Letter, Lowercase</span></span>|  
|<span data-ttu-id="79ebf-308">Lu</span><span class="sxs-lookup"><span data-stu-id="79ebf-308">Lu</span></span>|<span data-ttu-id="79ebf-309">字母，大写</span><span class="sxs-lookup"><span data-stu-id="79ebf-309">Letter, Uppercase</span></span>|  
|<span data-ttu-id="79ebf-310">Lt</span><span class="sxs-lookup"><span data-stu-id="79ebf-310">Lt</span></span>|<span data-ttu-id="79ebf-311">字母，首字母大写</span><span class="sxs-lookup"><span data-stu-id="79ebf-311">Letter, Titlecase</span></span>|  
|<span data-ttu-id="79ebf-312">Lo</span><span class="sxs-lookup"><span data-stu-id="79ebf-312">Lo</span></span>|<span data-ttu-id="79ebf-313">字母，其他</span><span class="sxs-lookup"><span data-stu-id="79ebf-313">Letter, Other</span></span>|  
|<span data-ttu-id="79ebf-314">Lm</span><span class="sxs-lookup"><span data-stu-id="79ebf-314">Lm</span></span>|<span data-ttu-id="79ebf-315">字母，修饰符</span><span class="sxs-lookup"><span data-stu-id="79ebf-315">Letter, Modifier</span></span>|  
|<span data-ttu-id="79ebf-316">Mn</span><span class="sxs-lookup"><span data-stu-id="79ebf-316">Mn</span></span>|<span data-ttu-id="79ebf-317">标记，非间距</span><span class="sxs-lookup"><span data-stu-id="79ebf-317">Mark, Nonspacing</span></span>|  
|<span data-ttu-id="79ebf-318">Nd</span><span class="sxs-lookup"><span data-stu-id="79ebf-318">Nd</span></span>|<span data-ttu-id="79ebf-319">数字，十进制数</span><span class="sxs-lookup"><span data-stu-id="79ebf-319">Number, Decimal Digit</span></span>|  
|<span data-ttu-id="79ebf-320">Pc</span><span class="sxs-lookup"><span data-stu-id="79ebf-320">Pc</span></span>|<span data-ttu-id="79ebf-321">标点，连接符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-321">Punctuation, Connector.</span></span> <span data-ttu-id="79ebf-322">此类别包含 10 个字符，最常用的字符是 LOWLINE 字符 (_)，u+005F。</span><span class="sxs-lookup"><span data-stu-id="79ebf-322">This category includes ten characters, the most commonly used of which is the LOWLINE character (_), u+005F.</span></span>|  
  
 <span data-ttu-id="79ebf-323">如果指定了符合 ECMAScript 的行为，则 `\W` 等效于 `[^a-zA-Z_0-9]`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-323">If ECMAScript-compliant behavior is specified, `\W` is equivalent to `[^a-zA-Z_0-9]`.</span></span> <span data-ttu-id="79ebf-324">有关 ECMAScript 正则表达式的信息，请参阅[正则表达式选项](../../../docs/standard/base-types/regular-expression-options.md)中的“ECMAScript 匹配行为”部分。</span><span class="sxs-lookup"><span data-stu-id="79ebf-324">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79ebf-325">由于它匹配任何非单词字符，因此当正则表达式模式尝试多次匹配任何非单词字符且后跟特定非单词字符时，`\W` 语言元素通常会与惰性限定符一起使用。</span><span class="sxs-lookup"><span data-stu-id="79ebf-325">Because it matches any non-word character, the `\W` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any non-word character multiple times followed by a specific non-word character.</span></span> <span data-ttu-id="79ebf-326">有关详细信息，请参阅[限定符](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-326">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="79ebf-327">下面的示例阐释 `\W` 字符类。</span><span class="sxs-lookup"><span data-stu-id="79ebf-327">The following example illustrates the `\W` character class.</span></span>  <span data-ttu-id="79ebf-328">它定义正则表达式模式 `\b(\w+)(\W){1,2}`，该模式匹配后跟一个或两个非单词字符（例如，空白或标点符号）的单词。</span><span class="sxs-lookup"><span data-stu-id="79ebf-328">It defines a regular expression pattern, `\b(\w+)(\W){1,2}`, that matches a word followed by one or two non-word characters, such as white space or punctuation.</span></span> <span data-ttu-id="79ebf-329">正则表达式模式可以解释为下表中所示内容。</span><span class="sxs-lookup"><span data-stu-id="79ebf-329">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="79ebf-330">元素</span><span class="sxs-lookup"><span data-stu-id="79ebf-330">Element</span></span>|<span data-ttu-id="79ebf-331">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-331">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="79ebf-332">\b</span><span class="sxs-lookup"><span data-stu-id="79ebf-332">\b</span></span>|<span data-ttu-id="79ebf-333">在单词边界处开始匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-333">Begin the match at a word boundary.</span></span>|  
|<span data-ttu-id="79ebf-334">(\w+)</span><span class="sxs-lookup"><span data-stu-id="79ebf-334">(\w+)</span></span>|<span data-ttu-id="79ebf-335">匹配一个或多个单词字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-335">Match one or more word characters.</span></span> <span data-ttu-id="79ebf-336">这是第一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="79ebf-336">This is the first capturing group.</span></span>|  
|<span data-ttu-id="79ebf-337">(\W){1,2}</span><span class="sxs-lookup"><span data-stu-id="79ebf-337">(\W){1,2}</span></span>|<span data-ttu-id="79ebf-338">匹配非单词字符一次或两次。</span><span class="sxs-lookup"><span data-stu-id="79ebf-338">Match a non-word character either one or two times.</span></span> <span data-ttu-id="79ebf-339">这是第二个捕获组。</span><span class="sxs-lookup"><span data-stu-id="79ebf-339">This is the second capturing group.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwordchar1.cs#9)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwordchar1.vb#9)]  
  
 <span data-ttu-id="79ebf-340">由于第二个捕获组的 <xref:System.Text.RegularExpressions.Group> 对象仅包含单个捕获的非单词字符，因此该示例将从 <xref:System.Text.RegularExpressions.CaptureCollection> 属性返回的 <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> 对象中检索所有捕获的非单词字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-340">Because the <xref:System.Text.RegularExpressions.Group> object for the second capturing group contains only a single captured non-word character, the example retrieves all captured non-word characters from the <xref:System.Text.RegularExpressions.CaptureCollection> object that is returned by the <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> property.</span></span>  
  
 [<span data-ttu-id="79ebf-341">返回页首</span><span class="sxs-lookup"><span data-stu-id="79ebf-341">Back to Top</span></span>](#Top)  
  
<a name="WhitespaceCharacter"></a>   
## <a name="white-space-character-s"></a><span data-ttu-id="79ebf-342">空白字符：\s</span><span class="sxs-lookup"><span data-stu-id="79ebf-342">White-Space Character: \s</span></span>  
 <span data-ttu-id="79ebf-343">`\s` 匹配任何空白字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-343">`\s` matches any white-space character.</span></span> <span data-ttu-id="79ebf-344">它等效于下表中列出的转义序列和 Unicode 类别。</span><span class="sxs-lookup"><span data-stu-id="79ebf-344">It is equivalent to the escape sequences and Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="79ebf-345">类别</span><span class="sxs-lookup"><span data-stu-id="79ebf-345">Category</span></span>|<span data-ttu-id="79ebf-346">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-346">Description</span></span>|  
|--------------|-----------------|  
|`\f`|<span data-ttu-id="79ebf-347">窗体换页符，\u000C。</span><span class="sxs-lookup"><span data-stu-id="79ebf-347">The form feed character, \u000C.</span></span>|  
|`\n`|<span data-ttu-id="79ebf-348">换行符，\u000A。</span><span class="sxs-lookup"><span data-stu-id="79ebf-348">The newline character, \u000A.</span></span>|  
|`\r`|<span data-ttu-id="79ebf-349">回车符，\u000D。</span><span class="sxs-lookup"><span data-stu-id="79ebf-349">The carriage return character, \u000D.</span></span>|  
|`\t`|<span data-ttu-id="79ebf-350">制表符，\u0009。</span><span class="sxs-lookup"><span data-stu-id="79ebf-350">The tab character, \u0009.</span></span>|  
|`\v`|<span data-ttu-id="79ebf-351">垂直制表符，\u000B。</span><span class="sxs-lookup"><span data-stu-id="79ebf-351">The vertical tab character, \u000B.</span></span>|  
|`\x85`|<span data-ttu-id="79ebf-352">省略号或 NEXT LINE (NEL) 字符 (…)，\u0085。</span><span class="sxs-lookup"><span data-stu-id="79ebf-352">The ellipsis or NEXT LINE (NEL) character (…), \u0085.</span></span>|  
|`\p{Z}`|<span data-ttu-id="79ebf-353">匹配任何分隔符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-353">Matches any separator character.</span></span>|  
  
 <span data-ttu-id="79ebf-354">如果指定了符合 ECMAScript 的行为，则 `\s` 等效于 `[ \f\n\r\t\v]`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-354">If ECMAScript-compliant behavior is specified, `\s` is equivalent to `[ \f\n\r\t\v]`.</span></span> <span data-ttu-id="79ebf-355">有关 ECMAScript 正则表达式的信息，请参阅[正则表达式选项](../../../docs/standard/base-types/regular-expression-options.md)中的“ECMAScript 匹配行为”部分。</span><span class="sxs-lookup"><span data-stu-id="79ebf-355">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="79ebf-356">下面的示例阐释 `\s` 字符类。</span><span class="sxs-lookup"><span data-stu-id="79ebf-356">The following example illustrates the `\s` character class.</span></span> <span data-ttu-id="79ebf-357">它定义正则表达式模式 `\b\w+(e)?s(\s|$)`，该模式匹配以“s”或“es”结尾且后跟一个空白字符或输入字符串末尾的单词。</span><span class="sxs-lookup"><span data-stu-id="79ebf-357">It defines a regular expression pattern, `\b\w+(e)?s(\s|$)`, that matches a word ending in either "s" or "es" followed by either a white-space character or the end of the input string.</span></span> <span data-ttu-id="79ebf-358">正则表达式模式可以解释为下表中所示内容。</span><span class="sxs-lookup"><span data-stu-id="79ebf-358">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="79ebf-359">元素</span><span class="sxs-lookup"><span data-stu-id="79ebf-359">Element</span></span>|<span data-ttu-id="79ebf-360">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-360">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="79ebf-361">\b</span><span class="sxs-lookup"><span data-stu-id="79ebf-361">\b</span></span>|<span data-ttu-id="79ebf-362">在单词边界处开始匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-362">Begin the match at a word boundary.</span></span>|  
|<span data-ttu-id="79ebf-363">\w+</span><span class="sxs-lookup"><span data-stu-id="79ebf-363">\w+</span></span>|<span data-ttu-id="79ebf-364">匹配一个或多个单词字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-364">Match one or more word characters.</span></span>|  
|<span data-ttu-id="79ebf-365">(e)?</span><span class="sxs-lookup"><span data-stu-id="79ebf-365">(e)?</span></span>|<span data-ttu-id="79ebf-366">匹配“e”零次或一次。</span><span class="sxs-lookup"><span data-stu-id="79ebf-366">Match an "e" either zero or one time.</span></span>|  
|<span data-ttu-id="79ebf-367">s</span><span class="sxs-lookup"><span data-stu-id="79ebf-367">s</span></span>|<span data-ttu-id="79ebf-368">匹配“s”。</span><span class="sxs-lookup"><span data-stu-id="79ebf-368">Match an "s".</span></span>|  
|<span data-ttu-id="79ebf-369">(\s&#124;$)</span><span class="sxs-lookup"><span data-stu-id="79ebf-369">(\s&#124;$)</span></span>|<span data-ttu-id="79ebf-370">匹配空白字符或输入字符串的末尾。</span><span class="sxs-lookup"><span data-stu-id="79ebf-370">Match either a white-space character or the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/whitespace1.cs#10)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/whitespace1.vb#10)]  
  
 [<span data-ttu-id="79ebf-371">返回页首</span><span class="sxs-lookup"><span data-stu-id="79ebf-371">Back to Top</span></span>](#Top)  
  
<a name="NonWhitespaceCharacter"></a>   
## <a name="non-white-space-character-s"></a><span data-ttu-id="79ebf-372">非空白字符：\S</span><span class="sxs-lookup"><span data-stu-id="79ebf-372">Non-White-Space Character: \S</span></span>  
 <span data-ttu-id="79ebf-373">`\S` 匹配任何非空白字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-373">`\S` matches any non-white-space character.</span></span> <span data-ttu-id="79ebf-374">它等效于 `[^\f\n\r\t\v\x85\p{Z}]` 正则表达式模式或与等效于 `\s` 的正则表达式模式（与空白字符匹配）相反。</span><span class="sxs-lookup"><span data-stu-id="79ebf-374">It is equivalent to the `[^\f\n\r\t\v\x85\p{Z}]` regular expression pattern, or the opposite of the regular expression pattern that is equivalent to `\s`, which matches white-space characters.</span></span> <span data-ttu-id="79ebf-375">有关详细信息，请参阅[空白字符：\s](#WhitespaceCharacter)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-375">For more information, see [White-Space Character: \s](#WhitespaceCharacter).</span></span>  
  
 <span data-ttu-id="79ebf-376">如果指定了符合 ECMAScript 的行为，则 `\S` 等效于 `[^ \f\n\r\t\v]`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-376">If ECMAScript-compliant behavior is specified, `\S` is equivalent to  `[^ \f\n\r\t\v]`.</span></span> <span data-ttu-id="79ebf-377">有关 ECMAScript 正则表达式的信息，请参阅[正则表达式选项](../../../docs/standard/base-types/regular-expression-options.md)中的“ECMAScript 匹配行为”部分。</span><span class="sxs-lookup"><span data-stu-id="79ebf-377">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="79ebf-378">下面的示例阐释 `\S` 语言元素。</span><span class="sxs-lookup"><span data-stu-id="79ebf-378">The following example illustrates the `\S` language element.</span></span> <span data-ttu-id="79ebf-379">正则表达式模式 `\b(\S+)\s?` 匹配由空白字符分隔的字符串。</span><span class="sxs-lookup"><span data-stu-id="79ebf-379">The regular expression pattern `\b(\S+)\s?` matches strings that are delimited by white-space characters.</span></span> <span data-ttu-id="79ebf-380">匹配项的 <xref:System.Text.RegularExpressions.GroupCollection> 对象中的第二个元素包含匹配的字符串。</span><span class="sxs-lookup"><span data-stu-id="79ebf-380">The second element in the match's <xref:System.Text.RegularExpressions.GroupCollection> object contains the matched string.</span></span> <span data-ttu-id="79ebf-381">正则表达式可按下表中的方式解释。</span><span class="sxs-lookup"><span data-stu-id="79ebf-381">The regular expression can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="79ebf-382">元素</span><span class="sxs-lookup"><span data-stu-id="79ebf-382">Element</span></span>|<span data-ttu-id="79ebf-383">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-383">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="79ebf-384">在单词边界处开始匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-384">Begin the match at a word boundary.</span></span>|  
|`(\S+)`|<span data-ttu-id="79ebf-385">匹配一个或多个非空白字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-385">Match one or more non-white-space characters.</span></span> <span data-ttu-id="79ebf-386">这是第一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="79ebf-386">This is the first capturing group.</span></span>|  
|`\s?`|<span data-ttu-id="79ebf-387">匹配零个或一个空白字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-387">Match zero or one white-space character.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwhitespace1.cs#11)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwhitespace1.vb#11)]  
  
 [<span data-ttu-id="79ebf-388">返回页首</span><span class="sxs-lookup"><span data-stu-id="79ebf-388">Back to Top</span></span>](#Top)  
  
<a name="DigitCharacter"></a>   
## <a name="decimal-digit-character-d"></a><span data-ttu-id="79ebf-389">十进制数字字符：\d</span><span class="sxs-lookup"><span data-stu-id="79ebf-389">Decimal Digit Character: \d</span></span>  
 <span data-ttu-id="79ebf-390">`\d` 匹配任何十进制数字。</span><span class="sxs-lookup"><span data-stu-id="79ebf-390">`\d` matches any decimal digit.</span></span> <span data-ttu-id="79ebf-391">它等效于 `\p{Nd}` 正则表达式模式，该模式包含标准的十进制数字 0-9 以及众多其他字符集的十进制数字。</span><span class="sxs-lookup"><span data-stu-id="79ebf-391">It is equivalent to the `\p{Nd}` regular expression pattern, which includes the standard decimal digits 0-9 as well as the decimal digits of a number of other character sets.</span></span>  
  
 <span data-ttu-id="79ebf-392">如果指定了符合 ECMAScript 的行为，则 `\d` 等效于 `[0-9]`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-392">If ECMAScript-compliant behavior is specified, `\d` is equivalent to  `[0-9]`.</span></span> <span data-ttu-id="79ebf-393">有关 ECMAScript 正则表达式的信息，请参阅[正则表达式选项](../../../docs/standard/base-types/regular-expression-options.md)中的“ECMAScript 匹配行为”部分。</span><span class="sxs-lookup"><span data-stu-id="79ebf-393">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="79ebf-394">下面的示例阐释 `\d` 语言元素。</span><span class="sxs-lookup"><span data-stu-id="79ebf-394">The following example illustrates the `\d` language element.</span></span> <span data-ttu-id="79ebf-395">它测试输入字符串是否表示美国和加拿大的有效电话号码。</span><span class="sxs-lookup"><span data-stu-id="79ebf-395">It tests whether an input string represents a valid telephone number in the United States and Canada.</span></span> <span data-ttu-id="79ebf-396">正则表达式模式 `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` 的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="79ebf-396">The regular expression pattern `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="79ebf-397">元素</span><span class="sxs-lookup"><span data-stu-id="79ebf-397">Element</span></span>|<span data-ttu-id="79ebf-398">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-398">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="79ebf-399">从输入字符串的开头部分开始匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-399">Begin the match at the beginning of the input string.</span></span>|  
|`\(?`|<span data-ttu-id="79ebf-400">匹配零个或一个“(”文本字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-400">Match zero or one literal "(" character.</span></span>|  
|`\d{3}`|<span data-ttu-id="79ebf-401">匹配三个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="79ebf-401">Match three decimal digits.</span></span>|  
|`\)?`|<span data-ttu-id="79ebf-402">匹配零个或一个“)”文本字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-402">Match zero or one literal ")" character.</span></span>|  
|`[\s-]`|<span data-ttu-id="79ebf-403">匹配连字符或空白字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-403">Match a hyphen or a white-space character.</span></span>|  
|`(\(?\d{3}\)?[\s-])?`|<span data-ttu-id="79ebf-404">匹配后跟三个十进制数字的可选左括号、可选右括号和空白字符或连字符零次或一次。</span><span class="sxs-lookup"><span data-stu-id="79ebf-404">Match an optional opening parenthesis followed by three decimal digits, an optional closing parenthesis, and either a white-space character or a hyphen zero or one time.</span></span> <span data-ttu-id="79ebf-405">这是第一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="79ebf-405">This is the first capturing group.</span></span>|  
|`\d{3}-\d{4}`|<span data-ttu-id="79ebf-406">匹配后跟连字符和四个以上的十进制数字的三个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="79ebf-406">Match three decimal digits followed by a hyphen and four more decimal digits.</span></span>|  
|`$`|<span data-ttu-id="79ebf-407">匹配输入字符串的末尾部分。</span><span class="sxs-lookup"><span data-stu-id="79ebf-407">Match the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/digit1.cs#12)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/digit1.vb#12)]  
  
 [<span data-ttu-id="79ebf-408">返回页首</span><span class="sxs-lookup"><span data-stu-id="79ebf-408">Back to Top</span></span>](#Top)  
  
<a name="NonDigitCharacter"></a>   
## <a name="non-digit-character-d"></a><span data-ttu-id="79ebf-409">非数字字符：\D</span><span class="sxs-lookup"><span data-stu-id="79ebf-409">Non-Digit Character: \D</span></span>  
 <span data-ttu-id="79ebf-410">`\D` 匹配任何非数字字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-410">`\D` matches any non-digit character.</span></span> <span data-ttu-id="79ebf-411">它等效于 `\P{Nd}` 正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="79ebf-411">It is equivalent to the `\P{Nd}` regular expression pattern.</span></span>  
  
 <span data-ttu-id="79ebf-412">如果指定了符合 ECMAScript 的行为，则 `\D` 等效于 `[^0-9]`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-412">If ECMAScript-compliant behavior is specified, `\D` is equivalent to  `[^0-9]`.</span></span> <span data-ttu-id="79ebf-413">有关 ECMAScript 正则表达式的信息，请参阅[正则表达式选项](../../../docs/standard/base-types/regular-expression-options.md)中的“ECMAScript 匹配行为”部分。</span><span class="sxs-lookup"><span data-stu-id="79ebf-413">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="79ebf-414">下面的示例阐释了 \D 语言元素。</span><span class="sxs-lookup"><span data-stu-id="79ebf-414">The following example illustrates the \D language element.</span></span> <span data-ttu-id="79ebf-415">它测试部件号等字符串是否包含适当的十进制和非十进制数字字符的组合。</span><span class="sxs-lookup"><span data-stu-id="79ebf-415">It tests whether a string such as a part number consists of the appropriate combination of decimal and non-decimal characters.</span></span> <span data-ttu-id="79ebf-416">正则表达式模式 `^\D\d{1,5}\D*$` 的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="79ebf-416">The regular expression pattern `^\D\d{1,5}\D*$` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="79ebf-417">元素</span><span class="sxs-lookup"><span data-stu-id="79ebf-417">Element</span></span>|<span data-ttu-id="79ebf-418">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-418">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="79ebf-419">从输入字符串的开头部分开始匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-419">Begin the match at the beginning of the input string.</span></span>|  
|`\D`|<span data-ttu-id="79ebf-420">匹配非数字字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-420">Match a non-digit character.</span></span>|  
|`\d{1,5}`|<span data-ttu-id="79ebf-421">匹配一到五个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="79ebf-421">Match from one to five decimal digits.</span></span>|  
|`\D*`|<span data-ttu-id="79ebf-422">匹配零个、一个或多个非十进制字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-422">Match zero, one, or more non-decimal characters.</span></span>|  
|`$`|<span data-ttu-id="79ebf-423">匹配输入字符串的末尾部分。</span><span class="sxs-lookup"><span data-stu-id="79ebf-423">Match the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nondigit1.cs#13)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nondigit1.vb#13)]  
  
 [<span data-ttu-id="79ebf-424">返回页首</span><span class="sxs-lookup"><span data-stu-id="79ebf-424">Back to Top</span></span>](#Top)  
  
<a name="SupportedUnicodeGeneralCategories"></a>   
## <a name="supported-unicode-general-categories"></a><span data-ttu-id="79ebf-425">支持的 Unicode 常规类别</span><span class="sxs-lookup"><span data-stu-id="79ebf-425">Supported Unicode General Categories</span></span>  
 <span data-ttu-id="79ebf-426">Unicode 定义下表列出的常规类别。</span><span class="sxs-lookup"><span data-stu-id="79ebf-426">Unicode defines the general categories listed in the following table.</span></span> <span data-ttu-id="79ebf-427">有关详细信息，请参阅 [Unicode 字符数据库](https://www.unicode.org/reports/tr44/)中的“UCD 文件格式”和“常规类别值”子主题。</span><span class="sxs-lookup"><span data-stu-id="79ebf-427">For more information, see the "UCD File Format" and "General Category Values" subtopics at the [Unicode Character Database](https://www.unicode.org/reports/tr44/).</span></span>  
  
|<span data-ttu-id="79ebf-428">类别</span><span class="sxs-lookup"><span data-stu-id="79ebf-428">Category</span></span>|<span data-ttu-id="79ebf-429">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-429">Description</span></span>|  
|--------------|-----------------|  
|`Lu`|<span data-ttu-id="79ebf-430">字母，大写</span><span class="sxs-lookup"><span data-stu-id="79ebf-430">Letter, Uppercase</span></span>|  
|`Ll`|<span data-ttu-id="79ebf-431">字母，小写</span><span class="sxs-lookup"><span data-stu-id="79ebf-431">Letter, Lowercase</span></span>|  
|`Lt`|<span data-ttu-id="79ebf-432">字母，首字母大写</span><span class="sxs-lookup"><span data-stu-id="79ebf-432">Letter, Titlecase</span></span>|  
|`Lm`|<span data-ttu-id="79ebf-433">字母，修饰符</span><span class="sxs-lookup"><span data-stu-id="79ebf-433">Letter, Modifier</span></span>|  
|`Lo`|<span data-ttu-id="79ebf-434">字母，其他</span><span class="sxs-lookup"><span data-stu-id="79ebf-434">Letter, Other</span></span>|  
|`L`|<span data-ttu-id="79ebf-435">所有字母字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-435">All letter characters.</span></span> <span data-ttu-id="79ebf-436">这包括 `Lu`、`Ll`、`Lt`、`Lm` 和 `Lo` 字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-436">This includes the `Lu`, `Ll`, `Lt`, `Lm`, and `Lo` characters.</span></span>|  
|`Mn`|<span data-ttu-id="79ebf-437">标记，非间距</span><span class="sxs-lookup"><span data-stu-id="79ebf-437">Mark, Nonspacing</span></span>|  
|`Mc`|<span data-ttu-id="79ebf-438">标记，间距组合</span><span class="sxs-lookup"><span data-stu-id="79ebf-438">Mark, Spacing Combining</span></span>|  
|`Me`|<span data-ttu-id="79ebf-439">标记，封闭</span><span class="sxs-lookup"><span data-stu-id="79ebf-439">Mark, Enclosing</span></span>|  
|`M`|<span data-ttu-id="79ebf-440">所有音调符号标记。</span><span class="sxs-lookup"><span data-stu-id="79ebf-440">All diacritic marks.</span></span> <span data-ttu-id="79ebf-441">这包括 `Mn`、`Mc` 和 `Me` 类别。</span><span class="sxs-lookup"><span data-stu-id="79ebf-441">This includes the `Mn`, `Mc`, and `Me` categories.</span></span>|  
|`Nd`|<span data-ttu-id="79ebf-442">数字，十进制数</span><span class="sxs-lookup"><span data-stu-id="79ebf-442">Number, Decimal Digit</span></span>|  
|`Nl`|<span data-ttu-id="79ebf-443">数字，字母</span><span class="sxs-lookup"><span data-stu-id="79ebf-443">Number, Letter</span></span>|  
|`No`|<span data-ttu-id="79ebf-444">数字，其他</span><span class="sxs-lookup"><span data-stu-id="79ebf-444">Number, Other</span></span>|  
|`N`|<span data-ttu-id="79ebf-445">所有数字。</span><span class="sxs-lookup"><span data-stu-id="79ebf-445">All numbers.</span></span> <span data-ttu-id="79ebf-446">这包括 `Nd`、`Nl` 和 `No` 类别。</span><span class="sxs-lookup"><span data-stu-id="79ebf-446">This includes the `Nd`, `Nl`, and `No` categories.</span></span>|  
|`Pc`|<span data-ttu-id="79ebf-447">标点，连接符</span><span class="sxs-lookup"><span data-stu-id="79ebf-447">Punctuation, Connector</span></span>|  
|`Pd`|<span data-ttu-id="79ebf-448">标点，短划线</span><span class="sxs-lookup"><span data-stu-id="79ebf-448">Punctuation, Dash</span></span>|  
|`Ps`|<span data-ttu-id="79ebf-449">标点，开始</span><span class="sxs-lookup"><span data-stu-id="79ebf-449">Punctuation, Open</span></span>|  
|`Pe`|<span data-ttu-id="79ebf-450">标点，结束</span><span class="sxs-lookup"><span data-stu-id="79ebf-450">Punctuation, Close</span></span>|  
|`Pi`|<span data-ttu-id="79ebf-451">标点，前引号（根据具体使用情况，作用可能像 Ps 或 Pe）</span><span class="sxs-lookup"><span data-stu-id="79ebf-451">Punctuation, Initial quote (may behave like Ps or Pe depending on usage)</span></span>|  
|`Pf`|<span data-ttu-id="79ebf-452">标点，后引号（根据具体使用情况，作用可能像 Ps 或 Pe）</span><span class="sxs-lookup"><span data-stu-id="79ebf-452">Punctuation, Final quote (may behave like Ps or Pe depending on usage)</span></span>|  
|`Po`|<span data-ttu-id="79ebf-453">标点，其他</span><span class="sxs-lookup"><span data-stu-id="79ebf-453">Punctuation, Other</span></span>|  
|`P`|<span data-ttu-id="79ebf-454">所有标点字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-454">All punctuation characters.</span></span> <span data-ttu-id="79ebf-455">这包括 `Pc`、`Pd`、`Ps`, `Pe`、`Pi`、`Pf` 和 `Po` 类别。</span><span class="sxs-lookup"><span data-stu-id="79ebf-455">This includes the `Pc`, `Pd`, `Ps`, `Pe`, `Pi`, `Pf`, and `Po` categories.</span></span>|  
|`Sm`|<span data-ttu-id="79ebf-456">符号，数学</span><span class="sxs-lookup"><span data-stu-id="79ebf-456">Symbol, Math</span></span>|  
|`Sc`|<span data-ttu-id="79ebf-457">符号，货币</span><span class="sxs-lookup"><span data-stu-id="79ebf-457">Symbol, Currency</span></span>|  
|`Sk`|<span data-ttu-id="79ebf-458">符号，修饰符</span><span class="sxs-lookup"><span data-stu-id="79ebf-458">Symbol, Modifier</span></span>|  
|`So`|<span data-ttu-id="79ebf-459">符号，其他</span><span class="sxs-lookup"><span data-stu-id="79ebf-459">Symbol, Other</span></span>|  
|`S`|<span data-ttu-id="79ebf-460">所有符号。</span><span class="sxs-lookup"><span data-stu-id="79ebf-460">All symbols.</span></span> <span data-ttu-id="79ebf-461">这包括 `Sm`、`Sc`、`Sk` 和 `So` 类别。</span><span class="sxs-lookup"><span data-stu-id="79ebf-461">This includes the `Sm`, `Sc`, `Sk`, and `So` categories.</span></span>|  
|`Zs`|<span data-ttu-id="79ebf-462">分隔符，空白</span><span class="sxs-lookup"><span data-stu-id="79ebf-462">Separator, Space</span></span>|  
|`Zl`|<span data-ttu-id="79ebf-463">分隔符，行</span><span class="sxs-lookup"><span data-stu-id="79ebf-463">Separator, Line</span></span>|  
|`Zp`|<span data-ttu-id="79ebf-464">分隔符，段落</span><span class="sxs-lookup"><span data-stu-id="79ebf-464">Separator, Paragraph</span></span>|  
|`Z`|<span data-ttu-id="79ebf-465">所有分隔符字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-465">All separator characters.</span></span> <span data-ttu-id="79ebf-466">这包括 `Zs`、`Zl` 和 `Zp` 类别。</span><span class="sxs-lookup"><span data-stu-id="79ebf-466">This includes the `Zs`, `Zl`, and `Zp` categories.</span></span>|  
|`Cc`|<span data-ttu-id="79ebf-467">其他，控制</span><span class="sxs-lookup"><span data-stu-id="79ebf-467">Other, Control</span></span>|  
|`Cf`|<span data-ttu-id="79ebf-468">其他，格式</span><span class="sxs-lookup"><span data-stu-id="79ebf-468">Other, Format</span></span>|  
|`Cs`|<span data-ttu-id="79ebf-469">其他，代理项</span><span class="sxs-lookup"><span data-stu-id="79ebf-469">Other, Surrogate</span></span>|  
|`Co`|<span data-ttu-id="79ebf-470">其他，私用</span><span class="sxs-lookup"><span data-stu-id="79ebf-470">Other, Private Use</span></span>|  
|`Cn`|<span data-ttu-id="79ebf-471">其他，未赋值（任何字符都不具有此属性）</span><span class="sxs-lookup"><span data-stu-id="79ebf-471">Other, Not Assigned (no characters have this property)</span></span>|  
|`C`|<span data-ttu-id="79ebf-472">所有控制字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-472">All control characters.</span></span> <span data-ttu-id="79ebf-473">这包括 `Cc`、`Cf`、`Cs`、`Co` 和 `Cn` 类别。</span><span class="sxs-lookup"><span data-stu-id="79ebf-473">This includes the `Cc`, `Cf`, `Cs`, `Co`, and `Cn` categories.</span></span>|  
  
 <span data-ttu-id="79ebf-474">可以通过将任何特定字符传递到 <xref:System.Char.GetUnicodeCategory%2A> 方法来确定该字符的 Unicode 类别。</span><span class="sxs-lookup"><span data-stu-id="79ebf-474">You can determine the Unicode category of any particular character by passing that character to the <xref:System.Char.GetUnicodeCategory%2A> method.</span></span> <span data-ttu-id="79ebf-475">下面的示例使用 <xref:System.Char.GetUnicodeCategory%2A> 方法来确定包含所选拉丁字符的数组中的每个元素的类别。</span><span class="sxs-lookup"><span data-stu-id="79ebf-475">The following example uses the <xref:System.Char.GetUnicodeCategory%2A> method to determine the category of each element in an array that contains selected Latin characters.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/getunicodecategory1.cs#14)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/getunicodecategory1.vb#14)]  
  
 [<span data-ttu-id="79ebf-476">返回页首</span><span class="sxs-lookup"><span data-stu-id="79ebf-476">Back to Top</span></span>](#Top)  
  
<a name="SupportedNamedBlocks"></a>   
## <a name="supported-named-blocks"></a><span data-ttu-id="79ebf-477">支持的命名块</span><span class="sxs-lookup"><span data-stu-id="79ebf-477">Supported Named Blocks</span></span>  
 <span data-ttu-id="79ebf-478">.NET 提供下表中所列的命名块。</span><span class="sxs-lookup"><span data-stu-id="79ebf-478">.NET provides the named blocks listed in the following table.</span></span> <span data-ttu-id="79ebf-479">该组支持的命名块基于 Unicode 4.0 和 Perl 5.6。</span><span class="sxs-lookup"><span data-stu-id="79ebf-479">The set of supported named blocks is based on Unicode 4.0 and Perl 5.6.</span></span>  
  
|<span data-ttu-id="79ebf-480">码位范围</span><span class="sxs-lookup"><span data-stu-id="79ebf-480">Code point range</span></span>|<span data-ttu-id="79ebf-481">块名称</span><span class="sxs-lookup"><span data-stu-id="79ebf-481">Block name</span></span>|  
|----------------------|----------------|  
|<span data-ttu-id="79ebf-482">0000 - 007F</span><span class="sxs-lookup"><span data-stu-id="79ebf-482">0000 - 007F</span></span>|`IsBasicLatin`|  
|<span data-ttu-id="79ebf-483">0080 - 00FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-483">0080 - 00FF</span></span>|`IsLatin-1Supplement`|  
|<span data-ttu-id="79ebf-484">0100 - 017F</span><span class="sxs-lookup"><span data-stu-id="79ebf-484">0100 - 017F</span></span>|`IsLatinExtended-A`|  
|<span data-ttu-id="79ebf-485">0180 - 024F</span><span class="sxs-lookup"><span data-stu-id="79ebf-485">0180 - 024F</span></span>|`IsLatinExtended-B`|  
|<span data-ttu-id="79ebf-486">0250 - 02AF</span><span class="sxs-lookup"><span data-stu-id="79ebf-486">0250 - 02AF</span></span>|`IsIPAExtensions`|  
|<span data-ttu-id="79ebf-487">02B0 - 02FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-487">02B0 - 02FF</span></span>|`IsSpacingModifierLetters`|  
|<span data-ttu-id="79ebf-488">0300 - 036F</span><span class="sxs-lookup"><span data-stu-id="79ebf-488">0300 - 036F</span></span>|`IsCombiningDiacriticalMarks`|  
|<span data-ttu-id="79ebf-489">0370 - 03FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-489">0370 - 03FF</span></span>|`IsGreek`<br /><br /> <span data-ttu-id="79ebf-490">或</span><span class="sxs-lookup"><span data-stu-id="79ebf-490">-or-</span></span><br /><br /> `IsGreekandCoptic`|  
|<span data-ttu-id="79ebf-491">0400 - 04FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-491">0400 - 04FF</span></span>|`IsCyrillic`|  
|<span data-ttu-id="79ebf-492">0500 - 052F</span><span class="sxs-lookup"><span data-stu-id="79ebf-492">0500 - 052F</span></span>|`IsCyrillicSupplement`|  
|<span data-ttu-id="79ebf-493">0530 - 058F</span><span class="sxs-lookup"><span data-stu-id="79ebf-493">0530 - 058F</span></span>|`IsArmenian`|  
|<span data-ttu-id="79ebf-494">0590 - 05FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-494">0590 - 05FF</span></span>|`IsHebrew`|  
|<span data-ttu-id="79ebf-495">0600 - 06FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-495">0600 - 06FF</span></span>|`IsArabic`|  
|<span data-ttu-id="79ebf-496">0700 - 074F</span><span class="sxs-lookup"><span data-stu-id="79ebf-496">0700 - 074F</span></span>|`IsSyriac`|  
|<span data-ttu-id="79ebf-497">0780 - 07BF</span><span class="sxs-lookup"><span data-stu-id="79ebf-497">0780 - 07BF</span></span>|`IsThaana`|  
|<span data-ttu-id="79ebf-498">0900 - 097F</span><span class="sxs-lookup"><span data-stu-id="79ebf-498">0900 - 097F</span></span>|`IsDevanagari`|  
|<span data-ttu-id="79ebf-499">0980 - 09FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-499">0980 - 09FF</span></span>|`IsBengali`|  
|<span data-ttu-id="79ebf-500">0A00 - 0A7F</span><span class="sxs-lookup"><span data-stu-id="79ebf-500">0A00 - 0A7F</span></span>|`IsGurmukhi`|  
|<span data-ttu-id="79ebf-501">0A80 - 0AFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-501">0A80 - 0AFF</span></span>|`IsGujarati`|  
|<span data-ttu-id="79ebf-502">0B00 - 0B7F</span><span class="sxs-lookup"><span data-stu-id="79ebf-502">0B00 - 0B7F</span></span>|`IsOriya`|  
|<span data-ttu-id="79ebf-503">0B80 - 0BFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-503">0B80 - 0BFF</span></span>|`IsTamil`|  
|<span data-ttu-id="79ebf-504">0C00 - 0C7F</span><span class="sxs-lookup"><span data-stu-id="79ebf-504">0C00 - 0C7F</span></span>|`IsTelugu`|  
|<span data-ttu-id="79ebf-505">0C80 - 0CFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-505">0C80 - 0CFF</span></span>|`IsKannada`|  
|<span data-ttu-id="79ebf-506">0D00 - 0D7F</span><span class="sxs-lookup"><span data-stu-id="79ebf-506">0D00 - 0D7F</span></span>|`IsMalayalam`|  
|<span data-ttu-id="79ebf-507">0D80 - 0DFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-507">0D80 - 0DFF</span></span>|`IsSinhala`|  
|<span data-ttu-id="79ebf-508">0E00 - 0E7F</span><span class="sxs-lookup"><span data-stu-id="79ebf-508">0E00 - 0E7F</span></span>|`IsThai`|  
|<span data-ttu-id="79ebf-509">0E80 - 0EFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-509">0E80 - 0EFF</span></span>|`IsLao`|  
|<span data-ttu-id="79ebf-510">0F00 - 0FFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-510">0F00 - 0FFF</span></span>|`IsTibetan`|  
|<span data-ttu-id="79ebf-511">1000 - 109F</span><span class="sxs-lookup"><span data-stu-id="79ebf-511">1000 - 109F</span></span>|`IsMyanmar`|  
|<span data-ttu-id="79ebf-512">10A0 - 10FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-512">10A0 - 10FF</span></span>|`IsGeorgian`|  
|<span data-ttu-id="79ebf-513">1100 - 11FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-513">1100 - 11FF</span></span>|`IsHangulJamo`|  
|<span data-ttu-id="79ebf-514">1200 - 137F</span><span class="sxs-lookup"><span data-stu-id="79ebf-514">1200 - 137F</span></span>|`IsEthiopic`|  
|<span data-ttu-id="79ebf-515">13A0 - 13FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-515">13A0 - 13FF</span></span>|`IsCherokee`|  
|<span data-ttu-id="79ebf-516">1400 - 167F</span><span class="sxs-lookup"><span data-stu-id="79ebf-516">1400 - 167F</span></span>|`IsUnifiedCanadianAboriginalSyllabics`|  
|<span data-ttu-id="79ebf-517">1680 - 169F</span><span class="sxs-lookup"><span data-stu-id="79ebf-517">1680 - 169F</span></span>|`IsOgham`|  
|<span data-ttu-id="79ebf-518">16A0 - 16FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-518">16A0 - 16FF</span></span>|`IsRunic`|  
|<span data-ttu-id="79ebf-519">1700 - 171F</span><span class="sxs-lookup"><span data-stu-id="79ebf-519">1700 - 171F</span></span>|`IsTagalog`|  
|<span data-ttu-id="79ebf-520">1720 - 173F</span><span class="sxs-lookup"><span data-stu-id="79ebf-520">1720 - 173F</span></span>|`IsHanunoo`|  
|<span data-ttu-id="79ebf-521">1740 - 175F</span><span class="sxs-lookup"><span data-stu-id="79ebf-521">1740 - 175F</span></span>|`IsBuhid`|  
|<span data-ttu-id="79ebf-522">1760 - 177F</span><span class="sxs-lookup"><span data-stu-id="79ebf-522">1760 - 177F</span></span>|`IsTagbanwa`|  
|<span data-ttu-id="79ebf-523">1780 - 17FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-523">1780 - 17FF</span></span>|`IsKhmer`|  
|<span data-ttu-id="79ebf-524">1800 - 18AF</span><span class="sxs-lookup"><span data-stu-id="79ebf-524">1800 - 18AF</span></span>|`IsMongolian`|  
|<span data-ttu-id="79ebf-525">1900 - 194F</span><span class="sxs-lookup"><span data-stu-id="79ebf-525">1900 - 194F</span></span>|`IsLimbu`|  
|<span data-ttu-id="79ebf-526">1950 - 197F</span><span class="sxs-lookup"><span data-stu-id="79ebf-526">1950 - 197F</span></span>|`IsTaiLe`|  
|<span data-ttu-id="79ebf-527">19E0 - 19FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-527">19E0 - 19FF</span></span>|`IsKhmerSymbols`|  
|<span data-ttu-id="79ebf-528">1D00 - 1D7F</span><span class="sxs-lookup"><span data-stu-id="79ebf-528">1D00 - 1D7F</span></span>|`IsPhoneticExtensions`|  
|<span data-ttu-id="79ebf-529">1E00 - 1EFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-529">1E00 - 1EFF</span></span>|`IsLatinExtendedAdditional`|  
|<span data-ttu-id="79ebf-530">1F00 - 1FFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-530">1F00 - 1FFF</span></span>|`IsGreekExtended`|  
|<span data-ttu-id="79ebf-531">2000 - 206F</span><span class="sxs-lookup"><span data-stu-id="79ebf-531">2000 - 206F</span></span>|`IsGeneralPunctuation`|  
|<span data-ttu-id="79ebf-532">2070 - 209F</span><span class="sxs-lookup"><span data-stu-id="79ebf-532">2070 - 209F</span></span>|`IsSuperscriptsandSubscripts`|  
|<span data-ttu-id="79ebf-533">20A0 - 20CF</span><span class="sxs-lookup"><span data-stu-id="79ebf-533">20A0 - 20CF</span></span>|`IsCurrencySymbols`|  
|<span data-ttu-id="79ebf-534">20D0 - 20FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-534">20D0 - 20FF</span></span>|`IsCombiningDiacriticalMarksforSymbols`<br /><br /> <span data-ttu-id="79ebf-535">或</span><span class="sxs-lookup"><span data-stu-id="79ebf-535">-or-</span></span><br /><br /> `IsCombiningMarksforSymbols`|  
|<span data-ttu-id="79ebf-536">2100 - 214F</span><span class="sxs-lookup"><span data-stu-id="79ebf-536">2100 - 214F</span></span>|`IsLetterlikeSymbols`|  
|<span data-ttu-id="79ebf-537">2150 - 218F</span><span class="sxs-lookup"><span data-stu-id="79ebf-537">2150 - 218F</span></span>|`IsNumberForms`|  
|<span data-ttu-id="79ebf-538">2190 - 21FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-538">2190 - 21FF</span></span>|`IsArrows`|  
|<span data-ttu-id="79ebf-539">2200 - 22FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-539">2200 - 22FF</span></span>|`IsMathematicalOperators`|  
|<span data-ttu-id="79ebf-540">2300 - 23FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-540">2300 - 23FF</span></span>|`IsMiscellaneousTechnical`|  
|<span data-ttu-id="79ebf-541">2400 - 243F</span><span class="sxs-lookup"><span data-stu-id="79ebf-541">2400 - 243F</span></span>|`IsControlPictures`|  
|<span data-ttu-id="79ebf-542">2440 - 245F</span><span class="sxs-lookup"><span data-stu-id="79ebf-542">2440 - 245F</span></span>|`IsOpticalCharacterRecognition`|  
|<span data-ttu-id="79ebf-543">2460 - 24FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-543">2460 - 24FF</span></span>|`IsEnclosedAlphanumerics`|  
|<span data-ttu-id="79ebf-544">2500 - 257F</span><span class="sxs-lookup"><span data-stu-id="79ebf-544">2500 - 257F</span></span>|`IsBoxDrawing`|  
|<span data-ttu-id="79ebf-545">2580 - 259F</span><span class="sxs-lookup"><span data-stu-id="79ebf-545">2580 - 259F</span></span>|`IsBlockElements`|  
|<span data-ttu-id="79ebf-546">25A0 - 25FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-546">25A0 - 25FF</span></span>|`IsGeometricShapes`|  
|<span data-ttu-id="79ebf-547">2600 - 26FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-547">2600 - 26FF</span></span>|`IsMiscellaneousSymbols`|  
|<span data-ttu-id="79ebf-548">2700 - 27BF</span><span class="sxs-lookup"><span data-stu-id="79ebf-548">2700 - 27BF</span></span>|`IsDingbats`|  
|<span data-ttu-id="79ebf-549">27C0 - 27EF</span><span class="sxs-lookup"><span data-stu-id="79ebf-549">27C0 - 27EF</span></span>|`IsMiscellaneousMathematicalSymbols-A`|  
|<span data-ttu-id="79ebf-550">27F0 - 27FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-550">27F0 - 27FF</span></span>|`IsSupplementalArrows-A`|  
|<span data-ttu-id="79ebf-551">2800 - 28FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-551">2800 - 28FF</span></span>|`IsBraillePatterns`|  
|<span data-ttu-id="79ebf-552">2900 - 297F</span><span class="sxs-lookup"><span data-stu-id="79ebf-552">2900 - 297F</span></span>|`IsSupplementalArrows-B`|  
|<span data-ttu-id="79ebf-553">2980 - 29FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-553">2980 - 29FF</span></span>|`IsMiscellaneousMathematicalSymbols-B`|  
|<span data-ttu-id="79ebf-554">2A00 - 2AFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-554">2A00 - 2AFF</span></span>|`IsSupplementalMathematicalOperators`|  
|<span data-ttu-id="79ebf-555">2B00 - 2BFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-555">2B00 - 2BFF</span></span>|`IsMiscellaneousSymbolsandArrows`|  
|<span data-ttu-id="79ebf-556">2E80 - 2EFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-556">2E80 - 2EFF</span></span>|`IsCJKRadicalsSupplement`|  
|<span data-ttu-id="79ebf-557">2F00 - 2FDF</span><span class="sxs-lookup"><span data-stu-id="79ebf-557">2F00 - 2FDF</span></span>|`IsKangxiRadicals`|  
|<span data-ttu-id="79ebf-558">2FF0 - 2FFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-558">2FF0 - 2FFF</span></span>|`IsIdeographicDescriptionCharacters`|  
|<span data-ttu-id="79ebf-559">3000 - 303F</span><span class="sxs-lookup"><span data-stu-id="79ebf-559">3000 - 303F</span></span>|`IsCJKSymbolsandPunctuation`|  
|<span data-ttu-id="79ebf-560">3040 - 309F</span><span class="sxs-lookup"><span data-stu-id="79ebf-560">3040 - 309F</span></span>|`IsHiragana`|  
|<span data-ttu-id="79ebf-561">30A0 - 30FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-561">30A0 - 30FF</span></span>|`IsKatakana`|  
|<span data-ttu-id="79ebf-562">3100 - 312F</span><span class="sxs-lookup"><span data-stu-id="79ebf-562">3100 - 312F</span></span>|`IsBopomofo`|  
|<span data-ttu-id="79ebf-563">3130 - 318F</span><span class="sxs-lookup"><span data-stu-id="79ebf-563">3130 - 318F</span></span>|`IsHangulCompatibilityJamo`|  
|<span data-ttu-id="79ebf-564">3190 - 319F</span><span class="sxs-lookup"><span data-stu-id="79ebf-564">3190 - 319F</span></span>|`IsKanbun`|  
|<span data-ttu-id="79ebf-565">31A0 - 31BF</span><span class="sxs-lookup"><span data-stu-id="79ebf-565">31A0 - 31BF</span></span>|`IsBopomofoExtended`|  
|<span data-ttu-id="79ebf-566">31F0 - 31FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-566">31F0 - 31FF</span></span>|`IsKatakanaPhoneticExtensions`|  
|<span data-ttu-id="79ebf-567">3200 - 32FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-567">3200 - 32FF</span></span>|`IsEnclosedCJKLettersandMonths`|  
|<span data-ttu-id="79ebf-568">3300 - 33FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-568">3300 - 33FF</span></span>|`IsCJKCompatibility`|  
|<span data-ttu-id="79ebf-569">3400 - 4DBF</span><span class="sxs-lookup"><span data-stu-id="79ebf-569">3400 - 4DBF</span></span>|`IsCJKUnifiedIdeographsExtensionA`|  
|<span data-ttu-id="79ebf-570">4DC0 - 4DFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-570">4DC0 - 4DFF</span></span>|`IsYijingHexagramSymbols`|  
|<span data-ttu-id="79ebf-571">4E00 - 9FFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-571">4E00 - 9FFF</span></span>|`IsCJKUnifiedIdeographs`|  
|<span data-ttu-id="79ebf-572">A000 - A48F</span><span class="sxs-lookup"><span data-stu-id="79ebf-572">A000 - A48F</span></span>|`IsYiSyllables`|  
|<span data-ttu-id="79ebf-573">A490 - A4CF</span><span class="sxs-lookup"><span data-stu-id="79ebf-573">A490 - A4CF</span></span>|`IsYiRadicals`|  
|<span data-ttu-id="79ebf-574">AC00 - D7AF</span><span class="sxs-lookup"><span data-stu-id="79ebf-574">AC00 - D7AF</span></span>|`IsHangulSyllables`|  
|<span data-ttu-id="79ebf-575">D800 - DB7F</span><span class="sxs-lookup"><span data-stu-id="79ebf-575">D800 - DB7F</span></span>|`IsHighSurrogates`|  
|<span data-ttu-id="79ebf-576">DB80 - DBFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-576">DB80 - DBFF</span></span>|`IsHighPrivateUseSurrogates`|  
|<span data-ttu-id="79ebf-577">DC00 - DFFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-577">DC00 - DFFF</span></span>|`IsLowSurrogates`|  
|<span data-ttu-id="79ebf-578">E000 - F8FF</span><span class="sxs-lookup"><span data-stu-id="79ebf-578">E000 - F8FF</span></span>|<span data-ttu-id="79ebf-579">`IsPrivateUse` 或 `IsPrivateUseArea`</span><span class="sxs-lookup"><span data-stu-id="79ebf-579">`IsPrivateUse` or `IsPrivateUseArea`</span></span>|  
|<span data-ttu-id="79ebf-580">F900 - FAFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-580">F900 - FAFF</span></span>|`IsCJKCompatibilityIdeographs`|  
|<span data-ttu-id="79ebf-581">FB00 - FB4F</span><span class="sxs-lookup"><span data-stu-id="79ebf-581">FB00 - FB4F</span></span>|`IsAlphabeticPresentationForms`|  
|<span data-ttu-id="79ebf-582">FB50 - FDFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-582">FB50 - FDFF</span></span>|`IsArabicPresentationForms-A`|  
|<span data-ttu-id="79ebf-583">FE00 - FE0F</span><span class="sxs-lookup"><span data-stu-id="79ebf-583">FE00 - FE0F</span></span>|`IsVariationSelectors`|  
|<span data-ttu-id="79ebf-584">FE20 - FE2F</span><span class="sxs-lookup"><span data-stu-id="79ebf-584">FE20 - FE2F</span></span>|`IsCombiningHalfMarks`|  
|<span data-ttu-id="79ebf-585">FE30 - FE4F</span><span class="sxs-lookup"><span data-stu-id="79ebf-585">FE30 - FE4F</span></span>|`IsCJKCompatibilityForms`|  
|<span data-ttu-id="79ebf-586">FE50 - FE6F</span><span class="sxs-lookup"><span data-stu-id="79ebf-586">FE50 - FE6F</span></span>|`IsSmallFormVariants`|  
|<span data-ttu-id="79ebf-587">FE70 - FEFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-587">FE70 - FEFF</span></span>|`IsArabicPresentationForms-B`|  
|<span data-ttu-id="79ebf-588">FF00 - FFEF</span><span class="sxs-lookup"><span data-stu-id="79ebf-588">FF00 - FFEF</span></span>|`IsHalfwidthandFullwidthForms`|  
|<span data-ttu-id="79ebf-589">FFF0 - FFFF</span><span class="sxs-lookup"><span data-stu-id="79ebf-589">FFF0 - FFFF</span></span>|`IsSpecials`|  
  
 [<span data-ttu-id="79ebf-590">返回页首</span><span class="sxs-lookup"><span data-stu-id="79ebf-590">Back to Top</span></span>](#Top)  
  
<a name="CharacterClassSubtraction"></a>   
## <a name="character-class-subtraction-basegroup---excludedgroup"></a><span data-ttu-id="79ebf-591">字符类减法: [base_group - [excluded_group]]</span><span class="sxs-lookup"><span data-stu-id="79ebf-591">Character Class Subtraction: [base_group - [excluded_group]]</span></span>  
 <span data-ttu-id="79ebf-592">一个字符类定义一组字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-592">A character class defines a set of characters.</span></span> <span data-ttu-id="79ebf-593">字符类减法将产生一组字符，该组字符是从一个字符类中排除另一个字符类中的字符的结果。</span><span class="sxs-lookup"><span data-stu-id="79ebf-593">Character class subtraction yields a set of characters that is the result of excluding the characters in one character class from another character class.</span></span>  
  
 <span data-ttu-id="79ebf-594">字符类减法表达式具有以下形式：</span><span class="sxs-lookup"><span data-stu-id="79ebf-594">A character class subtraction expression has the following form:</span></span>  
  
 <span data-ttu-id="79ebf-595">`[` base_group `-[` excluded_group `]]`</span><span class="sxs-lookup"><span data-stu-id="79ebf-595">`[` *base_group* `-[` *excluded_group* `]]`</span></span>  
  
 <span data-ttu-id="79ebf-596">方括号 (`[]`) 和连字符 (`-`) 是强制的。</span><span class="sxs-lookup"><span data-stu-id="79ebf-596">The square brackets (`[]`) and hyphen (`-`) are mandatory.</span></span> <span data-ttu-id="79ebf-597">base_group 是[正字符组](#PositiveGroup)或[负字符组](#NegativeGroup)。</span><span class="sxs-lookup"><span data-stu-id="79ebf-597">The *base_group* is a [positive character group](#PositiveGroup) or a [negative character group](#NegativeGroup).</span></span> <span data-ttu-id="79ebf-598">*excluded_group* 部分是另一个正字符组或负字符组，或者是另一个字符类减法表达式（即，可以嵌套字符类减法表达式）。</span><span class="sxs-lookup"><span data-stu-id="79ebf-598">The *excluded_group* component is another positive or negative character group, or another character class subtraction expression (that is, you can nest character class subtraction expressions).</span></span>  
  
 <span data-ttu-id="79ebf-599">例如，假设你有一个由从“a”至“z”范围内的字符组成的基本组。</span><span class="sxs-lookup"><span data-stu-id="79ebf-599">For example, suppose you have a base group that consists of the character range from "a" through "z".</span></span> <span data-ttu-id="79ebf-600">若要定义由除字符“m”之外的基本组组成的字符集，请使用 `[a-z-[m]]`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-600">To define the set of characters that consists of the base group except for the character "m", use `[a-z-[m]]`.</span></span> <span data-ttu-id="79ebf-601">若要定义由除字符集“d”、“j”和“p”之外的基本组组成的字符集，请使用 `[a-z-[djp]]`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-601">To define the set of characters that consists of the base group except for the set of characters "d", "j", and "p", use `[a-z-[djp]]`.</span></span> <span data-ttu-id="79ebf-602">若要定义由除从“m”至“p”字符范围之外的基本组组成的字符集，请使用 `[a-z-[m-p]]`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-602">To define the set of characters that consists of the base group except for the character range from "m" through "p", use `[a-z-[m-p]]`.</span></span>  
  
 <span data-ttu-id="79ebf-603">可考虑使用嵌套字符类减法表达式 `[a-z-[d-w-[m-o]]]`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-603">Consider the nested character class subtraction expression, `[a-z-[d-w-[m-o]]]`.</span></span> <span data-ttu-id="79ebf-604">该表达式由最里面的字符范围向外计算。</span><span class="sxs-lookup"><span data-stu-id="79ebf-604">The expression is evaluated from the innermost character range outward.</span></span> <span data-ttu-id="79ebf-605">首先，在从“d”至“w”的字符范围中减去从“m”至“o”的字符范围，这将产生从“d”至“l”和从“p”至“w”的字符集。</span><span class="sxs-lookup"><span data-stu-id="79ebf-605">First, the character range from "m" through "o" is subtracted from the character range "d" through "w", which yields the set of characters from "d" through "l" and "p" through "w".</span></span> <span data-ttu-id="79ebf-606">然后，在从“a”至“z”的字符范围中减去该集合，这将产生字符集 `[abcmnoxyz]`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-606">That set is then subtracted from the character range from "a" through "z", which yields the set of characters `[abcmnoxyz]`.</span></span>  
  
 <span data-ttu-id="79ebf-607">可以将任何字符类用于字符类减法。</span><span class="sxs-lookup"><span data-stu-id="79ebf-607">You can use any character class with character class subtraction.</span></span> <span data-ttu-id="79ebf-608">若要定义字符集，且该字符集包括除空白字符 (`\s`)、标点通用类别中的字符 (`\p{P}`)、`IsGreek` 命名块中的字符 (`\p{IsGreek}`) 以及 Unicode NEXT LINE 控制字符 (\x85) 之外的所有从 \u0000 至 \uFFFF 的 Unicode 字符，请使用 `[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]`。</span><span class="sxs-lookup"><span data-stu-id="79ebf-608">To define the set of characters that consists of all Unicode characters from \u0000 through \uFFFF except white-space characters (`\s`), the characters in the punctuation general category (`\p{P}`), the characters in the `IsGreek` named block (`\p{IsGreek}`), and the Unicode NEXT LINE control character (\x85), use `[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]`.</span></span>  
  
 <span data-ttu-id="79ebf-609">为字符类减法表达式选择将会产生有用结果的字符类。</span><span class="sxs-lookup"><span data-stu-id="79ebf-609">Choose character classes for a character class subtraction expression that will yield useful results.</span></span> <span data-ttu-id="79ebf-610">避免使用产生空字符集的表达式，这将无法匹配任何内容，同时避免使用等效于初始基本组的表达式。</span><span class="sxs-lookup"><span data-stu-id="79ebf-610">Avoid an expression that yields an empty set of characters, which cannot match anything, or an expression that is equivalent to the original base group.</span></span> <span data-ttu-id="79ebf-611">例如，表达式 `[\p{IsBasicLatin}-[\x00-\x7F]]` 从 `IsBasicLatin` 常规类别中减去 `IsBasicLatin` 字符范围内的所有字符，其结果为空集合。</span><span class="sxs-lookup"><span data-stu-id="79ebf-611">For example, the empty set is the result of the expression `[\p{IsBasicLatin}-[\x00-\x7F]]`, which subtracts all characters in the `IsBasicLatin` character range from the `IsBasicLatin` general category.</span></span> <span data-ttu-id="79ebf-612">类似地，表达式 `[a-z-[0-9]]` 的结果为初始基本组。</span><span class="sxs-lookup"><span data-stu-id="79ebf-612">Similarly, the original base group is the result of the expression `[a-z-[0-9]]`.</span></span>  <span data-ttu-id="79ebf-613">这是因为，基本组（它是从“a”至“z”的字母组成的字符范围）不包含排除组（它是从“0”至“9”的十进制数组成的字符范围）中的任何字符。</span><span class="sxs-lookup"><span data-stu-id="79ebf-613">This is because the base group, which is the character range of letters from "a" through "z", does not contain any characters in the excluded group, which is the character range of decimal digits from "0" through "9".</span></span>  
  
 <span data-ttu-id="79ebf-614">下面的示例定义正则表达式 `^[0-9-[2468]]+$`，该表达式匹配输入字符串中的零和奇数。</span><span class="sxs-lookup"><span data-stu-id="79ebf-614">The following example defines a regular expression, `^[0-9-[2468]]+$`, that matches zero and odd digits in an input string.</span></span>  <span data-ttu-id="79ebf-615">正则表达式模式可以解释为下表中所示内容。</span><span class="sxs-lookup"><span data-stu-id="79ebf-615">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="79ebf-616">元素</span><span class="sxs-lookup"><span data-stu-id="79ebf-616">Element</span></span>|<span data-ttu-id="79ebf-617">描述</span><span class="sxs-lookup"><span data-stu-id="79ebf-617">Description</span></span>|  
|-------------|-----------------|  
|^|<span data-ttu-id="79ebf-618">从输入字符串的开头处开始进行匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-618">Begin the match at the start of the input string.</span></span>|  
|`[0-9-[2468]]+`|<span data-ttu-id="79ebf-619">匹配任意字符（从 0 到 9，除了 2、4、6 和 8 之外）的一个或多个匹配项。</span><span class="sxs-lookup"><span data-stu-id="79ebf-619">Match one or more occurrences of any character from 0 to 9 except for 2, 4, 6, and 8.</span></span> <span data-ttu-id="79ebf-620">换句话说，匹配零或奇数的一个或多个匹配项。</span><span class="sxs-lookup"><span data-stu-id="79ebf-620">In other words, match one or more occurrences of zero or an odd digit.</span></span>|  
|$|<span data-ttu-id="79ebf-621">在输入字符串末尾结束匹配。</span><span class="sxs-lookup"><span data-stu-id="79ebf-621">End the match at the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/classsubtraction1.cs#15)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/classsubtraction1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="79ebf-622">请参阅</span><span class="sxs-lookup"><span data-stu-id="79ebf-622">See Also</span></span>  
 <xref:System.Char.GetUnicodeCategory%2A>  
 [<span data-ttu-id="79ebf-623">正则表达式语言 - 快速参考</span><span class="sxs-lookup"><span data-stu-id="79ebf-623">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 [<span data-ttu-id="79ebf-624">正则表达式选项</span><span class="sxs-lookup"><span data-stu-id="79ebf-624">Regular Expression Options</span></span>](../../../docs/standard/base-types/regular-expression-options.md)
