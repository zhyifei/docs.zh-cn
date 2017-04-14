---
title: "图形和多媒体 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "动画, 功能"
  - "图形功能"
  - "媒体, 功能"
  - "声音效果"
  - "转换效果"
  - "视频效果"
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# 图形和多媒体
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供对多媒体、矢量图形、动画和内容组成的支持，使开发人员可以轻松地生成悦目的用户界面和内容。  使用 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 可以创建矢量图形或复杂的动画并将媒体集成到应用程序中。  
  
 本主题介绍 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的图形、动画和媒体功能，使用这些功能，可以向应用程序添加图形、过渡效果、声音和视频。  
  
> [!NOTE]
>  强烈建议不要在 Windows 服务中使用 WPF 类型。  如果尝试在 Windows 服务中使用 WPF 类型，则服务可能无法按预期方式工作。  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>   
## WPF 4 在图形和多媒体方面的新增功能  
 已经做出了一些与图形和动画相关的更改。  
  
-   布局舍入  
  
     如果对象边缘落在像素设备的中间位置，则与 DPI 无关的图形系统可以创建呈现项目，如模糊或半透明边缘。  以前的 WPF 版本提供了像素捕捉来帮助处理这种情况。  Silverlight 2 引入了布局舍入，这是另外一种移动元素以使边缘落在整个像素边界上的方法。  WPF 现在支持使用 <xref:System.Windows.FrameworkElement> 上的 <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> 附加属性进行布局舍入。  
  
-   缓存合成  
  
     通过使用新的 <xref:System.Windows.Media.BitmapCache> 和 <xref:System.Windows.Media.BitmapCacheBrush> 类，可以将可视化树的复杂部分缓存为位图，并大大缩短呈现时间。  位图保持对用户输入（如鼠标单击）的响应能力，并且您可以将它画到其他元素上，就像使用任何刷子一样。  
  
-   像素着色器 3 支持  
  
     WPF 4 基于 WPF 3.5 SP1 中引入的 <xref:System.Windows.Media.Effects.ShaderEffect> 支持而构建，允许应用程序使用像素着色器 \(PS\) 3.0 版写入效果。  PS 3.0 着色器型号比 PS 2.0 更加复杂，从而允许在受支持的硬件上创建更多效果。  
  
-   缓动函数  
  
     您可以使用缓动函数增强动画，利用这些函数，可以对动画的行为进行其他控制。  例如，您可以将 <xref:System.Windows.Media.Animation.ElasticEase> 应用到动画以使动画出现弹出行为。  有关更多信息，请参见 <xref:System.Windows.Media.Animation> 命名空间中的缓动类型。  
  
<a name="graphics_and_rendering"></a>   
## 图形和呈现  
 WPF 包括对高质量的二维图形的支持。  功能包括画笔、几何图形、图像、形状和转换。  有关更多信息，请参见[图形](../../../../docs/framework/wpf/graphics-multimedia/graphics.md)。  图形元素的呈现基于 <xref:System.Windows.Media.Visual> 类。  屏幕上的可视化对象的结构通过可视化树进行描述。  有关更多信息，请参见 [WPF 图形呈现疑难解答](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)。  
  
### 二维形状  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 提供了一个库，包含用矢量绘制的常用 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 形状，如下图中演示的矩形和椭圆。  
  
 ![椭圆和矩形](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure4.png "WPFIntroFigure4")  
  
 这些内部的 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 形状不仅仅是形状：它们是可编程的元素，能够实现可通过最常见的控件（包括键盘输入和鼠标输入）实现的许多功能。  下面的示例演示如何处理单击 <xref:System.Windows.Shapes.Ellipse> 元素引起的 <xref:System.Windows.UIElement.MouseUp> 事件。  
  
```xaml  
<Window  
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
  x:Class="Window1" >  
  <Ellipse Fill="LightBlue" MouseUp="ellipseButton_MouseUp" />  
</Window>  
```  
  
```csharp  
public partial class Window1  : Window  
{  
    void ellipseButton_MouseUp(object sender, MouseButtonEventArgs e)  
    {  
        MessageBox.Show("You clicked the ellipse!");  
    }  
}  
```  
  
```vb  
Partial Public Class Window1  
    Inherits Window  
    Private Sub ellipseButton_MouseUp(ByVal sender As Object, ByVal e As MouseButtonEventArgs)  
        MessageBox.Show("You clicked the ellipse!")  
    End Sub  
End Class  
  
```  
  
 下面的插图显示前面 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 标记和代码隐藏的输出。  
  
 ![包含文本“单击省略号！”的窗口](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure12.png "WPFIntroFigure12")  
  
 有关更多信息，请参见 [WPF 中的形状和基本绘图概述](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)。  有关介绍性示例，请参见 [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037)（形状元素示例）。  
  
### 二维几何图形  
 当 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 提供的 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 形状不足时，可以使用 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中的几何图形和路径支持来创建自己的形状。  下面的插图显示如何使用几何图形来创建形状、如何将几何图形用作绘图画笔以及如何使用几何图形来剪裁其他 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 元素。  
  
 ![Path 的各种用法](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure5.png "WPFIntroFigure5")  
  
 有关更多信息，请参见[Geometry 概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)。  有关介绍性示例，请参见 [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989)（几何图形示例）。  
  
### 二维效果  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 提供了一个包含 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 类的库，可用来创建各种效果。  使用 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 的[!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]呈现功能，可以绘制具有渐变、位图、绘图和视频的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 元素，并借助于旋转、缩放和[扭曲](GTMT)功能来操作这些元素。  下图举例说明通过 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 画笔可获得的多种效果。  
  
 ![不同画笔的图示](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure6.png "WPFIntroFigure6")  
  
 有关更多信息，请参见 [WPF 画笔概述](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md)。  有关介绍性示例，请参见 [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973)（画笔示例）。  
  
<a name="rendering"></a>   
## 三维呈现  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 提供了一组[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]呈现功能，这些功能可与 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中的[!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]图形支持功能集成，以便您创建更加令人惊喜的布局、[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 和数据可视化效果。  在色谱的一端，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 允许您将 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 图像呈现到 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 形状的一个图面上，如下图中所示。  
  
 ![Visual3D 示例屏幕快照](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure13.png "WPFIntroFigure13")  
  
 有关更多信息，请参见[三维图形概述](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)。  有关介绍性示例，请参见 [3\-D Solids Sample](http://go.microsoft.com/fwlink/?LinkID=159964)（三维实体示例）。  
  
<a name="animation"></a>   
## 动画  
 使用动画，可以使控件和元素变大、晃动、旋转和淡化，还可以产生有趣的页面过渡和更多效果。  由于 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 允许您对大多数属性进行动画处理，因此，您不但可以对大多数 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 对象进行动画处理，而且还可以使用 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 来对您创建的自定义对象进行动画处理。  
  
 ![具有动画效果的立方体图](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure7.png "WPFIntroFigure7")  
  
 有关更多信息，请参见[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。  有关介绍性示例，请参见 [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969)（动画示例库）。  
  
<a name="media"></a>   
## 媒体  
 图像、视频和音频是用来传达信息和用户体验的富媒体方法。  
  
### 图像  
 图像（包括图标、背景甚至动画的一部分）是大多数应用程序的核心部分。  由于您经常需要使用图像，因此 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 提供了以各种方式处理图像的功能。  下图只说明了其中的一种方法。  
  
 ![样式示例屏幕快照](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro\_EventTriggers")  
  
 有关更多信息，请参见[图像处理概述](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)。  
  
### 视频和音频  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 的一个核心图形功能就是为处理多媒体（包括视频和音频）提供本机支持。  下面的示例说明如何在应用程序中插入媒体播放器。  
  
```xaml  
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />  
```  
  
 <xref:System.Windows.Controls.MediaElement> 既能够播放视频又能够播放音频，而且具有很好的可扩展性，可以用来方便地创建自定义的 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]。  
  
 有关更多信息，请参见 [多媒体概述](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)。  
  
## 请参阅  
 <xref:System.Windows.Media>   
 <xref:System.Windows.Media.Animation>   
 <xref:System.Windows.Media.Media3D>   
 [二维图形和图像处理](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [WPF 中的形状和基本绘图概述](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [使用纯色和渐变进行绘制概述](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [使用图像、绘图和 Visual 进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Animation and Timing](http://msdn.microsoft.com/zh-cn/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [3\-D Graphics](http://msdn.microsoft.com/zh-cn/565c1f3c-235b-47de-b05b-3b53ed63f1b8)   
 [Multimedia](http://msdn.microsoft.com/zh-cn/44a8dcd0-80cb-4db0-a222-87cde68c2fac)