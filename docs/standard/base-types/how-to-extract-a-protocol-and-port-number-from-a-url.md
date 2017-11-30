---
title: "如何：从 URL 中提取协议和端口号"
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
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10ab05ac8b24c0658be2f27809137c6b0bd4834f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a><span data-ttu-id="85c03-102">如何：从 URL 中提取协议和端口号</span><span class="sxs-lookup"><span data-stu-id="85c03-102">How to: Extract a Protocol and Port Number from a URL</span></span>
<span data-ttu-id="85c03-103">下面的示例从 URL 中提取协议和端口号。</span><span class="sxs-lookup"><span data-stu-id="85c03-103">The following example extracts a protocol and port number from a URL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85c03-104">示例</span><span class="sxs-lookup"><span data-stu-id="85c03-104">Example</span></span>  
 <span data-ttu-id="85c03-105">该示例使用<xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>方法返回的协议跟端口号后跟一个冒号。</span><span class="sxs-lookup"><span data-stu-id="85c03-105">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method to return the protocol followed by a colon followed by the port number.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 <span data-ttu-id="85c03-106">正则表达式模式 `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` 可按下表中的方式解释。</span><span class="sxs-lookup"><span data-stu-id="85c03-106">The regular expression pattern `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="85c03-107">模式</span><span class="sxs-lookup"><span data-stu-id="85c03-107">Pattern</span></span>|<span data-ttu-id="85c03-108">描述</span><span class="sxs-lookup"><span data-stu-id="85c03-108">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="85c03-109">从字符串的开头部分开始匹配。</span><span class="sxs-lookup"><span data-stu-id="85c03-109">Begin the match at the start of the string.</span></span>|  
|`(?<proto>\w+)`|<span data-ttu-id="85c03-110">匹配一个或多个单词字符。</span><span class="sxs-lookup"><span data-stu-id="85c03-110">Match one or more word characters.</span></span> <span data-ttu-id="85c03-111">此组命名`proto`。</span><span class="sxs-lookup"><span data-stu-id="85c03-111">Name this group `proto`.</span></span>|  
|`://`|<span data-ttu-id="85c03-112">匹配后跟两个正斜线的冒号。</span><span class="sxs-lookup"><span data-stu-id="85c03-112">Match a colon followed by two slash marks.</span></span>|  
|`[^/]+?`|<span data-ttu-id="85c03-113">匹配正斜线以外的任何字符的一次或多次出现（但尽可能少）。</span><span class="sxs-lookup"><span data-stu-id="85c03-113">Match one or more occurrences (but as few as possible) of any character other than a slash mark.</span></span>|  
|`(?<port>:\d+)?`|<span data-ttu-id="85c03-114">匹配后跟一个或多个数字字符的冒号的零次或一次出现。</span><span class="sxs-lookup"><span data-stu-id="85c03-114">Match zero or one occurrence of a colon followed by one or more digit characters.</span></span> <span data-ttu-id="85c03-115">此组命名`port`。</span><span class="sxs-lookup"><span data-stu-id="85c03-115">Name this group `port`.</span></span>|  
|`/`|<span data-ttu-id="85c03-116">匹配正斜线。</span><span class="sxs-lookup"><span data-stu-id="85c03-116">Match a slash mark.</span></span>|  
  
 <span data-ttu-id="85c03-117"><xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>方法会扩展到`${proto}${port}`替换序列，串联两个已命名的组捕获在正则表达式模式中的值。</span><span class="sxs-lookup"><span data-stu-id="85c03-117">The <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method expands the `${proto}${port}` replacement sequence, which concatenates the value of the two named groups captured in the regular expression pattern.</span></span> <span data-ttu-id="85c03-118">它是到显式连接字符串的结果从返回的集合对象中检索到一个便捷替代方式<xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="85c03-118">It is a convenient alternative to explicitly concatenating the strings retrieved from the collection object returned by the <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="85c03-119">该示例使用<xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>带有两个替换方法`${proto}`和`${port}`、 输出字符串中包含的捕获的组。</span><span class="sxs-lookup"><span data-stu-id="85c03-119">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method with two substitutions, `${proto}` and `${port}`, to include the captured groups in the output string.</span></span> <span data-ttu-id="85c03-120">您可以捕获的组匹配项的从<xref:System.Text.RegularExpressions.GroupCollection>对象相反，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="85c03-120">You can retrieve the captured groups from the match's <xref:System.Text.RegularExpressions.GroupCollection> object instead, as the following code shows.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="85c03-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85c03-121">See Also</span></span>  
 [<span data-ttu-id="85c03-122">.NET 正则表达式</span><span class="sxs-lookup"><span data-stu-id="85c03-122">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
