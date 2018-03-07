---
title: "正则表达式示例：扫描 HREF"
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
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c6da140ea82fc3c6d3f5f3001f37711ffe861370
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="regular-expression-example-scanning-for-hrefs"></a><span data-ttu-id="63839-102">正则表达式示例：扫描 HREF</span><span class="sxs-lookup"><span data-stu-id="63839-102">Regular Expression Example: Scanning for HREFs</span></span>
<span data-ttu-id="63839-103">下面的示例搜索输入字符串并显示所有 href="…" 的值和它们在字符串中的位置。</span><span class="sxs-lookup"><span data-stu-id="63839-103">The following example searches an input string and displays all the href="…" values and their locations in the string.</span></span>  
  
## <a name="the-regex-object"></a><span data-ttu-id="63839-104">Regex 对象</span><span class="sxs-lookup"><span data-stu-id="63839-104">The Regex Object</span></span>  
 <span data-ttu-id="63839-105">因为可以通过用户代码多次调用 `DumpHRefs` 方法，所以它使用 `static`（Visual Basic 中的 `Shared`）<xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="63839-105">Because the `DumpHRefs` method can be called multiple times from user code, it uses the `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="63839-106">这样一来，正则表达式引擎不仅可以缓存正则表达式，还杜绝了每次调用方法时实例化新 <xref:System.Text.RegularExpressions.Regex> 对象产生的开销。</span><span class="sxs-lookup"><span data-stu-id="63839-106">This enables the regular expression engine to cache the regular expression and avoids the overhead of instantiating a new <xref:System.Text.RegularExpressions.Regex> object each time the method is called.</span></span> <span data-ttu-id="63839-107">随后使用 <xref:System.Text.RegularExpressions.Match> 对象循环访问字符串中的所有匹配。</span><span class="sxs-lookup"><span data-stu-id="63839-107">A <xref:System.Text.RegularExpressions.Match> object is then used to iterate through all matches in the string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 <span data-ttu-id="63839-108">下面的示例因而演示 `DumpHRefs` 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="63839-108">The following example then illustrates a call to the `DumpHRefs` method.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 <span data-ttu-id="63839-109">正则表达式模式 `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` 的含义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="63839-109">The regular expression pattern `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="63839-110">模式</span><span class="sxs-lookup"><span data-stu-id="63839-110">Pattern</span></span>|<span data-ttu-id="63839-111">描述</span><span class="sxs-lookup"><span data-stu-id="63839-111">Description</span></span>|  
|-------------|-----------------|  
|`href`|<span data-ttu-id="63839-112">匹配文本字符串“href”。</span><span class="sxs-lookup"><span data-stu-id="63839-112">Match the literal string "href".</span></span> <span data-ttu-id="63839-113">匹配不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="63839-113">The match is case-insensitive.</span></span>|  
|`\s*`|<span data-ttu-id="63839-114">匹配零个或多个空白字符。</span><span class="sxs-lookup"><span data-stu-id="63839-114">Match zero or more white-space characters.</span></span>|  
|`=`|<span data-ttu-id="63839-115">匹配等于号。</span><span class="sxs-lookup"><span data-stu-id="63839-115">Match the equals sign.</span></span>|  
|`\s*`|<span data-ttu-id="63839-116">匹配零个或多个空白字符。</span><span class="sxs-lookup"><span data-stu-id="63839-116">Match zero or more white-space characters.</span></span>|  
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|<span data-ttu-id="63839-117">匹配以下项之一，而不将结果分配到捕获组：</span><span class="sxs-lookup"><span data-stu-id="63839-117">Match one of the following without assigning the result to a captured group:</span></span><br /><br /> <span data-ttu-id="63839-118">-   引号或撇号，后跟零个或多个除引号或撇号以外的任意字符，再后跟引号或撇号。</span><span class="sxs-lookup"><span data-stu-id="63839-118">-   A quotation mark or apostrophe, followed by zero or more occurrences of any character other than a quotation mark or apostrophe, followed by a quotation mark or apostrophe.</span></span> <span data-ttu-id="63839-119">名为 `1` 的组包含在此模式。</span><span class="sxs-lookup"><span data-stu-id="63839-119">The group named `1` is included in this pattern.</span></span><br /><span data-ttu-id="63839-120">-   一个或多个非空格字符。</span><span class="sxs-lookup"><span data-stu-id="63839-120">-   One or more non-white-space characters.</span></span> <span data-ttu-id="63839-121">名为 `1` 的组包含在此模式。</span><span class="sxs-lookup"><span data-stu-id="63839-121">The group named `1` is included in this pattern.</span></span>|  
|`(?<1>[^"']*)`|<span data-ttu-id="63839-122">将零个或多个引号或单引号以外的任意字符分配给名为 `1` 的捕获组。</span><span class="sxs-lookup"><span data-stu-id="63839-122">Assign zero or more occurrences of any character other than a quotation mark or apostrophe to the capturing group named `1`.</span></span>|  
|`"(?<1>\S+)`|<span data-ttu-id="63839-123">将一个或多个非空白字符分配给名为 `1` 的捕获组。</span><span class="sxs-lookup"><span data-stu-id="63839-123">Assign one or more non-white-space characters to the capturing group named `1`.</span></span>|  
  
## <a name="match-result-class"></a><span data-ttu-id="63839-124">匹配结果类</span><span class="sxs-lookup"><span data-stu-id="63839-124">Match Result Class</span></span>  
 <span data-ttu-id="63839-125">搜索结果存储在 <xref:System.Text.RegularExpressions.Match> 类中，此类可访问搜索提取的所有子字符串。</span><span class="sxs-lookup"><span data-stu-id="63839-125">The results of a search are stored in the <xref:System.Text.RegularExpressions.Match> class, which provides access to all the substrings extracted by the search.</span></span> <span data-ttu-id="63839-126">它还会记住搜索的字符串和使用的正则表达式，因此可以调用 <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> 方法，从上一次搜索结束的位置开始执行另一次搜索。</span><span class="sxs-lookup"><span data-stu-id="63839-126">It also remembers the string being searched and the regular expression being used, so it can call the <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> method to perform another search starting where the last one ended.</span></span>  
  
## <a name="explicitly-named-captures"></a><span data-ttu-id="63839-127">显式命名的捕获</span><span class="sxs-lookup"><span data-stu-id="63839-127">Explicitly Named Captures</span></span>  
 <span data-ttu-id="63839-128">在传统正则表达式中，捕获圆括号会自动按顺序编号。</span><span class="sxs-lookup"><span data-stu-id="63839-128">In traditional regular expressions, capturing parentheses are automatically numbered sequentially.</span></span> <span data-ttu-id="63839-129">这会导致两个问题。</span><span class="sxs-lookup"><span data-stu-id="63839-129">This leads to two problems.</span></span> <span data-ttu-id="63839-130">首先，如果通过插入或删除一组圆括号修改正则表达式，则必须重新编写引用带编号捕获的所有代码才能反映新编号。</span><span class="sxs-lookup"><span data-stu-id="63839-130">First, if a regular expression is modified by inserting or removing a set of parentheses, all code that refers to the numbered captures must be rewritten to reflect the new numbering.</span></span> <span data-ttu-id="63839-131">其次，由于不同的圆括号组通常用于为可接受的匹配项提供两个替代表达式，则可能难以确定这两个表达式中的哪个表达式实际返回了结果。</span><span class="sxs-lookup"><span data-stu-id="63839-131">Second, because different sets of parentheses often are used to provide two alternative expressions for an acceptable match, it might be difficult to determine which of the two expressions actually returned a result.</span></span>  
  
 <span data-ttu-id="63839-132">为了解决这些问题，<xref:System.Text.RegularExpressions.Regex> 类支持语法 `(?<name>…)`，以便将匹配捕获到指定槽中（可以使用字符串或整数命名槽；如果使用整数命名，可以更快地召回）。</span><span class="sxs-lookup"><span data-stu-id="63839-132">To address these problems, the <xref:System.Text.RegularExpressions.Regex> class supports the syntax `(?<name>…)` for capturing a match into a specified slot (the slot can be named using a string or an integer; integers can be recalled more quickly).</span></span> <span data-ttu-id="63839-133">因此，相同字符串的替代匹配全都可以定向到相同位置。</span><span class="sxs-lookup"><span data-stu-id="63839-133">Thus, alternative matches for the same string all can be directed to the same place.</span></span> <span data-ttu-id="63839-134">发生冲突时，放入槽中的最后一个匹配项是成功的匹配项。</span><span class="sxs-lookup"><span data-stu-id="63839-134">In case of a conflict, the last match dropped into a slot is the successful match.</span></span> <span data-ttu-id="63839-135">（但是，提供了适用于单个槽的多个匹配项的完整列表。</span><span class="sxs-lookup"><span data-stu-id="63839-135">(However, a complete list of multiple matches for a single slot is available.</span></span> <span data-ttu-id="63839-136">有关详细信息，请参阅 <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> 集合。）</span><span class="sxs-lookup"><span data-stu-id="63839-136">See the <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> collection for details.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63839-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="63839-137">See Also</span></span>  
 [<span data-ttu-id="63839-138">.NET 正则表达式</span><span class="sxs-lookup"><span data-stu-id="63839-138">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
