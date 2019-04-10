---
title: 如何：为路由事件添加类处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
ms.openlocfilehash: 7b897954cbdab461dc0305c6290e67c1af5282c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224261"
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a><span data-ttu-id="98cbc-102">如何：为路由事件添加类处理</span><span class="sxs-lookup"><span data-stu-id="98cbc-102">How to: Add Class Handling for a Routed Event</span></span>
<span data-ttu-id="98cbc-103">通过类处理程序或路由中的任何给定节点上的实例处理程序可以处理路由的事件。</span><span class="sxs-lookup"><span data-stu-id="98cbc-103">Routed events can be handled either by class handlers or instance handlers on any given node in the route.</span></span> <span data-ttu-id="98cbc-104">类处理程序首先，调用，并可以由类实现来禁止显示来自实例处理的事件或引入其他事件上所拥有的基类的事件的特定行为。</span><span class="sxs-lookup"><span data-stu-id="98cbc-104">Class handlers are invoked first, and can be used by class implementations to suppress events from instance handling or introduce other event specific behaviors on events that are owned by base classes.</span></span> <span data-ttu-id="98cbc-105">此示例说明了实现类处理程序的两个密切相关的方法。</span><span class="sxs-lookup"><span data-stu-id="98cbc-105">This example illustrates two closely related techniques for implementing class handlers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98cbc-106">示例</span><span class="sxs-lookup"><span data-stu-id="98cbc-106">Example</span></span>  
 <span data-ttu-id="98cbc-107">此示例使用自定义类基于<xref:System.Windows.Controls.Canvas>面板。</span><span class="sxs-lookup"><span data-stu-id="98cbc-107">This example uses a custom class based on the <xref:System.Windows.Controls.Canvas> panel.</span></span> <span data-ttu-id="98cbc-108">应用程序的基本前提是自定义类引入了包括截获任何鼠标按钮单击和它们的处理，然后将调用的子元素类或其任何实例处理程序的标记及其子元素上的行为。</span><span class="sxs-lookup"><span data-stu-id="98cbc-108">The basic premise of the application is that the custom class introduces behaviors on its child elements, including intercepting any left mouse button clicks and marking them handled, before the child element class or any instance handlers on it will be invoked.</span></span>  
  
 <span data-ttu-id="98cbc-109"><xref:System.Windows.UIElement>类公开一个虚拟方法，使类上处理<xref:System.Windows.UIElement.PreviewMouseLeftButtonDown>事件，只需重写该事件。</span><span class="sxs-lookup"><span data-stu-id="98cbc-109">The <xref:System.Windows.UIElement> class exposes a virtual method that enables class handling on the <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> event, by simply overriding the event.</span></span> <span data-ttu-id="98cbc-110">这是实现类处理，如果此类的虚方法为您的类层次结构中的某处可用的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="98cbc-110">This is the simplest way to implement class handling if such a virtual method is available somewhere in your class' hierarchy.</span></span> <span data-ttu-id="98cbc-111">下面的代码演示<xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A>派生自"MyEditContainer"中的实现<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="98cbc-111">The following code shows the <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementation in the "MyEditContainer" that is derived from <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="98cbc-112">实现将事件标记为已处理参数中，然后添加一些代码来提供基本明显的变化的源元素。</span><span class="sxs-lookup"><span data-stu-id="98cbc-112">The implementation marks the event as handled in the arguments, and then adds some code to give the source element a basic visible change.</span></span>  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 <span data-ttu-id="98cbc-113">如果任何虚拟基类上或针对该特定方法可用，可以直接使用的实用程序方法添加类处理<xref:System.Windows.EventManager>类， <xref:System.Windows.EventManager.RegisterClassHandler%2A>。</span><span class="sxs-lookup"><span data-stu-id="98cbc-113">If no virtual is available on base classes or for that particular method, class handling can be added directly using a utility method of the <xref:System.Windows.EventManager> class, <xref:System.Windows.EventManager.RegisterClassHandler%2A>.</span></span> <span data-ttu-id="98cbc-114">只应添加类处理的类的静态初始化内部调用此方法。</span><span class="sxs-lookup"><span data-stu-id="98cbc-114">This method should only be called within the static initialization of classes that are adding class handling.</span></span> <span data-ttu-id="98cbc-115">此示例将添加另一个处理程序<xref:System.Windows.UIElement.PreviewMouseLeftButtonDown>，并在这种情况下注册的类是自定义的类。</span><span class="sxs-lookup"><span data-stu-id="98cbc-115">This example adds another handler for <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , and in this case the registered class is the custom class.</span></span> <span data-ttu-id="98cbc-116">与此相反，使用虚方法，注册的类时，真正<xref:System.Windows.UIElement>基类。</span><span class="sxs-lookup"><span data-stu-id="98cbc-116">In contrast, when using the virtuals, the registered class is really the <xref:System.Windows.UIElement> base class.</span></span> <span data-ttu-id="98cbc-117">在基类和子类每个在其中注册类处理的情况下，首次调用子类处理程序。</span><span class="sxs-lookup"><span data-stu-id="98cbc-117">In cases where base classes and subclass each register class handling, the subclass handlers are invoked first.</span></span> <span data-ttu-id="98cbc-118">在应用程序行为将是，此处理程序首先会显示其消息框，则会显示虚拟方法的处理程序中的可视更改。</span><span class="sxs-lookup"><span data-stu-id="98cbc-118">The behavior in an application would be that first this handler would show its message box and then the visual change in the virtual method's handler would be shown.</span></span>  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a><span data-ttu-id="98cbc-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="98cbc-119">See also</span></span>

- <xref:System.Windows.EventManager>
- [<span data-ttu-id="98cbc-120">将路由事件标记为“已处理”和“类处理”</span><span class="sxs-lookup"><span data-stu-id="98cbc-120">Marking Routed Events as Handled, and Class Handling</span></span>](marking-routed-events-as-handled-and-class-handling.md)
- [<span data-ttu-id="98cbc-121">处理路由事件</span><span class="sxs-lookup"><span data-stu-id="98cbc-121">Handle a Routed Event</span></span>](how-to-handle-a-routed-event.md)
- [<span data-ttu-id="98cbc-122">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="98cbc-122">Routed Events Overview</span></span>](routed-events-overview.md)
