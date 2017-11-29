---
title: 203 - ClientParameterInspectorAfterCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b736d9e2827708caea54fbe230b0b638492adb96
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="d6a70-102">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="d6a70-102">203 - ClientParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="d6a70-103">属性</span><span class="sxs-lookup"><span data-stu-id="d6a70-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6a70-104">ID</span><span class="sxs-lookup"><span data-stu-id="d6a70-104">ID</span></span>|<span data-ttu-id="d6a70-105">203</span><span class="sxs-lookup"><span data-stu-id="d6a70-105">203</span></span>|  
|<span data-ttu-id="d6a70-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d6a70-106">Keywords</span></span>|<span data-ttu-id="d6a70-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d6a70-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="d6a70-108">级别</span><span class="sxs-lookup"><span data-stu-id="d6a70-108">Level</span></span>|<span data-ttu-id="d6a70-109">信息</span><span class="sxs-lookup"><span data-stu-id="d6a70-109">Information</span></span>|  
|<span data-ttu-id="d6a70-110">通道</span><span class="sxs-lookup"><span data-stu-id="d6a70-110">Channel</span></span>|<span data-ttu-id="d6a70-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="d6a70-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d6a70-112">描述</span><span class="sxs-lookup"><span data-stu-id="d6a70-112">Description</span></span>  
 <span data-ttu-id="d6a70-113">服务模型在客户端参数检查器上调用 `AfterCall` 方法之后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="d6a70-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d6a70-114">消息</span><span class="sxs-lookup"><span data-stu-id="d6a70-114">Message</span></span>  
 <span data-ttu-id="d6a70-115">调度程序对“%1”类型的 ClientParameterInspector 调用了“AfterCall”。</span><span class="sxs-lookup"><span data-stu-id="d6a70-115">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d6a70-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="d6a70-116">Details</span></span>  
  
|<span data-ttu-id="d6a70-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d6a70-117">Data Item Name</span></span>|<span data-ttu-id="d6a70-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d6a70-118">Data Item Type</span></span>|<span data-ttu-id="d6a70-119">描述</span><span class="sxs-lookup"><span data-stu-id="d6a70-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d6a70-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="d6a70-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="d6a70-121">所调用检查器的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="d6a70-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="d6a70-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="d6a70-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="d6a70-123">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="d6a70-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d6a70-124">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="d6a70-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d6a70-125">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="d6a70-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d6a70-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d6a70-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d6a70-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d6a70-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
