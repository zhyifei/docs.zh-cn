---
title: "如何︰ 声明自定义事件以节省内存 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: 11
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
ms.openlocfilehash: 130cbda875d6a56f826aefea341d233ea4b3731d
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="d6ff1-102">如何：声明自定义事件以节省内存 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6ff1-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="d6ff1-103">重要应用程序保持其内存使用量较低时，有几种情况。</span><span class="sxs-lookup"><span data-stu-id="d6ff1-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="d6ff1-104">自定义事件允许应用程序内存仅用于其处理的事件。</span><span class="sxs-lookup"><span data-stu-id="d6ff1-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="d6ff1-105">默认情况下，当一个类声明事件时，编译器将内存分配给一个字段来存储事件信息。</span><span class="sxs-lookup"><span data-stu-id="d6ff1-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="d6ff1-106">如果类具有许多未使用的事件，它们将不必要地占用内存。</span><span class="sxs-lookup"><span data-stu-id="d6ff1-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="d6ff1-107">而不是使用 Visual Basic 提供的事件的默认实现，您可以使用自定义事件以更加仔细地管理内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="d6ff1-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6ff1-108">示例</span><span class="sxs-lookup"><span data-stu-id="d6ff1-108">Example</span></span>  
 <span data-ttu-id="d6ff1-109">在此示例中，类使用的一个实例<xref:System.ComponentModel.EventHandlerList>类中，存储在`Events`字段中，在使用中存储有关的事件的信息。</xref:System.ComponentModel.EventHandlerList></span><span class="sxs-lookup"><span data-stu-id="d6ff1-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="d6ff1-110"><xref:System.ComponentModel.EventHandlerList>类是经过优化的列表类，用于保存委托。</xref:System.ComponentModel.EventHandlerList></span><span class="sxs-lookup"><span data-stu-id="d6ff1-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="d6ff1-111">类使用中的所有事件`Events`字段来跟踪哪些方法正处理的每个事件。</span><span class="sxs-lookup"><span data-stu-id="d6ff1-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 <span data-ttu-id="d6ff1-112">[!code-vb[VbVbalrEvents #&22;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d6ff1-112">[!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6ff1-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6ff1-113">See Also</span></span>  
 <span data-ttu-id="d6ff1-114"><xref:System.ComponentModel.EventHandlerList></xref:System.ComponentModel.EventHandlerList></span><span class="sxs-lookup"><span data-stu-id="d6ff1-114"><xref:System.ComponentModel.EventHandlerList></span></span>   
<span data-ttu-id="d6ff1-115"> [事件](../../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="d6ff1-115"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="d6ff1-116"> [如何：声明自定义事件以避免阻止](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="d6ff1-116"> [How to: Declare Custom Events To Avoid Blocking](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)</span></span>
