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
ms.openlocfilehash: a632d59ddd75b375ff5e828a9f35aeecb0118f1c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="b3873-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="b3873-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b3873-103">属性</span><span class="sxs-lookup"><span data-stu-id="b3873-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b3873-104">ID</span><span class="sxs-lookup"><span data-stu-id="b3873-104">ID</span></span>|<span data-ttu-id="b3873-105">1017</span><span class="sxs-lookup"><span data-stu-id="b3873-105">1017</span></span>|  
|<span data-ttu-id="b3873-106">关键字</span><span class="sxs-lookup"><span data-stu-id="b3873-106">Keywords</span></span>|<span data-ttu-id="b3873-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b3873-107">WFRuntime</span></span>|  
|<span data-ttu-id="b3873-108">级别</span><span class="sxs-lookup"><span data-stu-id="b3873-108">Level</span></span>|<span data-ttu-id="b3873-109">详细</span><span class="sxs-lookup"><span data-stu-id="b3873-109">Verbose</span></span>|  
|<span data-ttu-id="b3873-110">通道</span><span class="sxs-lookup"><span data-stu-id="b3873-110">Channel</span></span>|<span data-ttu-id="b3873-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="b3873-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b3873-112">描述</span><span class="sxs-lookup"><span data-stu-id="b3873-112">Description</span></span>  
 <span data-ttu-id="b3873-113">指示已安排 CancelActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="b3873-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b3873-114">消息</span><span class="sxs-lookup"><span data-stu-id="b3873-114">Message</span></span>  
 <span data-ttu-id="b3873-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了 CancelActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="b3873-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b3873-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="b3873-116">Details</span></span>  
  
|<span data-ttu-id="b3873-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="b3873-117">Data Item Name</span></span>|<span data-ttu-id="b3873-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="b3873-118">Data Item Type</span></span>|<span data-ttu-id="b3873-119">描述</span><span class="sxs-lookup"><span data-stu-id="b3873-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b3873-120">Activity</span><span class="sxs-lookup"><span data-stu-id="b3873-120">Activity</span></span>|<span data-ttu-id="b3873-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b3873-121">xs:string</span></span>|<span data-ttu-id="b3873-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="b3873-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="b3873-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b3873-123">DisplayName</span></span>|<span data-ttu-id="b3873-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b3873-124">xs:string</span></span>|<span data-ttu-id="b3873-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b3873-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="b3873-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b3873-126">InstanceId</span></span>|<span data-ttu-id="b3873-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b3873-127">xs:string</span></span>|<span data-ttu-id="b3873-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="b3873-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b3873-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b3873-129">AppDomain</span></span>|<span data-ttu-id="b3873-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="b3873-130">xs:string</span></span>|<span data-ttu-id="b3873-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="b3873-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
