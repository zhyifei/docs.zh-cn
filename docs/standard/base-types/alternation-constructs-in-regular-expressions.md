---
title: "正则表达式中的备用构造"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- either/or matching
- alternative matching patterns
- regular expressions, alternation constructs
- alternation constructs
- optional matching patterns
- constructs, alternation
- .NET Framework regular expressions, alternation constructs
ms.assetid: 071e22e9-fbb0-4ecf-add1-8d2424f9f2d1
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8e565d029096b88d304b9cfc241807084873e735
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="alternation-constructs-in-regular-expressions"></a><span data-ttu-id="33db2-102">正则表达式中的备用构造</span><span class="sxs-lookup"><span data-stu-id="33db2-102">Alternation Constructs in Regular Expressions</span></span>
<a name="top"></a> <span data-ttu-id="33db2-103">替换构造可修改正则表达式以启用 either/or 或条件匹配。</span><span class="sxs-lookup"><span data-stu-id="33db2-103">Alternation constructs modify a regular expression to enable either/or or conditional matching.</span></span> <span data-ttu-id="33db2-104">.NET 支持三种备用构造：</span><span class="sxs-lookup"><span data-stu-id="33db2-104">.NET supports three alternation constructs:</span></span>  
  
-   [<span data-ttu-id="33db2-105">利用 &#124; 的模式匹配</span><span class="sxs-lookup"><span data-stu-id="33db2-105">Pattern matching with &#124;</span></span>](#Either_Or)  
  
-   [<span data-ttu-id="33db2-106">利用 (?(expression)yes&#124;no) 的条件匹配</span><span class="sxs-lookup"><span data-stu-id="33db2-106">Conditional matching with (?(expression)yes&#124;no)</span></span>](#Conditional_Expr)  
  
-   [<span data-ttu-id="33db2-107">基于有效的捕获组的条件匹配</span><span class="sxs-lookup"><span data-stu-id="33db2-107">Conditional matching based on a valid captured group</span></span>](#Conditional_Group)  
  
<a name="Either_Or"></a>   
## <a name="pattern-matching-with-124"></a><span data-ttu-id="33db2-108">利用 &#124; 的模式匹配</span><span class="sxs-lookup"><span data-stu-id="33db2-108">Pattern Matching with &#124;</span></span>  
 <span data-ttu-id="33db2-109">可以使用竖线 (`|`) 字符匹配一系列模式中的任何一种模式，其中 `|` 字符用于分隔每个模式。</span><span class="sxs-lookup"><span data-stu-id="33db2-109">You can use the vertical bar (`|`) character to match any one of a series of patterns, where the `|` character separates each pattern.</span></span>  
  
 <span data-ttu-id="33db2-110">与正向字符集一样， `|` 字符可用于匹配多个字符中的任意一个字符。</span><span class="sxs-lookup"><span data-stu-id="33db2-110">Like the positive character class, the `|` character can be used to match any one of a number of single characters.</span></span> <span data-ttu-id="33db2-111">以下示例使用正向字符集和 either/or 模式匹配（使用 `|` 字符）查找字符串中单词“gray”或“grey”的匹配项。</span><span class="sxs-lookup"><span data-stu-id="33db2-111">The following example uses both a positive character class and either/or pattern matching with the `|` character to locate occurrences of the words "gray" or "grey" in a string.</span></span> <span data-ttu-id="33db2-112">在该示例中， `|` 字符生成了更为详细的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="33db2-112">In this case, the `|` character produces a regular expression that is more verbose.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation1.cs#1)]
 [!code-vb[RegularExpressions.Language.Alternation#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation1.vb#1)]  
  
 <span data-ttu-id="33db2-113">使用 `|` 字符的正则表达式 `\bgr(a|e)y\b`的解释如下表所示。</span><span class="sxs-lookup"><span data-stu-id="33db2-113">The regular expression that uses the `|` character, `\bgr(a|e)y\b`, is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="33db2-114">模式</span><span class="sxs-lookup"><span data-stu-id="33db2-114">Pattern</span></span>|<span data-ttu-id="33db2-115">描述</span><span class="sxs-lookup"><span data-stu-id="33db2-115">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="33db2-116">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="33db2-116">Start at a word boundary.</span></span>|  
|`gr`|<span data-ttu-id="33db2-117">匹配字符“gr”。</span><span class="sxs-lookup"><span data-stu-id="33db2-117">Match the characters "gr".</span></span>|  
|<code>(a&#124;e)</code>|<span data-ttu-id="33db2-118">匹配“a”或“e”。</span><span class="sxs-lookup"><span data-stu-id="33db2-118">Match either an "a" or an "e".</span></span>|  
|`y\b`|<span data-ttu-id="33db2-119">匹配单词边界中的“y”。</span><span class="sxs-lookup"><span data-stu-id="33db2-119">Match a "y" on a word boundary.</span></span>|  
  
 <span data-ttu-id="33db2-120">还可以使用 `|` 字符执行具有多个字符或子表达式（包含任意组合的字符常量和正则表达式语言元素）的 either/or 匹配。</span><span class="sxs-lookup"><span data-stu-id="33db2-120">The `|` character can also be used to perform an either/or match with multiple characters or subexpressions, which can include any combination of character literals and regular expression language elements.</span></span> <span data-ttu-id="33db2-121">（字符类不提供此功能。）下面的示例使用 `|` 字符提取美国社会安全号码 (SSN)（格式为 ddd-dd-dddd 的 9 位数字），或美国雇主标识号 (EIN)（格式为 dd-ddddddd 的 9 位数字）。</span><span class="sxs-lookup"><span data-stu-id="33db2-121">(The character class does not provide this functionality.) The following example uses the `|` character to extract either a U.S. Social Security Number (SSN), which is a 9-digit number with the format *ddd*-*dd*-*dddd*, or a U.S. Employer Identification Number (EIN), which is a 9-digit number with the format *dd*-*ddddddd*.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation2.cs#2)]
 [!code-vb[RegularExpressions.Language.Alternation#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation2.vb#2)]  
  
 <span data-ttu-id="33db2-122">正则表达式 `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` 可以解释为下表中所示内容。</span><span class="sxs-lookup"><span data-stu-id="33db2-122">The regular expression `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="33db2-123">模式</span><span class="sxs-lookup"><span data-stu-id="33db2-123">Pattern</span></span>|<span data-ttu-id="33db2-124">描述</span><span class="sxs-lookup"><span data-stu-id="33db2-124">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="33db2-125">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="33db2-125">Start at a word boundary.</span></span>|  
|<code>(\d{2}-\d{7}&#124;\d{3}-\d{2}-\d{4})</code>|<span data-ttu-id="33db2-126">匹配以下其中一个内容：连字符连接的两个十进制数字和七个十进制数字；或三个十进制数字后接连字符，后接两个十进制数字，后接另一个连字符，然后再接四个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="33db2-126">Match either of the following: two decimal digits followed by a hyphen followed by seven decimal digits; or three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\d`|<span data-ttu-id="33db2-127">在单词边界处结束匹配。</span><span class="sxs-lookup"><span data-stu-id="33db2-127">End the match at a word boundary.</span></span>|  
  
 [<span data-ttu-id="33db2-128">返回页首</span><span class="sxs-lookup"><span data-stu-id="33db2-128">Back to top</span></span>](#top)  
  
<a name="Conditional_Expr"></a>   
## <a name="conditional-matching-with-an-expression"></a><span data-ttu-id="33db2-129">条件匹配的表达式</span><span class="sxs-lookup"><span data-stu-id="33db2-129">Conditional Matching with an Expression</span></span>  
 <span data-ttu-id="33db2-130">此语言元素尝试根据是否可以匹配初始模式来匹配两种模式之一。</span><span class="sxs-lookup"><span data-stu-id="33db2-130">This language element attempts to match one of two patterns depending on whether it can match an initial pattern.</span></span> <span data-ttu-id="33db2-131">语法为：</span><span class="sxs-lookup"><span data-stu-id="33db2-131">Its syntax is:</span></span>  
  
 <span data-ttu-id="33db2-132">`(?(`expression`)`yes`|`no`)`</span><span class="sxs-lookup"><span data-stu-id="33db2-132">`(?(` *expression* `)` *yes* `|` *no* `)`</span></span>  
  
 <span data-ttu-id="33db2-133">其中， *expression* 是要匹配的初始模式， *yes* 是当匹配 *expression* 时要匹配的模式，而 *no* 是未匹配 *expression* 时要匹配的可选模式。</span><span class="sxs-lookup"><span data-stu-id="33db2-133">where *expression* is the initial pattern to match, *yes* is the pattern to match if *expression* is matched, and *no* is the optional pattern to match if *expression* is not matched.</span></span> <span data-ttu-id="33db2-134">正则表达式引擎将 *expression* 视为一个宽度为零的断言；也就是说，正则表达式引擎在计算 *expression*之后，不再处理输入流的后续数据。</span><span class="sxs-lookup"><span data-stu-id="33db2-134">The regular expression engine treats *expression* as a zero-width assertion; that is, the regular expression engine does not advance in the input stream after it evaluates *expression*.</span></span> <span data-ttu-id="33db2-135">因此，该构造是等效于以下语法：</span><span class="sxs-lookup"><span data-stu-id="33db2-135">Therefore, this construct is equivalent to the following:</span></span>  
  
 <span data-ttu-id="33db2-136">`(?(?=` *表达式* `)` *是* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="33db2-136">`(?(?=` *expression* `)` *yes* `|` *no* `)`</span></span>  
  
 <span data-ttu-id="33db2-137">其中 `(?=`expression`)` 是宽度为零的断言构造。</span><span class="sxs-lookup"><span data-stu-id="33db2-137">where `(?=`*expression*`)` is a zero-width assertion construct.</span></span> <span data-ttu-id="33db2-138">（有关详细信息，请参阅[分组构造](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)。）由于正则表达式引擎将 expression 解释为定位点（零宽断言），因此 expression 必须是零宽断言（有关详细信息，请参阅[定位标记](../../../docs/standard/base-types/anchors-in-regular-expressions.md)），或者是也包含在 yes 中的子表达式。</span><span class="sxs-lookup"><span data-stu-id="33db2-138">(For more information, see [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).) Because the regular expression engine interprets *expression* as an anchor (a zero-width assertion), *expression* must either be a zero-width assertion (for more information, see [Anchors](../../../docs/standard/base-types/anchors-in-regular-expressions.md)) or a subexpression that is also contained in *yes*.</span></span> <span data-ttu-id="33db2-139">否则，无法匹配 *yes* 模式。</span><span class="sxs-lookup"><span data-stu-id="33db2-139">Otherwise, the *yes* pattern cannot be matched.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33db2-140">如果 *expression*是命名捕获组或带编号的捕获组，则替换构造将被解释为捕获测试；有关详细信息，请参阅下一节 [基于有效捕获组的条件匹配](#Conditional_Group)。</span><span class="sxs-lookup"><span data-stu-id="33db2-140">If *expression*is a named or numbered capturing group, the alternation construct is interpreted as a capture test; for more information, see the next section, [Conditional Matching Based on a Valid Capture Group](#Conditional_Group).</span></span> <span data-ttu-id="33db2-141">换而言之，正则表达式引擎不会尝试匹配捕获的子字符串，而是测试该组是否存在。</span><span class="sxs-lookup"><span data-stu-id="33db2-141">In other words, the regular expression engine does not attempt to match the captured substring, but instead tests for the presence or absence of the group.</span></span>  
  
 <span data-ttu-id="33db2-142">下面的示例是[利用 &#124; 的 Either/Or 模式匹配](#Either_Or)一节中的示例变体。</span><span class="sxs-lookup"><span data-stu-id="33db2-142">The following example is a variation of the example that appears in the [Either/Or Pattern Matching with &#124;](#Either_Or) section.</span></span> <span data-ttu-id="33db2-143">它使用条件匹配来确定单词边界之后的前三个字符是否是后接一个连字符的两个数字。</span><span class="sxs-lookup"><span data-stu-id="33db2-143">It uses conditional matching to determine whether the first three characters after a word boundary are two digits followed by a hyphen.</span></span> <span data-ttu-id="33db2-144">如果是，则将尝试匹配美国雇主标识号 (EIN)。</span><span class="sxs-lookup"><span data-stu-id="33db2-144">If they are, it attempts to match a U.S. Employer Identification Number (EIN).</span></span> <span data-ttu-id="33db2-145">如果不是，则将尝试匹配美国社会保障号 (SSN)。</span><span class="sxs-lookup"><span data-stu-id="33db2-145">If not, it attempts to match a U.S. Social Security Number (SSN).</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation3.cs#3)]
 [!code-vb[RegularExpressions.Language.Alternation#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation3.vb#3)]  
  
 <span data-ttu-id="33db2-146">正则表达式模式 `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` 的含义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="33db2-146">The regular expression pattern `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="33db2-147">模式</span><span class="sxs-lookup"><span data-stu-id="33db2-147">Pattern</span></span>|<span data-ttu-id="33db2-148">描述</span><span class="sxs-lookup"><span data-stu-id="33db2-148">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="33db2-149">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="33db2-149">Start at a word boundary.</span></span>|  
|`(?(\d{2}-)`|<span data-ttu-id="33db2-150">确定接下来的三个字符是否由两个数字后接一个连字符组成。</span><span class="sxs-lookup"><span data-stu-id="33db2-150">Determine whether the next three characters consist of two digits followed by a hyphen.</span></span>|  
|`\d{2}-\d{7}`|<span data-ttu-id="33db2-151">如果前面的模式匹配，则匹配后接一个连字符和七个数字的两个数字。</span><span class="sxs-lookup"><span data-stu-id="33db2-151">If the previous pattern matches, match two digits followed by a hyphen followed by seven digits.</span></span>|  
|`\d{3}-\d{2}-\d{4}`|<span data-ttu-id="33db2-152">如果前面的模式不匹配，则匹配三个十进制数字，后接一个连字符，再接两个十进制数字，再接另一个连字符，再接四个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="33db2-152">If the previous pattern does not match, match three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="33db2-153">与字边界匹配。</span><span class="sxs-lookup"><span data-stu-id="33db2-153">Match a word boundary.</span></span>|  
  
 [<span data-ttu-id="33db2-154">返回页首</span><span class="sxs-lookup"><span data-stu-id="33db2-154">Back to top</span></span>](#top)  
  
<a name="Conditional_Group"></a>   
## <a name="conditional-matching-based-on-a-valid-captured-group"></a><span data-ttu-id="33db2-155">基于有效的捕获组的条件匹配</span><span class="sxs-lookup"><span data-stu-id="33db2-155">Conditional Matching Based on a Valid Captured Group</span></span>  
 <span data-ttu-id="33db2-156">此语言元素尝试根据是否已经匹配指定的捕获组来匹配两种模式之一。</span><span class="sxs-lookup"><span data-stu-id="33db2-156">This language element attempts to match one of two patterns depending on whether it has matched a specified capturing group.</span></span> <span data-ttu-id="33db2-157">语法为：</span><span class="sxs-lookup"><span data-stu-id="33db2-157">Its syntax is:</span></span>  
  
 <span data-ttu-id="33db2-158">`(?(` *name* `)` *是* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="33db2-158">`(?(` *name* `)` *yes* `|` *no* `)`</span></span>  
  
 <span data-ttu-id="33db2-159">或</span><span class="sxs-lookup"><span data-stu-id="33db2-159">or</span></span>  
  
 <span data-ttu-id="33db2-160">`(?(` *数值* `)` *是* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="33db2-160">`(?(` *number* `)` *yes* `|` *no* `)`</span></span>  
  
 <span data-ttu-id="33db2-161">其中， *name* 是捕获组的名称， *number* 是捕获组的编号； *yes* 是当 *name* 或 *number* 具有匹配项时要匹配的表达式； *no* 是当不具有匹配项时要匹配的可选表达式。</span><span class="sxs-lookup"><span data-stu-id="33db2-161">where *name* is the name and *number* is the number of a capturing group, *yes* is the expression to match if *name* or *number* has a match, and *no* is the optional expression to match if it does not.</span></span>  
  
 <span data-ttu-id="33db2-162">如果 *name* 与正则表达式模式中所用捕获组的名称不对应，则替换构造将解释为表达式测试，如上一节中所述。</span><span class="sxs-lookup"><span data-stu-id="33db2-162">If *name* does not correspond to the name of a capturing group that is used in the regular expression pattern, the alternation construct is interpreted as an expression test, as explained in the previous section.</span></span> <span data-ttu-id="33db2-163">通常，这意味着 *expression* 的计算结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="33db2-163">Typically, this means that *expression* evaluates to `false`.</span></span> <span data-ttu-id="33db2-164">如果 *number* 与正则表达式模式中所用带编号的捕获组不对应，则正则表达式引擎将引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="33db2-164">If *number* does not correspond to a numbered capturing group that is used in the regular expression pattern, the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="33db2-165">下面的示例是[利用 &#124; 的 Either/Or 模式匹配](#Either_Or)一节中的示例变体。</span><span class="sxs-lookup"><span data-stu-id="33db2-165">The following example is a variation of the example that appears in the [Either/Or Pattern Matching with &#124;](#Either_Or) section.</span></span> <span data-ttu-id="33db2-166">它使用一个名为 `n2` 的捕获组，其中包含两个数字，后接一个连字符。</span><span class="sxs-lookup"><span data-stu-id="33db2-166">It uses a capturing group named `n2` that consists of two digits followed by a hyphen.</span></span> <span data-ttu-id="33db2-167">替换构造测试此捕获组是否在输入字符串中找到匹配项。</span><span class="sxs-lookup"><span data-stu-id="33db2-167">The alternation construct tests whether this capturing group has been matched in the input string.</span></span> <span data-ttu-id="33db2-168">如果有匹配项，则替换构造会尝试匹配九位数的美国雇主标识号 (EIN)。</span><span class="sxs-lookup"><span data-stu-id="33db2-168">If it has, the alternation construct attempts to match the last seven digits of a nine-digit U.S. Employer Identification Number (EIN).</span></span> <span data-ttu-id="33db2-169">如果没有匹配项，则将尝试匹配九位数的美国社会保障号 (SSN)。</span><span class="sxs-lookup"><span data-stu-id="33db2-169">If it has not, it attempts to match a nine-digit U.S. Social Security Number (SSN).</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation4.cs#4)]
 [!code-vb[RegularExpressions.Language.Alternation#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation4.vb#4)]  
  
 <span data-ttu-id="33db2-170">正则表达式模式 `\b(?<n2>\d{2}-)*(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b` 的含义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="33db2-170">The regular expression pattern `\b(?<n2>\d{2}-)*(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="33db2-171">模式</span><span class="sxs-lookup"><span data-stu-id="33db2-171">Pattern</span></span>|<span data-ttu-id="33db2-172">描述</span><span class="sxs-lookup"><span data-stu-id="33db2-172">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="33db2-173">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="33db2-173">Start at a word boundary.</span></span>|  
|`(?<n2>\d{2}-)*`|<span data-ttu-id="33db2-174">匹配两个数字后接一个连字符的零或一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="33db2-174">Match zero or one occurrence of two digits followed by a hyphen.</span></span> <span data-ttu-id="33db2-175">命名此捕获组 `n2`。</span><span class="sxs-lookup"><span data-stu-id="33db2-175">Name this capturing group `n2`.</span></span>|  
|`(?(n2)`|<span data-ttu-id="33db2-176">测试输入字符串中是否有 `n2` 的匹配项。</span><span class="sxs-lookup"><span data-stu-id="33db2-176">Test whether `n2` was matched in the input string.</span></span>|  
|`)\d{7}`|<span data-ttu-id="33db2-177">如果找到 `n2` 的匹配项，则匹配 7 个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="33db2-177">If `n2` was matched, match seven decimal digits.</span></span>|  
|<code>&#124;\d{3}-\d{2}-\d{4}</code>|<span data-ttu-id="33db2-178">如果未找到 `n2` 的匹配项，则匹配 3 个十进制数字，后接一个连字符，再接 2 个十进制数字，再接另一个连字符，再接 4 个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="33db2-178">If `n2` was not matched, match three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="33db2-179">与字边界匹配。</span><span class="sxs-lookup"><span data-stu-id="33db2-179">Match a word boundary.</span></span>|  
  
 <span data-ttu-id="33db2-180">下面示例中显示此示例变体使用编号组而非命名组。</span><span class="sxs-lookup"><span data-stu-id="33db2-180">A variation of this example that uses a numbered group instead of a named group is shown in the following example.</span></span> <span data-ttu-id="33db2-181">正则表达式模式为 `\b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`。</span><span class="sxs-lookup"><span data-stu-id="33db2-181">Its regular expression pattern is `\b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation5.cs#5)]
 [!code-vb[RegularExpressions.Language.Alternation#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="33db2-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="33db2-182">See Also</span></span>  
 [<span data-ttu-id="33db2-183">正则表达式语言 - 快速参考</span><span class="sxs-lookup"><span data-stu-id="33db2-183">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
