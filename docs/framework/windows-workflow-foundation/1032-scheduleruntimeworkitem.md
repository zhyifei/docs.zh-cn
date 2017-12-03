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
ms.openlocfilehash: d2a150b9e9c78a9ce1f5e20b962a58ef2d5dde9d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="9dfb3-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="9dfb3-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="9dfb3-103">属性</span><span class="sxs-lookup"><span data-stu-id="9dfb3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9dfb3-104">ID</span><span class="sxs-lookup"><span data-stu-id="9dfb3-104">ID</span></span>|<span data-ttu-id="9dfb3-105">1032</span><span class="sxs-lookup"><span data-stu-id="9dfb3-105">1032</span></span>|  
|<span data-ttu-id="9dfb3-106">关键字</span><span class="sxs-lookup"><span data-stu-id="9dfb3-106">Keywords</span></span>|<span data-ttu-id="9dfb3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9dfb3-107">WFRuntime</span></span>|  
|<span data-ttu-id="9dfb3-108">级别</span><span class="sxs-lookup"><span data-stu-id="9dfb3-108">Level</span></span>|<span data-ttu-id="9dfb3-109">详细</span><span class="sxs-lookup"><span data-stu-id="9dfb3-109">Verbose</span></span>|  
|<span data-ttu-id="9dfb3-110">通道</span><span class="sxs-lookup"><span data-stu-id="9dfb3-110">Channel</span></span>|<span data-ttu-id="9dfb3-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="9dfb3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9dfb3-112">描述</span><span class="sxs-lookup"><span data-stu-id="9dfb3-112">Description</span></span>  
 <span data-ttu-id="9dfb3-113">指示已安排 RuntimeWorkItem。</span><span class="sxs-lookup"><span data-stu-id="9dfb3-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9dfb3-114">消息</span><span class="sxs-lookup"><span data-stu-id="9dfb3-114">Message</span></span>  
 <span data-ttu-id="9dfb3-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了运行时工作项。</span><span class="sxs-lookup"><span data-stu-id="9dfb3-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9dfb3-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="9dfb3-116">Details</span></span>  
  
|<span data-ttu-id="9dfb3-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="9dfb3-117">Data Item Name</span></span>|<span data-ttu-id="9dfb3-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="9dfb3-118">Data Item Type</span></span>|<span data-ttu-id="9dfb3-119">描述</span><span class="sxs-lookup"><span data-stu-id="9dfb3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9dfb3-120">Activity</span><span class="sxs-lookup"><span data-stu-id="9dfb3-120">Activity</span></span>|<span data-ttu-id="9dfb3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9dfb3-121">xs:string</span></span>|<span data-ttu-id="9dfb3-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="9dfb3-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="9dfb3-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9dfb3-123">DisplayName</span></span>|<span data-ttu-id="9dfb3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9dfb3-124">xs:string</span></span>|<span data-ttu-id="9dfb3-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="9dfb3-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="9dfb3-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="9dfb3-126">InstanceId</span></span>|<span data-ttu-id="9dfb3-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9dfb3-127">xs:string</span></span>|<span data-ttu-id="9dfb3-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="9dfb3-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="9dfb3-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9dfb3-129">AppDomain</span></span>|<span data-ttu-id="9dfb3-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="9dfb3-130">xs:string</span></span>|<span data-ttu-id="9dfb3-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="9dfb3-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
