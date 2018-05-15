---
title: 如何：使用多边形元素来绘制闭合形状
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 4105139e159783cf0197f4e56c82001835077cbf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="b9fed-102">如何：使用多边形元素来绘制闭合形状</span><span class="sxs-lookup"><span data-stu-id="b9fed-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="b9fed-103">此示例演示如何通过使用绘制闭合的形状<xref:System.Windows.Shapes.Polygon>元素。</span><span class="sxs-lookup"><span data-stu-id="b9fed-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="b9fed-104">若要绘制的闭合的形状，创建<xref:System.Windows.Shapes.Polygon>元素，并使用其<xref:System.Windows.Shapes.Polygon.Points%2A>属性指定的顶点的形状。</span><span class="sxs-lookup"><span data-stu-id="b9fed-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="b9fed-105">自动绘制连接的第一个和最后一个点线。</span><span class="sxs-lookup"><span data-stu-id="b9fed-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="b9fed-106">最后，指定<xref:System.Windows.Shapes.Shape.Fill%2A>、 <xref:System.Windows.Shapes.Shape.Stroke%2A>，和/或文件名。</span><span class="sxs-lookup"><span data-stu-id="b9fed-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9fed-107">示例</span><span class="sxs-lookup"><span data-stu-id="b9fed-107">Example</span></span>  
 <span data-ttu-id="b9fed-108">在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，点的有效语法是用空格分隔列表的以逗号分隔的 x 和 y 坐标对。</span><span class="sxs-lookup"><span data-stu-id="b9fed-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="b9fed-109">虽然本示例使用<xref:System.Windows.Controls.Canvas>来包含多边形，但是您可以使用多边形元素 （以及所有其他形状元素） 以及任何<xref:System.Windows.Controls.Panel>或<xref:System.Windows.Controls.Control>支持非文本内容。</span><span class="sxs-lookup"><span data-stu-id="b9fed-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="b9fed-110">此示例摘自更大的示例;有关完整的示例，请参阅[形状元素示例](http://go.microsoft.com/fwlink/?LinkID=160037)。</span><span class="sxs-lookup"><span data-stu-id="b9fed-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>
