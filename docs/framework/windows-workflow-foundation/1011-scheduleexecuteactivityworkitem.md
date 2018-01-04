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
ms.workload: dotnet
ms.openlocfilehash: fe006534e0199888668145be9da3f964055cc464
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="76393-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="76393-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="76393-103">属性</span><span class="sxs-lookup"><span data-stu-id="76393-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76393-104">ID</span><span class="sxs-lookup"><span data-stu-id="76393-104">ID</span></span>|<span data-ttu-id="76393-105">1011</span><span class="sxs-lookup"><span data-stu-id="76393-105">1011</span></span>|  
|<span data-ttu-id="76393-106">关键字</span><span class="sxs-lookup"><span data-stu-id="76393-106">Keywords</span></span>|<span data-ttu-id="76393-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="76393-107">WFRuntime</span></span>|  
|<span data-ttu-id="76393-108">级别</span><span class="sxs-lookup"><span data-stu-id="76393-108">Level</span></span>|<span data-ttu-id="76393-109">详细</span><span class="sxs-lookup"><span data-stu-id="76393-109">Verbose</span></span>|  
|<span data-ttu-id="76393-110">通道</span><span class="sxs-lookup"><span data-stu-id="76393-110">Channel</span></span>|<span data-ttu-id="76393-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="76393-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="76393-112">描述</span><span class="sxs-lookup"><span data-stu-id="76393-112">Description</span></span>  
 <span data-ttu-id="76393-113">指示已安排 ExecuteActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="76393-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="76393-114">消息</span><span class="sxs-lookup"><span data-stu-id="76393-114">Message</span></span>  
 <span data-ttu-id="76393-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了 ExecuteActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="76393-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="76393-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="76393-116">Details</span></span>  
  
|<span data-ttu-id="76393-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="76393-117">Data Item Name</span></span>|<span data-ttu-id="76393-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="76393-118">Data Item Type</span></span>|<span data-ttu-id="76393-119">描述</span><span class="sxs-lookup"><span data-stu-id="76393-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="76393-120">Activity</span><span class="sxs-lookup"><span data-stu-id="76393-120">Activity</span></span>|<span data-ttu-id="76393-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="76393-121">xs:string</span></span>|<span data-ttu-id="76393-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="76393-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="76393-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="76393-123">DisplayName</span></span>|<span data-ttu-id="76393-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="76393-124">xs:string</span></span>|<span data-ttu-id="76393-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="76393-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="76393-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="76393-126">InstanceId</span></span>|<span data-ttu-id="76393-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="76393-127">xs:string</span></span>|<span data-ttu-id="76393-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="76393-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="76393-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="76393-129">AppDomain</span></span>|<span data-ttu-id="76393-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="76393-130">xs:string</span></span>|<span data-ttu-id="76393-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="76393-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
