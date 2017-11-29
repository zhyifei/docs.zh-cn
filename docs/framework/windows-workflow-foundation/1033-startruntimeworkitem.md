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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0de8e45a592cae49060f976b28a7a7bcf8781265
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="c1acc-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="c1acc-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="c1acc-103">属性</span><span class="sxs-lookup"><span data-stu-id="c1acc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c1acc-104">ID</span><span class="sxs-lookup"><span data-stu-id="c1acc-104">ID</span></span>|<span data-ttu-id="c1acc-105">2052</span><span class="sxs-lookup"><span data-stu-id="c1acc-105">1033</span></span>|  
|<span data-ttu-id="c1acc-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c1acc-106">Keywords</span></span>|<span data-ttu-id="c1acc-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c1acc-107">WFRuntime</span></span>|  
|<span data-ttu-id="c1acc-108">级别</span><span class="sxs-lookup"><span data-stu-id="c1acc-108">Level</span></span>|<span data-ttu-id="c1acc-109">详细</span><span class="sxs-lookup"><span data-stu-id="c1acc-109">Verbose</span></span>|  
|<span data-ttu-id="c1acc-110">通道</span><span class="sxs-lookup"><span data-stu-id="c1acc-110">Channel</span></span>|<span data-ttu-id="c1acc-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c1acc-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c1acc-112">描述</span><span class="sxs-lookup"><span data-stu-id="c1acc-112">Description</span></span>  
 <span data-ttu-id="c1acc-113">指示 RuntimeWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="c1acc-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c1acc-114">消息</span><span class="sxs-lookup"><span data-stu-id="c1acc-114">Message</span></span>  
 <span data-ttu-id="c1acc-115">开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行运行时工作项。</span><span class="sxs-lookup"><span data-stu-id="c1acc-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c1acc-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="c1acc-116">Details</span></span>  
  
|<span data-ttu-id="c1acc-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="c1acc-117">Data Item Name</span></span>|<span data-ttu-id="c1acc-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="c1acc-118">Data Item Type</span></span>|<span data-ttu-id="c1acc-119">描述</span><span class="sxs-lookup"><span data-stu-id="c1acc-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c1acc-120">Activity</span><span class="sxs-lookup"><span data-stu-id="c1acc-120">Activity</span></span>|<span data-ttu-id="c1acc-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1acc-121">xs:string</span></span>|<span data-ttu-id="c1acc-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="c1acc-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="c1acc-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c1acc-123">DisplayName</span></span>|<span data-ttu-id="c1acc-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1acc-124">xs:string</span></span>|<span data-ttu-id="c1acc-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c1acc-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="c1acc-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c1acc-126">InstanceId</span></span>|<span data-ttu-id="c1acc-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1acc-127">xs:string</span></span>|<span data-ttu-id="c1acc-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="c1acc-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c1acc-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c1acc-129">AppDomain</span></span>|<span data-ttu-id="c1acc-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1acc-130">xs:string</span></span>|<span data-ttu-id="c1acc-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="c1acc-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
