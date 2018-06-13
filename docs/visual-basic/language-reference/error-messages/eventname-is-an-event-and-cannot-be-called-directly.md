---
title: '&#39;&lt;eventname&gt; &#39;是一种事件，并且不能直接调用'
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 4d8a7d716d2b7c52d1d027a1e7959d981bb0857e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587327"
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="c2717-102">&#39;&lt;eventname&gt; &#39;是一种事件，并且不能直接调用</span><span class="sxs-lookup"><span data-stu-id="c2717-102">&#39;&lt;eventname&gt;&#39; is an event, and cannot be called directly</span></span>
<span data-ttu-id="c2717-103"><`eventname`> 是一种事件，并因此不能直接调用。</span><span class="sxs-lookup"><span data-stu-id="c2717-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="c2717-104">使用`RaiseEvent`语句以引发一个事件。</span><span class="sxs-lookup"><span data-stu-id="c2717-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="c2717-105">过程调用指定过程名称的事件。</span><span class="sxs-lookup"><span data-stu-id="c2717-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="c2717-106">事件处理程序是一个过程，但事件本身的信号的设备，必须引发事件并处理。</span><span class="sxs-lookup"><span data-stu-id="c2717-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="c2717-107">**错误 ID:** BC32022</span><span class="sxs-lookup"><span data-stu-id="c2717-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c2717-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="c2717-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="c2717-109">使用`RaiseEvent`语句发出信号事件并调用或多个处理它的过程。</span><span class="sxs-lookup"><span data-stu-id="c2717-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2717-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2717-110">See Also</span></span>  
 [<span data-ttu-id="c2717-111">RaiseEvent 语句</span><span class="sxs-lookup"><span data-stu-id="c2717-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
