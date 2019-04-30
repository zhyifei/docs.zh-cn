---
title: 堆栈 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7cba2bd1dd5b83e29c7a6c192a1a7e5e2d33ecc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949144"
---
# <a name="stack-etw-event"></a><span data-ttu-id="acebf-102">堆栈 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="acebf-102">Stack ETW Event</span></span>
<span data-ttu-id="acebf-103">堆栈事件应与其他事件结合使用，在引发事件后生成堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="acebf-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="acebf-104">启用运行时提供程序时，记录该事件。</span><span class="sxs-lookup"><span data-stu-id="acebf-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="acebf-105">这是一个发生频率非常高的事件，因为每当引发另一个运行时事件时，都将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="acebf-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="acebf-106">因此，我们建议谨慎使用此事件。</span><span class="sxs-lookup"><span data-stu-id="acebf-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="acebf-107">下表显示了关键字和级别。</span><span class="sxs-lookup"><span data-stu-id="acebf-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="acebf-108">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="acebf-108">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="acebf-109">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="acebf-109">Keyword for raising the event</span></span>|<span data-ttu-id="acebf-110">级别</span><span class="sxs-lookup"><span data-stu-id="acebf-110">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="acebf-111">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="acebf-111">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="acebf-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="acebf-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="acebf-113">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="acebf-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="acebf-114">Event</span><span class="sxs-lookup"><span data-stu-id="acebf-114">Event</span></span>|<span data-ttu-id="acebf-115">事件 ID</span><span class="sxs-lookup"><span data-stu-id="acebf-115">Event ID</span></span>|<span data-ttu-id="acebf-116">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="acebf-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="acebf-117">82</span><span class="sxs-lookup"><span data-stu-id="acebf-117">82</span></span>|<span data-ttu-id="acebf-118">与其他事件结合使用，在事件发生后生成堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="acebf-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="acebf-119">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="acebf-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="acebf-120">字段名</span><span class="sxs-lookup"><span data-stu-id="acebf-120">Field name</span></span>|<span data-ttu-id="acebf-121">数据类型</span><span class="sxs-lookup"><span data-stu-id="acebf-121">Data Type</span></span>|<span data-ttu-id="acebf-122">描述</span><span class="sxs-lookup"><span data-stu-id="acebf-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="acebf-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="acebf-123">ClrInstanceID</span></span>|<span data-ttu-id="acebf-124">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="acebf-124">win:Uint16</span></span>|<span data-ttu-id="acebf-125">唯一运行时标识符。</span><span class="sxs-lookup"><span data-stu-id="acebf-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="acebf-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="acebf-126">Reserved1</span></span>|<span data-ttu-id="acebf-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="acebf-127">win:UInt8</span></span>|<span data-ttu-id="acebf-128">保留。</span><span class="sxs-lookup"><span data-stu-id="acebf-128">Reserved.</span></span>|  
|<span data-ttu-id="acebf-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="acebf-129">Reserved2</span></span>|<span data-ttu-id="acebf-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="acebf-130">win:UInt8</span></span>|<span data-ttu-id="acebf-131">保留。</span><span class="sxs-lookup"><span data-stu-id="acebf-131">Reserved.</span></span>|  
|<span data-ttu-id="acebf-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="acebf-132">FrameCount</span></span>|<span data-ttu-id="acebf-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="acebf-133">win:UInt32</span></span>|<span data-ttu-id="acebf-134">堆栈跟踪中的帧数。</span><span class="sxs-lookup"><span data-stu-id="acebf-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="acebf-135">堆栈</span><span class="sxs-lookup"><span data-stu-id="acebf-135">Stack</span></span>|<span data-ttu-id="acebf-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="acebf-136">win:Pointer</span></span>|<span data-ttu-id="acebf-137">指令指针的列</span><span class="sxs-lookup"><span data-stu-id="acebf-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="acebf-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="acebf-138">See also</span></span>

- [<span data-ttu-id="acebf-139">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="acebf-139">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
