---
title: 如何：处理路由事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], handling
- bubbling events [WPF]
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
ms.openlocfilehash: edb3d6724af89b7e85986c50b579084e3c4e5070
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211590"
---
# <a name="how-to-handle-a-routed-event"></a><span data-ttu-id="a03b6-102">如何：处理路由事件</span><span class="sxs-lookup"><span data-stu-id="a03b6-102">How to: Handle a Routed Event</span></span>
<span data-ttu-id="a03b6-103">本示例演示了浮升事件的工作原理，以及如何编写可处理路由事件数据的处理程序。</span><span class="sxs-lookup"><span data-stu-id="a03b6-103">This example shows how bubbling events work and how to write a handler that can process the routed event data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a03b6-104">示例</span><span class="sxs-lookup"><span data-stu-id="a03b6-104">Example</span></span>  
 <span data-ttu-id="a03b6-105">在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中，元素以元素树结构形式排列。</span><span class="sxs-lookup"><span data-stu-id="a03b6-105">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], elements are arranged in an element tree structure.</span></span> <span data-ttu-id="a03b6-106">父元素可以参与处理最初由元素树中的子元素引发的事件。</span><span class="sxs-lookup"><span data-stu-id="a03b6-106">The parent element can participate in the handling of events that are initially raised by child elements in the element tree.</span></span> <span data-ttu-id="a03b6-107">这都是因为事件路由。</span><span class="sxs-lookup"><span data-stu-id="a03b6-107">This is possible because of event routing.</span></span>  
  
 <span data-ttu-id="a03b6-108">路由事件通常遵循以下两个路由策略之一：浮升和隧道。</span><span class="sxs-lookup"><span data-stu-id="a03b6-108">Routed events typically follow one of two routing strategies, bubbling or tunneling.</span></span> <span data-ttu-id="a03b6-109">此示例重点介绍浮升事件，并使用<xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType>事件可显示路由的工作原理。</span><span class="sxs-lookup"><span data-stu-id="a03b6-109">This example focuses on the bubbling event and uses the <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> event to show how routing works.</span></span>  
  
 <span data-ttu-id="a03b6-110">下面的示例创建两个<xref:System.Windows.Controls.Button>控制，并使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]特性语法将事件处理程序附加到公用父元素，它在此示例中为<xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="a03b6-110">The following example creates two <xref:System.Windows.Controls.Button> controls and uses [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax to attach an event handler to a common parent element, which in this example is <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="a03b6-111">而不是将单个事件处理程序附加每个<xref:System.Windows.Controls.Button>子元素，该示例使用特性语法将附加到的事件处理程序<xref:System.Windows.Controls.StackPanel>父元素。</span><span class="sxs-lookup"><span data-stu-id="a03b6-111">Instead of attaching individual event handlers for each <xref:System.Windows.Controls.Button> child element, the example uses attribute syntax to attach the event handler to the <xref:System.Windows.Controls.StackPanel> parent element.</span></span> <span data-ttu-id="a03b6-112">此事件处理模式展示了如何使用事件路由技术来减少附加处理程序的元素数。</span><span class="sxs-lookup"><span data-stu-id="a03b6-112">This event-handling pattern shows how to use event routing as a technique for reducing the number of elements where a handler is attached.</span></span> <span data-ttu-id="a03b6-113">每个的所有浮升事件<xref:System.Windows.Controls.Button>通过父元素路由。</span><span class="sxs-lookup"><span data-stu-id="a03b6-113">All the bubbling events for each <xref:System.Windows.Controls.Button> route through the parent element.</span></span>  
  
 <span data-ttu-id="a03b6-114">请注意，在父<xref:System.Windows.Controls.StackPanel>元素中，<xref:System.Windows.Controls.Primitives.ButtonBase.Click>指定为该属性进行部分限定的命名的事件名称<xref:System.Windows.Controls.Button>类。</span><span class="sxs-lookup"><span data-stu-id="a03b6-114">Note that on the parent <xref:System.Windows.Controls.StackPanel> element, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event name specified as the attribute is partially qualified by naming the <xref:System.Windows.Controls.Button> class.</span></span> <span data-ttu-id="a03b6-115"><xref:System.Windows.Controls.Button>类是<xref:System.Windows.Controls.Primitives.ButtonBase>派生的类具有<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件在其成员列表中的。</span><span class="sxs-lookup"><span data-stu-id="a03b6-115">The <xref:System.Windows.Controls.Button> class is a <xref:System.Windows.Controls.Primitives.ButtonBase> derived class that has the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in its members listing.</span></span> <span data-ttu-id="a03b6-116">如果要处理的事件不在附加路由事件处理程序的元素的成员列表中，则有必要使用这种部分限定技术来附加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a03b6-116">This partial qualification technique for attaching an event handler is necessary if the event that is being handled does not exist in the members listing of the element where the routed event handler is attached.</span></span>  
  
 [!code-xaml[RoutedEventHandle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 <span data-ttu-id="a03b6-117">下面的示例处理<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件。</span><span class="sxs-lookup"><span data-stu-id="a03b6-117">The following example handles the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  <span data-ttu-id="a03b6-118">该示例会报告哪个元素处理事件以及哪个元素引发事件。</span><span class="sxs-lookup"><span data-stu-id="a03b6-118">The example reports which element handles the event and which element raises the event.</span></span> <span data-ttu-id="a03b6-119">用户单击任一按钮时都将执行事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a03b6-119">The event handler is executed when the user clicks either button.</span></span>  
  
 [!code-csharp[RoutedEventHandle#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="a03b6-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a03b6-120">See also</span></span>

- <xref:System.Windows.RoutedEvent>
- [<span data-ttu-id="a03b6-121">输入概述</span><span class="sxs-lookup"><span data-stu-id="a03b6-121">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="a03b6-122">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="a03b6-122">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="a03b6-123">帮助主题</span><span class="sxs-lookup"><span data-stu-id="a03b6-123">How-to Topics</span></span>](events-how-to-topics.md)
- [<span data-ttu-id="a03b6-124">XAML 语法详述</span><span class="sxs-lookup"><span data-stu-id="a03b6-124">XAML Syntax In Detail</span></span>](xaml-syntax-in-detail.md)
