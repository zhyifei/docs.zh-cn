---
title: 4203 - RenewLockSystemError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 06d4695eb125475f41a94c7f2266df6d2c3f400d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="89619-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="89619-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="89619-103">属性</span><span class="sxs-lookup"><span data-stu-id="89619-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="89619-104">ID</span><span class="sxs-lookup"><span data-stu-id="89619-104">ID</span></span>|<span data-ttu-id="89619-105">4203</span><span class="sxs-lookup"><span data-stu-id="89619-105">4203</span></span>|  
|<span data-ttu-id="89619-106">关键字</span><span class="sxs-lookup"><span data-stu-id="89619-106">Keywords</span></span>|<span data-ttu-id="89619-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="89619-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="89619-108">级别</span><span class="sxs-lookup"><span data-stu-id="89619-108">Level</span></span>|<span data-ttu-id="89619-109">错误</span><span class="sxs-lookup"><span data-stu-id="89619-109">Error</span></span>|  
|<span data-ttu-id="89619-110">通道</span><span class="sxs-lookup"><span data-stu-id="89619-110">Channel</span></span>|<span data-ttu-id="89619-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="89619-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="89619-112">描述</span><span class="sxs-lookup"><span data-stu-id="89619-112">Description</span></span>  
 <span data-ttu-id="89619-113">指示 SQL 提供程序由于锁定到期日已过或者已删除锁定所有者，未能延长锁定到期日。</span><span class="sxs-lookup"><span data-stu-id="89619-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="89619-114">SqlWorkflowInstanceStore 将被中止。</span><span class="sxs-lookup"><span data-stu-id="89619-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="89619-115">消息</span><span class="sxs-lookup"><span data-stu-id="89619-115">Message</span></span>  
 <span data-ttu-id="89619-116">未能延长锁定到期日，锁定到期日已过，或者已删除锁定所有者。</span><span class="sxs-lookup"><span data-stu-id="89619-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="89619-117">正在中止 SqlWorkflowInstanceStore。</span><span class="sxs-lookup"><span data-stu-id="89619-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="89619-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="89619-118">Details</span></span>  
  
|<span data-ttu-id="89619-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="89619-119">Data Item Name</span></span>|<span data-ttu-id="89619-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="89619-120">Data Item Type</span></span>|<span data-ttu-id="89619-121">描述</span><span class="sxs-lookup"><span data-stu-id="89619-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="89619-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="89619-122">AppDomain</span></span>|<span data-ttu-id="89619-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="89619-123">xs:string</span></span>|<span data-ttu-id="89619-124">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="89619-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
