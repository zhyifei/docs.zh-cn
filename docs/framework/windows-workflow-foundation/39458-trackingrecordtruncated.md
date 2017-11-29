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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ecf18d6d751edd47dbeca7d2e5f4491892e41e6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="1f8a0-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="1f8a0-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="1f8a0-103">属性</span><span class="sxs-lookup"><span data-stu-id="1f8a0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1f8a0-104">ID</span><span class="sxs-lookup"><span data-stu-id="1f8a0-104">ID</span></span>|<span data-ttu-id="1f8a0-105">39458</span><span class="sxs-lookup"><span data-stu-id="1f8a0-105">39458</span></span>|  
|<span data-ttu-id="1f8a0-106">关键字</span><span class="sxs-lookup"><span data-stu-id="1f8a0-106">Keywords</span></span>|<span data-ttu-id="1f8a0-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="1f8a0-107">WFTracking</span></span>|  
|<span data-ttu-id="1f8a0-108">级别</span><span class="sxs-lookup"><span data-stu-id="1f8a0-108">Level</span></span>|<span data-ttu-id="1f8a0-109">警告</span><span class="sxs-lookup"><span data-stu-id="1f8a0-109">Warning</span></span>|  
|<span data-ttu-id="1f8a0-110">通道</span><span class="sxs-lookup"><span data-stu-id="1f8a0-110">Channel</span></span>|<span data-ttu-id="1f8a0-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="1f8a0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1f8a0-112">描述</span><span class="sxs-lookup"><span data-stu-id="1f8a0-112">Description</span></span>  
 <span data-ttu-id="1f8a0-113">指示已截断跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="1f8a0-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="1f8a0-114">已移除了变量/批注/用户数据。</span><span class="sxs-lookup"><span data-stu-id="1f8a0-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1f8a0-115">消息</span><span class="sxs-lookup"><span data-stu-id="1f8a0-115">Message</span></span>  
 <span data-ttu-id="1f8a0-116">用提供程序 %2 向 ETW 会话写入了截断的跟踪记录 %1。</span><span class="sxs-lookup"><span data-stu-id="1f8a0-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="1f8a0-117">已移除了变量/批注/用户数据</span><span class="sxs-lookup"><span data-stu-id="1f8a0-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="1f8a0-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="1f8a0-118">Details</span></span>  
  
|<span data-ttu-id="1f8a0-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="1f8a0-119">Data Item Name</span></span>|<span data-ttu-id="1f8a0-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="1f8a0-120">Data Item Type</span></span>|<span data-ttu-id="1f8a0-121">描述</span><span class="sxs-lookup"><span data-stu-id="1f8a0-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1f8a0-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="1f8a0-122">RecordNumber</span></span>|<span data-ttu-id="1f8a0-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="1f8a0-123">xs:string</span></span>|<span data-ttu-id="1f8a0-124">跟踪记录编号。</span><span class="sxs-lookup"><span data-stu-id="1f8a0-124">The tracking record number.</span></span>|  
|<span data-ttu-id="1f8a0-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="1f8a0-125">ProviderId</span></span>|<span data-ttu-id="1f8a0-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="1f8a0-126">xs:string</span></span>|<span data-ttu-id="1f8a0-127">ETW 提供程序 ID。</span><span class="sxs-lookup"><span data-stu-id="1f8a0-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="1f8a0-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1f8a0-128">AppDomain</span></span>|<span data-ttu-id="1f8a0-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="1f8a0-129">xs:string</span></span>|<span data-ttu-id="1f8a0-130">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="1f8a0-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
