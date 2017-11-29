---
title: "如何：声明自定义事件以避免阻止 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a36c855efb67752674615a61f2fa701974ce5f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="eeded-102">如何：声明自定义事件以避免阻止 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eeded-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="eeded-103">有几种情况下很重要的一个事件处理程序不会阻止后续的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="eeded-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="eeded-104">自定义事件允许事件以异步方式调用其事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="eeded-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="eeded-105">默认情况下，事件声明的后备存储字段是按顺序将合并所有事件处理程序的多路广播的委托。</span><span class="sxs-lookup"><span data-stu-id="eeded-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="eeded-106">这意味着，如果一个处理程序采用较长时间才能完成，它将阻止其他处理程序直到它完成。</span><span class="sxs-lookup"><span data-stu-id="eeded-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="eeded-107">（功能良好的事件处理程序应永远不会执行时间较长或可能起阻止作用的操作。）</span><span class="sxs-lookup"><span data-stu-id="eeded-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="eeded-108">而不是使用 Visual Basic 提供的事件的默认实现，你可以使用自定义事件以异步方式执行的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="eeded-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eeded-109">示例</span><span class="sxs-lookup"><span data-stu-id="eeded-109">Example</span></span>  
 <span data-ttu-id="eeded-110">在此示例中，`AddHandler`访问器将添加的每个处理程序委托`Click`事件<xref:System.Collections.ArrayList>存储在`EventHandlerList`字段。</span><span class="sxs-lookup"><span data-stu-id="eeded-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="eeded-111">在代码引发`Click`事件，`RaiseEvent`访问器时，将调用以异步方式使用的所有事件处理程序委托<xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="eeded-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="eeded-112">该方法调用每个工作线程上的处理程序并立即返回，因此处理程序无法阻止另一个。</span><span class="sxs-lookup"><span data-stu-id="eeded-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="eeded-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eeded-113">See Also</span></span>  
 <xref:System.Collections.ArrayList>  
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>  
 [<span data-ttu-id="eeded-114">事件</span><span class="sxs-lookup"><span data-stu-id="eeded-114">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="eeded-115">如何：声明自定义事件以节省内存</span><span class="sxs-lookup"><span data-stu-id="eeded-115">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
