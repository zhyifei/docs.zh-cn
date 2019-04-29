---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: 416feb4073b31178b016ae72c9cd85e15c4a68c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774408"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="7cf06-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="7cf06-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="7cf06-103">属性</span><span class="sxs-lookup"><span data-stu-id="7cf06-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7cf06-104">Id</span><span class="sxs-lookup"><span data-stu-id="7cf06-104">ID</span></span>|<span data-ttu-id="7cf06-105">39458</span><span class="sxs-lookup"><span data-stu-id="7cf06-105">39458</span></span>|  
|<span data-ttu-id="7cf06-106">关键字</span><span class="sxs-lookup"><span data-stu-id="7cf06-106">Keywords</span></span>|<span data-ttu-id="7cf06-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="7cf06-107">WFTracking</span></span>|  
|<span data-ttu-id="7cf06-108">级别</span><span class="sxs-lookup"><span data-stu-id="7cf06-108">Level</span></span>|<span data-ttu-id="7cf06-109">警告</span><span class="sxs-lookup"><span data-stu-id="7cf06-109">Warning</span></span>|  
|<span data-ttu-id="7cf06-110">通道</span><span class="sxs-lookup"><span data-stu-id="7cf06-110">Channel</span></span>|<span data-ttu-id="7cf06-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="7cf06-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7cf06-112">描述</span><span class="sxs-lookup"><span data-stu-id="7cf06-112">Description</span></span>  
 <span data-ttu-id="7cf06-113">指示已截断跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="7cf06-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="7cf06-114">已移除了变量/批注/用户数据。</span><span class="sxs-lookup"><span data-stu-id="7cf06-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7cf06-115">消息</span><span class="sxs-lookup"><span data-stu-id="7cf06-115">Message</span></span>  
 <span data-ttu-id="7cf06-116">用提供程序 %2 向 ETW 会话写入了截断的跟踪记录 %1。</span><span class="sxs-lookup"><span data-stu-id="7cf06-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="7cf06-117">已移除了变量/批注/用户数据</span><span class="sxs-lookup"><span data-stu-id="7cf06-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="7cf06-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="7cf06-118">Details</span></span>  
  
|<span data-ttu-id="7cf06-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="7cf06-119">Data Item Name</span></span>|<span data-ttu-id="7cf06-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="7cf06-120">Data Item Type</span></span>|<span data-ttu-id="7cf06-121">描述</span><span class="sxs-lookup"><span data-stu-id="7cf06-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7cf06-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="7cf06-122">RecordNumber</span></span>|<span data-ttu-id="7cf06-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="7cf06-123">xs:string</span></span>|<span data-ttu-id="7cf06-124">跟踪记录编号。</span><span class="sxs-lookup"><span data-stu-id="7cf06-124">The tracking record number.</span></span>|  
|<span data-ttu-id="7cf06-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="7cf06-125">ProviderId</span></span>|<span data-ttu-id="7cf06-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="7cf06-126">xs:string</span></span>|<span data-ttu-id="7cf06-127">ETW 提供程序 ID。</span><span class="sxs-lookup"><span data-stu-id="7cf06-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="7cf06-128">应用程序域</span><span class="sxs-lookup"><span data-stu-id="7cf06-128">AppDomain</span></span>|<span data-ttu-id="7cf06-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="7cf06-129">xs:string</span></span>|<span data-ttu-id="7cf06-130">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="7cf06-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
