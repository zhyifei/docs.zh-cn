---
title: 1040 - InArgumentBound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7dfaad1b-36c0-4575-84c1-31d63b0eaf5d
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b3ce0997dcdad4779f87744edf661316b2efa47c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1040---inargumentbound"></a><span data-ttu-id="e3157-102">1040 - InArgumentBound</span><span class="sxs-lookup"><span data-stu-id="e3157-102">1040 - InArgumentBound</span></span>
## <a name="properties"></a><span data-ttu-id="e3157-103">属性</span><span class="sxs-lookup"><span data-stu-id="e3157-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e3157-104">ID</span><span class="sxs-lookup"><span data-stu-id="e3157-104">ID</span></span>|<span data-ttu-id="e3157-105">1040</span><span class="sxs-lookup"><span data-stu-id="e3157-105">1040</span></span>|  
|<span data-ttu-id="e3157-106">关键字</span><span class="sxs-lookup"><span data-stu-id="e3157-106">Keywords</span></span>|<span data-ttu-id="e3157-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="e3157-107">WFActivities</span></span>|  
|<span data-ttu-id="e3157-108">级别</span><span class="sxs-lookup"><span data-stu-id="e3157-108">Level</span></span>|<span data-ttu-id="e3157-109">详细</span><span class="sxs-lookup"><span data-stu-id="e3157-109">Verbose</span></span>|  
|<span data-ttu-id="e3157-110">通道</span><span class="sxs-lookup"><span data-stu-id="e3157-110">Channel</span></span>|<span data-ttu-id="e3157-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="e3157-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e3157-112">描述</span><span class="sxs-lookup"><span data-stu-id="e3157-112">Description</span></span>  
 <span data-ttu-id="e3157-113">指示已绑定 In 参数。</span><span class="sxs-lookup"><span data-stu-id="e3157-113">Indicates an In argument has been bound.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e3157-114">消息</span><span class="sxs-lookup"><span data-stu-id="e3157-114">Message</span></span>  
 <span data-ttu-id="e3157-115">Activity“%2”、DisplayName“%3”、InstanceId“%4”中的 In 参数“%1”已经与值 %5 绑定。</span><span class="sxs-lookup"><span data-stu-id="e3157-115">In argument '%1' on Activity '%2', DisplayName: '%3', InstanceId: '%4' has been bound with value: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e3157-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="e3157-116">Details</span></span>  
  
|<span data-ttu-id="e3157-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="e3157-117">Data Item Name</span></span>|<span data-ttu-id="e3157-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="e3157-118">Data Item Type</span></span>|<span data-ttu-id="e3157-119">描述</span><span class="sxs-lookup"><span data-stu-id="e3157-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e3157-120">InArgument</span><span class="sxs-lookup"><span data-stu-id="e3157-120">InArgument</span></span>|<span data-ttu-id="e3157-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e3157-121">xs:string</span></span>|<span data-ttu-id="e3157-122">InArgument 的名称。</span><span class="sxs-lookup"><span data-stu-id="e3157-122">The name of the InArgument.</span></span>|  
|<span data-ttu-id="e3157-123">Activity</span><span class="sxs-lookup"><span data-stu-id="e3157-123">Activity</span></span>|<span data-ttu-id="e3157-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e3157-124">xs:string</span></span>|<span data-ttu-id="e3157-125">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="e3157-125">The type name of the activity.</span></span>|  
|<span data-ttu-id="e3157-126">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e3157-126">DisplayName</span></span>|<span data-ttu-id="e3157-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="e3157-127">xs:string</span></span>|<span data-ttu-id="e3157-128">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="e3157-128">The display name of the activity.</span></span>|  
|<span data-ttu-id="e3157-129">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e3157-129">InstanceId</span></span>|<span data-ttu-id="e3157-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e3157-130">xs:string</span></span>|<span data-ttu-id="e3157-131">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="e3157-131">The instance id of the activity.</span></span>|  
|<span data-ttu-id="e3157-132">值</span><span class="sxs-lookup"><span data-stu-id="e3157-132">Value</span></span>|<span data-ttu-id="e3157-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="e3157-133">xs:string</span></span>|<span data-ttu-id="e3157-134">绑定到 InArgument 的值。</span><span class="sxs-lookup"><span data-stu-id="e3157-134">The value bound to the InArgument.</span></span>|  
|<span data-ttu-id="e3157-135">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e3157-135">AppDomain</span></span>|<span data-ttu-id="e3157-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="e3157-136">xs:string</span></span>|<span data-ttu-id="e3157-137">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="e3157-137">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
