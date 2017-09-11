---
title: "如何︰ 声明自定义事件以避免阻止 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declaring events, custom
- events [Visual Basic], custom
- custom events
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 52181d1c307e4e312f4511719e540fd6d5bfcfa8
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="1bc85-102">如何：声明自定义事件以避免阻止 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1bc85-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="1bc85-103">有几种情况下很重要的一个事件处理程序不会阻止后续事件处理程序时。</span><span class="sxs-lookup"><span data-stu-id="1bc85-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="1bc85-104">自定义事件允许事件以异步方式调用其事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="1bc85-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="1bc85-105">默认情况下，在事件声明的后备存储字段是一个按顺序组合所有事件处理程序的多路广播的委托。</span><span class="sxs-lookup"><span data-stu-id="1bc85-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="1bc85-106">这意味着，如果一个处理程序采用较长时间才能完成，它将阻止其他处理程序直到它完成。</span><span class="sxs-lookup"><span data-stu-id="1bc85-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="1bc85-107">（功能良好的事件处理程序应永远不会执行耗时较长或可能起阻止作用的操作。）</span><span class="sxs-lookup"><span data-stu-id="1bc85-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="1bc85-108">而不是使用 Visual Basic 提供的事件的默认实现，您可以使用自定义事件以异步方式执行的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="1bc85-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bc85-109">示例</span><span class="sxs-lookup"><span data-stu-id="1bc85-109">Example</span></span>  
 <span data-ttu-id="1bc85-110">在此示例中，`AddHandler`取值函数添加的每个处理程序委托`Click`事件到<xref:System.Collections.ArrayList>存储在`EventHandlerList`字段。</xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="1bc85-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="1bc85-111">在代码引发`Click`事件，`RaiseEvent`取值函数时，将调用以异步方式使用的所有事件处理程序委托<xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>方法。</xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></span><span class="sxs-lookup"><span data-stu-id="1bc85-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="1bc85-112">该方法调用每个工作线程上的处理程序，并立即返回，这样处理程序无法阻止的另一个。</span><span class="sxs-lookup"><span data-stu-id="1bc85-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 <span data-ttu-id="1bc85-113">[!code-vb[VbVbalrEvents #&27;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1bc85-113">[!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bc85-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1bc85-114">See Also</span></span>  
 <span data-ttu-id="1bc85-115"><xref:System.Collections.ArrayList></xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="1bc85-115"><xref:System.Collections.ArrayList></span></span>   
 <span data-ttu-id="1bc85-116"><xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></span><span class="sxs-lookup"><span data-stu-id="1bc85-116"><xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></span></span>   
<span data-ttu-id="1bc85-117"> [事件](../../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="1bc85-117"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="1bc85-118"> [如何：声明自定义事件以节省内存](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)</span><span class="sxs-lookup"><span data-stu-id="1bc85-118"> [How to: Declare Custom Events To Conserve Memory](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)</span></span>
