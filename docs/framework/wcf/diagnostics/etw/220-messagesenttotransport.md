---
title: 220 - MessageSentToTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d391d7bb8276f4b20d831acd59aa8a78db38995c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="220---messagesenttotransport"></a><span data-ttu-id="eb673-102">220 - MessageSentToTransport</span><span class="sxs-lookup"><span data-stu-id="eb673-102">220 - MessageSentToTransport</span></span>
## <a name="properties"></a><span data-ttu-id="eb673-103">属性</span><span class="sxs-lookup"><span data-stu-id="eb673-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eb673-104">Id</span><span class="sxs-lookup"><span data-stu-id="eb673-104">Id</span></span>|<span data-ttu-id="eb673-105">220</span><span class="sxs-lookup"><span data-stu-id="eb673-105">220</span></span>|  
|<span data-ttu-id="eb673-106">关键字</span><span class="sxs-lookup"><span data-stu-id="eb673-106">Keywords</span></span>|<span data-ttu-id="eb673-107">EndToEndMonitoring，疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="eb673-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="eb673-108">级别</span><span class="sxs-lookup"><span data-stu-id="eb673-108">Level</span></span>|<span data-ttu-id="eb673-109">信息</span><span class="sxs-lookup"><span data-stu-id="eb673-109">Information</span></span>|  
|<span data-ttu-id="eb673-110">通道</span><span class="sxs-lookup"><span data-stu-id="eb673-110">Channel</span></span>|<span data-ttu-id="eb673-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="eb673-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="eb673-112">描述</span><span class="sxs-lookup"><span data-stu-id="eb673-112">Description</span></span>  
 <span data-ttu-id="eb673-113">服务模型向传输发送消息时将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="eb673-113">This event is emitted when the Service Model sends a message to the transport.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb673-114">不会为单向传输发出此事件。</span><span class="sxs-lookup"><span data-stu-id="eb673-114">This event will not be emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="eb673-115">消息</span><span class="sxs-lookup"><span data-stu-id="eb673-115">Message</span></span>  
 <span data-ttu-id="eb673-116">调度程序向传输发送了一条消息。</span><span class="sxs-lookup"><span data-stu-id="eb673-116">The Dispatcher sent a message to the transport.</span></span> <span data-ttu-id="eb673-117">相关 ID 为“%1”。</span><span class="sxs-lookup"><span data-stu-id="eb673-117">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="eb673-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="eb673-118">Details</span></span>  
  
|<span data-ttu-id="eb673-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="eb673-119">Data Item Name</span></span>|<span data-ttu-id="eb673-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="eb673-120">Data Item Type</span></span>|<span data-ttu-id="eb673-121">描述</span><span class="sxs-lookup"><span data-stu-id="eb673-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="eb673-122">相关 ID</span><span class="sxs-lookup"><span data-stu-id="eb673-122">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="eb673-123">用于将服务或客户端的 `MessageSentToTransport` 事件与另一端的对应 `MessageReceivedFromTransport` 相关的活动 ID。</span><span class="sxs-lookup"><span data-stu-id="eb673-123">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="eb673-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="eb673-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="eb673-125">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="eb673-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="eb673-126">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="eb673-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="eb673-127">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="eb673-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="eb673-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="eb673-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="eb673-129">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="eb673-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
