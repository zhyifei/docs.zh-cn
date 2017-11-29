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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7457b65f81e9e26b9de6055df474a83ce4264846
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="47edf-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="47edf-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="47edf-103">属性</span><span class="sxs-lookup"><span data-stu-id="47edf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47edf-104">ID</span><span class="sxs-lookup"><span data-stu-id="47edf-104">ID</span></span>|<span data-ttu-id="47edf-105">1015</span><span class="sxs-lookup"><span data-stu-id="47edf-105">1015</span></span>|  
|<span data-ttu-id="47edf-106">关键字</span><span class="sxs-lookup"><span data-stu-id="47edf-106">Keywords</span></span>|<span data-ttu-id="47edf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="47edf-107">WFRuntime</span></span>|  
|<span data-ttu-id="47edf-108">级别</span><span class="sxs-lookup"><span data-stu-id="47edf-108">Level</span></span>|<span data-ttu-id="47edf-109">详细</span><span class="sxs-lookup"><span data-stu-id="47edf-109">Verbose</span></span>|  
|<span data-ttu-id="47edf-110">通道</span><span class="sxs-lookup"><span data-stu-id="47edf-110">Channel</span></span>|<span data-ttu-id="47edf-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="47edf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="47edf-112">描述</span><span class="sxs-lookup"><span data-stu-id="47edf-112">Description</span></span>  
 <span data-ttu-id="47edf-113">指示 CompletionWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="47edf-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="47edf-114">消息</span><span class="sxs-lookup"><span data-stu-id="47edf-114">Message</span></span>  
 <span data-ttu-id="47edf-115">开始为父 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 CompletionWorkItem。</span><span class="sxs-lookup"><span data-stu-id="47edf-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="47edf-116">已完成的活动“%4”、DisplayName：“%5”、InstanceId：“%6”。</span><span class="sxs-lookup"><span data-stu-id="47edf-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="47edf-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="47edf-117">Details</span></span>  
  
|<span data-ttu-id="47edf-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="47edf-118">Data Item Name</span></span>|<span data-ttu-id="47edf-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="47edf-119">Data Item Type</span></span>|<span data-ttu-id="47edf-120">描述</span><span class="sxs-lookup"><span data-stu-id="47edf-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="47edf-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="47edf-121">ParentActivity</span></span>|<span data-ttu-id="47edf-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="47edf-122">xs:string</span></span>|<span data-ttu-id="47edf-123">父活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="47edf-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="47edf-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="47edf-124">ParentDisplayName</span></span>|<span data-ttu-id="47edf-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="47edf-125">xs:string</span></span>|<span data-ttu-id="47edf-126">父活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="47edf-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="47edf-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="47edf-127">ParentInstanceId</span></span>|<span data-ttu-id="47edf-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="47edf-128">xs:string</span></span>|<span data-ttu-id="47edf-129">父活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="47edf-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="47edf-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="47edf-130">CompletedActivity</span></span>|<span data-ttu-id="47edf-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="47edf-131">xs:string</span></span>|<span data-ttu-id="47edf-132">已完成活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="47edf-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="47edf-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="47edf-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="47edf-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="47edf-134">xs:string</span></span>|<span data-ttu-id="47edf-135">已完成活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="47edf-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="47edf-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="47edf-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="47edf-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="47edf-137">xs:string</span></span>|<span data-ttu-id="47edf-138">已完成活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="47edf-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="47edf-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="47edf-139">AppDomain</span></span>|<span data-ttu-id="47edf-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="47edf-140">xs:string</span></span>|<span data-ttu-id="47edf-141">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="47edf-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
