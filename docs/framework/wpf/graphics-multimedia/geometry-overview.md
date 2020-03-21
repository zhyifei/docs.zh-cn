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
ms.openlocfilehash: ff42e59edd9d98b0b52dc3bdd3ace0c35df60878
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112370"
---
# <a name="geometry-overview"></a>Geometry 概述
本概述介绍如何使用类[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<xref:System.Windows.Media.Geometry>来描述形状。 本主题还对比对象和<xref:System.Windows.Media.Geometry><xref:System.Windows.Shapes.Shape>元素之间的差异。  

<a name="wcpsdk_graphics_geometry_introduction"></a>
## <a name="what-is-a-geometry"></a>什么是 Geometry？  
 类<xref:System.Windows.Media.Geometry>和派生自它的类（如<xref:System.Windows.Media.EllipseGeometry>、<xref:System.Windows.Media.PathGeometry>和<xref:System.Windows.Media.CombinedGeometry>）使您能够描述 2D 形状的几何体。 这些几何描述具有许多用途，例如定义要绘制到屏幕的形状或定义命中测试和剪裁区域。 甚至可以使用几何定义动画路径。  
  
 <xref:System.Windows.Media.Geometry>对象可以是简单的，例如矩形和圆，或从两个或多个几何对象创建的复合对象。  可以使用<xref:System.Windows.Media.PathGeometry>和<xref:System.Windows.Media.StreamGeometry>类创建更复杂的几何体，这使您能够描述弧和曲线。  
  
 因为<xref:System.Windows.Media.Geometry>是 一种<xref:System.Windows.Freezable> <xref:System.Windows.Media.Geometry> ，对象提供了几个特殊功能：它们可以声明为[资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)，在多个对象之间共享，使只读以提高性能，克隆，并使线程安全。 有关<xref:System.Windows.Freezable>对象提供的不同要素的详细信息，请参阅[可冻结对象概述](../advanced/freezable-objects-overview.md)。  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>
## <a name="geometries-vs-shapes"></a>几何形状与形状  
 <xref:System.Windows.Media.Geometry>和<xref:System.Windows.Shapes.Shape>类看起来相似，因为它们都描述了 2D 形状（<xref:System.Windows.Media.EllipseGeometry>例如<xref:System.Windows.Shapes.Ellipse>比较和），但存在重要差异。  
  
 首先，<xref:System.Windows.Media.Geometry>类从<xref:System.Windows.Freezable>类继承，<xref:System.Windows.Shapes.Shape>而类从<xref:System.Windows.FrameworkElement>继承。 由于它们是元素，<xref:System.Windows.Shapes.Shape>因此对象可以渲染自己并参与布局系统，而<xref:System.Windows.Media.Geometry>对象不能。  
  
 尽管<xref:System.Windows.Shapes.Shape>对象比<xref:System.Windows.Media.Geometry>对象更容易使用，但<xref:System.Windows.Media.Geometry>对象更通用。 当<xref:System.Windows.Shapes.Shape>对象用于渲染 2D 图形时，<xref:System.Windows.Media.Geometry>对象可用于定义 2D 图形的几何区域、定义用于剪切的区域或定义用于命中测试的区域。例如。  
  
### <a name="the-path-shape"></a>Path 形状  
 一<xref:System.Windows.Shapes.Shape>个，<xref:System.Windows.Shapes.Path>类，实际上使用来描述<xref:System.Windows.Media.Geometry>其内容。 通过设置<xref:System.Windows.Shapes.Path.Data%2A><xref:System.Windows.Shapes.Path>的 属性<xref:System.Windows.Media.Geometry>和<xref:System.Windows.Shapes.Shape.Fill%2A>和<xref:System.Windows.Shapes.Shape.Stroke%2A>属性，可以呈现 。 <xref:System.Windows.Media.Geometry>  
  
<a name="commonproperties"></a>
## <a name="common-properties-that-take-a-geometry"></a>采用 Geometry 的常见属性  
 上述部分提到了可将 Geometry 对象与其他对象结合用于各种目的，如绘制形状、动画处理和剪裁。 下表列出了具有获取<xref:System.Windows.Media.Geometry>对象的属性的几个类。  
  
|类型|properties|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>
## <a name="simple-geometry-types"></a>简单几何类型  
 所有几何体的基类都是抽象类<xref:System.Windows.Media.Geometry>。  从类派生的<xref:System.Windows.Media.Geometry>类大致可以分为三类：简单几何体、路径几何体和复合几何体。  
  
 简单几何类包括<xref:System.Windows.Media.LineGeometry>和<xref:System.Windows.Media.RectangleGeometry><xref:System.Windows.Media.EllipseGeometry>， 用于创建基本几何形状，如线条、矩形和圆。  
  
- 通过<xref:System.Windows.Media.LineGeometry>指定行的起始点和终点来定义。  
  
- 定义<xref:System.Windows.Media.RectangleGeometry>与一个<xref:System.Windows.Rect>结构，指定其相对位置及其高度和宽度。 您可以通过设置 和<xref:System.Windows.Media.RectangleGeometry.RadiusX%2A><xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>属性来创建圆角矩形。  
  
- <xref:System.Windows.Media.EllipseGeometry>由中心点、x 半径和 y 半径定义。  以下示例介绍如何创建简单几何来进行呈现和剪裁。  
  
 这些相同的形状以及更复杂的形状可以使用 或 通过将几何对象组合在一<xref:System.Windows.Media.PathGeometry>起创建，但这些类为生成这些基本几何形状提供了更简单的方法。  
  
 下面的示例演示如何创建和呈现 。 <xref:System.Windows.Media.LineGeometry>  如前所述，<xref:System.Windows.Media.Geometry>对象无法绘制自身，因此该示例使用<xref:System.Windows.Shapes.Path>形状来渲染线条。  因为一条线没有区域，设置<xref:System.Windows.Shapes.Shape.Fill%2A>的属性<xref:System.Windows.Shapes.Path>将不起作用;相反，仅指定<xref:System.Windows.Shapes.Shape.Stroke%2A><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>和 属性。 下图显示该示例的输出。  
  
 ![一个 LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
从 (10,20) 绘制到 (100,130) 的 LineGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 下一个示例演示如何创建和呈现 。 <xref:System.Windows.Media.EllipseGeometry>  示例<xref:System.Windows.Media.EllipseGeometry.Center%2A>将<xref:System.Windows.Media.EllipseGeometry>的 设置为 的 设置为`50,50`点，x 半径和 y 半径都设置为`50`，这将创建直径为 100 的圆。  椭圆的内部通过为 Path 元素的 Fill 属性（本例<xref:System.Windows.Media.Brushes.Gold%2A>中）分配值来绘制。 下图显示该示例的输出。  
  
 ![一个 EllipseGeometry](./media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
在 (50,50) 处绘制的一个 EllipseGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 下面的示例演示如何创建和呈现 。 <xref:System.Windows.Media.RectangleGeometry>  矩形的位置和尺寸由<xref:System.Windows.Rect>结构定义。 位置为 `50,50`，高度和宽度均为 `25`，这将创建一个正方形。 下图显示该示例的输出。  
  
 ![一个 RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
在 50,50 处绘制的一个 RectangleGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 下面的示例演示如何将 用作<xref:System.Windows.Media.EllipseGeometry>图像的剪辑区域。  对象<xref:System.Windows.Controls.Image>定义的对象为<xref:System.Windows.FrameworkElement.Width%2A>200 和 150。 <xref:System.Windows.FrameworkElement.Height%2A>  <xref:System.Windows.Media.EllipseGeometry><xref:System.Windows.Media.EllipseGeometry.RadiusY%2A><xref:System.Windows.Media.EllipseGeometry.Center%2A><xref:System.Windows.UIElement.Clip%2A>值为 100、值 75 和值 100，75 的 设置为图像的属性。 <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A>  将仅显示处于椭圆形区域内的图像部分。 下图显示该示例的输出。  
  
 ![具有剪裁和没有剪裁的图像](./media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
用于剪裁 Image 控件的 EllipseGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>
## <a name="path-geometries"></a>路径几何  
 类<xref:System.Windows.Media.PathGeometry>及其轻量级等效项<xref:System.Windows.Media.StreamGeometry>类提供了描述由弧、曲线和线组成的多个复杂图形的方法。  
  
 在 的核心是<xref:System.Windows.Media.PathGeometry><xref:System.Windows.Media.PathFigure>对象的集合，因此之所以命名，是因为每个图形描述 中的<xref:System.Windows.Media.PathGeometry>离散形状。 每个<xref:System.Windows.Media.PathFigure>对象本身由一个或多个<xref:System.Windows.Media.PathSegment>对象组成，每个对象都描述了图形的一段。  
  
 有多种类型的线段。  
  
|线段类型|说明|示例|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|在两点之间创建一条椭圆弧。|[创建椭圆弧](how-to-create-an-elliptical-arc.md)。|  
|<xref:System.Windows.Media.BezierSegment>|在两点之间创建一个三次方贝塞尔曲线。|[创建一个立方贝塞尔曲线](how-to-create-a-cubic-bezier-curve.md)。|  
|<xref:System.Windows.Media.LineSegment>|创建两个点之间的直线。|[在 PathGeometry 中创建 LineSegment](how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|创建一系列三次方贝塞尔曲线。|请参阅<xref:System.Windows.Media.PolyBezierSegment>类型页。|  
|<xref:System.Windows.Media.PolyLineSegment>|创建一系列直线。|请参阅<xref:System.Windows.Media.PolyLineSegment>类型页。|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|创建一系列二次贝塞尔曲线。|请参阅页面<xref:System.Windows.Media.PolyQuadraticBezierSegment>。|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|创建二次贝塞尔曲线。|[创建二次贝塞尔曲线](how-to-create-a-quadratic-bezier-curve.md)。|  
  
 中的线段<xref:System.Windows.Media.PathFigure>合并为单个几何形状，每个段的端点是下一个段的起点。 的属性<xref:System.Windows.Media.PathFigure.StartPoint%2A><xref:System.Windows.Media.PathFigure>指定从中绘制第一个段的点。 每个后续段都从上一段的终点开始。 例如，`10,50``10,150`可以通过将<xref:System.Windows.Media.PathFigure.StartPoint%2A>属性设置为 和`10,50`创建<xref:System.Windows.Media.LineSegment>属性<xref:System.Windows.Media.LineSegment.Point%2A>设置为 的`10,150`  
  
 下面的示例创建一个包含<xref:System.Windows.Media.PathGeometry>的带有 的<xref:System.Windows.Media.PathFigure><xref:System.Windows.Media.LineSegment>单个的简单组成的，并使用<xref:System.Windows.Shapes.Path>元素显示它。 对象的<xref:System.Windows.Media.PathFigure><xref:System.Windows.Media.PathFigure.StartPoint%2A>设置为`10,20`和<xref:System.Windows.Media.LineSegment>`100,130` 下图显示了此示例<xref:System.Windows.Media.PathGeometry>创建的示例。  
  
 ![一个 LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
包含单个 LineSegment 的 PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 值得将此示例与前面的<xref:System.Windows.Media.LineGeometry>示例进行对比。  用于<xref:System.Windows.Media.PathGeometry>的语法比用于<xref:System.Windows.Media.LineGeometry>简单语法的语法要详细得多，在这种情况下，使用<xref:System.Windows.Media.LineGeometry>类可能更有意义，但 详细<xref:System.Windows.Media.PathGeometry>语法允许极其复杂和复杂的几何区域。  
  
 可以使用<xref:System.Windows.Media.PathSegment>对象的组合创建更复杂的几何体。  
  
 下一个<xref:System.Windows.Media.BezierSegment>示例使用 、<xref:System.Windows.Media.LineSegment>和<xref:System.Windows.Media.ArcSegment>创建形状。 该示例首先创建一个立方 Bezier 曲线是通过定义四个点：起始点，即上一段的终点、一个端点<xref:System.Windows.Media.BezierSegment.Point3%2A>（） 和两个<xref:System.Windows.Media.BezierSegment.Point1%2A>控制<xref:System.Windows.Media.BezierSegment.Point2%2A>点 （和 ）。  三次方贝赛尔曲线的两个控制点行为像磁铁一样，朝着自身方向吸引本应为直线的部分，从而形成一条曲线。 第一个控制点<xref:System.Windows.Media.BezierSegment.Point1%2A>， 影响曲线的开始部分;第二个<xref:System.Windows.Media.BezierSegment.Point2%2A>控制点 ， 影响曲线的结束部分。  
  
 然后，该示例添加<xref:System.Windows.Media.LineSegment>一个 ，该点在之前的<xref:System.Windows.Media.BezierSegment>终点之间绘制到其<xref:System.Windows.Media.LineSegment>属性指定的点。  
  
 然后，该示例添加<xref:System.Windows.Media.ArcSegment>一个 ，该点从前面的<xref:System.Windows.Media.LineSegment>端点绘制到其<xref:System.Windows.Media.ArcSegment.Point%2A>属性指定的点。 该示例还指定圆弧的 x 和 y 半径<xref:System.Windows.Media.ArcSegment.Size%2A>（）、旋转角度<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>（）、指示结果弧角角度应大的标志 （），<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>以及指示弧方向绘制方向的值 （）。<xref:System.Windows.Media.ArcSegment.SweepDirection%2A> 下图显示此示例所创建的形状。  
  
 ![一个 PathGeometry](./media/graphicsmm-path2.gif "graphicsmm_path2")  
一个 PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 使用 中的多个<xref:System.Windows.Media.PathFigure>对象可以创建更复杂的几何体。 <xref:System.Windows.Media.PathGeometry>  
  
 下面的示例创建具有两<xref:System.Windows.Media.PathGeometry>个<xref:System.Windows.Media.PathFigure>对象的 ，每个对象包含多个<xref:System.Windows.Media.PathSegment>对象。  使用<xref:System.Windows.Media.PathFigure>上例中的 和<xref:System.Windows.Media.PathFigure>a<xref:System.Windows.Media.PolyLineSegment>和<xref:System.Windows.Media.QuadraticBezierSegment>a。  A<xref:System.Windows.Media.PolyLineSegment>使用点数组定义，<xref:System.Windows.Media.QuadraticBezierSegment>使用控制点和端点定义 。 下图显示此示例所创建的形状。  
  
 ![一个 PathGeometry](./media/graphicsmm-path.gif "graphicsmm_path")  
带有多个图形的 PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 与类<xref:System.Windows.Media.PathGeometry>一样，<xref:System.Windows.Media.StreamGeometry>定义可能包含曲线、圆弧和线条的复杂几何形状。 与<xref:System.Windows.Media.PathGeometry>不同，的内容<xref:System.Windows.Media.StreamGeometry>不支持数据绑定、动画或修改。 当您需要<xref:System.Windows.Media.StreamGeometry>描述复杂的几何体，但不希望支持数据绑定、动画或修改时，请使用 。 由于其效率，<xref:System.Windows.Media.StreamGeometry>该类是描述装饰器的好选择。  
  
 有关示例，请参阅[使用 StreamGeometry 创建形状](how-to-create-a-shape-using-a-streamgeometry.md)。  
  
### <a name="path-markup-syntax"></a>路径标记语法  
 和 类型支持使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]一系列特殊的移动和绘制命令的属性语法。 <xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.PathGeometry> 有关详细信息，请参阅[路径标记语法](path-markup-syntax.md)。  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>
## <a name="composite-geometries"></a>复合几何  
 可以使用<xref:System.Windows.Media.GeometryGroup>、或<xref:System.Windows.Media.CombinedGeometry>调用静态<xref:System.Windows.Media.Geometry>方法<xref:System.Windows.Media.Geometry.Combine%2A>创建复合几何对象。  
  
- 对象<xref:System.Windows.Media.CombinedGeometry>和方法<xref:System.Windows.Media.Geometry.Combine%2A>执行布尔操作以组合由两个几何体定义的区域。 <xref:System.Windows.Media.Geometry>没有区域的对象将被丢弃。 只能组合<xref:System.Windows.Media.Geometry>两个对象（尽管这两个几何体也可以是复合几何体）。  
  
- 类<xref:System.Windows.Media.GeometryGroup>创建它包含<xref:System.Windows.Media.Geometry>的对象的合并，而不合并其区域。 任意数量的<xref:System.Windows.Media.Geometry>对象都可以添加到 。 <xref:System.Windows.Media.GeometryGroup> 有关示例，请参阅[创建复合形状](how-to-create-a-composite-shape.md)。  
  
 因为它们不执行组合操作，因此使用<xref:System.Windows.Media.GeometryGroup>对象比使用<xref:System.Windows.Media.CombinedGeometry>对象或<xref:System.Windows.Media.Geometry.Combine%2A>方法具有性能优势。  
  
<a name="combindgeometriessection"></a>
## <a name="combined-geometries"></a>合并几何  
 上一节提到<xref:System.Windows.Media.CombinedGeometry>对象，<xref:System.Windows.Media.Geometry.Combine%2A>该方法组合了由它们包含的几何体定义的区域。 枚<xref:System.Windows.Media.GeometryCombineMode>举指定几何体的组合方式。 属性<xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A>的可能值为<xref:System.Windows.Media.GeometryCombineMode.Union>： 、、<xref:System.Windows.Media.GeometryCombineMode.Intersect><xref:System.Windows.Media.GeometryCombineMode.Exclude>和<xref:System.Windows.Media.GeometryCombineMode.Xor>。  
  
 在下面的示例中，使用联合<xref:System.Windows.Media.CombinedGeometry>联合模式定义 。  和<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>定义为<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>半径相同的圆，但中心偏移 50。  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![“联合”组合模式的结果](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 在下面的示例中，使用<xref:System.Windows.Media.CombinedGeometry><xref:System.Windows.Media.GeometryCombineMode.Xor>的组合模式 定义 。  和<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>定义为<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>半径相同的圆，但中心偏移 50。  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Xor 组合模式的结果](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 有关其他示例，请参阅[创建复合形状](how-to-create-a-composite-shape.md)和[创建合并的几何](how-to-create-a-combined-geometry.md)。  
  
<a name="freezable_features"></a>
## <a name="freezable-features"></a>Freezable 功能  
 <xref:System.Windows.Freezable>由于该<xref:System.Windows.Media.Geometry>类从类继承，因此提供了几个特殊功能：<xref:System.Windows.Media.Geometry>对象可以声明为[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)，在多个对象之间共享，使只读以提高性能、克隆和使线程安全。 有关<xref:System.Windows.Freezable>对象提供的不同要素的详细信息，请参阅[可冻结对象概述](../advanced/freezable-objects-overview.md)。  
  
<a name="othergeometryfeatures"></a>
## <a name="other-geometry-features"></a>其他几何功能  
 该<xref:System.Windows.Media.Geometry>类还提供有用的实用程序方法，例如：  
  
- <xref:System.Windows.Media.Geometry.GetArea%2A>- 获取 的区域<xref:System.Windows.Media.Geometry>。  
  
- <xref:System.Windows.Media.Geometry.FillContains%2A>- 确定几何图形是否包含另一<xref:System.Windows.Media.Geometry>个 。  
  
- <xref:System.Windows.Media.Geometry.StrokeContains%2A>- 确定 的描边<xref:System.Windows.Media.Geometry>是否包含指定的点。  
  
 有关其<xref:System.Windows.Media.Geometry>方法的完整列表，请参阅 类。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Geometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [2D 图形和图像处理](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [路径标记语法](path-markup-syntax.md)
- [如何使用主题](geometries-how-to-topics.md)
- [动画概述](animation-overview.md)
- [WPF 中的形状和基本绘图概述](shapes-and-basic-drawing-in-wpf-overview.md)
- [Drawing 对象概述](drawing-objects-overview.md)
