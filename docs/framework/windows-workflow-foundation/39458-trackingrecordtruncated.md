---
title: 39458 - TrackingRecordTruncated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d2bc07cff75fce7ddb50da9f54d161d7f235cab
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="d7ee1-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="d7ee1-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="d7ee1-103">属性</span><span class="sxs-lookup"><span data-stu-id="d7ee1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7ee1-104">ID</span><span class="sxs-lookup"><span data-stu-id="d7ee1-104">ID</span></span>|<span data-ttu-id="d7ee1-105">39458</span><span class="sxs-lookup"><span data-stu-id="d7ee1-105">39458</span></span>|  
|<span data-ttu-id="d7ee1-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d7ee1-106">Keywords</span></span>|<span data-ttu-id="d7ee1-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="d7ee1-107">WFTracking</span></span>|  
|<span data-ttu-id="d7ee1-108">级别</span><span class="sxs-lookup"><span data-stu-id="d7ee1-108">Level</span></span>|<span data-ttu-id="d7ee1-109">警告</span><span class="sxs-lookup"><span data-stu-id="d7ee1-109">Warning</span></span>|  
|<span data-ttu-id="d7ee1-110">通道</span><span class="sxs-lookup"><span data-stu-id="d7ee1-110">Channel</span></span>|<span data-ttu-id="d7ee1-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="d7ee1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d7ee1-112">描述</span><span class="sxs-lookup"><span data-stu-id="d7ee1-112">Description</span></span>  
 <span data-ttu-id="d7ee1-113">指示已截断跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="d7ee1-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="d7ee1-114">已移除了变量/批注/用户数据。</span><span class="sxs-lookup"><span data-stu-id="d7ee1-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d7ee1-115">消息</span><span class="sxs-lookup"><span data-stu-id="d7ee1-115">Message</span></span>  
 <span data-ttu-id="d7ee1-116">用提供程序 %2 向 ETW 会话写入了截断的跟踪记录 %1。</span><span class="sxs-lookup"><span data-stu-id="d7ee1-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="d7ee1-117">已移除了变量/批注/用户数据</span><span class="sxs-lookup"><span data-stu-id="d7ee1-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="d7ee1-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="d7ee1-118">Details</span></span>  
  
|<span data-ttu-id="d7ee1-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d7ee1-119">Data Item Name</span></span>|<span data-ttu-id="d7ee1-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d7ee1-120">Data Item Type</span></span>|<span data-ttu-id="d7ee1-121">描述</span><span class="sxs-lookup"><span data-stu-id="d7ee1-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d7ee1-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="d7ee1-122">RecordNumber</span></span>|<span data-ttu-id="d7ee1-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="d7ee1-123">xs:string</span></span>|<span data-ttu-id="d7ee1-124">跟踪记录编号。</span><span class="sxs-lookup"><span data-stu-id="d7ee1-124">The tracking record number.</span></span>|  
|<span data-ttu-id="d7ee1-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="d7ee1-125">ProviderId</span></span>|<span data-ttu-id="d7ee1-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="d7ee1-126">xs:string</span></span>|<span data-ttu-id="d7ee1-127">ETW 提供程序 ID。</span><span class="sxs-lookup"><span data-stu-id="d7ee1-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="d7ee1-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d7ee1-128">AppDomain</span></span>|<span data-ttu-id="d7ee1-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="d7ee1-129">xs:string</span></span>|<span data-ttu-id="d7ee1-130">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d7ee1-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
