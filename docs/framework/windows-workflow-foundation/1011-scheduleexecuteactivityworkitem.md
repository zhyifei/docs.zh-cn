---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec89acb9d83a28ac280db7c3d536bfe63669fa97
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="98b0d-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="98b0d-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="98b0d-103">属性</span><span class="sxs-lookup"><span data-stu-id="98b0d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98b0d-104">ID</span><span class="sxs-lookup"><span data-stu-id="98b0d-104">ID</span></span>|<span data-ttu-id="98b0d-105">1011</span><span class="sxs-lookup"><span data-stu-id="98b0d-105">1011</span></span>|  
|<span data-ttu-id="98b0d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="98b0d-106">Keywords</span></span>|<span data-ttu-id="98b0d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="98b0d-107">WFRuntime</span></span>|  
|<span data-ttu-id="98b0d-108">级别</span><span class="sxs-lookup"><span data-stu-id="98b0d-108">Level</span></span>|<span data-ttu-id="98b0d-109">详细</span><span class="sxs-lookup"><span data-stu-id="98b0d-109">Verbose</span></span>|  
|<span data-ttu-id="98b0d-110">通道</span><span class="sxs-lookup"><span data-stu-id="98b0d-110">Channel</span></span>|<span data-ttu-id="98b0d-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="98b0d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="98b0d-112">描述</span><span class="sxs-lookup"><span data-stu-id="98b0d-112">Description</span></span>  
 <span data-ttu-id="98b0d-113">指示已安排 ExecuteActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="98b0d-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="98b0d-114">消息</span><span class="sxs-lookup"><span data-stu-id="98b0d-114">Message</span></span>  
 <span data-ttu-id="98b0d-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了 ExecuteActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="98b0d-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="98b0d-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="98b0d-116">Details</span></span>  
  
|<span data-ttu-id="98b0d-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="98b0d-117">Data Item Name</span></span>|<span data-ttu-id="98b0d-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="98b0d-118">Data Item Type</span></span>|<span data-ttu-id="98b0d-119">描述</span><span class="sxs-lookup"><span data-stu-id="98b0d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="98b0d-120">Activity</span><span class="sxs-lookup"><span data-stu-id="98b0d-120">Activity</span></span>|<span data-ttu-id="98b0d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="98b0d-121">xs:string</span></span>|<span data-ttu-id="98b0d-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="98b0d-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="98b0d-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="98b0d-123">DisplayName</span></span>|<span data-ttu-id="98b0d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="98b0d-124">xs:string</span></span>|<span data-ttu-id="98b0d-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="98b0d-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="98b0d-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="98b0d-126">InstanceId</span></span>|<span data-ttu-id="98b0d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="98b0d-127">xs:string</span></span>|<span data-ttu-id="98b0d-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="98b0d-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="98b0d-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="98b0d-129">AppDomain</span></span>|<span data-ttu-id="98b0d-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="98b0d-130">xs:string</span></span>|<span data-ttu-id="98b0d-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="98b0d-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
