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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b64ea860e9881ed31aa0d8e78dec55f329cc6fad
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="7824c-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="7824c-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="7824c-103">属性</span><span class="sxs-lookup"><span data-stu-id="7824c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7824c-104">ID</span><span class="sxs-lookup"><span data-stu-id="7824c-104">ID</span></span>|<span data-ttu-id="7824c-105">1018</span><span class="sxs-lookup"><span data-stu-id="7824c-105">1018</span></span>|  
|<span data-ttu-id="7824c-106">关键字</span><span class="sxs-lookup"><span data-stu-id="7824c-106">Keywords</span></span>|<span data-ttu-id="7824c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7824c-107">WFRuntime</span></span>|  
|<span data-ttu-id="7824c-108">级别</span><span class="sxs-lookup"><span data-stu-id="7824c-108">Level</span></span>|<span data-ttu-id="7824c-109">详细</span><span class="sxs-lookup"><span data-stu-id="7824c-109">Verbose</span></span>|  
|<span data-ttu-id="7824c-110">通道</span><span class="sxs-lookup"><span data-stu-id="7824c-110">Channel</span></span>|<span data-ttu-id="7824c-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="7824c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7824c-112">描述</span><span class="sxs-lookup"><span data-stu-id="7824c-112">Description</span></span>  
 <span data-ttu-id="7824c-113">指示 CancelActivityWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="7824c-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7824c-114">消息</span><span class="sxs-lookup"><span data-stu-id="7824c-114">Message</span></span>  
 <span data-ttu-id="7824c-115">开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 CancelActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="7824c-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7824c-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="7824c-116">Details</span></span>  
  
|<span data-ttu-id="7824c-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="7824c-117">Data Item Name</span></span>|<span data-ttu-id="7824c-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="7824c-118">Data Item Type</span></span>|<span data-ttu-id="7824c-119">描述</span><span class="sxs-lookup"><span data-stu-id="7824c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7824c-120">Activity</span><span class="sxs-lookup"><span data-stu-id="7824c-120">Activity</span></span>|<span data-ttu-id="7824c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="7824c-121">xs:string</span></span>|<span data-ttu-id="7824c-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="7824c-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="7824c-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7824c-123">DisplayName</span></span>|<span data-ttu-id="7824c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="7824c-124">xs:string</span></span>|<span data-ttu-id="7824c-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="7824c-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="7824c-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="7824c-126">InstanceId</span></span>|<span data-ttu-id="7824c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="7824c-127">xs:string</span></span>|<span data-ttu-id="7824c-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="7824c-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="7824c-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7824c-129">AppDomain</span></span>|<span data-ttu-id="7824c-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="7824c-130">xs:string</span></span>|<span data-ttu-id="7824c-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="7824c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
