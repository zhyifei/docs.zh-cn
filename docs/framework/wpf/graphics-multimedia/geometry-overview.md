---
title: "Geometry 概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometry classes [WPF]
- graphics [WPF], geometry classes
ms.assetid: 9fba8934-98b7-4af6-82f6-f4ef887f963a
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e58e3ea00a00b24e476fd158beb3b0515e607f9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="geometry-overview"></a>Geometry 概述
本概述介绍如何使用[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<xref:System.Windows.Media.Geometry>类来描述形状。 本主题还形成了鲜明对比之间的差异<xref:System.Windows.Media.Geometry>对象和<xref:System.Windows.Shapes.Shape>元素。  
  
  
<a name="wcpsdk_graphics_geometry_introduction"></a>   
## <a name="what-is-a-geometry"></a>什么是 Geometry？  
 <xref:System.Windows.Media.Geometry>类和类从中派生，如<xref:System.Windows.Media.EllipseGeometry>， <xref:System.Windows.Media.PathGeometry>，和<xref:System.Windows.Media.CombinedGeometry>，使你可以描述的二维形状的几何图形。 这些几何描述具有许多用途，例如定义要绘制到屏幕的形状或定义命中测试和剪裁区域。 甚至可以使用几何定义动画路径。  
  
 <xref:System.Windows.Media.Geometry>对象可以是简单，，例如矩形和圆形或复合，创建两个或多个几何对象。  可以通过创建更复杂的几何图形<xref:System.Windows.Media.PathGeometry>和<xref:System.Windows.Media.StreamGeometry>类，使你可以描述弧线和曲线。  
  
 因为<xref:System.Windows.Media.Geometry>是一种<xref:System.Windows.Freezable>，<xref:System.Windows.Media.Geometry>对象提供几个特殊功能： 它们可以声明为[资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)、 多个对象，进行只读的以提高性能，克隆，之间共享和设为线程安全。 有关提供的不同功能的详细信息<xref:System.Windows.Freezable>对象，请参阅[可冻结对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)。  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>   
## <a name="geometries-vs-shapes"></a>几何与形状  
 <xref:System.Windows.Media.Geometry>和<xref:System.Windows.Shapes.Shape>类看上去相似，因为它们都描述的二维形状 (比较<xref:System.Windows.Media.EllipseGeometry>和<xref:System.Windows.Shapes.Ellipse>例如)，但存在重要差异。  
  
 对于其中一个，<xref:System.Windows.Media.Geometry>类继承自<xref:System.Windows.Freezable>类在时<xref:System.Windows.Shapes.Shape>类继承自<xref:System.Windows.FrameworkElement>。 由于它们都是元素，<xref:System.Windows.Shapes.Shape>对象可以呈现本身和参与布局系统，而<xref:System.Windows.Media.Geometry>对象不能。  
  
 尽管<xref:System.Windows.Shapes.Shape>对象是更易于使用比<xref:System.Windows.Media.Geometry>对象，<xref:System.Windows.Media.Geometry>对象是更为丰富。 虽然<xref:System.Windows.Shapes.Shape>对象用于呈现二维图形<xref:System.Windows.Media.Geometry>对象可以用于定义的二维图形的几何区域、 定义的区域剪辑，或定义的区域的命中测试，例如。  
  
### <a name="the-path-shape"></a>Path 形状  
 一个<xref:System.Windows.Shapes.Shape>、<xref:System.Windows.Shapes.Path>类，实际使用<xref:System.Windows.Media.Geometry>来描述其内容。 通过设置<xref:System.Windows.Shapes.Path.Data%2A>属性<xref:System.Windows.Shapes.Path>与<xref:System.Windows.Media.Geometry>和设置其<xref:System.Windows.Shapes.Shape.Fill%2A>和<xref:System.Windows.Shapes.Shape.Stroke%2A>属性，可以呈现<xref:System.Windows.Media.Geometry>。  
  
<a name="commonproperties"></a>   
## <a name="common-properties-that-take-a-geometry"></a>采用 Geometry 的常见属性  
 上述部分提到了可将 Geometry 对象与其他对象结合用于各种目的，如绘制形状、动画处理和剪裁。 下表列出具有需要的属性的多个类<xref:System.Windows.Media.Geometry>对象。  
  
|类型|属性|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>   
## <a name="simple-geometry-types"></a>简单几何类型  
 所有的几何图形的基类是抽象类<xref:System.Windows.Media.Geometry>。  派生自的类<xref:System.Windows.Media.Geometry>类可以大致分为三个类别： 简单的几何图形、 路径几何图形和复合几何图形。  
  
 简单的几何图形类包括<xref:System.Windows.Media.LineGeometry>， <xref:System.Windows.Media.RectangleGeometry>，和<xref:System.Windows.Media.EllipseGeometry>和用于创建基本的几何形状，如线条、 矩形和圆形。  
  
-   A<xref:System.Windows.Media.LineGeometry>定义通过指定行和终结点的起始点。  
  
-   A<xref:System.Windows.Media.RectangleGeometry>使用定义<xref:System.Windows.Rect>结构指定的相对位置和其高度和宽度。 你可以通过设置创建一个圆角的矩形<xref:System.Windows.Media.RectangleGeometry.RadiusX%2A>和<xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>属性。  
  
-   <xref:System.Windows.Media.EllipseGeometry>定义的中心点，x 轴半径和 y 轴半径。  以下示例介绍如何创建简单几何来进行呈现和剪裁。  
  
 这些相同的形状，以及更复杂的形状，可以使用创建<xref:System.Windows.Media.PathGeometry>或通过组合在一起，几何对象，但这些类提供了更简单的方法用于生成这些基本的几何形状。  
  
 下面的示例演示如何创建和呈现<xref:System.Windows.Media.LineGeometry>。  如前所述，<xref:System.Windows.Media.Geometry>对象是无法自我绘制，因此该示例使用<xref:System.Windows.Shapes.Path>形状来呈现直线。  由于行具有没有区域，设置<xref:System.Windows.Shapes.Shape.Fill%2A>属性<xref:System.Windows.Shapes.Path>没有任何效果; 相反，仅<xref:System.Windows.Shapes.Shape.Stroke%2A>和<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>指定属性。 下图显示该示例的输出。  
  
 ![一个 LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")  
从 (10,20) 绘制到 (100,130) 的 LineGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 下面的示例演示如何创建和呈现<xref:System.Windows.Media.EllipseGeometry>。  示例集<xref:System.Windows.Media.EllipseGeometry.Center%2A>的<xref:System.Windows.Media.EllipseGeometry>设置为点`50,50`和 x 轴半径和 y 轴半径都设置为`50`，这将创建一个圆一个直径为 100。  通过将值分配给的路径元素的填充属性，在这种情况下绘制椭圆的内部<xref:System.Windows.Media.Brushes.Gold%2A>。 下图显示该示例的输出。  
  
 ![一个 EllipseGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
在 (50,50) 处绘制的一个 EllipseGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 下面的示例演示如何创建和呈现<xref:System.Windows.Media.RectangleGeometry>。  通过定义的位置和矩形的尺寸<xref:System.Windows.Rect>结构。 位置为 `50,50`，高度和宽度均为 `25`，这将创建一个正方形。 下图显示该示例的输出。  
  
 ![一个 RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
在 50,50 处绘制的一个 RectangleGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 下面的示例演示如何使用<xref:System.Windows.Media.EllipseGeometry>作为映像的剪辑区域。  <xref:System.Windows.Controls.Image>对象定义与<xref:System.Windows.FrameworkElement.Width%2A>的 200 和<xref:System.Windows.FrameworkElement.Height%2A>的 150。  <xref:System.Windows.Media.EllipseGeometry>与<xref:System.Windows.Media.EllipseGeometry.RadiusX%2A>值为 100， <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> 75，值和<xref:System.Windows.Media.EllipseGeometry.Center%2A>100,75 值设置为<xref:System.Windows.UIElement.Clip%2A>的映像的属性。  将仅显示处于椭圆形区域内的图像部分。 下图显示该示例的输出。  
  
 ![图像和没有剪辑](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
用于剪裁 Image 控件的 EllipseGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>   
## <a name="path-geometries"></a>路径几何  
 <xref:System.Windows.Media.PathGeometry>类和它轻量的等效项，<xref:System.Windows.Media.StreamGeometry>类中，提供了一种用于描述多个复杂的数字组成弧、 曲线和行。  
  
 核心<xref:System.Windows.Media.PathGeometry>是一套<xref:System.Windows.Media.PathFigure>对象，这样命名是因为每个图描述了中的一个离散形状<xref:System.Windows.Media.PathGeometry>。 每个<xref:System.Windows.Media.PathFigure>本身包含一个或多个<xref:System.Windows.Media.PathSegment>对象，其中每个描述图一段。  
  
 有多种类型的线段。  
  
|线段类型|描述|示例|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|创建两个点之间的椭圆弧。|[创建椭圆弧](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)。|  
|<xref:System.Windows.Media.BezierSegment>|创建两个点之间的三次方贝塞尔曲线。|[创建三次方贝塞尔曲线](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)。|  
|<xref:System.Windows.Media.LineSegment>|创建两个点之间的直线。|[在 PathGeometry 中创建 LineSegment](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|创建一系列三次方贝塞尔曲线。|请参阅<xref:System.Windows.Media.PolyBezierSegment>类型页。|  
|<xref:System.Windows.Media.PolyLineSegment>|创建一系列直线。|请参阅<xref:System.Windows.Media.PolyLineSegment>类型页。|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|创建一系列的二次贝塞尔曲线。|请参阅<xref:System.Windows.Media.PolyQuadraticBezierSegment>页。|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|创建一条二次贝塞尔曲线。|[创建二次贝塞尔曲线](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)。|  
  
 中的线段<xref:System.Windows.Media.PathFigure>合并为单个几何形状下, 一段的起始点每一条线段的终点。 <xref:System.Windows.Media.PathFigure.StartPoint%2A>属性<xref:System.Windows.Media.PathFigure>指定从中提取第一条线段的点。 每个后续线段都从上一线段的终点开始。 例如，从竖线`10,50`到`10,150`可以通过设置定义<xref:System.Windows.Media.PathFigure.StartPoint%2A>属性`10,50`和创建<xref:System.Windows.Media.LineSegment>与<xref:System.Windows.Media.LineSegment.Point%2A>属性设置的`10,150`。  
  
 下面的示例创建一个简单<xref:System.Windows.Media.PathGeometry>组成单个<xref:System.Windows.Media.PathFigure>与<xref:System.Windows.Media.LineSegment>并显示它使用<xref:System.Windows.Shapes.Path>元素。 <xref:System.Windows.Media.PathFigure>对象的<xref:System.Windows.Media.PathFigure.StartPoint%2A>设置为`10,20`和<xref:System.Windows.Media.LineSegment>使用的一个终结点定义`100,130`。 下图显示<xref:System.Windows.Media.PathGeometry>由此示例创建。  
  
 ![一个 LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")  
包含单个 LineSegment 的 PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 值得对比此示例与前面<xref:System.Windows.Media.LineGeometry>示例。  用于的语法<xref:System.Windows.Media.PathGeometry>比使用一个简单的更详细<xref:System.Windows.Media.LineGeometry>，而且它可能会使更易于理解使用<xref:System.Windows.Media.LineGeometry>但详细语法中的这种情况下，类<xref:System.Windows.Media.PathGeometry>允许极其复杂的几何区域。  
  
 可以通过使用的组合创建更复杂的几何图形<xref:System.Windows.Media.PathSegment>对象。  
  
 下一个示例使用<xref:System.Windows.Media.BezierSegment>、 <xref:System.Windows.Media.LineSegment>，和<xref:System.Windows.Media.ArcSegment>来创建形状。 此示例首先创建三次方贝塞尔曲线是通过定义四个点： 一个开始点，这是前一条线段，一个终结点的终点 (<xref:System.Windows.Media.BezierSegment.Point3%2A>)，以及两个控制点 (<xref:System.Windows.Media.BezierSegment.Point1%2A>和<xref:System.Windows.Media.BezierSegment.Point2%2A>)。  三次方贝赛尔曲线的两个控制点行为像磁铁一样，朝着自身方向吸引本应为直线的部分，从而形成一条曲线。 第一个控制点， <xref:System.Windows.Media.BezierSegment.Point1%2A>，影响开头曲线部分; 第二个控制点， <xref:System.Windows.Media.BezierSegment.Point2%2A>，影响曲线的结束部分。  
  
 然后该示例添加<xref:System.Windows.Media.LineSegment>，其中前面终结点之间绘制<xref:System.Windows.Media.BezierSegment>，到由指定的点前面其<xref:System.Windows.Media.LineSegment>属性。  
  
 然后该示例添加<xref:System.Windows.Media.ArcSegment>，其中从前面的终结点绘制<xref:System.Windows.Media.LineSegment>由指定的点到其<xref:System.Windows.Media.ArcSegment.Point%2A>属性。 该示例还指定弧的 x 轴半径和 y-半径 (<xref:System.Windows.Media.ArcSegment.Size%2A>)，旋转角度 (<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>)、 一个标志，指示大小应为生成弧的角度 (<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>)，和一个值，该值的方向绘制弧 (<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>). 下图显示此示例所创建的形状。  
  
 ![一个 PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path2.gif "graphicsmm_path2")  
一个 PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 可以通过使用多个创建更复杂的几何图形<xref:System.Windows.Media.PathFigure>对象内<xref:System.Windows.Media.PathGeometry>。  
  
 下面的示例创建<xref:System.Windows.Media.PathGeometry>包含两个<xref:System.Windows.Media.PathFigure>对象，其中每个包含多个<xref:System.Windows.Media.PathSegment>对象。  <xref:System.Windows.Media.PathFigure>从上面的示例和<xref:System.Windows.Media.PathFigure>与<xref:System.Windows.Media.PolyLineSegment>和<xref:System.Windows.Media.QuadraticBezierSegment>使用。  A<xref:System.Windows.Media.PolyLineSegment>使用的点数组定义和<xref:System.Windows.Media.QuadraticBezierSegment>使用控点和终结点定义。 下图显示此示例所创建的形状。  
  
 ![一个 PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path.gif "graphicsmm_path")  
带有多个图形的 PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 如<xref:System.Windows.Media.PathGeometry>类，<xref:System.Windows.Media.StreamGeometry>定义曲线、 弧线和行可能包含复杂几何形状。 与不同<xref:System.Windows.Media.PathGeometry>的内容<xref:System.Windows.Media.StreamGeometry>不支持数据绑定、 动画或修改。 使用<xref:System.Windows.Media.StreamGeometry>需要来描述复杂的几何图形，但不是希望支持数据绑定、 动画或修改的开销。 由于其效率，<xref:System.Windows.Media.StreamGeometry>类是一个不错的选择，用于描述装饰器。  
  
 有关示例，请参阅[使用 StreamGeometry 创建形状](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md)。  
  
### <a name="path-markup-syntax"></a>路径标记语法  
 <xref:System.Windows.Media.PathGeometry>和<xref:System.Windows.Media.StreamGeometry>类型支持[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]特性语法使用一系列特殊的移动和绘制命令。 有关详细信息，请参阅[路径标记语法](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)。  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>   
## <a name="composite-geometries"></a>复合几何  
 可以使用创建的复合几何图形对象<xref:System.Windows.Media.GeometryGroup>、 <xref:System.Windows.Media.CombinedGeometry>，或通过调用静态<xref:System.Windows.Media.Geometry>方法<xref:System.Windows.Media.Geometry.Combine%2A>。  
  
-   <xref:System.Windows.Media.CombinedGeometry>对象和<xref:System.Windows.Media.Geometry.Combine%2A>方法执行布尔操作，以合并两个几何图形由定义的区域。 <xref:System.Windows.Media.Geometry>有没有区域的对象将被丢弃。 只有两个<xref:System.Windows.Media.Geometry>（尽管这两个几何图形也可能是复合几何图形），可以组合对象。  
  
-   <xref:System.Windows.Media.GeometryGroup>类创建的组合体<xref:System.Windows.Media.Geometry>对象但不合并其区域包含。 任意数量的<xref:System.Windows.Media.Geometry>对象可以添加到<xref:System.Windows.Media.GeometryGroup>。 有关示例，请参阅[创建复合形状](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)。  
  
 因为它们不会执行合并操作，所以使用<xref:System.Windows.Media.GeometryGroup>对象通过使用提供的性能优势<xref:System.Windows.Media.CombinedGeometry>对象或<xref:System.Windows.Media.Geometry.Combine%2A>方法。  
  
<a name="combindgeometriessection"></a>   
## <a name="combined-geometries"></a>合并几何  
 上一部分中所述<xref:System.Windows.Media.CombinedGeometry>对象和<xref:System.Windows.Media.Geometry.Combine%2A>方法组合它们包含的几何图形由定义的区域。 <xref:System.Windows.Media.GeometryCombineMode>枚举指定几何图形的组合的方式。 可能值<xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A>属性： <xref:System.Windows.Media.GeometryCombineMode.Union>， <xref:System.Windows.Media.GeometryCombineMode.Intersect>， <xref:System.Windows.Media.GeometryCombineMode.Exclude>，和<xref:System.Windows.Media.GeometryCombineMode.Xor>。  
  
 在下面的示例中，<xref:System.Windows.Media.CombinedGeometry>定义组合模式的联合。  同时<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>定义圆的半径相同，但是中心偏移量为 50。  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Results of the Union combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 在下面的示例中，<xref:System.Windows.Media.CombinedGeometry>组合模式的定义<xref:System.Windows.Media.GeometryCombineMode.Xor>。  同时<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>定义圆的半径相同，但是中心偏移量为 50。  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Results of the Xor combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 有关其他示例，请参阅[创建复合形状](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)和[创建合并的几何](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-combined-geometry.md)。  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Freezable 功能  
 因为它继承自<xref:System.Windows.Freezable>类，<xref:System.Windows.Media.Geometry>类提供几个特殊功能：<xref:System.Windows.Media.Geometry>对象可声明为[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)、 多个对象，进行只读的以提高之间共享性能，克隆，并进行线程安全。 有关提供的不同功能的详细信息<xref:System.Windows.Freezable>对象，请参阅[可冻结对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)。  
  
<a name="othergeometryfeatures"></a>   
## <a name="other-geometry-features"></a>其他几何功能  
 <xref:System.Windows.Media.Geometry>类还提供了有用的实用工具方法，如下所示：  
  
-   <xref:System.Windows.Media.Geometry.GetArea%2A>-获取的区域<xref:System.Windows.Media.Geometry>。  
  
-   <xref:System.Windows.Media.Geometry.FillContains%2A>-确定几何图形是否包含另一个<xref:System.Windows.Media.Geometry>。  
  
-   <xref:System.Windows.Media.Geometry.StrokeContains%2A>-确定是否的描边<xref:System.Windows.Media.Geometry>包含指定的点。  
  
 请参阅<xref:System.Windows.Media.Geometry>有关其方法的完整列表的类。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Geometry>  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [2D 图形和图像处理](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [路径标记语法](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [WPF 中的形状和基本绘图概述](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Drawing 对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
