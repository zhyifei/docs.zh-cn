---
title: 如何：使用关键帧对双精度属性值进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
ms.openlocfilehash: 67466bbb5fd7e7a46c312e14666c23048bf43d80
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44339326"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a><span data-ttu-id="6d9d6-102">如何：使用关键帧对双精度属性值进行动画处理</span><span class="sxs-lookup"><span data-stu-id="6d9d6-102">How to: Animate a Double by Using Key Frames</span></span>
<span data-ttu-id="6d9d6-103">此示例演示如何采用的属性的值进行动画处理<xref:System.Double>使用关键帧。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-103">This example shows how to animate the value of a property that takes a <xref:System.Double> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d9d6-104">示例</span><span class="sxs-lookup"><span data-stu-id="6d9d6-104">Example</span></span>  
 <span data-ttu-id="6d9d6-105">以下示例将在屏幕上移动矩形。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-105">The following example moves a rectangle across a screen.</span></span> <span data-ttu-id="6d9d6-106">该示例使用<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.TranslateTransform.X%2A>的属性<xref:System.Windows.Media.TranslateTransform>应用于<xref:System.Windows.Shapes.Rectangle>。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-106">The example uses the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.TranslateTransform.X%2A> property of a <xref:System.Windows.Media.TranslateTransform> applied to a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="6d9d6-107">此无限重复的动画通过以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="6d9d6-107">This animation, which repeats indefinitely, uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="6d9d6-108">在前三秒中，使用的实例<xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>类将矩形沿路径以稳定速率从其起始位置到 500 位置。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-108">During the first three seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> class to move the rectangle along a path at a steady rate from its starting position to the 500 position.</span></span> <span data-ttu-id="6d9d6-109">之类的线性关键帧<xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>创建值之间平滑的线性转换。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="6d9d6-110">在第四秒结束时，使用的实例<xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>类将矩形突然移动到下一个位置。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-110">At the end of the fourth second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> class to suddenly move the rectangle to the next position.</span></span> <span data-ttu-id="6d9d6-111">之类的离散关键帧<xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>值之间创建突然跳跃。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> create sudden jumps between values.</span></span> <span data-ttu-id="6d9d6-112">在该示例中，矩形位于起始位置，然后突然出现在 500 位置。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-112">In this example, the rectangle is at the starting position and then suddenly appears at the 500 position.</span></span>  
  
3.  <span data-ttu-id="6d9d6-113">在最后两秒内，使用的实例<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>类，以将该矩形移回其起始位置。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-113">In the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> class to move the rectangle back to its starting position.</span></span> <span data-ttu-id="6d9d6-114">之类的自由绘制曲线关键帧<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>创建的变量的值会根据之间转换<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-114">Spline key frames like <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> create a variable transition between values according to the value of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="6d9d6-115">在本示例中，矩形开始时缓慢移动，然后以指数级加速，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-115">In this example, the rectangle begins by moving slowly and then speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="6d9d6-116">有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="6d9d6-117">与其他动画示例保持一致，对于此示例中的代码版本使用<xref:System.Windows.Media.Animation.Storyboard>对象来应用<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-117">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="6d9d6-118">或者，应用单个动画在代码中的，它时，使用更加简便<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法而不是使用<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-118">Alternatively, when applying a single animation in code, it is simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="6d9d6-119">有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="6d9d6-119">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d9d6-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d9d6-120">See Also</span></span>  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Shapes.Rectangle>  
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>  
 [<span data-ttu-id="6d9d6-121">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="6d9d6-121">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="6d9d6-122">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="6d9d6-122">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
