---
title: 异常 Thrown_V1 ETW 事件
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f0e968053c87319bf90bf3de0f21d750ec899ab
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447628"
---
# <a name="exception-thrown_v1-etw-event"></a><span data-ttu-id="b89f3-102">异常 Thrown_V1 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="b89f3-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="b89f3-103">该事件捕获有关引发的异常的信息。</span><span class="sxs-lookup"><span data-stu-id="b89f3-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="b89f3-104">下表显示了引发事件的关键字以及事件的级别。</span><span class="sxs-lookup"><span data-stu-id="b89f3-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="b89f3-105">（有关详细信息，请参阅 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)。）</span><span class="sxs-lookup"><span data-stu-id="b89f3-105">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="b89f3-106">引发事件的关键字</span><span class="sxs-lookup"><span data-stu-id="b89f3-106">Keyword for raising the event</span></span>|<span data-ttu-id="b89f3-107">层次</span><span class="sxs-lookup"><span data-stu-id="b89f3-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b89f3-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="b89f3-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="b89f3-109">警告 (2)</span><span class="sxs-lookup"><span data-stu-id="b89f3-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="b89f3-110">下表显示了事件信息。</span><span class="sxs-lookup"><span data-stu-id="b89f3-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="b89f3-111">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="b89f3-111">Event</span></span>|<span data-ttu-id="b89f3-112">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b89f3-112">Event ID</span></span>|<span data-ttu-id="b89f3-113">在发生以下情况时引发</span><span class="sxs-lookup"><span data-stu-id="b89f3-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="b89f3-114">80</span><span class="sxs-lookup"><span data-stu-id="b89f3-114">80</span></span>|<span data-ttu-id="b89f3-115">引发托管异常。</span><span class="sxs-lookup"><span data-stu-id="b89f3-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="b89f3-116">下表显示了事件数据。</span><span class="sxs-lookup"><span data-stu-id="b89f3-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="b89f3-117">字段名</span><span class="sxs-lookup"><span data-stu-id="b89f3-117">Field name</span></span>|<span data-ttu-id="b89f3-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="b89f3-118">Data type</span></span>|<span data-ttu-id="b89f3-119">描述</span><span class="sxs-lookup"><span data-stu-id="b89f3-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b89f3-120">异常类型</span><span class="sxs-lookup"><span data-stu-id="b89f3-120">Exception Type</span></span>|<span data-ttu-id="b89f3-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b89f3-121">win:UnicodeString</span></span>|<span data-ttu-id="b89f3-122">异常的类型，例如，`System.NullReferenceException`。</span><span class="sxs-lookup"><span data-stu-id="b89f3-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="b89f3-123">异常消息</span><span class="sxs-lookup"><span data-stu-id="b89f3-123">Exception Message</span></span>|<span data-ttu-id="b89f3-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b89f3-124">win:UnicodeString</span></span>|<span data-ttu-id="b89f3-125">实际的异常消息。</span><span class="sxs-lookup"><span data-stu-id="b89f3-125">Actual exception message.</span></span>|  
|<span data-ttu-id="b89f3-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="b89f3-126">EIPCodeThrow</span></span>|<span data-ttu-id="b89f3-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="b89f3-127">win:Pointer</span></span>|<span data-ttu-id="b89f3-128">指向异常发生位置的指令指针。</span><span class="sxs-lookup"><span data-stu-id="b89f3-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="b89f3-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="b89f3-129">ExceptionHR</span></span>|<span data-ttu-id="b89f3-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b89f3-130">win:UInt32</span></span>|<span data-ttu-id="b89f3-131">异常 [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a)。</span><span class="sxs-lookup"><span data-stu-id="b89f3-131">Exception [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|  
|<span data-ttu-id="b89f3-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="b89f3-132">ExceptionFlags</span></span>|<span data-ttu-id="b89f3-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b89f3-133">win:UInt16</span></span>|<span data-ttu-id="b89f3-134">0x01: HasInnerException（参阅 Visual Basic 文档中的 [CLR ETW 事件](clr-etw-events.md)）。</span><span class="sxs-lookup"><span data-stu-id="b89f3-134">0x01: HasInnerException (see [CLR ETW Events](clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="b89f3-135">0x02: IsNestedException。</span><span class="sxs-lookup"><span data-stu-id="b89f3-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="b89f3-136">0x04: IsRethrownException。</span><span class="sxs-lookup"><span data-stu-id="b89f3-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="b89f3-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span><span class="sxs-lookup"><span data-stu-id="b89f3-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="b89f3-138">0x10: IsCLSCompliant（从 <xref:System.Exception> 派生的异常符合 CLS，此外的其他异常均不符合 CLS）。</span><span class="sxs-lookup"><span data-stu-id="b89f3-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="b89f3-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b89f3-139">ClrInstanceID</span></span>|<span data-ttu-id="b89f3-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b89f3-140">win:UInt16</span></span>|<span data-ttu-id="b89f3-141">CLR 或 CoreCLR 的实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="b89f3-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b89f3-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="b89f3-142">See also</span></span>

- [<span data-ttu-id="b89f3-143">CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="b89f3-143">CLR ETW Events</span></span>](clr-etw-events.md)
