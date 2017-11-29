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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4de69b1fc2647d7723db8aebb02942938db7478f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="94e48-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="94e48-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="94e48-103">属性</span><span class="sxs-lookup"><span data-stu-id="94e48-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="94e48-104">ID</span><span class="sxs-lookup"><span data-stu-id="94e48-104">ID</span></span>|<span data-ttu-id="94e48-105">1032</span><span class="sxs-lookup"><span data-stu-id="94e48-105">1032</span></span>|  
|<span data-ttu-id="94e48-106">关键字</span><span class="sxs-lookup"><span data-stu-id="94e48-106">Keywords</span></span>|<span data-ttu-id="94e48-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="94e48-107">WFRuntime</span></span>|  
|<span data-ttu-id="94e48-108">级别</span><span class="sxs-lookup"><span data-stu-id="94e48-108">Level</span></span>|<span data-ttu-id="94e48-109">详细</span><span class="sxs-lookup"><span data-stu-id="94e48-109">Verbose</span></span>|  
|<span data-ttu-id="94e48-110">通道</span><span class="sxs-lookup"><span data-stu-id="94e48-110">Channel</span></span>|<span data-ttu-id="94e48-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="94e48-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="94e48-112">描述</span><span class="sxs-lookup"><span data-stu-id="94e48-112">Description</span></span>  
 <span data-ttu-id="94e48-113">指示已安排 RuntimeWorkItem。</span><span class="sxs-lookup"><span data-stu-id="94e48-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="94e48-114">消息</span><span class="sxs-lookup"><span data-stu-id="94e48-114">Message</span></span>  
 <span data-ttu-id="94e48-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了运行时工作项。</span><span class="sxs-lookup"><span data-stu-id="94e48-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="94e48-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="94e48-116">Details</span></span>  
  
|<span data-ttu-id="94e48-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="94e48-117">Data Item Name</span></span>|<span data-ttu-id="94e48-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="94e48-118">Data Item Type</span></span>|<span data-ttu-id="94e48-119">描述</span><span class="sxs-lookup"><span data-stu-id="94e48-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="94e48-120">Activity</span><span class="sxs-lookup"><span data-stu-id="94e48-120">Activity</span></span>|<span data-ttu-id="94e48-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="94e48-121">xs:string</span></span>|<span data-ttu-id="94e48-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="94e48-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="94e48-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="94e48-123">DisplayName</span></span>|<span data-ttu-id="94e48-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="94e48-124">xs:string</span></span>|<span data-ttu-id="94e48-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="94e48-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="94e48-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="94e48-126">InstanceId</span></span>|<span data-ttu-id="94e48-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="94e48-127">xs:string</span></span>|<span data-ttu-id="94e48-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="94e48-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="94e48-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="94e48-129">AppDomain</span></span>|<span data-ttu-id="94e48-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="94e48-130">xs:string</span></span>|<span data-ttu-id="94e48-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="94e48-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
