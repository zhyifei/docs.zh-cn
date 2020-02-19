---
title: 如何：绘制椭圆或圆
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: 5f17615da4907cba6e25b68f2f934602c2f8a390
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452917"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="2bb63-102">如何：绘制椭圆或圆</span><span class="sxs-lookup"><span data-stu-id="2bb63-102">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="2bb63-103">此示例演示如何使用 <xref:System.Windows.Shapes.Ellipse> 元素来绘制椭圆和圆圈。</span><span class="sxs-lookup"><span data-stu-id="2bb63-103">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="2bb63-104">若要绘制一个椭圆，请创建一个 <xref:System.Windows.Shapes.Ellipse> 元素，并指定其 <xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A>。</span><span class="sxs-lookup"><span data-stu-id="2bb63-104">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="2bb63-105">使用其 <xref:System.Windows.Shapes.Shape.Fill%2A> 属性指定用来绘制椭圆内部的 <xref:System.Windows.Media.Brush>。</span><span class="sxs-lookup"><span data-stu-id="2bb63-105">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="2bb63-106">使用其 <xref:System.Windows.Shapes.Shape.Stroke%2A> 属性指定用来绘制椭圆轮廓的 <xref:System.Windows.Media.Brush>。</span><span class="sxs-lookup"><span data-stu-id="2bb63-106">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="2bb63-107"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 属性指定椭圆轮廓的粗细。</span><span class="sxs-lookup"><span data-stu-id="2bb63-107">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="2bb63-108">若要绘制一个圆，请使 <xref:System.Windows.Shapes.Ellipse> 元素的 <xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A> 彼此相等。</span><span class="sxs-lookup"><span data-stu-id="2bb63-108">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="2bb63-109">下面的示例在一个 <xref:System.Windows.Controls.Canvas>中绘制四个 <xref:System.Windows.Shapes.Ellipse> 元素。</span><span class="sxs-lookup"><span data-stu-id="2bb63-109">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bb63-110">示例</span><span class="sxs-lookup"><span data-stu-id="2bb63-110">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="2bb63-111">虽然此示例使用 <xref:System.Windows.Controls.Canvas> 来包含省略号，但你可以将椭圆形元素（和所有其他形状元素）与支持非文本内容的任何 <xref:System.Windows.Controls.Panel> 或 <xref:System.Windows.Controls.Control> 一起使用。</span><span class="sxs-lookup"><span data-stu-id="2bb63-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="2bb63-112">此示例摘自一个更大的示例;有关完整示例，请参阅[形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)。</span><span class="sxs-lookup"><span data-stu-id="2bb63-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bb63-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bb63-113">See also</span></span>

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="2bb63-114">形状元素示例</span><span class="sxs-lookup"><span data-stu-id="2bb63-114">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
