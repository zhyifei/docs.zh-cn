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
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bc9db7317c7a73f70a2cb83322b8b3a4c3771b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-example-scanning-for-hrefs"></a><span data-ttu-id="b2b44-102">正则表达式示例：扫描 HREF</span><span class="sxs-lookup"><span data-stu-id="b2b44-102">Regular Expression Example: Scanning for HREFs</span></span>
<span data-ttu-id="b2b44-103">下面的示例搜索输入字符串并显示所有 href="…" 的值和它们在字符串中的位置。</span><span class="sxs-lookup"><span data-stu-id="b2b44-103">The following example searches an input string and displays all the href="…" values and their locations in the string.</span></span>  
  
## <a name="the-regex-object"></a><span data-ttu-id="b2b44-104">Regex 对象</span><span class="sxs-lookup"><span data-stu-id="b2b44-104">The Regex Object</span></span>  
 <span data-ttu-id="b2b44-105">因为`DumpHRefs`方法可以从用户代码调用多次，它使用`static`(`Shared`在 Visual Basic 中)<xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="b2b44-105">Because the `DumpHRefs` method can be called multiple times from user code, it uses the `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b2b44-106">这允许正则表达式引擎缓存的正则表达式，并可避免实例化一个新的开销<xref:System.Text.RegularExpressions.Regex>对象每次调用方法。</span><span class="sxs-lookup"><span data-stu-id="b2b44-106">This enables the regular expression engine to cache the regular expression and avoids the overhead of instantiating a new <xref:System.Text.RegularExpressions.Regex> object each time the method is called.</span></span> <span data-ttu-id="b2b44-107">A<xref:System.Text.RegularExpressions.Match>对象然后用于循环访问字符串中的所有匹配项。</span><span class="sxs-lookup"><span data-stu-id="b2b44-107">A <xref:System.Text.RegularExpressions.Match> object is then used to iterate through all matches in the string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 <span data-ttu-id="b2b44-108">下面的示例因而演示 `DumpHRefs` 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="b2b44-108">The following example then illustrates a call to the `DumpHRefs` method.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 <span data-ttu-id="b2b44-109">正则表达式模式 `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` 的含义如下表所示。</span><span class="sxs-lookup"><span data-stu-id="b2b44-109">The regular expression pattern `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="b2b44-110">模式</span><span class="sxs-lookup"><span data-stu-id="b2b44-110">Pattern</span></span>|<span data-ttu-id="b2b44-111">描述</span><span class="sxs-lookup"><span data-stu-id="b2b44-111">Description</span></span>|  
|-------------|-----------------|  
|`href`|<span data-ttu-id="b2b44-112">匹配文本字符串“href”。</span><span class="sxs-lookup"><span data-stu-id="b2b44-112">Match the literal string "href".</span></span> <span data-ttu-id="b2b44-113">匹配不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b2b44-113">The match is case-insensitive.</span></span>|  
|`\s*`|<span data-ttu-id="b2b44-114">匹配零个或多个空白字符。</span><span class="sxs-lookup"><span data-stu-id="b2b44-114">Match zero or more white-space characters.</span></span>|  
|`=`|<span data-ttu-id="b2b44-115">匹配等号。</span><span class="sxs-lookup"><span data-stu-id="b2b44-115">Match the equals sign.</span></span>|  
|`\s*`|<span data-ttu-id="b2b44-116">匹配零个或多个空白字符。</span><span class="sxs-lookup"><span data-stu-id="b2b44-116">Match zero or more white-space characters.</span></span>|  
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|<span data-ttu-id="b2b44-117">与以下项之一匹配而不将结果分配给捕获的组：</span><span class="sxs-lookup"><span data-stu-id="b2b44-117">Match one of the following without assigning the result to a captured group:</span></span><br /><br /> <span data-ttu-id="b2b44-118">-A 引号或单引号后, 跟一个引号或单引号后, 跟一个引号或单引号以外的任意字符的零个或多个。</span><span class="sxs-lookup"><span data-stu-id="b2b44-118">-   A quotation mark or apostrophe, followed by zero or more occurrences of any character other than a quotation mark or apostrophe, followed by a quotation mark or apostrophe.</span></span> <span data-ttu-id="b2b44-119">名为 `1` 的组包含在此模式。</span><span class="sxs-lookup"><span data-stu-id="b2b44-119">The group named `1` is included in this pattern.</span></span><br /><span data-ttu-id="b2b44-120">的一个或多个非空白字符。</span><span class="sxs-lookup"><span data-stu-id="b2b44-120">-   One or more non-white-space characters.</span></span> <span data-ttu-id="b2b44-121">名为 `1` 的组包含在此模式。</span><span class="sxs-lookup"><span data-stu-id="b2b44-121">The group named `1` is included in this pattern.</span></span>|  
|`(?<1>[^"']*)`|<span data-ttu-id="b2b44-122">将零个或多个引号或单引号以外的任意字符分配给名为 `1` 的捕获组。</span><span class="sxs-lookup"><span data-stu-id="b2b44-122">Assign zero or more occurrences of any character other than a quotation mark or apostrophe to the capturing group named `1`.</span></span>|  
|`"(?<1>\S+)`|<span data-ttu-id="b2b44-123">将一个或多个非空白字符分配给名为 `1` 的捕获组。</span><span class="sxs-lookup"><span data-stu-id="b2b44-123">Assign one or more non-white-space characters to the capturing group named `1`.</span></span>|  
  
## <a name="match-result-class"></a><span data-ttu-id="b2b44-124">匹配结果类</span><span class="sxs-lookup"><span data-stu-id="b2b44-124">Match Result Class</span></span>  
 <span data-ttu-id="b2b44-125">搜索结果将存储在<xref:System.Text.RegularExpressions.Match>类，该类提供访问所有搜索所提取的子字符串。</span><span class="sxs-lookup"><span data-stu-id="b2b44-125">The results of a search are stored in the <xref:System.Text.RegularExpressions.Match> class, which provides access to all the substrings extracted by the search.</span></span> <span data-ttu-id="b2b44-126">它还会记住要搜索的字符串和正则表达式中使用，以便它可以调用<xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>方法来执行的最后一个结束的地方开始另一个搜索。</span><span class="sxs-lookup"><span data-stu-id="b2b44-126">It also remembers the string being searched and the regular expression being used, so it can call the <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> method to perform another search starting where the last one ended.</span></span>  
  
## <a name="explicitly-named-captures"></a><span data-ttu-id="b2b44-127">显式命名的捕获</span><span class="sxs-lookup"><span data-stu-id="b2b44-127">Explicitly Named Captures</span></span>  
 <span data-ttu-id="b2b44-128">在传统正则表达式中，捕获圆括号会自动按顺序编号。</span><span class="sxs-lookup"><span data-stu-id="b2b44-128">In traditional regular expressions, capturing parentheses are automatically numbered sequentially.</span></span> <span data-ttu-id="b2b44-129">这会导致两个问题。</span><span class="sxs-lookup"><span data-stu-id="b2b44-129">This leads to two problems.</span></span> <span data-ttu-id="b2b44-130">首先，如果通过插入或删除一组圆括号修改正则表达式，则必须重新编写引用带编号捕获的所有代码才能反映新编号。</span><span class="sxs-lookup"><span data-stu-id="b2b44-130">First, if a regular expression is modified by inserting or removing a set of parentheses, all code that refers to the numbered captures must be rewritten to reflect the new numbering.</span></span> <span data-ttu-id="b2b44-131">其次，由于不同的圆括号组通常用于为可接受的匹配项提供两个替代表达式，则可能难以确定这两个表达式中的哪个表达式实际返回了结果。</span><span class="sxs-lookup"><span data-stu-id="b2b44-131">Second, because different sets of parentheses often are used to provide two alternative expressions for an acceptable match, it might be difficult to determine which of the two expressions actually returned a result.</span></span>  
  
 <span data-ttu-id="b2b44-132">若要解决这些问题，<xref:System.Text.RegularExpressions.Regex>类支持语法`(?<name>…)`将匹配捕获到指定的槽 （可以使用字符串或整数命名槽; 可以更快地回调整数）。</span><span class="sxs-lookup"><span data-stu-id="b2b44-132">To address these problems, the <xref:System.Text.RegularExpressions.Regex> class supports the syntax `(?<name>…)` for capturing a match into a specified slot (the slot can be named using a string or an integer; integers can be recalled more quickly).</span></span> <span data-ttu-id="b2b44-133">因此，相同字符串的替代匹配全都可以定向到相同位置。</span><span class="sxs-lookup"><span data-stu-id="b2b44-133">Thus, alternative matches for the same string all can be directed to the same place.</span></span> <span data-ttu-id="b2b44-134">发生冲突时，放入槽中的最后一个匹配项是成功的匹配项。</span><span class="sxs-lookup"><span data-stu-id="b2b44-134">In case of a conflict, the last match dropped into a slot is the successful match.</span></span> <span data-ttu-id="b2b44-135">（但是，提供了适用于单个槽的多个匹配项的完整列表。</span><span class="sxs-lookup"><span data-stu-id="b2b44-135">(However, a complete list of multiple matches for a single slot is available.</span></span> <span data-ttu-id="b2b44-136">请参阅<xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType>有关详细信息的集合。)</span><span class="sxs-lookup"><span data-stu-id="b2b44-136">See the <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> collection for details.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b44-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2b44-137">See Also</span></span>  
 [<span data-ttu-id="b2b44-138">.NET 正则表达式</span><span class="sxs-lookup"><span data-stu-id="b2b44-138">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
