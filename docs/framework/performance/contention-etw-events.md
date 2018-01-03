---
title: "争用 ETW 事件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a09419c208d4ac754eb48da0c8d1b5d93386eb3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="contention-etw-events"></a><span data-ttu-id="773d4-102">争用 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="773d4-102">Contention ETW Events</span></span>
<span data-ttu-id="773d4-103">只要运行时使用的 <xref:System.Threading.Monitor?displayProperty=nameWithType> 锁或本机锁出现争用情况，就会引发争用事件。</span><span class="sxs-lookup"><span data-stu-id="773d4-103">Contention events are raised whenever there is contention for <xref:System.Threading.Monitor?displayProperty=nameWithType> locks or native locks used by the runtime.</span></span> <span data-ttu-id="773d4-104">一个线程等待的锁被另一线程占有时将发生争用。</span><span class="sxs-lookup"><span data-stu-id="773d4-104">Contention occurs when a thread is waiting for a lock while another thread possesses the lock.</span></span>  
  
 <span data-ttu-id="773d4-105">下表显示了引发争用事件的关键字以及事件的级别。</span><span class="sxs-lookup"><span data-stu-id="773d4-105">The following table shows the keyword under which contention events are raised, and the level of the events.</span></span> <span data-ttu-id="773d4-106">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="773d4-106">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="773d4-107">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="773d4-107">Keyword for raising the event</span></span>|<span data-ttu-id="773d4-108">级别</span><span class="sxs-lookup"><span data-stu-id="773d4-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="773d4-109">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="773d4-109">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="773d4-110">信息性 (4)</span><span class="sxs-lookup"><span data-stu-id="773d4-110">Informational (4)</span></span>|  
  
 <span data-ttu-id="773d4-111">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="773d4-111">The following table shows event information.</span></span>  
  
|<span data-ttu-id="773d4-112">Event</span><span class="sxs-lookup"><span data-stu-id="773d4-112">Event</span></span>|<span data-ttu-id="773d4-113">事件 ID</span><span class="sxs-lookup"><span data-stu-id="773d4-113">Event ID</span></span>|<span data-ttu-id="773d4-114">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="773d4-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ContentionStart_V1`|<span data-ttu-id="773d4-115">81</span><span class="sxs-lookup"><span data-stu-id="773d4-115">81</span></span>|<span data-ttu-id="773d4-116">争用开始。</span><span class="sxs-lookup"><span data-stu-id="773d4-116">Contention starts.</span></span> <span data-ttu-id="773d4-117">此事件不包括线程等待获取锁之前的旋转时间；仅在线程等待获取锁时引发此事件。</span><span class="sxs-lookup"><span data-stu-id="773d4-117">This event does not include the amount of spinning time before a thread waits to acquire a lock; it is raised only when the thread waits to acquire a lock.</span></span>|  
|`ContentionStop`|<span data-ttu-id="773d4-118">81</span><span class="sxs-lookup"><span data-stu-id="773d4-118">81</span></span>|<span data-ttu-id="773d4-119">争用结束。</span><span class="sxs-lookup"><span data-stu-id="773d4-119">Contention ends.</span></span>|  
  
 <span data-ttu-id="773d4-120">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="773d4-120">The following table shows event data.</span></span>  
  
|<span data-ttu-id="773d4-121">字段名</span><span class="sxs-lookup"><span data-stu-id="773d4-121">Field name</span></span>|<span data-ttu-id="773d4-122">数据类型</span><span class="sxs-lookup"><span data-stu-id="773d4-122">Data type</span></span>|<span data-ttu-id="773d4-123">描述</span><span class="sxs-lookup"><span data-stu-id="773d4-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="773d4-124">Flags</span><span class="sxs-lookup"><span data-stu-id="773d4-124">Flags</span></span>|<span data-ttu-id="773d4-125">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="773d4-125">win:UInt8</span></span>|<span data-ttu-id="773d4-126">0 表示托管；1 表示本机。</span><span class="sxs-lookup"><span data-stu-id="773d4-126">0 for managed; 1 for native.</span></span>|  
|<span data-ttu-id="773d4-127">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="773d4-127">ClrInstanceID</span></span>|<span data-ttu-id="773d4-128">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="773d4-128">win:UInt16</span></span>|<span data-ttu-id="773d4-129">CLR 实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="773d4-129">Unique ID for the instance of CLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="773d4-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="773d4-130">See Also</span></span>  
 [<span data-ttu-id="773d4-131">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="773d4-131">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
