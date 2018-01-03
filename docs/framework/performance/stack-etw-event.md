---
title: "堆栈 ETW 事件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1107c6608fe5136eb6159b1d4f0a438e95c4dabb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="stack-etw-event"></a><span data-ttu-id="add34-102">堆栈 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="add34-102">Stack ETW Event</span></span>
<span data-ttu-id="add34-103">堆栈事件应与其他事件结合使用，在引发事件后生成堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="add34-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="add34-104">启用运行时提供程序时，记录该事件。</span><span class="sxs-lookup"><span data-stu-id="add34-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="add34-105">这是一个发生频率非常高的事件，因为每当引发另一个运行时事件时，都将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="add34-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="add34-106">因此，我们建议谨慎使用此事件。</span><span class="sxs-lookup"><span data-stu-id="add34-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="add34-107">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="add34-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="add34-108">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="add34-108">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="add34-109">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="add34-109">Keyword for raising the event</span></span>|<span data-ttu-id="add34-110">级别</span><span class="sxs-lookup"><span data-stu-id="add34-110">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="add34-111">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="add34-111">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="add34-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="add34-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="add34-113">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="add34-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="add34-114">Event</span><span class="sxs-lookup"><span data-stu-id="add34-114">Event</span></span>|<span data-ttu-id="add34-115">事件 ID</span><span class="sxs-lookup"><span data-stu-id="add34-115">Event ID</span></span>|<span data-ttu-id="add34-116">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="add34-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="add34-117">82</span><span class="sxs-lookup"><span data-stu-id="add34-117">82</span></span>|<span data-ttu-id="add34-118">与其他事件结合使用，在事件发生后生成堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="add34-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="add34-119">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="add34-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="add34-120">字段名</span><span class="sxs-lookup"><span data-stu-id="add34-120">Field name</span></span>|<span data-ttu-id="add34-121">数据类型</span><span class="sxs-lookup"><span data-stu-id="add34-121">Data Type</span></span>|<span data-ttu-id="add34-122">描述</span><span class="sxs-lookup"><span data-stu-id="add34-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="add34-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="add34-123">ClrInstanceID</span></span>|<span data-ttu-id="add34-124">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="add34-124">win:Uint16</span></span>|<span data-ttu-id="add34-125">唯一运行时标识符。</span><span class="sxs-lookup"><span data-stu-id="add34-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="add34-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="add34-126">Reserved1</span></span>|<span data-ttu-id="add34-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="add34-127">win:UInt8</span></span>|<span data-ttu-id="add34-128">保留。</span><span class="sxs-lookup"><span data-stu-id="add34-128">Reserved.</span></span>|  
|<span data-ttu-id="add34-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="add34-129">Reserved2</span></span>|<span data-ttu-id="add34-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="add34-130">win:UInt8</span></span>|<span data-ttu-id="add34-131">保留。</span><span class="sxs-lookup"><span data-stu-id="add34-131">Reserved.</span></span>|  
|<span data-ttu-id="add34-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="add34-132">FrameCount</span></span>|<span data-ttu-id="add34-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="add34-133">win:UInt32</span></span>|<span data-ttu-id="add34-134">堆栈跟踪中的帧数。</span><span class="sxs-lookup"><span data-stu-id="add34-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="add34-135">堆栈</span><span class="sxs-lookup"><span data-stu-id="add34-135">Stack</span></span>|<span data-ttu-id="add34-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="add34-136">win:Pointer</span></span>|<span data-ttu-id="add34-137">指令指针的列</span><span class="sxs-lookup"><span data-stu-id="add34-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="add34-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="add34-138">See Also</span></span>  
 [<span data-ttu-id="add34-139">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="add34-139">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
