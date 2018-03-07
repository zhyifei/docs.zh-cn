---
title: "将 .NET Framework 类型转换为字符串"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6ca134e13593fdacd759b0000e0e159f76ea067f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="converting-net-framework-types-to-strings"></a><span data-ttu-id="3ef45-102">将 .NET Framework 类型转换为字符串</span><span class="sxs-lookup"><span data-stu-id="3ef45-102">Converting .NET Framework Types to Strings</span></span>
<span data-ttu-id="3ef45-103">若要将 .NET Framework 类型转换为字符串，请使用 ToString 方法。</span><span class="sxs-lookup"><span data-stu-id="3ef45-103">If you want to convert a .NET Framework type to a string, use the **ToString** method.</span></span> <span data-ttu-id="3ef45-104">ToString 方法返回传入的类型的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="3ef45-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="3ef45-105">下表列出了以映射到 XML 架构 (XSD) 规范的格式返回字符串的 .NET Framework 类型。</span><span class="sxs-lookup"><span data-stu-id="3ef45-105">The following table lists the .NET Framework types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="3ef45-106">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="3ef45-106">.NET Framework type</span></span>|<span data-ttu-id="3ef45-107">返回的字符串类型</span><span class="sxs-lookup"><span data-stu-id="3ef45-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="3ef45-108">Boolean</span><span class="sxs-lookup"><span data-stu-id="3ef45-108">Boolean</span></span>|<span data-ttu-id="3ef45-109">“true”、“false”</span><span class="sxs-lookup"><span data-stu-id="3ef45-109">"true", "false"</span></span>|  
|<span data-ttu-id="3ef45-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="3ef45-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="3ef45-111">“INF”</span><span class="sxs-lookup"><span data-stu-id="3ef45-111">"INF"</span></span>|  
|<span data-ttu-id="3ef45-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="3ef45-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="3ef45-113">“-INF”</span><span class="sxs-lookup"><span data-stu-id="3ef45-113">"-INF"</span></span>|  
|<span data-ttu-id="3ef45-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="3ef45-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="3ef45-115">“INF”</span><span class="sxs-lookup"><span data-stu-id="3ef45-115">"INF"</span></span>|  
|<span data-ttu-id="3ef45-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="3ef45-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="3ef45-117">“-INF”</span><span class="sxs-lookup"><span data-stu-id="3ef45-117">"-INF"</span></span>|  
|<span data-ttu-id="3ef45-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="3ef45-118">DateTime</span></span>|<span data-ttu-id="3ef45-119">格式为 yyyy-MM-ddTHH:mm:sszzzzzz 及其子集。</span><span class="sxs-lookup"><span data-stu-id="3ef45-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="3ef45-120">Timespan</span><span class="sxs-lookup"><span data-stu-id="3ef45-120">Timespan</span></span>|<span data-ttu-id="3ef45-121">格式是 PnYnMnTnHnMnS，例如，`P2Y10M15DT10H30M20S` 表示长 2 年 10 个月 15 天 10 小时 30 分钟 20 秒的持续时间。</span><span class="sxs-lookup"><span data-stu-id="3ef45-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ef45-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ef45-122">See Also</span></span>  
 [<span data-ttu-id="3ef45-123">XML 数据类型转换</span><span class="sxs-lookup"><span data-stu-id="3ef45-123">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="3ef45-124">将字符串转换为 .NET Framework 数据类型</span><span class="sxs-lookup"><span data-stu-id="3ef45-124">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
