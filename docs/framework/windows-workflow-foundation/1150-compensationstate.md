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
ms.openlocfilehash: dc5de180030b8c07cb5ade268205e94079e0fbb9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1150---compensationstate"></a><span data-ttu-id="56f27-102">1150 - CompensationState</span><span class="sxs-lookup"><span data-stu-id="56f27-102">1150 - CompensationState</span></span>
## <a name="properties"></a><span data-ttu-id="56f27-103">属性</span><span class="sxs-lookup"><span data-stu-id="56f27-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56f27-104">ID</span><span class="sxs-lookup"><span data-stu-id="56f27-104">ID</span></span>|<span data-ttu-id="56f27-105">1150</span><span class="sxs-lookup"><span data-stu-id="56f27-105">1150</span></span>|  
|<span data-ttu-id="56f27-106">关键字</span><span class="sxs-lookup"><span data-stu-id="56f27-106">Keywords</span></span>|<span data-ttu-id="56f27-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="56f27-107">WFActivities</span></span>|  
|<span data-ttu-id="56f27-108">级别</span><span class="sxs-lookup"><span data-stu-id="56f27-108">Level</span></span>|<span data-ttu-id="56f27-109">信息</span><span class="sxs-lookup"><span data-stu-id="56f27-109">Information</span></span>|  
|<span data-ttu-id="56f27-110">通道</span><span class="sxs-lookup"><span data-stu-id="56f27-110">Channel</span></span>|<span data-ttu-id="56f27-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="56f27-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="56f27-112">描述</span><span class="sxs-lookup"><span data-stu-id="56f27-112">Description</span></span>  
 <span data-ttu-id="56f27-113">指示状态在 CompensableActivity 中发生更改。</span><span class="sxs-lookup"><span data-stu-id="56f27-113">Indicates a change of state in a CompensableActivity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="56f27-114">消息</span><span class="sxs-lookup"><span data-stu-id="56f27-114">Message</span></span>  
 <span data-ttu-id="56f27-115">CompensableActivity“%1”的状态为“%2”。</span><span class="sxs-lookup"><span data-stu-id="56f27-115">CompensableActivity '%1' is in the '%2' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="56f27-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="56f27-116">Details</span></span>  
  
|<span data-ttu-id="56f27-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="56f27-117">Data Item Name</span></span>|<span data-ttu-id="56f27-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="56f27-118">Data Item Type</span></span>|<span data-ttu-id="56f27-119">描述</span><span class="sxs-lookup"><span data-stu-id="56f27-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="56f27-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="56f27-120">DisplayName</span></span>|<span data-ttu-id="56f27-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="56f27-121">xs:string</span></span>|<span data-ttu-id="56f27-122">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="56f27-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="56f27-123">状态</span><span class="sxs-lookup"><span data-stu-id="56f27-123">State</span></span>|<span data-ttu-id="56f27-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="56f27-124">xs:string</span></span>|<span data-ttu-id="56f27-125">补偿状态。</span><span class="sxs-lookup"><span data-stu-id="56f27-125">The compensation state.</span></span>|  
|<span data-ttu-id="56f27-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="56f27-126">AppDomain</span></span>|<span data-ttu-id="56f27-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="56f27-127">xs:string</span></span>|<span data-ttu-id="56f27-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="56f27-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
