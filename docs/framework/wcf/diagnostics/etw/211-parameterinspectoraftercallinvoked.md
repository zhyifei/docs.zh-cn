---
title: 211 - ParameterInspectorAfterCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 78424b8057518f5d9f201ead33b2784ffeeb7e58
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="f39c5-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="f39c5-102">211 - ParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="f39c5-103">属性</span><span class="sxs-lookup"><span data-stu-id="f39c5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f39c5-104">ID</span><span class="sxs-lookup"><span data-stu-id="f39c5-104">ID</span></span>|<span data-ttu-id="f39c5-105">211</span><span class="sxs-lookup"><span data-stu-id="f39c5-105">211</span></span>|  
|<span data-ttu-id="f39c5-106">关键字</span><span class="sxs-lookup"><span data-stu-id="f39c5-106">Keywords</span></span>|<span data-ttu-id="f39c5-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f39c5-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f39c5-108">级别</span><span class="sxs-lookup"><span data-stu-id="f39c5-108">Level</span></span>|<span data-ttu-id="f39c5-109">信息</span><span class="sxs-lookup"><span data-stu-id="f39c5-109">Information</span></span>|  
|<span data-ttu-id="f39c5-110">通道</span><span class="sxs-lookup"><span data-stu-id="f39c5-110">Channel</span></span>|<span data-ttu-id="f39c5-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="f39c5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f39c5-112">描述</span><span class="sxs-lookup"><span data-stu-id="f39c5-112">Description</span></span>  
 <span data-ttu-id="f39c5-113">服务模型对 `AfterCall` 调用 `ParameterInspector` 方法之后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="f39c5-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f39c5-114">消息</span><span class="sxs-lookup"><span data-stu-id="f39c5-114">Message</span></span>  
 <span data-ttu-id="f39c5-115">调度程序对“%1”类型的 ParameterInspector 调用了“AfterCall”。</span><span class="sxs-lookup"><span data-stu-id="f39c5-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f39c5-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="f39c5-116">Details</span></span>  
  
|<span data-ttu-id="f39c5-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="f39c5-117">Data Item Name</span></span>|<span data-ttu-id="f39c5-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="f39c5-118">Data Item Type</span></span>|<span data-ttu-id="f39c5-119">描述</span><span class="sxs-lookup"><span data-stu-id="f39c5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f39c5-120">类型名称</span><span class="sxs-lookup"><span data-stu-id="f39c5-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="f39c5-121">所调用 `ParameterInspector` 的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="f39c5-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="f39c5-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="f39c5-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="f39c5-123">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="f39c5-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f39c5-124">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="f39c5-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f39c5-125">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="f39c5-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f39c5-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f39c5-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f39c5-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="f39c5-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
