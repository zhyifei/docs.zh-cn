---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 9b7a463851d380eba1ef7b28fbc6decd0cfc979c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774213"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="c8a88-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="c8a88-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="c8a88-103">属性</span><span class="sxs-lookup"><span data-stu-id="c8a88-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c8a88-104">Id</span><span class="sxs-lookup"><span data-stu-id="c8a88-104">ID</span></span>|<span data-ttu-id="c8a88-105">4212</span><span class="sxs-lookup"><span data-stu-id="c8a88-105">4212</span></span>|  
|<span data-ttu-id="c8a88-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c8a88-106">Keywords</span></span>|<span data-ttu-id="c8a88-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="c8a88-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="c8a88-108">级别</span><span class="sxs-lookup"><span data-stu-id="c8a88-108">Level</span></span>|<span data-ttu-id="c8a88-109">警告</span><span class="sxs-lookup"><span data-stu-id="c8a88-109">Warning</span></span>|  
|<span data-ttu-id="c8a88-110">通道</span><span class="sxs-lookup"><span data-stu-id="c8a88-110">Channel</span></span>|<span data-ttu-id="c8a88-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c8a88-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c8a88-112">描述</span><span class="sxs-lookup"><span data-stu-id="c8a88-112">Description</span></span>  
 <span data-ttu-id="c8a88-113">尝试获取实例锁时 SQL 提供程序遇到了超时。</span><span class="sxs-lookup"><span data-stu-id="c8a88-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c8a88-114">消息</span><span class="sxs-lookup"><span data-stu-id="c8a88-114">Message</span></span>  
 <span data-ttu-id="c8a88-115">尝试获取实例锁超时。</span><span class="sxs-lookup"><span data-stu-id="c8a88-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="c8a88-116">操作在分配的超时 %1 内没有完成。</span><span class="sxs-lookup"><span data-stu-id="c8a88-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="c8a88-117">分配给此操作的时间可能是更长超时的一部分。</span><span class="sxs-lookup"><span data-stu-id="c8a88-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c8a88-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="c8a88-118">Details</span></span>  
  
|<span data-ttu-id="c8a88-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="c8a88-119">Data Item Name</span></span>|<span data-ttu-id="c8a88-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="c8a88-120">Data Item Type</span></span>|<span data-ttu-id="c8a88-121">描述</span><span class="sxs-lookup"><span data-stu-id="c8a88-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c8a88-122">延迟</span><span class="sxs-lookup"><span data-stu-id="c8a88-122">Delay</span></span>|<span data-ttu-id="c8a88-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="c8a88-123">xs:string</span></span>|<span data-ttu-id="c8a88-124">两次重试之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="c8a88-124">The delay between retries.</span></span>|  
|<span data-ttu-id="c8a88-125">应用程序域</span><span class="sxs-lookup"><span data-stu-id="c8a88-125">AppDomain</span></span>|<span data-ttu-id="c8a88-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="c8a88-126">xs:string</span></span>|<span data-ttu-id="c8a88-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="c8a88-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
