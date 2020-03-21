---
title: 形状和基本绘图概述
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
ms.openlocfilehash: 44104bec478f1fbb10acc0e591af43ea95fecdc5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141323"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>WPF 中的形状和基本图形概述
本主题概述了如何使用<xref:System.Windows.Shapes.Shape>对象进行绘制。 A<xref:System.Windows.Shapes.Shape>是一种<xref:System.Windows.UIElement>允许您将形状绘制到屏幕的类型。 由于对象是 UI<xref:System.Windows.Shapes.Shape>元素，因此可以在元素<xref:System.Windows.Controls.Panel>和大多数控件内使用对象。  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 为图形和绘制服务提供多层访问。 在顶层，<xref:System.Windows.Shapes.Shape>对象易于使用，并提供许多有用的功能，如布局和参与[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]事件系统。  

<a name="shapes"></a>
## <a name="shape-objects"></a>形状对象  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供了许多现成的<xref:System.Windows.Shapes.Shape>对象。  所有形状对象都从<xref:System.Windows.Shapes.Shape>类继承。 可用的形状对象包括<xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>、、、<xref:System.Windows.Shapes.Polygon><xref:System.Windows.Shapes.Polyline>和<xref:System.Windows.Shapes.Rectangle>。 <xref:System.Windows.Shapes.Shape>对象共享以下公共属性。  
  
- <xref:System.Windows.Shapes.Shape.Stroke%2A>：描述形状轮廓的绘制方式。  
  
- <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>：描述形状轮廓的厚度。  
  
- <xref:System.Windows.Shapes.Shape.Fill%2A>：描述形状内部如何绘制。  
  
- 用于指定坐标和顶点的数据属性，以与设备无关的像素来度量。  
  
 因为它们派生自<xref:System.Windows.UIElement>，形状对象可以在面板和大多数控件内使用。 该<xref:System.Windows.Controls.Canvas>面板是创建复杂图形的一个特别好的选择，因为它支持其子对象的绝对定位。  
  
 该<xref:System.Windows.Shapes.Line>类使您能够在两点之间画一条线。 以下示例演示了指定线坐标和笔划属性的几种方法。  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 下图显示了渲染的<xref:System.Windows.Shapes.Line>。  
  
 ![直线图示](./media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 尽管<xref:System.Windows.Shapes.Line>类确实提供属性<xref:System.Windows.Shapes.Shape.Fill%2A>，但设置它不起作用，<xref:System.Windows.Shapes.Line>因为 没有区域。  
  
 另一个常见的形状<xref:System.Windows.Shapes.Ellipse>是 。  通过定义<xref:System.Windows.Shapes.Ellipse>形状<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性创建 。 要绘制圆，请指定<xref:System.Windows.Shapes.Ellipse>其<xref:System.Windows.FrameworkElement.Width%2A><xref:System.Windows.FrameworkElement.Height%2A>和 值相等的 。  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 下图显示了渲染<xref:System.Windows.Shapes.Ellipse>的示例。  
  
 ![椭圆图示](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>
## <a name="using-paths-and-geometries"></a>使用路径和几何图形  
 该<xref:System.Windows.Shapes.Path>类使您能够绘制曲线和复杂形状。 这些曲线和形状使用<xref:System.Windows.Media.Geometry>对象进行描述。 要使用<xref:System.Windows.Shapes.Path>， 创建<xref:System.Windows.Media.Geometry>并使用它来设置<xref:System.Windows.Shapes.Path>对象的属性。 <xref:System.Windows.Shapes.Path.Data%2A>  
  
 有多种<xref:System.Windows.Media.Geometry>对象可供选择。 <xref:System.Windows.Media.RectangleGeometry><xref:System.Windows.Media.EllipseGeometry>和<xref:System.Windows.Media.LineGeometry>类描述相对简单的形状。 要创建更复杂的形状或创建曲线，请使用 。 <xref:System.Windows.Media.PathGeometry>  
  
<a name="pathgeometry"></a>
### <a name="pathgeometry-and-pathsegments"></a>PathGeometry and PathSegments  
 <xref:System.Windows.Media.PathGeometry>对象由一个或多个<xref:System.Windows.Media.PathFigure>对象组成;每个<xref:System.Windows.Media.PathFigure>表示不同的"图形"或形状。 每个<xref:System.Windows.Media.PathFigure>对象本身由一个或多个<xref:System.Windows.Media.PathSegment>对象组成，每个对象表示图形或形状的连接部分。 段类型包括以下内容： <xref:System.Windows.Media.LineSegment>、<xref:System.Windows.Media.BezierSegment>和<xref:System.Windows.Media.ArcSegment>。  
  
 在下面的示例中， a<xref:System.Windows.Shapes.Path>用于绘制二次贝塞尔曲线。  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 下图显示了呈现的形状。  
  
 ![路径图示](./media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 有关<xref:System.Windows.Media.PathGeometry>和其他<xref:System.Windows.Media.Geometry>类的详细信息，请参阅[几何概述](geometry-overview.md)。  
  
<a name="pathdatastring"></a>
### <a name="xaml-abbreviated-syntax"></a>XAML 缩写语法  
 在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中，还可以使用特殊的缩写语法来描述 。 <xref:System.Windows.Shapes.Path> 以下示例中，使用了缩写语法绘制复杂的形状。  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 下图显示了渲染的<xref:System.Windows.Shapes.Path>。  
  
 ![路径图示](./media/shape-ovw-path.PNG "shape_ovw_path")  
  
 <xref:System.Windows.Shapes.Path.Data%2A>属性字符串以 M 指示的"moveto"命令开头，该命令为 坐标<xref:System.Windows.Controls.Canvas>系中的路径建立起点。 <xref:System.Windows.Shapes.Path>数据参数区分大小写。 大写 M 表示新当前点的绝对位置。 小写字母 m 指示相对坐标。 第一段是一条三次贝塞尔曲线，该曲线以 (100,200) 开始，至 (400,175) 结束，使用 (100,25) 和 (400,350) 这两个控制点绘制。 此段由<xref:System.Windows.Shapes.Path.Data%2A>属性字符串中的 C 命令指示。 同样，大写的 C 指示绝对路径；小写的 c 指示相对路径。  
  
 第二段以绝对水平“lineto”命令 H 开头，它指定绘制一条从前面的子路径的终点 (400,175) 到新终点 (280,175) 的直线。 因为它是水平的"lineto"命令，因此指定的值是*x*坐标。  
  
 有关完整的路径语法，请参阅引用<xref:System.Windows.Shapes.Path.Data%2A>并使用[路径几何创建形状](how-to-create-a-shape-by-using-a-pathgeometry.md)。  
  
<a name="fillpaint"></a>
## <a name="painting-shapes"></a>绘制形状  
 <xref:System.Windows.Media.Brush>对象用于绘制形状的<xref:System.Windows.Shapes.Shape.Stroke%2A>和<xref:System.Windows.Shapes.Shape.Fill%2A>。 在下面的示例中，指定 了 描<xref:System.Windows.Shapes.Ellipse>边和填充。 注意画笔属性的有效输入可以是关键字或十六进制颜色值。 有关可用颜色关键字的详细信息，请参阅<xref:System.Windows.Media.Colors><xref:System.Windows.Media>命名空间中的类的属性。  
  
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
  
 下图显示了渲染的<xref:System.Windows.Shapes.Ellipse>。  
  
 ![椭圆](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")  
  
 或者，可以使用属性元素语法显式创建对象<xref:System.Windows.Media.SolidColorBrush>以绘制具有纯色的形状。  
  
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
  
 下图显示了呈现的形状。  
  
 ![SolidColorBrush 图示](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")  
  
 还可以使用渐变、图像、模式等绘制形状的笔划或填充。 有关详细信息，请参阅[具有纯色和渐变的绘画概述](painting-with-solid-colors-and-gradients-overview.md)。  
  
<a name="stretchableshapessection"></a>
## <a name="stretchable-shapes"></a>可拉伸的形状  
 <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>、、、<xref:System.Windows.Shapes.Polygon><xref:System.Windows.Shapes.Polyline>和<xref:System.Windows.Shapes.Rectangle>类都具有<xref:System.Windows.Shapes.Shape.Stretch%2A>属性。 此属性确定如何拉伸<xref:System.Windows.Shapes.Shape>对象的内容（要绘制的形状）以填充<xref:System.Windows.Shapes.Shape>对象的布局空间。 <xref:System.Windows.Shapes.Shape>对象的布局空间是布局系统<xref:System.Windows.Shapes.Shape>分配的空间量，因为布局系统具有显式<xref:System.Windows.FrameworkElement.Width%2A>设置和<xref:System.Windows.FrameworkElement.Height%2A>设置，也因为它<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>及其和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>设置。 有关 Windows 演示文稿基础中布局的其他信息，请参阅[布局](../advanced/layout.md)概述。  
  
 Stretch 属性采用下列值之一：  
  
- <xref:System.Windows.Media.Stretch.None>：<xref:System.Windows.Shapes.Shape>对象的内容不会拉伸。  
  
- <xref:System.Windows.Media.Stretch.Fill>：<xref:System.Windows.Shapes.Shape>对象的内容被拉伸以填充其布局空间。  不保留纵横比。  
  
- <xref:System.Windows.Media.Stretch.Uniform>：对象<xref:System.Windows.Shapes.Shape>的内容尽可能拉伸以填充其布局空间，同时保持其原始纵横比。  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>：对象<xref:System.Windows.Shapes.Shape>的内容被拉伸以完全填充其布局空间，同时保持其原始纵横比。  
  
 请注意，当<xref:System.Windows.Shapes.Shape>对象的内容拉伸时，<xref:System.Windows.Shapes.Shape>对象的轮廓在拉伸后绘制。  
  
 在下面的示例中，a<xref:System.Windows.Shapes.Polygon>用于绘制一个非常小的三角形，从 （0，0） 到 （0，1） 到 （1，1）。 对象的<xref:System.Windows.Shapes.Polygon><xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>设置为 100，其拉伸属性设置为"填充"。 因此，<xref:System.Windows.Shapes.Polygon>对象的内容（三角形）被拉伸以填充更大的空间。  
  
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
## <a name="transforming-shapes"></a>转换形状  
 类<xref:System.Windows.Media.Transform>提供了在二维平面中变换形状的方法。  不同类型的变换<xref:System.Windows.Media.RotateTransform>包括旋转 （ ）、刻度 （<xref:System.Windows.Media.ScaleTransform>）、倾斜<xref:System.Windows.Media.SkewTransform>（ ）<xref:System.Windows.Media.TranslateTransform>和转换 （ 。  
  
 应用于形状的常见转换就是旋转。  要旋转形状，请创建<xref:System.Windows.Media.RotateTransform>并指定其<xref:System.Windows.Media.RotateTransform.Angle%2A>。 a <xref:System.Windows.Media.RotateTransform.Angle%2A> 45 顺时针旋转元素 45 度;角度为 90 沿顺时针旋转元件 90 度;等等。 如果要控制<xref:System.Windows.Media.RotateTransform.CenterX%2A>元素<xref:System.Windows.Media.RotateTransform.CenterY%2A>旋转的点，则设置 和 属性。 这些属性值在被转换的元素的坐标空间中表示。 <xref:System.Windows.Media.RotateTransform.CenterX%2A>默认值<xref:System.Windows.Media.RotateTransform.CenterY%2A>为零。 最后，将<xref:System.Windows.Media.RotateTransform>应用 到 元素。 如果不希望变换影响布局，则设置形状的<xref:System.Windows.UIElement.RenderTransform%2A>属性。  
  
 在下面的示例中，a<xref:System.Windows.Media.RotateTransform>用于围绕形状的左上角 （0，0） 旋转 45 度的形状。  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 在以下示例中，另一个形状也旋转了 45 度，但这次它围绕点 (25,50) 旋转。  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 下图显示了应用两次转换的结果。  
  
 ![以不同中心点进行的 45 度旋转](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 在前面的示例中，对每一个形状对象应用了一次转换。 要将多个转换应用于形状（或任何其他 UI 元素），请使用 。 <xref:System.Windows.Media.TransformGroup>  
  
## <a name="see-also"></a>另请参阅

- [2D 图形和图像处理](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [使用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)
- [Geometry 概述](geometry-overview.md)
- [演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [动画概述](animation-overview.md)
