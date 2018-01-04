---
title: 225 - TraceCorrelationKeys
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9a8d9120c4173d90d7bf6b1ff2054117f80ac96a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="ba805-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="ba805-102">225 - TraceCorrelationKeys</span></span>
## <a name="properties"></a><span data-ttu-id="ba805-103">属性</span><span class="sxs-lookup"><span data-stu-id="ba805-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ba805-104">ID</span><span class="sxs-lookup"><span data-stu-id="ba805-104">ID</span></span>|<span data-ttu-id="ba805-105">225</span><span class="sxs-lookup"><span data-stu-id="ba805-105">225</span></span>|  
|<span data-ttu-id="ba805-106">关键字</span><span class="sxs-lookup"><span data-stu-id="ba805-106">Keywords</span></span>|<span data-ttu-id="ba805-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ba805-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ba805-108">级别</span><span class="sxs-lookup"><span data-stu-id="ba805-108">Level</span></span>|<span data-ttu-id="ba805-109">信息</span><span class="sxs-lookup"><span data-stu-id="ba805-109">Information</span></span>|  
|<span data-ttu-id="ba805-110">通道</span><span class="sxs-lookup"><span data-stu-id="ba805-110">Channel</span></span>|<span data-ttu-id="ba805-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="ba805-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ba805-112">描述</span><span class="sxs-lookup"><span data-stu-id="ba805-112">Description</span></span>  
 <span data-ttu-id="ba805-113">将基于内容的相关用于工作流服务时将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="ba805-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="ba805-114">该事件包含为关联消息和实例而应用的相关键。</span><span class="sxs-lookup"><span data-stu-id="ba805-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ba805-115">消息</span><span class="sxs-lookup"><span data-stu-id="ba805-115">Message</span></span>  
 <span data-ttu-id="ba805-116">使用父作用域“%3”中的值“%2”计算出的相关键“%1”。</span><span class="sxs-lookup"><span data-stu-id="ba805-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ba805-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="ba805-117">Details</span></span>  
  
|<span data-ttu-id="ba805-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="ba805-118">Data Item Name</span></span>|<span data-ttu-id="ba805-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="ba805-119">Data Item Type</span></span>|<span data-ttu-id="ba805-120">描述</span><span class="sxs-lookup"><span data-stu-id="ba805-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ba805-121">实例键</span><span class="sxs-lookup"><span data-stu-id="ba805-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="ba805-122">依据相关值生成的键。</span><span class="sxs-lookup"><span data-stu-id="ba805-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="ba805-123">值</span><span class="sxs-lookup"><span data-stu-id="ba805-123">Values</span></span>|`xs:string`|<span data-ttu-id="ba805-124">用于计算相关实例键的值。</span><span class="sxs-lookup"><span data-stu-id="ba805-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="ba805-125">父作用域</span><span class="sxs-lookup"><span data-stu-id="ba805-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="ba805-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="ba805-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="ba805-127">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="ba805-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ba805-128">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="ba805-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ba805-129">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="ba805-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ba805-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ba805-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ba805-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="ba805-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
