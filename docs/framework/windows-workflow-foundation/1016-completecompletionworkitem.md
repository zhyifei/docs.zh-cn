---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 3f0904a561a242cd3be528c9707a409b6f98e0fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925081"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="754e1-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="754e1-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="754e1-103">属性</span><span class="sxs-lookup"><span data-stu-id="754e1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="754e1-104">Id</span><span class="sxs-lookup"><span data-stu-id="754e1-104">ID</span></span>|<span data-ttu-id="754e1-105">1016</span><span class="sxs-lookup"><span data-stu-id="754e1-105">1016</span></span>|  
|<span data-ttu-id="754e1-106">关键字</span><span class="sxs-lookup"><span data-stu-id="754e1-106">Keywords</span></span>|<span data-ttu-id="754e1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="754e1-107">WFRuntime</span></span>|  
|<span data-ttu-id="754e1-108">级别</span><span class="sxs-lookup"><span data-stu-id="754e1-108">Level</span></span>|<span data-ttu-id="754e1-109">详细</span><span class="sxs-lookup"><span data-stu-id="754e1-109">Verbose</span></span>|  
|<span data-ttu-id="754e1-110">通道</span><span class="sxs-lookup"><span data-stu-id="754e1-110">Channel</span></span>|<span data-ttu-id="754e1-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="754e1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="754e1-112">描述</span><span class="sxs-lookup"><span data-stu-id="754e1-112">Description</span></span>  
 <span data-ttu-id="754e1-113">指示 CompletionWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="754e1-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="754e1-114">消息</span><span class="sxs-lookup"><span data-stu-id="754e1-114">Message</span></span>  
 <span data-ttu-id="754e1-115">父 Activity“%1”、DisplayName“'%2”、InstanceId“%3”已完成了 CompletionWorkItem。</span><span class="sxs-lookup"><span data-stu-id="754e1-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="754e1-116">已完成的活动“%4”、DisplayName：“%5”、InstanceId：“%6”。</span><span class="sxs-lookup"><span data-stu-id="754e1-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="754e1-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="754e1-117">Details</span></span>  
  
|<span data-ttu-id="754e1-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="754e1-118">Data Item Name</span></span>|<span data-ttu-id="754e1-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="754e1-119">Data Item Type</span></span>|<span data-ttu-id="754e1-120">描述</span><span class="sxs-lookup"><span data-stu-id="754e1-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="754e1-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="754e1-121">ParentActivity</span></span>|<span data-ttu-id="754e1-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="754e1-122">xs:string</span></span>|<span data-ttu-id="754e1-123">父活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="754e1-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="754e1-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="754e1-124">ParentDisplayName</span></span>|<span data-ttu-id="754e1-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="754e1-125">xs:string</span></span>|<span data-ttu-id="754e1-126">父活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="754e1-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="754e1-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="754e1-127">ParentInstanceId</span></span>|<span data-ttu-id="754e1-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="754e1-128">xs:string</span></span>|<span data-ttu-id="754e1-129">父活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="754e1-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="754e1-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="754e1-130">CompletedActivity</span></span>|<span data-ttu-id="754e1-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="754e1-131">xs:string</span></span>|<span data-ttu-id="754e1-132">已完成活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="754e1-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="754e1-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="754e1-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="754e1-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="754e1-134">xs:string</span></span>|<span data-ttu-id="754e1-135">已完成活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="754e1-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="754e1-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="754e1-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="754e1-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="754e1-137">xs:string</span></span>|<span data-ttu-id="754e1-138">已完成活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="754e1-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="754e1-139">应用程序域</span><span class="sxs-lookup"><span data-stu-id="754e1-139">AppDomain</span></span>|<span data-ttu-id="754e1-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="754e1-140">xs:string</span></span>|<span data-ttu-id="754e1-141">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="754e1-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
