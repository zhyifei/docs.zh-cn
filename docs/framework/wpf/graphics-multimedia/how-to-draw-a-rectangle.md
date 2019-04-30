---
title: 如何：绘制矩形
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 261026b994b432565928b38ff1657115ff7cbe4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947623"
---
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="0ccc0-102">如何：绘制矩形</span><span class="sxs-lookup"><span data-stu-id="0ccc0-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="0ccc0-103">此示例演示如何使用来绘制一个矩形<xref:System.Windows.Shapes.Rectangle>元素。</span><span class="sxs-lookup"><span data-stu-id="0ccc0-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="0ccc0-104">若要绘制一个矩形，创建<xref:System.Windows.Shapes.Rectangle>元素，并指定其<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>。</span><span class="sxs-lookup"><span data-stu-id="0ccc0-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="0ccc0-105">若要绘制的矩形的内部，设置其<xref:System.Windows.Shapes.Shape.Fill%2A>。</span><span class="sxs-lookup"><span data-stu-id="0ccc0-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="0ccc0-106">若要为矩形轮廓，使用其<xref:System.Windows.Shapes.Shape.Stroke%2A>和<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0ccc0-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="0ccc0-107">若要绘制矩形圆角中，指定可选<xref:System.Windows.Shapes.Rectangle.RadiusX%2A>和<xref:System.Windows.Shapes.Rectangle.RadiusY%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0ccc0-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="0ccc0-108"><xref:System.Windows.Shapes.Rectangle.RadiusX%2A>和<xref:System.Windows.Shapes.Rectangle.RadiusY%2A>属性设置用于圆角化矩形角的椭圆的 x 轴和 y 轴半径。</span><span class="sxs-lookup"><span data-stu-id="0ccc0-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="0ccc0-109">在以下示例中，两个<xref:System.Windows.Shapes.Rectangle>元素绘制<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="0ccc0-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="0ccc0-110">第一个矩形具有<xref:System.Windows.Media.Brushes.Blue%2A>内部。</span><span class="sxs-lookup"><span data-stu-id="0ccc0-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="0ccc0-111">第二个矩形具有<xref:System.Windows.Media.Brushes.Blue%2A>内部，<xref:System.Windows.Media.Brushes.Black%2A>大纲和圆的角。</span><span class="sxs-lookup"><span data-stu-id="0ccc0-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ccc0-112">示例</span><span class="sxs-lookup"><span data-stu-id="0ccc0-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="0ccc0-113">虽然此示例使用<xref:System.Windows.Controls.Canvas>来包含矩形，但是您可以使用矩形元素 （和所有其他形状元素） 以及任何<xref:System.Windows.Controls.Panel>或<xref:System.Windows.Controls.Control>支持非文本内容。</span><span class="sxs-lookup"><span data-stu-id="0ccc0-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="0ccc0-114">事实上，矩形是特别有用的某些部分提供背景<xref:System.Windows.Controls.Grid>面板。</span><span class="sxs-lookup"><span data-stu-id="0ccc0-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="0ccc0-115">有关示例，请参阅[表概述](../advanced/table-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0ccc0-115">For an example, see the [Table Overview](../advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="0ccc0-116">此示例摘自一个更大的示例;有关完整示例，请参阅[形状元素示例](https://go.microsoft.com/fwlink/?LinkID=160037)。</span><span class="sxs-lookup"><span data-stu-id="0ccc0-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ccc0-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ccc0-117">See also</span></span>

- <xref:System.Windows.Shapes.Rectangle>
- [<span data-ttu-id="0ccc0-118">形状元素示例</span><span class="sxs-lookup"><span data-stu-id="0ccc0-118">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
- [<span data-ttu-id="0ccc0-119">WPF 中的形状和基本绘图概述</span><span class="sxs-lookup"><span data-stu-id="0ccc0-119">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="0ccc0-120">表概述</span><span class="sxs-lookup"><span data-stu-id="0ccc0-120">Table Overview</span></span>](../advanced/table-overview.md)
