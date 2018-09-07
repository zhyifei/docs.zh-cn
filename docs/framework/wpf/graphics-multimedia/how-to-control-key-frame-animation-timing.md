---
title: 如何：控制关键帧动画的计时
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-fram animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: d65bf6f7643adf1d98d468853ae8017a4a6554ac
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086188"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="ecae1-102">如何：控制关键帧动画的计时</span><span class="sxs-lookup"><span data-stu-id="ecae1-102">How to: Control Key-Frame Animation Timing</span></span>
<span data-ttu-id="ecae1-103">此示例演示如何控制关键帧动画中的关键帧的时间。</span><span class="sxs-lookup"><span data-stu-id="ecae1-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="ecae1-104">像其他动画关键帧动画具有<xref:System.Windows.Media.Animation.Timeline.Duration%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ecae1-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="ecae1-105">除了指定动画的持续时间，您需要指定该持续时间的哪一部分分配给每个其关键帧。</span><span class="sxs-lookup"><span data-stu-id="ecae1-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="ecae1-106">若要分配的时间，则指定<xref:System.Windows.Media.Animation.KeyTime>中每个关键帧动画。</span><span class="sxs-lookup"><span data-stu-id="ecae1-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>  
  
 <span data-ttu-id="ecae1-107"><xref:System.Windows.Media.Animation.KeyTime>为每个关键帧指定 （未指定关键帧播放的时间长度） 的关键帧结束时。</span><span class="sxs-lookup"><span data-stu-id="ecae1-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="ecae1-108">您可以指定<xref:System.Windows.Media.Animation.KeyTime>作为<xref:System.TimeSpan>值，以百分比表示，或作为<xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>或<xref:System.Windows.Media.Animation.KeyTime.Paced%2A>特殊值。</span><span class="sxs-lookup"><span data-stu-id="ecae1-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecae1-109">示例</span><span class="sxs-lookup"><span data-stu-id="ecae1-109">Example</span></span>  
 <span data-ttu-id="ecae1-110">下面的示例使用<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>若要在屏幕上对矩形进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="ecae1-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="ecae1-111">使用设置关键帧的关键时间<xref:System.TimeSpan>值。</span><span class="sxs-lookup"><span data-stu-id="ecae1-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 <span data-ttu-id="ecae1-112">下图显示达到每个关键帧的值。</span><span class="sxs-lookup"><span data-stu-id="ecae1-112">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="ecae1-113">![在 3、 4 和 10 秒时达到的键值](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="ecae1-113">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>  
  
 <span data-ttu-id="ecae1-114">下一个示例演示具有完全相同，只不过使用百分比值设置关键帧的关键时间的动画。</span><span class="sxs-lookup"><span data-stu-id="ecae1-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xaml[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 <span data-ttu-id="ecae1-115">下图显示达到每个关键帧的值。</span><span class="sxs-lookup"><span data-stu-id="ecae1-115">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="ecae1-116">![在 3、 4 和 10 秒时达到的键值](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="ecae1-116">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>  
  
 <span data-ttu-id="ecae1-117">下面的示例使用<xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>关键时间值。</span><span class="sxs-lookup"><span data-stu-id="ecae1-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xaml[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 <span data-ttu-id="ecae1-118">下图显示达到每个关键帧的值。</span><span class="sxs-lookup"><span data-stu-id="ecae1-118">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="ecae1-119">![在 3.3、 6.6 和 9.9 秒时达到的关键值](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="ecae1-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>  
  
 <span data-ttu-id="ecae1-120">最后一个示例使用<xref:System.Windows.Media.Animation.KeyTime.Paced%2A>关键时间值。</span><span class="sxs-lookup"><span data-stu-id="ecae1-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xaml[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 <span data-ttu-id="ecae1-121">下图显示达到每个关键帧的值。</span><span class="sxs-lookup"><span data-stu-id="ecae1-121">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="ecae1-122">![密钥值在 0、 5 和 10 秒时达到](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="ecae1-122">![Key values are reached at 0, 5, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>  
  
 <span data-ttu-id="ecae1-123">为简单起见，此示例使用本地动画的代码版本不是演示图板，因为仅将一个动画应用到单个属性，但可以修改示例以改为使用情节提要。</span><span class="sxs-lookup"><span data-stu-id="ecae1-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="ecae1-124">有关演示如何声明中的代码将情节提要的示例，请参阅[使用情节提要对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="ecae1-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="ecae1-125">有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="ecae1-125">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span> <span data-ttu-id="ecae1-126">关键帧动画的详细信息，请参阅[关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ecae1-126">For more information about key frame animations, see the [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecae1-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecae1-127">See Also</span></span>  
 [<span data-ttu-id="ecae1-128">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="ecae1-128">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="ecae1-129">动画概述</span><span class="sxs-lookup"><span data-stu-id="ecae1-129">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="ecae1-130">帮助主题</span><span class="sxs-lookup"><span data-stu-id="ecae1-130">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
