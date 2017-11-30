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
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a>如何：从 URL 中提取协议和端口号
下面的示例从 URL 中提取协议和端口号。  
  
## <a name="example"></a>示例  
 该示例使用<xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>方法返回的协议跟端口号后跟一个冒号。  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 正则表达式模式 `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` 可按下表中的方式解释。  
  
|模式|描述|  
|-------------|-----------------|  
|`^`|从字符串的开头部分开始匹配。|  
|`(?<proto>\w+)`|匹配一个或多个单词字符。 此组命名`proto`。|  
|`://`|匹配后跟两个正斜线的冒号。|  
|`[^/]+?`|匹配正斜线以外的任何字符的一次或多次出现（但尽可能少）。|  
|`(?<port>:\d+)?`|匹配后跟一个或多个数字字符的冒号的零次或一次出现。 此组命名`port`。|  
|`/`|匹配正斜线。|  
  
 <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>方法会扩展到`${proto}${port}`替换序列，串联两个已命名的组捕获在正则表达式模式中的值。 它是到显式连接字符串的结果从返回的集合对象中检索到一个便捷替代方式<xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>属性。  
  
 该示例使用<xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>带有两个替换方法`${proto}`和`${port}`、 输出字符串中包含的捕获的组。 您可以捕获的组匹配项的从<xref:System.Text.RegularExpressions.GroupCollection>对象相反，如以下代码所示。  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a>另请参阅  
 [.NET 正则表达式](../../../docs/standard/base-types/regular-expressions.md)
