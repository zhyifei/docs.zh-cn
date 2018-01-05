---
title: "如何：使用演示图板控制 MediaElement"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f52801ee3704c13ec5213cfc54b6392baa97e245
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="9b773-102">如何：使用演示图板控制 MediaElement</span><span class="sxs-lookup"><span data-stu-id="9b773-102">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="9b773-103">此示例演示如何控制<xref:System.Windows.Controls.MediaElement>使用<xref:System.Windows.Media.MediaTimeline>中<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="9b773-103">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b773-104">示例</span><span class="sxs-lookup"><span data-stu-id="9b773-104">Example</span></span>  
 <span data-ttu-id="9b773-105">当你使用<xref:System.Windows.Media.MediaTimeline>中<xref:System.Windows.Media.Animation.Storyboard>来控制的计时<xref:System.Windows.Controls.MediaElement>，功能等同于其他功能<xref:System.Windows.Media.Animation.Timeline>对象，例如动画。</span><span class="sxs-lookup"><span data-stu-id="9b773-105">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="9b773-106">例如，<xref:System.Windows.Media.MediaTimeline>使用<xref:System.Windows.Media.Animation.Timeline>属性，例如<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>属性来指定何时启动<xref:System.Windows.Controls.MediaElement>（启动媒体播放）。</span><span class="sxs-lookup"><span data-stu-id="9b773-106">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="9b773-107">它还使用<xref:System.Windows.Media.Animation.Timeline.Duration%2A>属性来指定多长时间<xref:System.Windows.Controls.MediaElement>处于活动状态 （持续时间的媒体播放）。</span><span class="sxs-lookup"><span data-stu-id="9b773-107">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="9b773-108">有关使用<xref:System.Windows.Media.Animation.Timeline>对象与<xref:System.Windows.Media.Animation.Storyboard>，请参阅[情节提要概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9b773-108">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="9b773-109">此示例演示如何创建使用简单的媒体播放器<xref:System.Windows.Media.MediaTimeline>来控制播放。</span><span class="sxs-lookup"><span data-stu-id="9b773-109">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="9b773-110">媒体播放器包括播放、 暂停、 继续和停止按钮。</span><span class="sxs-lookup"><span data-stu-id="9b773-110">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="9b773-111">播放器还具有<xref:System.Windows.Controls.Slider>充当一个进度栏控件。</span><span class="sxs-lookup"><span data-stu-id="9b773-111">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="9b773-112">下面的示例创建[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]媒体播放器。</span><span class="sxs-lookup"><span data-stu-id="9b773-112">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="9b773-113">下面的示例创建进度栏的功能。</span><span class="sxs-lookup"><span data-stu-id="9b773-113">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="9b773-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b773-114">See Also</span></span>  
 <xref:System.Windows.Controls.MediaElement>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [<span data-ttu-id="9b773-115">控制 MediaElement（播放、暂停、停止、音量和速度）</span><span class="sxs-lookup"><span data-stu-id="9b773-115">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)  
 [<span data-ttu-id="9b773-116">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="9b773-116">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="9b773-117">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="9b773-117">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="9b773-118">动画概述</span><span class="sxs-lookup"><span data-stu-id="9b773-118">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="9b773-119">帮助主题</span><span class="sxs-lookup"><span data-stu-id="9b773-119">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [<span data-ttu-id="9b773-120">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="9b773-120">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
