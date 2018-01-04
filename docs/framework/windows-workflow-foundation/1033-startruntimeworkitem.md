---
title: 1033 - StartRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df5502c3d2cb1e9ec9454ed43c3a468a27307d07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="8a18d-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="8a18d-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8a18d-103">属性</span><span class="sxs-lookup"><span data-stu-id="8a18d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a18d-104">ID</span><span class="sxs-lookup"><span data-stu-id="8a18d-104">ID</span></span>|<span data-ttu-id="8a18d-105">1033</span><span class="sxs-lookup"><span data-stu-id="8a18d-105">1033</span></span>|  
|<span data-ttu-id="8a18d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="8a18d-106">Keywords</span></span>|<span data-ttu-id="8a18d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8a18d-107">WFRuntime</span></span>|  
|<span data-ttu-id="8a18d-108">级别</span><span class="sxs-lookup"><span data-stu-id="8a18d-108">Level</span></span>|<span data-ttu-id="8a18d-109">详细</span><span class="sxs-lookup"><span data-stu-id="8a18d-109">Verbose</span></span>|  
|<span data-ttu-id="8a18d-110">通道</span><span class="sxs-lookup"><span data-stu-id="8a18d-110">Channel</span></span>|<span data-ttu-id="8a18d-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="8a18d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8a18d-112">描述</span><span class="sxs-lookup"><span data-stu-id="8a18d-112">Description</span></span>  
 <span data-ttu-id="8a18d-113">指示 RuntimeWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="8a18d-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8a18d-114">消息</span><span class="sxs-lookup"><span data-stu-id="8a18d-114">Message</span></span>  
 <span data-ttu-id="8a18d-115">开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行运行时工作项。</span><span class="sxs-lookup"><span data-stu-id="8a18d-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8a18d-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="8a18d-116">Details</span></span>  
  
|<span data-ttu-id="8a18d-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="8a18d-117">Data Item Name</span></span>|<span data-ttu-id="8a18d-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="8a18d-118">Data Item Type</span></span>|<span data-ttu-id="8a18d-119">描述</span><span class="sxs-lookup"><span data-stu-id="8a18d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8a18d-120">Activity</span><span class="sxs-lookup"><span data-stu-id="8a18d-120">Activity</span></span>|<span data-ttu-id="8a18d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a18d-121">xs:string</span></span>|<span data-ttu-id="8a18d-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="8a18d-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8a18d-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8a18d-123">DisplayName</span></span>|<span data-ttu-id="8a18d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a18d-124">xs:string</span></span>|<span data-ttu-id="8a18d-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="8a18d-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8a18d-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8a18d-126">InstanceId</span></span>|<span data-ttu-id="8a18d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a18d-127">xs:string</span></span>|<span data-ttu-id="8a18d-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="8a18d-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8a18d-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8a18d-129">AppDomain</span></span>|<span data-ttu-id="8a18d-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a18d-130">xs:string</span></span>|<span data-ttu-id="8a18d-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="8a18d-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
