---
title: 1012 - StartExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a3b03e8ac24bc1652b88b71e8c25862a07c194f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="8948b-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="8948b-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8948b-103">属性</span><span class="sxs-lookup"><span data-stu-id="8948b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8948b-104">ID</span><span class="sxs-lookup"><span data-stu-id="8948b-104">ID</span></span>|<span data-ttu-id="8948b-105">1012</span><span class="sxs-lookup"><span data-stu-id="8948b-105">1012</span></span>|  
|<span data-ttu-id="8948b-106">关键字</span><span class="sxs-lookup"><span data-stu-id="8948b-106">Keywords</span></span>|<span data-ttu-id="8948b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8948b-107">WFRuntime</span></span>|  
|<span data-ttu-id="8948b-108">级别</span><span class="sxs-lookup"><span data-stu-id="8948b-108">Level</span></span>|<span data-ttu-id="8948b-109">详细</span><span class="sxs-lookup"><span data-stu-id="8948b-109">Verbose</span></span>|  
|<span data-ttu-id="8948b-110">通道</span><span class="sxs-lookup"><span data-stu-id="8948b-110">Channel</span></span>|<span data-ttu-id="8948b-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="8948b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8948b-112">描述</span><span class="sxs-lookup"><span data-stu-id="8948b-112">Description</span></span>  
 <span data-ttu-id="8948b-113">指示 ExecuteActivityWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="8948b-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8948b-114">消息</span><span class="sxs-lookup"><span data-stu-id="8948b-114">Message</span></span>  
 <span data-ttu-id="8948b-115">开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 ExecuteActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="8948b-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8948b-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="8948b-116">Details</span></span>  
  
|<span data-ttu-id="8948b-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="8948b-117">Data Item Name</span></span>|<span data-ttu-id="8948b-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="8948b-118">Data Item Type</span></span>|<span data-ttu-id="8948b-119">描述</span><span class="sxs-lookup"><span data-stu-id="8948b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8948b-120">Activity</span><span class="sxs-lookup"><span data-stu-id="8948b-120">Activity</span></span>|<span data-ttu-id="8948b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8948b-121">xs:string</span></span>|<span data-ttu-id="8948b-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="8948b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8948b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8948b-123">DisplayName</span></span>|<span data-ttu-id="8948b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8948b-124">xs:string</span></span>|<span data-ttu-id="8948b-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="8948b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8948b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8948b-126">InstanceId</span></span>|<span data-ttu-id="8948b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8948b-127">xs:string</span></span>|<span data-ttu-id="8948b-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="8948b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8948b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8948b-129">AppDomain</span></span>|<span data-ttu-id="8948b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8948b-130">xs:string</span></span>|<span data-ttu-id="8948b-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="8948b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
