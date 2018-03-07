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
# <a name="padding-strings-in-net"></a><span data-ttu-id="34df2-102">填充 .NET 中的字符串</span><span class="sxs-lookup"><span data-stu-id="34df2-102">Padding Strings in .NET</span></span>
<span data-ttu-id="34df2-103">使用下面的 <xref:System.String> 方法之一，在原始字符串中填充前导或尾随字符，以达到指定总长度，从而新建字符串。</span><span class="sxs-lookup"><span data-stu-id="34df2-103">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="34df2-104">填充字符可以是空格或指定字符，因而显示为右对齐或左对齐。</span><span class="sxs-lookup"><span data-stu-id="34df2-104">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>  
  
|<span data-ttu-id="34df2-105">方法名称</span><span class="sxs-lookup"><span data-stu-id="34df2-105">Method name</span></span>|<span data-ttu-id="34df2-106">使用</span><span class="sxs-lookup"><span data-stu-id="34df2-106">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="34df2-107">使用前导字符将字符串填充到指定总长度。</span><span class="sxs-lookup"><span data-stu-id="34df2-107">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="34df2-108">使用尾随字符将字符串填充到指定总长度。</span><span class="sxs-lookup"><span data-stu-id="34df2-108">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="34df2-109">PadLeft</span><span class="sxs-lookup"><span data-stu-id="34df2-109">PadLeft</span></span>  
 <span data-ttu-id="34df2-110"><xref:System.String.PadLeft%2A?displayProperty=nameWithType> 方法将足够多的前导填充字符连接到原始字符串，以达到指定总长度，从而新建字符串。</span><span class="sxs-lookup"><span data-stu-id="34df2-110">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="34df2-111"><xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> 方法使用空格作为填充字符，<xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> 方法支持指定自己的填充字符。</span><span class="sxs-lookup"><span data-stu-id="34df2-111">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="34df2-112">下面的代码示例使用 <xref:System.String.PadLeft%2A> 方法新建长度为 20 个字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="34df2-112">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="34df2-113">该示例向控制台显示“`--------Hello World!`”。</span><span class="sxs-lookup"><span data-stu-id="34df2-113">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="34df2-114">PadRight</span><span class="sxs-lookup"><span data-stu-id="34df2-114">PadRight</span></span>  
 <span data-ttu-id="34df2-115"><xref:System.String.PadRight%2A?displayProperty=nameWithType> 方法将足够多的尾随填充字符连接到原始字符串，以达到指定总长度，从而新建字符串。</span><span class="sxs-lookup"><span data-stu-id="34df2-115">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="34df2-116"><xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> 方法使用空格作为填充字符，<xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> 方法支持指定自己的填充字符。</span><span class="sxs-lookup"><span data-stu-id="34df2-116">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="34df2-117">下面的代码示例使用 <xref:System.String.PadRight%2A> 方法新建长度为 20 个字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="34df2-117">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="34df2-118">该示例向控制台显示“`Hello World!--------`”。</span><span class="sxs-lookup"><span data-stu-id="34df2-118">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="34df2-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="34df2-119">See Also</span></span>  
 [<span data-ttu-id="34df2-120">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="34df2-120">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
