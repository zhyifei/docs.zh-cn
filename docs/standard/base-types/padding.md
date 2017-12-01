---
title: ".NET 中的空白字符串"
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
- cpp
helpviewer_keywords:
- strings [.NET Framework], padding
- white space
- PadRight method
- PadLeft method
- padding strings
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29cd40645cf06ac9babb4738259938a3da04a155
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="padding-strings-in-net"></a>.NET 中的空白字符串
使用以下项之一<xref:System.String>方法来创建一个新字符串，则用前导空格或尾随到指定的总长度的字符填充原始字符串组成。 填充字符可以是空格或指定字符，因而显示为右对齐或左对齐。  
  
|方法名称|使用|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|使用前导字符将字符串填充到指定总长度。|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|使用尾随字符将字符串填充到指定总长度。|  
  
## <a name="padleft"></a>PadLeft  
 <xref:System.String.PadLeft%2A?displayProperty=nameWithType>方法通过串联到原始字符串使其达到指定的总长度足够前导填充字符来创建一个新字符串。 <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType>方法中的空白区域用作填充字符和<xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType>方法，可指定你自己的填充字符。  
  
 下面的代码示例使用<xref:System.String.PadLeft%2A>方法来创建一个新字符串，长度为 20 个字符。 该示例向控制台显示“`--------Hello World!`”。  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a>PadRight  
 <xref:System.String.PadRight%2A?displayProperty=nameWithType>方法通过串联到原始字符串使其达到指定的总长度足够尾随填充字符来创建一个新字符串。 <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType>方法中的空白区域用作填充字符和<xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType>方法，可指定你自己的填充字符。  
  
 下面的代码示例使用<xref:System.String.PadRight%2A>方法来创建一个新字符串，长度为 20 个字符。 该示例向控制台显示“`Hello World!--------`”。  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a>另请参阅  
 [基本字符串操作](../../../docs/standard/base-types/basic-string-operations.md)
