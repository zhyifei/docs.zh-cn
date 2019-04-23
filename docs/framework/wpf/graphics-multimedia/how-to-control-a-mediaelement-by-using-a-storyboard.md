---
title: 如何：使用情节提要控制 MediaElement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multimedia [WPF], controlling playback of media with Storyboards
- controlling playback of media [WPF], with Storyboards
- Storyboards [WPF], controlling playback of media with
- media [WPF], controlling playback with Storyboards
- playback of media [WPF], controlling with Storyboards
ms.assetid: 6128ca77-b826-4e36-b968-6f237157c543
ms.openlocfilehash: ae785e11b1da0f2c408b24021ad46ab071419378
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100309"
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="62650-102">如何：使用情节提要控制 MediaElement</span><span class="sxs-lookup"><span data-stu-id="62650-102">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="62650-103">此示例演示如何控制<xref:System.Windows.Controls.MediaElement>通过使用<xref:System.Windows.Media.MediaTimeline>中<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="62650-103">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62650-104">示例</span><span class="sxs-lookup"><span data-stu-id="62650-104">Example</span></span>  
 <span data-ttu-id="62650-105">当你使用<xref:System.Windows.Media.MediaTimeline>中<xref:System.Windows.Media.Animation.Storyboard>控制的计时<xref:System.Windows.Controls.MediaElement>，功能是相同的功能的其他<xref:System.Windows.Media.Animation.Timeline>对象，例如动画。</span><span class="sxs-lookup"><span data-stu-id="62650-105">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="62650-106">例如，<xref:System.Windows.Media.MediaTimeline>使用<xref:System.Windows.Media.Animation.Timeline>属性，如<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>属性来指定何时开始<xref:System.Windows.Controls.MediaElement>（启动媒体的播放）。</span><span class="sxs-lookup"><span data-stu-id="62650-106">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="62650-107">它还使用<xref:System.Windows.Media.Animation.Timeline.Duration%2A>属性来指定多长时间<xref:System.Windows.Controls.MediaElement>处于活动状态 （的媒体的播放持续时间）。</span><span class="sxs-lookup"><span data-stu-id="62650-107">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="62650-108">有关使用详细信息<xref:System.Windows.Media.Animation.Timeline>对象与<xref:System.Windows.Media.Animation.Storyboard>，请参阅[情节提要概述](storyboards-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="62650-108">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="62650-109">此示例演示如何创建简单的媒体播放器使用<xref:System.Windows.Media.MediaTimeline>来控制播放。</span><span class="sxs-lookup"><span data-stu-id="62650-109">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="62650-110">Media player 还包括播放、 暂停、 继续和停止按钮。</span><span class="sxs-lookup"><span data-stu-id="62650-110">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="62650-111">播放机也有<xref:System.Windows.Controls.Slider>充当一个进度栏控件。</span><span class="sxs-lookup"><span data-stu-id="62650-111">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="62650-112">下面的示例创建[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]媒体播放器。</span><span class="sxs-lookup"><span data-stu-id="62650-112">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="62650-113">以下示例创建进度栏的功能。</span><span class="sxs-lookup"><span data-stu-id="62650-113">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="62650-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="62650-114">See also</span></span>

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="62650-115">控制 MediaElement（播放、暂停、停止、音量和速度）</span><span class="sxs-lookup"><span data-stu-id="62650-115">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [<span data-ttu-id="62650-116">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="62650-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="62650-117">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="62650-117">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="62650-118">动画概述</span><span class="sxs-lookup"><span data-stu-id="62650-118">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="62650-119">帮助主题</span><span class="sxs-lookup"><span data-stu-id="62650-119">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="62650-120">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="62650-120">Graphics and Multimedia</span></span>](index.md)
