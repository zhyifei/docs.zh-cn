---
title: 如何：控制关键帧动画的计时
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344739"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="5ea75-102">如何：控制关键帧动画的计时</span><span class="sxs-lookup"><span data-stu-id="5ea75-102">How to: Control Key-Frame Animation Timing</span></span>

<span data-ttu-id="5ea75-103">此示例演示如何控制关键帧动画中关键帧的计时。</span><span class="sxs-lookup"><span data-stu-id="5ea75-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="5ea75-104">与其他动画一样，关键帧动画具有属性<xref:System.Windows.Media.Animation.Timeline.Duration%2A>。</span><span class="sxs-lookup"><span data-stu-id="5ea75-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="5ea75-105">除了指定动画的持续时间外，还需要指定将该持续时间的哪一部分分配给其每个关键帧。</span><span class="sxs-lookup"><span data-stu-id="5ea75-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="5ea75-106">要指定时间，请为动画中的每个关键<xref:System.Windows.Media.Animation.KeyTime>帧指定 a。</span><span class="sxs-lookup"><span data-stu-id="5ea75-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>

<span data-ttu-id="5ea75-107">每个<xref:System.Windows.Media.Animation.KeyTime>关键帧指定关键帧何时结束（它不指定关键帧播放的时间长度）。</span><span class="sxs-lookup"><span data-stu-id="5ea75-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="5ea75-108"><xref:System.Windows.Media.Animation.KeyTime>您可以将 指定<xref:System.TimeSpan>为值、百分比或 或<xref:System.Windows.Media.Animation.KeyTime.Uniform%2A><xref:System.Windows.Media.Animation.KeyTime.Paced%2A>特殊值。</span><span class="sxs-lookup"><span data-stu-id="5ea75-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>

## <a name="example"></a><span data-ttu-id="5ea75-109">示例</span><span class="sxs-lookup"><span data-stu-id="5ea75-109">Example</span></span>

<span data-ttu-id="5ea75-110">下面的示例使用<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>在屏幕上为矩形设置动画。</span><span class="sxs-lookup"><span data-stu-id="5ea75-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="5ea75-111">关键帧的键时间设置的值<xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="5ea75-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

<span data-ttu-id="5ea75-112">下图显示了何时达到每个关键帧的值。</span><span class="sxs-lookup"><span data-stu-id="5ea75-112">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="5ea75-113">![在 3、4 和 10 秒时达到的关键值](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="5ea75-113">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>

<span data-ttu-id="5ea75-114">下一个示例显示相同的动画，只不过关键帧的键时间设置的百分比值。</span><span class="sxs-lookup"><span data-stu-id="5ea75-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

<span data-ttu-id="5ea75-115">下图显示了何时达到每个关键帧的值。</span><span class="sxs-lookup"><span data-stu-id="5ea75-115">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="5ea75-116">![在 3、4 和 10 秒时达到的关键值](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="5ea75-116">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>

<span data-ttu-id="5ea75-117">下一个示例<xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>使用关键时间值。</span><span class="sxs-lookup"><span data-stu-id="5ea75-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

<span data-ttu-id="5ea75-118">下图显示了何时达到每个关键帧的值。</span><span class="sxs-lookup"><span data-stu-id="5ea75-118">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="5ea75-119">![在 3.3、6.6 和 9.9 秒时达到的关键值](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="5ea75-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>

<span data-ttu-id="5ea75-120">最后一个示例<xref:System.Windows.Media.Animation.KeyTime.Paced%2A>使用关键时间值。</span><span class="sxs-lookup"><span data-stu-id="5ea75-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

<span data-ttu-id="5ea75-121">下图显示了何时达到每个关键帧的值。</span><span class="sxs-lookup"><span data-stu-id="5ea75-121">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="5ea75-122">![在 0、5 和 10 秒时达到的关键值](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="5ea75-122">![Key values are reached at 0, 5, and 10 seconds](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>

<span data-ttu-id="5ea75-123">为简单起见，此示例的代码版本使用本地动画，而不是情节提要，因为只有单个动画应用于单个属性，但可以修改示例以改用情节提要。</span><span class="sxs-lookup"><span data-stu-id="5ea75-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="5ea75-124">有关如何在代码中声明情节提要的示例，请参阅[使用情节提要对属性进行动画处理](how-to-animate-a-property-by-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="5ea75-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span></span>

<span data-ttu-id="5ea75-125">有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。</span><span class="sxs-lookup"><span data-stu-id="5ea75-125">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span> <span data-ttu-id="5ea75-126">有关关键帧动画的详细信息，请参阅[关键帧动画概述](key-frame-animations-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5ea75-126">For more information about key frame animations, see the [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5ea75-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ea75-127">See also</span></span>

- [<span data-ttu-id="5ea75-128">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="5ea75-128">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="5ea75-129">动画概述</span><span class="sxs-lookup"><span data-stu-id="5ea75-129">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="5ea75-130">帮助主题</span><span class="sxs-lookup"><span data-stu-id="5ea75-130">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
