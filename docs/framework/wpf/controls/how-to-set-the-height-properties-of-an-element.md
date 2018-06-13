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
ms.openlocfilehash: 467cd57c728be015fb9eb9b974ca6e81e4fd7754
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554839"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a><span data-ttu-id="c1e30-102">如何：设置元素的高度属性</span><span class="sxs-lookup"><span data-stu-id="c1e30-102">How to: Set the Height Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="c1e30-103">示例</span><span class="sxs-lookup"><span data-stu-id="c1e30-103">Example</span></span>  
 <span data-ttu-id="c1e30-104">此示例以可视方式显示在之间的四个高度相关的属性中的呈现行为的差异[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c1e30-104">This example visually shows the differences in rendering behavior among the four height-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="c1e30-105"><xref:System.Windows.FrameworkElement>类公开描述的元素的高度特征的四个属性。</span><span class="sxs-lookup"><span data-stu-id="c1e30-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the height characteristics of an element.</span></span> <span data-ttu-id="c1e30-106">这四个属性可能会发生冲突，并且当他们执行，将优先的值确定，如下所示：<xref:System.Windows.FrameworkElement.MinHeight%2A>值优先于<xref:System.Windows.FrameworkElement.MaxHeight%2A>值，后者又优先于<xref:System.Windows.FrameworkElement.Height%2A>值。</span><span class="sxs-lookup"><span data-stu-id="c1e30-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinHeight%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxHeight%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Height%2A> value.</span></span> <span data-ttu-id="c1e30-107">第四个属性， <xref:System.Windows.FrameworkElement.ActualHeight%2A>，是只读的并将报告由与在布局流程交互的实际高度。</span><span class="sxs-lookup"><span data-stu-id="c1e30-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, is read-only, and reports the actual height as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="c1e30-108">以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]示例绘制<xref:System.Windows.Shapes.Rectangle>元素 (`rect1`) 的子级<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="c1e30-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="c1e30-109">你可以更改的高度属性<xref:System.Windows.Shapes.Rectangle>通过使用一系列<xref:System.Windows.Controls.ListBox>表示的属性值的元素<xref:System.Windows.FrameworkElement.MinHeight%2A>， <xref:System.Windows.FrameworkElement.MaxHeight%2A>，和<xref:System.Windows.FrameworkElement.Height%2A>。</span><span class="sxs-lookup"><span data-stu-id="c1e30-109">You can change the height properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="c1e30-110">这种方式，可以直观地显示每个属性的优先级。</span><span class="sxs-lookup"><span data-stu-id="c1e30-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="c1e30-111">下面的代码隐藏示例处理事件的<xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>事件引发。</span><span class="sxs-lookup"><span data-stu-id="c1e30-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="c1e30-112">每个处理程序将使用从输入<xref:System.Windows.Controls.ListBox>，将值作为分析<xref:System.Double>，并将值应用于指定高度相关的属性。</span><span class="sxs-lookup"><span data-stu-id="c1e30-112">Each handler takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified height-related property.</span></span> <span data-ttu-id="c1e30-113">高度值也是转换为字符串，并且写入到各种<xref:System.Windows.Controls.TextBlock>（这些元素的定义未显示在所选 XAML） 的元素。</span><span class="sxs-lookup"><span data-stu-id="c1e30-113">The height values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="c1e30-114">有关完整的示例，请参阅[高度属性示例](http://go.microsoft.com/fwlink/?LinkID=159993)。</span><span class="sxs-lookup"><span data-stu-id="c1e30-114">For the complete sample, see [Height Properties Sample](http://go.microsoft.com/fwlink/?LinkID=159993).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1e30-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1e30-115">See Also</span></span>  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.ActualHeight%2A>  
 <xref:System.Windows.FrameworkElement.MaxHeight%2A>  
 <xref:System.Windows.FrameworkElement.MinHeight%2A>  
 <xref:System.Windows.FrameworkElement.Height%2A>  
 [<span data-ttu-id="c1e30-116">设置元素的宽度属性</span><span class="sxs-lookup"><span data-stu-id="c1e30-116">Set the Width Properties of an Element</span></span>](../../../../docs/framework/wpf/controls/how-to-set-the-width-properties-of-an-element.md)  
 [<span data-ttu-id="c1e30-117">面板概述</span><span class="sxs-lookup"><span data-stu-id="c1e30-117">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="c1e30-118">高度属性示例</span><span class="sxs-lookup"><span data-stu-id="c1e30-118">Height Properties Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159993)
