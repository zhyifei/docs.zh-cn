---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: 6a2d4c866ec7d43e8ae40b5616a97c3b7adf1843
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032261"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="416a5-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="416a5-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="416a5-103">属性</span><span class="sxs-lookup"><span data-stu-id="416a5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="416a5-104">Id</span><span class="sxs-lookup"><span data-stu-id="416a5-104">ID</span></span>|<span data-ttu-id="416a5-105">1015</span><span class="sxs-lookup"><span data-stu-id="416a5-105">1015</span></span>|  
|<span data-ttu-id="416a5-106">关键字</span><span class="sxs-lookup"><span data-stu-id="416a5-106">Keywords</span></span>|<span data-ttu-id="416a5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="416a5-107">WFRuntime</span></span>|  
|<span data-ttu-id="416a5-108">级别</span><span class="sxs-lookup"><span data-stu-id="416a5-108">Level</span></span>|<span data-ttu-id="416a5-109">详细</span><span class="sxs-lookup"><span data-stu-id="416a5-109">Verbose</span></span>|  
|<span data-ttu-id="416a5-110">通道</span><span class="sxs-lookup"><span data-stu-id="416a5-110">Channel</span></span>|<span data-ttu-id="416a5-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="416a5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="416a5-112">描述</span><span class="sxs-lookup"><span data-stu-id="416a5-112">Description</span></span>  
 <span data-ttu-id="416a5-113">指示 CompletionWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="416a5-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="416a5-114">消息</span><span class="sxs-lookup"><span data-stu-id="416a5-114">Message</span></span>  
 <span data-ttu-id="416a5-115">开始为父 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 CompletionWorkItem。</span><span class="sxs-lookup"><span data-stu-id="416a5-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="416a5-116">已完成的活动“%4”、DisplayName：“%5”、InstanceId：“%6”。</span><span class="sxs-lookup"><span data-stu-id="416a5-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="416a5-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="416a5-117">Details</span></span>  
  
|<span data-ttu-id="416a5-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="416a5-118">Data Item Name</span></span>|<span data-ttu-id="416a5-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="416a5-119">Data Item Type</span></span>|<span data-ttu-id="416a5-120">描述</span><span class="sxs-lookup"><span data-stu-id="416a5-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="416a5-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="416a5-121">ParentActivity</span></span>|<span data-ttu-id="416a5-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="416a5-122">xs:string</span></span>|<span data-ttu-id="416a5-123">父活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="416a5-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="416a5-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="416a5-124">ParentDisplayName</span></span>|<span data-ttu-id="416a5-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="416a5-125">xs:string</span></span>|<span data-ttu-id="416a5-126">父活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="416a5-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="416a5-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="416a5-127">ParentInstanceId</span></span>|<span data-ttu-id="416a5-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="416a5-128">xs:string</span></span>|<span data-ttu-id="416a5-129">父活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="416a5-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="416a5-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="416a5-130">CompletedActivity</span></span>|<span data-ttu-id="416a5-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="416a5-131">xs:string</span></span>|<span data-ttu-id="416a5-132">已完成活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="416a5-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="416a5-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="416a5-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="416a5-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="416a5-134">xs:string</span></span>|<span data-ttu-id="416a5-135">已完成活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="416a5-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="416a5-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="416a5-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="416a5-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="416a5-137">xs:string</span></span>|<span data-ttu-id="416a5-138">已完成活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="416a5-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="416a5-139">应用程序域</span><span class="sxs-lookup"><span data-stu-id="416a5-139">AppDomain</span></span>|<span data-ttu-id="416a5-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="416a5-140">xs:string</span></span>|<span data-ttu-id="416a5-141">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="416a5-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
