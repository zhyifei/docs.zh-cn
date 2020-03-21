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
ms.openlocfilehash: 7a5d00eb2fb7c66e5e42d40893806e13717e1d2e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186538"
---
# <a name="drawing-objects-overview"></a>Drawing 对象概述
本主题介绍<xref:System.Windows.Media.Drawing>对象，并介绍如何使用它们有效地绘制形状、位图、文本和媒体。 在<xref:System.Windows.Media.Drawing>创建剪贴画、使用<xref:System.Windows.Media.DrawingBrush>上画或使用对象时使用<xref:System.Windows.Media.Visual>对象。  

<a name="whatisadrawingsection"></a>
## <a name="what-is-a-drawing-object"></a>什么是 Drawing 对象？  
 <xref:System.Windows.Media.Drawing>对象描述可见内容，如形状、位图、视频或文本行。 不同类型的图形描述不同类型的内容。 下面是不同类型图形对象的列表。  
  
- <xref:System.Windows.Media.GeometryDrawing>• 绘制形状。  
  
- <xref:System.Windows.Media.ImageDrawing>• 绘制图像。  
  
- <xref:System.Windows.Media.GlyphRunDrawing>• 绘制文本。  
  
- <xref:System.Windows.Media.VideoDrawing>• 播放音频或视频文件。  
  
- <xref:System.Windows.Media.DrawingGroup>• 绘制其他绘图。 使用图形组将其他图形合并到单个复合图形。  
  
 <xref:System.Windows.Media.Drawing>对象是通用的;有许多方法可以使用<xref:System.Windows.Media.Drawing>对象。  
  
- 可以使用 和<xref:System.Windows.Media.DrawingImage><xref:System.Windows.Controls.Image>控件将其显示为图像。  
  
- 可以将其与 一起<xref:System.Windows.Media.DrawingBrush>用于绘制对象，例如 。 <xref:System.Windows.Controls.Page.Background%2A> <xref:System.Windows.Controls.Page>  
  
- 您可以使用它来描述 的外观<xref:System.Windows.Media.DrawingVisual>。  
  
- 可以使用它枚举 的内容<xref:System.Windows.Media.Visual>。  
  
 WPF 提供能够绘制形状、位图、文本和媒体的其他对象类型。 例如，您还可以使用<xref:System.Windows.Shapes.Shape>对象绘制形状，并且<xref:System.Windows.Controls.MediaElement>控件提供了向应用程序添加视频的另一种方法。 那么，何时应该使用<xref:System.Windows.Media.Drawing>对象？ 当您可以牺牲框架级别功能以获得性能优势时，或者在需要时需要<xref:System.Windows.Freezable>功能时。 由于<xref:System.Windows.Media.Drawing>对象不支持[布局](../advanced/layout.md)、输入和焦点，因此它们提供了性能优势，非常适合描述背景、剪辑艺术以及使用<xref:System.Windows.Media.Visual>对象的低级绘图。  
  
 由于它们是类型<xref:System.Windows.Freezable>对象，<xref:System.Windows.Media.Drawing>因此对象具有多个特殊功能，其中包括：它们可以声明为[资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)、在多个对象之间共享、仅读以提高性能、克隆和使线程安全。 有关<xref:System.Windows.Freezable>对象提供的不同要素的详细信息，请参阅[可冻结对象概述](../advanced/freezable-objects-overview.md)。  
  
<a name="drawinggeometriessection"></a>
## <a name="draw-a-shape"></a>绘制形状  
 要绘制形状，请使用 。 <xref:System.Windows.Media.GeometryDrawing> 几何图形的属性<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>描述要绘制的形状，其<xref:System.Windows.Media.GeometryDrawing.Brush%2A>属性描述如何绘制形状的内部，其<xref:System.Windows.Media.GeometryDrawing.Pen%2A>属性描述如何绘制其轮廓。  
  
 下面的示例使用 来<xref:System.Windows.Media.GeometryDrawing>绘制形状。 形状由 和 两<xref:System.Windows.Media.GeometryGroup><xref:System.Windows.Media.EllipseGeometry>个对象描述。 形状的内部用 绘制，<xref:System.Windows.Media.LinearGradientBrush>其轮廓用<xref:System.Windows.Media.Brushes.Black%2A><xref:System.Windows.Media.Pen>绘制。  
  
 本示例创建以下<xref:System.Windows.Media.GeometryDrawing>。  
  
 ![两个椭圆形的 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
一个 GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 有关完整示例，请参阅[创建 GeometryDrawing](how-to-create-a-geometrydrawing.md)。  
  
 其他<xref:System.Windows.Media.Geometry>类，例如<xref:System.Windows.Media.PathGeometry>，使您能够通过创建曲线和圆弧来创建更复杂的形状。 有关<xref:System.Windows.Media.Geometry>对象的详细信息，请参阅[几何概述](geometry-overview.md)。  
  
 有关绘制不使用<xref:System.Windows.Media.Drawing>对象的形状的其他方法的详细信息，请参阅[WPF 概述 中的形状和基本图形](shapes-and-basic-drawing-in-wpf-overview.md)。  
  
<a name="drawingimagessection"></a>
## <a name="draw-an-image"></a>绘制图像  
 要绘制图像，请使用 。 <xref:System.Windows.Media.ImageDrawing> 对象的属性描述要绘制的图像，其<xref:System.Windows.Media.ImageDrawing.Rect%2A>属性定义绘制图像的区域。 <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> <xref:System.Windows.Media.ImageDrawing>  
  
 以下示例将在一个矩形的 (75,75) 处绘制一个 100 x 100 像素的图像。 下图显示了示例<xref:System.Windows.Media.ImageDrawing>创建的示例。 添加了灰色边框以显示 的边界<xref:System.Windows.Media.ImageDrawing>。  
  
 ![在 &#40;75,75&#41; 处绘制的 100 x 100 ImageDrawing](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
100 x 100 的 ImageDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 有关图像的详细信息，请参阅[图像处理概述](imaging-overview.md)。  
  
<a name="playmedia"></a>
## <a name="play-media-code-only"></a>播放媒体（仅代码）  
  
> [!NOTE]
> 尽管可以声明<xref:System.Windows.Media.VideoDrawing>in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，但只能使用代码加载和播放其媒体。 要在 中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]播放视频，<xref:System.Windows.Controls.MediaElement>请使用  
  
 要播放音频或视频文件，请使用 和<xref:System.Windows.Media.VideoDrawing>。 <xref:System.Windows.Media.MediaPlayer> 加载并播放媒体有两种方法。 第一种方法是自己使用<xref:System.Windows.Media.MediaPlayer>和<xref:System.Windows.Media.VideoDrawing>， 第二种方法是创建自己的<xref:System.Windows.Media.MediaTimeline>方法， 与 和<xref:System.Windows.Media.MediaPlayer>一<xref:System.Windows.Media.VideoDrawing>起使用 。  
  
> [!NOTE]
> 当媒体随应用程序一起分发时，无法像图像那样将媒体文件用作项目资源。 在项目文件中，必须改为将媒体类型设置为 `Content` 并将 `CopyToOutputDirectory` 设置为 `PreserveNewest` 或 `Always`。  
  
 要在不创建自己的媒体的情况下播放媒体<xref:System.Windows.Media.MediaTimeline>，请执行以下步骤。  
  
1. 创建 <xref:System.Windows.Media.MediaPlayer> 对象。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. 使用<xref:System.Windows.Media.MediaPlayer.Open%2A>方法加载媒体文件。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. 创建 <xref:System.Windows.Media.VideoDrawing>。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. 通过设置<xref:System.Windows.Media.VideoDrawing.Rect%2A>的属性<xref:System.Windows.Media.VideoDrawing>来指定绘制媒体的大小和位置。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. 使用<xref:System.Windows.Media.VideoDrawing.Player%2A><xref:System.Windows.Media.MediaPlayer>创建的 设置<xref:System.Windows.Media.VideoDrawing>的属性。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. 使用<xref:System.Windows.Media.MediaPlayer.Play%2A>的方法<xref:System.Windows.Media.MediaPlayer>开始播放媒体。  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 下面的示例使用 和<xref:System.Windows.Media.VideoDrawing>a<xref:System.Windows.Media.MediaPlayer>播放一次视频文件。  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 要获得对介质的额外计时控制，请使用<xref:System.Windows.Media.MediaTimeline><xref:System.Windows.Media.MediaPlayer>和<xref:System.Windows.Media.VideoDrawing>对象。 <xref:System.Windows.Media.MediaTimeline>使您能够指定视频是否应重复。 要将<xref:System.Windows.Media.VideoDrawing><xref:System.Windows.Media.MediaTimeline>和 使用 ， 执行以下步骤：  
  
1. 声明<xref:System.Windows.Media.MediaTimeline>并设置其计时行为。  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. 从<xref:System.Windows.Media.MediaClock>中<xref:System.Windows.Media.MediaTimeline>创建 。  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. 创建<xref:System.Windows.Media.MediaPlayer>，并使用<xref:System.Windows.Media.MediaClock>来设置其<xref:System.Windows.Media.MediaPlayer.Clock%2A>属性。  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. 创建<xref:System.Windows.Media.VideoDrawing>并将 分配<xref:System.Windows.Media.MediaPlayer>到<xref:System.Windows.Media.VideoDrawing.Player%2A>的属性<xref:System.Windows.Media.VideoDrawing>。  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 下面的示例使用<xref:System.Windows.Media.MediaTimeline>a<xref:System.Windows.Media.MediaPlayer>和 a<xref:System.Windows.Media.VideoDrawing>反复播放视频。  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 请注意<xref:System.Windows.Media.MediaTimeline>，使用 时，使用 从<xref:System.Windows.Media.Animation.ClockController><xref:System.Windows.Media.Animation.Clock.Controller%2A>属性返回的交互式<xref:System.Windows.Media.MediaClock>来控制媒体播放，而不是 使用 的<xref:System.Windows.Media.MediaPlayer>交互式方法。  
  
<a name="drawtext"></a>
## <a name="draw-text"></a>绘制文本  
 要绘制文本，请使用 和<xref:System.Windows.Media.GlyphRunDrawing> <xref:System.Windows.Media.GlyphRun>。 下面的示例使用<xref:System.Windows.Media.GlyphRunDrawing>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 A<xref:System.Windows.Media.GlyphRun>是一个低级对象，用于固定格式的文档表示和打印方案。 将文本绘制到屏幕的更简单方法是使用 或<xref:System.Windows.Controls.Label>。 <xref:System.Windows.Controls.TextBlock> 有关 的详细信息<xref:System.Windows.Media.GlyphRun>，请参阅[字形 Run 对象和字形元素概述简介](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md)。  
  
<a name="compositedrawingssection"></a>
## <a name="composite-drawings"></a>复合绘图  
 A<xref:System.Windows.Media.DrawingGroup>使您能够将多个图形合并到单个复合图形中。 通过使用 ，<xref:System.Windows.Media.DrawingGroup>可以将形状、图像和文本合并到单个<xref:System.Windows.Media.Drawing>对象中。  
  
 下面的示例使用 将<xref:System.Windows.Media.DrawingGroup>两<xref:System.Windows.Media.GeometryDrawing>个对象和一个<xref:System.Windows.Media.ImageDrawing>对象组合在一起。 本示例生成以下输出。  
  
 ![具有多个绘图的 DrawingGroup](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
复合绘图  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 还<xref:System.Windows.Media.DrawingGroup>使您能够对其内容应用不一样蒙版、变换、位图效果和其他操作。 <xref:System.Windows.Media.DrawingGroup>操作按以下顺序应用<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>： 、 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>、 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A> <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>、 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>、 <xref:System.Windows.Media.DrawingGroup.Transform%2A>、 、 然后 。  
  
 下图显示了操作的应用顺序<xref:System.Windows.Media.DrawingGroup>。  
  
 ![DrawingGroup 操作顺序](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
DrawingGroup 操作的顺序  
  
 下表描述了可用于操作<xref:System.Windows.Media.DrawingGroup>对象内容的属性。  
  
|properties|说明|图示|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|更改内容选定部分的不<xref:System.Windows.Media.DrawingGroup>恰当性。 有关示例，请参阅[如何：控制绘图的不透明度](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90))。|![具有不一视拟面膜的绘图组](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|均匀地更改内容的不<xref:System.Windows.Media.DrawingGroup>均匀性。 使用此属性可使<xref:System.Windows.Media.Drawing>透明或部分透明。 有关示例，请参阅[如何：向绘图应用不透明蒙板](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90))。|![具有不同不透明度设置的 DrawingGroup](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|对<xref:System.Windows.Media.DrawingGroup>内容<xref:System.Windows.Media.Effects.BitmapEffect>应用 a。 有关示例，请参阅[如何：向绘图应用 BitmapEffect](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90))。|![具有 BlurBitmapEffect 的 DrawingGroup](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|将<xref:System.Windows.Media.DrawingGroup>内容剪辑到使用 描述的区域<xref:System.Windows.Media.Geometry>。 有关示例，请参阅[如何：剪裁绘图](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90))。|![具有定义的剪辑区域的 DrawingGroup](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|根据指定的基准将与设备无关的像素与设备像素对齐。 此属性对于确保细节丰富的图形在低 DPI 屏幕上清晰地呈现很有用。 有关示例，请参阅[向绘图应用 GuidelineSet](how-to-apply-a-guidelineset-to-a-drawing.md)。|![具有和没有 GuidelineSet 的 DrawingGroup](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|转换<xref:System.Windows.Media.DrawingGroup>内容。 有关示例，请参阅[如何：向绘图应用转换](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90))。|![旋转后的 DrawingGroup](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>
## <a name="display-a-drawing-as-an-image"></a>将绘图显示为图像  
 要显示<xref:System.Windows.Media.Drawing>具有控件<xref:System.Windows.Controls.Image>的 ，<xref:System.Windows.Media.DrawingImage>请使用<xref:System.Windows.Controls.Image>作为 控件<xref:System.Windows.Controls.Image.Source%2A>的，<xref:System.Windows.Media.DrawingImage>并将对象的属性<xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType>设置为要显示的图形。  
  
 下面的示例使用<xref:System.Windows.Media.DrawingImage>和 控件<xref:System.Windows.Controls.Image>来显示 。 <xref:System.Windows.Media.GeometryDrawing> 本示例生成以下输出。  
  
 ![两个椭圆形的 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
一个 DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>
## <a name="paint-an-object-with-a-drawing"></a>使用 Drawing 绘制对象  
 A<xref:System.Windows.Media.DrawingBrush>是一种使用绘图对象绘制区域的画笔类型。 几乎可以使用它绘制任何带有绘图的图形对象。 的属性<xref:System.Windows.Media.Drawing><xref:System.Windows.Media.DrawingBrush>描述其<xref:System.Windows.Media.DrawingBrush.Drawing%2A>。 要使用<xref:System.Windows.Media.Drawing><xref:System.Windows.Media.DrawingBrush>渲染 ， 使用 画笔的属性<xref:System.Windows.Media.Drawing>将其添加到画笔，并使用画笔绘制图形对象（如控件或面板）。  
  
 以下示例使用 使用<xref:System.Windows.Media.DrawingBrush>从<xref:System.Windows.Media.GeometryDrawing><xref:System.Windows.Shapes.Shape.Fill%2A>创建的<xref:System.Windows.Shapes.Rectangle>模式绘制 的 。 本示例生成以下输出。  
  
 ![平铺的 DrawingBrush](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
与 DrawingBrush 结合使用的 GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 该<xref:System.Windows.Media.DrawingBrush>类提供了各种选项来拉伸和平铺其内容。 有关 的详细信息<xref:System.Windows.Media.DrawingBrush>，请参阅["具有图像、绘图和视觉对象"的绘画](painting-with-images-drawings-and-visuals.md)概述。  
  
<a name="renderingwithvisualsection"></a>
## <a name="render-a-drawing-with-a-visual"></a>使用视觉对象呈现绘图  
 是<xref:System.Windows.Media.DrawingVisual>一种视觉对象类型，旨在渲染图形。 对于希望生成高度自定义的图形环境的开发者来说，可以选择直接在视觉对象层上工作，但在本概述中不作介绍。 有关详细信息，请参阅[使用 DrawingVisual 对象](using-drawingvisual-objects.md)概述。  
  
<a name="drawingcontextobjects"></a>
## <a name="drawingcontext-objects"></a>DrawingContext 对象  
 类<xref:System.Windows.Media.DrawingContext>使您能够使用可视内容填充<xref:System.Windows.Media.Visual>或<xref:System.Windows.Media.Drawing>。 许多此类较低级别的图形对象使用 ，<xref:System.Windows.Media.DrawingContext>因为它非常有效地描述图形内容。  
  
 尽管<xref:System.Windows.Media.DrawingContext>绘制方法看起来与<xref:System.Drawing.Graphics?displayProperty=nameWithType>类型的绘制方法类似，但它们实际上非常不同。 <xref:System.Windows.Media.DrawingContext>与保留模式图形系统一起使用，而<xref:System.Drawing.Graphics?displayProperty=nameWithType>该类型与即时模式图形系统一起使用。 使用<xref:System.Windows.Media.DrawingContext>对象的绘制命令时，实际上存储一组呈现指令（尽管确切的存储机制取决于提供<xref:System.Windows.Media.DrawingContext>）的对象类型，图形系统稍后将使用该指令。您没有实时绘制到屏幕。 有关 Windows 演示基础 （WPF） 图形系统工作原理的详细信息，请参阅[WPF 图形呈现概述](wpf-graphics-rendering-overview.md)。  
  
 你从来没有直接实例化; <xref:System.Windows.Media.DrawingContext>但是，可以从某些方法（如 和<xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType><xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>获取绘图上下文）获取绘图上下文。  
  
<a name="enumeratevisualcontents"></a>
## <a name="enumerate-the-contents-of-a-visual"></a>枚举 Visual 的内容  
 除了其他用途外，<xref:System.Windows.Media.Drawing>对象还提供用于枚举 的对象模型。 <xref:System.Windows.Media.Visual>  
  
 下面的示例使用 方法<xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>检索<xref:System.Windows.Media.DrawingGroup>的值<xref:System.Windows.Media.Visual>并枚举它。  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- [2D 图形和图像处理](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
- [Geometry 概述](geometry-overview.md)
- [WPF 中的形状和基本绘图概述](shapes-and-basic-drawing-in-wpf-overview.md)
- [WPF 图形呈现概述](wpf-graphics-rendering-overview.md)
- [Freezable 对象概述](../advanced/freezable-objects-overview.md)
- [如何使用主题](drawings-how-to-topics.md)
