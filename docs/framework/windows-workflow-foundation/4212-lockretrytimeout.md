---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 9b7a463851d380eba1ef7b28fbc6decd0cfc979c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511262"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="3ef2a-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="3ef2a-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="3ef2a-103">属性</span><span class="sxs-lookup"><span data-stu-id="3ef2a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ef2a-104">ID</span><span class="sxs-lookup"><span data-stu-id="3ef2a-104">ID</span></span>|<span data-ttu-id="3ef2a-105">4212</span><span class="sxs-lookup"><span data-stu-id="3ef2a-105">4212</span></span>|  
|<span data-ttu-id="3ef2a-106">关键字</span><span class="sxs-lookup"><span data-stu-id="3ef2a-106">Keywords</span></span>|<span data-ttu-id="3ef2a-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="3ef2a-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="3ef2a-108">级别</span><span class="sxs-lookup"><span data-stu-id="3ef2a-108">Level</span></span>|<span data-ttu-id="3ef2a-109">警告</span><span class="sxs-lookup"><span data-stu-id="3ef2a-109">Warning</span></span>|  
|<span data-ttu-id="3ef2a-110">通道</span><span class="sxs-lookup"><span data-stu-id="3ef2a-110">Channel</span></span>|<span data-ttu-id="3ef2a-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="3ef2a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3ef2a-112">描述</span><span class="sxs-lookup"><span data-stu-id="3ef2a-112">Description</span></span>  
 <span data-ttu-id="3ef2a-113">尝试获取实例锁时 SQL 提供程序遇到了超时。</span><span class="sxs-lookup"><span data-stu-id="3ef2a-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3ef2a-114">消息</span><span class="sxs-lookup"><span data-stu-id="3ef2a-114">Message</span></span>  
 <span data-ttu-id="3ef2a-115">尝试获取实例锁超时。</span><span class="sxs-lookup"><span data-stu-id="3ef2a-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="3ef2a-116">操作在分配的超时 %1 内没有完成。</span><span class="sxs-lookup"><span data-stu-id="3ef2a-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="3ef2a-117">分配给此操作的时间可能是更长超时的一部分。</span><span class="sxs-lookup"><span data-stu-id="3ef2a-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3ef2a-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="3ef2a-118">Details</span></span>  
  
|<span data-ttu-id="3ef2a-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="3ef2a-119">Data Item Name</span></span>|<span data-ttu-id="3ef2a-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="3ef2a-120">Data Item Type</span></span>|<span data-ttu-id="3ef2a-121">描述</span><span class="sxs-lookup"><span data-stu-id="3ef2a-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3ef2a-122">Delay</span><span class="sxs-lookup"><span data-stu-id="3ef2a-122">Delay</span></span>|<span data-ttu-id="3ef2a-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ef2a-123">xs:string</span></span>|<span data-ttu-id="3ef2a-124">两次重试之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="3ef2a-124">The delay between retries.</span></span>|  
|<span data-ttu-id="3ef2a-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3ef2a-125">AppDomain</span></span>|<span data-ttu-id="3ef2a-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ef2a-126">xs:string</span></span>|<span data-ttu-id="3ef2a-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="3ef2a-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
