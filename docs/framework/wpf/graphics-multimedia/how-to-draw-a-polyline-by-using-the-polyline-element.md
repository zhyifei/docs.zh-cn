---
title: 如何：使用 Polyline 元素来绘制折线
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: c4aab17958180710c392491a27cc22fa006f8c5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688969"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="de133-102">如何：使用 Polyline 元素来绘制折线</span><span class="sxs-lookup"><span data-stu-id="de133-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="de133-103">此示例演示如何来绘制折线，这是通过使用一系列相互连接的直线，<xref:System.Windows.Shapes.Polyline>元素。</span><span class="sxs-lookup"><span data-stu-id="de133-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="de133-104">若要绘制折线，创建<xref:System.Windows.Shapes.Polyline>元素，并使用其<xref:System.Windows.Shapes.Polyline.Points%2A>属性指定形状顶点。</span><span class="sxs-lookup"><span data-stu-id="de133-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="de133-105">最后，使用<xref:System.Windows.Shapes.Shape.Stroke%2A>和<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>属性来描述线的折线轮廓，因为没有笔画行是不可见。</span><span class="sxs-lookup"><span data-stu-id="de133-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de133-106">因为<xref:System.Windows.Shapes.Polyline>元素不是闭合的形状，<xref:System.Windows.Shapes.Shape.Fill%2A>属性不起作用，即使你有意关闭形状轮廓。</span><span class="sxs-lookup"><span data-stu-id="de133-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="de133-107">若要创建具有一个闭合的形状<xref:System.Windows.Shapes.Shape.Fill%2A>，使用<xref:System.Windows.Shapes.Polygon>元素。</span><span class="sxs-lookup"><span data-stu-id="de133-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="de133-108">下面的示例绘制两个<xref:System.Windows.Shapes.Polyline>内的元素<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="de133-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de133-109">示例</span><span class="sxs-lookup"><span data-stu-id="de133-109">Example</span></span>  
 <span data-ttu-id="de133-110">在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，点的有效语法是以逗号分隔的 x 和 y 坐标对的空格分隔列表。</span><span class="sxs-lookup"><span data-stu-id="de133-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="de133-111">虽然此示例使用<xref:System.Windows.Controls.Canvas>来包含折线，但是您可以使用 polyline 元素 （和所有其他形状元素） 以及任何<xref:System.Windows.Controls.Panel>或<xref:System.Windows.Controls.Control>支持非文本内容。</span><span class="sxs-lookup"><span data-stu-id="de133-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="de133-112">此示例摘自一个更大的示例;有关完整示例，请参阅[形状元素示例](https://go.microsoft.com/fwlink/?LinkID=160037)。</span><span class="sxs-lookup"><span data-stu-id="de133-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de133-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="de133-113">See also</span></span>
- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="de133-114">形状元素示例</span><span class="sxs-lookup"><span data-stu-id="de133-114">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
- [<span data-ttu-id="de133-115">WPF 中的形状和基本绘图概述</span><span class="sxs-lookup"><span data-stu-id="de133-115">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
