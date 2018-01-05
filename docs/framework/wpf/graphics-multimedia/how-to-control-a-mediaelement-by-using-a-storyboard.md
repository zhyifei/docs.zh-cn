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
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a>如何：使用演示图板控制 MediaElement
此示例演示如何控制<xref:System.Windows.Controls.MediaElement>使用<xref:System.Windows.Media.MediaTimeline>中<xref:System.Windows.Media.Animation.Storyboard>。  
  
## <a name="example"></a>示例  
 当你使用<xref:System.Windows.Media.MediaTimeline>中<xref:System.Windows.Media.Animation.Storyboard>来控制的计时<xref:System.Windows.Controls.MediaElement>，功能等同于其他功能<xref:System.Windows.Media.Animation.Timeline>对象，例如动画。 例如，<xref:System.Windows.Media.MediaTimeline>使用<xref:System.Windows.Media.Animation.Timeline>属性，例如<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>属性来指定何时启动<xref:System.Windows.Controls.MediaElement>（启动媒体播放）。 它还使用<xref:System.Windows.Media.Animation.Timeline.Duration%2A>属性来指定多长时间<xref:System.Windows.Controls.MediaElement>处于活动状态 （持续时间的媒体播放）。 有关使用<xref:System.Windows.Media.Animation.Timeline>对象与<xref:System.Windows.Media.Animation.Storyboard>，请参阅[情节提要概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)。  
  
 此示例演示如何创建使用简单的媒体播放器<xref:System.Windows.Media.MediaTimeline>来控制播放。 媒体播放器包括播放、 暂停、 继续和停止按钮。 播放器还具有<xref:System.Windows.Controls.Slider>充当一个进度栏控件。  
  
 下面的示例创建[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]媒体播放器。  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 下面的示例创建进度栏的功能。  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.MediaElement>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [控制 MediaElement（播放、暂停、停止、音量和速度）](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)  
 [演示图板概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [图形和多媒体](../../../../docs/framework/wpf/graphics-multimedia/index.md)
