---
title: 1015 - StartCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bc317157ed7658a52aa60c9b74942f9e84d47257
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="77f50-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="77f50-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="77f50-103">属性</span><span class="sxs-lookup"><span data-stu-id="77f50-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="77f50-104">ID</span><span class="sxs-lookup"><span data-stu-id="77f50-104">ID</span></span>|<span data-ttu-id="77f50-105">1015</span><span class="sxs-lookup"><span data-stu-id="77f50-105">1015</span></span>|  
|<span data-ttu-id="77f50-106">关键字</span><span class="sxs-lookup"><span data-stu-id="77f50-106">Keywords</span></span>|<span data-ttu-id="77f50-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="77f50-107">WFRuntime</span></span>|  
|<span data-ttu-id="77f50-108">级别</span><span class="sxs-lookup"><span data-stu-id="77f50-108">Level</span></span>|<span data-ttu-id="77f50-109">详细</span><span class="sxs-lookup"><span data-stu-id="77f50-109">Verbose</span></span>|  
|<span data-ttu-id="77f50-110">通道</span><span class="sxs-lookup"><span data-stu-id="77f50-110">Channel</span></span>|<span data-ttu-id="77f50-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="77f50-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="77f50-112">描述</span><span class="sxs-lookup"><span data-stu-id="77f50-112">Description</span></span>  
 <span data-ttu-id="77f50-113">指示 CompletionWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="77f50-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="77f50-114">消息</span><span class="sxs-lookup"><span data-stu-id="77f50-114">Message</span></span>  
 <span data-ttu-id="77f50-115">开始为父 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 CompletionWorkItem。</span><span class="sxs-lookup"><span data-stu-id="77f50-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="77f50-116">已完成的活动“%4”、DisplayName：“%5”、InstanceId：“%6”。</span><span class="sxs-lookup"><span data-stu-id="77f50-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="77f50-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="77f50-117">Details</span></span>  
  
|<span data-ttu-id="77f50-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="77f50-118">Data Item Name</span></span>|<span data-ttu-id="77f50-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="77f50-119">Data Item Type</span></span>|<span data-ttu-id="77f50-120">描述</span><span class="sxs-lookup"><span data-stu-id="77f50-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="77f50-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="77f50-121">ParentActivity</span></span>|<span data-ttu-id="77f50-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="77f50-122">xs:string</span></span>|<span data-ttu-id="77f50-123">父活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="77f50-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="77f50-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="77f50-124">ParentDisplayName</span></span>|<span data-ttu-id="77f50-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="77f50-125">xs:string</span></span>|<span data-ttu-id="77f50-126">父活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="77f50-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="77f50-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="77f50-127">ParentInstanceId</span></span>|<span data-ttu-id="77f50-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="77f50-128">xs:string</span></span>|<span data-ttu-id="77f50-129">父活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="77f50-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="77f50-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="77f50-130">CompletedActivity</span></span>|<span data-ttu-id="77f50-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="77f50-131">xs:string</span></span>|<span data-ttu-id="77f50-132">已完成活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="77f50-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="77f50-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="77f50-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="77f50-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="77f50-134">xs:string</span></span>|<span data-ttu-id="77f50-135">已完成活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="77f50-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="77f50-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="77f50-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="77f50-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="77f50-137">xs:string</span></span>|<span data-ttu-id="77f50-138">已完成活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="77f50-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="77f50-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="77f50-139">AppDomain</span></span>|<span data-ttu-id="77f50-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="77f50-140">xs:string</span></span>|<span data-ttu-id="77f50-141">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="77f50-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
