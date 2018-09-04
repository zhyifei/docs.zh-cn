---
title: 如何：使用 PathGeometry 创建形状
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: 4c9cd7a1af921a0a547c7dec3afc5f69b29e6aed
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43553942"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="9df75-102">如何：使用 PathGeometry 创建形状</span><span class="sxs-lookup"><span data-stu-id="9df75-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="9df75-103">此示例演示如何使用创建形状<xref:System.Windows.Media.PathGeometry>类。</span><span class="sxs-lookup"><span data-stu-id="9df75-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="9df75-104"><xref:System.Windows.Media.PathGeometry> 对象组成的一个或多个<xref:System.Windows.Media.PathFigure>对象; 每个<xref:System.Windows.Media.PathFigure>表示不同"图"或形状。</span><span class="sxs-lookup"><span data-stu-id="9df75-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="9df75-105">每个<xref:System.Windows.Media.PathFigure>本身由一个或多个<xref:System.Windows.Media.PathSegment>对象，每个资源表示图或形状的一个连接的部分。</span><span class="sxs-lookup"><span data-stu-id="9df75-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="9df75-106">线段的类型包括<xref:System.Windows.Media.LineSegment>， <xref:System.Windows.Media.ArcSegment>，和<xref:System.Windows.Media.BezierSegment>。</span><span class="sxs-lookup"><span data-stu-id="9df75-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9df75-107">示例</span><span class="sxs-lookup"><span data-stu-id="9df75-107">Example</span></span>  
 <span data-ttu-id="9df75-108">下面的示例使用<xref:System.Windows.Media.PathGeometry>进而形成一个三角形。</span><span class="sxs-lookup"><span data-stu-id="9df75-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="9df75-109"><xref:System.Windows.Media.PathGeometry>将显示使用<xref:System.Windows.Shapes.Path>元素。</span><span class="sxs-lookup"><span data-stu-id="9df75-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="9df75-110">下图显示在上一个示例中创建的形状。</span><span class="sxs-lookup"><span data-stu-id="9df75-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="9df75-111">![PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="9df75-111">![A PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="9df75-112">使用 PathGeometry 创建一个三角形</span><span class="sxs-lookup"><span data-stu-id="9df75-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="9df75-113">前面的示例介绍了如何创建一个相对简单的形状，一个三角形。</span><span class="sxs-lookup"><span data-stu-id="9df75-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="9df75-114">一个<xref:System.Windows.Media.PathGeometry>还可用于创建更复杂的形状，包括弧线和曲线。</span><span class="sxs-lookup"><span data-stu-id="9df75-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="9df75-115">有关示例，请参阅[创建椭圆弧](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)，[创建三次方贝塞尔曲线](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)，并[创建二次贝塞尔曲线](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)。</span><span class="sxs-lookup"><span data-stu-id="9df75-115">For examples, see [Create an Elliptical Arc](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="9df75-116">此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](https://go.microsoft.com/fwlink/?LinkID=159989)。</span><span class="sxs-lookup"><span data-stu-id="9df75-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9df75-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="9df75-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [<span data-ttu-id="9df75-118">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="9df75-118">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="9df75-119">几何图形示例</span><span class="sxs-lookup"><span data-stu-id="9df75-119">Geometries Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159989)
