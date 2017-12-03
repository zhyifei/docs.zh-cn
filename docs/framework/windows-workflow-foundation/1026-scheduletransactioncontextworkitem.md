---
title: 1026 - ScheduleTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a5fb800718c1fd231d0cd02bf015333a44fa794f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="9a9b3-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="9a9b3-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="9a9b3-103">属性</span><span class="sxs-lookup"><span data-stu-id="9a9b3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9a9b3-104">ID</span><span class="sxs-lookup"><span data-stu-id="9a9b3-104">ID</span></span>|<span data-ttu-id="9a9b3-105">1026</span><span class="sxs-lookup"><span data-stu-id="9a9b3-105">1026</span></span>|  
|<span data-ttu-id="9a9b3-106">关键字</span><span class="sxs-lookup"><span data-stu-id="9a9b3-106">Keywords</span></span>|<span data-ttu-id="9a9b3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9a9b3-107">WFRuntime</span></span>|  
|<span data-ttu-id="9a9b3-108">级别</span><span class="sxs-lookup"><span data-stu-id="9a9b3-108">Level</span></span>|<span data-ttu-id="9a9b3-109">详细</span><span class="sxs-lookup"><span data-stu-id="9a9b3-109">Verbose</span></span>|  
|<span data-ttu-id="9a9b3-110">通道</span><span class="sxs-lookup"><span data-stu-id="9a9b3-110">Channel</span></span>|<span data-ttu-id="9a9b3-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="9a9b3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9a9b3-112">描述</span><span class="sxs-lookup"><span data-stu-id="9a9b3-112">Description</span></span>  
 <span data-ttu-id="9a9b3-113">指示已安排 TransactionContextWorkItem。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9a9b3-114">消息</span><span class="sxs-lookup"><span data-stu-id="9a9b3-114">Message</span></span>  
 <span data-ttu-id="9a9b3-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了 TransactionContextWorkItem。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9a9b3-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="9a9b3-116">Details</span></span>  
  
|<span data-ttu-id="9a9b3-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="9a9b3-117">Data Item Name</span></span>|<span data-ttu-id="9a9b3-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="9a9b3-118">Data Item Type</span></span>|<span data-ttu-id="9a9b3-119">描述</span><span class="sxs-lookup"><span data-stu-id="9a9b3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9a9b3-120">Activity</span><span class="sxs-lookup"><span data-stu-id="9a9b3-120">Activity</span></span>|<span data-ttu-id="9a9b3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9a9b3-121">xs:string</span></span>|<span data-ttu-id="9a9b3-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="9a9b3-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9a9b3-123">DisplayName</span></span>|<span data-ttu-id="9a9b3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9a9b3-124">xs:string</span></span>|<span data-ttu-id="9a9b3-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="9a9b3-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="9a9b3-126">InstanceId</span></span>|<span data-ttu-id="9a9b3-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9a9b3-127">xs:string</span></span>|<span data-ttu-id="9a9b3-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="9a9b3-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9a9b3-129">AppDomain</span></span>|<span data-ttu-id="9a9b3-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="9a9b3-130">xs:string</span></span>|<span data-ttu-id="9a9b3-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="9a9b3-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
