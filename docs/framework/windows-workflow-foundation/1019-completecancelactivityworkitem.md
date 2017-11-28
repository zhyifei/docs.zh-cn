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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9f8af4486d4659afd4c98016a6f88719271f1a1b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="5c7b6-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="5c7b6-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="5c7b6-103">属性</span><span class="sxs-lookup"><span data-stu-id="5c7b6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5c7b6-104">ID</span><span class="sxs-lookup"><span data-stu-id="5c7b6-104">ID</span></span>|<span data-ttu-id="5c7b6-105">1019</span><span class="sxs-lookup"><span data-stu-id="5c7b6-105">1019</span></span>|  
|<span data-ttu-id="5c7b6-106">关键字</span><span class="sxs-lookup"><span data-stu-id="5c7b6-106">Keywords</span></span>|<span data-ttu-id="5c7b6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5c7b6-107">WFRuntime</span></span>|  
|<span data-ttu-id="5c7b6-108">级别</span><span class="sxs-lookup"><span data-stu-id="5c7b6-108">Level</span></span>|<span data-ttu-id="5c7b6-109">详细</span><span class="sxs-lookup"><span data-stu-id="5c7b6-109">Verbose</span></span>|  
|<span data-ttu-id="5c7b6-110">通道</span><span class="sxs-lookup"><span data-stu-id="5c7b6-110">Channel</span></span>|<span data-ttu-id="5c7b6-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="5c7b6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5c7b6-112">描述</span><span class="sxs-lookup"><span data-stu-id="5c7b6-112">Description</span></span>  
 <span data-ttu-id="5c7b6-113">指示 CancelActivityWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="5c7b6-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5c7b6-114">消息</span><span class="sxs-lookup"><span data-stu-id="5c7b6-114">Message</span></span>  
 <span data-ttu-id="5c7b6-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的 CancelActivityWorkItem 已经完成。</span><span class="sxs-lookup"><span data-stu-id="5c7b6-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5c7b6-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="5c7b6-116">Details</span></span>  
  
|<span data-ttu-id="5c7b6-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="5c7b6-117">Data Item Name</span></span>|<span data-ttu-id="5c7b6-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="5c7b6-118">Data Item Type</span></span>|<span data-ttu-id="5c7b6-119">描述</span><span class="sxs-lookup"><span data-stu-id="5c7b6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5c7b6-120">Activity</span><span class="sxs-lookup"><span data-stu-id="5c7b6-120">Activity</span></span>|<span data-ttu-id="5c7b6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5c7b6-121">xs:string</span></span>|<span data-ttu-id="5c7b6-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="5c7b6-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="5c7b6-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5c7b6-123">DisplayName</span></span>|<span data-ttu-id="5c7b6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5c7b6-124">xs:string</span></span>|<span data-ttu-id="5c7b6-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="5c7b6-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="5c7b6-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5c7b6-126">InstanceId</span></span>|<span data-ttu-id="5c7b6-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="5c7b6-127">xs:string</span></span>|<span data-ttu-id="5c7b6-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="5c7b6-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="5c7b6-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5c7b6-129">AppDomain</span></span>|<span data-ttu-id="5c7b6-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="5c7b6-130">xs:string</span></span>|<span data-ttu-id="5c7b6-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="5c7b6-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
