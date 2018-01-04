---
title: 1150 - CompensationState
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28621fceab89a2302decafb1c97cdebf406888df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1150---compensationstate"></a><span data-ttu-id="4ba59-102">1150 - CompensationState</span><span class="sxs-lookup"><span data-stu-id="4ba59-102">1150 - CompensationState</span></span>
## <a name="properties"></a><span data-ttu-id="4ba59-103">属性</span><span class="sxs-lookup"><span data-stu-id="4ba59-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4ba59-104">ID</span><span class="sxs-lookup"><span data-stu-id="4ba59-104">ID</span></span>|<span data-ttu-id="4ba59-105">1150</span><span class="sxs-lookup"><span data-stu-id="4ba59-105">1150</span></span>|  
|<span data-ttu-id="4ba59-106">关键字</span><span class="sxs-lookup"><span data-stu-id="4ba59-106">Keywords</span></span>|<span data-ttu-id="4ba59-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="4ba59-107">WFActivities</span></span>|  
|<span data-ttu-id="4ba59-108">级别</span><span class="sxs-lookup"><span data-stu-id="4ba59-108">Level</span></span>|<span data-ttu-id="4ba59-109">信息</span><span class="sxs-lookup"><span data-stu-id="4ba59-109">Information</span></span>|  
|<span data-ttu-id="4ba59-110">通道</span><span class="sxs-lookup"><span data-stu-id="4ba59-110">Channel</span></span>|<span data-ttu-id="4ba59-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="4ba59-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4ba59-112">描述</span><span class="sxs-lookup"><span data-stu-id="4ba59-112">Description</span></span>  
 <span data-ttu-id="4ba59-113">指示状态在 CompensableActivity 中发生更改。</span><span class="sxs-lookup"><span data-stu-id="4ba59-113">Indicates a change of state in a CompensableActivity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4ba59-114">消息</span><span class="sxs-lookup"><span data-stu-id="4ba59-114">Message</span></span>  
 <span data-ttu-id="4ba59-115">CompensableActivity“%1”的状态为“%2”。</span><span class="sxs-lookup"><span data-stu-id="4ba59-115">CompensableActivity '%1' is in the '%2' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4ba59-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="4ba59-116">Details</span></span>  
  
|<span data-ttu-id="4ba59-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="4ba59-117">Data Item Name</span></span>|<span data-ttu-id="4ba59-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="4ba59-118">Data Item Type</span></span>|<span data-ttu-id="4ba59-119">描述</span><span class="sxs-lookup"><span data-stu-id="4ba59-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4ba59-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4ba59-120">DisplayName</span></span>|<span data-ttu-id="4ba59-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ba59-121">xs:string</span></span>|<span data-ttu-id="4ba59-122">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="4ba59-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="4ba59-123">状态</span><span class="sxs-lookup"><span data-stu-id="4ba59-123">State</span></span>|<span data-ttu-id="4ba59-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ba59-124">xs:string</span></span>|<span data-ttu-id="4ba59-125">补偿状态。</span><span class="sxs-lookup"><span data-stu-id="4ba59-125">The compensation state.</span></span>|  
|<span data-ttu-id="4ba59-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4ba59-126">AppDomain</span></span>|<span data-ttu-id="4ba59-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ba59-127">xs:string</span></span>|<span data-ttu-id="4ba59-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="4ba59-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
