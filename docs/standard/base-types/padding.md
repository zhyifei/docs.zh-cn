---
title: "填充 .NET 中的字符串"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ea903c1f950e7c226e043c1fa7276a66126b2512
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="padding-strings-in-net"></a>填充 .NET 中的字符串
使用下面的 <xref:System.String> 方法之一，在原始字符串中填充前导或尾随字符，以达到指定总长度，从而新建字符串。 填充字符可以是空格或指定字符，因而显示为右对齐或左对齐。  
  
|方法名称|使用|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|使用前导字符将字符串填充到指定总长度。|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|使用尾随字符将字符串填充到指定总长度。|  
  
## <a name="padleft"></a>PadLeft  
 <xref:System.String.PadLeft%2A?displayProperty=nameWithType> 方法将足够多的前导填充字符连接到原始字符串，以达到指定总长度，从而新建字符串。 <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> 方法使用空格作为填充字符，<xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> 方法支持指定自己的填充字符。  
  
 下面的代码示例使用 <xref:System.String.PadLeft%2A> 方法新建长度为 20 个字符的字符串。 该示例向控制台显示“`--------Hello World!`”。  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a>PadRight  
 <xref:System.String.PadRight%2A?displayProperty=nameWithType> 方法将足够多的尾随填充字符连接到原始字符串，以达到指定总长度，从而新建字符串。 <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> 方法使用空格作为填充字符，<xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> 方法支持指定自己的填充字符。  
  
 下面的代码示例使用 <xref:System.String.PadRight%2A> 方法新建长度为 20 个字符的字符串。 该示例向控制台显示“`Hello World!--------`”。  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a>请参阅  
 [基本字符串操作](../../../docs/standard/base-types/basic-string-operations.md)
