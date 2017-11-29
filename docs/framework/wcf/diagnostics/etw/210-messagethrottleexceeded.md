---
title: 210 - MessageThrottleExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ca08ea-c11c-4753-946e-98aa820f8711
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2d027f549e86095c732d0e60df3faded44a39fd2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="210---messagethrottleexceeded"></a><span data-ttu-id="61d2b-102">210 - MessageThrottleExceeded</span><span class="sxs-lookup"><span data-stu-id="61d2b-102">210 - MessageThrottleExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="61d2b-103">属性</span><span class="sxs-lookup"><span data-stu-id="61d2b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="61d2b-104">ID</span><span class="sxs-lookup"><span data-stu-id="61d2b-104">ID</span></span>|<span data-ttu-id="61d2b-105">210</span><span class="sxs-lookup"><span data-stu-id="61d2b-105">210</span></span>|  
|<span data-ttu-id="61d2b-106">关键字</span><span class="sxs-lookup"><span data-stu-id="61d2b-106">Keywords</span></span>|<span data-ttu-id="61d2b-107">EndToEndMonitoring、HealthMonitoring、疑难解答、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="61d2b-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="61d2b-108">级别</span><span class="sxs-lookup"><span data-stu-id="61d2b-108">Level</span></span>|<span data-ttu-id="61d2b-109">警告</span><span class="sxs-lookup"><span data-stu-id="61d2b-109">Warning</span></span>|  
|<span data-ttu-id="61d2b-110">通道</span><span class="sxs-lookup"><span data-stu-id="61d2b-110">Channel</span></span>|<span data-ttu-id="61d2b-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="61d2b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="61d2b-112">描述</span><span class="sxs-lookup"><span data-stu-id="61d2b-112">Description</span></span>  
 <span data-ttu-id="61d2b-113">在超过三个主服务控制器中止值之一时，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="61d2b-113">This event is emitted when one of the three main service throttles have been exceeded.</span></span> <span data-ttu-id="61d2b-114">请注意，仅在首次超过中止值时才发出此事件。</span><span class="sxs-lookup"><span data-stu-id="61d2b-114">Note that this event is only emitted when the throttle limit is initially exceeded.</span></span> <span data-ttu-id="61d2b-115">例如，如果并发调用的中止值为 10，则第 11 个并发调用将导致 `MessageThrottleExceeded` 事件。</span><span class="sxs-lookup"><span data-stu-id="61d2b-115">For example, if the throttle limit for concurrent calls is 10, the 11th concurrent call results in a `MessageThrottleExceeded` event.</span></span> <span data-ttu-id="61d2b-116">第 12 个调用不会再次导致事件。</span><span class="sxs-lookup"><span data-stu-id="61d2b-116">The 12th call does not result in another event.</span></span> <span data-ttu-id="61d2b-117">此外，为避免噪声事件流，在中止值附近波动的活动不会导致其他事件。</span><span class="sxs-lookup"><span data-stu-id="61d2b-117">Additionally, to avoid a noisy event stream, activity that hovers around the limit does not result in another event.</span></span> <span data-ttu-id="61d2b-118">在本示例中，如果有 2 个调用完成，则还存在 9 个并发调用。</span><span class="sxs-lookup"><span data-stu-id="61d2b-118">In this example, if a couple of calls complete then there are 9 concurrent calls.</span></span> <span data-ttu-id="61d2b-119">如果随后再发出了 2 个调用，则当前值再次达到 11。</span><span class="sxs-lookup"><span data-stu-id="61d2b-119">If subsequently two more calls come in, the current value is again 11.</span></span> <span data-ttu-id="61d2b-120">不过，这不会再次引发事件。</span><span class="sxs-lookup"><span data-stu-id="61d2b-120">This does not result in another event.</span></span> <span data-ttu-id="61d2b-121">当前值下降到中止值的 70% 时，将发出一个不同的事件以指示活动已减少。</span><span class="sxs-lookup"><span data-stu-id="61d2b-121">When the current value falls to 70 percent of the throttle limit a different event is emitted that indicates that the activity has slowed.</span></span> <span data-ttu-id="61d2b-122">以后超出中止值的活动将导致发出另一个 `MessageThrottleExceeded` 事件。</span><span class="sxs-lookup"><span data-stu-id="61d2b-122">Future activity that exceeds the limit results in another `MessageThrottleExceeded` event being emitted.</span></span> <span data-ttu-id="61d2b-123">在本示例中，如果并发调用数下降到 7，然后再次达到 11，则发出另一个 `MessageThrottleExceeded` 事件。</span><span class="sxs-lookup"><span data-stu-id="61d2b-123">In this example, if the amount of concurrent calls falls to 7 and then again reaches 11 and another `MessageThrottleExceeded` event is emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="61d2b-124">消息</span><span class="sxs-lookup"><span data-stu-id="61d2b-124">Message</span></span>  
 <span data-ttu-id="61d2b-125">达到了“%2”的中止值“%1”。</span><span class="sxs-lookup"><span data-stu-id="61d2b-125">The '%1' throttle limit of '%2' was hit.</span></span>  
  
## <a name="details"></a><span data-ttu-id="61d2b-126">详细信息</span><span class="sxs-lookup"><span data-stu-id="61d2b-126">Details</span></span>  
  
|<span data-ttu-id="61d2b-127">数据项名称</span><span class="sxs-lookup"><span data-stu-id="61d2b-127">Data Item Name</span></span>|<span data-ttu-id="61d2b-128">数据项类型</span><span class="sxs-lookup"><span data-stu-id="61d2b-128">Data Item Type</span></span>|<span data-ttu-id="61d2b-129">描述</span><span class="sxs-lookup"><span data-stu-id="61d2b-129">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="61d2b-130">中止值名称</span><span class="sxs-lookup"><span data-stu-id="61d2b-130">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="61d2b-131">超过的中止值的名称。</span><span class="sxs-lookup"><span data-stu-id="61d2b-131">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="61d2b-132">`MaxConcurrentCalls`、`MaxConcurrentInstances` 或 `MaxConcurrentSessions`。</span><span class="sxs-lookup"><span data-stu-id="61d2b-132">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="61d2b-133">限制值</span><span class="sxs-lookup"><span data-stu-id="61d2b-133">Limit</span></span>|`xs:long`|<span data-ttu-id="61d2b-134">当前配置的中止值限制。</span><span class="sxs-lookup"><span data-stu-id="61d2b-134">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="61d2b-135">HostReference</span><span class="sxs-lookup"><span data-stu-id="61d2b-135">HostReference</span></span>|`xs:string`|<span data-ttu-id="61d2b-136">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="61d2b-136">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="61d2b-137">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="61d2b-137">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="61d2b-138">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="61d2b-138">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="61d2b-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="61d2b-139">AppDomain</span></span>|`xs:string`|<span data-ttu-id="61d2b-140">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="61d2b-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
