---
title: 如何：使 UIElement 呈现为透明或半透明
ms.date: 03/30/2017
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
ms.openlocfilehash: 7bf79848edb84a5bd93d1196fbe0b3196d159ff3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545306"
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a><span data-ttu-id="50e87-102">如何：使 UIElement 呈现为透明或半透明</span><span class="sxs-lookup"><span data-stu-id="50e87-102">How to: Make a UIElement Transparent or Semi-Transparent</span></span>
<span data-ttu-id="50e87-103">此示例演示如何使<xref:System.Windows.UIElement>透明或不完全透明。</span><span class="sxs-lookup"><span data-stu-id="50e87-103">This example shows how to make a <xref:System.Windows.UIElement> transparent or semi-transparent.</span></span> <span data-ttu-id="50e87-104">若要使元素透明或不完全透明，你将设置其<xref:System.Windows.UIElement.Opacity%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="50e87-104">To make an element transparent or semi-transparent, you set its <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="50e87-105">值为`0.0`使元素完全透明，而值`1.0`使元素完全不透明。</span><span class="sxs-lookup"><span data-stu-id="50e87-105">A value of `0.0` makes the element completely transparent, while a value of `1.0` makes the element completely opaque.</span></span> <span data-ttu-id="50e87-106">值为`0.5`使元素 50%不透明，依次类推。</span><span class="sxs-lookup"><span data-stu-id="50e87-106">A value of `0.5` makes the element 50% opaque, and so on.</span></span> <span data-ttu-id="50e87-107">元素的<xref:System.Windows.UIElement.Opacity%2A>设置为`1.0`默认情况下。</span><span class="sxs-lookup"><span data-stu-id="50e87-107">An element's <xref:System.Windows.UIElement.Opacity%2A> is set to `1.0` by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50e87-108">示例</span><span class="sxs-lookup"><span data-stu-id="50e87-108">Example</span></span>  
 <span data-ttu-id="50e87-109">下面的示例设置<xref:System.Windows.UIElement.Opacity%2A>到按钮的`0.25`，使它和其内容 （在这种情况下，该按钮的文本） 25%不透明。</span><span class="sxs-lookup"><span data-stu-id="50e87-109">The following example sets the <xref:System.Windows.UIElement.Opacity%2A> of a button to `0.25`, making it and its contents (in this case, the button's text) 25% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 <span data-ttu-id="50e87-110">如果元素的内容有其自己<xref:System.Windows.UIElement.Opacity%2A>设置，这些值乘以包含元素<xref:System.Windows.UIElement.Opacity%2A>。</span><span class="sxs-lookup"><span data-stu-id="50e87-110">If an element's contents have their own <xref:System.Windows.UIElement.Opacity%2A> settings, those values are multiplied against the containing elements <xref:System.Windows.UIElement.Opacity%2A>.</span></span>  
  
 <span data-ttu-id="50e87-111">下面的示例设置按钮的<xref:System.Windows.UIElement.Opacity%2A>到`0.25`，和<xref:System.Windows.UIElement.Opacity%2A>的<xref:System.Windows.Controls.Image>控件中的按钮为与包含`0.5`。</span><span class="sxs-lookup"><span data-stu-id="50e87-111">The following example sets a button's <xref:System.Windows.UIElement.Opacity%2A> to `0.25`, and the <xref:System.Windows.UIElement.Opacity%2A> of an <xref:System.Windows.Controls.Image> control contained with in the button to `0.5`.</span></span> <span data-ttu-id="50e87-112">因此，图像将显示 12.5%不透明： 0.25 \* 0.5 = 0.125。</span><span class="sxs-lookup"><span data-stu-id="50e87-112">As a result, the image appears 12.5% opaque: 0.25 \* 0.5 = 0.125.</span></span>  
  
 [!code-xaml[brushsamples_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 <span data-ttu-id="50e87-113">若要控制元素的不透明度的另一个方法是设置的不透明度<xref:System.Windows.Media.Brush>绘制元素。</span><span class="sxs-lookup"><span data-stu-id="50e87-113">Another way to control the opacity of an element is to set the opacity of the <xref:System.Windows.Media.Brush> that paints the element.</span></span> <span data-ttu-id="50e87-114">这种方法，您可以有选择性地修改元素，某些部分的不透明度，并通过使用元素的提供性能优势<xref:System.Windows.UIElement.Opacity%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="50e87-114">This approach enables you to selectively alter the opacity of portions of an element, and provides performance benefits over using the element's <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="50e87-115">下面的示例设置<xref:System.Windows.Media.Brush.Opacity%2A>的<xref:System.Windows.Media.SolidColorBrush>用于绘制按钮的<xref:System.Windows.Controls.Control.Background%2A>设置为`0.25`。</span><span class="sxs-lookup"><span data-stu-id="50e87-115">The following example sets the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush> used to paint the button's <xref:System.Windows.Controls.Control.Background%2A> is set to `0.25`.</span></span> <span data-ttu-id="50e87-116">因此，画笔的背景为 25%不透明的但其内容 （该按钮的文本） 仍保留 100%不透明。</span><span class="sxs-lookup"><span data-stu-id="50e87-116">As a result, the brush's background is 25% opaque, but its contents (the button's text) remain 100% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 <span data-ttu-id="50e87-117">您也可以控制单个画笔颜色的不透明度。</span><span class="sxs-lookup"><span data-stu-id="50e87-117">You may also control the opacity of individual colors within a brush.</span></span> <span data-ttu-id="50e87-118">有关颜色和画笔的详细信息，请参阅[使用纯色和渐变概述绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="50e87-118">For more information about colors and brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span> <span data-ttu-id="50e87-119">有关展示如何进行动画处理的元素的不透明度的示例，请参阅[动画元素或画笔的不透明度](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md)。</span><span class="sxs-lookup"><span data-stu-id="50e87-119">For an example showing how to animate an element's opacity, see [Animate the Opacity of an Element or Brush](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span></span>
