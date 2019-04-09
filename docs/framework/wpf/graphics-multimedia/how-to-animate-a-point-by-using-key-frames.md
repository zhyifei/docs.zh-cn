---
title: 如何：使用关键帧对点进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: 2e34ba035c8d7f9132915a9269d545f32033cbed
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132582"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a><span data-ttu-id="e6913-102">如何：使用关键帧对点进行动画处理</span><span class="sxs-lookup"><span data-stu-id="e6913-102">How to: Animate a Point by Using Key Frames</span></span>
<span data-ttu-id="e6913-103">此示例演示如何使用<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Point>。</span><span class="sxs-lookup"><span data-stu-id="e6913-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate a <xref:System.Windows.Point>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6913-104">示例</span><span class="sxs-lookup"><span data-stu-id="e6913-104">Example</span></span>  
 <span data-ttu-id="e6913-105">以下示例沿三角形路径移动椭圆形。</span><span class="sxs-lookup"><span data-stu-id="e6913-105">The following example moves an ellipse along a triangular path.</span></span> <span data-ttu-id="e6913-106">该示例使用<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性的<xref:System.Windows.Media.EllipseGeometry>。</span><span class="sxs-lookup"><span data-stu-id="e6913-106">The example uses the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property of an <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="e6913-107">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="e6913-107">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="e6913-108">在前半秒中，使用的实例<xref:System.Windows.Media.Animation.LinearPointKeyFrame>类将椭圆形沿路径以稳定速率从其起始位置。</span><span class="sxs-lookup"><span data-stu-id="e6913-108">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearPointKeyFrame> class to move the ellipse along a path at a steady rate from its starting position.</span></span> <span data-ttu-id="e6913-109">之类的线性关键帧<xref:System.Windows.Media.Animation.LinearPointKeyFrame>创建值之间平滑的线性插值。</span><span class="sxs-lookup"><span data-stu-id="e6913-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearPointKeyFrame> create a smooth linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="e6913-110">在结束时的下一个前半秒中，使用的实例<xref:System.Windows.Media.Animation.DiscretePointKeyFrame>类将椭圆形沿路径突然移动到下一个位置。</span><span class="sxs-lookup"><span data-stu-id="e6913-110">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> class to suddenly move the ellipse along the path to the next position.</span></span> <span data-ttu-id="e6913-111">之类的离散关键帧<xref:System.Windows.Media.Animation.DiscretePointKeyFrame>值之间创建突然跳跃。</span><span class="sxs-lookup"><span data-stu-id="e6913-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> create sudden jumps between values.</span></span>  
  
3.  <span data-ttu-id="e6913-112">在最后两秒内，使用的实例<xref:System.Windows.Media.Animation.SplinePointKeyFrame>类将椭圆形移回其起始位置。</span><span class="sxs-lookup"><span data-stu-id="e6913-112">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame> class to move the ellipse back to its starting position.</span></span> <span data-ttu-id="e6913-113">之类的自由绘制曲线关键帧<xref:System.Windows.Media.Animation.SplinePointKeyFrame>创建根据的值在值之间的变量转换<xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e6913-113">Spline key frames like <xref:System.Windows.Media.Animation.SplinePointKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="e6913-114">在此示例中，动画开始时较为缓慢，然后以指数方式加速，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="e6913-114">In this example, the animation begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="e6913-115">有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="e6913-115">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="e6913-116">与其他动画示例保持一致，对于此示例中的代码版本使用<xref:System.Windows.Media.Animation.Storyboard>对象来应用<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>。</span><span class="sxs-lookup"><span data-stu-id="e6913-116">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="e6913-117">但是，当应用单个动画在代码中的，它是使用更加简便<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法而不是使用<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="e6913-117">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="e6913-118">有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="e6913-118">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6913-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6913-119">See also</span></span>

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [<span data-ttu-id="e6913-120">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="e6913-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="e6913-121">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="e6913-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
