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
ms.workload: dotnet
ms.openlocfilehash: 2d64d18474ff867ee5679e07c18a288f07185f60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="989ea-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="989ea-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="989ea-103">属性</span><span class="sxs-lookup"><span data-stu-id="989ea-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="989ea-104">ID</span><span class="sxs-lookup"><span data-stu-id="989ea-104">ID</span></span>|<span data-ttu-id="989ea-105">1018</span><span class="sxs-lookup"><span data-stu-id="989ea-105">1018</span></span>|  
|<span data-ttu-id="989ea-106">关键字</span><span class="sxs-lookup"><span data-stu-id="989ea-106">Keywords</span></span>|<span data-ttu-id="989ea-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="989ea-107">WFRuntime</span></span>|  
|<span data-ttu-id="989ea-108">级别</span><span class="sxs-lookup"><span data-stu-id="989ea-108">Level</span></span>|<span data-ttu-id="989ea-109">详细</span><span class="sxs-lookup"><span data-stu-id="989ea-109">Verbose</span></span>|  
|<span data-ttu-id="989ea-110">通道</span><span class="sxs-lookup"><span data-stu-id="989ea-110">Channel</span></span>|<span data-ttu-id="989ea-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="989ea-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="989ea-112">描述</span><span class="sxs-lookup"><span data-stu-id="989ea-112">Description</span></span>  
 <span data-ttu-id="989ea-113">指示 CancelActivityWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="989ea-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="989ea-114">消息</span><span class="sxs-lookup"><span data-stu-id="989ea-114">Message</span></span>  
 <span data-ttu-id="989ea-115">开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 CancelActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="989ea-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="989ea-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="989ea-116">Details</span></span>  
  
|<span data-ttu-id="989ea-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="989ea-117">Data Item Name</span></span>|<span data-ttu-id="989ea-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="989ea-118">Data Item Type</span></span>|<span data-ttu-id="989ea-119">描述</span><span class="sxs-lookup"><span data-stu-id="989ea-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="989ea-120">Activity</span><span class="sxs-lookup"><span data-stu-id="989ea-120">Activity</span></span>|<span data-ttu-id="989ea-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="989ea-121">xs:string</span></span>|<span data-ttu-id="989ea-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="989ea-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="989ea-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="989ea-123">DisplayName</span></span>|<span data-ttu-id="989ea-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="989ea-124">xs:string</span></span>|<span data-ttu-id="989ea-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="989ea-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="989ea-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="989ea-126">InstanceId</span></span>|<span data-ttu-id="989ea-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="989ea-127">xs:string</span></span>|<span data-ttu-id="989ea-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="989ea-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="989ea-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="989ea-129">AppDomain</span></span>|<span data-ttu-id="989ea-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="989ea-130">xs:string</span></span>|<span data-ttu-id="989ea-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="989ea-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
