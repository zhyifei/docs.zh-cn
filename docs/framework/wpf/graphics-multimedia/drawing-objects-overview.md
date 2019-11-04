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
ms.openlocfilehash: d4527c331308ff6cd517705212e09428216d2378
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459727"
---
# <a name="drawing-objects-overview"></a>Drawing 对象概述
本主题介绍 <xref:System.Windows.Media.Drawing> 对象，并说明如何使用它们高效地绘制形状、位图、文本和媒体。 创建剪贴画、使用 <xref:System.Windows.Media.DrawingBrush>绘画或使用 <xref:System.Windows.Media.Visual> 对象时，请使用 <xref:System.Windows.Media.Drawing> 对象。  

<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>什么是 Drawing 对象？  
 <xref:System.Windows.Media.Drawing> 对象描述可见内容，如形状、位图、视频或文本行。 不同类型的图形描述不同类型的内容。 下面是不同类型图形对象的列表。  
  
- <xref:System.Windows.Media.GeometryDrawing> –绘制形状。  
  
- <xref:System.Windows.Media.ImageDrawing> –绘制图像。  
  
- <xref:System.Windows.Media.GlyphRunDrawing> –绘制文本。  
  
- <xref:System.Windows.Media.VideoDrawing> –播放音频或视频文件。  
  
- <xref:System.Windows.Media.DrawingGroup> –绘制其他绘图。 使用绘图组将其他绘图合并到单个复合绘图。  
  
 <xref:System.Windows.Media.Drawing> 对象是通用的;可以通过多种方式使用 <xref:System.Windows.Media.Drawing> 对象。  
  
- 您可以使用 <xref:System.Windows.Media.DrawingImage> 和 <xref:System.Windows.Controls.Image> 控件将其显示为图像。  
  
- 可以将其与 <xref:System.Windows.Media.DrawingBrush> 一起使用来绘制对象，如 <xref:System.Windows.Controls.Page>的 <xref:System.Windows.Controls.Page.Background%2A>。  
  
- 您可以使用它来描述 <xref:System.Windows.Media.DrawingVisual>的外观。  
  
- 可以使用它来枚举 <xref:System.Windows.Media.Visual>的内容。  
  
 WPF 提供能够绘制形状、位图、文本和媒体的其他对象类型。 例如，您还可以使用 <xref:System.Windows.Shapes.Shape> 对象绘制形状，而 <xref:System.Windows.Controls.MediaElement> 控件提供了另一种向应用程序中添加视频的方式。 那么，何时应使用 <xref:System.Windows.Media.Drawing> 对象？ 当你可能牺牲框架级别功能来获得性能优势或需要 <xref:System.Windows.Freezable> 功能时。 由于 <xref:System.Windows.Media.Drawing> 对象缺少[布局](../advanced/layout.md)、输入和焦点支持，因此它们提供性能优势，使其非常适合用于描述背景、剪贴画和具有 <xref:System.Windows.Media.Visual> 对象的低级别绘图。  
  
 由于它们是 <xref:System.Windows.Freezable> 对象的类型，<xref:System.Windows.Media.Drawing> 对象将获得几项特殊功能，其中包括：它们可以声明为[资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)、在多个对象之间共享、变为只读以提高性能、克隆和进行线程安全的。 有关 <xref:System.Windows.Freezable> 对象提供的不同功能的详细信息，请参阅可[冻结对象概述](../advanced/freezable-objects-overview.md)。  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>绘制形状  
 若要绘制形状，请使用 <xref:System.Windows.Media.GeometryDrawing>。 几何绘图的 <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> 属性说明了要绘制的形状，其 <xref:System.Windows.Media.GeometryDrawing.Brush%2A> 属性说明了应如何绘制形状的内部，其 <xref:System.Windows.Media.GeometryDrawing.Pen%2A> 属性说明了应如何绘制其轮廓。  
  
 下面的示例使用 <xref:System.Windows.Media.GeometryDrawing> 绘制形状。 该形状由 <xref:System.Windows.Media.GeometryGroup> 和两个 <xref:System.Windows.Media.EllipseGeometry> 对象进行描述。 形状的内部用一个 <xref:System.Windows.Media.LinearGradientBrush> 绘制，并使用 <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>绘制其轮廓。  
  
 此示例创建以下 <xref:System.Windows.Media.GeometryDrawing>。  
  
 ![两个椭圆形的 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
一个 GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 有关完整示例，请参阅[创建 GeometryDrawing](how-to-create-a-geometrydrawing.md)。  
  
 其他 <xref:System.Windows.Media.Geometry> 类，如 <xref:System.Windows.Media.PathGeometry> 使您可以通过创建曲线和弧形来创建更复杂的形状。 有关 <xref:System.Windows.Media.Geometry> 对象的详细信息，请参阅[几何概述](geometry-overview.md)。  
  
 有关绘制不使用 <xref:System.Windows.Media.Drawing> 对象的形状的其他方法的详细信息，请参阅[WPF 中的形状和基本绘图概述](shapes-and-basic-drawing-in-wpf-overview.md)。  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>绘制图像  
 若要绘制图像，请使用 <xref:System.Windows.Media.ImageDrawing>。 <xref:System.Windows.Media.ImageDrawing> 对象的 <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> 属性描述要绘制的图像，其 <xref:System.Windows.Media.ImageDrawing.Rect%2A> 属性定义绘制图像的区域。  
  
 以下示例将在一个矩形的 (75,75) 处绘制一个 100 x 100 像素的图像。 下图显示了该示例创建的 <xref:System.Windows.Media.ImageDrawing>。 添加了灰色边框以显示 <xref:System.Windows.Media.ImageDrawing>的边界。  
  
 ![在 &#40;75,75&#41; 处绘制的 100 x 100 ImageDrawing](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
100 x 100 的 ImageDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 有关图像的详细信息，请参阅[图像处理概述](imaging-overview.md)。  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>播放媒体（仅代码）  
  
> [!NOTE]
> 尽管可以在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中声明 <xref:System.Windows.Media.VideoDrawing>，但只能使用代码加载和播放其媒体。 若要在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中播放视频，请改用 <xref:System.Windows.Controls.MediaElement>。  
  
 若要播放音频或视频文件，请使用 <xref:System.Windows.Media.VideoDrawing> 和 <xref:System.Windows.Media.MediaPlayer>。 加载并播放媒体有两种方法。 第一种方法是单独使用 <xref:System.Windows.Media.MediaPlayer> 和 <xref:System.Windows.Media.VideoDrawing>，第二种方法是创建您自己的 <xref:System.Windows.Media.MediaTimeline> 与 <xref:System.Windows.Media.MediaPlayer> 和 <xref:System.Windows.Media.VideoDrawing>一起使用。  
  
> [!NOTE]
> 当媒体随应用程序一起分发时，无法像图像那样将媒体文件用作项目资源。 在项目文件中，必须改为将媒体类型设置为 `Content` 并将 `CopyToOutputDirectory` 设置为 `PreserveNewest` 或 `Always`。  
  
 若要播放媒体而不创建自己的 <xref:System.Windows.Media.MediaTimeline>，请执行以下步骤。  
  
1. 创建 <xref:System.Windows.Media.MediaPlayer> 对象。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. 使用 <xref:System.Windows.Media.MediaPlayer.Open%2A> 方法加载媒体文件。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. 创建 <xref:System.Windows.Media.VideoDrawing>。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. 通过设置 <xref:System.Windows.Media.VideoDrawing>的 <xref:System.Windows.Media.VideoDrawing.Rect%2A> 属性，指定用于绘制媒体的大小和位置。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. 用创建的 <xref:System.Windows.Media.MediaPlayer> 设置 <xref:System.Windows.Media.VideoDrawing> 的 <xref:System.Windows.Media.VideoDrawing.Player%2A> 属性。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. 使用 <xref:System.Windows.Media.MediaPlayer> 的 <xref:System.Windows.Media.MediaPlayer.Play%2A> 方法开始播放媒体。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 下面的示例使用 <xref:System.Windows.Media.VideoDrawing> 和 <xref:System.Windows.Media.MediaPlayer> 一次播放视频文件。  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 若要获取对媒体的其他计时控制，请将 <xref:System.Windows.Media.MediaTimeline> 与 <xref:System.Windows.Media.MediaPlayer> 和 <xref:System.Windows.Media.VideoDrawing> 对象结合使用。 通过 <xref:System.Windows.Media.MediaTimeline> 可以指定是否应重复播放视频。 若要在 <xref:System.Windows.Media.VideoDrawing>中使用 <xref:System.Windows.Media.MediaTimeline>，请执行以下步骤：  
  
1. 声明 <xref:System.Windows.Media.MediaTimeline> 并设置其计时行为。  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. 从 <xref:System.Windows.Media.MediaTimeline>创建 <xref:System.Windows.Media.MediaClock>。  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. 创建 <xref:System.Windows.Media.MediaPlayer>，并使用 <xref:System.Windows.Media.MediaClock> 设置其 <xref:System.Windows.Media.MediaPlayer.Clock%2A> 属性。  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. 创建 <xref:System.Windows.Media.VideoDrawing>，并将 <xref:System.Windows.Media.MediaPlayer> 分配给 <xref:System.Windows.Media.VideoDrawing>的 <xref:System.Windows.Media.VideoDrawing.Player%2A> 属性。  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 下面的示例使用带有 <xref:System.Windows.Media.MediaPlayer> 和 <xref:System.Windows.Media.VideoDrawing> 的 <xref:System.Windows.Media.MediaTimeline> 来反复播放视频。  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 请注意，当你使用 <xref:System.Windows.Media.MediaTimeline>时，将使用从 <xref:System.Windows.Media.MediaClock> 的 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 属性返回的交互式 <xref:System.Windows.Media.Animation.ClockController> 来控制媒体播放，而不是 <xref:System.Windows.Media.MediaPlayer>的交互式方法。  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>绘制文本  
 若要绘制文本，请使用 <xref:System.Windows.Media.GlyphRunDrawing> 和 <xref:System.Windows.Media.GlyphRun>。 下面的示例使用 <xref:System.Windows.Media.GlyphRunDrawing> 绘制文本 "Hello World"。  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 <xref:System.Windows.Media.GlyphRun> 是一种低级别的对象，用于固定格式的文档演示和打印方案。 在屏幕上绘制文本的一种更简单的方法是使用 <xref:System.Windows.Controls.Label> 或 <xref:System.Windows.Controls.TextBlock>。 有关 <xref:System.Windows.Media.GlyphRun>的详细信息，请参阅[GlyphRun 对象和字形元素](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md)概述。  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>复合绘图  
 使用 <xref:System.Windows.Media.DrawingGroup> 可以将多个绘图组合成单个复合绘图。 通过使用 <xref:System.Windows.Media.DrawingGroup>，可以将形状、图像和文本合并为单个 <xref:System.Windows.Media.Drawing> 对象。  
  
 下面的示例使用 <xref:System.Windows.Media.DrawingGroup> 将两个 <xref:System.Windows.Media.GeometryDrawing> 对象和一个 <xref:System.Windows.Media.ImageDrawing> 对象组合在一起。 本示例生成以下输出。  
  
 ![具有多个绘图的 DrawingGroup](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
复合绘图  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 还可以通过 <xref:System.Windows.Media.DrawingGroup> 将不透明蒙板、转换、位图效果和其他操作应用于其内容。 按以下顺序应用 <xref:System.Windows.Media.DrawingGroup> 操作： <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>、<xref:System.Windows.Media.DrawingGroup.Opacity%2A>、<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>、<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>、<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>，然后 <xref:System.Windows.Media.DrawingGroup.Transform%2A>。  
  
 下图显示了应用 <xref:System.Windows.Media.DrawingGroup> 操作的顺序。  
  
 ![DrawingGroup 操作顺序](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
DrawingGroup 操作的顺序  
  
 下表介绍了可用于操作 <xref:System.Windows.Media.DrawingGroup> 对象内容的属性。  
  
|Property|描述|图示|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|更改 <xref:System.Windows.Media.DrawingGroup> 内容的选定部分的不透明度。 有关示例，请参阅[如何：控制绘图的不透明度](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90))。|![使用不透明蒙板的 DrawingGroup](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|统一更改 <xref:System.Windows.Media.DrawingGroup> 内容的不透明度。 使用此属性可以使 <xref:System.Windows.Media.Drawing> 透明或部分透明。 有关示例，请参阅[如何：向绘图应用不透明蒙板](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90))。|![具有不同不透明度设置的具有](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|将 <xref:System.Windows.Media.Effects.BitmapEffect> 应用到 <xref:System.Windows.Media.DrawingGroup> 内容。 有关示例，请参阅[如何：向绘图应用 BitmapEffect](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90))。|![使用 BlurBitmapEffect 的 DrawingGroup](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|将 <xref:System.Windows.Media.DrawingGroup> 内容剪辑到使用 <xref:System.Windows.Media.Geometry>描述的区域。 有关示例，请参阅[如何：剪裁绘图](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90))。|![具有定义的剪辑区域的 DrawingGroup](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|根据指定的基准将与设备无关的像素与设备像素对齐。 此属性对于确保细节丰富的图形在低 DPI 屏幕上清晰地呈现很有用。 有关示例，请参阅[向绘图应用 GuidelineSet](how-to-apply-a-guidelineset-to-a-drawing.md)。|![具有和不包含向 guidelineset 的 DrawingGroup](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|转换 <xref:System.Windows.Media.DrawingGroup> 内容。 有关示例，请参阅[如何：向绘图应用转换](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90))。|![旋转后的 DrawingGroup](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>将绘图显示为图像  
 若要显示具有 <xref:System.Windows.Controls.Image> 控件的 <xref:System.Windows.Media.Drawing>，请使用 <xref:System.Windows.Media.DrawingImage> 作为 <xref:System.Windows.Controls.Image> 控件的 <xref:System.Windows.Controls.Image.Source%2A>，并将 <xref:System.Windows.Media.DrawingImage> 对象的 <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> 属性设置为要显示的绘图。  
  
 下面的示例使用 <xref:System.Windows.Media.DrawingImage> 和 <xref:System.Windows.Controls.Image> 控件来显示 <xref:System.Windows.Media.GeometryDrawing>。 本示例生成以下输出。  
  
 ![两个椭圆形的 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
一个 DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>使用 Drawing 绘制对象  
 <xref:System.Windows.Media.DrawingBrush> 是一种使用绘图对象绘制区域的画笔。 几乎可以使用它绘制任何带有绘图的图形对象。 <xref:System.Windows.Media.DrawingBrush> 的 <xref:System.Windows.Media.Drawing> 属性说明了其 <xref:System.Windows.Media.DrawingBrush.Drawing%2A>。 若要呈现包含 <xref:System.Windows.Media.DrawingBrush>的 <xref:System.Windows.Media.Drawing>，请使用画笔的 <xref:System.Windows.Media.Drawing> 属性将其添加到画笔，并使用画笔绘制图形对象（如控件或面板）。  
  
 下面的示例使用 <xref:System.Windows.Media.DrawingBrush> 用从 <xref:System.Windows.Media.GeometryDrawing>创建的模式绘制 <xref:System.Windows.Shapes.Rectangle> 的 <xref:System.Windows.Shapes.Shape.Fill%2A>。 本示例生成以下输出。  
  
 ![平铺的 DrawingBrush](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
与 DrawingBrush 结合使用的 GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 <xref:System.Windows.Media.DrawingBrush> 类提供各种选项来拉伸和平铺其内容。 有关 <xref:System.Windows.Media.DrawingBrush>的详细信息，请参阅[通过图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)概述。  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>使用视觉对象呈现绘图  
 <xref:System.Windows.Media.DrawingVisual> 是一种用于呈现绘图的视觉对象。 对于希望生成高度自定义的图形环境的开发者来说，可以选择直接在视觉对象层上工作，但在本概述中不作介绍。 有关详细信息，请参阅[使用 DrawingVisual 对象](using-drawingvisual-objects.md)概述。  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>DrawingContext 对象  
 利用 <xref:System.Windows.Media.DrawingContext> 类，您可以使用可视内容填充 <xref:System.Windows.Media.Visual> 或 <xref:System.Windows.Media.Drawing>。 许多此类低级别图形对象使用 <xref:System.Windows.Media.DrawingContext>，因为它非常有效地描述图形内容。  
  
 尽管 <xref:System.Windows.Media.DrawingContext> 绘制方法的外观类似于 <xref:System.Drawing.Graphics?displayProperty=nameWithType> 类型的绘制方法，但它们实际上是非常不同的。 <xref:System.Windows.Media.DrawingContext> 用于保留模式图形系统，而 <xref:System.Drawing.Graphics?displayProperty=nameWithType> 类型用于即时模式图形系统。 使用 <xref:System.Windows.Media.DrawingContext> 对象的绘图命令时，实际上存储的是一组呈现说明（尽管具体的存储机制取决于提供 <xref:System.Windows.Media.DrawingContext>的对象类型），而该对象稍后将由图形系统使用;您不会实时绘制到屏幕上。 有关 Windows Presentation Foundation （WPF）图形系统的工作原理的详细信息，请参阅[WPF 图形呈现概述](wpf-graphics-rendering-overview.md)。  
  
 永远不会直接实例化 <xref:System.Windows.Media.DrawingContext>;不过，您可以从某些方法（如 <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>）获取一个绘图上下文。  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>枚举 Visual 的内容  
 除了其他用途以外，<xref:System.Windows.Media.Drawing> 对象还提供用于枚举 <xref:System.Windows.Media.Visual>的内容的对象模型。  
  
 下面的示例使用 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 方法检索 <xref:System.Windows.Media.Visual> 的 <xref:System.Windows.Media.DrawingGroup> 值并对其进行枚举。  
  
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
