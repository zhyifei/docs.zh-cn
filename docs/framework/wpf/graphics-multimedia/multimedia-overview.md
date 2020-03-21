---
title: 多媒体概述
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: d4abf4d9fd324ffbf2737dc686c02e50ca1a8a5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181883"
---
# <a name="multimedia-overview"></a>多媒体概述
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的多媒体功能能够使音频和视频集成到应用程序，增强用户体验。 本主题介绍了 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的多媒体功能。  

<a name="mediaapi"></a>
## <a name="media-api"></a>媒体 API  
 <xref:System.Windows.Controls.MediaElement>和<xref:System.Windows.Media.MediaPlayer>类用于显示音频或视频内容。 可以以交互方式或时钟控制这些类。 这些类可以在 Microsoft Windows 媒体播放器 10 控件上用于媒体播放。 要使用哪个类取决于方案。  
  
 <xref:System.Windows.Controls.MediaElement>是布局<xref:System.Windows.UIElement>支持的 ，可以用作[Layout](../advanced/layout.md)许多控件的内容。 它也可用在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 与代码中。 <xref:System.Windows.Media.MediaPlayer>另一方面，是为<xref:System.Windows.Media.Drawing>对象设计的，并且缺少布局支持。 使用 加载的媒体<xref:System.Windows.Media.MediaPlayer>只能使用<xref:System.Windows.Media.VideoDrawing>或 直接与 交互显示<xref:System.Windows.Media.DrawingContext>。 <xref:System.Windows.Media.MediaPlayer>不能在 XAML 中使用。  
  
 有关绘图对象和绘图上下文的详细信息，请参阅 [Drawing 对象概述](drawing-objects-overview.md)。  
  
> [!NOTE]
> 使用应用程序分发媒体时，不可将媒体文件用作项目资源。 在项目文件中，必须改为将媒体类型设置为 `Content` 并将 `CopyToOutputDirectory` 设置为 `PreserveNewest` 或 `Always`。  
  
<a name="mediaplaybackmodes"></a>
## <a name="media-playback-modes"></a>媒体播放模式  
  
> [!NOTE]
> 和<xref:System.Windows.Controls.MediaElement><xref:System.Windows.Media.MediaPlayer>都有类似的成员。 本节中的链接引用<xref:System.Windows.Controls.MediaElement>类成员。 除非特别注意，否则在<xref:System.Windows.Controls.MediaElement>类中链接的成员也可以在类中找到。 <xref:System.Windows.Media.MediaPlayer>  
  
 要了解 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的媒体播放，需要了解可以播放媒体的不同模式。 <xref:System.Windows.Controls.MediaElement>和<xref:System.Windows.Media.MediaPlayer>都可以在两种不同的媒体模式下使用，即独立模式和时钟模式。 媒体模式由<xref:System.Windows.Controls.MediaElement.Clock%2A>属性确定。 当<xref:System.Windows.Controls.MediaElement.Clock%2A>`null`为 时，媒体对象处于独立模式。 当<xref:System.Windows.Controls.MediaElement.Clock%2A>为非空时，媒体对象处于时钟模式。 默认情况下，媒体对象处于独立模式。  
  
### <a name="independent-mode"></a>独立模式  
 在独立模式下，媒体内容驱动媒体播放。 独立模式可实现下列选项：  
  
- <xref:System.Uri>可以直接指定介质。  
  
- 可以直接控制媒体播放。  
  
- <xref:System.Windows.Controls.MediaElement.Position%2A>可以修改媒体和<xref:System.Windows.Controls.MediaElement.SpeedRatio%2A>属性。  
  
 通过设置<xref:System.Windows.Controls.MediaElement>对象<xref:System.Windows.Controls.MediaElement.Source%2A>的属性或调用<xref:System.Windows.Media.MediaPlayer>对象<xref:System.Windows.Media.MediaPlayer.Open%2A>的方法来加载媒体。  
  
 要在独立模式下控制媒体播放，可使用媒体对象的控制方法。 可用的控制方法是<xref:System.Windows.Controls.MediaElement.Play%2A>、<xref:System.Windows.Controls.MediaElement.Pause%2A><xref:System.Windows.Controls.MediaElement.Close%2A>和<xref:System.Windows.Controls.MediaElement.Stop%2A>。 对于<xref:System.Windows.Controls.MediaElement>，使用这些方法的交互式控件仅在 设置为<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>时才可用<xref:System.Windows.Controls.MediaState.Manual>。 这些方法在媒体对象处于时钟模式时不可用。  
  
 请参阅[控制 MediaElement（Play、Pause、Stop、Volume 和 Speed）](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)了解独立模式的示例。  
  
### <a name="clock-mode"></a>时钟模式  
 在时钟模式下，驱动器<xref:System.Windows.Media.MediaTimeline>媒体播放。 时钟模式具有以下特征：  
  
- 媒体的是<xref:System.Uri>间接设置通过<xref:System.Windows.Media.MediaTimeline>。  
  
- 可由时钟控制媒体播放。 不可使用媒体对象的控制方法。  
  
- 通过设置<xref:System.Windows.Media.MediaTimeline>对象<xref:System.Windows.Media.MediaTimeline.Source%2A>的属性、从时间线创建时钟以及将时钟分配给媒体对象来加载媒体。 当<xref:System.Windows.Media.MediaTimeline>内部<xref:System.Windows.Media.Animation.Storyboard>目标 时，媒体也会以这种方式加载<xref:System.Windows.Controls.MediaElement>。  
  
 要控制时钟模式下的媒体播放，<xref:System.Windows.Media.Animation.ClockController>必须使用控制方法。 A<xref:System.Windows.Media.Animation.ClockController>是从<xref:System.Windows.Media.Animation.ClockController>的属性获取的<xref:System.Windows.Media.MediaClock>。 如果在时钟模式下尝试使用 或<xref:System.Windows.Controls.MediaElement><xref:System.Windows.Media.MediaPlayer>对象的控制方法，将引发 。 <xref:System.InvalidOperationException>  
  
 请参阅[动画概述](animation-overview.md)了解有关时钟和时间线的更多信息。  
  
 请参阅[使用情节提要控制 MediaElement](how-to-control-a-mediaelement-by-using-a-storyboard.md) 了解时钟模式的示例。  
  
<a name="mediaelement"></a>
## <a name="mediaelement-class"></a>MediaElement 类  
 向应用程序添加媒体非常简单，只需向<xref:System.Windows.Controls.MediaElement>[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]应用程序的控件添加控件，并向要包括的媒体提供<xref:System.Uri>一样。 Microsoft Windows 媒体播放器 10 支持的所有媒体类型[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]。 下面的示例显示了<xref:System.Windows.Controls.MediaElement>中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]的简单用法。  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 在此示例中，媒体一旦加载会自动播放。 媒体完成播放后会关闭并且所有媒体资源已发布（包括视频内存）。 这是对象的默认行为，<xref:System.Windows.Controls.MediaElement>由<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>和<xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>属性控制。  
  
### <a name="controlling-a-mediaelement"></a>控制 MediaElement  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A><xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>和 属性分别控制<xref:System.Windows.Controls.MediaElement>时<xref:System.Windows.FrameworkElement.IsLoaded%2A>`true`或`false`的行为。 属性<xref:System.Windows.Controls.MediaState>设置为影响媒体播放行为。 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>例如，默认值<xref:System.Windows.Controls.MediaState.Play>为，默认值<xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>为<xref:System.Windows.Controls.MediaState.Close>。 这意味着，一旦<xref:System.Windows.Controls.MediaElement>加载和预卷完成，媒体开始播放。 一旦播放完毕，媒体就会关闭并且发布所有媒体资源。  
  
 和<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A><xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>属性不是控制媒体播放的唯一方法。 在时钟模式下，时钟可以控制，<xref:System.Windows.Controls.MediaElement>交互控制方法可以控制何时<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>是<xref:System.Windows.Controls.MediaState.Manual>。 <xref:System.Windows.Controls.MediaElement>通过评估以下优先级来处理这种控制竞争。  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. 卸载媒体时就位。 这可确保默认情况下释放所有媒体资源，即使<xref:System.Windows.Media.MediaClock>与 关联也是如此。 <xref:System.Windows.Controls.MediaElement>  
  
2. <xref:System.Windows.Media.MediaClock>. 当媒体具有 时就<xref:System.Windows.Controls.MediaElement.Clock%2A>位。 如果卸载媒体，则 只要<xref:System.Windows.Media.MediaClock><xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>是<xref:System.Windows.Controls.MediaState.Manual>， 就会生效。 时钟模式始终覆盖 的<xref:System.Windows.Controls.MediaElement>加载行为。  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. 加载媒体时就位。  
  
4. 交互式控制方法。 在原地<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>时<xref:System.Windows.Controls.MediaState.Manual>是 。 可用的控制方法是<xref:System.Windows.Controls.MediaElement.Play%2A>、<xref:System.Windows.Controls.MediaElement.Pause%2A><xref:System.Windows.Controls.MediaElement.Close%2A>和<xref:System.Windows.Controls.MediaElement.Stop%2A>。  
  
### <a name="displaying-a-mediaelement"></a>显示 MediaElement  
 要显示<xref:System.Windows.Controls.MediaElement>的内容，它必须具有要呈现的内容，并且其<xref:System.Windows.FrameworkElement.ActualWidth%2A>和<xref:System.Windows.FrameworkElement.ActualHeight%2A>属性将设置为零，直到加载内容。 对于仅包含音频的内容，这些属性将始终为零。 对于视频内容，一旦<xref:System.Windows.Controls.MediaElement.MediaOpened>事件被引发，<xref:System.Windows.FrameworkElement.ActualWidth%2A>将<xref:System.Windows.FrameworkElement.ActualHeight%2A>报告加载介质的大小。 这意味着，在加载媒体之前<xref:System.Windows.Controls.MediaElement>，不会占用 或[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]<xref:System.Windows.FrameworkElement.Width%2A><xref:System.Windows.FrameworkElement.Height%2A>属性中的任何物理空间。  
  
 设置 和<xref:System.Windows.FrameworkElement.Width%2A><xref:System.Windows.FrameworkElement.Height%2A>属性将导致媒体拉伸以填充 为 提供的区域<xref:System.Windows.Controls.MediaElement>。 为了保持媒体的原始纵横比，应设置<xref:System.Windows.FrameworkElement.Width%2A>或<xref:System.Windows.FrameworkElement.Height%2A>属性，但不能同时设置这两种。 设置<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性将导致介质以固定元素大小呈现，而该大小可能不可取。  
  
 要避免出现固定大小元素，[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 可以预滚媒体。 这是通过将 设置为<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>或<xref:System.Windows.Controls.MediaState.Play><xref:System.Windows.Controls.MediaState.Pause>。 在状态<xref:System.Windows.Controls.MediaState.Pause>下，媒体将预卷并呈现第一帧。 在一<xref:System.Windows.Controls.MediaState.Play>种状态下，媒体将预先播放并开始播放。  
  
<a name="mediaplayer"></a>
## <a name="mediaplayer-class"></a>MediaPlayer 类  
 当<xref:System.Windows.Controls.MediaElement>类是框架元素时，<xref:System.Windows.Media.MediaPlayer>类被设计为用于<xref:System.Windows.Media.Drawing>对象。 当可以牺牲框架级别要素以获得性能优势时，或者在需要时<xref:System.Windows.Freezable>，使用绘图对象。 <xref:System.Windows.Media.MediaPlayer>使您能够利用这些功能，同时在应用程序中提供媒体内容。 喜欢<xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> ，可以在独立模式或时钟模式下使用，<xref:System.Windows.Controls.MediaElement>但没有对象的卸载和加载状态。 这降低了 的<xref:System.Windows.Media.MediaPlayer>播放控制复杂性。  
  
### <a name="controlling-mediaplayer"></a>控制 MediaPlayer  
 因为它是<xref:System.Windows.Media.MediaPlayer>无状态的，只有两种方法可以控制媒体播放。  
  
1. 交互式控制方法。 在独立模式下就位（`null`<xref:System.Windows.Media.MediaPlayer.Clock%2A>属性）。  
  
2. <xref:System.Windows.Media.MediaClock>. 当媒体具有 时就<xref:System.Windows.Media.MediaPlayer.Clock%2A>位。  
  
### <a name="displaying-a-mediaplayer"></a>显示 MediaPlayer  
 从技术上讲，无法显示<xref:System.Windows.Media.MediaPlayer>，因为它没有物理表示形式。 但是，它可用于在<xref:System.Windows.Media.Drawing>使用<xref:System.Windows.Media.VideoDrawing>类中呈现媒体。 下面的示例演示了使用<xref:System.Windows.Media.VideoDrawing>显示媒体。  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 有关<xref:System.Windows.Media.Drawing>对象的详细信息，请参阅[绘图对象概述](drawing-objects-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.DrawingGroup>
- [布局](../advanced/layout.md)
- [如何使用主题](audio-and-video-how-to-topics.md)
