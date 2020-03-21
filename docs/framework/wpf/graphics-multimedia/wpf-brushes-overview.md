---
title: 画笔概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: 7a9474b392052900952f5b677ad94b16025de8dd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186580"
---
# <a name="wpf-brushes-overview"></a>WPF 画笔概述
屏幕上可见的一切可见，因为它是由画笔绘制的。 例如，画笔用于描述按钮的背景、文本的前景和形状的填充。 本主题介绍使用[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]画笔绘画的概念，并提供示例。 借助画笔，可以利用任意内容（从简单的纯色到复杂的图案和图像集）绘制 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 对象。  
  
<a name="paintingwithbrush"></a>
## <a name="painting-with-a-brush"></a>用画笔绘画  
 具有<xref:System.Windows.Media.Brush>输出的区域的"绘制"。 不同的画笔具有不同的输出类型。 有些画笔用纯色绘制区域，其他画笔使用渐变、图案、图像或绘图绘制区域。 下图显示了每种不同<xref:System.Windows.Media.Brush>类型的示例。  
  
 ![画笔类型](./media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
画笔示例  
  
 大多数可视对象都允许您指定绘制它们的方式。 下表列出了可以使用 的<xref:System.Windows.Media.Brush>一些常见对象和属性。  
  
|类|画笔属性|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 以下各节介绍不同类型的<xref:System.Windows.Media.Brush>类型，并提供每种类型的示例。  
  
<a name="paintwithsolidcolorbrush"></a>
## <a name="paint-with-a-solid-color"></a>纯色涂料  
 A<xref:System.Windows.Media.SolidColorBrush>用固体<xref:System.Windows.Media.Color>绘制区域。 指定<xref:System.Windows.Media.SolidColorBrush.Color%2A><xref:System.Windows.Media.SolidColorBrush>： 的方法有多种，例如，您可以指定其 alpha、红色、蓝色和绿色通道或使用<xref:System.Windows.Media.Colors>类提供的预定义颜色之一。  
  
 下面的示例使用 来<xref:System.Windows.Media.SolidColorBrush>绘制 的<xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle>。 下图显示了绘制的矩形。  
  
 ![使用 SolidColorBrush 绘制的矩形](./media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
使用纯色画笔绘制的矩形  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 有关该类的详细信息，<xref:System.Windows.Media.SolidColorBrush>请参阅[使用纯色和渐变概述进行绘画](painting-with-solid-colors-and-gradients-overview.md)。  
  
<a name="paintwithlineargradientbrush"></a>
## <a name="paint-with-a-linear-gradient"></a>使用线性渐变绘制  
 绘制<xref:System.Windows.Media.LinearGradientBrush>具有线性渐变的区域。 线性渐变在线条（渐变轴）中混合了两种或多种颜色。 您可以使用<xref:System.Windows.Media.GradientStop>对象指定渐变中的颜色及其位置。  
  
 下面的示例使用 来<xref:System.Windows.Media.LinearGradientBrush>绘制 的<xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle>。 下图显示了绘制的矩形。  
  
 ![使用 LinearGradientBrush 绘制的矩形](./media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
使用线性渐变画笔绘制的矩形  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 有关该类的详细信息，<xref:System.Windows.Media.LinearGradientBrush>请参阅[使用纯色和渐变概述进行绘画](painting-with-solid-colors-and-gradients-overview.md)。  
  
<a name="paintwithradialgradientbrush"></a>
## <a name="paint-with-a-radial-gradient"></a>使用径向渐变绘制  
 绘制<xref:System.Windows.Media.RadialGradientBrush>具有径向渐变的区域。 径向渐变在一个圆圈上混合两种或多种颜色。 与类一<xref:System.Windows.Media.LinearGradientBrush>样，使用<xref:System.Windows.Media.GradientStop>对象指定渐变中的颜色及其位置。  
  
 下面的示例使用 来<xref:System.Windows.Media.RadialGradientBrush>绘制 的<xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle>。 下图显示了绘制的矩形。  
  
 ![使用 RadialGradientBrush 绘制的矩形](./media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
使用径向渐变画笔绘制的矩形  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 有关该类的详细信息，<xref:System.Windows.Media.RadialGradientBrush>请参阅[使用纯色和渐变概述进行绘画](painting-with-solid-colors-and-gradients-overview.md)。  
  
<a name="paintwithimage"></a>
## <a name="paint-with-an-image"></a>使用图像绘制  
 用<xref:System.Windows.Media.ImageBrush>油漆区域<xref:System.Windows.Media.ImageSource>。  
  
 下面的示例使用<xref:System.Windows.Media.ImageBrush>来绘制 的<xref:System.Windows.Shapes.Shape.Fill%2A>。 <xref:System.Windows.Shapes.Rectangle> 下图显示了绘制的矩形。  
  
 ![使用 ImageBrush 绘制的矩形](./media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
使用图像绘制的矩形  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 有关该类的详细信息，<xref:System.Windows.Media.ImageBrush>请参阅[使用图像、绘图和视觉对象进行绘画](painting-with-images-drawings-and-visuals.md)。  
  
<a name="paintwithdrawing"></a>
## <a name="paint-with-a-drawing"></a>使用绘图绘制  
 a<xref:System.Windows.Media.DrawingBrush>用 绘制区域<xref:System.Windows.Media.Drawing>。 可以<xref:System.Windows.Media.Drawing>包含形状、图像、文本和媒体。  
  
 下面的示例使用 来<xref:System.Windows.Media.DrawingBrush>绘制 的<xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle>。 下图显示了绘制的矩形。  
  
 ![使用 DrawingBrush 绘制的矩形](./media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
使用绘图画笔绘制的矩形  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 有关该类的详细信息，<xref:System.Windows.Media.DrawingBrush>请参阅[使用图像、绘图和视觉对象进行绘画](painting-with-images-drawings-and-visuals.md)。  
  
<a name="paintwithvisual"></a>
## <a name="paint-with-a-visual"></a>使用视觉对象绘制  
 用<xref:System.Windows.Media.VisualBrush><xref:System.Windows.Media.Visual>对象绘制区域。 Visual 对象的示例包括<xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Page>、<xref:System.Windows.Controls.MediaElement>和 。 还<xref:System.Windows.Media.VisualBrush>使您能够将应用程序某一部分的内容投影到另一个区域;它对于创建反射效果和放大屏幕部分非常有用。  
  
 下面的示例使用 来<xref:System.Windows.Media.VisualBrush>绘制 的<xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle>。 下图显示了绘制的矩形。  
  
 ![使用 VisualBrush 绘制的矩形](./media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
使用视觉画笔绘制的矩形  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 有关该类的详细信息，<xref:System.Windows.Media.VisualBrush>请参阅[使用图像、绘图和视觉对象进行绘画](painting-with-images-drawings-and-visuals.md)。  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>
## <a name="paint-using-predefined-and-system-brushes"></a>使用预定义和系统画笔绘制  
 为方便起见，Windows 演示文稿基础 （WPF） 提供了一组预定义和系统画笔，可用于绘制对象。  
  
- 有关可用预定义画笔的列表，请参阅类<xref:System.Windows.Media.Brushes>。 有关演示如何使用预定义的画笔的示例，请参阅[使用纯色绘制区域](how-to-paint-an-area-with-a-solid-color.md)。  
  
- 有关可用系统画笔的列表，请参阅类<xref:System.Windows.SystemColors>。 例如，请参阅[使用系统画笔绘制区域](how-to-paint-an-area-with-a-system-brush.md)。  
  
<a name="commonbrushfeatures"></a>
## <a name="common-brush-features"></a>常见画笔功能  
 <xref:System.Windows.Media.Brush>对象提供可用于<xref:System.Windows.Media.Brush.Opacity%2A>使画笔透明或部分透明的属性。 <xref:System.Windows.Media.Brush.Opacity%2A>值 0 使画笔完全透明，而<xref:System.Windows.Media.Brush.Opacity%2A>值 1 使画笔完全不透明。 下面的示例使用 属性<xref:System.Windows.Media.Brush.Opacity%2A>使<xref:System.Windows.Media.SolidColorBrush>25% 不透明。  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 如果画笔包含部分透明的颜色，则通过乘法与画笔的不透明度值组合颜色的不透明度值。 例如，如果画笔的不向性值为 0.5，并且画笔中使用的颜色也具有 0.5 的不连续值，则输出颜色的不向性值为 0.25。  
  
> [!NOTE]
> 与使用画笔<xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType>属性更改整个元素的不向性相比，更改画笔的不向性值更有效。  
  
 您可以使用画笔<xref:System.Windows.Media.Brush.Transform%2A>或<xref:System.Windows.Media.Brush.RelativeTransform%2A>属性旋转、缩放、倾斜和翻译画笔的内容。 有关详细信息，请参阅[画笔转换概述](brush-transformation-overview.md)。  
  
 因为它们是<xref:System.Windows.Media.Animation.Animatable>对象，<xref:System.Windows.Media.Brush>因此可以对对象进行动画处理。 有关详细信息，请参阅 [动画概述](animation-overview.md)。  
  
<a name="freezable_features"></a>
### <a name="freezable-features"></a>Freezable 功能  
 由于该<xref:System.Windows.Freezable>类从类继承，因此<xref:System.Windows.Media.Brush>提供了几个特殊功能：<xref:System.Windows.Media.Brush>对象可以声明为[资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)、在多个对象之间共享和克隆。 此外，除所有类型<xref:System.Windows.Media.Brush>外<xref:System.Windows.Media.VisualBrush>，还可以只读，以提高性能并使线程安全。  
  
 有关<xref:System.Windows.Freezable>对象提供的不同要素的详细信息，请参阅[可冻结对象概述](../advanced/freezable-objects-overview.md)。  
  
 有关无法冻结对象的原因<xref:System.Windows.Media.VisualBrush>的详细信息，请参阅<xref:System.Windows.Media.VisualBrush>类型页。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.Brushes>
- [使用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)
- [使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
- [Freezable 对象概述](../advanced/freezable-objects-overview.md)
- [画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
- [ImageBrush 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [VisualBrush 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
- [如何使用主题](brushes-how-to-topics.md)
- [其他性能建议](../advanced/optimizing-performance-other-recommendations.md)
