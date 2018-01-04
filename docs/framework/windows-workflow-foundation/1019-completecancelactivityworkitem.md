---
title: 1019 - CompleteCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 378f756003e45905e3697e2e9470aa1e582a2ad6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="e20e4-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="e20e4-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="e20e4-103">属性</span><span class="sxs-lookup"><span data-stu-id="e20e4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e20e4-104">ID</span><span class="sxs-lookup"><span data-stu-id="e20e4-104">ID</span></span>|<span data-ttu-id="e20e4-105">1019</span><span class="sxs-lookup"><span data-stu-id="e20e4-105">1019</span></span>|  
|<span data-ttu-id="e20e4-106">关键字</span><span class="sxs-lookup"><span data-stu-id="e20e4-106">Keywords</span></span>|<span data-ttu-id="e20e4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e20e4-107">WFRuntime</span></span>|  
|<span data-ttu-id="e20e4-108">级别</span><span class="sxs-lookup"><span data-stu-id="e20e4-108">Level</span></span>|<span data-ttu-id="e20e4-109">详细</span><span class="sxs-lookup"><span data-stu-id="e20e4-109">Verbose</span></span>|  
|<span data-ttu-id="e20e4-110">通道</span><span class="sxs-lookup"><span data-stu-id="e20e4-110">Channel</span></span>|<span data-ttu-id="e20e4-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="e20e4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e20e4-112">描述</span><span class="sxs-lookup"><span data-stu-id="e20e4-112">Description</span></span>  
 <span data-ttu-id="e20e4-113">指示 CancelActivityWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="e20e4-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e20e4-114">消息</span><span class="sxs-lookup"><span data-stu-id="e20e4-114">Message</span></span>  
 <span data-ttu-id="e20e4-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的 CancelActivityWorkItem 已经完成。</span><span class="sxs-lookup"><span data-stu-id="e20e4-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e20e4-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="e20e4-116">Details</span></span>  
  
|<span data-ttu-id="e20e4-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="e20e4-117">Data Item Name</span></span>|<span data-ttu-id="e20e4-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="e20e4-118">Data Item Type</span></span>|<span data-ttu-id="e20e4-119">描述</span><span class="sxs-lookup"><span data-stu-id="e20e4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e20e4-120">Activity</span><span class="sxs-lookup"><span data-stu-id="e20e4-120">Activity</span></span>|<span data-ttu-id="e20e4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e20e4-121">xs:string</span></span>|<span data-ttu-id="e20e4-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="e20e4-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="e20e4-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e20e4-123">DisplayName</span></span>|<span data-ttu-id="e20e4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e20e4-124">xs:string</span></span>|<span data-ttu-id="e20e4-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="e20e4-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="e20e4-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e20e4-126">InstanceId</span></span>|<span data-ttu-id="e20e4-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="e20e4-127">xs:string</span></span>|<span data-ttu-id="e20e4-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="e20e4-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="e20e4-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e20e4-129">AppDomain</span></span>|<span data-ttu-id="e20e4-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e20e4-130">xs:string</span></span>|<span data-ttu-id="e20e4-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="e20e4-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
