---
title: 使用图像、图形和视觉对象进行绘制
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- painting [WPF], with images
- painting with visuals [WPF]
- brushes [WPF], painting with images
- brushes [WPF], painting with visuals
ms.assetid: 779aac3f-8d41-49d8-8130-768244aa2240
ms.openlocfilehash: e0e5e386b32425c87502d18a24e758193c14a5b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186921"
---
# <a name="painting-with-images-drawings-and-visuals"></a>使用图像、图形和视觉对象进行绘制
本主题<xref:System.Windows.Media.ImageBrush>介绍如何使用<xref:System.Windows.Media.DrawingBrush>和<xref:System.Windows.Media.VisualBrush>对象使用图像、或<xref:System.Windows.Media.Drawing>。 <xref:System.Windows.Media.Visual>  

<a name="prereqs"></a>
## <a name="prerequisites"></a>系统必备  
 要了解本主题，应熟悉 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供的不同画笔类型及其基本功能。 有关介绍，请参阅 [WPF 画笔概述](wpf-brushes-overview.md)。  
  
<a name="image"></a>
## <a name="paint-an-area-with-an-image"></a>使用图像绘制区域  
 用<xref:System.Windows.Media.ImageBrush>油漆区域<xref:System.Windows.Media.ImageSource>。 与 一起使用<xref:System.Windows.Media.ImageSource>的最常见类型<xref:System.Windows.Media.ImageBrush>是<xref:System.Windows.Media.Imaging.BitmapImage>，它描述了位图图形。 可以使用 对象<xref:System.Windows.Media.DrawingImage>进行绘制<xref:System.Windows.Media.Drawing>，但<xref:System.Windows.Media.DrawingBrush>使用 对象更简单。 有关<xref:System.Windows.Media.ImageSource>对象的详细信息，请参阅[映像概述](imaging-overview.md)。  
  
 要使用 进行<xref:System.Windows.Media.ImageBrush>绘制，请<xref:System.Windows.Media.Imaging.BitmapImage>创建 并使用它来加载位图内容。 然后，使用<xref:System.Windows.Media.Imaging.BitmapImage>设置<xref:System.Windows.Media.ImageBrush.ImageSource%2A>的属性<xref:System.Windows.Media.ImageBrush>。 最后，将<xref:System.Windows.Media.ImageBrush>应用 到要绘制的对象。  在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中还可以仅设置<xref:System.Windows.Media.ImageBrush.ImageSource%2A><xref:System.Windows.Media.ImageBrush>具有要加载的图像路径的属性。  
  
 与所有<xref:System.Windows.Media.Brush>对象一样，<xref:System.Windows.Media.ImageBrush>还可用于绘制对象，如形状、面板、控件和文本。 下图显示了可以使用 可以实现的一<xref:System.Windows.Media.ImageBrush>些效果。  
  
 ![ImageBrush 输出示例](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
使用 ImageBrush 绘制的对象  
  
 默认情况下，如果绘制<xref:System.Windows.Media.ImageBrush>区域的纵横比与图像不同，则拉伸其图像以完全填充要绘制的区域，从而扭曲图像。 可以通过<xref:System.Windows.Media.TileBrush.Stretch%2A>将属性的<xref:System.Windows.Media.Stretch.Fill>默认值更改为<xref:System.Windows.Media.Stretch.None>来<xref:System.Windows.Media.Stretch.Uniform>更改此行为。 <xref:System.Windows.Media.Stretch.UniformToFill> 因为<xref:System.Windows.Media.ImageBrush>是 的类型<xref:System.Windows.Media.TileBrush>，您可以准确指定图像画笔填充输出区域的方式，甚至创建模式。 有关高级<xref:System.Windows.Media.TileBrush>功能的详细信息，请参阅[TileBrush 概述](tilebrush-overview.md)。  
  
<a name="fillingpanelwithimage"></a>
## <a name="example-paint-an-object-with-a-bitmap-image"></a>示例：用位图图像绘制对象  
 下面的示例使用<xref:System.Windows.Media.ImageBrush>来绘制 的<xref:System.Windows.Controls.Panel.Background%2A>。 <xref:System.Windows.Controls.Canvas>  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>
## <a name="paint-an-area-with-a-drawing"></a>使用图形绘制区域  
 A<xref:System.Windows.Media.DrawingBrush>使您能够使用形状、文本、图像和视频绘制区域。 绘图画笔内的形状可能本身被绘制为纯色、渐变、图像，甚至另一个<xref:System.Windows.Media.DrawingBrush>。 下图演示了 的一<xref:System.Windows.Media.DrawingBrush>些用途。  
  
 ![DrawingBrush 输出示例](./media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
使用 DrawingBrush 绘制的对象  
  
 用<xref:System.Windows.Media.DrawingBrush><xref:System.Windows.Media.Drawing>对象绘制区域。 <xref:System.Windows.Media.Drawing>对象描述可见内容，如形状、位图、视频或文本行。 不同类型的图形描述不同类型的内容。 下面是不同类型图形对象的列表。  
  
- <xref:System.Windows.Media.GeometryDrawing>• 绘制形状。  
  
- <xref:System.Windows.Media.ImageDrawing>• 绘制图像。  
  
- <xref:System.Windows.Media.GlyphRunDrawing>• 绘制文本。  
  
- <xref:System.Windows.Media.VideoDrawing>• 播放音频或视频文件。  
  
- <xref:System.Windows.Media.DrawingGroup>• 绘制其他绘图。 使用图形组将其他图形合并到单个复合图形。  
  
 有关<xref:System.Windows.Media.Drawing>对象的详细信息，请参阅[绘图对象概述](drawing-objects-overview.md)。  
  
 像<xref:System.Windows.Media.ImageBrush>一个<xref:System.Windows.Media.DrawingBrush>一<xref:System.Windows.Media.DrawingBrush.Drawing%2A>个，拉伸它来填充其输出区域。 可以通过从 其默认设置更改<xref:System.Windows.Media.TileBrush.Stretch%2A>属性来<xref:System.Windows.Media.Stretch.Fill>重写此行为。 有关更多信息，请参见 <xref:System.Windows.Media.TileBrush.Stretch%2A> 属性。  
  
<a name="fillingareawithdrawingbrushexample"></a>
## <a name="example-paint-an-object-with-a-drawing"></a>示例：使用图形绘制对象  
 下面的示例显示如何使用三个椭圆形的图形绘制对象。 A<xref:System.Windows.Media.GeometryDrawing>用于描述椭圆。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>
## <a name="paint-an-area-with-a-visual"></a>使用视觉对象绘制区域  
 在所有画笔中最通用和最强大的，<xref:System.Windows.Media.VisualBrush>用 油漆区域。 <xref:System.Windows.Media.Visual> A<xref:System.Windows.Media.Visual>是一种低级图形类型，用作许多有用图形组件的祖先。 例如，<xref:System.Windows.Window>和<xref:System.Windows.FrameworkElement><xref:System.Windows.Controls.Control>类是所有类型的<xref:System.Windows.Media.Visual>对象。 使用<xref:System.Windows.Media.VisualBrush>，可以使用几乎任何[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]图形对象绘制区域。  
  
> [!NOTE]
> 尽管<xref:System.Windows.Media.VisualBrush>是<xref:System.Windows.Freezable>对象的一种类型，但当其<xref:System.Windows.Media.VisualBrush.Visual%2A>属性设置为 以外的`null`值时，它不能冻结（使只读）。  
  
 有两种方法可以指定<xref:System.Windows.Media.VisualBrush.Visual%2A>的内容。 <xref:System.Windows.Media.VisualBrush>  
  
- 创建新，<xref:System.Windows.Media.Visual>并用它来设置<xref:System.Windows.Media.VisualBrush.Visual%2A>的属性。 <xref:System.Windows.Media.VisualBrush> 有关示例，请参阅后面的[示例：使用视觉对象绘制对象](#examplevisualbrush1)一节。  
  
- 使用现有<xref:System.Windows.Media.Visual>，这将创建目标的<xref:System.Windows.Media.Visual>重复图像。 然后，可以使用<xref:System.Windows.Media.VisualBrush>创建有趣的效果，如反射和放大倍率。 有关示例，请参阅[示例：创建反射](#examplevisualbrush2)一节。  
  
 当您为 和<xref:System.Windows.Media.VisualBrush.Visual%2A><xref:System.Windows.Media.VisualBrush>定义 new<xref:System.Windows.Media.Visual>时<xref:System.Windows.UIElement>，该 和 是 （如面板或控件）， 当<xref:System.Windows.UIElement><xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A>属性设置为`true`时，布局系统在 及其子元素上运行。 但是，根<xref:System.Windows.UIElement>基本上与系统的其余部分隔离：样式，外部布局不能渗透到此边界中。 因此，应显式指定根<xref:System.Windows.UIElement>的大小，因为它的唯一父级是 ，<xref:System.Windows.Media.VisualBrush>因此它不能自动调整自身大小到要绘制的区域。 有关 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的布局的更多信息，请参阅[布局](../advanced/layout.md)。  
  
 喜欢<xref:System.Windows.Media.ImageBrush><xref:System.Windows.Media.DrawingBrush>和<xref:System.Windows.Media.VisualBrush>，拉伸其内容以填充其输出区域。 可以通过从 其默认设置更改<xref:System.Windows.Media.TileBrush.Stretch%2A>属性来<xref:System.Windows.Media.Stretch.Fill>重写此行为。 有关更多信息，请参见 <xref:System.Windows.Media.TileBrush.Stretch%2A> 属性。  
  
<a name="examplevisualbrush1"></a>
## <a name="example-paint-an-object-with-a-visual"></a>示例：使用视觉对象绘制对象  
 在下面的示例中，许多控件和面板用于绘制矩形。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>
## <a name="example-create-a-reflection"></a>示例：创建反射  
 前面的示例演示如何创建一个用于背景的新<xref:System.Windows.Media.Visual>。 您还可以使用 显示<xref:System.Windows.Media.VisualBrush>现有视觉对象;此功能使您能够生成有趣的视觉效果，如反射和放大倍率。 下面的示例使用<xref:System.Windows.Media.VisualBrush>创建包含多个元素的 的<xref:System.Windows.Controls.Border>反射。 下图显示了此示例生成的输出。  
  
 ![反射的 Visual 对象](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
反射的 Visual 对象  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 有关显示如何放大屏幕部分以及如何创建反射的更多示例，请参阅 [VisualBrush 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)。  
  
<a name="tilebrush"></a>
## <a name="tilebrush-features"></a>TileBrush 功能  
 <xref:System.Windows.Media.ImageBrush><xref:System.Windows.Media.DrawingBrush>，是<xref:System.Windows.Media.VisualBrush>对象的类型<xref:System.Windows.Media.TileBrush>。 <xref:System.Windows.Media.TileBrush>对象可对图像、绘图或视觉对象绘制区域的方式进行大量控制。 例如，不使用单个拉伸图像绘制区域，而是使用创建图案的一系列平铺图像绘制区域。  
  
 A<xref:System.Windows.Media.TileBrush>有三个主要组件：内容、磁贴和输出区域。  
  
 ![TileBrush 组成部分](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
具有单个图块的 TileBrush 的组成部分  
  
 ![已平铺的 TileBrush 组件](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
使用多个平铺的 TileBrush 组件  
  
 有关<xref:System.Windows.Media.TileBrush>对象平铺功能的详细信息，请参阅[TileBrush 概述](tilebrush-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [TileBrush 概述](tilebrush-overview.md)
- [WPF 画笔概述](wpf-brushes-overview.md)
- [图像处理概述](imaging-overview.md)
- [Drawing 对象概述](drawing-objects-overview.md)
- [不透明蒙板概述](opacity-masks-overview.md)
- [WPF 图形呈现概述](wpf-graphics-rendering-overview.md)
- [ImageBrush 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [VisualBrush 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
