---
title: 将 .NET Framework 类型转换为字符串
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: a63e0175f6660967eb4aa678c6731d353e44e2d5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711072"
---
# <a name="converting-net-framework-types-to-strings"></a><span data-ttu-id="c1bd4-102">将 .NET Framework 类型转换为字符串</span><span class="sxs-lookup"><span data-stu-id="c1bd4-102">Converting .NET Framework Types to Strings</span></span>
<span data-ttu-id="c1bd4-103">若要将 .NET Framework 类型转换为字符串，请使用 ToString  方法。</span><span class="sxs-lookup"><span data-stu-id="c1bd4-103">If you want to convert a .NET Framework type to a string, use the **ToString** method.</span></span> <span data-ttu-id="c1bd4-104">ToString  方法返回传入的类型的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="c1bd4-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="c1bd4-105">下表列出了以映射到 XML 架构 (XSD) 规范的格式返回字符串的 .NET Framework 类型。</span><span class="sxs-lookup"><span data-stu-id="c1bd4-105">The following table lists the .NET Framework types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="c1bd4-106">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="c1bd4-106">.NET Framework type</span></span>|<span data-ttu-id="c1bd4-107">返回的字符串类型</span><span class="sxs-lookup"><span data-stu-id="c1bd4-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="c1bd4-108">Boolean</span><span class="sxs-lookup"><span data-stu-id="c1bd4-108">Boolean</span></span>|<span data-ttu-id="c1bd4-109">“true”、“false”</span><span class="sxs-lookup"><span data-stu-id="c1bd4-109">"true", "false"</span></span>|  
|<span data-ttu-id="c1bd4-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="c1bd4-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="c1bd4-111">“INF”</span><span class="sxs-lookup"><span data-stu-id="c1bd4-111">"INF"</span></span>|  
|<span data-ttu-id="c1bd4-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="c1bd4-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="c1bd4-113">“-INF”</span><span class="sxs-lookup"><span data-stu-id="c1bd4-113">"-INF"</span></span>|  
|<span data-ttu-id="c1bd4-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="c1bd4-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="c1bd4-115">“INF”</span><span class="sxs-lookup"><span data-stu-id="c1bd4-115">"INF"</span></span>|  
|<span data-ttu-id="c1bd4-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="c1bd4-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="c1bd4-117">“-INF”</span><span class="sxs-lookup"><span data-stu-id="c1bd4-117">"-INF"</span></span>|  
|<span data-ttu-id="c1bd4-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="c1bd4-118">DateTime</span></span>|<span data-ttu-id="c1bd4-119">格式为 yyyy-MM-ddTHH:mm:sszzzzzz 及其子集。</span><span class="sxs-lookup"><span data-stu-id="c1bd4-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="c1bd4-120">Timespan</span><span class="sxs-lookup"><span data-stu-id="c1bd4-120">Timespan</span></span>|<span data-ttu-id="c1bd4-121">格式是 PnYnMnTnHnMnS，例如，`P2Y10M15DT10H30M20S` 表示长 2 年 10 个月 15 天 10 小时 30 分钟 20 秒的持续时间。</span><span class="sxs-lookup"><span data-stu-id="c1bd4-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1bd4-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1bd4-122">See also</span></span>

- [<span data-ttu-id="c1bd4-123">XML 数据类型转换</span><span class="sxs-lookup"><span data-stu-id="c1bd4-123">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)
- [<span data-ttu-id="c1bd4-124">将字符串转换为 .NET Framework 数据类型</span><span class="sxs-lookup"><span data-stu-id="c1bd4-124">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
