---
title: WPF 中的形状和基本图形概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shapes [WPF], about shapes
- basic drawing [WPF]
- vector drawing [WPF], overview
- vectors [WPF], drawing
- Shape objects [WPF]
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
ms.openlocfilehash: 47df352c3b001f088f34ea057b34698efc4f4b53
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48778096"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a><span data-ttu-id="21937-102">WPF 中的形状和基本图形概述</span><span class="sxs-lookup"><span data-stu-id="21937-102">Shapes and Basic Drawing in WPF Overview</span></span>
<span data-ttu-id="21937-103">本主题概述了如何绘制与<xref:System.Windows.Shapes.Shape>对象。</span><span class="sxs-lookup"><span data-stu-id="21937-103">This topic gives an overview of how to draw with <xref:System.Windows.Shapes.Shape> objects.</span></span> <span data-ttu-id="21937-104">一个<xref:System.Windows.Shapes.Shape>是一种<xref:System.Windows.UIElement>，使您可以在屏幕上绘制一个形状。</span><span class="sxs-lookup"><span data-stu-id="21937-104">A <xref:System.Windows.Shapes.Shape> is a type of <xref:System.Windows.UIElement> that enables you to draw a shape to the screen.</span></span> <span data-ttu-id="21937-105">由于它们是 UI 元素<xref:System.Windows.Shapes.Shape>对象可以用在<xref:System.Windows.Controls.Panel>元素和多数控件。</span><span class="sxs-lookup"><span data-stu-id="21937-105">Because they are UI elements, <xref:System.Windows.Shapes.Shape> objects can be used inside <xref:System.Windows.Controls.Panel> elements and most controls.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="21937-106">为图形和绘制服务提供多层访问。</span><span class="sxs-lookup"><span data-stu-id="21937-106"> offers several layers of access to graphics and rendering services.</span></span> <span data-ttu-id="21937-107">在顶层，<xref:System.Windows.Shapes.Shape>对象是易于使用和提供许多有用的功能，例如布局和参与[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]事件系统。</span><span class="sxs-lookup"><span data-stu-id="21937-107">At the top layer, <xref:System.Windows.Shapes.Shape> objects are easy to use and provide many useful features, such as layout and participation in the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] event system.</span></span>  
  
  
<a name="shapes"></a>   
## <a name="shape-objects"></a><span data-ttu-id="21937-108">形状对象</span><span class="sxs-lookup"><span data-stu-id="21937-108">Shape Objects</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="21937-109">提供了随时可用的大量<xref:System.Windows.Shapes.Shape>对象。</span><span class="sxs-lookup"><span data-stu-id="21937-109"> provides a number of ready-to-use <xref:System.Windows.Shapes.Shape> objects.</span></span>  <span data-ttu-id="21937-110">所有形状对象都继承自<xref:System.Windows.Shapes.Shape>类。</span><span class="sxs-lookup"><span data-stu-id="21937-110">All shape objects inherit from the <xref:System.Windows.Shapes.Shape> class.</span></span> <span data-ttu-id="21937-111">可用形状对象包括<xref:System.Windows.Shapes.Ellipse>， <xref:System.Windows.Shapes.Line>， <xref:System.Windows.Shapes.Path>， <xref:System.Windows.Shapes.Polygon>， <xref:System.Windows.Shapes.Polyline>，并<xref:System.Windows.Shapes.Rectangle>。</span><span class="sxs-lookup"><span data-stu-id="21937-111">Available shape objects include <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="21937-112"><xref:System.Windows.Shapes.Shape> 对象共享以下通用属性。</span><span class="sxs-lookup"><span data-stu-id="21937-112"><xref:System.Windows.Shapes.Shape> objects share the following common properties.</span></span>  
  
-   <span data-ttu-id="21937-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>： 介绍了如何绘制形状的轮廓。</span><span class="sxs-lookup"><span data-stu-id="21937-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Describes how the shape's outline is painted.</span></span>  
  
-   <span data-ttu-id="21937-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>： 描述形状的轮廓的粗细。</span><span class="sxs-lookup"><span data-stu-id="21937-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describes the thickness of the shape's outline.</span></span>  
  
-   <span data-ttu-id="21937-115"><xref:System.Windows.Shapes.Shape.Fill%2A>： 介绍了如何绘制形状的内部。</span><span class="sxs-lookup"><span data-stu-id="21937-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Describes how the interior of the shape is painted.</span></span>  
  
-   <span data-ttu-id="21937-116">用于指定坐标和顶点的数据属性，以与设备无关的像素来度量。</span><span class="sxs-lookup"><span data-stu-id="21937-116">Data properties to specify coordinates and vertices, measured in device-independent pixels.</span></span>  
  
 <span data-ttu-id="21937-117">由于它们源自<xref:System.Windows.UIElement>，形状对象可以用在面板和多数控件。</span><span class="sxs-lookup"><span data-stu-id="21937-117">Because they derive from <xref:System.Windows.UIElement>, shape objects can be used inside panels and most controls.</span></span> <span data-ttu-id="21937-118"><xref:System.Windows.Controls.Canvas>面板是特别适合用于创建复杂的图形，因为它支持绝对定位子对象。</span><span class="sxs-lookup"><span data-stu-id="21937-118">The <xref:System.Windows.Controls.Canvas> panel is a particularly good choice for creating complex drawings because it supports absolute positioning of its child objects.</span></span>  
  
 <span data-ttu-id="21937-119"><xref:System.Windows.Shapes.Line>类使您能够在两点之间绘制线条。</span><span class="sxs-lookup"><span data-stu-id="21937-119">The <xref:System.Windows.Shapes.Line> class enables you to draw a line between two points.</span></span> <span data-ttu-id="21937-120">以下示例演示了指定线坐标和笔划属性的几种方法。</span><span class="sxs-lookup"><span data-stu-id="21937-120">The following example shows several ways to specify line coordinates and stroke properties.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 <span data-ttu-id="21937-121">下图显示了呈现<xref:System.Windows.Shapes.Line>。</span><span class="sxs-lookup"><span data-stu-id="21937-121">The following image shows the rendered <xref:System.Windows.Shapes.Line>.</span></span>  
  
 <span data-ttu-id="21937-122">![Line illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.gif "shape_ovw_line2")</span><span class="sxs-lookup"><span data-stu-id="21937-122">![Line illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.gif "shape_ovw_line2")</span></span>  
  
 <span data-ttu-id="21937-123">尽管<xref:System.Windows.Shapes.Line>确实提供了类<xref:System.Windows.Shapes.Shape.Fill%2A>属性，将其设置没有任何作用，因为<xref:System.Windows.Shapes.Line>没有区域。</span><span class="sxs-lookup"><span data-stu-id="21937-123">Although the <xref:System.Windows.Shapes.Line> class does provide a <xref:System.Windows.Shapes.Shape.Fill%2A> property, setting it has no effect because a <xref:System.Windows.Shapes.Line> has no area.</span></span>  
  
 <span data-ttu-id="21937-124">另一个常见形状是<xref:System.Windows.Shapes.Ellipse>。</span><span class="sxs-lookup"><span data-stu-id="21937-124">Another common shape is the <xref:System.Windows.Shapes.Ellipse>.</span></span>  <span data-ttu-id="21937-125">创建<xref:System.Windows.Shapes.Ellipse>通过定义的形状<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="21937-125">Create an <xref:System.Windows.Shapes.Ellipse> by defining the shape's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span> <span data-ttu-id="21937-126">若要绘制一个圆圈，指定<xref:System.Windows.Shapes.Ellipse>其<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>值是否相等。</span><span class="sxs-lookup"><span data-stu-id="21937-126">To draw a circle, specify an <xref:System.Windows.Shapes.Ellipse> whose <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> values are equal.</span></span>  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 <span data-ttu-id="21937-127">下图显示了示例的呈现<xref:System.Windows.Shapes.Ellipse>。</span><span class="sxs-lookup"><span data-stu-id="21937-127">The following image shows an example of a rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="21937-128">![Ellipse illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span><span class="sxs-lookup"><span data-stu-id="21937-128">![Ellipse illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span></span>  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a><span data-ttu-id="21937-129">使用路径和几何图形</span><span class="sxs-lookup"><span data-stu-id="21937-129">Using Paths and Geometries</span></span>  
 <span data-ttu-id="21937-130"><xref:System.Windows.Shapes.Path>类可以绘制曲线和复杂的形状。</span><span class="sxs-lookup"><span data-stu-id="21937-130">The <xref:System.Windows.Shapes.Path> class enables you to draw curves and complex shapes.</span></span> <span data-ttu-id="21937-131">这些曲线和形状使用描述<xref:System.Windows.Media.Geometry>对象。</span><span class="sxs-lookup"><span data-stu-id="21937-131">These curves and shapes are described using <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="21937-132">若要使用<xref:System.Windows.Shapes.Path>，创建<xref:System.Windows.Media.Geometry>并使用它来设置<xref:System.Windows.Shapes.Path>对象的<xref:System.Windows.Shapes.Path.Data%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="21937-132">To use a <xref:System.Windows.Shapes.Path>, you create a <xref:System.Windows.Media.Geometry> and use it to set the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Path.Data%2A> property.</span></span>  
  
 <span data-ttu-id="21937-133">有各种<xref:System.Windows.Media.Geometry>对象可供选择。</span><span class="sxs-lookup"><span data-stu-id="21937-133">There are a variety of <xref:System.Windows.Media.Geometry> objects to choose from.</span></span> <span data-ttu-id="21937-134"><xref:System.Windows.Media.LineGeometry>， <xref:System.Windows.Media.RectangleGeometry>，和<xref:System.Windows.Media.EllipseGeometry>类描述了相对简单的形状。</span><span class="sxs-lookup"><span data-stu-id="21937-134">The <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, and <xref:System.Windows.Media.EllipseGeometry> classes describe relatively simple shapes.</span></span> <span data-ttu-id="21937-135">若要创建更复杂的形状或创建曲线，使用<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="21937-135">To create more complex shapes or create curves, use a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a><span data-ttu-id="21937-136">PathGeometry and PathSegments</span><span class="sxs-lookup"><span data-stu-id="21937-136">PathGeometry and PathSegments</span></span>  
 <span data-ttu-id="21937-137"><xref:System.Windows.Media.PathGeometry> 对象由一个或多个组成<xref:System.Windows.Media.PathFigure>对象; 每个<xref:System.Windows.Media.PathFigure>表示不同"图"或形状。</span><span class="sxs-lookup"><span data-stu-id="21937-137"><xref:System.Windows.Media.PathGeometry> objects are comprised of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="21937-138">每个<xref:System.Windows.Media.PathFigure>本身包含一个或多个<xref:System.Windows.Media.PathSegment>对象，每个资源表示图或形状的一个连接的部分。</span><span class="sxs-lookup"><span data-stu-id="21937-138">Each <xref:System.Windows.Media.PathFigure> is itself comprised of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="21937-139">段类型包括以下类型： <xref:System.Windows.Media.LineSegment>， <xref:System.Windows.Media.BezierSegment>，和<xref:System.Windows.Media.ArcSegment>。</span><span class="sxs-lookup"><span data-stu-id="21937-139">Segment types include the following: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, and <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
 <span data-ttu-id="21937-140">在以下示例中，<xref:System.Windows.Shapes.Path>用于绘制二次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="21937-140">In the following example, a <xref:System.Windows.Shapes.Path> is used to draw a quadratic Bezier curve.</span></span>  
  
 [!code-xaml[geometrysample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="21937-141">下图显示了呈现的形状。</span><span class="sxs-lookup"><span data-stu-id="21937-141">The following image shows the rendered shape.</span></span>  
  
 <span data-ttu-id="21937-142">![Path illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.gif "shape_ovw_path2")</span><span class="sxs-lookup"><span data-stu-id="21937-142">![Path illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.gif "shape_ovw_path2")</span></span>  
  
 <span data-ttu-id="21937-143">有关详细信息<xref:System.Windows.Media.PathGeometry>和其他<xref:System.Windows.Media.Geometry>类，请参见[几何概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="21937-143">For more information about <xref:System.Windows.Media.PathGeometry> and the other <xref:System.Windows.Media.Geometry> classes, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a><span data-ttu-id="21937-144">XAML 缩写语法</span><span class="sxs-lookup"><span data-stu-id="21937-144">XAML Abbreviated Syntax</span></span>  
 <span data-ttu-id="21937-145">在中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，还可以使用特殊的缩写的语法来描述<xref:System.Windows.Shapes.Path>。</span><span class="sxs-lookup"><span data-stu-id="21937-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may also use a special abbreviated syntax to describe a <xref:System.Windows.Shapes.Path>.</span></span> <span data-ttu-id="21937-146">以下示例中，使用了缩写语法绘制复杂的形状。</span><span class="sxs-lookup"><span data-stu-id="21937-146">In the following example, abbreviated syntax is used to draw a complex shape.</span></span>  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 <span data-ttu-id="21937-147">下图显示了呈现<xref:System.Windows.Shapes.Path>。</span><span class="sxs-lookup"><span data-stu-id="21937-147">The following image shows a rendered <xref:System.Windows.Shapes.Path>.</span></span>  
  
 <span data-ttu-id="21937-148">![Path illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.PNG "shape_ovw_path")</span><span class="sxs-lookup"><span data-stu-id="21937-148">![Path illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.PNG "shape_ovw_path")</span></span>  
  
 <span data-ttu-id="21937-149"><xref:System.Windows.Shapes.Path.Data%2A>属性字符串以"moveto"命令，用 M 表示，这建立路径的起始点的坐标系统中<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="21937-149">The <xref:System.Windows.Shapes.Path.Data%2A> attribute string begins with the "moveto" command, indicated by M, which establishes a start point for the path in the coordinate system of the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="21937-150"><xref:System.Windows.Shapes.Path> 数据参数是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="21937-150"><xref:System.Windows.Shapes.Path> data parameters are case-sensitive.</span></span> <span data-ttu-id="21937-151">大写字母 M 指示新的当前点的绝对位置。</span><span class="sxs-lookup"><span data-stu-id="21937-151">The capital M indicates an absolute location for the new current point.</span></span> <span data-ttu-id="21937-152">小写字母 m 指示相对坐标。</span><span class="sxs-lookup"><span data-stu-id="21937-152">A lowercase m would indicate relative coordinates.</span></span> <span data-ttu-id="21937-153">第一段是一条三次贝塞尔曲线，该曲线以 (100,200) 开始，至 (400,175) 结束，使用 (100,25) 和 (400,350) 这两个控制点绘制。</span><span class="sxs-lookup"><span data-stu-id="21937-153">The first segment is a cubic Bezier curve beginning at (100,200) and ending at (400,175), drawn using the two control points (100,25) and (400,350).</span></span> <span data-ttu-id="21937-154">此段中的 C 命令指示<xref:System.Windows.Shapes.Path.Data%2A>属性字符串。</span><span class="sxs-lookup"><span data-stu-id="21937-154">This segment is indicated by the C command in the <xref:System.Windows.Shapes.Path.Data%2A> attribute string.</span></span> <span data-ttu-id="21937-155">同样，大写的 C 指示绝对路径；小写的 c 指示相对路径。</span><span class="sxs-lookup"><span data-stu-id="21937-155">Again, the capital C indicates an absolute path; the lowercase c would indicate a relative path.</span></span>  
  
 <span data-ttu-id="21937-156">第二段以绝对水平“lineto”命令 H 开头，它指定绘制一条从前面的子路径的终点 (400,175) 到新终点 (280,175) 的直线。</span><span class="sxs-lookup"><span data-stu-id="21937-156">The second segment begins with an absolute horizontal "lineto" command H, which specifies a line drawn from the preceding subpath's endpoint (400,175) to a new endpoint (280,175).</span></span> <span data-ttu-id="21937-157">它是一个水平"lineto"命令，因为指定的值是*x*-协调。</span><span class="sxs-lookup"><span data-stu-id="21937-157">Because it is a horizontal "lineto" command, the value specified is an *x*-coordinate.</span></span>  
  
 <span data-ttu-id="21937-158">有关完整的路径语法，请参阅<xref:System.Windows.Shapes.Path.Data%2A>引用和[使用 PathGeometry 创建形状](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)。</span><span class="sxs-lookup"><span data-stu-id="21937-158">For the complete path syntax, see the <xref:System.Windows.Shapes.Path.Data%2A> reference and [Create a Shape by Using a PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a><span data-ttu-id="21937-159">绘制形状</span><span class="sxs-lookup"><span data-stu-id="21937-159">Painting Shapes</span></span>  
 <span data-ttu-id="21937-160"><xref:System.Windows.Media.Brush> 对象用于绘制的形状<xref:System.Windows.Shapes.Shape.Stroke%2A>和<xref:System.Windows.Shapes.Shape.Fill%2A>。</span><span class="sxs-lookup"><span data-stu-id="21937-160"><xref:System.Windows.Media.Brush> objects are used to paint a shape's <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="21937-161">在下面的示例、 笔划和填充<xref:System.Windows.Shapes.Ellipse>指定。</span><span class="sxs-lookup"><span data-stu-id="21937-161">In the following example, the stroke and fill of an <xref:System.Windows.Shapes.Ellipse> are specified.</span></span> <span data-ttu-id="21937-162">注意画笔属性的有效输入可以是关键字或十六进制颜色值。</span><span class="sxs-lookup"><span data-stu-id="21937-162">Note that valid input for brush properties can be either a keyword or hexadecimal color value.</span></span> <span data-ttu-id="21937-163">有关可用颜色关键字的详细信息，请参阅的属性<xref:System.Windows.Media.Colors>类中<xref:System.Windows.Media>命名空间。</span><span class="sxs-lookup"><span data-stu-id="21937-163">For more information about available color keywords, see properties of the <xref:System.Windows.Media.Colors> class in the <xref:System.Windows.Media> namespace.</span></span>  
  
```xaml
<Canvas Background="LightGray">   
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
```  
  
 <span data-ttu-id="21937-164">下图显示了呈现<xref:System.Windows.Shapes.Ellipse>。</span><span class="sxs-lookup"><span data-stu-id="21937-164">The following image shows the rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="21937-165">![椭圆](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span><span class="sxs-lookup"><span data-stu-id="21937-165">![An ellipse](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span></span>  
  
 <span data-ttu-id="21937-166">或者，可以使用属性元素语法显式创建<xref:System.Windows.Media.SolidColorBrush>对象绘制形状用纯色。</span><span class="sxs-lookup"><span data-stu-id="21937-166">Alternatively, you can use property element syntax to explicitly create a <xref:System.Windows.Media.SolidColorBrush> object to paint the shape with a solid color.</span></span>  
  
```xaml
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"   
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 <span data-ttu-id="21937-167">下图显示了呈现的形状。</span><span class="sxs-lookup"><span data-stu-id="21937-167">The following illustration shows the rendered shape.</span></span>  
  
 <span data-ttu-id="21937-168">![SolidColorBrush illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="21937-168">![SolidColorBrush illustration](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span></span>  
  
 <span data-ttu-id="21937-169">还可以使用渐变、图像、模式等绘制形状的笔划或填充。</span><span class="sxs-lookup"><span data-stu-id="21937-169">You can also paint a shape's stroke or fill with gradients, images, patterns, and more.</span></span> <span data-ttu-id="21937-170">有关详细信息，请参阅[使用纯色和渐变概述进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="21937-170">For more information, see the [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a><span data-ttu-id="21937-171">可拉伸的形状</span><span class="sxs-lookup"><span data-stu-id="21937-171">Stretchable Shapes</span></span>  
 <span data-ttu-id="21937-172"><xref:System.Windows.Shapes.Line>， <xref:System.Windows.Shapes.Path>， <xref:System.Windows.Shapes.Polygon>， <xref:System.Windows.Shapes.Polyline>，并<xref:System.Windows.Shapes.Rectangle>类都具有<xref:System.Windows.Shapes.Shape.Stretch%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="21937-172">The <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle> classes all have a <xref:System.Windows.Shapes.Shape.Stretch%2A> property.</span></span> <span data-ttu-id="21937-173">此属性确定如何<xref:System.Windows.Shapes.Shape>对象的内容 （要绘制的形状） 拉伸以填充<xref:System.Windows.Shapes.Shape>对象的布局空间。</span><span class="sxs-lookup"><span data-stu-id="21937-173">This property determines how a <xref:System.Windows.Shapes.Shape> object's contents (the shape to be drawn) is stretched to fill the <xref:System.Windows.Shapes.Shape> object's layout space.</span></span> <span data-ttu-id="21937-174">一个<xref:System.Windows.Shapes.Shape>对象的布局空间是空间量<xref:System.Windows.Shapes.Shape>分配由布局系统，是由于显式<xref:System.Windows.FrameworkElement.Width%2A>并<xref:System.Windows.FrameworkElement.Height%2A>设置或由于其<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>设置。</span><span class="sxs-lookup"><span data-stu-id="21937-174">A <xref:System.Windows.Shapes.Shape> object's layout space is the amount of space the <xref:System.Windows.Shapes.Shape> is allocated by the layout system, because of either an explicit <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> setting or because of its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> settings.</span></span> <span data-ttu-id="21937-175">在 Windows Presentation Foundation 中的布局的其他信息，请参阅[布局](../../../../docs/framework/wpf/advanced/layout.md)概述。</span><span class="sxs-lookup"><span data-stu-id="21937-175">For additional information on layout in Windows Presentation Foundation, see [Layout](../../../../docs/framework/wpf/advanced/layout.md) overview.</span></span>  
  
 <span data-ttu-id="21937-176">Stretch 属性采用下列值之一：</span><span class="sxs-lookup"><span data-stu-id="21937-176">The Stretch property takes one of the following values:</span></span>  
  
-   <span data-ttu-id="21937-177"><xref:System.Windows.Media.Stretch.None>:<xref:System.Windows.Shapes.Shape>对象的内容未拉伸。</span><span class="sxs-lookup"><span data-stu-id="21937-177"><xref:System.Windows.Media.Stretch.None>: The <xref:System.Windows.Shapes.Shape> object's contents are not stretched.</span></span>  
  
-   <span data-ttu-id="21937-178"><xref:System.Windows.Media.Stretch.Fill>:<xref:System.Windows.Shapes.Shape>对象的内容被拉伸以填充布局空间。</span><span class="sxs-lookup"><span data-stu-id="21937-178"><xref:System.Windows.Media.Stretch.Fill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to fill its layout space.</span></span>  <span data-ttu-id="21937-179">不保留纵横比。</span><span class="sxs-lookup"><span data-stu-id="21937-179">Aspect ratio is not preserved.</span></span>  
  
-   <span data-ttu-id="21937-180"><xref:System.Windows.Media.Stretch.Uniform>:<xref:System.Windows.Shapes.Shape>对象的内容将被拉伸以尽可能以填充布局空间，同时保留原始纵横比。</span><span class="sxs-lookup"><span data-stu-id="21937-180"><xref:System.Windows.Media.Stretch.Uniform>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched as much as possible to fill its layout space while preserving its original aspect ratio.</span></span>  
  
-   <span data-ttu-id="21937-181"><xref:System.Windows.Media.Stretch.UniformToFill>:<xref:System.Windows.Shapes.Shape>对象的内容被拉伸以完全填充布局空间，同时保留原始纵横比。</span><span class="sxs-lookup"><span data-stu-id="21937-181"><xref:System.Windows.Media.Stretch.UniformToFill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to completely fill its layout space while preserving its original aspect ratio.</span></span>  
  
 <span data-ttu-id="21937-182">请注意，当<xref:System.Windows.Shapes.Shape>对象的内容将被拉伸，<xref:System.Windows.Shapes.Shape>在拉伸后绘制对象的轮廓。</span><span class="sxs-lookup"><span data-stu-id="21937-182">Note that, when a <xref:System.Windows.Shapes.Shape> object's contents are stretched, the <xref:System.Windows.Shapes.Shape> object's outline is painted after the stretching.</span></span>  
  
 <span data-ttu-id="21937-183">在以下示例中，<xref:System.Windows.Shapes.Polygon>用于绘制从 (0，0) 到 (0，1) 很小的三角形到 (1，1)。</span><span class="sxs-lookup"><span data-stu-id="21937-183">In the following example, a <xref:System.Windows.Shapes.Polygon> is used to draw a very small triangle from (0,0) to (0,1) to (1,1).</span></span> <span data-ttu-id="21937-184"><xref:System.Windows.Shapes.Polygon>对象的<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>设置为 100，并且其拉伸属性设置为 Fill。</span><span class="sxs-lookup"><span data-stu-id="21937-184">The <xref:System.Windows.Shapes.Polygon> object's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> are set to 100, and its stretch property is set to Fill.</span></span> <span data-ttu-id="21937-185">因此，<xref:System.Windows.Shapes.Polygon>对象的内容 （三角形） 被拉伸以填充较大的空间。</span><span class="sxs-lookup"><span data-stu-id="21937-185">As a result, the <xref:System.Windows.Shapes.Polygon> object's contents (the triangle) are stretched to fill the larger space.</span></span>  
  
```xaml
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
```

```csharp
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
```

<a name="transforms"></a>   
## <a name="transforming-shapes"></a><span data-ttu-id="21937-186">转换形状</span><span class="sxs-lookup"><span data-stu-id="21937-186">Transforming Shapes</span></span>  
 <span data-ttu-id="21937-187"><xref:System.Windows.Media.Transform>类提供了转换形状在二维平面中的方法。</span><span class="sxs-lookup"><span data-stu-id="21937-187">The <xref:System.Windows.Media.Transform> class provides the means to transform shapes in a two-dimensional plane.</span></span>  <span data-ttu-id="21937-188">不同类型的转换包括旋转 (<xref:System.Windows.Media.RotateTransform>)，小数位数 (<xref:System.Windows.Media.ScaleTransform>)、 倾斜 (<xref:System.Windows.Media.SkewTransform>)，和转换 (<xref:System.Windows.Media.TranslateTransform>)。</span><span class="sxs-lookup"><span data-stu-id="21937-188">The different types of transformation include rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), skew (<xref:System.Windows.Media.SkewTransform>), and translation (<xref:System.Windows.Media.TranslateTransform>).</span></span>  
  
 <span data-ttu-id="21937-189">应用于形状的常见转换就是旋转。</span><span class="sxs-lookup"><span data-stu-id="21937-189">A common transform to apply to a shape is a rotation.</span></span>  <span data-ttu-id="21937-190">若要旋转形状，创建<xref:System.Windows.Media.RotateTransform>并指定其<xref:System.Windows.Media.RotateTransform.Angle%2A>。</span><span class="sxs-lookup"><span data-stu-id="21937-190">To rotate a shape, create a <xref:System.Windows.Media.RotateTransform> and specify its <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span></span> <span data-ttu-id="21937-191"><xref:System.Windows.Media.RotateTransform.Angle%2A>的 45 将元素旋转 45 度顺时针旋转; 90 的角度将元素旋转 90 度顺时针旋转; 依此类推。</span><span class="sxs-lookup"><span data-stu-id="21937-191">An <xref:System.Windows.Media.RotateTransform.Angle%2A> of 45 rotates the element 45 degrees clockwise; an angle of 90 rotates the element 90 degrees clockwise; and so on.</span></span> <span data-ttu-id="21937-192">设置<xref:System.Windows.Media.RotateTransform.CenterX%2A>和<xref:System.Windows.Media.RotateTransform.CenterY%2A>属性，如果你想要控制元素旋转所围绕的点。</span><span class="sxs-lookup"><span data-stu-id="21937-192">Set the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties if you want to control the point about which the element is rotated.</span></span> <span data-ttu-id="21937-193">这些属性值在被转换的元素的坐标空间中表示。</span><span class="sxs-lookup"><span data-stu-id="21937-193">These property values are expressed in the coordinate space of the element being transformed.</span></span> <span data-ttu-id="21937-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> 和<xref:System.Windows.Media.RotateTransform.CenterY%2A>默认值为零。</span><span class="sxs-lookup"><span data-stu-id="21937-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> have default values of zero.</span></span> <span data-ttu-id="21937-195">最后，将应用<xref:System.Windows.Media.RotateTransform>到元素。</span><span class="sxs-lookup"><span data-stu-id="21937-195">Finally, apply the <xref:System.Windows.Media.RotateTransform> to the element.</span></span> <span data-ttu-id="21937-196">如果不希望转换影响布局，设置形状的<xref:System.Windows.UIElement.RenderTransform%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="21937-196">If you don't want the transform to affect layout, set the shape's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="21937-197">在以下示例中，<xref:System.Windows.Media.RotateTransform>用于旋转形状的左上角 (0，0) 形状 45 度。</span><span class="sxs-lookup"><span data-stu-id="21937-197">In the following example, a <xref:System.Windows.Media.RotateTransform> is used to rotate a shape 45 degrees about the shape's top left corner (0,0).</span></span>  
  
 [!code-xaml[transformssample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 <span data-ttu-id="21937-198">在以下示例中，另一个形状也旋转了 45 度，但这次它围绕点 (25,50) 旋转。</span><span class="sxs-lookup"><span data-stu-id="21937-198">In the next example, another shape is rotated 45 degrees, but this time it's rotated about the point (25,50).</span></span>  
  
 [!code-xaml[transformssample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 <span data-ttu-id="21937-199">下图显示了应用两次转换的结果。</span><span class="sxs-lookup"><span data-stu-id="21937-199">The following illustration shows the results of applying the two transforms.</span></span>  
  
 <span data-ttu-id="21937-200">![围绕不同中心点旋转 45 度](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="21937-200">![45 degree rotations with different center points](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
  
 <span data-ttu-id="21937-201">在前面的示例中，对每一个形状对象应用了一次转换。</span><span class="sxs-lookup"><span data-stu-id="21937-201">In the previous examples, a single transform was applied to each shape object.</span></span> <span data-ttu-id="21937-202">若要将多个转换应用到一个形状 （或任何其他 UI 元素），使用<xref:System.Windows.Media.TransformGroup>。</span><span class="sxs-lookup"><span data-stu-id="21937-202">To apply multiple transforms to a shape (or any other UI element), use a <xref:System.Windows.Media.TransformGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21937-203">请参阅</span><span class="sxs-lookup"><span data-stu-id="21937-203">See Also</span></span>  
 [<span data-ttu-id="21937-204">2D 图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="21937-204">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [<span data-ttu-id="21937-205">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="21937-205">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="21937-206">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="21937-206">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="21937-207">演练：我的第一个 WPF 桌面应用程序</span><span class="sxs-lookup"><span data-stu-id="21937-207">Walkthrough: My first WPF desktop application</span></span>](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)  
 [<span data-ttu-id="21937-208">动画概述</span><span class="sxs-lookup"><span data-stu-id="21937-208">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
