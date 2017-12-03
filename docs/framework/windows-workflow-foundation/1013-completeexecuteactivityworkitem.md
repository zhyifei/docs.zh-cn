---
title: 1013 - CompleteExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de9add3f537c1d8ff97c92892197598bcc7a4fe7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="a34c1-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="a34c1-102">1013 - CompleteExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="a34c1-103">属性</span><span class="sxs-lookup"><span data-stu-id="a34c1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a34c1-104">ID</span><span class="sxs-lookup"><span data-stu-id="a34c1-104">ID</span></span>|<span data-ttu-id="a34c1-105">1013</span><span class="sxs-lookup"><span data-stu-id="a34c1-105">1013</span></span>|  
|<span data-ttu-id="a34c1-106">关键字</span><span class="sxs-lookup"><span data-stu-id="a34c1-106">Keywords</span></span>|<span data-ttu-id="a34c1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a34c1-107">WFRuntime</span></span>|  
|<span data-ttu-id="a34c1-108">级别</span><span class="sxs-lookup"><span data-stu-id="a34c1-108">Level</span></span>|<span data-ttu-id="a34c1-109">详细</span><span class="sxs-lookup"><span data-stu-id="a34c1-109">Verbose</span></span>|  
|<span data-ttu-id="a34c1-110">通道</span><span class="sxs-lookup"><span data-stu-id="a34c1-110">Channel</span></span>|<span data-ttu-id="a34c1-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="a34c1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a34c1-112">描述</span><span class="sxs-lookup"><span data-stu-id="a34c1-112">Description</span></span>  
 <span data-ttu-id="a34c1-113">指示 ExecuteActivityWorkItem 已完成</span><span class="sxs-lookup"><span data-stu-id="a34c1-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="a34c1-114">消息</span><span class="sxs-lookup"><span data-stu-id="a34c1-114">Message</span></span>  
 <span data-ttu-id="a34c1-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的 ExecuteActivityWorkItem 已经完成。</span><span class="sxs-lookup"><span data-stu-id="a34c1-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a34c1-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="a34c1-116">Details</span></span>  
  
|<span data-ttu-id="a34c1-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="a34c1-117">Data Item Name</span></span>|<span data-ttu-id="a34c1-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="a34c1-118">Data Item Type</span></span>|<span data-ttu-id="a34c1-119">描述</span><span class="sxs-lookup"><span data-stu-id="a34c1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a34c1-120">Activity</span><span class="sxs-lookup"><span data-stu-id="a34c1-120">Activity</span></span>|<span data-ttu-id="a34c1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a34c1-121">xs:string</span></span>|<span data-ttu-id="a34c1-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="a34c1-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="a34c1-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a34c1-123">DisplayName</span></span>|<span data-ttu-id="a34c1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a34c1-124">xs:string</span></span>|<span data-ttu-id="a34c1-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="a34c1-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="a34c1-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a34c1-126">InstanceId</span></span>|<span data-ttu-id="a34c1-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="a34c1-127">xs:string</span></span>|<span data-ttu-id="a34c1-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="a34c1-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="a34c1-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a34c1-129">AppDomain</span></span>|<span data-ttu-id="a34c1-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="a34c1-130">xs:string</span></span>|<span data-ttu-id="a34c1-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="a34c1-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
