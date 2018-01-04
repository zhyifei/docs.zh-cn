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
ms.workload: dotnet
ms.openlocfilehash: f47b383547da5145c5307670fee2eda10fcab402
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="85e3f-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="85e3f-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="85e3f-103">属性</span><span class="sxs-lookup"><span data-stu-id="85e3f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85e3f-104">ID</span><span class="sxs-lookup"><span data-stu-id="85e3f-104">ID</span></span>|<span data-ttu-id="85e3f-105">4212</span><span class="sxs-lookup"><span data-stu-id="85e3f-105">4212</span></span>|  
|<span data-ttu-id="85e3f-106">关键字</span><span class="sxs-lookup"><span data-stu-id="85e3f-106">Keywords</span></span>|<span data-ttu-id="85e3f-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="85e3f-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="85e3f-108">级别</span><span class="sxs-lookup"><span data-stu-id="85e3f-108">Level</span></span>|<span data-ttu-id="85e3f-109">警告</span><span class="sxs-lookup"><span data-stu-id="85e3f-109">Warning</span></span>|  
|<span data-ttu-id="85e3f-110">通道</span><span class="sxs-lookup"><span data-stu-id="85e3f-110">Channel</span></span>|<span data-ttu-id="85e3f-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="85e3f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="85e3f-112">描述</span><span class="sxs-lookup"><span data-stu-id="85e3f-112">Description</span></span>  
 <span data-ttu-id="85e3f-113">尝试获取实例锁时 SQL 提供程序遇到了超时。</span><span class="sxs-lookup"><span data-stu-id="85e3f-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="85e3f-114">消息</span><span class="sxs-lookup"><span data-stu-id="85e3f-114">Message</span></span>  
 <span data-ttu-id="85e3f-115">尝试获取实例锁超时。</span><span class="sxs-lookup"><span data-stu-id="85e3f-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="85e3f-116">操作在分配的超时 %1 内没有完成。</span><span class="sxs-lookup"><span data-stu-id="85e3f-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="85e3f-117">分配给此操作的时间可能是更长超时的一部分。</span><span class="sxs-lookup"><span data-stu-id="85e3f-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="85e3f-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="85e3f-118">Details</span></span>  
  
|<span data-ttu-id="85e3f-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="85e3f-119">Data Item Name</span></span>|<span data-ttu-id="85e3f-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="85e3f-120">Data Item Type</span></span>|<span data-ttu-id="85e3f-121">描述</span><span class="sxs-lookup"><span data-stu-id="85e3f-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="85e3f-122">Delay</span><span class="sxs-lookup"><span data-stu-id="85e3f-122">Delay</span></span>|<span data-ttu-id="85e3f-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="85e3f-123">xs:string</span></span>|<span data-ttu-id="85e3f-124">两次重试之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="85e3f-124">The delay between retries.</span></span>|  
|<span data-ttu-id="85e3f-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="85e3f-125">AppDomain</span></span>|<span data-ttu-id="85e3f-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="85e3f-126">xs:string</span></span>|<span data-ttu-id="85e3f-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="85e3f-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
