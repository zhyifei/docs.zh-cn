---
title: Geometry 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometry classes [WPF]
- graphics [WPF], geometry classes
ms.assetid: 9fba8934-98b7-4af6-82f6-f4ef887f963a
ms.openlocfilehash: f45c13e1af9bc2d1f75da11b13a2c03936b136c1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455020"
---
# <a name="geometry-overview"></a>Geometry 概述
本概述介绍如何使用 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.Geometry> 类来描述形状。 本主题还对 <xref:System.Windows.Media.Geometry> 对象和 <xref:System.Windows.Shapes.Shape> 元素之间的差异进行了对比。  

<a name="wcpsdk_graphics_geometry_introduction"></a>   
## <a name="what-is-a-geometry"></a>什么是 Geometry？  
 <xref:System.Windows.Media.Geometry> 类和派生自它的类（如 <xref:System.Windows.Media.EllipseGeometry>、<xref:System.Windows.Media.PathGeometry>和 <xref:System.Windows.Media.CombinedGeometry>）使你可以描述二维形状的几何。 这些几何描述具有许多用途，例如定义要绘制到屏幕的形状或定义命中测试和剪裁区域。 甚至可以使用几何定义动画路径。  
  
 从两个或多个 geometry 对象创建的 <xref:System.Windows.Media.Geometry> 对象可以很简单，例如矩形和圆圈，或复合。  可以通过使用 <xref:System.Windows.Media.PathGeometry> 和 <xref:System.Windows.Media.StreamGeometry> 类来创建更复杂的几何图形，这使您能够描述弧线和曲线。  
  
 由于 <xref:System.Windows.Media.Geometry> 是一种 <xref:System.Windows.Freezable>类型，因此 <xref:System.Windows.Media.Geometry> 对象提供多种特殊功能：可以将它们声明为[资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)、在多个对象之间共享、变为只读以提高性能、克隆并使其成为线程安全的。 有关 <xref:System.Windows.Freezable> 对象提供的不同功能的详细信息，请参阅可[冻结对象概述](../advanced/freezable-objects-overview.md)。  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>   
## <a name="geometries-vs-shapes"></a>几何图形与形状  
 <xref:System.Windows.Media.Geometry> 和 <xref:System.Windows.Shapes.Shape> 类看起来类似，因为它们都描述了二维形状（例如，比较 <xref:System.Windows.Media.EllipseGeometry> 和 <xref:System.Windows.Shapes.Ellipse>），但存在重要差异。  
  
 一种情况是，<xref:System.Windows.Media.Geometry> 类继承自 <xref:System.Windows.Freezable> 类，而 <xref:System.Windows.Shapes.Shape> 类从 <xref:System.Windows.FrameworkElement>继承。 因为它们是元素，所以 <xref:System.Windows.Shapes.Shape> 对象可以呈现自身并参与布局系统，而 <xref:System.Windows.Media.Geometry> 对象不能。  
  
 尽管 <xref:System.Windows.Shapes.Shape> 对象比 <xref:System.Windows.Media.Geometry> 对象更易于使用，但 <xref:System.Windows.Media.Geometry> 对象更通用。 虽然 <xref:System.Windows.Shapes.Shape> 对象用于呈现二维图形，但 <xref:System.Windows.Media.Geometry> 对象可用于定义二维图形的几何区域、定义用于剪裁的区域，或定义用于命中测试的区域（例如）。  
  
### <a name="the-path-shape"></a>Path 形状  
 <xref:System.Windows.Shapes.Path> 类一 <xref:System.Windows.Shapes.Shape>实际使用 <xref:System.Windows.Media.Geometry> 来描述其内容。 通过使用 <xref:System.Windows.Media.Geometry> 设置 <xref:System.Windows.Shapes.Path> 的 <xref:System.Windows.Shapes.Path.Data%2A> 属性并设置其 <xref:System.Windows.Shapes.Shape.Fill%2A> 和 <xref:System.Windows.Shapes.Shape.Stroke%2A> 属性，可以呈现 <xref:System.Windows.Media.Geometry>。  
  
<a name="commonproperties"></a>   
## <a name="common-properties-that-take-a-geometry"></a>采用 Geometry 的常见属性  
 上述部分提到了可将 Geometry 对象与其他对象结合用于各种目的，如绘制形状、动画处理和剪裁。 下表列出了具有采用 <xref:System.Windows.Media.Geometry> 对象的属性的几个类。  
  
|键入|Property|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>   
## <a name="simple-geometry-types"></a>简单几何类型  
 所有几何图形的基类都是 <xref:System.Windows.Media.Geometry>的抽象类。  派生自 <xref:System.Windows.Media.Geometry> 类的类可以大致分为三个类别：简单的几何图形、路径几何图形和复合几何图形。  
  
 简单的 geometry 类包括 <xref:System.Windows.Media.LineGeometry>、<xref:System.Windows.Media.RectangleGeometry>和 <xref:System.Windows.Media.EllipseGeometry>，并用于创建基本几何形状，如线条、矩形和圆圈。  
  
- <xref:System.Windows.Media.LineGeometry> 是通过指定直线的起点和终点来定义的。  
  
- 使用 <xref:System.Windows.Rect> 结构定义 <xref:System.Windows.Media.RectangleGeometry>，该结构指定其相对位置及其高度和宽度。 可以通过设置 "<xref:System.Windows.Media.RectangleGeometry.RadiusX%2A>" 和 "<xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>" 属性来创建圆角矩形。  
  
- <xref:System.Windows.Media.EllipseGeometry> 由中心点定义，x 半径和 y 轴半径。  以下示例介绍如何创建简单几何来进行呈现和剪裁。  
  
 您可以使用 <xref:System.Windows.Media.PathGeometry> 或将 geometry 对象组合在一起来创建这些相同的形状，以及更复杂的形状，但这些类提供了一种更简单的方法来生成这些基本几何形状。  
  
 下面的示例演示如何创建和呈现 <xref:System.Windows.Media.LineGeometry>。  如前所述，<xref:System.Windows.Media.Geometry> 对象无法绘制自身，因此该示例使用 <xref:System.Windows.Shapes.Path> 的形状呈现线条。  由于线条没有区域，因此设置 <xref:System.Windows.Shapes.Path> 的 <xref:System.Windows.Shapes.Shape.Fill%2A> 属性将不起任何作用;相反，仅指定 <xref:System.Windows.Shapes.Shape.Stroke%2A> 和 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 属性。 下图显示该示例的输出。  
  
 ![一个 LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
从 (10,20) 绘制到 (100,130) 的 LineGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 下一个示例演示如何创建和呈现 <xref:System.Windows.Media.EllipseGeometry>。  示例将 <xref:System.Windows.Media.EllipseGeometry> 设置 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 设置为点 `50,50`，x 轴半径和 y 轴半径均设置为 `50`，这将创建直径为100的圆。  绘制椭圆的内部，方法是将一个值分配给 Path 元素的 Fill 属性，这种情况下 <xref:System.Windows.Media.Brushes.Gold%2A>。 下图显示该示例的输出。  
  
 ![一个 EllipseGeometry](./media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
在 (50,50) 处绘制的一个 EllipseGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 下面的示例演示如何创建和呈现 <xref:System.Windows.Media.RectangleGeometry>。  矩形的位置和尺寸由 <xref:System.Windows.Rect> 的结构定义。 位置为 `50,50`，高度和宽度均为 `25`，这将创建一个正方形。 下图显示该示例的输出。  
  
 ![一个 RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
在 50,50 处绘制的一个 RectangleGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 下面的示例演示如何使用 <xref:System.Windows.Media.EllipseGeometry> 作为图像的剪辑区域。  定义 <xref:System.Windows.Controls.Image> 对象时，<xref:System.Windows.FrameworkElement.Width%2A> 为200，<xref:System.Windows.FrameworkElement.Height%2A> 150。  <xref:System.Windows.Media.EllipseGeometry>，其 <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> 值为100，<xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> 值为75，<xref:System.Windows.Media.EllipseGeometry.Center%2A> 值为100，75则设置为图像的 <xref:System.Windows.UIElement.Clip%2A> 属性。  将仅显示处于椭圆形区域内的图像部分。 下图显示该示例的输出。  
  
 ![具有剪裁和没有剪裁的图像](./media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
用于剪裁 Image 控件的 EllipseGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>   
## <a name="path-geometries"></a>路径几何  
 <xref:System.Windows.Media.PathGeometry> 类及其轻型等效项（<xref:System.Windows.Media.StreamGeometry> 类）提供了描述由弧线、曲线和线条组成的多个复杂图形的方式。  
  
 <xref:System.Windows.Media.PathGeometry> 的核心是 <xref:System.Windows.Media.PathFigure> 对象的集合，因此命名为，因为每个图形都描述 <xref:System.Windows.Media.PathGeometry>中的离散形状。 每个 <xref:System.Windows.Media.PathFigure> 都由一个或多个 <xref:System.Windows.Media.PathSegment> 对象组成，其中每个对象都描述了一个图形段。  
  
 有多种类型的线段。  
  
|线段类型|描述|示例|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|创建两个点之间的椭圆弧。|[创建椭圆弧](how-to-create-an-elliptical-arc.md)。|  
|<xref:System.Windows.Media.BezierSegment>|创建两个点之间的三次方贝塞尔曲线。|[创建三次方贝塞尔曲线](how-to-create-a-cubic-bezier-curve.md)。|  
|<xref:System.Windows.Media.LineSegment>|创建两个点之间的直线。|[在 PathGeometry 中创建 LineSegment](how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|创建一系列三次方贝塞尔曲线。|请参阅 <xref:System.Windows.Media.PolyBezierSegment> 类型 "页。|  
|<xref:System.Windows.Media.PolyLineSegment>|创建一系列直线。|请参阅 <xref:System.Windows.Media.PolyLineSegment> 类型 "页。|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|创建一系列的二次贝塞尔曲线。|请参阅 <xref:System.Windows.Media.PolyQuadraticBezierSegment> 页面。|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|创建一条二次贝塞尔曲线。|[创建二次贝塞尔曲线](how-to-create-a-quadratic-bezier-curve.md)。|  
  
 <xref:System.Windows.Media.PathFigure> 中的段合并为单个几何形状，其中每个段的终点都是下一段的起点。 <xref:System.Windows.Media.PathFigure> 的 <xref:System.Windows.Media.PathFigure.StartPoint%2A> 属性指定绘制第一段的起点。 每个后续线段都从上一线段的终点开始。 例如，可以通过将 <xref:System.Windows.Media.PathFigure.StartPoint%2A> 属性设置为 `10,50` 并创建 <xref:System.Windows.Media.LineSegment> 属性设置 <xref:System.Windows.Media.LineSegment.Point%2A> 的 `10,150`来定义从 `10,50` 到 `10,150` 的垂直线。  
  
 下面的示例创建一个简单的 <xref:System.Windows.Media.PathGeometry>，其中包含一个具有 <xref:System.Windows.Media.LineSegment> 的 <xref:System.Windows.Media.PathFigure> 并使用 <xref:System.Windows.Shapes.Path> 元素显示它。 <xref:System.Windows.Media.PathFigure> 对象的 <xref:System.Windows.Media.PathFigure.StartPoint%2A> 设置为 `10,20`，并且 <xref:System.Windows.Media.LineSegment> 定义为 `100,130`的端点。 下图显示了此示例创建的 <xref:System.Windows.Media.PathGeometry>。  
  
 ![一个 LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
包含单个 LineSegment 的 PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 值得一提的是，将此示例与前面的 <xref:System.Windows.Media.LineGeometry> 示例进行对比。  用于 <xref:System.Windows.Media.PathGeometry> 的语法比用于简单 <xref:System.Windows.Media.LineGeometry>的语法更详细，在这种情况下，使用 <xref:System.Windows.Media.LineGeometry> 类可能更有意义，但是，<xref:System.Windows.Media.PathGeometry> 的详细语法允许极其复杂的几何区域。  
  
 可以使用 <xref:System.Windows.Media.PathSegment> 对象的组合来创建更复杂的几何。  
  
 下一个示例使用 <xref:System.Windows.Media.BezierSegment>、<xref:System.Windows.Media.LineSegment>和 <xref:System.Windows.Media.ArcSegment> 来创建形状。 该示例首先通过定义四个点来创建三次方贝塞尔曲线：一个开始点，即上一段的终点、终点（<xref:System.Windows.Media.BezierSegment.Point3%2A>）和两个控制点（<xref:System.Windows.Media.BezierSegment.Point1%2A> 和 <xref:System.Windows.Media.BezierSegment.Point2%2A>）。  三次方贝赛尔曲线的两个控制点行为像磁铁一样，朝着自身方向吸引本应为直线的部分，从而形成一条曲线。 第一个控制点 <xref:System.Windows.Media.BezierSegment.Point1%2A>会影响曲线的开始部分;<xref:System.Windows.Media.BezierSegment.Point2%2A>的第二个控制点会影响曲线的结束部分。  
  
 然后，该示例添加了一个 <xref:System.Windows.Media.LineSegment>，该在前面 <xref:System.Windows.Media.BezierSegment> 的终点与 <xref:System.Windows.Media.LineSegment> 属性指定的点之间绘制。  
  
 然后，该示例添加了一个 <xref:System.Windows.Media.ArcSegment>，它从前面 <xref:System.Windows.Media.LineSegment> 的终点绘制到由其 <xref:System.Windows.Media.ArcSegment.Point%2A> 属性指定的点。 该示例还指定了弧线的 x 轴和 y 轴半径（<xref:System.Windows.Media.ArcSegment.Size%2A>）、一个旋转角度（<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>）、一个标志，该标志指示生成的圆弧应使用的角度（<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>）和一个指示弧绘制方向（<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>）的值。 下图显示此示例所创建的形状。  
  
 ![一个 PathGeometry](./media/graphicsmm-path2.gif "graphicsmm_path2")  
一个 PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 可以通过在 <xref:System.Windows.Media.PathGeometry>中使用多个 <xref:System.Windows.Media.PathFigure> 对象来创建更复杂的几何。  
  
 下面的示例创建一个包含两个 <xref:System.Windows.Media.PathFigure> 对象的 <xref:System.Windows.Media.PathGeometry>，其中每个对象都包含多个 <xref:System.Windows.Media.PathSegment> 对象。  使用了上述示例中的 <xref:System.Windows.Media.PathFigure>，并使用了 <xref:System.Windows.Media.PolyLineSegment> 和 <xref:System.Windows.Media.QuadraticBezierSegment> 的 <xref:System.Windows.Media.PathFigure>。  使用点数组定义 <xref:System.Windows.Media.PolyLineSegment>，并使用控制点和终点定义 <xref:System.Windows.Media.QuadraticBezierSegment>。 下图显示此示例所创建的形状。  
  
 ![一个 PathGeometry](./media/graphicsmm-path.gif "graphicsmm_path")  
带有多个图形的 PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 与 <xref:System.Windows.Media.PathGeometry> 类一样，<xref:System.Windows.Media.StreamGeometry> 定义可能包含曲线、弧形和直线的复杂几何形状。 与 <xref:System.Windows.Media.PathGeometry>不同，<xref:System.Windows.Media.StreamGeometry> 的内容不支持数据绑定、动画或修改。 当你需要描述复杂的几何图形但不需要支持数据绑定、动画或修改的开销时，可使用 <xref:System.Windows.Media.StreamGeometry>。 由于其效率，<xref:System.Windows.Media.StreamGeometry> 类是描述装饰器的不错选择。  
  
 有关示例，请参阅[使用 StreamGeometry 创建形状](how-to-create-a-shape-using-a-streamgeometry.md)。  
  
### <a name="path-markup-syntax"></a>路径标记语法  
 <xref:System.Windows.Media.PathGeometry> 和 <xref:System.Windows.Media.StreamGeometry> 类型使用一系列特殊的移动和绘制命令支持 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 特性语法。 有关详细信息，请参阅[路径标记语法](path-markup-syntax.md)。  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>   
## <a name="composite-geometries"></a>复合几何  
 复合几何图形对象可以使用 <xref:System.Windows.Media.GeometryGroup>、<xref:System.Windows.Media.CombinedGeometry>或通过调用静态 <xref:System.Windows.Media.Geometry> 方法 <xref:System.Windows.Media.Geometry.Combine%2A>来创建。  
  
- <xref:System.Windows.Media.CombinedGeometry> 对象和 <xref:System.Windows.Media.Geometry.Combine%2A> 方法执行布尔运算，以组合两个几何图形定义的区域。 不包含区域的 <xref:System.Windows.Media.Geometry> 对象将被丢弃。 只有两个 <xref:System.Windows.Media.Geometry> 对象可以组合（尽管这两个几何图形也可以是复合几何图形）。  
  
- <xref:System.Windows.Media.GeometryGroup> 类创建它所包含的 <xref:System.Windows.Media.Geometry> 对象的指，而不将其区域组合在一起。 可以将任意数量的 <xref:System.Windows.Media.Geometry> 对象添加到 <xref:System.Windows.Media.GeometryGroup>中。 有关示例，请参阅[创建复合形状](how-to-create-a-composite-shape.md)。  
  
 由于使用 <xref:System.Windows.Media.GeometryGroup> 对象不执行合并操作，因此使用 <xref:System.Windows.Media.CombinedGeometry> 对象或 <xref:System.Windows.Media.Geometry.Combine%2A> 方法可提高性能。  
  
<a name="combindgeometriessection"></a>   
## <a name="combined-geometries"></a>合并几何  
 前面部分提到了 <xref:System.Windows.Media.CombinedGeometry> 对象，<xref:System.Windows.Media.Geometry.Combine%2A> 方法组合了其包含的几何图形所定义的区域。 <xref:System.Windows.Media.GeometryCombineMode> 枚举指定如何组合几何图形。 <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> 属性的可能值为： <xref:System.Windows.Media.GeometryCombineMode.Union>、<xref:System.Windows.Media.GeometryCombineMode.Intersect>、<xref:System.Windows.Media.GeometryCombineMode.Exclude>和 <xref:System.Windows.Media.GeometryCombineMode.Xor>。  
  
 在下面的示例中，使用 Union 的合并模式定义了一个 <xref:System.Windows.Media.CombinedGeometry>。  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 和 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 都定义为相同半径的圆，但中心偏移50。  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![联合组合模式的结果](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 在下面的示例中，使用 <xref:System.Windows.Media.GeometryCombineMode.Xor>的合并模式定义了一个 <xref:System.Windows.Media.CombinedGeometry>。  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 和 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 都定义为相同半径的圆，但中心偏移50。  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Xor 组合模式的结果](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 有关其他示例，请参阅[创建复合形状](how-to-create-a-composite-shape.md)和[创建合并的几何](how-to-create-a-combined-geometry.md)。  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Freezable 功能  
 因为它继承自 <xref:System.Windows.Freezable> 类，所以 <xref:System.Windows.Media.Geometry> 类提供若干特殊功能： <xref:System.Windows.Media.Geometry> 对象可以声明为[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)、在多个对象之间共享、变为只读以提高性能、克隆和进行线程安全的。 有关 <xref:System.Windows.Freezable> 对象提供的不同功能的详细信息，请参阅可[冻结对象概述](../advanced/freezable-objects-overview.md)。  
  
<a name="othergeometryfeatures"></a>   
## <a name="other-geometry-features"></a>其他几何功能  
 <xref:System.Windows.Media.Geometry> 类还提供有用的实用工具方法，如下所示：  
  
- <xref:System.Windows.Media.Geometry.GetArea%2A> 获取 <xref:System.Windows.Media.Geometry>的区域。  
  
- <xref:System.Windows.Media.Geometry.FillContains%2A> 确定几何图形是否包含另一个 <xref:System.Windows.Media.Geometry>。  
  
- <xref:System.Windows.Media.Geometry.StrokeContains%2A> 确定 <xref:System.Windows.Media.Geometry> 的笔划是否包含指定的点。  
  
 有关其方法的完整列表，请参阅 <xref:System.Windows.Media.Geometry> 类。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Geometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [2D 图形和图像处理](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [路径标记语法](path-markup-syntax.md)
- [帮助主题](geometries-how-to-topics.md)
- [动画概述](animation-overview.md)
- [WPF 中的形状和基本绘图概述](shapes-and-basic-drawing-in-wpf-overview.md)
- [Drawing 对象概述](drawing-objects-overview.md)
