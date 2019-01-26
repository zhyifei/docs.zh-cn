---
title: 如何：播放带有动画的媒体
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: e6a011b1fa6f3551c3570370247fbae262b20e4c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594247"
---
# <a name="how-to-play-media-with-animations"></a>如何：播放带有动画的媒体
此示例演示如何通过使用在同一时间播放媒体和动画<xref:System.Windows.Media.MediaTimeline>并<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>中相同的类<xref:System.Windows.Media.Animation.Storyboard>。  
  
## <a name="example"></a>示例  
 可以使用一个或多个<xref:System.Windows.Media.MediaTimeline>中的对象<xref:System.Windows.Media.Animation.Storyboard>与其他<xref:System.Windows.Media.Animation.Timeline>对象，例如动画。  
  
 下面的示例设置<xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>的属性<xref:System.Windows.Media.Animation.Storyboard>的值为`Slip`，它指定动画不播放之前在媒体 （在此示例中为视频） 进行。 如果媒体播放因加载时间而延迟，可能需要此功能。  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)
- [演示图板概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
- [关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [图形和多媒体](../../../../docs/framework/wpf/graphics-multimedia/index.md)
