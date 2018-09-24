---
title: 正则表达式中的字符转义
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unescaped characters
- replacement patterns
- characters, escapes
- regular expressions, character escapes
- escape characters
- .NET Framework regular expressions, character escapes
- constructs, character escapes
ms.assetid: f49cc9cc-db7d-4058-8b8a-422bc08b29b0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b390b1d3d935ad045d59dd6b3d2e42cdbe82dd7
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46583845"
---
# <a name="character-escapes-in-regular-expressions"></a><span data-ttu-id="5ed06-102">正则表达式中的字符转义</span><span class="sxs-lookup"><span data-stu-id="5ed06-102">Character Escapes in Regular Expressions</span></span>
<span data-ttu-id="5ed06-103">正则表达式中的反斜杠 (\\) 指示以下值之一：</span><span class="sxs-lookup"><span data-stu-id="5ed06-103">The backslash (\\) in a regular expression indicates one of the following:</span></span>  
  
-   <span data-ttu-id="5ed06-104">后接字符为特殊字符，如下节表中所示。</span><span class="sxs-lookup"><span data-stu-id="5ed06-104">The character that follows it is a special character, as shown in the table in the following section.</span></span> <span data-ttu-id="5ed06-105">例如，`\b` 是指示正则表达式匹配应从单词边界开始的定位点，`\t` 表示制表符，而 `\x020` 表示空间。</span><span class="sxs-lookup"><span data-stu-id="5ed06-105">For example, `\b` is an anchor that indicates that a regular expression match should begin on a word boundary, `\t` represents a tab, and `\x020` represents a space.</span></span>  
  
-   <span data-ttu-id="5ed06-106">本应解释为未转义语言构造的字符应按字面意思进行解释。</span><span class="sxs-lookup"><span data-stu-id="5ed06-106">A character that otherwise would be interpreted as an unescaped language construct should be interpreted literally.</span></span> <span data-ttu-id="5ed06-107">例如，大括号 (`{`) 开始定义限定符，而反斜杠后接大括号 (`\{`) 表示正则表达式引擎应匹配大括号。</span><span class="sxs-lookup"><span data-stu-id="5ed06-107">For example, a brace (`{`) begins the definition of a quantifier, but a backslash followed by a brace (`\{`) indicates that the regular expression engine should match the brace.</span></span> <span data-ttu-id="5ed06-108">同样，单个反斜杠标记转义的语言构造的开始，而两个反斜杠 (`\\`) 表示正则表达式引擎应匹配反斜杠。</span><span class="sxs-lookup"><span data-stu-id="5ed06-108">Similarly, a single backslash marks the beginning of an escaped language construct, but two backslashes (`\\`) indicate that the regular expression engine should match the backslash.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ed06-109">字符转义可在正则表达式模式中识别，但无法在替换模式中识别。</span><span class="sxs-lookup"><span data-stu-id="5ed06-109">Character escapes are recognized in regular expression patterns but not in replacement patterns.</span></span>  
  
## <a name="character-escapes-in-net"></a><span data-ttu-id="5ed06-110">.NET 中的字符转义</span><span class="sxs-lookup"><span data-stu-id="5ed06-110">Character Escapes in .NET</span></span>  
 <span data-ttu-id="5ed06-111">下表列出了 .NET 中正则表达式支持的字符转义。</span><span class="sxs-lookup"><span data-stu-id="5ed06-111">The following table lists the character escapes supported by regular expressions in .NET.</span></span>  
  
|<span data-ttu-id="5ed06-112">字符或序列</span><span class="sxs-lookup"><span data-stu-id="5ed06-112">Character or sequence</span></span>|<span data-ttu-id="5ed06-113">描述</span><span class="sxs-lookup"><span data-stu-id="5ed06-113">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="5ed06-114">除以下字符外的所有字符：</span><span class="sxs-lookup"><span data-stu-id="5ed06-114">All characters except for the following:</span></span><br /><br /> <span data-ttu-id="5ed06-115">.</span><span class="sxs-lookup"><span data-stu-id="5ed06-115">.</span></span> <span data-ttu-id="5ed06-116">$ ^ { [ ( &#124; ) \* + ?</span><span class="sxs-lookup"><span data-stu-id="5ed06-116">$ ^ { [ ( &#124; ) \* + ?</span></span> \ |<span data-ttu-id="5ed06-117">“字符或序列”列中未包含的字符在正则表达式中没有特殊含义；此类字符与自身匹配。</span><span class="sxs-lookup"><span data-stu-id="5ed06-117">Characters other than those listed in the **Character or sequence** column have no special meaning in regular expressions; they match themselves.</span></span><br /><br /> <span data-ttu-id="5ed06-118">“字符或序列”列中包括的字符均为特殊的正则表达式语言元素。</span><span class="sxs-lookup"><span data-stu-id="5ed06-118">The characters included in the **Character or sequence** column are special regular expression language elements.</span></span> <span data-ttu-id="5ed06-119">若要在正则表达式中匹配这些字符，必须将其转义或纳入[正字符组](../../../docs/standard/base-types/character-classes-in-regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="5ed06-119">To match them in a regular expression, they must be escaped or included in a [positive character group](../../../docs/standard/base-types/character-classes-in-regular-expressions.md).</span></span> <span data-ttu-id="5ed06-120">例如，正则表达式 `\$\d+` 或 `[$]\d+` 匹配“$1200”。</span><span class="sxs-lookup"><span data-stu-id="5ed06-120">For example, the regular expression `\$\d+` or `[$]\d+` matches "$1200".</span></span>|  
|`\a`|<span data-ttu-id="5ed06-121">匹配响铃（警报）字符，`\u0007`。</span><span class="sxs-lookup"><span data-stu-id="5ed06-121">Matches a bell (alarm) character, `\u0007`.</span></span>|  
|`\b`|<span data-ttu-id="5ed06-122">在 `[`character_group`]` 字符类中，匹配退格，`\u0008`。</span><span class="sxs-lookup"><span data-stu-id="5ed06-122">In a `[`*character_group*`]` character class, matches a backspace, `\u0008`.</span></span>  <span data-ttu-id="5ed06-123">（请参阅[字符类](../../../docs/standard/base-types/character-classes-in-regular-expressions.md)。）在字符类之外，`\b` 是匹配字边界的定位点。</span><span class="sxs-lookup"><span data-stu-id="5ed06-123">(See [Character Classes](../../../docs/standard/base-types/character-classes-in-regular-expressions.md).) Outside a character class, `\b` is an anchor that matches a word boundary.</span></span> <span data-ttu-id="5ed06-124">（请参阅[定位标记](../../../docs/standard/base-types/anchors-in-regular-expressions.md)）</span><span class="sxs-lookup"><span data-stu-id="5ed06-124">(See [Anchors](../../../docs/standard/base-types/anchors-in-regular-expressions.md).)</span></span>|  
|`\t`|<span data-ttu-id="5ed06-125">匹配制表符，`\u0009`。</span><span class="sxs-lookup"><span data-stu-id="5ed06-125">Matches a tab, `\u0009`.</span></span>|  
|`\r`|<span data-ttu-id="5ed06-126">匹配回车，`\u000D`。</span><span class="sxs-lookup"><span data-stu-id="5ed06-126">Matches a carriage return, `\u000D`.</span></span> <span data-ttu-id="5ed06-127">请注意，`\r` 不等同于换行符，`\n`。</span><span class="sxs-lookup"><span data-stu-id="5ed06-127">Note that `\r` is not equivalent to the newline character, `\n`.</span></span>|  
|`\v`|<span data-ttu-id="5ed06-128">匹配垂直制表符，`\u000B`。</span><span class="sxs-lookup"><span data-stu-id="5ed06-128">Matches a vertical tab, `\u000B`.</span></span>|  
|`\f`|<span data-ttu-id="5ed06-129">匹配换页，`\u000C`。</span><span class="sxs-lookup"><span data-stu-id="5ed06-129">Matches a form feed, `\u000C`.</span></span>|  
|`\n`|<span data-ttu-id="5ed06-130">匹配换行，`\u000A`。</span><span class="sxs-lookup"><span data-stu-id="5ed06-130">Matches a new line, `\u000A`.</span></span>|  
|`\e`|<span data-ttu-id="5ed06-131">匹配转义，`\u001B`。</span><span class="sxs-lookup"><span data-stu-id="5ed06-131">Matches an escape, `\u001B`.</span></span>|  
|<span data-ttu-id="5ed06-132">`\` *nnn*</span><span class="sxs-lookup"><span data-stu-id="5ed06-132">`\` *nnn*</span></span>|<span data-ttu-id="5ed06-133">匹配 ASCII 字符，其中 nnn 包含表示八进制字符代码的两位数或三位数。</span><span class="sxs-lookup"><span data-stu-id="5ed06-133">Matches an ASCII character, where *nnn* consists of two or three digits that represent the octal character code.</span></span> <span data-ttu-id="5ed06-134">例如，`\040` 表示空格字符。</span><span class="sxs-lookup"><span data-stu-id="5ed06-134">For example, `\040` represents a space character.</span></span> <span data-ttu-id="5ed06-135">如果此构造仅包含一个数字（如 `\2`）或者它对应捕获组的编号，则将它解释为向后引用。</span><span class="sxs-lookup"><span data-stu-id="5ed06-135">This construct is interpreted as a backreference if it has only one digit (for example, `\2`) or if it corresponds to the number of a capturing group.</span></span> <span data-ttu-id="5ed06-136">（请参阅[向后引用构造](../../../docs/standard/base-types/backreference-constructs-in-regular-expressions.md)。）</span><span class="sxs-lookup"><span data-stu-id="5ed06-136">(See [Backreference Constructs](../../../docs/standard/base-types/backreference-constructs-in-regular-expressions.md).)</span></span>|  
|<span data-ttu-id="5ed06-137">`\x` nn</span><span class="sxs-lookup"><span data-stu-id="5ed06-137">`\x` *nn*</span></span>|<span data-ttu-id="5ed06-138">匹配 ASCII 字符，其中 nn 是两位数的十六进制字符代码。</span><span class="sxs-lookup"><span data-stu-id="5ed06-138">Matches an ASCII character, where *nn* is a two-digit hexadecimal character code.</span></span>|  
|<span data-ttu-id="5ed06-139">`\c` X</span><span class="sxs-lookup"><span data-stu-id="5ed06-139">`\c` *X*</span></span>|<span data-ttu-id="5ed06-140">匹配 ASCII 控制字符，其中 X 是控制字符的字母。</span><span class="sxs-lookup"><span data-stu-id="5ed06-140">Matches an ASCII control character, where X is the letter of the control character.</span></span> <span data-ttu-id="5ed06-141">例如，`\cC` 为 CTRL-C。</span><span class="sxs-lookup"><span data-stu-id="5ed06-141">For example, `\cC` is CTRL-C.</span></span>|  
|<span data-ttu-id="5ed06-142">`\u` nnnn</span><span class="sxs-lookup"><span data-stu-id="5ed06-142">`\u` *nnnn*</span></span>|<span data-ttu-id="5ed06-143">匹配的 UTF-16 代码单元，单元值是 nnnn 十六进制。</span><span class="sxs-lookup"><span data-stu-id="5ed06-143">Matches a UTF-16 code unit whose value is *nnnn* hexadecimal.</span></span> <span data-ttu-id="5ed06-144">**注意：**.NET 不支持用于指定 Unicode 的 Perl 5 字符转义。</span><span class="sxs-lookup"><span data-stu-id="5ed06-144">**Note:**  The Perl 5 character escape that is used to specify Unicode is not supported by .NET.</span></span> <span data-ttu-id="5ed06-145">Perl 5 字符转义采用以下格式 `\x{`####`…}`，其中 ####`…` 是一系列十六进制数字。</span><span class="sxs-lookup"><span data-stu-id="5ed06-145">The Perl 5 character escape has the form `\x{`*####*`…}`, where *####*`…` is a series of hexadecimal digits.</span></span> <span data-ttu-id="5ed06-146">改用 `\u`nnnn。</span><span class="sxs-lookup"><span data-stu-id="5ed06-146">Instead, use `\u`*nnnn*.</span></span>|  
|`\`|<span data-ttu-id="5ed06-147">后接字符未识别为转义字符时，将匹配此字符。</span><span class="sxs-lookup"><span data-stu-id="5ed06-147">When followed by a character that is not recognized as an escaped character, matches that character.</span></span> <span data-ttu-id="5ed06-148">例如，`\*` 匹配星号 (\*) 并等同于 `\x2A`。</span><span class="sxs-lookup"><span data-stu-id="5ed06-148">For example, `\*` matches an asterisk (\*) and is the same as `\x2A`.</span></span>|  
  
## <a name="an-example"></a><span data-ttu-id="5ed06-149">示例</span><span class="sxs-lookup"><span data-stu-id="5ed06-149">An Example</span></span>  
 <span data-ttu-id="5ed06-150">以下示例说明了如何使用正则表达式中的字符转义。</span><span class="sxs-lookup"><span data-stu-id="5ed06-150">The following example illustrates the use of character escapes in a regular expression.</span></span> <span data-ttu-id="5ed06-151">分析了包含 2009 年世界上最大城市的名称及其人口的字符串。</span><span class="sxs-lookup"><span data-stu-id="5ed06-151">It parses a string that contains the names of the world's largest cities and their populations in 2009.</span></span> <span data-ttu-id="5ed06-152">使用制表符 (`\t`) 或垂直条（&#124; 或 `\u007c`）将每个城市名与其人口数量分开。</span><span class="sxs-lookup"><span data-stu-id="5ed06-152">Each city name is separated from its population by a tab (`\t`) or a vertical bar (&#124; or `\u007c`).</span></span> <span data-ttu-id="5ed06-153">使用回车符和换行符分隔各个城市及其人口。</span><span class="sxs-lookup"><span data-stu-id="5ed06-153">Individual cities and their populations are separated from each other by a carriage return and line feed.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Escapes#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.escapes/cs/escape1.cs#1)]
 [!code-vb[RegularExpressions.Language.Escapes#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.escapes/vb/escape1.vb#1)]  
  
 <span data-ttu-id="5ed06-154">正则表达式 `\G(.+)[\t|\u007c](.+)\r?\n` 可以解释为下表中所示内容。</span><span class="sxs-lookup"><span data-stu-id="5ed06-154">The regular expression `\G(.+)[\t|\u007c](.+)\r?\n` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="5ed06-155">模式</span><span class="sxs-lookup"><span data-stu-id="5ed06-155">Pattern</span></span>|<span data-ttu-id="5ed06-156">描述</span><span class="sxs-lookup"><span data-stu-id="5ed06-156">Description</span></span>|  
|-------------|-----------------|  
|`\G`|<span data-ttu-id="5ed06-157">从上次匹配结束处开始匹配。</span><span class="sxs-lookup"><span data-stu-id="5ed06-157">Begin the match where the last match ended.</span></span>|  
|`(.+)`|<span data-ttu-id="5ed06-158">一次或多次匹配任何字符。</span><span class="sxs-lookup"><span data-stu-id="5ed06-158">Match any character one or more times.</span></span> <span data-ttu-id="5ed06-159">这是第一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="5ed06-159">This is the first capturing group.</span></span>|  
|`[\t\u007c]`|<span data-ttu-id="5ed06-160">匹配制表符 (`\t`) 或垂直条 (&#124;)。</span><span class="sxs-lookup"><span data-stu-id="5ed06-160">Match a tab (`\t`) or a vertical bar (&#124;).</span></span>|  
|`(.+)`|<span data-ttu-id="5ed06-161">一次或多次匹配任何字符。</span><span class="sxs-lookup"><span data-stu-id="5ed06-161">Match any character one or more times.</span></span> <span data-ttu-id="5ed06-162">这是第二个捕获组。</span><span class="sxs-lookup"><span data-stu-id="5ed06-162">This is the second capturing group.</span></span>|  
|`\r?\n`|<span data-ttu-id="5ed06-163">匹配零或一个出现回车符后接新行的次数。</span><span class="sxs-lookup"><span data-stu-id="5ed06-163">Match zero or one occurrence of a carriage return followed by a new line.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ed06-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ed06-164">See also</span></span>

- [<span data-ttu-id="5ed06-165">正则表达式语言 - 快速参考</span><span class="sxs-lookup"><span data-stu-id="5ed06-165">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
