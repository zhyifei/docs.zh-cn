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
ms.workload: dotnet
ms.openlocfilehash: 4d12549d201ac621361bd6a517df6c6b53ab7aec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="283b5-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="283b5-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="283b5-103">属性</span><span class="sxs-lookup"><span data-stu-id="283b5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="283b5-104">ID</span><span class="sxs-lookup"><span data-stu-id="283b5-104">ID</span></span>|<span data-ttu-id="283b5-105">39458</span><span class="sxs-lookup"><span data-stu-id="283b5-105">39458</span></span>|  
|<span data-ttu-id="283b5-106">关键字</span><span class="sxs-lookup"><span data-stu-id="283b5-106">Keywords</span></span>|<span data-ttu-id="283b5-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="283b5-107">WFTracking</span></span>|  
|<span data-ttu-id="283b5-108">级别</span><span class="sxs-lookup"><span data-stu-id="283b5-108">Level</span></span>|<span data-ttu-id="283b5-109">警告</span><span class="sxs-lookup"><span data-stu-id="283b5-109">Warning</span></span>|  
|<span data-ttu-id="283b5-110">通道</span><span class="sxs-lookup"><span data-stu-id="283b5-110">Channel</span></span>|<span data-ttu-id="283b5-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="283b5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="283b5-112">描述</span><span class="sxs-lookup"><span data-stu-id="283b5-112">Description</span></span>  
 <span data-ttu-id="283b5-113">指示已截断跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="283b5-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="283b5-114">已移除了变量/批注/用户数据。</span><span class="sxs-lookup"><span data-stu-id="283b5-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="283b5-115">消息</span><span class="sxs-lookup"><span data-stu-id="283b5-115">Message</span></span>  
 <span data-ttu-id="283b5-116">用提供程序 %2 向 ETW 会话写入了截断的跟踪记录 %1。</span><span class="sxs-lookup"><span data-stu-id="283b5-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="283b5-117">已移除了变量/批注/用户数据</span><span class="sxs-lookup"><span data-stu-id="283b5-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="283b5-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="283b5-118">Details</span></span>  
  
|<span data-ttu-id="283b5-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="283b5-119">Data Item Name</span></span>|<span data-ttu-id="283b5-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="283b5-120">Data Item Type</span></span>|<span data-ttu-id="283b5-121">描述</span><span class="sxs-lookup"><span data-stu-id="283b5-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="283b5-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="283b5-122">RecordNumber</span></span>|<span data-ttu-id="283b5-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="283b5-123">xs:string</span></span>|<span data-ttu-id="283b5-124">跟踪记录编号。</span><span class="sxs-lookup"><span data-stu-id="283b5-124">The tracking record number.</span></span>|  
|<span data-ttu-id="283b5-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="283b5-125">ProviderId</span></span>|<span data-ttu-id="283b5-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="283b5-126">xs:string</span></span>|<span data-ttu-id="283b5-127">ETW 提供程序 ID。</span><span class="sxs-lookup"><span data-stu-id="283b5-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="283b5-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="283b5-128">AppDomain</span></span>|<span data-ttu-id="283b5-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="283b5-129">xs:string</span></span>|<span data-ttu-id="283b5-130">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="283b5-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
