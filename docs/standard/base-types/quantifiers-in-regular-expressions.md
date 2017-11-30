---
title: "正则表达式中的限定符"
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
- regular expressions, quantifiers
- metacharacters, quantifiers
- minimal matching quantifiers
- quantifiers in regular expressions
- .NET Framework regular expressions, quantifiers
- quantifiers
- lazy quantifiers
ms.assetid: 36b81212-6511-49ed-a8f1-ff080415312f
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab06aa0c331c8cbd4c8986cced29334046f30264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="quantifiers-in-regular-expressions"></a><span data-ttu-id="e1cb7-102">正则表达式中的限定符</span><span class="sxs-lookup"><span data-stu-id="e1cb7-102">Quantifiers in Regular Expressions</span></span>
<span data-ttu-id="e1cb7-103">限定符指定输入中必须存在字符、组或字符类的多少实例才能找到匹配项。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-103">Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found.</span></span>  <span data-ttu-id="e1cb7-104">下表列出了 .NET 支持的限定符。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-104">The following table lists the quantifiers supported by .NET.</span></span>  
  
|<span data-ttu-id="e1cb7-105">贪婪限定符</span><span class="sxs-lookup"><span data-stu-id="e1cb7-105">Greedy quantifier</span></span>|<span data-ttu-id="e1cb7-106">惰性限定符</span><span class="sxs-lookup"><span data-stu-id="e1cb7-106">Lazy quantifier</span></span>|<span data-ttu-id="e1cb7-107">描述</span><span class="sxs-lookup"><span data-stu-id="e1cb7-107">Description</span></span>|  
|-----------------------|---------------------|-----------------|  
|`*`|`*?`|<span data-ttu-id="e1cb7-108">匹配零次或多次。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-108">Match zero or more times.</span></span>|  
|`+`|`+?`|<span data-ttu-id="e1cb7-109">匹配一次或多次。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-109">Match one or more times.</span></span>|  
|`?`|`??`|<span data-ttu-id="e1cb7-110">匹配零次或一次。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-110">Match zero or one time.</span></span>|  
|<span data-ttu-id="e1cb7-111">`{` *n* `}`</span><span class="sxs-lookup"><span data-stu-id="e1cb7-111">`{` *n* `}`</span></span>|<span data-ttu-id="e1cb7-112">`{` *n* `}?`</span><span class="sxs-lookup"><span data-stu-id="e1cb7-112">`{` *n* `}?`</span></span>|<span data-ttu-id="e1cb7-113">完全匹配 *n* 时间。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-113">Match exactly *n* times.</span></span>|  
|<span data-ttu-id="e1cb7-114">`{` *n* `,}`</span><span class="sxs-lookup"><span data-stu-id="e1cb7-114">`{` *n* `,}`</span></span>|<span data-ttu-id="e1cb7-115">`{` *n* `,}?`</span><span class="sxs-lookup"><span data-stu-id="e1cb7-115">`{` *n* `,}?`</span></span>|<span data-ttu-id="e1cb7-116">匹配至少 *n* 时间。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-116">Match at least *n* times.</span></span>|  
|<span data-ttu-id="e1cb7-117">`{` *n* `,` *m* `}`</span><span class="sxs-lookup"><span data-stu-id="e1cb7-117">`{` *n* `,` *m* `}`</span></span>|<span data-ttu-id="e1cb7-118">`{` *n* `,` *m* `}?`</span><span class="sxs-lookup"><span data-stu-id="e1cb7-118">`{` *n* `,` *m* `}?`</span></span>|<span data-ttu-id="e1cb7-119">与来自 *n* 到*m*时间。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-119">Match from *n* to *m* times.</span></span>|  
  
 <span data-ttu-id="e1cb7-120">所需数量`n`和`m`是整数常量。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-120">The quantities `n` and `m` are integer constants.</span></span> <span data-ttu-id="e1cb7-121">通常，限定符是贪婪的；它们使正则表达式引擎匹配尽可能多的特定模式实例。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-121">Ordinarily, quantifiers are greedy; they cause the regular expression engine to match as many occurrences of particular patterns as possible.</span></span> <span data-ttu-id="e1cb7-122">向限定符追加 `?` 字符可使它成为惰性的；会使正则表达式引擎匹配尽可能少的实例。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-122">Appending the `?` character to a quantifier makes it lazy; it causes the regular expression engine to match as few occurrences as possible.</span></span> <span data-ttu-id="e1cb7-123">有关贪婪与惰性限定符之间的差异的完整说明，请参见本主题后面的[贪婪与惰性限定符](#Greedy)部分。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-123">For a complete description of the difference between greedy and lazy quantifiers, see the section [Greedy and Lazy Quantifiers](#Greedy) later in this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e1cb7-124">嵌套限定符（例如正则表达式模式 `(a*)*` 的行为）可以按输入字符串中的字符数的指数函数形式，来增加正则表达式引擎必须执行的比较次数。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-124">Nesting quantifiers (for example, as the regular expression pattern `(a*)*` does) can increase the number of comparisons that the regular expression engine must perform, as an exponential function of the number of characters in the input string.</span></span> <span data-ttu-id="e1cb7-125">此行为，并且其解决方法有关的详细信息，请参阅[回溯](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-125">For more information about this behavior and its workarounds, see [Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md).</span></span>  
  
## <a name="regular-expression-quantifiers"></a><span data-ttu-id="e1cb7-126">正则表达式限定符</span><span class="sxs-lookup"><span data-stu-id="e1cb7-126">Regular Expression Quantifiers</span></span>  
 <span data-ttu-id="e1cb7-127">以下部分列出了 .NET 正则表达式支持的限定符。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-127">The following sections list the quantifiers supported by .NET regular expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1cb7-128">如果 *，+，？，{，和} 个字符正则表达式模式中出现，正则表达式引擎会将其解析为限定符或限定符构造的一部分除非它们包括在[字符类](../../../docs/standard/base-types/character-classes-in-regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-128">If the *, +, ?, {, and } characters are encountered in a regular expression pattern, the regular expression engine interprets them as quantifiers or part of quantifier constructs unless they are included in a [character class](../../../docs/standard/base-types/character-classes-in-regular-expressions.md).</span></span> <span data-ttu-id="e1cb7-129">若要在字符类外部将这些字符解释文本字符，必须通过在它们前面加反斜杠来对它们进行转义。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-129">To interpret these as literal characters outside a character class, you must escape them by preceding them with a backslash.</span></span> <span data-ttu-id="e1cb7-130">例如，在字符串`\*`正则表达式模式可以解释为原义星号 ("\*") 字符。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-130">For example, the string `\*` in a regular expression pattern is interpreted as a literal asterisk ("\*") character.</span></span>  
  
### <a name="match-zero-or-more-times-"></a><span data-ttu-id="e1cb7-131">匹配零次或多次：*</span><span class="sxs-lookup"><span data-stu-id="e1cb7-131">Match Zero or More Times: *</span></span>  
 <span data-ttu-id="e1cb7-132">`*` 限定符与前面的元素匹配零次或多次。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-132">The `*` quantifier matches the preceding element zero or more times.</span></span> <span data-ttu-id="e1cb7-133">它相当于`{0,}`限定符。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-133">It is equivalent to the `{0,}` quantifier.</span></span> <span data-ttu-id="e1cb7-134">`*`是贪婪限定符的惰性限定符是`*?`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-134">`*` is a greedy quantifier whose lazy equivalent is `*?`.</span></span>  
  
 <span data-ttu-id="e1cb7-135">下面的示例说明此正则表达式。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-135">The following example illustrates this regular expression.</span></span> <span data-ttu-id="e1cb7-136">在输入字符串中的九个数字中，五个与模式匹配，四个（`95`、`929`、`9129` 和 `9919`）不匹配。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-136">Of the nine digits in the input string, five match the pattern and four (`95`, `929`, `9129`, and `9919`) do not.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#1)]  
  
 <span data-ttu-id="e1cb7-137">正则表达式模式的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-137">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="e1cb7-138">模式</span><span class="sxs-lookup"><span data-stu-id="e1cb7-138">Pattern</span></span>|<span data-ttu-id="e1cb7-139">说明</span><span class="sxs-lookup"><span data-stu-id="e1cb7-139">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="e1cb7-140">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-140">Start at a word boundary.</span></span>|  
|`91*`|<span data-ttu-id="e1cb7-141">匹配后跟零个或多个“1”字符的“9”。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-141">Match a "9" followed by zero or more "1" characters.</span></span>|  
|`9*`|<span data-ttu-id="e1cb7-142">匹配零个或多个“9”字符。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-142">Match zero or more "9" characters.</span></span>|  
|`\b`|<span data-ttu-id="e1cb7-143">在字边界结束。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-143">End at a word boundary.</span></span>|  
  
### <a name="match-one-or-more-times-"></a><span data-ttu-id="e1cb7-144">匹配一次或多次：+</span><span class="sxs-lookup"><span data-stu-id="e1cb7-144">Match One or More Times: +</span></span>  
 <span data-ttu-id="e1cb7-145">`+`限定符匹配前面的元素一个或多个时间。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-145">The `+` quantifier matches the preceding element one or more times.</span></span> <span data-ttu-id="e1cb7-146">它相当于`{1,}`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-146">It is equivalent to `{1,}`.</span></span> <span data-ttu-id="e1cb7-147">`+`是贪婪限定符的惰性限定符是`+?`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-147">`+` is a greedy quantifier whose lazy equivalent is `+?`.</span></span>  
  
 <span data-ttu-id="e1cb7-148">例如，正则表达式 `\ban+\w*?\b` 会尝试匹配以后跟字母 `n` 的一个或多个实例的字母 `a` 开头的完整单词。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-148">For example, the regular expression `\ban+\w*?\b` tries to match entire words that begin with the letter `a` followed by one or more instances of the letter `n`.</span></span> <span data-ttu-id="e1cb7-149">下面的示例说明此正则表达式。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-149">The following example illustrates this regular expression.</span></span> <span data-ttu-id="e1cb7-150">正则表达式会匹配单词 `an`、`annual`、`announcement` 和 `antique`，并且正确地无法匹配 `autumn` 和 `all`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-150">The regular expression matches the words `an`, `annual`, `announcement`, and `antique`, and correctly fails to match `autumn` and `all`.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#2)]  
  
 <span data-ttu-id="e1cb7-151">正则表达式模式的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-151">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="e1cb7-152">模式</span><span class="sxs-lookup"><span data-stu-id="e1cb7-152">Pattern</span></span>|<span data-ttu-id="e1cb7-153">说明</span><span class="sxs-lookup"><span data-stu-id="e1cb7-153">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="e1cb7-154">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-154">Start at a word boundary.</span></span>|  
|`an+`|<span data-ttu-id="e1cb7-155">匹配后跟一个或多个“n”字符的“a”。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-155">Match an "a" followed by one or more "n" characters.</span></span>|  
|`\w*?`|<span data-ttu-id="e1cb7-156">匹配单词字符零次或多次，但次数尽可能少。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-156">Match a word character zero or more times, but as few times as possible.</span></span>|  
|`\b`|<span data-ttu-id="e1cb7-157">在字边界结束。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-157">End at a word boundary.</span></span>|  
  
### <a name="match-zero-or-one-time-"></a><span data-ttu-id="e1cb7-158">匹配零次或一次：?</span><span class="sxs-lookup"><span data-stu-id="e1cb7-158">Match Zero or One Time: ?</span></span>  
 <span data-ttu-id="e1cb7-159">`?`限定符可以匹配前面的元素零个或一个时间。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-159">The `?` quantifier matches the preceding element zero or one time.</span></span> <span data-ttu-id="e1cb7-160">它相当于`{0,1}`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-160">It is equivalent to `{0,1}`.</span></span> <span data-ttu-id="e1cb7-161">`?`是贪婪限定符的惰性限定符是`??`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-161">`?` is a greedy quantifier whose lazy equivalent is `??`.</span></span>  
  
 <span data-ttu-id="e1cb7-162">例如，正则表达式 `\ban?\b` 会尝试匹配以后跟字母 `n` 的零个或一个实例的字母 `a` 开头的完整单词。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-162">For example, the regular expression `\ban?\b` tries to match entire words that begin with the letter `a` followed by zero or one instances of the letter `n`.</span></span> <span data-ttu-id="e1cb7-163">换句话说，它会尝试匹配单词 `a` 和 `an`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-163">In other words, it tries to match the words `a` and `an`.</span></span> <span data-ttu-id="e1cb7-164">下面的示例说明此正则表达式。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-164">The following example illustrates this regular expression.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#3)]
 [!code-vb[RegularExpressions.Quantifiers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#3)]  
  
 <span data-ttu-id="e1cb7-165">正则表达式模式的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-165">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="e1cb7-166">模式</span><span class="sxs-lookup"><span data-stu-id="e1cb7-166">Pattern</span></span>|<span data-ttu-id="e1cb7-167">说明</span><span class="sxs-lookup"><span data-stu-id="e1cb7-167">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="e1cb7-168">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-168">Start at a word boundary.</span></span>|  
|`an?`|<span data-ttu-id="e1cb7-169">匹配后跟零个或一个“n”字符的“a”。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-169">Match an "a" followed by zero or one "n" character.</span></span>|  
|`\b`|<span data-ttu-id="e1cb7-170">在字边界结束。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-170">End at a word boundary.</span></span>|  
  
### <a name="match-exactly-n-times-n"></a><span data-ttu-id="e1cb7-171">恰好匹配 n 次：{n}</span><span class="sxs-lookup"><span data-stu-id="e1cb7-171">Match Exactly n Times: {n}</span></span>  
 <span data-ttu-id="e1cb7-172">`{`  *n*  `}`限定符匹配前面的元素恰好 *n* 时间 where  *n* 是任意整数。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-172">The `{`*n*`}` quantifier matches the preceding element exactly *n* times, where *n* is any integer.</span></span> <span data-ttu-id="e1cb7-173">`{`*n*`}`是贪婪限定符的惰性限定符是`{`  *n*  `}?`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-173">`{`*n*`}` is a greedy quantifier whose lazy equivalent is `{`*n*`}?`.</span></span>  
  
 <span data-ttu-id="e1cb7-174">例如，正则表达式 `\b\d+\,\d{3}\b` 会尝试匹配依次后跟一个或多个十进制数字、三个十进制数字、一个单词边界的单词边界。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-174">For example, the regular expression `\b\d+\,\d{3}\b` tries to match a word boundary followed by one or more decimal digits followed by three decimal digits followed by a word boundary.</span></span> <span data-ttu-id="e1cb7-175">下面的示例说明此正则表达式。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-175">The following example illustrates this regular expression.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#4](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#4)]
 [!code-vb[RegularExpressions.Quantifiers#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#4)]  
  
 <span data-ttu-id="e1cb7-176">正则表达式模式的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-176">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="e1cb7-177">模式</span><span class="sxs-lookup"><span data-stu-id="e1cb7-177">Pattern</span></span>|<span data-ttu-id="e1cb7-178">说明</span><span class="sxs-lookup"><span data-stu-id="e1cb7-178">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="e1cb7-179">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-179">Start at a word boundary.</span></span>|  
|`\d+`|<span data-ttu-id="e1cb7-180">匹配一个或多个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-180">Match one or more decimal digits.</span></span>|  
|`\,`|<span data-ttu-id="e1cb7-181">匹配逗号字符。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-181">Match a comma character.</span></span>|  
|`\d{3}`|<span data-ttu-id="e1cb7-182">匹配三个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-182">Match three decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="e1cb7-183">在字边界结束。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-183">End at a word boundary.</span></span>|  
  
### <a name="match-at-least-n-times-n"></a><span data-ttu-id="e1cb7-184">至少匹配 n 次：{n,}</span><span class="sxs-lookup"><span data-stu-id="e1cb7-184">Match at Least n Times: {n,}</span></span>  
 <span data-ttu-id="e1cb7-185">`{`  *n*  `,}`限定符至少匹配前面的元素 *n* 时间 where  *n* 是任意整数。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-185">The `{`*n*`,}` quantifier matches the preceding element at least *n* times, where *n* is any integer.</span></span> <span data-ttu-id="e1cb7-186">`{`*n*`,}`是贪婪限定符的惰性限定符是`{`  *n*  `}?`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-186">`{`*n*`,}` is a greedy quantifier whose lazy equivalent is `{`*n*`}?`.</span></span>  
  
 <span data-ttu-id="e1cb7-187">例如，正则表达式 `\b\d{2,}\b\D+` 会尝试匹配依次后跟至少两个数字、一个单词边界和一个非数字字符的单词边界。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-187">For example, the regular expression `\b\d{2,}\b\D+` tries to match a word boundary followed by at least two digits followed by a word boundary and a non-digit character.</span></span> <span data-ttu-id="e1cb7-188">下面的示例说明此正则表达式。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-188">The following example illustrates this regular expression.</span></span> <span data-ttu-id="e1cb7-189">正则表达式不匹配短语`"7 days"`因为它只包含一个十进制数字，但它成功匹配短语`"10 weeks and 300 years"`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-189">The regular expression fails to match the phrase `"7 days"` because it contains just one decimal digit, but it successfully matches the phrases `"10 weeks and 300 years"`.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#5](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#5)]
 [!code-vb[RegularExpressions.Quantifiers#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#5)]  
  
 <span data-ttu-id="e1cb7-190">正则表达式模式的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-190">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="e1cb7-191">模式</span><span class="sxs-lookup"><span data-stu-id="e1cb7-191">Pattern</span></span>|<span data-ttu-id="e1cb7-192">说明</span><span class="sxs-lookup"><span data-stu-id="e1cb7-192">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="e1cb7-193">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-193">Start at a word boundary.</span></span>|  
|`\d{2,}`|<span data-ttu-id="e1cb7-194">匹配至少两个十进制数字。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-194">Match at least two decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="e1cb7-195">与字边界匹配。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-195">Match a word boundary.</span></span>|  
|`\D+`|<span data-ttu-id="e1cb7-196">匹配至少一个非十进制数字。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-196">Match at least one non-decimal digit.</span></span>|  
  
### <a name="match-between-n-and-m-times-nm"></a><span data-ttu-id="e1cb7-197">匹配 n 到 m 次：{n,m}</span><span class="sxs-lookup"><span data-stu-id="e1cb7-197">Match Between n and m Times: {n,m}</span></span>  
 <span data-ttu-id="e1cb7-198">`{`  *n*  `,` *M* `}`限定符至少匹配前面的元素 *n* 时间，但不是能超过*m*时间 where  *n* 和*m*均为整数。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-198">The `{`*n*`,`*m*`}` quantifier matches the preceding element at least *n* times, but no more than *m* times, where *n* and *m* are integers.</span></span> <span data-ttu-id="e1cb7-199">`{`*n*`,`*m* `}`是贪婪限定符的惰性限定符是`{`  *n*  `,` *m*`}?`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-199">`{`*n*`,`*m*`}` is a greedy quantifier whose lazy equivalent is `{`*n*`,`*m*`}?`.</span></span>  
  
 <span data-ttu-id="e1cb7-200">在下面的示例中，正则表达式 `(00\s){2,4}` 尝试与后跟一个空格的两个零数字匹配两到四次。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-200">In the following example, the regular expression `(00\s){2,4}` tries to match between two and four occurrences of two zero digits followed by a space.</span></span> <span data-ttu-id="e1cb7-201">请注意，输入字符串的最后一部分包含此模式五次，而不是最大值四次。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-201">Note that the final portion of the input string includes this pattern five times rather than the maximum of four.</span></span> <span data-ttu-id="e1cb7-202">但是，只有此子字符串的初始部分（到空格和第五对零）与正则表达式模式匹配。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-202">However, only the initial portion of this substring (up to the space and the fifth pair of zeros) matches the regular expression pattern.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#6](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#6)]
 [!code-vb[RegularExpressions.Quantifiers#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#6)]  
  
### <a name="match-zero-or-more-times-lazy-match-"></a><span data-ttu-id="e1cb7-203">匹配零次或多次（惰性匹配）：*?</span><span class="sxs-lookup"><span data-stu-id="e1cb7-203">Match Zero or More Times (Lazy Match): *?</span></span>  
 <span data-ttu-id="e1cb7-204">`*?`限定符匹配前面的元素零次或多次，但次数少尽可能。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-204">The `*?` quantifier matches the preceding element zero or more times, but as few times as possible.</span></span> <span data-ttu-id="e1cb7-205">它是对应的贪婪限定符惰性部分`*`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-205">It is the lazy counterpart of the greedy quantifier `*`.</span></span>  
  
 <span data-ttu-id="e1cb7-206">在下面的示例中，正则表达式 `\b\w*?oo\w*?\b` 匹配包含字符串 `oo` 的所有单词。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-206">In the following example, the regular expression `\b\w*?oo\w*?\b` matches all words that contain the string `oo`.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#7](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#7)]
 [!code-vb[RegularExpressions.Quantifiers#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#7)]  
  
 <span data-ttu-id="e1cb7-207">正则表达式模式的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-207">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="e1cb7-208">模式</span><span class="sxs-lookup"><span data-stu-id="e1cb7-208">Pattern</span></span>|<span data-ttu-id="e1cb7-209">说明</span><span class="sxs-lookup"><span data-stu-id="e1cb7-209">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="e1cb7-210">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-210">Start at a word boundary.</span></span>|  
|`\w*?`|<span data-ttu-id="e1cb7-211">匹配零个或多个单词字符，但字符要尽可能的少。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-211">Match zero or more word characters, but as few characters as possible.</span></span>|  
|`oo`|<span data-ttu-id="e1cb7-212">匹配字符串“oo”。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-212">Match the string "oo".</span></span>|  
|`\w*?`|<span data-ttu-id="e1cb7-213">匹配零个或多个单词字符，但字符要尽可能的少。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-213">Match zero or more word characters, but as few characters as possible.</span></span>|  
|`\b`|<span data-ttu-id="e1cb7-214">在单词边界处结束。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-214">End on a word boundary.</span></span>|  
  
### <a name="match-one-or-more-times-lazy-match-"></a><span data-ttu-id="e1cb7-215">匹配一次或多次（惰性匹配）：+?</span><span class="sxs-lookup"><span data-stu-id="e1cb7-215">Match One or More Times (Lazy Match): +?</span></span>  
 <span data-ttu-id="e1cb7-216">`+?`限定符一个或多个时间，但次数少尽可能匹配前面的元素。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-216">The `+?` quantifier matches the preceding element one or more times, but as few times as possible.</span></span> <span data-ttu-id="e1cb7-217">它是对应的贪婪限定符惰性部分`+`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-217">It is the lazy counterpart of the greedy quantifier `+`.</span></span>  
  
 <span data-ttu-id="e1cb7-218">例如，正则表达式 `\b\w+?\b` 匹配由单词边界分隔的一个或多个字符。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-218">For example, the regular expression `\b\w+?\b` matches one or more characters separated by word boundaries.</span></span> <span data-ttu-id="e1cb7-219">下面的示例说明此正则表达式。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-219">The following example illustrates this regular expression.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#8)]
 [!code-vb[RegularExpressions.Quantifiers#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#8)]  
  
### <a name="match-zero-or-one-time-lazy-match-"></a><span data-ttu-id="e1cb7-220">匹配零次或一次（惰性匹配）：??</span><span class="sxs-lookup"><span data-stu-id="e1cb7-220">Match Zero or One Time (Lazy Match): ??</span></span>  
 <span data-ttu-id="e1cb7-221">`??`限定符与前面的元素零个或一个时间，但次数少尽可能匹配。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-221">The `??` quantifier matches the preceding element zero or one time, but as few times as possible.</span></span> <span data-ttu-id="e1cb7-222">它是对应的贪婪限定符惰性部分`?`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-222">It is the lazy counterpart of the greedy quantifier `?`.</span></span>  
  
 <span data-ttu-id="e1cb7-223">例如，正则表达式 `^\s*(System.)??Console.Write(Line)??\(??` 尝试匹配字符串“Console.Write”或“Console.WriteLine”。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-223">For example, the regular expression `^\s*(System.)??Console.Write(Line)??\(??` attempts to match the strings "Console.Write" or "Console.WriteLine".</span></span> <span data-ttu-id="e1cb7-224">字符串还可以在“Console”前面包含“System.”，</span><span class="sxs-lookup"><span data-stu-id="e1cb7-224">The string can also include "System."</span></span> <span data-ttu-id="e1cb7-225">并且可以后跟左括号。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-225">before "Console", and it can be followed by an opening parenthesis.</span></span> <span data-ttu-id="e1cb7-226">字符串必须处于行的开头，不过前面可以是空格。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-226">The string must be at the beginning of a line, although it can be preceded by white space.</span></span> <span data-ttu-id="e1cb7-227">下面的示例说明此正则表达式。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-227">The following example illustrates this regular expression.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#9](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#9)]
 [!code-vb[RegularExpressions.Quantifiers#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#9)]  
  
 <span data-ttu-id="e1cb7-228">正则表达式模式的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-228">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="e1cb7-229">模式</span><span class="sxs-lookup"><span data-stu-id="e1cb7-229">Pattern</span></span>|<span data-ttu-id="e1cb7-230">描述</span><span class="sxs-lookup"><span data-stu-id="e1cb7-230">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="e1cb7-231">匹配输入流的开头。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-231">Match the start of the input stream.</span></span>|  
|`\s*`|<span data-ttu-id="e1cb7-232">匹配零个或多个空白字符。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-232">Match zero or more white-space characters.</span></span>|  
|`(System.)??`|<span data-ttu-id="e1cb7-233">匹配字符串“System.”的零个或一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-233">Match zero or one occurrence of the string "System.".</span></span>|  
|`Console.Write`|<span data-ttu-id="e1cb7-234">匹配字符串“Console.Write”。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-234">Match the string "Console.Write".</span></span>|  
|`(Line)??`|<span data-ttu-id="e1cb7-235">匹配字符串“Line”的零个或一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-235">Match zero or one occurrence of the string "Line".</span></span>|  
|`\(??`|<span data-ttu-id="e1cb7-236">匹配左括号的零个或一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-236">Match zero or one occurrence of the opening parenthesis.</span></span>|  
  
### <a name="match-exactly-n-times-lazy-match-n"></a><span data-ttu-id="e1cb7-237">恰好匹配 n 次（惰性匹配）：{n}?</span><span class="sxs-lookup"><span data-stu-id="e1cb7-237">Match Exactly n Times (Lazy Match): {n}?</span></span>  
 <span data-ttu-id="e1cb7-238">`{`  *n*  `}?`限定符匹配前面的元素恰好`n`时间 where  *n* 是任意整数。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-238">The `{`*n*`}?` quantifier matches the preceding element exactly `n` times, where *n* is any integer.</span></span> <span data-ttu-id="e1cb7-239">它是对应的贪婪限定符惰性部分`{`  *n*  `}+`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-239">It is the lazy counterpart of the greedy quantifier `{`*n*`}+`.</span></span>  
  
 <span data-ttu-id="e1cb7-240">在下面的示例中，正则表达式 `\b(\w{3,}?\.){2}?\w{3,}?\b` 用于标识网站地址。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-240">In the following example, the regular expression `\b(\w{3,}?\.){2}?\w{3,}?\b` is used to identify a Web site address.</span></span> <span data-ttu-id="e1cb7-241">请注意，它匹配“www.microsoft.com”和“msdn.microsoft.com”，但不匹配“mywebsite”或“mycompany.com”。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-241">Note that it matches "www.microsoft.com" and "msdn.microsoft.com", but does not match "mywebsite" or "mycompany.com".</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#10](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#10)]
 [!code-vb[RegularExpressions.Quantifiers#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#10)]  
  
 <span data-ttu-id="e1cb7-242">正则表达式模式的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-242">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="e1cb7-243">模式</span><span class="sxs-lookup"><span data-stu-id="e1cb7-243">Pattern</span></span>|<span data-ttu-id="e1cb7-244">说明</span><span class="sxs-lookup"><span data-stu-id="e1cb7-244">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="e1cb7-245">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-245">Start at a word boundary.</span></span>|  
|`(\w{3,}?\.)`|<span data-ttu-id="e1cb7-246">匹配至少 3 个后跟一个点或句点字符的单词字符，但字符数尽可能少。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-246">Match at least 3 word characters, but as few characters as possible, followed by a dot or period character.</span></span> <span data-ttu-id="e1cb7-247">这是第一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-247">This is the first capturing group.</span></span>|  
|`(\w{3,}?\.){2}?`|<span data-ttu-id="e1cb7-248">匹配第一个组中的模式两次，但次数尽可能少。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-248">Match the pattern in the first group two times, but as few times as possible.</span></span>|  
|`\b`|<span data-ttu-id="e1cb7-249">在单词边界处结束匹配。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-249">End the match on a word boundary.</span></span>|  
  
### <a name="match-at-least-n-times-lazy-match-n"></a><span data-ttu-id="e1cb7-250">至少匹配 n 次（惰性匹配）：{n,}?</span><span class="sxs-lookup"><span data-stu-id="e1cb7-250">Match at Least n Times (Lazy Match): {n,}?</span></span>  
 <span data-ttu-id="e1cb7-251">`{`  *n*  `,}?`限定符至少匹配前面的元素`n`时间 where  *n* 是任意整数，但尽可能少的次数可能。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-251">The `{`*n*`,}?` quantifier matches the preceding element at least `n` times, where *n* is any integer, but as few times as possible.</span></span> <span data-ttu-id="e1cb7-252">它是对应的贪婪限定符惰性部分`{`  *n*  `,}`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-252">It is the lazy counterpart of the greedy quantifier `{`*n*`,}`.</span></span>  
  
 <span data-ttu-id="e1cb7-253">请参阅示例`{`  *n*  `}?`举例说明的上一节中的限定符。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-253">See the example for the `{`*n*`}?` quantifier in the previous section for an illustration.</span></span> <span data-ttu-id="e1cb7-254">该示例中的正则表达式使用`{`  *n*  `,}`限定符来匹配包含后跟句号的至少三个字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-254">The regular expression in that example uses the `{`*n*`,}` quantifier to match a string that has at least three characters followed by a period.</span></span>  
  
### <a name="match-between-n-and-m-times-lazy-match-nm"></a><span data-ttu-id="e1cb7-255">匹配 n 到 m 次（惰性匹配）：{n,m}?</span><span class="sxs-lookup"><span data-stu-id="e1cb7-255">Match Between n and m Times (Lazy Match): {n,m}?</span></span>  
 <span data-ttu-id="e1cb7-256">`{`  *n*  `,` *M* `}?`限定符可以匹配前面的元素之间`n`和`m`时间 where *n* 和*m*都是整数，但次数少尽可能。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-256">The `{`*n*`,`*m*`}?` quantifier matches the preceding element between `n` and `m` times, where *n* and *m* are integers, but as few times as possible.</span></span> <span data-ttu-id="e1cb7-257">它是对应的贪婪限定符惰性部分`{`  *n*  `,` *m*`}`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-257">It is the lazy counterpart of the greedy quantifier `{`*n*`,`*m*`}`.</span></span>  
  
 <span data-ttu-id="e1cb7-258">在下面的示例中，正则表达式 `\b[A-Z](\w*\s+){1,10}?[.!?]` 匹配包含一到十个单词的句子。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-258">In the following example, the regular expression `\b[A-Z](\w*\s+){1,10}?[.!?]` matches sentences that contain between one and ten words.</span></span> <span data-ttu-id="e1cb7-259">它可匹配输入字符串中的所有句子（除了包含 18 个单词的一个句子）。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-259">It matches all the sentences in the input string except for one sentence that contains 18 words.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#12](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#12)]
 [!code-vb[RegularExpressions.Quantifiers#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#12)]  
  
 <span data-ttu-id="e1cb7-260">正则表达式模式的定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-260">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="e1cb7-261">模式</span><span class="sxs-lookup"><span data-stu-id="e1cb7-261">Pattern</span></span>|<span data-ttu-id="e1cb7-262">说明</span><span class="sxs-lookup"><span data-stu-id="e1cb7-262">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="e1cb7-263">在单词边界处开始。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-263">Start at a word boundary.</span></span>|  
|`[A-Z]`|<span data-ttu-id="e1cb7-264">匹配从 A 到 Z 的大写字符。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-264">Match an uppercase character from A to Z.</span></span>|  
|`(\w*\s+)`|<span data-ttu-id="e1cb7-265">匹配零个或多个后跟一个或多个空白字符的单词字符。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-265">Match zero or more word characters, followed by one or more white-space characters.</span></span> <span data-ttu-id="e1cb7-266">这是第一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-266">This is the first capture group.</span></span>|  
|`{1,10}?`|<span data-ttu-id="e1cb7-267">与前面的模式匹配 1 到 10 次，但次数尽可能少。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-267">Match the previous pattern between 1 and 10 times, but as few times as possible.</span></span>|  
|`[.!?]`|<span data-ttu-id="e1cb7-268">匹配标点字符“.”、“!”或“?”中的任何一种。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-268">Match any one of the punctuation characters ".", "!", or "?".</span></span>|  
  
<a name="Greedy"></a>   
## <a name="greedy-and-lazy-quantifiers"></a><span data-ttu-id="e1cb7-269">贪婪与惰性限定符</span><span class="sxs-lookup"><span data-stu-id="e1cb7-269">Greedy and Lazy Quantifiers</span></span>  
 <span data-ttu-id="e1cb7-270">一些限定符具有两个版本：</span><span class="sxs-lookup"><span data-stu-id="e1cb7-270">A number of the quantifiers have two versions:</span></span>  
  
-   <span data-ttu-id="e1cb7-271">贪婪版本。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-271">A greedy version.</span></span>  
  
     <span data-ttu-id="e1cb7-272">贪婪限定符尝试尽可能多地匹配元素。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-272">A greedy quantifier tries to match an element as many times as possible.</span></span>  
  
-   <span data-ttu-id="e1cb7-273">非贪婪 （或延迟） 版本。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-273">A non-greedy (or lazy) version.</span></span>  
  
     <span data-ttu-id="e1cb7-274">非贪婪限定符尝试尽可能少地匹配元素。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-274">A non-greedy quantifier tries to match an element as few times as possible.</span></span> <span data-ttu-id="e1cb7-275">你可以转换为惰性限定符将贪婪限定符，只需添加`?`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-275">You can turn a greedy quantifier into a lazy quantifier by simply adding a `?`.</span></span>  
  
 <span data-ttu-id="e1cb7-276">请考虑一个简单的正则表达式，它旨在从数字字符串（如信用卡号）中提取最后四位数。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-276">Consider a simple regular expression that is intended to extract the last four digits from a string of numbers such as a credit card number.</span></span> <span data-ttu-id="e1cb7-277">正则表达式使用的版本`*`贪婪限定符是`\b.*([0-9]{4})\b`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-277">The version of the regular expression that uses the `*` greedy quantifier is `\b.*([0-9]{4})\b`.</span></span> <span data-ttu-id="e1cb7-278">但是，如果字符串包含两个数字，则此正则表达式仅匹配第二个数字的最后四位数，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-278">However, if a string contains two numbers, this regular expression matches the last four digits of the second number only, as the following example shows.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#1)]  
  
 <span data-ttu-id="e1cb7-279">正则表达式不匹配的第一个数字，因为`*`限定符尝试匹配上一个元素中的整个字符串，可能根据多次，因此它找到其匹配字符串的末尾。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-279">The regular expression fails to match the first number because the `*` quantifier tries to match the previous element as many times as possible in the entire string, and so it finds its match at the end of the string.</span></span>  
  
 <span data-ttu-id="e1cb7-280">这不是所需行为。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-280">This is not the desired behavior.</span></span> <span data-ttu-id="e1cb7-281">相反，你可以使用`*?`惰性限定符一起提取数字从这两个编号，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-281">Instead, you can use the `*?`lazy quantifier to extract digits from both numbers, as the following example shows.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#2)]  
  
 <span data-ttu-id="e1cb7-282">在大多数情况下，具有贪婪和惰性限定符的正则表达式返回相同匹配项。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-282">In most cases, regular expressions with greedy and lazy quantifiers return the same matches.</span></span> <span data-ttu-id="e1cb7-283">它们通常返回不同的结果时使用通配符 (`.`) 元字符，与任何字符匹配。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-283">They most commonly return different results when they are used with the wildcard (`.`) metacharacter, which matches any character.</span></span>  
  
## <a name="quantifiers-and-empty-matches"></a><span data-ttu-id="e1cb7-284">限定符和空匹配项</span><span class="sxs-lookup"><span data-stu-id="e1cb7-284">Quantifiers and Empty Matches</span></span>  
 <span data-ttu-id="e1cb7-285">限定符`*`， `+`，和`{`  *n*  `,` *m* `}`和延迟的对应永远不会重复执行间隔为空当已找到的最小捕获数匹配。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-285">The quantifiers `*`, `+`, and `{`*n*`,`*m*`}` and their lazy counterparts never repeat after an empty match when the minimum number of captures has been found.</span></span> <span data-ttu-id="e1cb7-286">此规则会在最大可能组捕获数是无限或接近无限时，阻止限定符在空的子表达式匹配项上进入无限循环。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-286">This rule prevents quantifiers from entering infinite loops on empty subexpression matches when the maximum number of possible group captures is infinite or near infinite.</span></span>  
  
 <span data-ttu-id="e1cb7-287">例如，下面的代码演示对的调用结果<xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType>与正则表达式模式的方法`(a?)*`，与零个或一个"a"字符匹配零个或更多时间。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-287">For example, the following code shows the result of a call to the <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType> method with the regular expression pattern `(a?)*`, which matches zero or one "a" character zero or more times.</span></span> <span data-ttu-id="e1cb7-288">请注意，单个捕获组捕获每个"a"作为以及<xref:System.String.Empty?displayProperty=nameWithType>，但该没有第二个空匹配项，因为第一个空匹配使限定符停止重复。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-288">Note that the single capturing group captures each "a" as well as <xref:System.String.Empty?displayProperty=nameWithType>, but that there is no second empty match, because the first empty match causes the quantifier to stop repeating.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch1.vb#1)]  
  
 <span data-ttu-id="e1cb7-289">若要查看定义最小和最大捕获数的捕获组与定义固定捕获数的捕获组之间的实际差异，请考虑正则表达式模式 `(a\1|(?(1)\1)){0,2}` 和 `(a\1|(?(1)\1)){2}`。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-289">To see the practical difference between a capturing group that defines a minimum and a maximum number of captures and one that defines a fixed number of captures, consider the regular expression patterns `(a\1|(?(1)\1)){0,2}` and `(a\1|(?(1)\1)){2}`.</span></span> <span data-ttu-id="e1cb7-290">这两个正则表达式包含单个捕获组，其定义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-290">Both regular expressions consist of a single capturing group, which is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="e1cb7-291">模式</span><span class="sxs-lookup"><span data-stu-id="e1cb7-291">Pattern</span></span>|<span data-ttu-id="e1cb7-292">描述</span><span class="sxs-lookup"><span data-stu-id="e1cb7-292">Description</span></span>|  
|-------------|-----------------|  
|`(a\1`|<span data-ttu-id="e1cb7-293">匹配“a”以及第一个捕获组的值...</span><span class="sxs-lookup"><span data-stu-id="e1cb7-293">Either match "a" along with the value of the first captured group …</span></span>|  
|`&#124;(?(1)`|<span data-ttu-id="e1cb7-294">…</span><span class="sxs-lookup"><span data-stu-id="e1cb7-294">…</span></span> <span data-ttu-id="e1cb7-295">或测试是否定义了第一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-295">or test whether the first captured group has been defined.</span></span> <span data-ttu-id="e1cb7-296">(请注意，`(?(1)`构造未定义的捕获组。)</span><span class="sxs-lookup"><span data-stu-id="e1cb7-296">(Note that the `(?(1)` construct does not define a capturing group.)</span></span>|  
|`\1))`|<span data-ttu-id="e1cb7-297">如果第一个捕获组存在，则匹配其值。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-297">If the first captured group exists, match its value.</span></span> <span data-ttu-id="e1cb7-298">如果组不存在，将匹配组<xref:System.String.Empty?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-298">If the group does not exist, the group will match <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|  
  
 <span data-ttu-id="e1cb7-299">第一个正则表达式尝试与此模式匹配零到二次；第二个正则表达式尝试恰好匹配两次。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-299">The first regular expression tries to match this pattern between zero and two times; the second, exactly two times.</span></span> <span data-ttu-id="e1cb7-300">因为第一个模式达到其最小的数与其第一个捕获的捕获<xref:System.String.Empty?displayProperty=nameWithType>，它绝不会重复尝试匹配`a\1`;`{0,2}`限定符上次迭代中允许仅空匹配。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-300">Because the first pattern reaches its minimum number of captures with its first capture of <xref:System.String.Empty?displayProperty=nameWithType>, it never repeats to try to match `a\1`; the `{0,2}` quantifier allows only empty matches in the last iteration.</span></span> <span data-ttu-id="e1cb7-301">相反，第二个正则表达式匹配“a”，因为它会第二次计算 `a\1`；最小迭代数 2 会强制引擎在空匹配项后面重复。</span><span class="sxs-lookup"><span data-stu-id="e1cb7-301">In contrast, the second regular expression does match "a" because it evaluates `a\1` a second time; the minimum number of iterations, 2, forces the engine to repeat after an empty match.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch4.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch4.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e1cb7-302">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1cb7-302">See Also</span></span>  
 [<span data-ttu-id="e1cb7-303">正则表达式语言 - 快速参考</span><span class="sxs-lookup"><span data-stu-id="e1cb7-303">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 [<span data-ttu-id="e1cb7-304">回溯</span><span class="sxs-lookup"><span data-stu-id="e1cb7-304">Backtracking</span></span>](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)
