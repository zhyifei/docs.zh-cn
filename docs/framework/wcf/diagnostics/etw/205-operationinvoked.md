---
title: 205 - OperationInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2b0a96f1e3ba72a226d9b1a871382a27db61c57e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="205---operationinvoked"></a><span data-ttu-id="7511e-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="7511e-102">205 - OperationInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="7511e-103">属性</span><span class="sxs-lookup"><span data-stu-id="7511e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7511e-104">ID</span><span class="sxs-lookup"><span data-stu-id="7511e-104">ID</span></span>|<span data-ttu-id="7511e-105">205</span><span class="sxs-lookup"><span data-stu-id="7511e-105">205</span></span>|  
|<span data-ttu-id="7511e-106">关键字</span><span class="sxs-lookup"><span data-stu-id="7511e-106">Keywords</span></span>|<span data-ttu-id="7511e-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7511e-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="7511e-108">级别</span><span class="sxs-lookup"><span data-stu-id="7511e-108">Level</span></span>|<span data-ttu-id="7511e-109">信息</span><span class="sxs-lookup"><span data-stu-id="7511e-109">Information</span></span>|  
|<span data-ttu-id="7511e-110">通道</span><span class="sxs-lookup"><span data-stu-id="7511e-110">Channel</span></span>|<span data-ttu-id="7511e-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="7511e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7511e-112">描述</span><span class="sxs-lookup"><span data-stu-id="7511e-112">Description</span></span>  
 <span data-ttu-id="7511e-113">恰好在服务模型的默认 `OperationInvoker` 开始调用方法之前发出此事件。</span><span class="sxs-lookup"><span data-stu-id="7511e-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7511e-114">消息</span><span class="sxs-lookup"><span data-stu-id="7511e-114">Message</span></span>  
 <span data-ttu-id="7511e-115">OperationInvoker 调用了“%1”方法。</span><span class="sxs-lookup"><span data-stu-id="7511e-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="7511e-116">调用方信息:“%2”。</span><span class="sxs-lookup"><span data-stu-id="7511e-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7511e-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="7511e-117">Details</span></span>  
  
|<span data-ttu-id="7511e-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="7511e-118">Data Item Name</span></span>|<span data-ttu-id="7511e-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="7511e-119">Data Item Type</span></span>|<span data-ttu-id="7511e-120">描述</span><span class="sxs-lookup"><span data-stu-id="7511e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7511e-121">方法名</span><span class="sxs-lookup"><span data-stu-id="7511e-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="7511e-122">由 `OperationInvoker` 调用的方法的 CLR 名称。</span><span class="sxs-lookup"><span data-stu-id="7511e-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="7511e-123">调用方信息</span><span class="sxs-lookup"><span data-stu-id="7511e-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="7511e-124">客户端 IP 地址和端口号（格式为“IPAddress:PortNumber”）。</span><span class="sxs-lookup"><span data-stu-id="7511e-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="7511e-125">需要从操作上下文的“System.ServiceModel.Channels.RemoteEndpointMessageProperty”消息属性中检索这两个值。</span><span class="sxs-lookup"><span data-stu-id="7511e-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="7511e-126">请注意，对于非 TCP 绑定，该值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="7511e-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="7511e-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="7511e-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="7511e-128">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="7511e-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="7511e-129">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="7511e-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="7511e-130">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="7511e-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="7511e-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7511e-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7511e-132">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="7511e-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
