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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5debccf664768b84a7b213cd012b484df8fe3ef8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1150---compensationstate"></a><span data-ttu-id="9b47c-102">1150 - CompensationState</span><span class="sxs-lookup"><span data-stu-id="9b47c-102">1150 - CompensationState</span></span>
## <a name="properties"></a><span data-ttu-id="9b47c-103">属性</span><span class="sxs-lookup"><span data-stu-id="9b47c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9b47c-104">ID</span><span class="sxs-lookup"><span data-stu-id="9b47c-104">ID</span></span>|<span data-ttu-id="9b47c-105">1150</span><span class="sxs-lookup"><span data-stu-id="9b47c-105">1150</span></span>|  
|<span data-ttu-id="9b47c-106">关键字</span><span class="sxs-lookup"><span data-stu-id="9b47c-106">Keywords</span></span>|<span data-ttu-id="9b47c-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="9b47c-107">WFActivities</span></span>|  
|<span data-ttu-id="9b47c-108">级别</span><span class="sxs-lookup"><span data-stu-id="9b47c-108">Level</span></span>|<span data-ttu-id="9b47c-109">信息</span><span class="sxs-lookup"><span data-stu-id="9b47c-109">Information</span></span>|  
|<span data-ttu-id="9b47c-110">通道</span><span class="sxs-lookup"><span data-stu-id="9b47c-110">Channel</span></span>|<span data-ttu-id="9b47c-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="9b47c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9b47c-112">描述</span><span class="sxs-lookup"><span data-stu-id="9b47c-112">Description</span></span>  
 <span data-ttu-id="9b47c-113">指示状态在 CompensableActivity 中发生更改。</span><span class="sxs-lookup"><span data-stu-id="9b47c-113">Indicates a change of state in a CompensableActivity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9b47c-114">消息</span><span class="sxs-lookup"><span data-stu-id="9b47c-114">Message</span></span>  
 <span data-ttu-id="9b47c-115">CompensableActivity“%1”的状态为“%2”。</span><span class="sxs-lookup"><span data-stu-id="9b47c-115">CompensableActivity '%1' is in the '%2' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9b47c-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="9b47c-116">Details</span></span>  
  
|<span data-ttu-id="9b47c-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="9b47c-117">Data Item Name</span></span>|<span data-ttu-id="9b47c-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="9b47c-118">Data Item Type</span></span>|<span data-ttu-id="9b47c-119">描述</span><span class="sxs-lookup"><span data-stu-id="9b47c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9b47c-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9b47c-120">DisplayName</span></span>|<span data-ttu-id="9b47c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9b47c-121">xs:string</span></span>|<span data-ttu-id="9b47c-122">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="9b47c-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="9b47c-123">状态</span><span class="sxs-lookup"><span data-stu-id="9b47c-123">State</span></span>|<span data-ttu-id="9b47c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9b47c-124">xs:string</span></span>|<span data-ttu-id="9b47c-125">补偿状态。</span><span class="sxs-lookup"><span data-stu-id="9b47c-125">The compensation state.</span></span>|  
|<span data-ttu-id="9b47c-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9b47c-126">AppDomain</span></span>|<span data-ttu-id="9b47c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9b47c-127">xs:string</span></span>|<span data-ttu-id="9b47c-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="9b47c-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
