---
title: 如何：使用 RectangleGeometry 定义矩形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 9c57f1536065af0bca1f3752179547daa502c066
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511636"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a><span data-ttu-id="8cd94-102">如何：使用 RectangleGeometry 定义矩形</span><span class="sxs-lookup"><span data-stu-id="8cd94-102">How to: Define a Rectangle Using a RectangleGeometry</span></span>
<span data-ttu-id="8cd94-103">此示例介绍了如何使用<xref:System.Windows.Media.RectangleGeometry>类，用于描述一个矩形。</span><span class="sxs-lookup"><span data-stu-id="8cd94-103">This example describes how to use the <xref:System.Windows.Media.RectangleGeometry> class to describe a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cd94-104">示例</span><span class="sxs-lookup"><span data-stu-id="8cd94-104">Example</span></span>  
 <span data-ttu-id="8cd94-105">下面的示例演示如何创建和呈现<xref:System.Windows.Media.RectangleGeometry>。</span><span class="sxs-lookup"><span data-stu-id="8cd94-105">The following example shows how to create and render a <xref:System.Windows.Media.RectangleGeometry>.</span></span>  <span data-ttu-id="8cd94-106">通过定义相对位置和矩形的尺寸<xref:System.Windows.Rect>结构。</span><span class="sxs-lookup"><span data-stu-id="8cd94-106">The relative position and the dimensions of the rectangle are defined by a <xref:System.Windows.Rect> structure.</span></span> <span data-ttu-id="8cd94-107">相对位置是`50,50`和高度和宽度均`25`创建一个正方形。</span><span class="sxs-lookup"><span data-stu-id="8cd94-107">The relative position is `50,50` and the height and the width are both `25` creating a square.</span></span> <span data-ttu-id="8cd94-108">与绘制矩形的内部<xref:System.Windows.Media.Brushes.LemonChiffon%2A>用来绘制画笔，它的轮廓<xref:System.Windows.Media.Brushes.Black%2A>笔画粗细为`1`。</span><span class="sxs-lookup"><span data-stu-id="8cd94-108">The rectangle's interior is painted with a <xref:System.Windows.Media.Brushes.LemonChiffon%2A> brush and its outline is painted with a <xref:System.Windows.Media.Brushes.Black%2A> stroke with a thickness of `1`.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 <span data-ttu-id="8cd94-109">![一个 RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span><span class="sxs-lookup"><span data-stu-id="8cd94-109">![A RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span></span>  
<span data-ttu-id="8cd94-110">RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="8cd94-110">RectangleGeometry</span></span>  
  
 <span data-ttu-id="8cd94-111">虽然此示例使用了<xref:System.Windows.Shapes.Path>元素来呈现<xref:System.Windows.Media.RectangleGeometry>，有许多其他方法来使用<xref:System.Windows.Media.RectangleGeometry>对象。</span><span class="sxs-lookup"><span data-stu-id="8cd94-111">Although this example used a <xref:System.Windows.Shapes.Path> element to render the <xref:System.Windows.Media.RectangleGeometry>, there are many other ways to use <xref:System.Windows.Media.RectangleGeometry> objects.</span></span> <span data-ttu-id="8cd94-112">例如，<xref:System.Windows.Media.RectangleGeometry>可用于指定<xref:System.Windows.UIElement.Clip%2A>的<xref:System.Windows.UIElement>或<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>的<xref:System.Windows.Media.GeometryDrawing>。</span><span class="sxs-lookup"><span data-stu-id="8cd94-112">For example, a <xref:System.Windows.Media.RectangleGeometry> can be used to specify the <xref:System.Windows.UIElement.Clip%2A> of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> of a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="8cd94-113">其他简单的几何类包括<xref:System.Windows.Media.LineGeometry>和<xref:System.Windows.Media.EllipseGeometry>。</span><span class="sxs-lookup"><span data-stu-id="8cd94-113">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="8cd94-114">这些几何形状，以及更复杂的也可以创建使用<xref:System.Windows.Media.PathGeometry>或<xref:System.Windows.Media.StreamGeometry>。</span><span class="sxs-lookup"><span data-stu-id="8cd94-114">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cd94-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="8cd94-115">See also</span></span>
- [<span data-ttu-id="8cd94-116">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="8cd94-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [<span data-ttu-id="8cd94-117">创建复合形状</span><span class="sxs-lookup"><span data-stu-id="8cd94-117">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)
- [<span data-ttu-id="8cd94-118">使用 PathGeometry 创建形状</span><span class="sxs-lookup"><span data-stu-id="8cd94-118">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
