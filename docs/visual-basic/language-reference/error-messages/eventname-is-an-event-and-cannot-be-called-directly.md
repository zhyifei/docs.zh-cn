---
title: “<eventname>”是事件，不能直接调用
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: bf900566bdb4ecf8d8961a12b5dd67ba426caf27
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59305593"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="694a2-102">\<事件名称 > 是一种事件，而且不能直接调用</span><span class="sxs-lookup"><span data-stu-id="694a2-102">'\<eventname>' is an event, and cannot be called directly</span></span>
<span data-ttu-id="694a2-103"><`eventname`> 是一种事件，并因此不能直接调用。</span><span class="sxs-lookup"><span data-stu-id="694a2-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="694a2-104">使用`RaiseEvent`语句引发事件。</span><span class="sxs-lookup"><span data-stu-id="694a2-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="694a2-105">过程调用指定的事件的过程名称。</span><span class="sxs-lookup"><span data-stu-id="694a2-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="694a2-106">事件处理程序是一个过程，但事件本身的信号的设备，必须引发并处理。</span><span class="sxs-lookup"><span data-stu-id="694a2-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="694a2-107">**错误 ID:** BC32022</span><span class="sxs-lookup"><span data-stu-id="694a2-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="694a2-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="694a2-108">To correct this error</span></span>  
  
1. <span data-ttu-id="694a2-109">使用`RaiseEvent`语句发出信号事件并调用过程或对其进行处理的过程。</span><span class="sxs-lookup"><span data-stu-id="694a2-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="694a2-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="694a2-110">See also</span></span>

- [<span data-ttu-id="694a2-111">RaiseEvent 语句</span><span class="sxs-lookup"><span data-stu-id="694a2-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
