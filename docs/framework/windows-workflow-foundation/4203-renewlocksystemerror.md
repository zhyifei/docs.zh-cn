---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 984f7ddae8797cba17753a618d0820d21bde5eef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="d2edf-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="d2edf-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="d2edf-103">属性</span><span class="sxs-lookup"><span data-stu-id="d2edf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2edf-104">ID</span><span class="sxs-lookup"><span data-stu-id="d2edf-104">ID</span></span>|<span data-ttu-id="d2edf-105">4203</span><span class="sxs-lookup"><span data-stu-id="d2edf-105">4203</span></span>|  
|<span data-ttu-id="d2edf-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d2edf-106">Keywords</span></span>|<span data-ttu-id="d2edf-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="d2edf-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="d2edf-108">级别</span><span class="sxs-lookup"><span data-stu-id="d2edf-108">Level</span></span>|<span data-ttu-id="d2edf-109">错误</span><span class="sxs-lookup"><span data-stu-id="d2edf-109">Error</span></span>|  
|<span data-ttu-id="d2edf-110">通道</span><span class="sxs-lookup"><span data-stu-id="d2edf-110">Channel</span></span>|<span data-ttu-id="d2edf-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="d2edf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d2edf-112">描述</span><span class="sxs-lookup"><span data-stu-id="d2edf-112">Description</span></span>  
 <span data-ttu-id="d2edf-113">指示 SQL 提供程序由于锁定到期日已过或者已删除锁定所有者，未能延长锁定到期日。</span><span class="sxs-lookup"><span data-stu-id="d2edf-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="d2edf-114">SqlWorkflowInstanceStore 将被中止。</span><span class="sxs-lookup"><span data-stu-id="d2edf-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d2edf-115">消息</span><span class="sxs-lookup"><span data-stu-id="d2edf-115">Message</span></span>  
 <span data-ttu-id="d2edf-116">未能延长锁定到期日，锁定到期日已过，或者已删除锁定所有者。</span><span class="sxs-lookup"><span data-stu-id="d2edf-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="d2edf-117">正在中止 SqlWorkflowInstanceStore。</span><span class="sxs-lookup"><span data-stu-id="d2edf-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d2edf-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="d2edf-118">Details</span></span>  
  
|<span data-ttu-id="d2edf-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d2edf-119">Data Item Name</span></span>|<span data-ttu-id="d2edf-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d2edf-120">Data Item Type</span></span>|<span data-ttu-id="d2edf-121">描述</span><span class="sxs-lookup"><span data-stu-id="d2edf-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d2edf-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d2edf-122">AppDomain</span></span>|<span data-ttu-id="d2edf-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="d2edf-123">xs:string</span></span>|<span data-ttu-id="d2edf-124">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d2edf-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
