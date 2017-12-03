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
ms.openlocfilehash: 44ef71e254a2407b416a0efc4b560bf2f6013a74
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="9075f-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="9075f-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="9075f-103">属性</span><span class="sxs-lookup"><span data-stu-id="9075f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9075f-104">ID</span><span class="sxs-lookup"><span data-stu-id="9075f-104">ID</span></span>|<span data-ttu-id="9075f-105">1015</span><span class="sxs-lookup"><span data-stu-id="9075f-105">1015</span></span>|  
|<span data-ttu-id="9075f-106">关键字</span><span class="sxs-lookup"><span data-stu-id="9075f-106">Keywords</span></span>|<span data-ttu-id="9075f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9075f-107">WFRuntime</span></span>|  
|<span data-ttu-id="9075f-108">级别</span><span class="sxs-lookup"><span data-stu-id="9075f-108">Level</span></span>|<span data-ttu-id="9075f-109">详细</span><span class="sxs-lookup"><span data-stu-id="9075f-109">Verbose</span></span>|  
|<span data-ttu-id="9075f-110">通道</span><span class="sxs-lookup"><span data-stu-id="9075f-110">Channel</span></span>|<span data-ttu-id="9075f-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="9075f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9075f-112">描述</span><span class="sxs-lookup"><span data-stu-id="9075f-112">Description</span></span>  
 <span data-ttu-id="9075f-113">指示 CompletionWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="9075f-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9075f-114">消息</span><span class="sxs-lookup"><span data-stu-id="9075f-114">Message</span></span>  
 <span data-ttu-id="9075f-115">开始为父 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 CompletionWorkItem。</span><span class="sxs-lookup"><span data-stu-id="9075f-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="9075f-116">已完成的活动“%4”、DisplayName：“%5”、InstanceId：“%6”。</span><span class="sxs-lookup"><span data-stu-id="9075f-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9075f-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="9075f-117">Details</span></span>  
  
|<span data-ttu-id="9075f-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="9075f-118">Data Item Name</span></span>|<span data-ttu-id="9075f-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="9075f-119">Data Item Type</span></span>|<span data-ttu-id="9075f-120">描述</span><span class="sxs-lookup"><span data-stu-id="9075f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9075f-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="9075f-121">ParentActivity</span></span>|<span data-ttu-id="9075f-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="9075f-122">xs:string</span></span>|<span data-ttu-id="9075f-123">父活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="9075f-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="9075f-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="9075f-124">ParentDisplayName</span></span>|<span data-ttu-id="9075f-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="9075f-125">xs:string</span></span>|<span data-ttu-id="9075f-126">父活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="9075f-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="9075f-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="9075f-127">ParentInstanceId</span></span>|<span data-ttu-id="9075f-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="9075f-128">xs:string</span></span>|<span data-ttu-id="9075f-129">父活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="9075f-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="9075f-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="9075f-130">CompletedActivity</span></span>|<span data-ttu-id="9075f-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="9075f-131">xs:string</span></span>|<span data-ttu-id="9075f-132">已完成活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="9075f-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="9075f-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="9075f-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="9075f-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="9075f-134">xs:string</span></span>|<span data-ttu-id="9075f-135">已完成活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="9075f-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="9075f-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="9075f-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="9075f-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="9075f-137">xs:string</span></span>|<span data-ttu-id="9075f-138">已完成活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="9075f-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="9075f-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9075f-139">AppDomain</span></span>|<span data-ttu-id="9075f-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="9075f-140">xs:string</span></span>|<span data-ttu-id="9075f-141">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="9075f-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
