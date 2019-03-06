---
title: 如何：播放带有动画的媒体
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 0dc39d08ef17a628675018c17602623f2efd0173
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372897"
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="b72d9-102">如何：播放带有动画的媒体</span><span class="sxs-lookup"><span data-stu-id="b72d9-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="b72d9-103">此示例演示如何通过使用在同一时间播放媒体和动画<xref:System.Windows.Media.MediaTimeline>并<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>中相同的类<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="b72d9-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b72d9-104">示例</span><span class="sxs-lookup"><span data-stu-id="b72d9-104">Example</span></span>  
 <span data-ttu-id="b72d9-105">可以使用一个或多个<xref:System.Windows.Media.MediaTimeline>中的对象<xref:System.Windows.Media.Animation.Storyboard>与其他<xref:System.Windows.Media.Animation.Timeline>对象，例如动画。</span><span class="sxs-lookup"><span data-stu-id="b72d9-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="b72d9-106">下面的示例设置<xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>的属性<xref:System.Windows.Media.Animation.Storyboard>的值为`Slip`，它指定动画不播放之前在媒体 （在此示例中为视频） 进行。</span><span class="sxs-lookup"><span data-stu-id="b72d9-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="b72d9-107">如果媒体播放因加载时间而延迟，可能需要此功能。</span><span class="sxs-lookup"><span data-stu-id="b72d9-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b72d9-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="b72d9-108">See also</span></span>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [<span data-ttu-id="b72d9-109">帮助主题</span><span class="sxs-lookup"><span data-stu-id="b72d9-109">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="b72d9-110">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="b72d9-110">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="b72d9-111">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="b72d9-111">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="b72d9-112">动画概述</span><span class="sxs-lookup"><span data-stu-id="b72d9-112">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="b72d9-113">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="b72d9-113">Graphics and Multimedia</span></span>](index.md)
