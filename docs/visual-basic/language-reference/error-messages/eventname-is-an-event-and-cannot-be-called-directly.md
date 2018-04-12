---
title: '&#39;&lt;eventname&gt;&#39; 是一种事件，并且不能直接调用'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb987c957a28aa37c40ad975b945c20da4690f6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="7a730-102">&#39;&lt;eventname&gt;&#39; 是一种事件，并且不能直接调用</span><span class="sxs-lookup"><span data-stu-id="7a730-102">&#39;&lt;eventname&gt;&#39; is an event, and cannot be called directly</span></span>
<span data-ttu-id="7a730-103"><`eventname`> 是一种事件，并因此不能直接调用。</span><span class="sxs-lookup"><span data-stu-id="7a730-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="7a730-104">使用`RaiseEvent`语句以引发一个事件。</span><span class="sxs-lookup"><span data-stu-id="7a730-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="7a730-105">过程调用指定过程名称的事件。</span><span class="sxs-lookup"><span data-stu-id="7a730-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="7a730-106">事件处理程序是一个过程，但事件本身的信号的设备，必须引发事件并处理。</span><span class="sxs-lookup"><span data-stu-id="7a730-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="7a730-107">**错误 ID:** BC32022</span><span class="sxs-lookup"><span data-stu-id="7a730-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7a730-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="7a730-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="7a730-109">使用`RaiseEvent`语句发出信号事件并调用或多个处理它的过程。</span><span class="sxs-lookup"><span data-stu-id="7a730-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a730-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a730-110">See Also</span></span>  
 [<span data-ttu-id="7a730-111">RaiseEvent 语句</span><span class="sxs-lookup"><span data-stu-id="7a730-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
