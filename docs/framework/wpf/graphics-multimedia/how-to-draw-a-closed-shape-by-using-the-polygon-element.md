---
title: 如何：使用多边形元素来绘制闭合形状
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 324a5623ee658789b8600a43a89ce26cab7cd6cd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452969"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="0e8f5-102">如何：使用多边形元素来绘制闭合形状</span><span class="sxs-lookup"><span data-stu-id="0e8f5-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="0e8f5-103">此示例演示如何使用 <xref:System.Windows.Shapes.Polygon> 元素绘制闭合形状。</span><span class="sxs-lookup"><span data-stu-id="0e8f5-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="0e8f5-104">若要绘制闭合形状，请创建 <xref:System.Windows.Shapes.Polygon> 元素，并使用其 <xref:System.Windows.Shapes.Polygon.Points%2A> 属性指定形状的顶点。</span><span class="sxs-lookup"><span data-stu-id="0e8f5-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="0e8f5-105">将自动绘制一条线，用于连接第一个点和最后一个点。</span><span class="sxs-lookup"><span data-stu-id="0e8f5-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="0e8f5-106">最后，指定 <xref:System.Windows.Shapes.Shape.Fill%2A>和/或 <xref:System.Windows.Shapes.Shape.Stroke%2A>。</span><span class="sxs-lookup"><span data-stu-id="0e8f5-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e8f5-107">示例</span><span class="sxs-lookup"><span data-stu-id="0e8f5-107">Example</span></span>  
 <span data-ttu-id="0e8f5-108">在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中，点的有效语法为以空格分隔的、以逗号分隔的 x 和 y 坐标对的列表。</span><span class="sxs-lookup"><span data-stu-id="0e8f5-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="0e8f5-109">尽管该示例使用了一个包含多边形的 <xref:System.Windows.Controls.Canvas>，但您可以使用任何支持非文本内容的 <xref:System.Windows.Controls.Panel> 或 <xref:System.Windows.Controls.Control> 的多边形元素（以及其他所有形状元素）。</span><span class="sxs-lookup"><span data-stu-id="0e8f5-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="0e8f5-110">此示例摘自一个更大的示例;有关完整示例，请参阅[形状元素示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)。</span><span class="sxs-lookup"><span data-stu-id="0e8f5-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>
