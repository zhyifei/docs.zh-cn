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
ms.openlocfilehash: 10f8e0899e61d5d54589c910bdcbcd92d8ee947c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777060"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="c3a3c-102">如何：使用代码添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="c3a3c-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="c3a3c-103">此示例演示如何使用代码将事件处理程序添加到元素。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="c3a3c-104">如果你想要添加到事件处理程序[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]已加载元素，并包含的元素的标记页面，则必须添加使用代码处理程序。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="c3a3c-105">或者，如果您正在生成的应用程序完全使用代码而没有声明使用任何元素的元素树[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，可以调用特定方法来将事件处理程序添加到构造的元素树。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3a3c-106">示例</span><span class="sxs-lookup"><span data-stu-id="c3a3c-106">Example</span></span>  
 <span data-ttu-id="c3a3c-107">下面的示例添加一个新<xref:System.Windows.Controls.Button>到现有的页面中最初定义[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="c3a3c-108">代码隐藏文件实现事件处理程序方法，然后将该方法添加为新的事件处理程序上<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="c3a3c-109">C#的示例使用`+=`运算符分配的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="c3a3c-110">这是用于分配中的处理程序的相同运算符[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]事件处理模型。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-110">This is the same operator that is used to assign a handler in the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event handling model.</span></span> <span data-ttu-id="c3a3c-111">作为一种方式添加事件处理程序的情况下，Microsoft Visual Basic 不支持此运算符。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="c3a3c-112">相反，它要求两种技术之一：</span><span class="sxs-lookup"><span data-stu-id="c3a3c-112">It instead requires one of two techniques:</span></span>  
  
- <span data-ttu-id="c3a3c-113">使用<xref:System.Windows.UIElement.AddHandler%2A>方法，一起`AddressOf`运算符，以引用的事件处理程序实现。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
- <span data-ttu-id="c3a3c-114">使用`Handles`关键字作为事件处理程序定义的一部分。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="c3a3c-115">此处; 未显示这种方法请参阅[Visual Basic 和 WPF 事件处理](visual-basic-and-wpf-event-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  <span data-ttu-id="c3a3c-116">添加事件处理程序在最初分析[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]页是要简单得多。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="c3a3c-117">在对象元素中你想要添加事件处理程序，将添加匹配你想要处理的事件名称的属性。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="c3a3c-118">然后该属性的值指定的代码隐藏文件中定义的事件处理程序方法的名称为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]页。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="c3a3c-119">有关详细信息，请参阅[XAML 概述 (WPF)](xaml-overview-wpf.md)或[路由事件概述](routed-events-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c3a3c-119">For more information, see [XAML Overview (WPF)](xaml-overview-wpf.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3a3c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3a3c-120">See also</span></span>

- [<span data-ttu-id="c3a3c-121">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="c3a3c-121">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="c3a3c-122">帮助主题</span><span class="sxs-lookup"><span data-stu-id="c3a3c-122">How-to Topics</span></span>](events-how-to-topics.md)
