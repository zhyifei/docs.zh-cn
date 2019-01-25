---
title: 如何：声明自定义事件以节省内存 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: bf22c2029671588ab0ebaefd2554fcb2a5a1131c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719516"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="41094-102">如何：声明自定义事件以节省内存 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41094-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="41094-103">重要应用程序保持其内存使用量较低时，有几种情况。</span><span class="sxs-lookup"><span data-stu-id="41094-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="41094-104">自定义事件允许应用程序内存仅用于其处理的事件。</span><span class="sxs-lookup"><span data-stu-id="41094-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="41094-105">默认情况下，当一个类声明事件时，编译器将内存分配给一个字段来存储事件信息。</span><span class="sxs-lookup"><span data-stu-id="41094-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="41094-106">如果类具有多个未使用的事件，它们将不必要地占用内存。</span><span class="sxs-lookup"><span data-stu-id="41094-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="41094-107">而不是使用 Visual Basic 提供的事件的默认实现，可以使用自定义事件以更加仔细地管理内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="41094-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41094-108">示例</span><span class="sxs-lookup"><span data-stu-id="41094-108">Example</span></span>  
 <span data-ttu-id="41094-109">在此示例中，类使用的一个实例<xref:System.ComponentModel.EventHandlerList>类，存储在`Events`字段中，在使用中存储有关事件的信息。</span><span class="sxs-lookup"><span data-stu-id="41094-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="41094-110"><xref:System.ComponentModel.EventHandlerList>类是设计用来存放委托的优化的列表类。</span><span class="sxs-lookup"><span data-stu-id="41094-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="41094-111">类使用中的所有事件`Events`字段来跟踪哪些方法正处理的每个事件。</span><span class="sxs-lookup"><span data-stu-id="41094-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="41094-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="41094-112">See also</span></span>
- <xref:System.ComponentModel.EventHandlerList>
- [<span data-ttu-id="41094-113">事件</span><span class="sxs-lookup"><span data-stu-id="41094-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="41094-114">如何：声明自定义事件以避免阻止</span><span class="sxs-lookup"><span data-stu-id="41094-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
