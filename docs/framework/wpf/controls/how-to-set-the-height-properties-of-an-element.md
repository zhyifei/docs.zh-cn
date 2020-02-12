---
title: 如何：设置元素的高度属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: 6500af3c637092820e538d79894d600d617953bf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124281"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a><span data-ttu-id="80b2b-102">如何：设置元素的高度属性</span><span class="sxs-lookup"><span data-stu-id="80b2b-102">How to: Set the Height Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="80b2b-103">示例</span><span class="sxs-lookup"><span data-stu-id="80b2b-103">Example</span></span>  
 <span data-ttu-id="80b2b-104">此示例直观地显示了 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]中四个与高度相关的属性之间的呈现行为差异。</span><span class="sxs-lookup"><span data-stu-id="80b2b-104">This example visually shows the differences in rendering behavior among the four height-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="80b2b-105"><xref:System.Windows.FrameworkElement> 类公开了四个属性，这些属性描述元素的高度特性。</span><span class="sxs-lookup"><span data-stu-id="80b2b-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the height characteristics of an element.</span></span> <span data-ttu-id="80b2b-106">这四个属性可能会发生冲突，当发生这种情况时，将按如下所示确定优先级值： <xref:System.Windows.FrameworkElement.MinHeight%2A> 值优先于 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 值，而后者又优先于 <xref:System.Windows.FrameworkElement.Height%2A> 值。</span><span class="sxs-lookup"><span data-stu-id="80b2b-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinHeight%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxHeight%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Height%2A> value.</span></span> <span data-ttu-id="80b2b-107">第四个属性 <xref:System.Windows.FrameworkElement.ActualHeight%2A>为只读，并报告与布局过程的交互确定的实际高度。</span><span class="sxs-lookup"><span data-stu-id="80b2b-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, is read-only, and reports the actual height as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="80b2b-108">以下 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 示例将 <xref:System.Windows.Shapes.Rectangle> 元素（`rect1`）绘制为 <xref:System.Windows.Controls.Canvas>的子项。</span><span class="sxs-lookup"><span data-stu-id="80b2b-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="80b2b-109">您可以通过使用一系列表示 <xref:System.Windows.FrameworkElement.MinHeight%2A>、<xref:System.Windows.FrameworkElement.MaxHeight%2A>和 <xref:System.Windows.FrameworkElement.Height%2A>属性值的 <xref:System.Windows.Controls.ListBox> 元素，来更改 <xref:System.Windows.Shapes.Rectangle> 的高度属性。</span><span class="sxs-lookup"><span data-stu-id="80b2b-109">You can change the height properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="80b2b-110">通过这种方式，可直观显示每个属性的优先级。</span><span class="sxs-lookup"><span data-stu-id="80b2b-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="80b2b-111">下面的代码隐藏示例处理 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 事件引发的事件。</span><span class="sxs-lookup"><span data-stu-id="80b2b-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="80b2b-112">每个处理程序都从 <xref:System.Windows.Controls.ListBox>获取输入，将值分析为 <xref:System.Double>，并将值应用于指定的与高度相关的属性。</span><span class="sxs-lookup"><span data-stu-id="80b2b-112">Each handler takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified height-related property.</span></span> <span data-ttu-id="80b2b-113">高度值还会转换为字符串并写入各种 <xref:System.Windows.Controls.TextBlock> 元素（所选 XAML 中不显示这些元素的定义）。</span><span class="sxs-lookup"><span data-stu-id="80b2b-113">The height values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="80b2b-114">有关完整示例，请参阅[高度属性示例](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)。</span><span class="sxs-lookup"><span data-stu-id="80b2b-114">For the complete sample, see [Height Properties Sample](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b2b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80b2b-115">See also</span></span>

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [<span data-ttu-id="80b2b-116">设置元素的宽度属性</span><span class="sxs-lookup"><span data-stu-id="80b2b-116">Set the Width Properties of an Element</span></span>](how-to-set-the-width-properties-of-an-element.md)
- [<span data-ttu-id="80b2b-117">面板概述</span><span class="sxs-lookup"><span data-stu-id="80b2b-117">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="80b2b-118">Height 属性示例</span><span class="sxs-lookup"><span data-stu-id="80b2b-118">Height Properties Sample</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)
