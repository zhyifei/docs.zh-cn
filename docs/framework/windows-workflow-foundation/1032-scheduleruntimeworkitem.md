---
title: 1032 - ScheduleRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81cc73a5ab58e90f1a0ee5bdaf9a491d20206fb3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="dab20-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="dab20-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="dab20-103">属性</span><span class="sxs-lookup"><span data-stu-id="dab20-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dab20-104">ID</span><span class="sxs-lookup"><span data-stu-id="dab20-104">ID</span></span>|<span data-ttu-id="dab20-105">1032</span><span class="sxs-lookup"><span data-stu-id="dab20-105">1032</span></span>|  
|<span data-ttu-id="dab20-106">关键字</span><span class="sxs-lookup"><span data-stu-id="dab20-106">Keywords</span></span>|<span data-ttu-id="dab20-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="dab20-107">WFRuntime</span></span>|  
|<span data-ttu-id="dab20-108">级别</span><span class="sxs-lookup"><span data-stu-id="dab20-108">Level</span></span>|<span data-ttu-id="dab20-109">详细</span><span class="sxs-lookup"><span data-stu-id="dab20-109">Verbose</span></span>|  
|<span data-ttu-id="dab20-110">通道</span><span class="sxs-lookup"><span data-stu-id="dab20-110">Channel</span></span>|<span data-ttu-id="dab20-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="dab20-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dab20-112">描述</span><span class="sxs-lookup"><span data-stu-id="dab20-112">Description</span></span>  
 <span data-ttu-id="dab20-113">指示已安排 RuntimeWorkItem。</span><span class="sxs-lookup"><span data-stu-id="dab20-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="dab20-114">消息</span><span class="sxs-lookup"><span data-stu-id="dab20-114">Message</span></span>  
 <span data-ttu-id="dab20-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了运行时工作项。</span><span class="sxs-lookup"><span data-stu-id="dab20-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="dab20-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="dab20-116">Details</span></span>  
  
|<span data-ttu-id="dab20-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="dab20-117">Data Item Name</span></span>|<span data-ttu-id="dab20-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="dab20-118">Data Item Type</span></span>|<span data-ttu-id="dab20-119">描述</span><span class="sxs-lookup"><span data-stu-id="dab20-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="dab20-120">Activity</span><span class="sxs-lookup"><span data-stu-id="dab20-120">Activity</span></span>|<span data-ttu-id="dab20-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="dab20-121">xs:string</span></span>|<span data-ttu-id="dab20-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="dab20-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="dab20-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="dab20-123">DisplayName</span></span>|<span data-ttu-id="dab20-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="dab20-124">xs:string</span></span>|<span data-ttu-id="dab20-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="dab20-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="dab20-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="dab20-126">InstanceId</span></span>|<span data-ttu-id="dab20-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="dab20-127">xs:string</span></span>|<span data-ttu-id="dab20-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="dab20-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="dab20-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="dab20-129">AppDomain</span></span>|<span data-ttu-id="dab20-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="dab20-130">xs:string</span></span>|<span data-ttu-id="dab20-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="dab20-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
