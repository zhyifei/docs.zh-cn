---
title: WPF 画笔概述
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1ef53da1febd6a49af8404e5889a728a1b7c649b
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="wpf-brushes-overview"></a>WPF 画笔概述
在你的屏幕上可见的所有内容是可见的因为它已由画笔绘制。 例如，画笔用于描述背景的按钮、 文本、 前景和形状的填充。 本主题介绍的概念与绘制[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]画笔并提供了示例。 借助画笔，可以利用任意内容（从简单的纯色到复杂的图案和图像集）绘制 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 对象。  
  
<a name="paintingwithbrush"></a>   
## <a name="painting-with-a-brush"></a>使用画笔绘制  
 A <xref:System.Windows.Media.Brush> ""使用绘制区域其输出。 不同画笔具有不同类型的输出。 某些画笔绘制带有纯色，具有渐变、 模式、 图像或绘图的其他人的区域。 下图显示的每个不同示例<xref:System.Windows.Media.Brush>类型。  
  
 ![画笔类型](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
画笔示例  
  
 大多数的视觉对象，可以指定绘制方式。 下表列出了一些常见的对象和属性可以使用<xref:System.Windows.Media.Brush>。  
  
|类|画笔属性|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 下列各节描述了不同<xref:System.Windows.Media.Brush>类型并提供每个示例。  
  
<a name="paintwithsolidcolorbrush"></a>   
## <a name="paint-with-a-solid-color"></a>使用纯色绘制  
 A<xref:System.Windows.Media.SolidColorBrush>使用纯色绘制区域<xref:System.Windows.Media.Color>。 有各种方法来指定<xref:System.Windows.Media.SolidColorBrush.Color%2A>的<xref:System.Windows.Media.SolidColorBrush>： 例如，可以指定它 alpha、 红色、 蓝方和绿色的通道，或使用提供的预定义颜色之一<xref:System.Windows.Media.Colors>类。  
  
 下面的示例使用<xref:System.Windows.Media.SolidColorBrush>来绘制<xref:System.Windows.Shapes.Shape.Fill%2A>的<xref:System.Windows.Shapes.Rectangle>。 下图显示绘制的矩形。  
  
 ![使用 SolidColorBrush 绘制的矩形](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
使用 SolidColorBrush 绘制的矩形  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 有关详细信息<xref:System.Windows.Media.SolidColorBrush>类，请参阅[使用纯色和渐变概述绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。  
  
<a name="paintwithlineargradientbrush"></a>   
## <a name="paint-with-a-linear-gradient"></a>使用线性渐变绘制  
 A<xref:System.Windows.Media.LinearGradientBrush>使用线性渐变绘制区域。 线性渐变混合横跨一条直线，渐变轴的两个或多个颜色。 你使用<xref:System.Windows.Media.GradientStop>指定颜色渐变或它们的位置中的对象。  
  
 下面的示例使用<xref:System.Windows.Media.LinearGradientBrush>来绘制<xref:System.Windows.Shapes.Shape.Fill%2A>的<xref:System.Windows.Shapes.Rectangle>。 下图显示绘制的矩形。  
  
 ![使用 LinearGradientBrush 绘制的矩形](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
使用 LinearGradientBrush 绘制的矩形  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 有关详细信息<xref:System.Windows.Media.LinearGradientBrush>类，请参阅[使用纯色和渐变概述绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。  
  
<a name="paintwithradialgradientbrush"></a>   
## <a name="paint-with-a-radial-gradient"></a>使用径向渐变绘制  
 A<xref:System.Windows.Media.RadialGradientBrush>使用径向渐变绘制区域。 径向渐变跨一个圆混合两个或多个颜色。 与<xref:System.Windows.Media.LinearGradientBrush>类，用于<xref:System.Windows.Media.GradientStop>指定颜色渐变或它们的位置中的对象。  
  
 下面的示例使用<xref:System.Windows.Media.RadialGradientBrush>来绘制<xref:System.Windows.Shapes.Shape.Fill%2A>的<xref:System.Windows.Shapes.Rectangle>。 下图显示绘制的矩形。  
  
 ![使用 RadialGradientBrush 绘制的矩形](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
使用 RadialGradientBrush 绘制的矩形  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 有关详细信息<xref:System.Windows.Media.RadialGradientBrush>类，请参阅[使用纯色和渐变概述绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。  
  
<a name="paintwithimage"></a>   
## <a name="paint-with-an-image"></a>使用图像进行绘制  
 <xref:System.Windows.Media.ImageBrush>使用绘制区域<xref:System.Windows.Media.ImageSource>。  
  
 下面的示例使用<xref:System.Windows.Media.ImageBrush>来绘制<xref:System.Windows.Shapes.Shape.Fill%2A>的<xref:System.Windows.Shapes.Rectangle>。 下图显示绘制的矩形。  
  
 ![使用 imagebrush 绘制的矩形](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
使用图像绘制的矩形  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 有关详细信息<xref:System.Windows.Media.ImageBrush>类，请参阅[使用图像、 图形和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)。  
  
<a name="paintwithdrawing"></a>   
## <a name="paint-with-a-drawing"></a>使用绘图进行绘制  
 A<xref:System.Windows.Media.DrawingBrush>使用绘制区域<xref:System.Windows.Media.Drawing>。 A<xref:System.Windows.Media.Drawing>可以包含形状、 图像、 文本和媒体。  
  
 下面的示例使用<xref:System.Windows.Media.DrawingBrush>来绘制<xref:System.Windows.Shapes.Shape.Fill%2A>的<xref:System.Windows.Shapes.Rectangle>。 下图显示绘制的矩形。  
  
 ![使用 DrawingBrush 绘制的矩形](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
使用 DrawingBrush 绘制的矩形  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 有关详细信息<xref:System.Windows.Media.DrawingBrush>类，请参阅[使用图像、 图形和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)。  
  
<a name="paintwithvisual"></a>   
## <a name="paint-with-a-visual"></a>使用视觉对象进行绘制  
 A<xref:System.Windows.Media.VisualBrush>使用绘制区域<xref:System.Windows.Media.Visual>对象。 视觉对象的示例包括<xref:System.Windows.Controls.Button>， <xref:System.Windows.Controls.Page>，和<xref:System.Windows.Controls.MediaElement>。 A<xref:System.Windows.Media.VisualBrush>还允许你将内容从另一个区域，则应用程序的一部分是用于创建反射效果和放大屏幕的部分非常有用。  
  
 下面的示例使用<xref:System.Windows.Media.VisualBrush>来绘制<xref:System.Windows.Shapes.Shape.Fill%2A>的<xref:System.Windows.Shapes.Rectangle>。 下图显示绘制的矩形。  
  
 ![使用 VisualBrush 绘制的矩形](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
使用 VisualBrush 绘制的矩形  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 有关详细信息<xref:System.Windows.Media.VisualBrush>类，请参阅[使用图像、 图形和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)。  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## <a name="paint-using-predefined-and-system-brushes"></a>使用预定义画笔和系统画笔绘制  
 为方便起见，Windows Presentation Foundation (WPF) 提供一组预定义和系统画笔可用于绘制对象。  
  
-   有关可用的预定义画笔的列表，请参阅<xref:System.Windows.Media.Brushes>类。 有关演示如何使用预定义的画笔的示例，请参阅[使用纯色绘制区域](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-solid-color.md)。  
  
-   可用系统画笔的列表，请参阅<xref:System.Windows.SystemColors>类。 有关示例，请参阅[使用系统画笔绘制区域](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)。  
  
<a name="commonbrushfeatures"></a>   
## <a name="common-brush-features"></a>常见的画笔功能  
 <xref:System.Windows.Media.Brush> 对象提供<xref:System.Windows.Media.Brush.Opacity%2A>属性，可以用于将透明或半透明的画笔。 <xref:System.Windows.Media.Brush.Opacity%2A>值为 0，则画笔完全透明，而<xref:System.Windows.Media.Brush.Opacity%2A>值为 1，则画笔完全不透明。 下面的示例使用<xref:System.Windows.Media.Brush.Opacity%2A>属性以使<xref:System.Windows.Media.SolidColorBrush>25%不透明。  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 如果画笔包含部分透明的颜色，颜色的不透明度值相结合通过不透明度值相乘的画笔。 例如，如果画笔有的不透明度值为 0.5，画笔中使用的颜色又有的不透明度值为 0.5，则输出颜色具有 0.25 的不透明度值。  
  
> [!NOTE]
>  更高效，若要更改的画笔的不透明度值，更改整个元素使用的不透明度比其<xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType>属性。  
  
 可以旋转、 缩放、 倾斜，和将画笔的内容转换使用其<xref:System.Windows.Media.Brush.Transform%2A>或<xref:System.Windows.Media.Brush.RelativeTransform%2A>属性。 有关详细信息，请参阅[画笔转换概述](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)。  
  
 因为它们是<xref:System.Windows.Media.Animation.Animatable>对象，<xref:System.Windows.Media.Brush>对象可以进行动画处理。 有关详细信息，请参阅 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。  
  
<a name="freezable_features"></a>   
### <a name="freezable-features"></a>Freezable 功能  
 因为它继承自<xref:System.Windows.Freezable>类，<xref:System.Windows.Media.Brush>类提供了一些特殊功能：<xref:System.Windows.Media.Brush>对象可声明为[资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)、 在多个对象之间共享和克隆。 此外，所有<xref:System.Windows.Media.Brush>类型除外<xref:System.Windows.Media.VisualBrush>可以生成只读的以提高性能，生成线程安全。  
  
 有关提供的不同功能的详细信息<xref:System.Windows.Freezable>对象，请参阅[可冻结对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)。  
  
 有关详细信息为何<xref:System.Windows.Media.VisualBrush>对象不能为冻结，请参阅<xref:System.Windows.Media.VisualBrush>类型页。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Brush>  
 <xref:System.Windows.Media.Brushes>  
 [使用纯色和渐变进行绘制概述](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [使用图像、绘图和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Freezable 对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [画笔示例](http://go.microsoft.com/fwlink/?LinkID=159973)  
 [ImageBrush 示例](http://go.microsoft.com/fwlink/?LinkID=160005)  
 [VisualBrush 示例](http://go.microsoft.com/fwlink/?LinkID=160049)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/brushes-how-to-topics.md)  
 [其他性能建议](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
