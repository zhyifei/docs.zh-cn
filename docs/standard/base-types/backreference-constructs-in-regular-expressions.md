---
title: "正则表达式中的反向引用构造"
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
- backreferences
- constructs, backreference
- .NET Framework regular expressions, backreference constructs
- regular expressions, backreference constructs
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2ec92933bdf123412a3d489fc493d76c4a0dc0d0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="backreference-constructs-in-regular-expressions"></a><span data-ttu-id="e765b-102">正则表达式中的反向引用构造</span><span class="sxs-lookup"><span data-stu-id="e765b-102">Backreference Constructs in Regular Expressions</span></span>
<span data-ttu-id="e765b-103">反向引用提供了标识字符串中的重复字符或子字符串的方便途径。</span><span class="sxs-lookup"><span data-stu-id="e765b-103">Backreferences provide a convenient way to identify a repeated character or substring within a string.</span></span> <span data-ttu-id="e765b-104">例如，如果输入字符串包含某任意子字符串的多个匹配项，可以使用捕获组匹配第一个出现的子字符串，然后使用反向引用匹配后面出现的子字符串。</span><span class="sxs-lookup"><span data-stu-id="e765b-104">For example, if the input string contains multiple occurrences of an arbitrary substring, you can match the first occurrence with a capturing group, and then use a backreference to match subsequent occurrences of the substring.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e765b-105">单独语法用于引用替换字符串中命名的和带编号的捕获组。</span><span class="sxs-lookup"><span data-stu-id="e765b-105">A separate syntax is used to refer to named and numbered capturing groups in replacement strings.</span></span> <span data-ttu-id="e765b-106">有关更多信息，请参见 [Substitutions](substitutions-in-regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="e765b-106">For more information, see [Substitutions](substitutions-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="e765b-107">.NET 定义引用编号和命名捕获组的单独语言元素。</span><span class="sxs-lookup"><span data-stu-id="e765b-107">.NET defines separate language elements to refer to numbered and named capturing groups.</span></span> <span data-ttu-id="e765b-108">若要详细了解捕获组，请参阅[分组构造](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="e765b-108">For more information about capturing groups, see [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span></span>  
  
## <a name="numbered-backreferences"></a><span data-ttu-id="e765b-109">带编号的反向引用</span><span class="sxs-lookup"><span data-stu-id="e765b-109">Numbered Backreferences</span></span>  
 <span data-ttu-id="e765b-110">带编号的反向引用使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="e765b-110">A numbered backreference uses the following syntax:</span></span>  
  
 <span data-ttu-id="e765b-111">`\` *数值*</span><span class="sxs-lookup"><span data-stu-id="e765b-111">`\` *number*</span></span>  
  
 <span data-ttu-id="e765b-112">其中 *number* 是正则表达式中捕获组的序号位置。</span><span class="sxs-lookup"><span data-stu-id="e765b-112">where *number* is the ordinal position of the capturing group in the regular expression.</span></span> <span data-ttu-id="e765b-113">例如，`\4` 匹配第四个捕获组的内容。</span><span class="sxs-lookup"><span data-stu-id="e765b-113">For example, `\4` matches the contents of the fourth capturing group.</span></span> <span data-ttu-id="e765b-114">如果正则表达式模式中未定义 number，将会发生分析错误，并且正则表达式引擎会抛出 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="e765b-114">If *number* is not defined in the regular expression pattern, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="e765b-115">例如，正则表达式 `\b(\w+)\s\1` 有效，因为 `(\w+)` 是表达式中的第一个也是唯一一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="e765b-115">For example, the regular expression `\b(\w+)\s\1` is valid, because `(\w+)` is the first and only capturing group in the expression.</span></span> <span data-ttu-id="e765b-116">`\b(\w+)\s\2` 无效，该表达式会因为没有捕获组编号 `\2` 而引发自变量异常。</span><span class="sxs-lookup"><span data-stu-id="e765b-116">On the other hand, `\b(\w+)\s\2` is invalid and throws an argument exception, because there is no capturing group numbered `\2`.</span></span>  
  
 <span data-ttu-id="e765b-117">请注意八进制转义代码（如 `\16`）和使用相同表示法的 `\`number 反向引用之间的不明确问题。</span><span class="sxs-lookup"><span data-stu-id="e765b-117">Note the ambiguity between octal escape codes (such as `\16`) and `\`*number* backreferences that use the same notation.</span></span> <span data-ttu-id="e765b-118">这种多义性可通过如下方式解决：</span><span class="sxs-lookup"><span data-stu-id="e765b-118">This ambiguity is resolved as follows:</span></span>  
  
-   <span data-ttu-id="e765b-119">表达式 `\1` 到 `\9` 始终解释为反向应用，而不是八进制代码。</span><span class="sxs-lookup"><span data-stu-id="e765b-119">The expressions `\1` through `\9` are always interpreted as backreferences, and not as octal codes.</span></span>  
  
-   <span data-ttu-id="e765b-120">如果多位表达式的第一个数字是 8 或 9（如 `\80` 或 `\91`），该表达式将解释为文本。</span><span class="sxs-lookup"><span data-stu-id="e765b-120">If the first digit of a multidigit expression is 8 or 9 (such as `\80` or `\91`), the expression as interpreted as a literal.</span></span>  
  
-   <span data-ttu-id="e765b-121">对于编号为 `\10` 或更大值的表达式，如果存在与该编号对应的反向引用，则将该表达式视为反向引用；否则，将这些表达式解释为八进制代码。</span><span class="sxs-lookup"><span data-stu-id="e765b-121">Expressions from `\10` and greater are considered backreferences if there is a backreference corresponding to that number; otherwise, they are interpreted as octal codes.</span></span>  
  
-   <span data-ttu-id="e765b-122">如果正则表达式包含对未定义的组成员的反向引用，将会发生分析错误，并且正则表达式引擎会抛出 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="e765b-122">If a regular expression contains a backreference to an undefined group number, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="e765b-123">如果存在不明确问题，可以使用 `\k<`name`>` 表示法，此表示法非常明确，不会与八进制字符代码混淆。</span><span class="sxs-lookup"><span data-stu-id="e765b-123">If the ambiguity is a problem, you can use the `\k<`*name*`>` notation, which is unambiguous and cannot be confused with octal character codes.</span></span> <span data-ttu-id="e765b-124">同样，诸如 `\xdd` 的十六进制代码也是明确的，不会与反向引用混淆。</span><span class="sxs-lookup"><span data-stu-id="e765b-124">Similarly, hexadecimal codes such as `\xdd` are unambiguous and cannot be confused with backreferences.</span></span>  
  
 <span data-ttu-id="e765b-125">下面的示例查找字符串中双写的单词字符。</span><span class="sxs-lookup"><span data-stu-id="e765b-125">The following example finds doubled word characters in a string.</span></span> <span data-ttu-id="e765b-126">它定义一个由下列元素组成的正则表达式 `(\w)\1`。</span><span class="sxs-lookup"><span data-stu-id="e765b-126">It defines a regular expression, `(\w)\1`, which consists of the following elements.</span></span>  
  
|<span data-ttu-id="e765b-127">元素</span><span class="sxs-lookup"><span data-stu-id="e765b-127">Element</span></span>|<span data-ttu-id="e765b-128">描述</span><span class="sxs-lookup"><span data-stu-id="e765b-128">Description</span></span>|  
|-------------|-----------------|  
|`(\w)`|<span data-ttu-id="e765b-129">匹配单词字符，并将其分配给第一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="e765b-129">Match a word character and assign it to the first capturing group.</span></span>|  
|`\1`|<span data-ttu-id="e765b-130">匹配值与第一捕获组相同的下一个字符。</span><span class="sxs-lookup"><span data-stu-id="e765b-130">Match the next character that is the same as the value of the first capturing group.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
 [!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]  
  
## <a name="named-backreferences"></a><span data-ttu-id="e765b-131">命名的反向引用</span><span class="sxs-lookup"><span data-stu-id="e765b-131">Named Backreferences</span></span>  
 <span data-ttu-id="e765b-132">使用以下语法定义命名的反向引用：</span><span class="sxs-lookup"><span data-stu-id="e765b-132">A named backreference is defined by using the following syntax:</span></span>  
  
 <span data-ttu-id="e765b-133">`\k<` *name* `>`</span><span class="sxs-lookup"><span data-stu-id="e765b-133">`\k<` *name* `>`</span></span>  
  
 <span data-ttu-id="e765b-134">或：</span><span class="sxs-lookup"><span data-stu-id="e765b-134">or:</span></span>  
  
 <span data-ttu-id="e765b-135">`\k'`name`'`</span><span class="sxs-lookup"><span data-stu-id="e765b-135">`\k'` *name* `'`</span></span>  
  
 <span data-ttu-id="e765b-136">其中，*name* 是正则表达式模式中定义的捕获组的名称。</span><span class="sxs-lookup"><span data-stu-id="e765b-136">where *name* is the name of a capturing group defined in the regular expression pattern.</span></span> <span data-ttu-id="e765b-137">如果正则表达式模式中未定义 name，将会发生分析错误，并且正则表达式引擎会抛出 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="e765b-137">If *name* is not defined in the regular expression pattern, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="e765b-138">下面的示例查找字符串中双写的单词字符。</span><span class="sxs-lookup"><span data-stu-id="e765b-138">The following example finds doubled word characters in a string.</span></span> <span data-ttu-id="e765b-139">它定义一个由下列元素组成的正则表达式 `(?<char>\w)\k<char>`。</span><span class="sxs-lookup"><span data-stu-id="e765b-139">It defines a regular expression, `(?<char>\w)\k<char>`, which consists of the following elements.</span></span>  
  
|<span data-ttu-id="e765b-140">元素</span><span class="sxs-lookup"><span data-stu-id="e765b-140">Element</span></span>|<span data-ttu-id="e765b-141">描述</span><span class="sxs-lookup"><span data-stu-id="e765b-141">Description</span></span>|  
|-------------|-----------------|  
|`(?<char>\w)`|<span data-ttu-id="e765b-142">匹配字词字符，并将结果分配到 `char` 捕获组。</span><span class="sxs-lookup"><span data-stu-id="e765b-142">Match a word character and assign it to a capturing group named `char`.</span></span>|  
|`\k<char>`|<span data-ttu-id="e765b-143">匹配下一个与 `char` 捕获组的值相同的字符。</span><span class="sxs-lookup"><span data-stu-id="e765b-143">Match the next character that is the same as the value of the `char` capturing group.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
 [!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]  
  
 <span data-ttu-id="e765b-144">请注意，*name* 也可以是数字的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="e765b-144">Note that *name* can also be the string representation of a number.</span></span> <span data-ttu-id="e765b-145">例如，下面的示例使用正则表达式 `(?<2>\w)\k<2>` 查找字符串中双写的单词字符。</span><span class="sxs-lookup"><span data-stu-id="e765b-145">For example, the following example uses the regular expression `(?<2>\w)\k<2>` to find doubled word characters in a string.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
 [!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]  
  
## <a name="what-backreferences-match"></a><span data-ttu-id="e765b-146">反向引用匹配什么内容</span><span class="sxs-lookup"><span data-stu-id="e765b-146">What Backreferences Match</span></span>  
 <span data-ttu-id="e765b-147">反向引用引用组的最新定义（从左向右匹配时，最靠近左侧的定义）。</span><span class="sxs-lookup"><span data-stu-id="e765b-147">A backreference refers to the most recent definition of a group (the definition most immediately to the left, when matching left to right).</span></span> <span data-ttu-id="e765b-148">当组建立多个捕获时，反向引用会引用最新的捕获。</span><span class="sxs-lookup"><span data-stu-id="e765b-148">When a group makes multiple captures, a backreference refers to the most recent capture.</span></span>  
  
 <span data-ttu-id="e765b-149">下面的示例包含正则表达式模式 `(?<1>a)(?<1>\1b)*`，该模式重新定义 \1 命名组。</span><span class="sxs-lookup"><span data-stu-id="e765b-149">The following example includes a regular expression pattern, `(?<1>a)(?<1>\1b)*`, which redefines the \1 named group.</span></span> <span data-ttu-id="e765b-150">下表描述了正则表达式中的每个模式。</span><span class="sxs-lookup"><span data-stu-id="e765b-150">The following table describes each pattern in the regular expression.</span></span>  
  
|<span data-ttu-id="e765b-151">模式</span><span class="sxs-lookup"><span data-stu-id="e765b-151">Pattern</span></span>|<span data-ttu-id="e765b-152">描述</span><span class="sxs-lookup"><span data-stu-id="e765b-152">Description</span></span>|  
|-------------|-----------------|  
|`(?<1>a)`|<span data-ttu-id="e765b-153">匹配字符“a”，并将结果分配到 `1` 捕获组。</span><span class="sxs-lookup"><span data-stu-id="e765b-153">Match the character "a" and assign the result to the capturing group named `1`.</span></span>|  
|`(?<1>\1b)*`|<span data-ttu-id="e765b-154">匹配 `1` 组的 0 或 1 个值以及“b”，并将结果分配到 `1` 捕获组。</span><span class="sxs-lookup"><span data-stu-id="e765b-154">Match 0 or 1 occurrence of the group named `1` along with a "b", and assign the result to the capturing group named `1`.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
 [!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]  
  
 <span data-ttu-id="e765b-155">在比较正则表达式与输入字符串（“aababb”）时，正则表达式引擎执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e765b-155">In comparing the regular expression with the input string ("aababb"), the regular expression engine performs the following operations:</span></span>  
  
1.  <span data-ttu-id="e765b-156">从该字符串的开头开始，成功将“a”与表达式 `(?<1>a)` 匹配。</span><span class="sxs-lookup"><span data-stu-id="e765b-156">It starts at the beginning of the string, and successfully matches "a" with the expression `(?<1>a)`.</span></span> <span data-ttu-id="e765b-157">此时，`1` 组的值为“a”。</span><span class="sxs-lookup"><span data-stu-id="e765b-157">The value of the `1` group is now "a".</span></span>  
  
2.  <span data-ttu-id="e765b-158">继续匹配第二个字符，成功将字符串“ab”与表达式 `\1b` 或“ab”匹配。</span><span class="sxs-lookup"><span data-stu-id="e765b-158">It advances to the second character, and successfully matches the string "ab" with the expression `\1b`, or "ab".</span></span> <span data-ttu-id="e765b-159">然后，将结果“ab”分配到 `\1`。</span><span class="sxs-lookup"><span data-stu-id="e765b-159">It then assigns the result, "ab" to `\1`.</span></span>  
  
3.  <span data-ttu-id="e765b-160">继续匹配第四个字符。</span><span class="sxs-lookup"><span data-stu-id="e765b-160">It advances to the fourth character.</span></span> <span data-ttu-id="e765b-161">表达式 `(?<1>\1b)` 要匹配零次或多次，因此会成功将字符串“abb”与表达式 `\1b` 匹配。</span><span class="sxs-lookup"><span data-stu-id="e765b-161">The expression `(?<1>\1b)` is to be matched zero or more times, so it successfully matches the string "abb" with the expression `\1b`.</span></span> <span data-ttu-id="e765b-162">然后，将结果“abb”分配回到 `\1`。</span><span class="sxs-lookup"><span data-stu-id="e765b-162">It assigns the result, "abb", back to `\1`.</span></span>  
  
 <span data-ttu-id="e765b-163">在本示例中，`*` 是循环限定符 -- 它将被重复计算，直到正则表达式引擎不能与它定义的模式匹配为止。</span><span class="sxs-lookup"><span data-stu-id="e765b-163">In this example, `*` is a looping quantifier -- it is evaluated repeatedly until the regular expression engine cannot match the pattern it defines.</span></span> <span data-ttu-id="e765b-164">循环限定符不会清除组定义。</span><span class="sxs-lookup"><span data-stu-id="e765b-164">Looping quantifiers do not clear group definitions.</span></span>  
  
 <span data-ttu-id="e765b-165">如果某个组尚未捕获任何子字符串，则对该组的反向引用是不确定的，永远不会匹配。</span><span class="sxs-lookup"><span data-stu-id="e765b-165">If a group has not captured any substrings, a backreference to that group is undefined and never matches.</span></span> <span data-ttu-id="e765b-166">下面展示了正则表达式模式 `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b` 的定义：</span><span class="sxs-lookup"><span data-stu-id="e765b-166">This is illustrated by the regular expression pattern `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, which is defined as follows:</span></span>  
  
|<span data-ttu-id="e765b-167">模式</span><span class="sxs-lookup"><span data-stu-id="e765b-167">Pattern</span></span>|<span data-ttu-id="e765b-168">描述</span><span class="sxs-lookup"><span data-stu-id="e765b-168">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="e765b-169">在单词边界处开始匹配。</span><span class="sxs-lookup"><span data-stu-id="e765b-169">Begin the match on a word boundary.</span></span>|  
|`(\p{Lu}{2})`|<span data-ttu-id="e765b-170">匹配两个大写字母。</span><span class="sxs-lookup"><span data-stu-id="e765b-170">Match two uppercase letters.</span></span> <span data-ttu-id="e765b-171">这是第一个捕获组。</span><span class="sxs-lookup"><span data-stu-id="e765b-171">This is the first capturing group.</span></span>|  
|`(\d{2})?`|<span data-ttu-id="e765b-172">匹配两个十进制数的零个或一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="e765b-172">Match zero or one occurrence of two decimal digits.</span></span> <span data-ttu-id="e765b-173">这是第二个捕获组。</span><span class="sxs-lookup"><span data-stu-id="e765b-173">This is the second capturing group.</span></span>|  
|`(\p{Lu}{2})`|<span data-ttu-id="e765b-174">匹配两个大写字母。</span><span class="sxs-lookup"><span data-stu-id="e765b-174">Match two uppercase letters.</span></span> <span data-ttu-id="e765b-175">这是第三个捕获组。</span><span class="sxs-lookup"><span data-stu-id="e765b-175">This is the third capturing group.</span></span>|  
|`\b`|<span data-ttu-id="e765b-176">在单词边界处结束匹配。</span><span class="sxs-lookup"><span data-stu-id="e765b-176">End the match on a word boundary.</span></span>|  
  
 <span data-ttu-id="e765b-177">输入字符串可以匹配此正则表达式，即使第二个捕获组定义的两个十进制数字都不存在。</span><span class="sxs-lookup"><span data-stu-id="e765b-177">An input string can match this regular expression even if the two decimal digits that are defined by the second capturing group are not present.</span></span> <span data-ttu-id="e765b-178">下面的示例显示了即使匹配成功，也仍会在两个成功的捕获组之间找到空捕获组。</span><span class="sxs-lookup"><span data-stu-id="e765b-178">The following example shows that even though the match is successful, an empty capturing group is found between two successful capturing groups.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference5.cs#5)]
 [!code-vb[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="e765b-179">请参阅</span><span class="sxs-lookup"><span data-stu-id="e765b-179">See Also</span></span>  
 [<span data-ttu-id="e765b-180">正则表达式语言 - 快速参考</span><span class="sxs-lookup"><span data-stu-id="e765b-180">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
