---
title: 224 - MessageThrottleAtSeventyPercent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e2f96aea0df629c24eb9d795a4409cae6a9c9aa9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="224---messagethrottleatseventypercent"></a><span data-ttu-id="7e4ca-102">224 - MessageThrottleAtSeventyPercent</span><span class="sxs-lookup"><span data-stu-id="7e4ca-102">224 - MessageThrottleAtSeventyPercent</span></span>
## <a name="properties"></a><span data-ttu-id="7e4ca-103">属性</span><span class="sxs-lookup"><span data-stu-id="7e4ca-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7e4ca-104">ID</span><span class="sxs-lookup"><span data-stu-id="7e4ca-104">ID</span></span>|<span data-ttu-id="7e4ca-105">224</span><span class="sxs-lookup"><span data-stu-id="7e4ca-105">224</span></span>|  
|<span data-ttu-id="7e4ca-106">关键字</span><span class="sxs-lookup"><span data-stu-id="7e4ca-106">Keywords</span></span>|<span data-ttu-id="7e4ca-107">EndToEndMonitoring、HealthMonitoring、疑难解答、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7e4ca-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="7e4ca-108">级别</span><span class="sxs-lookup"><span data-stu-id="7e4ca-108">Level</span></span>|<span data-ttu-id="7e4ca-109">警告</span><span class="sxs-lookup"><span data-stu-id="7e4ca-109">Warning</span></span>|  
|<span data-ttu-id="7e4ca-110">通道</span><span class="sxs-lookup"><span data-stu-id="7e4ca-110">Channel</span></span>|<span data-ttu-id="7e4ca-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="7e4ca-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7e4ca-112">描述</span><span class="sxs-lookup"><span data-stu-id="7e4ca-112">Description</span></span>  
 <span data-ttu-id="7e4ca-113">当超出某个主服务中止值时，将发出 `MessageThrottleExceeded` 事件。</span><span class="sxs-lookup"><span data-stu-id="7e4ca-113">When one of the main service throttles has been exceeded, the `MessageThrottleExceeded` event is emitted.</span></span> <span data-ttu-id="7e4ca-114">当活动峰值变慢且当前中止值达到当前限制值的 70% 时，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="7e4ca-114">When the spike of activity slows and the current value of the throttle is at 70 percent of the current limit then this event is emitted.</span></span> <span data-ttu-id="7e4ca-115">请注意，仅在活动变慢时才发出一次此事件。</span><span class="sxs-lookup"><span data-stu-id="7e4ca-115">Note that this event is only emitted once as the activity is slowing.</span></span> <span data-ttu-id="7e4ca-116">如果当前值在 70% 标记的附近波动（例如，70,69,70,71,70,69），则只有第一次出现的 70% 会导致发出事件。</span><span class="sxs-lookup"><span data-stu-id="7e4ca-116">If the current value hovers at the 70 percent mark, (for example, 70,69,70,71,70,69), only the first occurrence of 70 percent results in an event.</span></span> <span data-ttu-id="7e4ca-117">在发出此事件后，如果将来出现超出中止值的情况，则也会导致发出 `MessageThrottleExceeded` 事件。</span><span class="sxs-lookup"><span data-stu-id="7e4ca-117">After this event is emitted, future occurrences of exceeding the throttle's limit result in a `MessageThrottleExceeded` event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7e4ca-118">消息</span><span class="sxs-lookup"><span data-stu-id="7e4ca-118">Message</span></span>  
 <span data-ttu-id="7e4ca-119">“%2”的“%1”中止值为 70%%。</span><span class="sxs-lookup"><span data-stu-id="7e4ca-119">The '%1' throttle limit of '%2' is at 70%%.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7e4ca-120">详细信息</span><span class="sxs-lookup"><span data-stu-id="7e4ca-120">Details</span></span>  
  
|<span data-ttu-id="7e4ca-121">数据项名称</span><span class="sxs-lookup"><span data-stu-id="7e4ca-121">Data Item Name</span></span>|<span data-ttu-id="7e4ca-122">数据项类型</span><span class="sxs-lookup"><span data-stu-id="7e4ca-122">Data Item Type</span></span>|<span data-ttu-id="7e4ca-123">描述</span><span class="sxs-lookup"><span data-stu-id="7e4ca-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7e4ca-124">中止值名称</span><span class="sxs-lookup"><span data-stu-id="7e4ca-124">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="7e4ca-125">超过的中止值的名称。</span><span class="sxs-lookup"><span data-stu-id="7e4ca-125">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="7e4ca-126">`MaxConcurrentCalls`、`MaxConcurrentInstances` 或 `MaxConcurrentSessions`。</span><span class="sxs-lookup"><span data-stu-id="7e4ca-126">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="7e4ca-127">限制值</span><span class="sxs-lookup"><span data-stu-id="7e4ca-127">Limit</span></span>|`xs:long`|<span data-ttu-id="7e4ca-128">当前配置的中止值限制。</span><span class="sxs-lookup"><span data-stu-id="7e4ca-128">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="7e4ca-129">HostReference</span><span class="sxs-lookup"><span data-stu-id="7e4ca-129">HostReference</span></span>|`xs:string`|<span data-ttu-id="7e4ca-130">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="7e4ca-130">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="7e4ca-131">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="7e4ca-131">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="7e4ca-132">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="7e4ca-132">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="7e4ca-133">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7e4ca-133">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7e4ca-134">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="7e4ca-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
