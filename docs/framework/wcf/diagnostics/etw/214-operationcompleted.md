---
title: 214 - OperationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 09a8dc1994da30c0f0c180640e3f66c8806e4528
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="214---operationcompleted"></a><span data-ttu-id="5e60a-102">214 - OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="5e60a-102">214 - OperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="5e60a-103">属性</span><span class="sxs-lookup"><span data-stu-id="5e60a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5e60a-104">ID</span><span class="sxs-lookup"><span data-stu-id="5e60a-104">ID</span></span>|<span data-ttu-id="5e60a-105">214</span><span class="sxs-lookup"><span data-stu-id="5e60a-105">214</span></span>|  
|<span data-ttu-id="5e60a-106">关键字</span><span class="sxs-lookup"><span data-stu-id="5e60a-106">Keywords</span></span>|<span data-ttu-id="5e60a-107">HealthMonitoring，EndToEndMonitoring，疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5e60a-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5e60a-108">级别</span><span class="sxs-lookup"><span data-stu-id="5e60a-108">Level</span></span>|<span data-ttu-id="5e60a-109">信息</span><span class="sxs-lookup"><span data-stu-id="5e60a-109">Information</span></span>|  
|<span data-ttu-id="5e60a-110">通道</span><span class="sxs-lookup"><span data-stu-id="5e60a-110">Channel</span></span>|<span data-ttu-id="5e60a-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="5e60a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5e60a-112">描述</span><span class="sxs-lookup"><span data-stu-id="5e60a-112">Description</span></span>  
 <span data-ttu-id="5e60a-113">如果服务模型的默认 `OperationInvoker` 已完成对某一方法的调用且未导致该方法引发异常，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="5e60a-113">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5e60a-114">消息</span><span class="sxs-lookup"><span data-stu-id="5e60a-114">Message</span></span>  
 <span data-ttu-id="5e60a-115">OperationInvoker 已完成对“%1”方法的调用。</span><span class="sxs-lookup"><span data-stu-id="5e60a-115">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="5e60a-116">该方法调用持续了“%2”毫秒。</span><span class="sxs-lookup"><span data-stu-id="5e60a-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5e60a-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="5e60a-117">Details</span></span>  
  
|<span data-ttu-id="5e60a-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="5e60a-118">Data Item Name</span></span>|<span data-ttu-id="5e60a-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="5e60a-119">Data Item Type</span></span>|<span data-ttu-id="5e60a-120">描述</span><span class="sxs-lookup"><span data-stu-id="5e60a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5e60a-121">方法名</span><span class="sxs-lookup"><span data-stu-id="5e60a-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="5e60a-122">由 `OperationInvoker` 调用的方法的 CLR 名称。</span><span class="sxs-lookup"><span data-stu-id="5e60a-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="5e60a-123">持续时间</span><span class="sxs-lookup"><span data-stu-id="5e60a-123">Duration</span></span>|`xs:long`|<span data-ttu-id="5e60a-124">`OperationInvoker` 调用方法所花费的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="5e60a-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="5e60a-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="5e60a-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="5e60a-126">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="5e60a-126">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5e60a-127">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="5e60a-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5e60a-128">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="5e60a-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5e60a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5e60a-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5e60a-130">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="5e60a-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
