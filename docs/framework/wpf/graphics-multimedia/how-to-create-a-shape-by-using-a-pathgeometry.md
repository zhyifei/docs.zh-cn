---
title: "如何：使用 PathGeometry 创建形状"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 784a8df792ca4dc05e36f5b7e9ec93b02e0e639f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="29f9a-102">如何：使用 PathGeometry 创建形状</span><span class="sxs-lookup"><span data-stu-id="29f9a-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="29f9a-103">此示例演示如何创建形状使用<xref:System.Windows.Media.PathGeometry>类。</span><span class="sxs-lookup"><span data-stu-id="29f9a-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="29f9a-104"><xref:System.Windows.Media.PathGeometry>对象包括一个或多个<xref:System.Windows.Media.PathFigure>对象; 每个<xref:System.Windows.Media.PathFigure>表示不同的"图"或形状。</span><span class="sxs-lookup"><span data-stu-id="29f9a-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="29f9a-105">每个<xref:System.Windows.Media.PathFigure>本身由一个或多个<xref:System.Windows.Media.PathSegment>对象，每个表示连接的部分图或形状。</span><span class="sxs-lookup"><span data-stu-id="29f9a-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="29f9a-106">段类型包括<xref:System.Windows.Media.LineSegment>， <xref:System.Windows.Media.ArcSegment>，和<xref:System.Windows.Media.BezierSegment>。</span><span class="sxs-lookup"><span data-stu-id="29f9a-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29f9a-107">示例</span><span class="sxs-lookup"><span data-stu-id="29f9a-107">Example</span></span>  
 <span data-ttu-id="29f9a-108">下面的示例使用<xref:System.Windows.Media.PathGeometry>从而形成一个三角形。</span><span class="sxs-lookup"><span data-stu-id="29f9a-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="29f9a-109"><xref:System.Windows.Media.PathGeometry>使用显示<xref:System.Windows.Shapes.Path>元素。</span><span class="sxs-lookup"><span data-stu-id="29f9a-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="29f9a-110">下图显示在上一个示例中创建的形状。</span><span class="sxs-lookup"><span data-stu-id="29f9a-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="29f9a-111">![一个 PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="29f9a-111">![A PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="29f9a-112">使用一个 PathGeometry 创建一个三角形</span><span class="sxs-lookup"><span data-stu-id="29f9a-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="29f9a-113">前面的示例演示如何创建一个相对简单形状上，一个三角形。</span><span class="sxs-lookup"><span data-stu-id="29f9a-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="29f9a-114">A<xref:System.Windows.Media.PathGeometry>还用于创建更复杂的图形，包括弧线和曲线。</span><span class="sxs-lookup"><span data-stu-id="29f9a-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="29f9a-115">有关示例，请参阅[创建一条椭圆弧](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)，[创建三次方贝塞尔曲线](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)，和[创建二次贝塞尔曲线](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)。</span><span class="sxs-lookup"><span data-stu-id="29f9a-115">For examples, see [Create an Elliptical Arc](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="29f9a-116">此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](http://go.microsoft.com/fwlink/?LinkID=159989)。</span><span class="sxs-lookup"><span data-stu-id="29f9a-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29f9a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="29f9a-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [<span data-ttu-id="29f9a-118">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="29f9a-118">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="29f9a-119">几何图形示例</span><span class="sxs-lookup"><span data-stu-id="29f9a-119">Geometries Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159989)
