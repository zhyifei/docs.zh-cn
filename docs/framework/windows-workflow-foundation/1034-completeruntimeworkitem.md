---
title: 1034 - CompleteRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 743b16232e239929f75e269faa16799a37043495
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="edf05-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="edf05-102">1034 - CompleteRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="edf05-103">属性</span><span class="sxs-lookup"><span data-stu-id="edf05-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="edf05-104">ID</span><span class="sxs-lookup"><span data-stu-id="edf05-104">ID</span></span>|<span data-ttu-id="edf05-105">1034</span><span class="sxs-lookup"><span data-stu-id="edf05-105">1034</span></span>|  
|<span data-ttu-id="edf05-106">关键字</span><span class="sxs-lookup"><span data-stu-id="edf05-106">Keywords</span></span>|<span data-ttu-id="edf05-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="edf05-107">WFRuntime</span></span>|  
|<span data-ttu-id="edf05-108">级别</span><span class="sxs-lookup"><span data-stu-id="edf05-108">Level</span></span>|<span data-ttu-id="edf05-109">详细</span><span class="sxs-lookup"><span data-stu-id="edf05-109">Verbose</span></span>|  
|<span data-ttu-id="edf05-110">通道</span><span class="sxs-lookup"><span data-stu-id="edf05-110">Channel</span></span>|<span data-ttu-id="edf05-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="edf05-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="edf05-112">描述</span><span class="sxs-lookup"><span data-stu-id="edf05-112">Description</span></span>  
 <span data-ttu-id="edf05-113">指示 RuntimeWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="edf05-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="edf05-114">消息</span><span class="sxs-lookup"><span data-stu-id="edf05-114">Message</span></span>  
 <span data-ttu-id="edf05-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的运行时工作项已经完成。</span><span class="sxs-lookup"><span data-stu-id="edf05-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="edf05-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="edf05-116">Details</span></span>  
  
|<span data-ttu-id="edf05-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="edf05-117">Data Item Name</span></span>|<span data-ttu-id="edf05-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="edf05-118">Data Item Type</span></span>|<span data-ttu-id="edf05-119">描述</span><span class="sxs-lookup"><span data-stu-id="edf05-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="edf05-120">Activity</span><span class="sxs-lookup"><span data-stu-id="edf05-120">Activity</span></span>|<span data-ttu-id="edf05-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="edf05-121">xs:string</span></span>|<span data-ttu-id="edf05-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="edf05-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="edf05-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="edf05-123">DisplayName</span></span>|<span data-ttu-id="edf05-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="edf05-124">xs:string</span></span>|<span data-ttu-id="edf05-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="edf05-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="edf05-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="edf05-126">InstanceId</span></span>|<span data-ttu-id="edf05-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="edf05-127">xs:string</span></span>|<span data-ttu-id="edf05-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="edf05-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="edf05-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="edf05-129">AppDomain</span></span>|<span data-ttu-id="edf05-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="edf05-130">xs:string</span></span>|<span data-ttu-id="edf05-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="edf05-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
