---
title: Drawing 对象概述
ms.date: 03/30/2017
helpviewer_keywords:
- ImageDrawing objects [WPF]
- GlyphRunDrawing objects [WPF]
- GeometryDrawing objects [WPF]
- drawings [WPF], about drawings
- Drawing objects [WPF]
- DrawingGroup objects [WPF]
ms.assetid: 9b5ce5c0-e204-4320-a7a8-0b2210d62f88
ms.openlocfilehash: d739865a692fa5ef448eba91369015580e5eda97
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916313"
---
# <a name="drawing-objects-overview"></a>Drawing 对象概述
本主题<xref:System.Windows.Media.Drawing>介绍对象, 并说明如何使用它们高效地绘制形状、位图、文本和媒体。 使用<xref:System.Windows.Media.Drawing>对象在创建剪贴画、使用或<xref:System.Windows.Media.Visual>绘图<xref:System.Windows.Media.DrawingBrush>时使用对象。  

<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>什么是 Drawing 对象？  
 <xref:System.Windows.Media.Drawing>对象描述可见内容, 如形状、位图、视频或文本行。 不同类型的图形描述不同类型的内容。 下面是不同类型图形对象的列表。  
  
- <xref:System.Windows.Media.GeometryDrawing>–绘制形状。  
  
- <xref:System.Windows.Media.ImageDrawing>–绘制图像。  
  
- <xref:System.Windows.Media.GlyphRunDrawing>–绘制文本。  
  
- <xref:System.Windows.Media.VideoDrawing>–播放音频或视频文件。  
  
- <xref:System.Windows.Media.DrawingGroup>–绘制其他绘图。 使用图形组将其他图形合并到单个复合图形。  
  
 <xref:System.Windows.Media.Drawing>对象非常通用;可以通过多种方式使用<xref:System.Windows.Media.Drawing>对象。  
  
- 您可以使用<xref:System.Windows.Media.DrawingImage> <xref:System.Windows.Controls.Image>和控件将其显示为图像。  
  
- 可以将其与一起<xref:System.Windows.Media.DrawingBrush>使用来绘制对象, 如<xref:System.Windows.Controls.Page.Background%2A>的<xref:System.Windows.Controls.Page>。  
  
- 您可以使用它来描述的外观<xref:System.Windows.Media.DrawingVisual>。  
  
- 可以使用它来枚举的内容<xref:System.Windows.Media.Visual>。  
  
 WPF 提供能够绘制形状、位图、文本和媒体的其他对象类型。 例如, 您还可以使用<xref:System.Windows.Shapes.Shape>对象来绘制形状, 控件提供了另一种向应用程序中添加视频的<xref:System.Windows.Controls.MediaElement>方法。 那么, 何时应使用<xref:System.Windows.Media.Drawing>对象呢？ 当你可能牺牲框架级别功能来获得性能优势或需要<xref:System.Windows.Freezable>功能时。 由于<xref:System.Windows.Media.Drawing>对象不支持[布局](../advanced/layout.md)、输入和焦点, 因此它们提供性能优势, 使其非常适合用于描述背景、剪贴画以及用于<xref:System.Windows.Media.Visual>对象的低级别绘图。  
  
 由于对象是一个类型<xref:System.Windows.Freezable>对象, <xref:System.Windows.Media.Drawing>因此对象将获得几个特殊功能, 其中包括: 它们可以声明为[资源](../advanced/xaml-resources.md)、在多个对象之间共享、变为只读以提高性能、克隆和使线程安全。 有关<xref:System.Windows.Freezable>对象提供的不同功能的详细信息, 请参阅可[冻结对象概述](../advanced/freezable-objects-overview.md)。  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>绘制形状  
 若要绘制形状, 请使用<xref:System.Windows.Media.GeometryDrawing>。 几何绘图的<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>属性说明了要绘制的形状, 其<xref:System.Windows.Media.GeometryDrawing.Brush%2A>属性说明了应如何绘制形状的内部, 其<xref:System.Windows.Media.GeometryDrawing.Pen%2A>属性说明了应如何绘制形状的轮廓。  
  
 下面的示例使用<xref:System.Windows.Media.GeometryDrawing>绘制形状。 该形状由<xref:System.Windows.Media.GeometryGroup>和两个<xref:System.Windows.Media.EllipseGeometry>对象进行描述。 形状的内部将使用<xref:System.Windows.Media.LinearGradientBrush>绘制, 并<xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>使用绘制其轮廓。  
  
 此示例将创建以下<xref:System.Windows.Media.GeometryDrawing>项。  
  
 ![两个省略号的 system.windows.media.geometrydrawing>](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
一个 GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 有关完整示例，请参阅[创建 GeometryDrawing](how-to-create-a-geometrydrawing.md)。  
  
 其他<xref:System.Windows.Media.Geometry>类 ( <xref:System.Windows.Media.PathGeometry>例如) 可通过创建曲线和弧形来创建更复杂的形状。 有关<xref:System.Windows.Media.Geometry>对象的详细信息, 请参阅[几何概述](geometry-overview.md)。  
  
 有关绘制不使用<xref:System.Windows.Media.Drawing>对象的形状的其他方法的详细信息, 请参阅[WPF 中的形状和基本绘图概述](shapes-and-basic-drawing-in-wpf-overview.md)。  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>绘制图像  
 若要绘制图像, 请使用<xref:System.Windows.Media.ImageDrawing>。 对象的<xref:System.Windows.Media.ImageDrawing.ImageSource%2A>属性描述要绘制的图像, 其<xref:System.Windows.Media.ImageDrawing.Rect%2A>属性定义绘制图像的区域。 <xref:System.Windows.Media.ImageDrawing>  
  
 以下示例将在一个矩形的 (75,75) 处绘制一个 100 x 100 像素的图像。 下图显示了该<xref:System.Windows.Media.ImageDrawing>示例创建的。 添加了灰色边框以显示的边界<xref:System.Windows.Media.ImageDrawing>。  
  
 ![100 x 100 ImageDrawing 于&#40;75, 75&#41; ](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
100 x 100 的 ImageDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 有关图像的详细信息，请参阅[图像处理概述](imaging-overview.md)。  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>播放媒体（仅代码）  
  
> [!NOTE]
> 尽管可以<xref:System.Windows.Media.VideoDrawing>在中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]声明, 但只能使用代码加载和播放其媒体。 若要在中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]播放视频, <xref:System.Windows.Controls.MediaElement>请改用。  
  
 若要播放音频或视频文件, 请使用<xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer>和。 加载并播放媒体有两种方法。 第一种方法是单独<xref:System.Windows.Media.MediaPlayer>使用<xref:System.Windows.Media.VideoDrawing>和, 第二种方法是创建您<xref:System.Windows.Media.MediaPlayer>自己<xref:System.Windows.Media.MediaTimeline>的以便与和<xref:System.Windows.Media.VideoDrawing>一起使用。  
  
> [!NOTE]
> 当媒体随应用程序一起分发时，无法像图像那样将媒体文件用作项目资源。 在项目文件中，必须改为将媒体类型设置为 `Content` 并将 `CopyToOutputDirectory` 设置为 `PreserveNewest` 或 `Always`。  
  
 若要播放媒体而不创建<xref:System.Windows.Media.MediaTimeline>自己的媒体, 请执行以下步骤。  
  
1. 创建 <xref:System.Windows.Media.MediaPlayer> 对象。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. <xref:System.Windows.Media.MediaPlayer.Open%2A>使用方法加载媒体文件。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. 创建 <xref:System.Windows.Media.VideoDrawing>。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. 通过设置<xref:System.Windows.Media.VideoDrawing.Rect%2A>的<xref:System.Windows.Media.VideoDrawing>属性, 指定要绘制媒体的大小和位置。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. 将的<xref:System.Windows.Media.VideoDrawing.Player%2A> <xref:System.Windows.Media.VideoDrawing>属性设置为您创建<xref:System.Windows.Media.MediaPlayer>的。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. 使用的<xref:System.Windows.Media.MediaPlayer>方法开始播放媒体。 <xref:System.Windows.Media.MediaPlayer.Play%2A>  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 下面的示例使用<xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer>和来播放视频文件一次。  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 若要获取对媒体的其他计时控制, 请<xref:System.Windows.Media.MediaTimeline>将<xref:System.Windows.Media.MediaPlayer>与和<xref:System.Windows.Media.VideoDrawing>对象一起使用。 <xref:System.Windows.Media.MediaTimeline>使您能够指定是否应重复视频。 若要将<xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.VideoDrawing>与结合使用, 请执行以下步骤:  
  
1. <xref:System.Windows.Media.MediaTimeline>声明并设置其计时行为。  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. <xref:System.Windows.Media.MediaClock> 通过<xref:System.Windows.Media.MediaTimeline>创建。  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. 创建一个<xref:System.Windows.Media.MediaPlayer>并<xref:System.Windows.Media.MediaClock>使用来设置其<xref:System.Windows.Media.MediaPlayer.Clock%2A>属性。  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. 创建一个<xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer>并将分配给<xref:System.Windows.Media.VideoDrawing.Player%2A>的<xref:System.Windows.Media.VideoDrawing>属性。  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 下面的示例使用<xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer>带有和的<xref:System.Windows.Media.VideoDrawing>来反复播放视频。  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 请注意<xref:System.Windows.Media.MediaTimeline>, 当你使用时, 你将使用从<xref:System.Windows.Media.Animation.ClockController> <xref:System.Windows.Media.Animation.Clock.Controller%2A>的<xref:System.Windows.Media.MediaClock>属性返回的交互式来控制媒体播放, 而不是的交互式方法<xref:System.Windows.Media.MediaPlayer>。  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>绘制文本  
 若要绘制文本, 请使用<xref:System.Windows.Media.GlyphRunDrawing> <xref:System.Windows.Media.GlyphRun>和。 下面的示例使用<xref:System.Windows.Media.GlyphRunDrawing>绘制文本 "Hello World"。  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 <xref:System.Windows.Media.GlyphRun>是用于固定格式的文档演示和打印方案的低级别对象。 在屏幕上绘制文本的一种更简单的方法是<xref:System.Windows.Controls.Label>使用<xref:System.Windows.Controls.TextBlock>或。 有关<xref:System.Windows.Media.GlyphRun>的详细信息, 请参阅[GlyphRun 对象和字形元素](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md)概述。  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>复合绘图  
 <xref:System.Windows.Media.DrawingGroup>利用, 您可以将多个绘图组合成单个复合绘图。 通过使用<xref:System.Windows.Media.DrawingGroup>, 可以将形状、图像和文本合并到单个<xref:System.Windows.Media.Drawing>对象中。  
  
 下面的示例使用将<xref:System.Windows.Media.DrawingGroup>两个<xref:System.Windows.Media.GeometryDrawing>对象和一个<xref:System.Windows.Media.ImageDrawing>对象组合在一起。 本示例生成以下输出。  
  
 ![具有多个绘图的 DrawingGroup](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
复合绘图  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <xref:System.Windows.Media.DrawingGroup>还使你能够对其内容应用不透明蒙板、转换、位图效果以及其他操作。 <xref:System.Windows.Media.DrawingGroup>按照以下顺序应用操作: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>、 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>、 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>、 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>、和<xref:System.Windows.Media.DrawingGroup.Transform%2A>。  
  
 下图显示了应用<xref:System.Windows.Media.DrawingGroup>操作的顺序。  
  
 ![操作的 DrawingGroup 顺序](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
DrawingGroup 操作的顺序  
  
 下表介绍了可用于操作<xref:System.Windows.Media.DrawingGroup>对象内容的属性。  
  
|Property|描述|图示|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|更改所选<xref:System.Windows.Media.DrawingGroup>内容部分的不透明度。 有关示例，请参见 [如何：控制绘图](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90))的不透明度。|![具有不透明蒙版的 DrawingGroup](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|统一更改<xref:System.Windows.Media.DrawingGroup>内容的不透明度。 使用此属性可以使<xref:System.Windows.Media.Drawing>透明或部分透明。 有关示例，请参见 [如何：向绘图](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90))应用不透明蒙板。|![具有不同不透明度设置的 DrawingGroup](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|<xref:System.Windows.Media.Effects.BitmapEffect> 将<xref:System.Windows.Media.DrawingGroup>应用于内容。 有关示例，请参见 [如何：将 BitmapEffect 应用于绘图](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90))。|![具有 BlurBitmapEffect 的 DrawingGroup](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|将内容剪辑到你<xref:System.Windows.Media.Geometry>使用描述的区域。 <xref:System.Windows.Media.DrawingGroup> 有关示例，请参见 [如何：剪切绘图](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)) 。|![具有定义的剪裁区域的 DrawingGroup](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|根据指定的基准将与设备无关的像素与设备像素对齐。 此属性对于确保细节丰富的图形在低 DPI 屏幕上清晰地呈现很有用。 有关示例，请参阅[向绘图应用 GuidelineSet](how-to-apply-a-guidelineset-to-a-drawing.md)。|![具有和没有 GuidelineSet 的 DrawingGroup](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|<xref:System.Windows.Media.DrawingGroup>转换内容。 有关示例，请参见 [如何：向绘图](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90))应用转换。|![旋转后的 DrawingGroup](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>将绘图显示为图像  
 若要在<xref:System.Windows.Media.Drawing> <xref:System.Windows.Controls.Image>控件<xref:System.Windows.Media.DrawingImage> <xref:System.Windows.Controls.Image.Source%2A> <xref:System.Windows.Media.DrawingImage> 中显示<xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> , 请使用作为控件的,并将对象的属性设置为要显示的绘图。<xref:System.Windows.Controls.Image>  
  
 下面的示例使用<xref:System.Windows.Media.DrawingImage> <xref:System.Windows.Controls.Image>和控件来显示<xref:System.Windows.Media.GeometryDrawing>。 本示例生成以下输出。  
  
 ![两个省略号的 system.windows.media.geometrydrawing>](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
一个 DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>使用 Drawing 绘制对象  
 <xref:System.Windows.Media.DrawingBrush>是一种使用绘图对象绘制区域的画笔。 几乎可以使用它绘制任何带有绘图的图形对象。 的<xref:System.Windows.Media.Drawing>属性<xref:System.Windows.Media.DrawingBrush>描述其<xref:System.Windows.Media.DrawingBrush.Drawing%2A>。 若要<xref:System.Windows.Media.Drawing> <xref:System.Windows.Media.DrawingBrush>使用呈现, 请使用画笔的<xref:System.Windows.Media.Drawing>属性将其添加到画笔, 并使用画笔绘制图形对象 (如控件或面板)。  
  
 下面的示例<xref:System.Windows.Media.DrawingBrush>使用来<xref:System.Windows.Shapes.Shape.Fill%2A>绘制<xref:System.Windows.Shapes.Rectangle>具有从<xref:System.Windows.Media.GeometryDrawing>创建的模式的的。 本示例生成以下输出。  
  
 ![平铺的 system.windows.media.drawingbrush>](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
与 DrawingBrush 结合使用的 GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 <xref:System.Windows.Media.DrawingBrush>类提供各种选项来拉伸和平铺其内容。 有关的详细信息<xref:System.Windows.Media.DrawingBrush>, 请参阅[通过图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)概述。  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>使用视觉对象呈现绘图  
 <xref:System.Windows.Media.DrawingVisual>是一种用于呈现绘图的视觉对象。 对于希望生成高度自定义的图形环境的开发者来说，可以选择直接在视觉对象层上工作，但在本概述中不作介绍。 有关详细信息，请参阅[使用 DrawingVisual 对象](using-drawingvisual-objects.md)概述。  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>DrawingContext 对象  
 利用类, 您可以<xref:System.Windows.Media.Drawing>使用可视<xref:System.Windows.Media.Visual>内容填充或。 <xref:System.Windows.Media.DrawingContext> 许多此类低级别图形对象都使用<xref:System.Windows.Media.DrawingContext> , 因为它非常有效地描述图形内容。  
  
 尽管绘图方法看起来类似于<xref:System.Drawing.Graphics?displayProperty=nameWithType>类型的绘制方法, 但它们实际上是非常不同的。 <xref:System.Windows.Media.DrawingContext> <xref:System.Windows.Media.DrawingContext>用于保留模式图形系统, 而<xref:System.Drawing.Graphics?displayProperty=nameWithType>类型用于即时模式图形系统。 使用<xref:System.Windows.Media.DrawingContext>对象的绘制命令时, 实际上存储的是一组呈现说明 (尽管具体的存储机制取决于提供的<xref:System.Windows.Media.DrawingContext>对象类型), 后者将在以后由图形系统使用; 你不会实时绘制到屏幕上。 有关 Windows Presentation Foundation (WPF) 图形系统的工作原理的详细信息, 请参阅[WPF 图形呈现概述](wpf-graphics-rendering-overview.md)。  
  
 永远不会直接实例<xref:System.Windows.Media.DrawingContext>化, 但可以从某些方法 ( <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType>如和<xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>) 获取一个绘图上下文。  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>枚举 Visual 的内容  
 除了其他用途以外, <xref:System.Windows.Media.Drawing>对象还提供用于枚举的内容<xref:System.Windows.Media.Visual>的对象模型。  
  
 下面的示例使用<xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>方法来<xref:System.Windows.Media.DrawingGroup>检索的<xref:System.Windows.Media.Visual>值并对其进行枚举。  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- [2D 图形和图像处理](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
- [Geometry 概述](geometry-overview.md)
- [WPF 中的形状和基本绘图概述](shapes-and-basic-drawing-in-wpf-overview.md)
- [WPF 图形呈现概述](wpf-graphics-rendering-overview.md)
- [Freezable 对象概述](../advanced/freezable-objects-overview.md)
- [帮助主题](drawings-how-to-topics.md)
