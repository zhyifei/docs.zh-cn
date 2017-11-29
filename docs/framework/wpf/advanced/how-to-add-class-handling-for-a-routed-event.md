---
title: "如何：为路由事件添加类处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abbbdce0ca12c4d8bdd12f616bf49c3d6f66f441
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a><span data-ttu-id="4a23f-102">如何：为路由事件添加类处理</span><span class="sxs-lookup"><span data-stu-id="4a23f-102">How to: Add Class Handling for a Routed Event</span></span>
<span data-ttu-id="4a23f-103">通过类处理程序或路线中的任何给定节点上的实例处理程序，可以处理路由的事件。</span><span class="sxs-lookup"><span data-stu-id="4a23f-103">Routed events can be handled either by class handlers or instance handlers on any given node in the route.</span></span> <span data-ttu-id="4a23f-104">首先，调用和类的实现可以使用取消实例处理的事件，或引入其他事件所拥有的基类的事件的特定行为的类处理。</span><span class="sxs-lookup"><span data-stu-id="4a23f-104">Class handlers are invoked first, and can be used by class implementations to suppress events from instance handling or introduce other event specific behaviors on events that are owned by base classes.</span></span> <span data-ttu-id="4a23f-105">此示例阐释用来实现类处理程序的两个密切相关的技术。</span><span class="sxs-lookup"><span data-stu-id="4a23f-105">This example illustrates two closely related techniques for implementing class handlers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a23f-106">示例</span><span class="sxs-lookup"><span data-stu-id="4a23f-106">Example</span></span>  
 <span data-ttu-id="4a23f-107">此示例使用自定义类基于<xref:System.Windows.Controls.Canvas>面板。</span><span class="sxs-lookup"><span data-stu-id="4a23f-107">This example uses a custom class based on the <xref:System.Windows.Controls.Canvas> panel.</span></span> <span data-ttu-id="4a23f-108">应用程序的基本前提是自定义类引入了对其子元素，包括截获任何鼠标左键单击并标记它们的处理，然后将调用的子元素类或在其上的任何实例处理行为。</span><span class="sxs-lookup"><span data-stu-id="4a23f-108">The basic premise of the application is that the custom class introduces behaviors on its child elements, including intercepting any left mouse button clicks and marking them handled, before the child element class or any instance handlers on it will be invoked.</span></span>  
  
 <span data-ttu-id="4a23f-109"><xref:System.Windows.UIElement>类公开一个虚拟方法，使类上处理<xref:System.Windows.UIElement.PreviewMouseLeftButtonDown>事件，只需重写该事件。</span><span class="sxs-lookup"><span data-stu-id="4a23f-109">The <xref:System.Windows.UIElement> class exposes a virtual method that enables class handling on the <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> event, by simply overriding the event.</span></span> <span data-ttu-id="4a23f-110">这是你的类层次结构中的某个位置可用这样的虚方法是否实现类处理的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="4a23f-110">This is the simplest way to implement class handling if such a virtual method is available somewhere in your class' hierarchy.</span></span> <span data-ttu-id="4a23f-111">下面的代码演示<xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A>派生自"MyEditContainer"中的实现<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="4a23f-111">The following code shows the <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementation in the "MyEditContainer" that is derived from <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="4a23f-112">实现将事件标记为参数，处理，然后添加某些代码来提供基本明显的变化的源元素。</span><span class="sxs-lookup"><span data-stu-id="4a23f-112">The implementation marks the event as handled in the arguments, and then adds some code to give the source element a basic visible change.</span></span>  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 <span data-ttu-id="4a23f-113">如果任何虚拟基类上或针对该特定的方法可用，可以直接使用的实用程序方法添加类处理<xref:System.Windows.EventManager>类， <xref:System.Windows.EventManager.RegisterClassHandler%2A>。</span><span class="sxs-lookup"><span data-stu-id="4a23f-113">If no virtual is available on base classes or for that particular method, class handling can be added directly using a utility method of the <xref:System.Windows.EventManager> class, <xref:System.Windows.EventManager.RegisterClassHandler%2A>.</span></span> <span data-ttu-id="4a23f-114">仅应要添加类处理的类的静态初始化内部调用此方法。</span><span class="sxs-lookup"><span data-stu-id="4a23f-114">This method should only be called within the static initialization of classes that are adding class handling.</span></span> <span data-ttu-id="4a23f-115">此示例将添加另一个处理程序<xref:System.Windows.UIElement.PreviewMouseLeftButtonDown>，并且在这种情况下为注册的类自定义类。</span><span class="sxs-lookup"><span data-stu-id="4a23f-115">This example adds another handler for <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , and in this case the registered class is the custom class.</span></span> <span data-ttu-id="4a23f-116">与此相反，使用虚方法，已注册的类时，实际上<xref:System.Windows.UIElement>基类。</span><span class="sxs-lookup"><span data-stu-id="4a23f-116">In contrast, when using the virtuals, the registered class is really the <xref:System.Windows.UIElement> base class.</span></span> <span data-ttu-id="4a23f-117">在基的类和子类每个在其中注册类处理的情况下，首先调用子类处理程序。</span><span class="sxs-lookup"><span data-stu-id="4a23f-117">In cases where base classes and subclass each register class handling, the subclass handlers are invoked first.</span></span> <span data-ttu-id="4a23f-118">在应用程序行为将是，此处理程序将首先显示其消息框，然后将显示了虚拟方法的处理程序中的可视化变更。</span><span class="sxs-lookup"><span data-stu-id="4a23f-118">The behavior in an application would be that first this handler would show its message box and then the visual change in the virtual method's handler would be shown.</span></span>  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a><span data-ttu-id="4a23f-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a23f-119">See Also</span></span>  
 <xref:System.Windows.EventManager>  
 [<span data-ttu-id="4a23f-120">将路由事件标记为“已处理”和“类处理”</span><span class="sxs-lookup"><span data-stu-id="4a23f-120">Marking Routed Events as Handled, and Class Handling</span></span>](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [<span data-ttu-id="4a23f-121">处理路由事件</span><span class="sxs-lookup"><span data-stu-id="4a23f-121">Handle a Routed Event</span></span>](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)  
 [<span data-ttu-id="4a23f-122">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="4a23f-122">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
