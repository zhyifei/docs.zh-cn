---
title: 1035 - RuntimeTransactionSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0fcd6662c0f8899b6830dc8e06cee4f56b5ff906
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="1ea14-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="1ea14-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="1ea14-103">属性</span><span class="sxs-lookup"><span data-stu-id="1ea14-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ea14-104">ID</span><span class="sxs-lookup"><span data-stu-id="1ea14-104">ID</span></span>|<span data-ttu-id="1ea14-105">1035</span><span class="sxs-lookup"><span data-stu-id="1ea14-105">1035</span></span>|  
|<span data-ttu-id="1ea14-106">关键字</span><span class="sxs-lookup"><span data-stu-id="1ea14-106">Keywords</span></span>|<span data-ttu-id="1ea14-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1ea14-107">WFRuntime</span></span>|  
|<span data-ttu-id="1ea14-108">级别</span><span class="sxs-lookup"><span data-stu-id="1ea14-108">Level</span></span>|<span data-ttu-id="1ea14-109">详细</span><span class="sxs-lookup"><span data-stu-id="1ea14-109">Verbose</span></span>|  
|<span data-ttu-id="1ea14-110">通道</span><span class="sxs-lookup"><span data-stu-id="1ea14-110">Channel</span></span>|<span data-ttu-id="1ea14-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="1ea14-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1ea14-112">描述</span><span class="sxs-lookup"><span data-stu-id="1ea14-112">Description</span></span>  
 <span data-ttu-id="1ea14-113">指示活动已设置为运行时事务。</span><span class="sxs-lookup"><span data-stu-id="1ea14-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1ea14-114">消息</span><span class="sxs-lookup"><span data-stu-id="1ea14-114">Message</span></span>  
 <span data-ttu-id="1ea14-115">运行时事务已设置 Activity"%1"、 DisplayName:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="1ea14-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="1ea14-116">执行隔离到活动"%4"、 DisplayName:"%5"、 InstanceId:"%6"。</span><span class="sxs-lookup"><span data-stu-id="1ea14-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1ea14-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="1ea14-117">Details</span></span>  
  
|<span data-ttu-id="1ea14-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="1ea14-118">Data Item Name</span></span>|<span data-ttu-id="1ea14-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="1ea14-119">Data Item Type</span></span>|<span data-ttu-id="1ea14-120">描述</span><span class="sxs-lookup"><span data-stu-id="1ea14-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1ea14-121">Activity</span><span class="sxs-lookup"><span data-stu-id="1ea14-121">Activity</span></span>|<span data-ttu-id="1ea14-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ea14-122">xs:string</span></span>|<span data-ttu-id="1ea14-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="1ea14-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="1ea14-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1ea14-124">DisplayName</span></span>|<span data-ttu-id="1ea14-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ea14-125">xs:string</span></span>|<span data-ttu-id="1ea14-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1ea14-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="1ea14-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="1ea14-127">InstanceId</span></span>|<span data-ttu-id="1ea14-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ea14-128">xs:string</span></span>|<span data-ttu-id="1ea14-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="1ea14-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="1ea14-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="1ea14-130">IsolatedActivity</span></span>|<span data-ttu-id="1ea14-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ea14-131">xs:string</span></span>|<span data-ttu-id="1ea14-132">事务隔离到的活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="1ea14-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="1ea14-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="1ea14-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="1ea14-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ea14-134">xs:string</span></span>|<span data-ttu-id="1ea14-135">事务隔离到的活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1ea14-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="1ea14-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="1ea14-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="1ea14-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ea14-137">xs:string</span></span>|<span data-ttu-id="1ea14-138">事务隔离到的活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="1ea14-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="1ea14-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1ea14-139">AppDomain</span></span>|<span data-ttu-id="1ea14-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ea14-140">xs:string</span></span>|<span data-ttu-id="1ea14-141">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="1ea14-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
