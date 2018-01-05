---
title: "如何：播放带有动画的媒体"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44ebb89c25fc37292f82533c929aae44854db5c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="84e42-102">如何：播放带有动画的媒体</span><span class="sxs-lookup"><span data-stu-id="84e42-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="84e42-103">此示例演示如何在同一时间播放媒体和动画，通过使用<xref:System.Windows.Media.MediaTimeline>和<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>中相同的类<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="84e42-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84e42-104">示例</span><span class="sxs-lookup"><span data-stu-id="84e42-104">Example</span></span>  
 <span data-ttu-id="84e42-105">你可以使用一个或多个<xref:System.Windows.Media.MediaTimeline>中的对象<xref:System.Windows.Media.Animation.Storyboard>以及其他<xref:System.Windows.Media.Animation.Timeline>对象，例如动画。</span><span class="sxs-lookup"><span data-stu-id="84e42-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="84e42-106">下面的示例设置<xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>属性<xref:System.Windows.Media.Animation.Storyboard>为值`Slip`，该值指定动画不播放之前媒体 （在此示例中视频） 进行。</span><span class="sxs-lookup"><span data-stu-id="84e42-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="84e42-107">如果媒体播放因加载时间而延迟，可能需要此功能。</span><span class="sxs-lookup"><span data-stu-id="84e42-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="84e42-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="84e42-108">See Also</span></span>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>  
 [<span data-ttu-id="84e42-109">帮助主题</span><span class="sxs-lookup"><span data-stu-id="84e42-109">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [<span data-ttu-id="84e42-110">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="84e42-110">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="84e42-111">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="84e42-111">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="84e42-112">动画概述</span><span class="sxs-lookup"><span data-stu-id="84e42-112">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="84e42-113">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="84e42-113">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
