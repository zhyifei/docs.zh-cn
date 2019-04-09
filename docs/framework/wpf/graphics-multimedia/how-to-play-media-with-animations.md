---
title: 如何：播放带有动画的媒体
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 200f9d62c67a02088fe5a5789cdb41a04837d430
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079898"
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="a3609-102">如何：播放带有动画的媒体</span><span class="sxs-lookup"><span data-stu-id="a3609-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="a3609-103">此示例演示如何通过使用在同一时间播放媒体和动画<xref:System.Windows.Media.MediaTimeline>并<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>中相同的类<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="a3609-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3609-104">示例</span><span class="sxs-lookup"><span data-stu-id="a3609-104">Example</span></span>  
 <span data-ttu-id="a3609-105">可以使用一个或多个<xref:System.Windows.Media.MediaTimeline>中的对象<xref:System.Windows.Media.Animation.Storyboard>与其他<xref:System.Windows.Media.Animation.Timeline>对象，例如动画。</span><span class="sxs-lookup"><span data-stu-id="a3609-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="a3609-106">下面的示例设置<xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>的属性<xref:System.Windows.Media.Animation.Storyboard>的值为`Slip`，它指定动画不播放之前在媒体 （在此示例中为视频） 进行。</span><span class="sxs-lookup"><span data-stu-id="a3609-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="a3609-107">如果媒体播放因加载时间而延迟，可能需要此功能。</span><span class="sxs-lookup"><span data-stu-id="a3609-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a3609-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3609-108">See also</span></span>

- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [<span data-ttu-id="a3609-109">帮助主题</span><span class="sxs-lookup"><span data-stu-id="a3609-109">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="a3609-110">演示图板概述</span><span class="sxs-lookup"><span data-stu-id="a3609-110">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="a3609-111">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="a3609-111">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="a3609-112">动画概述</span><span class="sxs-lookup"><span data-stu-id="a3609-112">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="a3609-113">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="a3609-113">Graphics and Multimedia</span></span>](index.md)
