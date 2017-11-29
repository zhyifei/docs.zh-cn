---
title: 222 - OperationFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1c76b502c9c1a767898b1e857c2e943c26fad5c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="222---operationfailed"></a><span data-ttu-id="3deab-102">222 - OperationFailed</span><span class="sxs-lookup"><span data-stu-id="3deab-102">222 - OperationFailed</span></span>
## <a name="properties"></a><span data-ttu-id="3deab-103">属性</span><span class="sxs-lookup"><span data-stu-id="3deab-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3deab-104">ID</span><span class="sxs-lookup"><span data-stu-id="3deab-104">ID</span></span>|<span data-ttu-id="3deab-105">222</span><span class="sxs-lookup"><span data-stu-id="3deab-105">222</span></span>|  
|<span data-ttu-id="3deab-106">关键字</span><span class="sxs-lookup"><span data-stu-id="3deab-106">Keywords</span></span>|<span data-ttu-id="3deab-107">EndToEndMonitoring、HealthMonitoring、疑难解答、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3deab-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="3deab-108">级别</span><span class="sxs-lookup"><span data-stu-id="3deab-108">Level</span></span>|<span data-ttu-id="3deab-109">警告</span><span class="sxs-lookup"><span data-stu-id="3deab-109">Warning</span></span>|  
|<span data-ttu-id="3deab-110">通道</span><span class="sxs-lookup"><span data-stu-id="3deab-110">Channel</span></span>|<span data-ttu-id="3deab-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="3deab-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3deab-112">描述</span><span class="sxs-lookup"><span data-stu-id="3deab-112">Description</span></span>  
 <span data-ttu-id="3deab-113">如果服务模型的默认 `OperationInvoker` 在调用其方法时遇到异常，则会发出此事件。</span><span class="sxs-lookup"><span data-stu-id="3deab-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="3deab-114">请注意，派生自 `FaultException` 的异常会导致不发出此事件。</span><span class="sxs-lookup"><span data-stu-id="3deab-114">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3deab-115">消息</span><span class="sxs-lookup"><span data-stu-id="3deab-115">Message</span></span>  
 <span data-ttu-id="3deab-116">“%1”方法在由 OperationInvoker 调用时引发了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="3deab-116">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="3deab-117">该方法调用持续了“%2”毫秒。</span><span class="sxs-lookup"><span data-stu-id="3deab-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3deab-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="3deab-118">Details</span></span>  
  
|<span data-ttu-id="3deab-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="3deab-119">Data Item Name</span></span>|<span data-ttu-id="3deab-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="3deab-120">Data Item Type</span></span>|<span data-ttu-id="3deab-121">描述</span><span class="sxs-lookup"><span data-stu-id="3deab-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3deab-122">方法名</span><span class="sxs-lookup"><span data-stu-id="3deab-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="3deab-123">由 `OperationInvoker` 调用的方法的 CLR 名称。</span><span class="sxs-lookup"><span data-stu-id="3deab-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="3deab-124">持续时间</span><span class="sxs-lookup"><span data-stu-id="3deab-124">Duration</span></span>|`xs:long`|<span data-ttu-id="3deab-125">`OperationInvoker` 调用方法所花费的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="3deab-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="3deab-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="3deab-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="3deab-127">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="3deab-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="3deab-128">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="3deab-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="3deab-129">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="3deab-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="3deab-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3deab-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3deab-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="3deab-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
