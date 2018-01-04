---
title: 57398 - MaxInstancesExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba48f19de1be3cfd2461e159b91fa365e24ee750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="f340d-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="f340d-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="f340d-103">属性</span><span class="sxs-lookup"><span data-stu-id="f340d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f340d-104">ID</span><span class="sxs-lookup"><span data-stu-id="f340d-104">ID</span></span>|<span data-ttu-id="f340d-105">57398</span><span class="sxs-lookup"><span data-stu-id="f340d-105">57398</span></span>|  
|<span data-ttu-id="f340d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="f340d-106">Keywords</span></span>|<span data-ttu-id="f340d-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="f340d-107">WFServices</span></span>|  
|<span data-ttu-id="f340d-108">级别</span><span class="sxs-lookup"><span data-stu-id="f340d-108">Level</span></span>|<span data-ttu-id="f340d-109">警告</span><span class="sxs-lookup"><span data-stu-id="f340d-109">Warning</span></span>|  
|<span data-ttu-id="f340d-110">通道</span><span class="sxs-lookup"><span data-stu-id="f340d-110">Channel</span></span>|<span data-ttu-id="f340d-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="f340d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f340d-112">描述</span><span class="sxs-lookup"><span data-stu-id="f340d-112">Description</span></span>  
 <span data-ttu-id="f340d-113">指示系统达到为限制“MaxConcurrentInstances”设置的限制值。</span><span class="sxs-lookup"><span data-stu-id="f340d-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f340d-114">消息</span><span class="sxs-lookup"><span data-stu-id="f340d-114">Message</span></span>  
 <span data-ttu-id="f340d-115">系统达到为限制“MaxConcurrentInstances”设置的限制值。</span><span class="sxs-lookup"><span data-stu-id="f340d-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="f340d-116">此限制的限制值设置为 %1。</span><span class="sxs-lookup"><span data-stu-id="f340d-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="f340d-117">可通过修改 serviceThrottle 元素中的特性“maxConcurrentInstances”或修改行为 ServiceThrottlingBehavior 的“MaxConcurrentInstances”属性来更改限制值。</span><span class="sxs-lookup"><span data-stu-id="f340d-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f340d-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="f340d-118">Details</span></span>  
  
|<span data-ttu-id="f340d-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="f340d-119">Data Item Name</span></span>|<span data-ttu-id="f340d-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="f340d-120">Data Item Type</span></span>|<span data-ttu-id="f340d-121">描述</span><span class="sxs-lookup"><span data-stu-id="f340d-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f340d-122">名称</span><span class="sxs-lookup"><span data-stu-id="f340d-122">Name</span></span>|<span data-ttu-id="f340d-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f340d-123">xs:string</span></span>|<span data-ttu-id="f340d-124">项的名称。</span><span class="sxs-lookup"><span data-stu-id="f340d-124">The name of the item.</span></span>|  
|<span data-ttu-id="f340d-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f340d-125">AppDomain</span></span>|<span data-ttu-id="f340d-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f340d-126">xs:string</span></span>|<span data-ttu-id="f340d-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="f340d-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
