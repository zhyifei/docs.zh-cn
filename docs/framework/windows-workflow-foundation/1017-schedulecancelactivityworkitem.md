---
title: 1017 - ScheduleCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b524f083c49f517c21c77da4f1d1488625a575b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="5bffc-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="5bffc-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="5bffc-103">属性</span><span class="sxs-lookup"><span data-stu-id="5bffc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5bffc-104">ID</span><span class="sxs-lookup"><span data-stu-id="5bffc-104">ID</span></span>|<span data-ttu-id="5bffc-105">1017</span><span class="sxs-lookup"><span data-stu-id="5bffc-105">1017</span></span>|  
|<span data-ttu-id="5bffc-106">关键字</span><span class="sxs-lookup"><span data-stu-id="5bffc-106">Keywords</span></span>|<span data-ttu-id="5bffc-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5bffc-107">WFRuntime</span></span>|  
|<span data-ttu-id="5bffc-108">级别</span><span class="sxs-lookup"><span data-stu-id="5bffc-108">Level</span></span>|<span data-ttu-id="5bffc-109">详细</span><span class="sxs-lookup"><span data-stu-id="5bffc-109">Verbose</span></span>|  
|<span data-ttu-id="5bffc-110">通道</span><span class="sxs-lookup"><span data-stu-id="5bffc-110">Channel</span></span>|<span data-ttu-id="5bffc-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="5bffc-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5bffc-112">描述</span><span class="sxs-lookup"><span data-stu-id="5bffc-112">Description</span></span>  
 <span data-ttu-id="5bffc-113">指示已安排 CancelActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="5bffc-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5bffc-114">消息</span><span class="sxs-lookup"><span data-stu-id="5bffc-114">Message</span></span>  
 <span data-ttu-id="5bffc-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了 CancelActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="5bffc-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5bffc-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="5bffc-116">Details</span></span>  
  
|<span data-ttu-id="5bffc-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="5bffc-117">Data Item Name</span></span>|<span data-ttu-id="5bffc-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="5bffc-118">Data Item Type</span></span>|<span data-ttu-id="5bffc-119">描述</span><span class="sxs-lookup"><span data-stu-id="5bffc-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5bffc-120">Activity</span><span class="sxs-lookup"><span data-stu-id="5bffc-120">Activity</span></span>|<span data-ttu-id="5bffc-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5bffc-121">xs:string</span></span>|<span data-ttu-id="5bffc-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="5bffc-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="5bffc-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5bffc-123">DisplayName</span></span>|<span data-ttu-id="5bffc-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5bffc-124">xs:string</span></span>|<span data-ttu-id="5bffc-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="5bffc-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="5bffc-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5bffc-126">InstanceId</span></span>|<span data-ttu-id="5bffc-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="5bffc-127">xs:string</span></span>|<span data-ttu-id="5bffc-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="5bffc-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="5bffc-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5bffc-129">AppDomain</span></span>|<span data-ttu-id="5bffc-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="5bffc-130">xs:string</span></span>|<span data-ttu-id="5bffc-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="5bffc-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
