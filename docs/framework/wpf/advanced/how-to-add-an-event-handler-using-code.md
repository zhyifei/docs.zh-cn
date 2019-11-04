---
title: 如何：使用代码添加事件处理程序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 457b8cf5c68096b20df7fe39f1cc3f40358f34d0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460437"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="8ef59-102">如何：使用代码添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="8ef59-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="8ef59-103">此示例演示如何使用代码将事件处理程序添加到元素。</span><span class="sxs-lookup"><span data-stu-id="8ef59-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="8ef59-104">如果要将事件处理程序添加到 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 元素，并且已加载包含该元素的标记页，则必须使用代码添加该处理程序。</span><span class="sxs-lookup"><span data-stu-id="8ef59-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="8ef59-105">或者，如果您正在完全使用代码构建应用程序的元素树，而没有使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]声明任何元素，则可以调用特定的方法将事件处理程序添加到构造的元素树中。</span><span class="sxs-lookup"><span data-stu-id="8ef59-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ef59-106">示例</span><span class="sxs-lookup"><span data-stu-id="8ef59-106">Example</span></span>  
 <span data-ttu-id="8ef59-107">下面的示例将新 <xref:System.Windows.Controls.Button> 添加到 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中最初定义的现有页面。</span><span class="sxs-lookup"><span data-stu-id="8ef59-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="8ef59-108">代码隐藏文件实现事件处理程序方法，然后将该方法作为新的事件处理程序添加到 <xref:System.Windows.Controls.Button>上。</span><span class="sxs-lookup"><span data-stu-id="8ef59-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="8ef59-109">该C#示例使用 `+=` 运算符为事件分配处理程序。</span><span class="sxs-lookup"><span data-stu-id="8ef59-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="8ef59-110">这是用于在公共语言运行时（CLR）事件处理模型中分配处理程序的同一运算符。</span><span class="sxs-lookup"><span data-stu-id="8ef59-110">This is the same operator that is used to assign a handler in the common language runtime (CLR) event handling model.</span></span> <span data-ttu-id="8ef59-111">Microsoft Visual Basic 不支持将此运算符作为添加事件处理程序的方法。</span><span class="sxs-lookup"><span data-stu-id="8ef59-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="8ef59-112">而是需要以下两种方法之一：</span><span class="sxs-lookup"><span data-stu-id="8ef59-112">It instead requires one of two techniques:</span></span>  
  
- <span data-ttu-id="8ef59-113">将 <xref:System.Windows.UIElement.AddHandler%2A> 方法与 `AddressOf` 运算符一起使用以引用事件处理程序实现。</span><span class="sxs-lookup"><span data-stu-id="8ef59-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
- <span data-ttu-id="8ef59-114">使用 `Handles` 关键字作为事件处理程序定义的一部分。</span><span class="sxs-lookup"><span data-stu-id="8ef59-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="8ef59-115">此处未显示此方法;请参阅[Visual Basic 和 WPF 事件处理](visual-basic-and-wpf-event-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="8ef59-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> <span data-ttu-id="8ef59-116">在最初分析的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页中添加事件处理程序要简单得多。</span><span class="sxs-lookup"><span data-stu-id="8ef59-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="8ef59-117">在要添加事件处理程序的对象元素中，添加一个与你要处理的事件的名称相匹配的属性。</span><span class="sxs-lookup"><span data-stu-id="8ef59-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="8ef59-118">然后，将该属性的值指定为在 "[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]" 页的代码隐藏文件中定义的事件处理程序方法的名称。</span><span class="sxs-lookup"><span data-stu-id="8ef59-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="8ef59-119">有关详细信息，请参阅[XAML 概述（WPF）](../../../desktop-wpf/fundamentals/xaml.md)或[路由事件概述](routed-events-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8ef59-119">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef59-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ef59-120">See also</span></span>

- [<span data-ttu-id="8ef59-121">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="8ef59-121">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="8ef59-122">帮助主题</span><span class="sxs-lookup"><span data-stu-id="8ef59-122">How-to Topics</span></span>](events-how-to-topics.md)
