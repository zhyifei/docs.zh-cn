---
title: 4212 - LockRetryTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abe1f560cc984551f069a75873a7e5545aec03cf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="249ca-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="249ca-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="249ca-103">属性</span><span class="sxs-lookup"><span data-stu-id="249ca-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="249ca-104">ID</span><span class="sxs-lookup"><span data-stu-id="249ca-104">ID</span></span>|<span data-ttu-id="249ca-105">4212</span><span class="sxs-lookup"><span data-stu-id="249ca-105">4212</span></span>|  
|<span data-ttu-id="249ca-106">关键字</span><span class="sxs-lookup"><span data-stu-id="249ca-106">Keywords</span></span>|<span data-ttu-id="249ca-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="249ca-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="249ca-108">级别</span><span class="sxs-lookup"><span data-stu-id="249ca-108">Level</span></span>|<span data-ttu-id="249ca-109">警告</span><span class="sxs-lookup"><span data-stu-id="249ca-109">Warning</span></span>|  
|<span data-ttu-id="249ca-110">通道</span><span class="sxs-lookup"><span data-stu-id="249ca-110">Channel</span></span>|<span data-ttu-id="249ca-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="249ca-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="249ca-112">描述</span><span class="sxs-lookup"><span data-stu-id="249ca-112">Description</span></span>  
 <span data-ttu-id="249ca-113">尝试获取实例锁时 SQL 提供程序遇到了超时。</span><span class="sxs-lookup"><span data-stu-id="249ca-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="249ca-114">消息</span><span class="sxs-lookup"><span data-stu-id="249ca-114">Message</span></span>  
 <span data-ttu-id="249ca-115">尝试获取实例锁超时。</span><span class="sxs-lookup"><span data-stu-id="249ca-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="249ca-116">操作在分配的超时 %1 内没有完成。</span><span class="sxs-lookup"><span data-stu-id="249ca-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="249ca-117">分配给此操作的时间可能是更长超时的一部分。</span><span class="sxs-lookup"><span data-stu-id="249ca-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="249ca-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="249ca-118">Details</span></span>  
  
|<span data-ttu-id="249ca-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="249ca-119">Data Item Name</span></span>|<span data-ttu-id="249ca-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="249ca-120">Data Item Type</span></span>|<span data-ttu-id="249ca-121">描述</span><span class="sxs-lookup"><span data-stu-id="249ca-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="249ca-122">Delay</span><span class="sxs-lookup"><span data-stu-id="249ca-122">Delay</span></span>|<span data-ttu-id="249ca-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="249ca-123">xs:string</span></span>|<span data-ttu-id="249ca-124">两次重试之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="249ca-124">The delay between retries.</span></span>|  
|<span data-ttu-id="249ca-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="249ca-125">AppDomain</span></span>|<span data-ttu-id="249ca-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="249ca-126">xs:string</span></span>|<span data-ttu-id="249ca-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="249ca-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
