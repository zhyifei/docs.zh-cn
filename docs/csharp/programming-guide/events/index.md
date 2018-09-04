---
title: 事件（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 03c2ffc37bc6c2e820b8e28599f415cde1be9be5
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521952"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="493f7-102">事件（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="493f7-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="493f7-103">[类](../../../csharp/language-reference/keywords/class.md) 或对象可以通过事件向其他类或对象通知发生的相关事情。</span><span class="sxs-lookup"><span data-stu-id="493f7-103">Events enable a [class](../../../csharp/language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="493f7-104">发送（或 *引发*）事件的类称为“发行者”  ，接收（或 *处理*）事件的类称为“订户” 。</span><span class="sxs-lookup"><span data-stu-id="493f7-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
 <span data-ttu-id="493f7-105">在典型的 C# Windows 窗体或 Web 应用程序中，可订阅由按钮和列表框等控件引发的事件。</span><span class="sxs-lookup"><span data-stu-id="493f7-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="493f7-106">可以使用 Visual C# 集成开发环境 (IDE) 来浏览控件发布的事件，并选择想要处理的事件。</span><span class="sxs-lookup"><span data-stu-id="493f7-106">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="493f7-107">IDE 将自动添加空白事件处理程序方法和订阅该事件的代码。</span><span class="sxs-lookup"><span data-stu-id="493f7-107">The IDE automatically adds an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="493f7-108">有关详细信息，请参阅[如何：订阅和取消订阅事件](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)。</span><span class="sxs-lookup"><span data-stu-id="493f7-108">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="events-overview"></a><span data-ttu-id="493f7-109">事件概述</span><span class="sxs-lookup"><span data-stu-id="493f7-109">Events Overview</span></span>  
 <span data-ttu-id="493f7-110">事件具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="493f7-110">Events have the following properties:</span></span>  
  
-   <span data-ttu-id="493f7-111">发行者确定何时引发事件；订户确定对事件作出何种响应。</span><span class="sxs-lookup"><span data-stu-id="493f7-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
-   <span data-ttu-id="493f7-112">一个事件可以有多个订户。</span><span class="sxs-lookup"><span data-stu-id="493f7-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="493f7-113">订户可以处理来自多个发行者的多个事件。</span><span class="sxs-lookup"><span data-stu-id="493f7-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
-   <span data-ttu-id="493f7-114">没有订户的事件永远也不会引发。</span><span class="sxs-lookup"><span data-stu-id="493f7-114">Events that have no subscribers are never raised.</span></span>  
  
-   <span data-ttu-id="493f7-115">事件通常用于表示用户操作，例如单击按钮或图形用户界面中的菜单选项。</span><span class="sxs-lookup"><span data-stu-id="493f7-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
-   <span data-ttu-id="493f7-116">当事件具有多个订户时，引发该事件时会同步调用事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="493f7-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="493f7-117">若要异步调用事件，请参阅 [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)。</span><span class="sxs-lookup"><span data-stu-id="493f7-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
-   <span data-ttu-id="493f7-118">在 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 类库中，事件基于 <xref:System.EventHandler> 委托和 <xref:System.EventArgs> 基类。</span><span class="sxs-lookup"><span data-stu-id="493f7-118">In the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="493f7-119">相关章节</span><span class="sxs-lookup"><span data-stu-id="493f7-119">Related Sections</span></span>  
 <span data-ttu-id="493f7-120">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="493f7-120">For more information, see:</span></span>  
  
-   [<span data-ttu-id="493f7-121">如何：订阅和取消订阅事件</span><span class="sxs-lookup"><span data-stu-id="493f7-121">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [<span data-ttu-id="493f7-122">如何：发布符合 .NET Framework 准则的事件</span><span class="sxs-lookup"><span data-stu-id="493f7-122">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [<span data-ttu-id="493f7-123">如何：在派生类中引发基类事件</span><span class="sxs-lookup"><span data-stu-id="493f7-123">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [<span data-ttu-id="493f7-124">如何：实现接口事件</span><span class="sxs-lookup"><span data-stu-id="493f7-124">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="493f7-125">线程同步</span><span class="sxs-lookup"><span data-stu-id="493f7-125">Thread Synchronization</span></span>](../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
  
-   [<span data-ttu-id="493f7-126">如何：使用字典存储事件实例</span><span class="sxs-lookup"><span data-stu-id="493f7-126">How to: Use a Dictionary to Store Event Instances</span></span>](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [<span data-ttu-id="493f7-127">如何：实现自定义事件访问器</span><span class="sxs-lookup"><span data-stu-id="493f7-127">How to: Implement Custom Event Accessors</span></span>](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="493f7-128">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="493f7-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="493f7-129">重要章节</span><span class="sxs-lookup"><span data-stu-id="493f7-129">Featured Book Chapters</span></span>  
 <span data-ttu-id="493f7-130">[C# 3.0 手册，第三版：为 C# 3.0 程序员提供的 250 多个解决方案](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) 中的 [委托、事件和 Lambda 表达式](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span><span class="sxs-lookup"><span data-stu-id="493f7-130">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span></span>  
  
 <span data-ttu-id="493f7-131">[Learning C# 3.0: Master the Fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) （学习 C# 3.0：掌握 C# 3.0 的基本知识）中的 [委托和事件](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span><span class="sxs-lookup"><span data-stu-id="493f7-131">[Delegates and Events](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="493f7-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="493f7-132">See Also</span></span>

- <xref:System.EventHandler>  
- [<span data-ttu-id="493f7-133">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="493f7-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="493f7-134">委托</span><span class="sxs-lookup"><span data-stu-id="493f7-134">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
- [<span data-ttu-id="493f7-135">在 Windows 窗体中创建事件处理程序</span><span class="sxs-lookup"><span data-stu-id="493f7-135">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
