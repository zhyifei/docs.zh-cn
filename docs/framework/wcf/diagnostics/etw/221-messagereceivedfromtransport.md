---
title: 221 - MessageReceivedFromTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4f977f938844f48182be6662f489506e8119fe67
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="12210-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="12210-102">221 - MessageReceivedFromTransport</span></span>
## <a name="properties"></a><span data-ttu-id="12210-103">属性</span><span class="sxs-lookup"><span data-stu-id="12210-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="12210-104">ID</span><span class="sxs-lookup"><span data-stu-id="12210-104">ID</span></span>|<span data-ttu-id="12210-105">221</span><span class="sxs-lookup"><span data-stu-id="12210-105">221</span></span>|  
|<span data-ttu-id="12210-106">关键字</span><span class="sxs-lookup"><span data-stu-id="12210-106">Keywords</span></span>|<span data-ttu-id="12210-107">EndToEndMonitoring，疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="12210-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="12210-108">级别</span><span class="sxs-lookup"><span data-stu-id="12210-108">Level</span></span>|<span data-ttu-id="12210-109">信息</span><span class="sxs-lookup"><span data-stu-id="12210-109">Information</span></span>|  
|<span data-ttu-id="12210-110">通道</span><span class="sxs-lookup"><span data-stu-id="12210-110">Channel</span></span>|<span data-ttu-id="12210-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="12210-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="12210-112">描述</span><span class="sxs-lookup"><span data-stu-id="12210-112">Description</span></span>  
 <span data-ttu-id="12210-113">服务模型从传输中接收消息时将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="12210-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="12210-114">消息</span><span class="sxs-lookup"><span data-stu-id="12210-114">Message</span></span>  
 <span data-ttu-id="12210-115">调度程序从传输收到一条消息。</span><span class="sxs-lookup"><span data-stu-id="12210-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="12210-116">相关 ID 为“%1”。</span><span class="sxs-lookup"><span data-stu-id="12210-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="12210-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="12210-117">Details</span></span>  
  
|<span data-ttu-id="12210-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="12210-118">Data Item Name</span></span>|<span data-ttu-id="12210-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="12210-119">Data Item Type</span></span>|<span data-ttu-id="12210-120">描述</span><span class="sxs-lookup"><span data-stu-id="12210-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="12210-121">相关 ID</span><span class="sxs-lookup"><span data-stu-id="12210-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="12210-122">用于将服务或客户端的 `MessageSentToTransport` 事件与另一端的对应 `MessageReceivedFromTransport` 相关的活动 ID。</span><span class="sxs-lookup"><span data-stu-id="12210-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="12210-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="12210-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="12210-124">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="12210-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="12210-125">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="12210-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="12210-126">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="12210-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="12210-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="12210-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="12210-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="12210-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
