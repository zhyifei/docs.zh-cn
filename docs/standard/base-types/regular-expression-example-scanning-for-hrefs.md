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
# <a name="regular-expression-example-scanning-for-hrefs"></a>正则表达式示例：扫描 HREF
下面的示例搜索输入字符串并显示所有 href="…" 的值和它们在字符串中的位置。  
  
## <a name="the-regex-object"></a>Regex 对象  
 因为`DumpHRefs`方法可以从用户代码调用多次，它使用`static`(`Shared`在 Visual Basic 中)<xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType>方法。 这允许正则表达式引擎缓存的正则表达式，并可避免实例化一个新的开销<xref:System.Text.RegularExpressions.Regex>对象每次调用方法。 A<xref:System.Text.RegularExpressions.Match>对象然后用于循环访问字符串中的所有匹配项。  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 下面的示例因而演示 `DumpHRefs` 方法的调用。  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 正则表达式模式 `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` 的含义如下表所示。  
  
|模式|描述|  
|-------------|-----------------|  
|`href`|匹配文本字符串“href”。 匹配不区分大小写。|  
|`\s*`|匹配零个或多个空白字符。|  
|`=`|匹配等号。|  
|`\s*`|匹配零个或多个空白字符。|  
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|与以下项之一匹配而不将结果分配给捕获的组：<br /><br /> -A 引号或单引号后, 跟一个引号或单引号后, 跟一个引号或单引号以外的任意字符的零个或多个。 名为 `1` 的组包含在此模式。<br />的一个或多个非空白字符。 名为 `1` 的组包含在此模式。|  
|`(?<1>[^"']*)`|将零个或多个引号或单引号以外的任意字符分配给名为 `1` 的捕获组。|  
|`"(?<1>\S+)`|将一个或多个非空白字符分配给名为 `1` 的捕获组。|  
  
## <a name="match-result-class"></a>匹配结果类  
 搜索结果将存储在<xref:System.Text.RegularExpressions.Match>类，该类提供访问所有搜索所提取的子字符串。 它还会记住要搜索的字符串和正则表达式中使用，以便它可以调用<xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>方法来执行的最后一个结束的地方开始另一个搜索。  
  
## <a name="explicitly-named-captures"></a>显式命名的捕获  
 在传统正则表达式中，捕获圆括号会自动按顺序编号。 这会导致两个问题。 首先，如果通过插入或删除一组圆括号修改正则表达式，则必须重新编写引用带编号捕获的所有代码才能反映新编号。 其次，由于不同的圆括号组通常用于为可接受的匹配项提供两个替代表达式，则可能难以确定这两个表达式中的哪个表达式实际返回了结果。  
  
 若要解决这些问题，<xref:System.Text.RegularExpressions.Regex>类支持语法`(?<name>…)`将匹配捕获到指定的槽 （可以使用字符串或整数命名槽; 可以更快地回调整数）。 因此，相同字符串的替代匹配全都可以定向到相同位置。 发生冲突时，放入槽中的最后一个匹配项是成功的匹配项。 （但是，提供了适用于单个槽的多个匹配项的完整列表。 请参阅<xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType>有关详细信息的集合。)  
  
## <a name="see-also"></a>另请参阅  
 [.NET 正则表达式](../../../docs/standard/base-types/regular-expressions.md)
