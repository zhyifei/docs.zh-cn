---
title: 如何：设置元素的宽度属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: a8fdc7c6659eb33f948741145c0b2e100bb133e4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376840"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a><span data-ttu-id="52a6c-102">如何：设置元素的宽度属性</span><span class="sxs-lookup"><span data-stu-id="52a6c-102">How to: Set the Width Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="52a6c-103">示例</span><span class="sxs-lookup"><span data-stu-id="52a6c-103">Example</span></span>  
 <span data-ttu-id="52a6c-104">此示例中直观地显示差异中的四个宽度相关属性之间的呈现行为[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="52a6c-104">This example visually shows the differences in rendering behavior among the four width-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="52a6c-105"><xref:System.Windows.FrameworkElement>类公开描述的元素的宽度特征的四个属性。</span><span class="sxs-lookup"><span data-stu-id="52a6c-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the width characteristics of an element.</span></span> <span data-ttu-id="52a6c-106">这四个属性可能会发生冲突，并且当他们这样做，将优先的值确定，如下所示：<xref:System.Windows.FrameworkElement.MinWidth%2A>值将优先于<xref:System.Windows.FrameworkElement.MaxWidth%2A>值，后者又优先于<xref:System.Windows.FrameworkElement.Width%2A>值。</span><span class="sxs-lookup"><span data-stu-id="52a6c-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinWidth%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxWidth%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Width%2A> value.</span></span> <span data-ttu-id="52a6c-107">第四个属性， <xref:System.Windows.FrameworkElement.ActualWidth%2A>，是只读的并将报告由与布局过程的交互的实际宽度。</span><span class="sxs-lookup"><span data-stu-id="52a6c-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, is read-only, and reports the actual width as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="52a6c-108">以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]示例绘制<xref:System.Windows.Shapes.Rectangle>元素 (`rect1`) 的子级作为<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="52a6c-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="52a6c-109">可以更改的宽度属性<xref:System.Windows.Shapes.Rectangle>通过使用一系列<xref:System.Windows.Controls.ListBox>表示的属性值的元素<xref:System.Windows.FrameworkElement.MinWidth%2A>， <xref:System.Windows.FrameworkElement.MaxWidth%2A>，和<xref:System.Windows.FrameworkElement.Width%2A>。</span><span class="sxs-lookup"><span data-stu-id="52a6c-109">You can change the width properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, and <xref:System.Windows.FrameworkElement.Width%2A>.</span></span> <span data-ttu-id="52a6c-110">以这种方式，以可视化方式显示每个属性的优先级。</span><span class="sxs-lookup"><span data-stu-id="52a6c-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="52a6c-111">下面的代码隐藏示例处理事件的<xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>事件引发。</span><span class="sxs-lookup"><span data-stu-id="52a6c-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="52a6c-112">每个自定义方法将来自输入<xref:System.Windows.Controls.ListBox>，将值作为分析<xref:System.Double>，并将值应用于指定的宽度与相关属性。</span><span class="sxs-lookup"><span data-stu-id="52a6c-112">Each custom method takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified width-related property.</span></span> <span data-ttu-id="52a6c-113">宽度值也转换为字符串和写入到各种<xref:System.Windows.Controls.TextBlock>元素 （这些元素的定义不在所选的 XAML 所示）。</span><span class="sxs-lookup"><span data-stu-id="52a6c-113">The width values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="52a6c-114">有关完整示例，请参阅[宽度属性比较示例](https://go.microsoft.com/fwlink/?LinkID=160050)。</span><span class="sxs-lookup"><span data-stu-id="52a6c-114">For the complete sample, see [Width Properties Comparison Sample](https://go.microsoft.com/fwlink/?LinkID=160050).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52a6c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="52a6c-115">See also</span></span>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [<span data-ttu-id="52a6c-116">面板概述</span><span class="sxs-lookup"><span data-stu-id="52a6c-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="52a6c-117">设置元素的高度属性</span><span class="sxs-lookup"><span data-stu-id="52a6c-117">Set the Height Properties of an Element</span></span>](how-to-set-the-height-properties-of-an-element.md)
- [<span data-ttu-id="52a6c-118">宽度属性比较示例</span><span class="sxs-lookup"><span data-stu-id="52a6c-118">Width Properties Comparison Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160050)
