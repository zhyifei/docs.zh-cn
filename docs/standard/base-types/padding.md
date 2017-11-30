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
# <a name="padding-strings-in-net"></a><span data-ttu-id="4c6a8-102">.NET 中的空白字符串</span><span class="sxs-lookup"><span data-stu-id="4c6a8-102">Padding Strings in .NET</span></span>
<span data-ttu-id="4c6a8-103">使用以下项之一<xref:System.String>方法来创建一个新字符串，则用前导空格或尾随到指定的总长度的字符填充原始字符串组成。</span><span class="sxs-lookup"><span data-stu-id="4c6a8-103">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="4c6a8-104">填充字符可以是空格或指定字符，因而显示为右对齐或左对齐。</span><span class="sxs-lookup"><span data-stu-id="4c6a8-104">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>  
  
|<span data-ttu-id="4c6a8-105">方法名称</span><span class="sxs-lookup"><span data-stu-id="4c6a8-105">Method name</span></span>|<span data-ttu-id="4c6a8-106">使用</span><span class="sxs-lookup"><span data-stu-id="4c6a8-106">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="4c6a8-107">使用前导字符将字符串填充到指定总长度。</span><span class="sxs-lookup"><span data-stu-id="4c6a8-107">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="4c6a8-108">使用尾随字符将字符串填充到指定总长度。</span><span class="sxs-lookup"><span data-stu-id="4c6a8-108">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="4c6a8-109">PadLeft</span><span class="sxs-lookup"><span data-stu-id="4c6a8-109">PadLeft</span></span>  
 <span data-ttu-id="4c6a8-110"><xref:System.String.PadLeft%2A?displayProperty=nameWithType>方法通过串联到原始字符串使其达到指定的总长度足够前导填充字符来创建一个新字符串。</span><span class="sxs-lookup"><span data-stu-id="4c6a8-110">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="4c6a8-111"><xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType>方法中的空白区域用作填充字符和<xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType>方法，可指定你自己的填充字符。</span><span class="sxs-lookup"><span data-stu-id="4c6a8-111">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="4c6a8-112">下面的代码示例使用<xref:System.String.PadLeft%2A>方法来创建一个新字符串，长度为 20 个字符。</span><span class="sxs-lookup"><span data-stu-id="4c6a8-112">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="4c6a8-113">该示例向控制台显示“`--------Hello World!`”。</span><span class="sxs-lookup"><span data-stu-id="4c6a8-113">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="4c6a8-114">PadRight</span><span class="sxs-lookup"><span data-stu-id="4c6a8-114">PadRight</span></span>  
 <span data-ttu-id="4c6a8-115"><xref:System.String.PadRight%2A?displayProperty=nameWithType>方法通过串联到原始字符串使其达到指定的总长度足够尾随填充字符来创建一个新字符串。</span><span class="sxs-lookup"><span data-stu-id="4c6a8-115">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="4c6a8-116"><xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType>方法中的空白区域用作填充字符和<xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType>方法，可指定你自己的填充字符。</span><span class="sxs-lookup"><span data-stu-id="4c6a8-116">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="4c6a8-117">下面的代码示例使用<xref:System.String.PadRight%2A>方法来创建一个新字符串，长度为 20 个字符。</span><span class="sxs-lookup"><span data-stu-id="4c6a8-117">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="4c6a8-118">该示例向控制台显示“`Hello World!--------`”。</span><span class="sxs-lookup"><span data-stu-id="4c6a8-118">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="4c6a8-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c6a8-119">See Also</span></span>  
 [<span data-ttu-id="4c6a8-120">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="4c6a8-120">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
