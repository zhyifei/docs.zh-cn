---
title: "如何：控制关键帧动画的计时"
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
- key frames [WPF], timing
- timing key-fram animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3bc3566cf25282749a09c5f2372cd1c81e3ce881
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="a6f6e-102">如何：控制关键帧动画的计时</span><span class="sxs-lookup"><span data-stu-id="a6f6e-102">How to: Control Key-Frame Animation Timing</span></span>
<span data-ttu-id="a6f6e-103">此示例演示如何控制的关键帧动画中的关键帧的计时。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="a6f6e-104">像其他动画关键帧动画具有<xref:System.Windows.Media.Animation.Timeline.Duration%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="a6f6e-105">除了指定动画的持续时间，你需要指定该持续时间的哪个部分分配给每个其关键帧。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="a6f6e-106">若要分配的时间，则指定<xref:System.Windows.Media.Animation.KeyTime>动画中每个关键帧的。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>  
  
 <span data-ttu-id="a6f6e-107"><xref:System.Windows.Media.Animation.KeyTime>每个关键帧指定时 （而不指定一个关键帧播放的时间长度） 关键帧结束。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="a6f6e-108">你可以指定<xref:System.Windows.Media.Animation.KeyTime>作为<xref:System.TimeSpan>值，为百分比，或作为<xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>或<xref:System.Windows.Media.Animation.KeyTime.Paced%2A>特殊值。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6f6e-109">示例</span><span class="sxs-lookup"><span data-stu-id="a6f6e-109">Example</span></span>  
 <span data-ttu-id="a6f6e-110">下面的示例使用<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>动画在屏幕的矩形。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="a6f6e-111">关键帧的关键时间设置与<xref:System.TimeSpan>值。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 <span data-ttu-id="a6f6e-112">如下图所示的每个关键帧的值为止。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-112">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="a6f6e-113">![在 3、 4 和 10 秒时达到键值](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="a6f6e-113">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>  
  
 <span data-ttu-id="a6f6e-114">下一个示例演示具有完全相同，只不过使用百分比值设置关键帧的关键时间的动画。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xaml[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 <span data-ttu-id="a6f6e-115">如下图所示的每个关键帧的值为止。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-115">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="a6f6e-116">![在 3、 4 和 10 秒时达到键值](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="a6f6e-116">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>  
  
 <span data-ttu-id="a6f6e-117">下一个示例使用<xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>关键时间值。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xaml[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 <span data-ttu-id="a6f6e-118">如下图所示的每个关键帧的值为止。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-118">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="a6f6e-119">![在 3.3、 6.6 和 9.9 秒时达到的关键值](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="a6f6e-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>  
  
 <span data-ttu-id="a6f6e-120">最后一个示例使用<xref:System.Windows.Media.Animation.KeyTime.Paced%2A>关键时间值。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xaml[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 <span data-ttu-id="a6f6e-121">如下图所示的每个关键帧的值为止。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-121">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="a6f6e-122">![在 0、 5 和 10 秒时达到键值](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="a6f6e-122">![Key values are reached at 0, 5, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>  
  
 <span data-ttu-id="a6f6e-123">为简单起见，此示例使用本地动画时，代码版本不是演示图板，因为单个动画应用于单个属性，但可以修改这些示例以改为使用情节提要。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="a6f6e-124">有关演示如何声明中的代码将情节提要的示例，请参阅[使用情节提要属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="a6f6e-125">有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-125">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span> <span data-ttu-id="a6f6e-126">关键帧动画有关的详细信息，请参阅[关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f6e-126">For more information about key frame animations, see the [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f6e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6f6e-127">See Also</span></span>  
 [<span data-ttu-id="a6f6e-128">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="a6f6e-128">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="a6f6e-129">动画概述</span><span class="sxs-lookup"><span data-stu-id="a6f6e-129">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="a6f6e-130">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="a6f6e-130">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
