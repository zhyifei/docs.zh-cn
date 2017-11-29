---
title: 1010 - ActivityCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1378ddd1550db614c9eddc44f79b19ff94ed585c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="c226b-102">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="c226b-102">1010 - ActivityCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="c226b-103">属性</span><span class="sxs-lookup"><span data-stu-id="c226b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c226b-104">ID</span><span class="sxs-lookup"><span data-stu-id="c226b-104">ID</span></span>|<span data-ttu-id="c226b-105">1010</span><span class="sxs-lookup"><span data-stu-id="c226b-105">1010</span></span>|  
|<span data-ttu-id="c226b-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c226b-106">Keywords</span></span>|<span data-ttu-id="c226b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c226b-107">WFRuntime</span></span>|  
|<span data-ttu-id="c226b-108">级别</span><span class="sxs-lookup"><span data-stu-id="c226b-108">Level</span></span>|<span data-ttu-id="c226b-109">信息</span><span class="sxs-lookup"><span data-stu-id="c226b-109">Information</span></span>|  
|<span data-ttu-id="c226b-110">通道</span><span class="sxs-lookup"><span data-stu-id="c226b-110">Channel</span></span>|<span data-ttu-id="c226b-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c226b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c226b-112">描述</span><span class="sxs-lookup"><span data-stu-id="c226b-112">Description</span></span>  
 <span data-ttu-id="c226b-113">指示活动已完成执行。</span><span class="sxs-lookup"><span data-stu-id="c226b-113">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c226b-114">消息</span><span class="sxs-lookup"><span data-stu-id="c226b-114">Message</span></span>  
 <span data-ttu-id="c226b-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”在“%4”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="c226b-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c226b-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="c226b-116">Details</span></span>  
  
|<span data-ttu-id="c226b-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="c226b-117">Data Item Name</span></span>|<span data-ttu-id="c226b-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="c226b-118">Data Item Type</span></span>|<span data-ttu-id="c226b-119">描述</span><span class="sxs-lookup"><span data-stu-id="c226b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c226b-120">Activity</span><span class="sxs-lookup"><span data-stu-id="c226b-120">Activity</span></span>|<span data-ttu-id="c226b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c226b-121">xs:string</span></span>|<span data-ttu-id="c226b-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="c226b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="c226b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c226b-123">DisplayName</span></span>|<span data-ttu-id="c226b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c226b-124">xs:string</span></span>|<span data-ttu-id="c226b-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c226b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="c226b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c226b-126">InstanceId</span></span>|<span data-ttu-id="c226b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c226b-127">xs:string</span></span>|<span data-ttu-id="c226b-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="c226b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c226b-129">状态</span><span class="sxs-lookup"><span data-stu-id="c226b-129">State</span></span>|<span data-ttu-id="c226b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="c226b-130">xs:string</span></span>|<span data-ttu-id="c226b-131">活动的状态。</span><span class="sxs-lookup"><span data-stu-id="c226b-131">The state of the activity.</span></span>|  
|<span data-ttu-id="c226b-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c226b-132">AppDomain</span></span>|<span data-ttu-id="c226b-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="c226b-133">xs:string</span></span>|<span data-ttu-id="c226b-134">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="c226b-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
