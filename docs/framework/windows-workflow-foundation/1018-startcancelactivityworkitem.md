---
title: 1018 - StartCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f74a133a685699bcefc014269a9ecb3ebea4e505
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="3e4f2-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="3e4f2-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3e4f2-103">属性</span><span class="sxs-lookup"><span data-stu-id="3e4f2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3e4f2-104">ID</span><span class="sxs-lookup"><span data-stu-id="3e4f2-104">ID</span></span>|<span data-ttu-id="3e4f2-105">1018</span><span class="sxs-lookup"><span data-stu-id="3e4f2-105">1018</span></span>|  
|<span data-ttu-id="3e4f2-106">关键字</span><span class="sxs-lookup"><span data-stu-id="3e4f2-106">Keywords</span></span>|<span data-ttu-id="3e4f2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3e4f2-107">WFRuntime</span></span>|  
|<span data-ttu-id="3e4f2-108">级别</span><span class="sxs-lookup"><span data-stu-id="3e4f2-108">Level</span></span>|<span data-ttu-id="3e4f2-109">详细</span><span class="sxs-lookup"><span data-stu-id="3e4f2-109">Verbose</span></span>|  
|<span data-ttu-id="3e4f2-110">通道</span><span class="sxs-lookup"><span data-stu-id="3e4f2-110">Channel</span></span>|<span data-ttu-id="3e4f2-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="3e4f2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3e4f2-112">描述</span><span class="sxs-lookup"><span data-stu-id="3e4f2-112">Description</span></span>  
 <span data-ttu-id="3e4f2-113">指示 CancelActivityWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="3e4f2-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3e4f2-114">消息</span><span class="sxs-lookup"><span data-stu-id="3e4f2-114">Message</span></span>  
 <span data-ttu-id="3e4f2-115">开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 CancelActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="3e4f2-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3e4f2-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="3e4f2-116">Details</span></span>  
  
|<span data-ttu-id="3e4f2-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="3e4f2-117">Data Item Name</span></span>|<span data-ttu-id="3e4f2-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="3e4f2-118">Data Item Type</span></span>|<span data-ttu-id="3e4f2-119">描述</span><span class="sxs-lookup"><span data-stu-id="3e4f2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3e4f2-120">Activity</span><span class="sxs-lookup"><span data-stu-id="3e4f2-120">Activity</span></span>|<span data-ttu-id="3e4f2-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e4f2-121">xs:string</span></span>|<span data-ttu-id="3e4f2-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="3e4f2-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3e4f2-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3e4f2-123">DisplayName</span></span>|<span data-ttu-id="3e4f2-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e4f2-124">xs:string</span></span>|<span data-ttu-id="3e4f2-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="3e4f2-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3e4f2-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3e4f2-126">InstanceId</span></span>|<span data-ttu-id="3e4f2-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e4f2-127">xs:string</span></span>|<span data-ttu-id="3e4f2-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="3e4f2-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3e4f2-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3e4f2-129">AppDomain</span></span>|<span data-ttu-id="3e4f2-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e4f2-130">xs:string</span></span>|<span data-ttu-id="3e4f2-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="3e4f2-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
