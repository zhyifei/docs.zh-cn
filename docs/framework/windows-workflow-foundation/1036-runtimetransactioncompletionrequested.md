---
title: 1036 - RuntimeTransactionCompletionRequested
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4f497d777221a98b38603b2ced29342651b1020b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="e7dc3-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="e7dc3-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="e7dc3-103">属性</span><span class="sxs-lookup"><span data-stu-id="e7dc3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e7dc3-104">ID</span><span class="sxs-lookup"><span data-stu-id="e7dc3-104">ID</span></span>|<span data-ttu-id="e7dc3-105">1036</span><span class="sxs-lookup"><span data-stu-id="e7dc3-105">1036</span></span>|  
|<span data-ttu-id="e7dc3-106">关键字</span><span class="sxs-lookup"><span data-stu-id="e7dc3-106">Keywords</span></span>|<span data-ttu-id="e7dc3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e7dc3-107">WFRuntime</span></span>|  
|<span data-ttu-id="e7dc3-108">级别</span><span class="sxs-lookup"><span data-stu-id="e7dc3-108">Level</span></span>|<span data-ttu-id="e7dc3-109">详细</span><span class="sxs-lookup"><span data-stu-id="e7dc3-109">Verbose</span></span>|  
|<span data-ttu-id="e7dc3-110">通道</span><span class="sxs-lookup"><span data-stu-id="e7dc3-110">Channel</span></span>|<span data-ttu-id="e7dc3-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="e7dc3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e7dc3-112">描述</span><span class="sxs-lookup"><span data-stu-id="e7dc3-112">Description</span></span>  
 <span data-ttu-id="e7dc3-113">指示活动已安排了运行时事务的完成。</span><span class="sxs-lookup"><span data-stu-id="e7dc3-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e7dc3-114">消息</span><span class="sxs-lookup"><span data-stu-id="e7dc3-114">Message</span></span>  
 <span data-ttu-id="e7dc3-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”已安排了运行时事务的完成。</span><span class="sxs-lookup"><span data-stu-id="e7dc3-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e7dc3-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="e7dc3-116">Details</span></span>  
  
|<span data-ttu-id="e7dc3-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="e7dc3-117">Data Item Name</span></span>|<span data-ttu-id="e7dc3-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="e7dc3-118">Data Item Type</span></span>|<span data-ttu-id="e7dc3-119">描述</span><span class="sxs-lookup"><span data-stu-id="e7dc3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e7dc3-120">Activity</span><span class="sxs-lookup"><span data-stu-id="e7dc3-120">Activity</span></span>|<span data-ttu-id="e7dc3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e7dc3-121">xs:string</span></span>|<span data-ttu-id="e7dc3-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="e7dc3-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="e7dc3-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e7dc3-123">DisplayName</span></span>|<span data-ttu-id="e7dc3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e7dc3-124">xs:string</span></span>|<span data-ttu-id="e7dc3-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="e7dc3-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="e7dc3-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e7dc3-126">InstanceId</span></span>|<span data-ttu-id="e7dc3-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="e7dc3-127">xs:string</span></span>|<span data-ttu-id="e7dc3-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="e7dc3-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="e7dc3-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e7dc3-129">AppDomain</span></span>|<span data-ttu-id="e7dc3-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e7dc3-130">xs:string</span></span>|<span data-ttu-id="e7dc3-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="e7dc3-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
