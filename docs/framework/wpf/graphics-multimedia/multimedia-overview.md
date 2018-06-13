---
title: 多媒体概述
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 7a986125cff1ff4812528212fa3aee7689af1f16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566426"
---
# <a name="multimedia-overview"></a>多媒体概述
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的多媒体功能能够使音频和视频集成到应用程序，增强用户体验。 本主题介绍了 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的多媒体功能。  
  
 
  
<a name="mediaapi"></a>   
## <a name="media-api"></a>媒体 API  
 <xref:System.Windows.Controls.MediaElement>和<xref:System.Windows.Media.MediaPlayer>类用于呈现音频或视频的内容。 可以以交互方式或时钟控制这些类。 这些类可以用在 [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 控件上进行媒体播放。 要使用哪个类取决于方案。  
  
 <xref:System.Windows.Controls.MediaElement> 是<xref:System.Windows.UIElement>，均支持[布局](../../../../docs/framework/wpf/advanced/layout.md)，且可用作多个控件的内容使用。 它也可用在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 与代码中。 <xref:System.Windows.Media.MediaPlayer>另一方面，专用于<xref:System.Windows.Media.Drawing>对象，并缺少布局的支持。 加载使用的媒体<xref:System.Windows.Media.MediaPlayer>仅可以通过使用显示<xref:System.Windows.Media.VideoDrawing>或通过直接与进行交互<xref:System.Windows.Media.DrawingContext>。 <xref:System.Windows.Media.MediaPlayer> 不能在 XAML 中使用。  
  
 有关绘图对象和绘图上下文的详细信息，请参阅 [Drawing 对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)。  
  
> [!NOTE]
>  使用应用程序分发媒体时，不可将媒体文件用作项目资源。 在项目文件中，必须改为将媒体类型设置为 `Content` 并将 `CopyToOutputDirectory` 设置为 `PreserveNewest` 或 `Always`。  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>媒体播放模式  
  
> [!NOTE]
>  同时<xref:System.Windows.Controls.MediaElement>和<xref:System.Windows.Media.MediaPlayer>具有类似的成员。 本部分中的链接是指<xref:System.Windows.Controls.MediaElement>类成员。 除非特别指明外，成员将链接到在<xref:System.Windows.Controls.MediaElement>类还可在<xref:System.Windows.Media.MediaPlayer>类。  
  
 要了解 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的媒体播放，需要了解可以播放媒体的不同模式。 同时<xref:System.Windows.Controls.MediaElement>和<xref:System.Windows.Media.MediaPlayer>可以在两种不同的媒体模式、 独立的模式和时钟模式中使用。 媒体模式由<xref:System.Windows.Controls.MediaElement.Clock%2A>属性。 当<xref:System.Windows.Controls.MediaElement.Clock%2A>是`null`，媒体对象是在独立模式下。 当<xref:System.Windows.Controls.MediaElement.Clock%2A>为非 null，媒体对象处于时钟模式。 默认情况下，媒体对象处于独立模式。  
  
### <a name="independent-mode"></a>独立模式  
 在独立模式下，媒体内容驱动媒体播放。 独立模式可实现下列选项：  
  
-   媒体的<xref:System.Uri>可以直接指定。  
  
-   可以直接控制媒体播放。  
  
-   媒体的<xref:System.Windows.Controls.MediaElement.Position%2A>和<xref:System.Windows.Controls.MediaElement.SpeedRatio%2A>可以修改属性。  
  
 由这两个设置加载媒体<xref:System.Windows.Controls.MediaElement>对象的<xref:System.Windows.Controls.MediaElement.Source%2A>属性或通过调用<xref:System.Windows.Media.MediaPlayer>对象的<xref:System.Windows.Media.MediaPlayer.Open%2A>方法。  
  
 要在独立模式下控制媒体播放，可使用媒体对象的控制方法。 可用的控制方法是<xref:System.Windows.Controls.MediaElement.Play%2A>， <xref:System.Windows.Controls.MediaElement.Pause%2A>， <xref:System.Windows.Controls.MediaElement.Close%2A>，和<xref:System.Windows.Controls.MediaElement.Stop%2A>。 有关<xref:System.Windows.Controls.MediaElement>，使用这些方法的交互式控件才可用<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>设置为<xref:System.Windows.Controls.MediaState.Manual>。 这些方法在媒体对象处于时钟模式时不可用。  
  
 请参阅[控制 MediaElement（Play、Pause、Stop、Volume 和 Speed）](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)了解独立模式的示例。  
  
### <a name="clock-mode"></a>时钟模式  
 在时钟模式下，<xref:System.Windows.Media.MediaTimeline>驱动器媒体播放。 时钟模式具有以下特征：  
  
-   媒体的<xref:System.Uri>通过间接设置<xref:System.Windows.Media.MediaTimeline>。  
  
-   可由时钟控制媒体播放。 不可使用媒体对象的控制方法。  
  
-   通过设置加载媒体<xref:System.Windows.Media.MediaTimeline>对象的<xref:System.Windows.Media.MediaTimeline.Source%2A>属性，从时间线创建时钟并将时钟分配给媒体对象。 媒体还加载这种方式时<xref:System.Windows.Media.MediaTimeline>内<xref:System.Windows.Media.Animation.Storyboard>目标<xref:System.Windows.Controls.MediaElement>。  
  
 在时钟模式下，控制媒体播放<xref:System.Windows.Media.Animation.ClockController>必须使用控制方法。 A<xref:System.Windows.Media.Animation.ClockController>从获取<xref:System.Windows.Media.Animation.ClockController>属性<xref:System.Windows.Media.MediaClock>。 如果你尝试使用其中任何的控制方法<xref:System.Windows.Controls.MediaElement>或<xref:System.Windows.Media.MediaPlayer>时钟模式下，对象<xref:System.InvalidOperationException>将引发。  
  
 请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)了解有关时钟和时间线的更多信息。  
  
 请参阅[使用情节提要控制 MediaElement](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md) 了解时钟模式的示例。  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>MediaElement 类  
 将媒体添加到应用程序非常简单，只添加<xref:System.Windows.Controls.MediaElement>控制转移到[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]的应用程序并提供<xref:System.Uri>到你想要包括的媒体。 所有 [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 支持的媒体类型都受到 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 的支持。 下面的示例演示的简单用法<xref:System.Windows.Controls.MediaElement>中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 在此示例中，媒体一旦加载会自动播放。 媒体完成播放后会关闭并且所有媒体资源已发布（包括视频内存）。 这是默认行为的<xref:System.Windows.Controls.MediaElement>对象，并由控制<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>和<xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>属性。  
  
### <a name="controlling-a-mediaelement"></a>控制 MediaElement  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>和<xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>属性控制的行为<xref:System.Windows.Controls.MediaElement>时<xref:System.Windows.FrameworkElement.IsLoaded%2A>是`true`或`false`分别。 <xref:System.Windows.Controls.MediaState>设置了属性以影响媒体播放行为。 例如，默认值<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>是<xref:System.Windows.Controls.MediaState.Play>和默认<xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>是<xref:System.Windows.Controls.MediaState.Close>。 这意味着，只要<xref:System.Windows.Controls.MediaElement>加载和预播放已完成，则媒体开始播放。 一旦播放完毕，媒体就会关闭并且发布所有媒体资源。  
  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>和<xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>属性不控制媒体的播放的唯一方法。 在时钟模式下，可以控制时钟<xref:System.Windows.Controls.MediaElement>和时，具有控制权的交互式控制方法<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>是<xref:System.Windows.Controls.MediaState.Manual>。 <xref:System.Windows.Controls.MediaElement> 通过评估以下优先级来处理这种控制争用。  
  
1.  <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>。 卸载媒体时就位。 这可确保，默认情况下，释放所有媒体资源，即使<xref:System.Windows.Media.MediaClock>与关联<xref:System.Windows.Controls.MediaElement>。  
  
2.  <xref:System.Windows.Media.MediaClock>。 就地时媒体具有<xref:System.Windows.Controls.MediaElement.Clock%2A>。 如果卸载媒体，则<xref:System.Windows.Media.MediaClock>将会生效的前提下尽可能<xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>是<xref:System.Windows.Controls.MediaState.Manual>。 时钟模式始终重写的加载的行为<xref:System.Windows.Controls.MediaElement>。  
  
3.  <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>。 加载媒体时就位。  
  
4.  交互式控制方法。 在放置时<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>是<xref:System.Windows.Controls.MediaState.Manual>。 可用的控制方法是<xref:System.Windows.Controls.MediaElement.Play%2A>， <xref:System.Windows.Controls.MediaElement.Pause%2A>， <xref:System.Windows.Controls.MediaElement.Close%2A>，和<xref:System.Windows.Controls.MediaElement.Stop%2A>。  
  
### <a name="displaying-a-mediaelement"></a>显示 MediaElement  
 若要显示<xref:System.Windows.Controls.MediaElement>它必须具有呈现内容，其中包含以其<xref:System.Windows.FrameworkElement.ActualWidth%2A>和<xref:System.Windows.FrameworkElement.ActualHeight%2A>属性设置为零直到加载内容。 对于仅包含音频的内容，这些属性将始终为零。 有关视频内容，一次<xref:System.Windows.Controls.MediaElement.MediaOpened>引发事件<xref:System.Windows.FrameworkElement.ActualWidth%2A>和<xref:System.Windows.FrameworkElement.ActualHeight%2A>将报表加载的介质的大小。 这意味着，直到加载媒体，<xref:System.Windows.Controls.MediaElement>不占用任何物理空间[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]除非<xref:System.Windows.FrameworkElement.Width%2A>或<xref:System.Windows.FrameworkElement.Height%2A>属性设置。  
  
 同时设置<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性将导致要拉伸以填充区域为提供的媒体<xref:System.Windows.Controls.MediaElement>。 若要保留的媒体原始纵横比，或者<xref:System.Windows.FrameworkElement.Width%2A>或<xref:System.Windows.FrameworkElement.Height%2A>属性应为组而不是两个。 同时设置<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性将导致在可能不希望的固定的元素大小中呈现的媒体。  
  
 要避免出现固定大小元素，[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 可以预滚媒体。 这可通过设置<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>为<xref:System.Windows.Controls.MediaState.Play>或<xref:System.Windows.Controls.MediaState.Pause>。 在<xref:System.Windows.Controls.MediaState.Pause>状态时，媒体会预先缓冲，并会显示第一帧。 在<xref:System.Windows.Controls.MediaState.Play>状态下，媒体会预先缓冲，开始播放。  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>MediaPlayer 类  
 其中<xref:System.Windows.Controls.MediaElement>类是框架元素时，<xref:System.Windows.Media.MediaPlayer>类旨在用于<xref:System.Windows.Media.Drawing>对象。 当可以牺牲 framework 级别功能，以获得性能优势或在需要时，将使用图形对象<xref:System.Windows.Freezable>功能。 <xref:System.Windows.Media.MediaPlayer> 可以同时提供你的应用程序中的媒体内容要利用这些功能。 如<xref:System.Windows.Controls.MediaElement>，<xref:System.Windows.Media.MediaPlayer>可在独立于或不时钟模式，但不是具有<xref:System.Windows.Controls.MediaElement>对象的卸载和加载状态。 这将减少播放控制的复杂程度<xref:System.Windows.Media.MediaPlayer>。  
  
### <a name="controlling-mediaplayer"></a>控制 MediaPlayer  
 因为<xref:System.Windows.Media.MediaPlayer>是无状态的有只有两种方式控制媒体的播放。  
  
1.  交互式控制方法。 在独立模式下时就地 (`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A>属性)。  
  
2.  <xref:System.Windows.Media.MediaClock>。 就地时媒体具有<xref:System.Windows.Media.MediaPlayer.Clock%2A>。  
  
### <a name="displaying-a-mediaplayer"></a>显示 MediaPlayer  
 从技术上讲，<xref:System.Windows.Media.MediaPlayer>无法显示，因为它没有任何物理表示形式。 但是，使用它来显示中的媒体<xref:System.Windows.Media.Drawing>使用<xref:System.Windows.Media.VideoDrawing>类。 下面的示例演示了利用<xref:System.Windows.Media.VideoDrawing>以显示媒体。  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 请参阅[绘制对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)有关详细信息<xref:System.Windows.Media.Drawing>对象。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.DrawingGroup>  
 [布局](../../../../docs/framework/wpf/advanced/layout.md)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)
