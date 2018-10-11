---
title: 事件（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 4031ff08bee945f019974ad590e9b3df6d9c263c
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086227"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="a2a4f-102">事件（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="a2a4f-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="a2a4f-103">[类](../../../csharp/language-reference/keywords/class.md) 或对象可以通过事件向其他类或对象通知发生的相关事情。</span><span class="sxs-lookup"><span data-stu-id="a2a4f-103">Events enable a [class](../../../csharp/language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="a2a4f-104">发送（或 *引发*）事件的类称为“发行者”  ，接收（或 *处理*）事件的类称为“订户” 。</span><span class="sxs-lookup"><span data-stu-id="a2a4f-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
 <span data-ttu-id="a2a4f-105">在典型的 C# Windows 窗体或 Web 应用程序中，可订阅由按钮和列表框等控件引发的事件。</span><span class="sxs-lookup"><span data-stu-id="a2a4f-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="a2a4f-106">可以使用 Visual C# 集成开发环境 (IDE) 来浏览控件发布的事件，并选择想要处理的事件。</span><span class="sxs-lookup"><span data-stu-id="a2a4f-106">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="a2a4f-107">IDE 将自动添加空白事件处理程序方法和订阅该事件的代码。</span><span class="sxs-lookup"><span data-stu-id="a2a4f-107">The IDE automatically adds an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="a2a4f-108">有关详细信息，请参阅[如何：订阅和取消订阅事件](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)。</span><span class="sxs-lookup"><span data-stu-id="a2a4f-108">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="events-overview"></a><span data-ttu-id="a2a4f-109">事件概述</span><span class="sxs-lookup"><span data-stu-id="a2a4f-109">Events Overview</span></span>  
 <span data-ttu-id="a2a4f-110">事件具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="a2a4f-110">Events have the following properties:</span></span>  
  
-   <span data-ttu-id="a2a4f-111">发行者确定何时引发事件；订户确定对事件作出何种响应。</span><span class="sxs-lookup"><span data-stu-id="a2a4f-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
-   <span data-ttu-id="a2a4f-112">一个事件可以有多个订户。</span><span class="sxs-lookup"><span data-stu-id="a2a4f-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="a2a4f-113">订户可以处理来自多个发行者的多个事件。</span><span class="sxs-lookup"><span data-stu-id="a2a4f-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
-   <span data-ttu-id="a2a4f-114">没有订户的事件永远也不会引发。</span><span class="sxs-lookup"><span data-stu-id="a2a4f-114">Events that have no subscribers are never raised.</span></span>  
  
-   <span data-ttu-id="a2a4f-115">事件通常用于表示用户操作，例如单击按钮或图形用户界面中的菜单选项。</span><span class="sxs-lookup"><span data-stu-id="a2a4f-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
-   <span data-ttu-id="a2a4f-116">当事件具有多个订户时，引发该事件时会同步调用事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a2a4f-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="a2a4f-117">若要异步调用事件，请参阅 [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)。</span><span class="sxs-lookup"><span data-stu-id="a2a4f-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
-   <span data-ttu-id="a2a4f-118">在 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 类库中，事件基于 <xref:System.EventHandler> 委托和 <xref:System.EventArgs> 基类。</span><span class="sxs-lookup"><span data-stu-id="a2a4f-118">In the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a2a4f-119">相关章节</span><span class="sxs-lookup"><span data-stu-id="a2a4f-119">Related Sections</span></span>  
 <span data-ttu-id="a2a4f-120">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="a2a4f-120">For more information, see:</span></span>  
  
-   [<span data-ttu-id="a2a4f-121">如何：订阅和取消订阅事件</span><span class="sxs-lookup"><span data-stu-id="a2a4f-121">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [<span data-ttu-id="a2a4f-122">如何：发布符合 .NET Framework 准则的事件</span><span class="sxs-lookup"><span data-stu-id="a2a4f-122">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [<span data-ttu-id="a2a4f-123">如何：在派生类中引发基类事件</span><span class="sxs-lookup"><span data-stu-id="a2a4f-123">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [<span data-ttu-id="a2a4f-124">如何：实现接口事件</span><span class="sxs-lookup"><span data-stu-id="a2a4f-124">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="a2a4f-125">如何：使用字典存储事件实例</span><span class="sxs-lookup"><span data-stu-id="a2a4f-125">How to: Use a Dictionary to Store Event Instances</span></span>](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [<span data-ttu-id="a2a4f-126">如何：实现自定义事件访问器</span><span class="sxs-lookup"><span data-stu-id="a2a4f-126">How to: Implement Custom Event Accessors</span></span>](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="a2a4f-127">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="a2a4f-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="a2a4f-128">重要章节</span><span class="sxs-lookup"><span data-stu-id="a2a4f-128">Featured Book Chapters</span></span>  
 <span data-ttu-id="a2a4f-129">[C# 3.0 手册，第三版：为 C# 3.0 程序员提供的 250 多个解决方案](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) 中的 [委托、事件和 Lambda 表达式](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span><span class="sxs-lookup"><span data-stu-id="a2a4f-129">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span></span>  
  
 <span data-ttu-id="a2a4f-130">[Learning C# 3.0: Master the Fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) （学习 C# 3.0：掌握 C# 3.0 的基本知识）中的 [委托和事件](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span><span class="sxs-lookup"><span data-stu-id="a2a4f-130">[Delegates and Events](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a4f-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2a4f-131">See Also</span></span>

- <xref:System.EventHandler>  
- [<span data-ttu-id="a2a4f-132">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a2a4f-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a2a4f-133">委托</span><span class="sxs-lookup"><span data-stu-id="a2a4f-133">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
- [<span data-ttu-id="a2a4f-134">在 Windows 窗体中创建事件处理程序</span><span class="sxs-lookup"><span data-stu-id="a2a4f-134">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
