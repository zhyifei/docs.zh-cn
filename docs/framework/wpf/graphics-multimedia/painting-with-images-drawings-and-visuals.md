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
ms.openlocfilehash: e80132a5467f932e5569787f43427044ba2be256
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929599"
---
# <a name="painting-with-images-drawings-and-visuals"></a>使用图像、图形和视觉对象进行绘制
本主题说明如何使用<xref:System.Windows.Media.ImageBrush>、 <xref:System.Windows.Media.DrawingBrush>和<xref:System.Windows.Media.VisualBrush>对象<xref:System.Windows.Media.Drawing>绘制带有图像、或的<xref:System.Windows.Media.Visual>区域。  

<a name="prereqs"></a>   
## <a name="prerequisites"></a>系统必备  
 要了解本主题，应熟悉 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供的不同画笔类型及其基本功能。 有关介绍，请参阅 [WPF 画笔概述](wpf-brushes-overview.md)。  
  
<a name="image"></a>   
## <a name="paint-an-area-with-an-image"></a>使用图像绘制区域  
 <xref:System.Windows.Media.ImageBrush> 使用<xref:System.Windows.Media.ImageSource>绘制区域。 与一起使用的最<xref:System.Windows.Media.ImageSource>常见类型<xref:System.Windows.Media.Imaging.BitmapImage>是,它描述位图图形。 <xref:System.Windows.Media.ImageBrush> 您可以使用<xref:System.Windows.Media.DrawingImage>来绘制<xref:System.Windows.Media.Drawing>对象, 但使用<xref:System.Windows.Media.DrawingBrush>是更简单的方法。 有关<xref:System.Windows.Media.ImageSource>对象的详细信息, 请参阅[图像处理概述](imaging-overview.md)。  
  
 若要使用<xref:System.Windows.Media.ImageBrush>绘制, 请<xref:System.Windows.Media.Imaging.BitmapImage>创建并使用它来加载位图内容。 然后, 使用<xref:System.Windows.Media.Imaging.BitmapImage> <xref:System.Windows.Media.ImageBrush.ImageSource%2A>设置的属性<xref:System.Windows.Media.ImageBrush>。 最后, 将应用<xref:System.Windows.Media.ImageBrush>到要绘制的对象。  在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中, 您还可以<xref:System.Windows.Media.ImageBrush.ImageSource%2A>将的<xref:System.Windows.Media.ImageBrush>属性设置为要加载的图像的路径。  
  
 与所有<xref:System.Windows.Media.Brush>对象一样<xref:System.Windows.Media.ImageBrush> , 可用于绘制对象 (如形状、面板、控件和文本)。 下图显示了可使用<xref:System.Windows.Media.ImageBrush>实现的一些效果。  
  
 ![System.windows.media.imagebrush> 输出示例](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
使用 ImageBrush 绘制的对象  
  
 默认情况下, <xref:System.Windows.Media.ImageBrush>拉伸图像以完全填充要绘制的区域, 这可能会使图像在绘制区域与图像的长宽比时扭曲。 可以<xref:System.Windows.Media.TileBrush.Stretch%2A>通过将属性从其默认<xref:System.Windows.Media.Stretch.Uniform> <xref:System.Windows.Media.Stretch.Fill>值更改为、或<xref:System.Windows.Media.Stretch.UniformToFill>来<xref:System.Windows.Media.Stretch.None>更改此行为。 由于<xref:System.Windows.Media.ImageBrush>是的<xref:System.Windows.Media.TileBrush>一种类型, 因此你可以精确指定图像画笔如何填充输出区域, 甚至还可以创建图案。 有关高级<xref:System.Windows.Media.TileBrush>功能的详细信息, 请参阅[TileBrush 概述](tilebrush-overview.md)。  
  
<a name="fillingpanelwithimage"></a>   
## <a name="example-paint-an-object-with-a-bitmap-image"></a>示例:使用位图图像绘制对象  
 下面的示例使用<xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Controls.Panel.Background%2A>绘制的<xref:System.Windows.Controls.Canvas>。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>   
## <a name="paint-an-area-with-a-drawing"></a>使用图形绘制区域  
 <xref:System.Windows.Media.DrawingBrush>利用, 您可以使用形状、文本、图像和视频绘制一个区域。 绘图画笔内的形状本身可能使用纯色、渐变、图像甚至另一种<xref:System.Windows.Media.DrawingBrush>颜色进行绘制。 下图演示了<xref:System.Windows.Media.DrawingBrush>的某些用法。  
  
 ![System.windows.media.drawingbrush> 输出示例](./media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
使用 DrawingBrush 绘制的对象  
  
 <xref:System.Windows.Media.DrawingBrush> 使用<xref:System.Windows.Media.Drawing>对象绘制区域。 <xref:System.Windows.Media.Drawing>对象描述可见内容, 如形状、位图、视频或文本行。 不同类型的图形描述不同类型的内容。 下面是不同类型图形对象的列表。  
  
- <xref:System.Windows.Media.GeometryDrawing>–绘制形状。  
  
- <xref:System.Windows.Media.ImageDrawing>–绘制图像。  
  
- <xref:System.Windows.Media.GlyphRunDrawing>–绘制文本。  
  
- <xref:System.Windows.Media.VideoDrawing>–播放音频或视频文件。  
  
- <xref:System.Windows.Media.DrawingGroup>–绘制其他绘图。 使用图形组将其他图形合并到单个复合图形。  
  
 有关<xref:System.Windows.Media.Drawing>对象的详细信息, 请参阅[绘图对象概述](drawing-objects-overview.md)。  
  
 <xref:System.Windows.Media.DrawingBrush.Drawing%2A>像一样<xref:System.Windows.Media.ImageBrush>, 会对其进行拉伸以填充<xref:System.Windows.Media.DrawingBrush>其输出区域。 可以通过从的默认<xref:System.Windows.Media.TileBrush.Stretch%2A> <xref:System.Windows.Media.Stretch.Fill>设置中更改属性来重写此行为。 有关更多信息，请参见 <xref:System.Windows.Media.TileBrush.Stretch%2A> 属性。  
  
<a name="fillingareawithdrawingbrushexample"></a>   
## <a name="example-paint-an-object-with-a-drawing"></a>示例:使用 Drawing 绘制对象  
 下面的示例显示如何使用三个椭圆形的图形绘制对象。 <xref:System.Windows.Media.GeometryDrawing>用于描述省略号。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>   
## <a name="paint-an-area-with-a-visual"></a>使用视觉对象绘制区域  
 所有画笔的功能最多且功能强大, <xref:System.Windows.Media.VisualBrush>可<xref:System.Windows.Media.Visual>使用绘制一个区域。 <xref:System.Windows.Media.Visual>是一种低级别图形类型, 用作许多有用图形组件的上级。 例如<xref:System.Windows.Window>,、 <xref:System.Windows.FrameworkElement>和<xref:System.Windows.Controls.Control>类都是对象的<xref:System.Windows.Media.Visual>类型。 使用, 可以绘制几乎任何[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]图形对象的区域。 <xref:System.Windows.Media.VisualBrush>  
  
> [!NOTE]
> 尽管<xref:System.Windows.Media.VisualBrush>是<xref:System.Windows.Freezable>对象的一种类型, 但它的<xref:System.Windows.Media.VisualBrush.Visual%2A> `null`属性设置为之外的值时, 不能将其冻结 (变为只读)。  
  
 可以通过两种方式来指定<xref:System.Windows.Media.VisualBrush.Visual%2A>的内容。 <xref:System.Windows.Media.VisualBrush>  
  
- 创建一个新<xref:System.Windows.Media.Visual>的, 并使用它来<xref:System.Windows.Media.VisualBrush.Visual%2A>设置的<xref:System.Windows.Media.VisualBrush>属性。 有关示例, 请参阅[示例:使用下面的视觉](#examplevisualbrush1)对象绘制对象。  
  
- 使用现有<xref:System.Windows.Media.Visual>的, 它创建目标<xref:System.Windows.Media.Visual>的重复映像。 然后, 可以使用<xref:System.Windows.Media.VisualBrush>来创建有趣的效果, 如反射和放大。 有关示例, 请参阅[示例:创建反射](#examplevisualbrush2)部分。  
  
 当你为提供一个<xref:System.Windows.Media.VisualBrush.Visual%2A>新<xref:System.Windows.Media.VisualBrush>的并<xref:System.Windows.UIElement> <xref:System.Windows.UIElement> <xref:System.Windows.Media.Visual>为 (如面板或控件) 定义新的时, <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A>布局系统将在及其子元素上运行 (当属性设置为`true`时)。 不过, 该根<xref:System.Windows.UIElement>实质上与系统的其余部分隔离: 样式, 而外部布局不能渗透此边界。 因此, 您应显式指定根<xref:System.Windows.UIElement>的大小, 因为它的<xref:System.Windows.Media.VisualBrush>唯一父级为, 因此它无法自动调整自身的大小。 有关 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的布局的更多信息，请参阅[布局](../advanced/layout.md)。  
  
 与<xref:System.Windows.Media.ImageBrush>和<xref:System.Windows.Media.DrawingBrush>一样,<xref:System.Windows.Media.VisualBrush>会拉伸其内容来填充输出区域。 可以通过从的默认<xref:System.Windows.Media.TileBrush.Stretch%2A> <xref:System.Windows.Media.Stretch.Fill>设置中更改属性来重写此行为。 有关更多信息，请参见 <xref:System.Windows.Media.TileBrush.Stretch%2A> 属性。  
  
<a name="examplevisualbrush1"></a>   
## <a name="example-paint-an-object-with-a-visual"></a>示例:使用视觉对象绘制对象  
 在下面的示例中，许多控件和面板用于绘制矩形。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>   
## <a name="example-create-a-reflection"></a>示例:创建反射  
 前面的示例演示了如何创建新<xref:System.Windows.Media.Visual>的以用作背景。 你还可以使用<xref:System.Windows.Media.VisualBrush>来显示现有视觉对象; 此功能使你能够生成有趣的视觉效果, 例如反射和放大。 下面的示例使用<xref:System.Windows.Media.VisualBrush>创建包含多个元素的的反射。 <xref:System.Windows.Controls.Border> 下图显示了此示例生成的输出。  
  
 ![反射的视觉对象](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
反射的 Visual 对象  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 有关显示如何放大屏幕部分以及如何创建反射的更多示例，请参阅 [VisualBrush 示例](https://go.microsoft.com/fwlink/?LinkID=160049)。  
  
<a name="tilebrush"></a>   
## <a name="tilebrush-features"></a>TileBrush 功能  
 <xref:System.Windows.Media.ImageBrush>、 <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.TileBrush>和<xref:System.Windows.Media.VisualBrush>是对象的类型。 <xref:System.Windows.Media.TileBrush>通过对象, 您可以很好地控制如何使用图像、绘图或视觉对象绘制区域。 例如，不使用单个拉伸图像绘制区域，而是使用创建图案的一系列平铺图像绘制区域。  
  
 <xref:System.Windows.Media.TileBrush>有三个主要组件: 内容、磁贴和输出区域。  
  
 ![TileBrush 组件](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
具有单个图块的 TileBrush 的组成部分  
  
 ![平铺 TileBrush 的组件](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
使用多个平铺的 TileBrush 组件  
  
 有关<xref:System.Windows.Media.TileBrush>对象的平铺功能的详细信息, 请参阅[TileBrush 概述](tilebrush-overview.md)。  
  
## <a name="see-also"></a>请参阅

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
- [System.windows.media.imagebrush> 示例](https://go.microsoft.com/fwlink/?LinkID=160005)
- [VisualBrush 示例](https://go.microsoft.com/fwlink/?LinkID=160049)
