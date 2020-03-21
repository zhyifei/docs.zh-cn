---
title: 优化性能：二维图形和图像处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], performance
- drawing [WPF], optimizing performance
- imaging [WPF], optimizing performance
- shapes [WPF], optimizing performance
- 2D graphics [WPF]
- images [WPF], optimizing performance
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
ms.openlocfilehash: 59ac7a5aa8b0591c51cdb6ee0d6435649e22fade
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111213"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>优化性能：二维图形和图像处理
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供了多种可按应用程序要求进行优化的二维图形和图像处理功能。 本主题提供有关这些方面性能优化的信息。  

<a name="Drawing_and_Shapes"></a>
## <a name="drawing-and-shapes"></a>绘图和形状  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供<xref:System.Windows.Media.Drawing>和<xref:System.Windows.Shapes.Shape>对象来表示图形绘图内容。 但是，<xref:System.Windows.Media.Drawing>对象比<xref:System.Windows.Shapes.Shape>对象更简单的构造，并提供更好的性能特征。  
  
 A<xref:System.Windows.Shapes.Shape>允许您将图形形状绘制到屏幕。 由于对象派生自类，<xref:System.Windows.FrameworkElement><xref:System.Windows.Shapes.Shape>因此可以在面板和大多数控件内使用对象。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 为图形和绘制服务提供多层访问。 在顶层，<xref:System.Windows.Shapes.Shape>对象易于使用，并提供许多有用的功能，如布局和事件处理。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供了许多现成可用的形状对象。 所有形状对象都从<xref:System.Windows.Shapes.Shape>类继承。 可用的形状对象包括<xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>、、、<xref:System.Windows.Shapes.Polygon><xref:System.Windows.Shapes.Polyline>和<xref:System.Windows.Shapes.Rectangle>。  
  
 <xref:System.Windows.Media.Drawing>另一方面，对象不派生自类<xref:System.Windows.FrameworkElement>，并为渲染形状、图像和文本提供较轻的实现。  
  
 有四种类型的<xref:System.Windows.Media.Drawing>对象：  
  
- <xref:System.Windows.Media.GeometryDrawing>绘制形状。  
  
- <xref:System.Windows.Media.ImageDrawing>绘制图像。  
  
- <xref:System.Windows.Media.GlyphRunDrawing>绘制文本。  
  
- <xref:System.Windows.Media.DrawingGroup>绘制其他图形。 使用图形组将其他图形合并到单个复合图形。  
  
 该<xref:System.Windows.Media.GeometryDrawing>对象用于渲染几何内容。 从<xref:System.Windows.Media.Geometry>它派生的类和具体类（如<xref:System.Windows.Media.CombinedGeometry>和<xref:System.Windows.Media.EllipseGeometry> <xref:System.Windows.Media.PathGeometry>）提供了一种渲染 2D 图形以及提供命中测试和剪切支持的方法。 几何对象可用于定义控件的区域或定义应用于图像的剪裁区域等。 几何对象可以是简单区域（例如矩形和圆形），或者是由两个或多个几何对象创建的复合区域。 可以通过组合<xref:System.Windows.Media.PathSegment>派生对象（如<xref:System.Windows.Media.ArcSegment>、<xref:System.Windows.Media.BezierSegment>和<xref:System.Windows.Media.QuadraticBezierSegment>）来创建更复杂的几何区域。  
  
 从表面上看，<xref:System.Windows.Media.Geometry>类和<xref:System.Windows.Shapes.Shape>类非常相似。 两者都用于 2D 图形的渲染，并且都有从它们派生的类似具体类，例如 和<xref:System.Windows.Media.EllipseGeometry><xref:System.Windows.Shapes.Ellipse>。 但是，这两个类集之间存在重大区别。 首先，<xref:System.Windows.Media.Geometry>类缺乏<xref:System.Windows.Shapes.Shape>类的某些功能，例如绘制自身的能力。 若要绘制几何对象，必须使用另一个类（例如 DrawingContext、Drawing 或 Path（值得注意的是 Path 是一个 Shape））来执行绘制操作。 填充、笔划和笔划粗细等绘制属性位于绘制几何对象的类上，而形状对象中包含这些属性。 可以这样来理解这种差别：几何对象定义区域（例如圆形），而形状对象定义区域、定义如何填充区域和设置区域边框并参与布局系统。  
  
 由于<xref:System.Windows.Shapes.Shape>对象派生自类<xref:System.Windows.FrameworkElement>，因此使用它们可以在应用程序中显著增加更多的内存消耗。 如果真的不需要图形内容的功能，<xref:System.Windows.FrameworkElement>请考虑使用较轻<xref:System.Windows.Media.Drawing>的对象。  
  
 有关<xref:System.Windows.Media.Drawing>对象的详细信息，请参阅[绘制对象概述](../graphics-multimedia/drawing-objects-overview.md)。  
  
<a name="StreamGeometry_Objects"></a>
## <a name="streamgeometry-objects"></a>StreamGeometry 对象  
 该<xref:System.Windows.Media.StreamGeometry>对象是创建几何形状的轻量级<xref:System.Windows.Media.PathGeometry>替代方法。 当您需要<xref:System.Windows.Media.StreamGeometry>描述复杂的几何体时，请使用 。 <xref:System.Windows.Media.StreamGeometry>针对处理许多<xref:System.Windows.Media.PathGeometry>对象进行了优化，与使用许多单个<xref:System.Windows.Media.PathGeometry>对象相比，性能更好。  
  
 下面的示例使用属性语法在 中<xref:System.Windows.Media.StreamGeometry>[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]创建三角形。  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 有关<xref:System.Windows.Media.StreamGeometry>对象的详细信息，请参阅[使用流几何创建形状](../graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md)。  
  
<a name="DrawingVisual_Objects"></a>
## <a name="drawingvisual-objects"></a>DrawingVisual 对象  
 该<xref:System.Windows.Media.DrawingVisual>对象是一个轻量级绘图类，用于渲染形状、图像或文本。 此类之所以为轻量类是因为它不提供布局或事件处理，从而性能得以提升。 因此，绘图非常适用于背景和剪贴画。 有关详细信息，请参阅[使用 DrawingVisual 对象](../graphics-multimedia/using-drawingvisual-objects.md)。  
  
<a name="Images"></a>
## <a name="images"></a>映像  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]与早期版本的 Windows 中的映像功能相比，映像提供了显著改进。 显示位图或在公共控件上使用图像等图像处理功能以前主要由 Microsoft Windows 图形设备接口 (GDI) 或Microsoft Windows GDI+ 应用程序编程接口 (API) 处理。 这些 API 提供基线图像处理功能，但缺少编解码器扩展性支持和高保真图像支持等功能。 WPF 图像处理 API 已经过重新设计，克服了 GDI 和 GDI+ 的缺点，提供新的 API 集以在应用程序内显示和使用图像。  
  
 使用图像时，为使性能更佳，请考虑以下建议：  
  
- 如果应用程序要求显示缩略图，请考虑创建一个缩略版图像。 默认情况下，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 会加载图像并将其解码到最大尺寸。 如果仅需要缩略版本图像，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 会先将图像解码为完整尺寸，然后将其缩放为缩略图大小，这个过程是多余的。 若要避免此多余的过程，可请求 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 将图像解码到缩略图大小，或者请求 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 加载缩略图大小的图像。  
  
- 请务必将图像解码到所需大小而不是默认大小。 如上所述，请求 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 将图像解码为所需大小而不是默认的最大尺寸。 这样不仅会减小应用程序的工作集，还会减慢其执行速度。  
  
- 如果可能，请将多个图像合并到单个图像中，例如由多个图像构成的胶卷条。  
  
- 有关详细信息，请参阅 [图像概述](../graphics-multimedia/imaging-overview.md)。  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 对任何位图缩放进行动画处理时，默认高质量图像重采样算法有时可能由于消耗过多系统资源导致帧速率下降，从而导致动画明显变慢。 通过将<xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A><xref:System.Windows.Media.RenderOptions>对象的属性设置为，<xref:System.Windows.Media.BitmapScalingMode.LowQuality>您可以在缩放位图时创建更平滑的动画。 <xref:System.Windows.Media.BitmapScalingMode.LowQuality>模式告诉渲[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]染引擎在处理图像时从质量优化算法切换到速度优化算法。  
  
 下面的示例演示如何为图像对象设置<xref:System.Windows.Media.BitmapScalingMode>。  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 默认情况下，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]不缓存<xref:System.Windows.Media.TileBrush>对象的呈现内容，如<xref:System.Windows.Media.DrawingBrush>和<xref:System.Windows.Media.VisualBrush>。 在场景中的内容或使用<xref:System.Windows.Media.TileBrush>都不在变化的静态方案中，这是有道理的，因为它可以节省视频内存。 当以非静态方式使用<xref:System.Windows.Media.TileBrush>具有静态内容的内容时，例如，当静态<xref:System.Windows.Media.DrawingBrush>或<xref:System.Windows.Media.VisualBrush>映射到旋转 3D 对象的表面时，则没有意义。 的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]默认行为是重新呈现<xref:System.Windows.Media.DrawingBrush>或<xref:System.Windows.Media.VisualBrush>每个帧的整个内容，即使内容不变。  
  
 通过将<xref:System.Windows.Media.RenderOptions.CachingHint%2A><xref:System.Windows.Media.RenderOptions>对象的属性设置为<xref:System.Windows.Media.CachingHint.Cache>，可以使用平铺画笔对象的缓存版本来提高性能。  
  
 和 属性值是相对大小值，用于确定何时<xref:System.Windows.Media.TileBrush>应由于比例变化而重新生成对象。 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> 例如，通过将<xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>属性设置为 2.0，仅当其大小超过当前缓存<xref:System.Windows.Media.TileBrush>大小的两倍时，才需要重新生成 该属性的缓存。  
  
 下面的示例演示如何对 使用 缓存提示选项<xref:System.Windows.Media.DrawingBrush>。  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## <a name="see-also"></a>另请参阅

- [优化 WPF 应用程序性能](optimizing-wpf-application-performance.md)
- [规划应用程序性能](planning-for-application-performance.md)
- [利用硬件](optimizing-performance-taking-advantage-of-hardware.md)
- [布局和设计](optimizing-performance-layout-and-design.md)
- [对象行为](optimizing-performance-object-behavior.md)
- [应用程序资源](optimizing-performance-application-resources.md)
- [文本](optimizing-performance-text.md)
- [数据绑定](optimizing-performance-data-binding.md)
- [其他性能建议](optimizing-performance-other-recommendations.md)
- [动画提示和技巧](../graphics-multimedia/animation-tips-and-tricks.md)
