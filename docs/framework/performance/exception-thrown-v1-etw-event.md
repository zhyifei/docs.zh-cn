---
title: 异常 Thrown_V1 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 865b7b16d5807bd9161855f453128a63c84eab96
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505218"
---
# <a name="exception-thrownv1-etw-event"></a><span data-ttu-id="cfacd-102">异常 Thrown_V1 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="cfacd-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="cfacd-103">该事件捕获有关引发的异常的信息。</span><span class="sxs-lookup"><span data-stu-id="cfacd-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="cfacd-104">下表显示了引发事件的关键字以及事件的级别。</span><span class="sxs-lookup"><span data-stu-id="cfacd-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="cfacd-105">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="cfacd-105">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="cfacd-106">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="cfacd-106">Keyword for raising the event</span></span>|<span data-ttu-id="cfacd-107">级别</span><span class="sxs-lookup"><span data-stu-id="cfacd-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cfacd-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="cfacd-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="cfacd-109">警告 (2)</span><span class="sxs-lookup"><span data-stu-id="cfacd-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="cfacd-110">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="cfacd-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="cfacd-111">事件</span><span class="sxs-lookup"><span data-stu-id="cfacd-111">Event</span></span>|<span data-ttu-id="cfacd-112">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cfacd-112">Event ID</span></span>|<span data-ttu-id="cfacd-113">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="cfacd-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="cfacd-114">80</span><span class="sxs-lookup"><span data-stu-id="cfacd-114">80</span></span>|<span data-ttu-id="cfacd-115">引发托管异常。</span><span class="sxs-lookup"><span data-stu-id="cfacd-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="cfacd-116">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="cfacd-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="cfacd-117">字段名</span><span class="sxs-lookup"><span data-stu-id="cfacd-117">Field name</span></span>|<span data-ttu-id="cfacd-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="cfacd-118">Data type</span></span>|<span data-ttu-id="cfacd-119">描述</span><span class="sxs-lookup"><span data-stu-id="cfacd-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="cfacd-120">异常类型</span><span class="sxs-lookup"><span data-stu-id="cfacd-120">Exception Type</span></span>|<span data-ttu-id="cfacd-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="cfacd-121">win:UnicodeString</span></span>|<span data-ttu-id="cfacd-122">异常的类型，例如，`System.NullReferenceException`。</span><span class="sxs-lookup"><span data-stu-id="cfacd-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="cfacd-123">异常消息</span><span class="sxs-lookup"><span data-stu-id="cfacd-123">Exception Message</span></span>|<span data-ttu-id="cfacd-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="cfacd-124">win:UnicodeString</span></span>|<span data-ttu-id="cfacd-125">实际的异常消息。</span><span class="sxs-lookup"><span data-stu-id="cfacd-125">Actual exception message.</span></span>|  
|<span data-ttu-id="cfacd-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="cfacd-126">EIPCodeThrow</span></span>|<span data-ttu-id="cfacd-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="cfacd-127">win:Pointer</span></span>|<span data-ttu-id="cfacd-128">指向异常发生位置的指令指针。</span><span class="sxs-lookup"><span data-stu-id="cfacd-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="cfacd-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="cfacd-129">ExceptionHR</span></span>|<span data-ttu-id="cfacd-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cfacd-130">win:UInt32</span></span>|<span data-ttu-id="cfacd-131">异常 [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679)。</span><span class="sxs-lookup"><span data-stu-id="cfacd-131">Exception [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="cfacd-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="cfacd-132">ExceptionFlags</span></span>|<span data-ttu-id="cfacd-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cfacd-133">win:UInt16</span></span>|<span data-ttu-id="cfacd-134">0x01: HasInnerException（参阅 Visual Basic 文档中的 [CLR ETW 事件](../../../docs/framework/performance/clr-etw-events.md)）。</span><span class="sxs-lookup"><span data-stu-id="cfacd-134">0x01: HasInnerException (see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="cfacd-135">0x02: IsNestedException。</span><span class="sxs-lookup"><span data-stu-id="cfacd-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="cfacd-136">0x04: IsRethrownException。</span><span class="sxs-lookup"><span data-stu-id="cfacd-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="cfacd-137">0x08: IsCorruptedStateException（表示进程状态已损坏，请参阅 MSDN 上的[处理损坏状态异常](https://go.microsoft.com/fwlink/?LinkId=179681)）。</span><span class="sxs-lookup"><span data-stu-id="cfacd-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="cfacd-138">0x10: IsCLSCompliant（从 <xref:System.Exception> 派生的异常符合 CLS，此外的其他异常均不符合 CLS）。</span><span class="sxs-lookup"><span data-stu-id="cfacd-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="cfacd-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="cfacd-139">ClrInstanceID</span></span>|<span data-ttu-id="cfacd-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cfacd-140">win:UInt16</span></span>|<span data-ttu-id="cfacd-141">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="cfacd-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cfacd-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="cfacd-142">See Also</span></span>  
 [<span data-ttu-id="cfacd-143">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="cfacd-143">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
