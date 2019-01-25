---
title: 异常 Thrown_V1 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 07932a12916138dd7cbee2576e4fc747898b8063
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610830"
---
# <a name="exception-thrownv1-etw-event"></a><span data-ttu-id="9c4d8-102">异常 Thrown_V1 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="9c4d8-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="9c4d8-103">该事件捕获有关引发的异常的信息。</span><span class="sxs-lookup"><span data-stu-id="9c4d8-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="9c4d8-104">下表显示了引发事件的关键字以及事件的级别。</span><span class="sxs-lookup"><span data-stu-id="9c4d8-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="9c4d8-105">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="9c4d8-105">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="9c4d8-106">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="9c4d8-106">Keyword for raising the event</span></span>|<span data-ttu-id="9c4d8-107">级别</span><span class="sxs-lookup"><span data-stu-id="9c4d8-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="9c4d8-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="9c4d8-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="9c4d8-109">警告 (2)</span><span class="sxs-lookup"><span data-stu-id="9c4d8-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="9c4d8-110">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="9c4d8-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="9c4d8-111">事件</span><span class="sxs-lookup"><span data-stu-id="9c4d8-111">Event</span></span>|<span data-ttu-id="9c4d8-112">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9c4d8-112">Event ID</span></span>|<span data-ttu-id="9c4d8-113">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="9c4d8-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="9c4d8-114">80</span><span class="sxs-lookup"><span data-stu-id="9c4d8-114">80</span></span>|<span data-ttu-id="9c4d8-115">引发托管异常。</span><span class="sxs-lookup"><span data-stu-id="9c4d8-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="9c4d8-116">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="9c4d8-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="9c4d8-117">字段名</span><span class="sxs-lookup"><span data-stu-id="9c4d8-117">Field name</span></span>|<span data-ttu-id="9c4d8-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c4d8-118">Data type</span></span>|<span data-ttu-id="9c4d8-119">描述</span><span class="sxs-lookup"><span data-stu-id="9c4d8-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="9c4d8-120">异常类型</span><span class="sxs-lookup"><span data-stu-id="9c4d8-120">Exception Type</span></span>|<span data-ttu-id="9c4d8-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9c4d8-121">win:UnicodeString</span></span>|<span data-ttu-id="9c4d8-122">异常的类型，例如，`System.NullReferenceException`。</span><span class="sxs-lookup"><span data-stu-id="9c4d8-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="9c4d8-123">异常消息</span><span class="sxs-lookup"><span data-stu-id="9c4d8-123">Exception Message</span></span>|<span data-ttu-id="9c4d8-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9c4d8-124">win:UnicodeString</span></span>|<span data-ttu-id="9c4d8-125">实际的异常消息。</span><span class="sxs-lookup"><span data-stu-id="9c4d8-125">Actual exception message.</span></span>|  
|<span data-ttu-id="9c4d8-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="9c4d8-126">EIPCodeThrow</span></span>|<span data-ttu-id="9c4d8-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="9c4d8-127">win:Pointer</span></span>|<span data-ttu-id="9c4d8-128">指向异常发生位置的指令指针。</span><span class="sxs-lookup"><span data-stu-id="9c4d8-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="9c4d8-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="9c4d8-129">ExceptionHR</span></span>|<span data-ttu-id="9c4d8-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="9c4d8-130">win:UInt32</span></span>|<span data-ttu-id="9c4d8-131">异常 [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679)。</span><span class="sxs-lookup"><span data-stu-id="9c4d8-131">Exception [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="9c4d8-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="9c4d8-132">ExceptionFlags</span></span>|<span data-ttu-id="9c4d8-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9c4d8-133">win:UInt16</span></span>|<span data-ttu-id="9c4d8-134">0x01:HasInnerException (请参阅[CLR ETW 事件](../../../docs/framework/performance/clr-etw-events.md)Visual Basic 文档中)。</span><span class="sxs-lookup"><span data-stu-id="9c4d8-134">0x01: HasInnerException (see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="9c4d8-135">0x02:IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="9c4d8-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="9c4d8-136">0x04:IsRethrownException。</span><span class="sxs-lookup"><span data-stu-id="9c4d8-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="9c4d8-137">0x08:IsCorruptedStateException (表示进程状态已损坏; 请参阅[处理损坏状态异常](https://go.microsoft.com/fwlink/?LinkId=179681)MSDN 上)。</span><span class="sxs-lookup"><span data-stu-id="9c4d8-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="9c4d8-138">0x10:IsCLSCompliant (从派生的异常<xref:System.Exception>符合 CLS 規格; 否则为不符合 CLS 規格)。</span><span class="sxs-lookup"><span data-stu-id="9c4d8-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="9c4d8-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="9c4d8-139">ClrInstanceID</span></span>|<span data-ttu-id="9c4d8-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9c4d8-140">win:UInt16</span></span>|<span data-ttu-id="9c4d8-141">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="9c4d8-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c4d8-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c4d8-142">See also</span></span>
- [<span data-ttu-id="9c4d8-143">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="9c4d8-143">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
