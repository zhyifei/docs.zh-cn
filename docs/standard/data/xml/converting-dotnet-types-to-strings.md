---
title: 将 .NET Framework 类型转换为字符串
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98ebc9248b0585295adf12e04dece0fef654c2e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583124"
---
# <a name="converting-net-framework-types-to-strings"></a><span data-ttu-id="e5437-102">将 .NET Framework 类型转换为字符串</span><span class="sxs-lookup"><span data-stu-id="e5437-102">Converting .NET Framework Types to Strings</span></span>
<span data-ttu-id="e5437-103">若要将 .NET Framework 类型转换为字符串，请使用 ToString 方法。</span><span class="sxs-lookup"><span data-stu-id="e5437-103">If you want to convert a .NET Framework type to a string, use the **ToString** method.</span></span> <span data-ttu-id="e5437-104">ToString 方法返回传入的类型的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="e5437-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="e5437-105">下表列出了以映射到 XML 架构 (XSD) 规范的格式返回字符串的 .NET Framework 类型。</span><span class="sxs-lookup"><span data-stu-id="e5437-105">The following table lists the .NET Framework types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="e5437-106">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="e5437-106">.NET Framework type</span></span>|<span data-ttu-id="e5437-107">返回的字符串类型</span><span class="sxs-lookup"><span data-stu-id="e5437-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="e5437-108">Boolean</span><span class="sxs-lookup"><span data-stu-id="e5437-108">Boolean</span></span>|<span data-ttu-id="e5437-109">“true”、“false”</span><span class="sxs-lookup"><span data-stu-id="e5437-109">"true", "false"</span></span>|  
|<span data-ttu-id="e5437-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="e5437-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="e5437-111">“INF”</span><span class="sxs-lookup"><span data-stu-id="e5437-111">"INF"</span></span>|  
|<span data-ttu-id="e5437-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="e5437-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="e5437-113">“-INF”</span><span class="sxs-lookup"><span data-stu-id="e5437-113">"-INF"</span></span>|  
|<span data-ttu-id="e5437-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="e5437-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="e5437-115">“INF”</span><span class="sxs-lookup"><span data-stu-id="e5437-115">"INF"</span></span>|  
|<span data-ttu-id="e5437-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="e5437-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="e5437-117">“-INF”</span><span class="sxs-lookup"><span data-stu-id="e5437-117">"-INF"</span></span>|  
|<span data-ttu-id="e5437-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="e5437-118">DateTime</span></span>|<span data-ttu-id="e5437-119">格式为 yyyy-MM-ddTHH:mm:sszzzzzz 及其子集。</span><span class="sxs-lookup"><span data-stu-id="e5437-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="e5437-120">Timespan</span><span class="sxs-lookup"><span data-stu-id="e5437-120">Timespan</span></span>|<span data-ttu-id="e5437-121">格式是 PnYnMnTnHnMnS，例如，`P2Y10M15DT10H30M20S` 表示长 2 年 10 个月 15 天 10 小时 30 分钟 20 秒的持续时间。</span><span class="sxs-lookup"><span data-stu-id="e5437-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5437-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5437-122">See also</span></span>

- [<span data-ttu-id="e5437-123">XML 数据类型转换</span><span class="sxs-lookup"><span data-stu-id="e5437-123">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)
- [<span data-ttu-id="e5437-124">将字符串转换为 .NET Framework 数据类型</span><span class="sxs-lookup"><span data-stu-id="e5437-124">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
