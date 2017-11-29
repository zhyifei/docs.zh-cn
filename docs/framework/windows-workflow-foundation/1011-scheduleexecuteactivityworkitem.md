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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 498752bfc896891a43a6a2e7a8245c508795c1ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="ff351-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="ff351-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ff351-103">属性</span><span class="sxs-lookup"><span data-stu-id="ff351-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ff351-104">ID</span><span class="sxs-lookup"><span data-stu-id="ff351-104">ID</span></span>|<span data-ttu-id="ff351-105">1011</span><span class="sxs-lookup"><span data-stu-id="ff351-105">1011</span></span>|  
|<span data-ttu-id="ff351-106">关键字</span><span class="sxs-lookup"><span data-stu-id="ff351-106">Keywords</span></span>|<span data-ttu-id="ff351-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ff351-107">WFRuntime</span></span>|  
|<span data-ttu-id="ff351-108">级别</span><span class="sxs-lookup"><span data-stu-id="ff351-108">Level</span></span>|<span data-ttu-id="ff351-109">详细</span><span class="sxs-lookup"><span data-stu-id="ff351-109">Verbose</span></span>|  
|<span data-ttu-id="ff351-110">通道</span><span class="sxs-lookup"><span data-stu-id="ff351-110">Channel</span></span>|<span data-ttu-id="ff351-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="ff351-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ff351-112">描述</span><span class="sxs-lookup"><span data-stu-id="ff351-112">Description</span></span>  
 <span data-ttu-id="ff351-113">指示已安排 ExecuteActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="ff351-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ff351-114">消息</span><span class="sxs-lookup"><span data-stu-id="ff351-114">Message</span></span>  
 <span data-ttu-id="ff351-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了 ExecuteActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="ff351-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ff351-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="ff351-116">Details</span></span>  
  
|<span data-ttu-id="ff351-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="ff351-117">Data Item Name</span></span>|<span data-ttu-id="ff351-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="ff351-118">Data Item Type</span></span>|<span data-ttu-id="ff351-119">描述</span><span class="sxs-lookup"><span data-stu-id="ff351-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ff351-120">Activity</span><span class="sxs-lookup"><span data-stu-id="ff351-120">Activity</span></span>|<span data-ttu-id="ff351-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ff351-121">xs:string</span></span>|<span data-ttu-id="ff351-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="ff351-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ff351-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ff351-123">DisplayName</span></span>|<span data-ttu-id="ff351-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ff351-124">xs:string</span></span>|<span data-ttu-id="ff351-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ff351-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ff351-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ff351-126">InstanceId</span></span>|<span data-ttu-id="ff351-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ff351-127">xs:string</span></span>|<span data-ttu-id="ff351-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="ff351-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ff351-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ff351-129">AppDomain</span></span>|<span data-ttu-id="ff351-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ff351-130">xs:string</span></span>|<span data-ttu-id="ff351-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="ff351-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
