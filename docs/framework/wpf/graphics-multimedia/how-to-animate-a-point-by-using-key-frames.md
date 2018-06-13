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
ms.openlocfilehash: a59ceb62d7feb33d2cc8a747a7bfb85e551d785c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557350"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a><span data-ttu-id="b246d-102">如何：使用关键帧对点进行动画处理</span><span class="sxs-lookup"><span data-stu-id="b246d-102">How to: Animate a Point by Using Key Frames</span></span>
<span data-ttu-id="b246d-103">此示例演示如何使用<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Point>。</span><span class="sxs-lookup"><span data-stu-id="b246d-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate a <xref:System.Windows.Point>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b246d-104">示例</span><span class="sxs-lookup"><span data-stu-id="b246d-104">Example</span></span>  
 <span data-ttu-id="b246d-105">以下示例沿三角形路径移动椭圆形。</span><span class="sxs-lookup"><span data-stu-id="b246d-105">The following example moves an ellipse along a triangular path.</span></span> <span data-ttu-id="b246d-106">该示例使用<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性<xref:System.Windows.Media.EllipseGeometry>。</span><span class="sxs-lookup"><span data-stu-id="b246d-106">The example uses the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property of an <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="b246d-107">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="b246d-107">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="b246d-108">第一个半秒内使用的是实例<xref:System.Windows.Media.Animation.LinearPointKeyFrame>类以恒定速率将沿路径椭圆，从它的起始位置。</span><span class="sxs-lookup"><span data-stu-id="b246d-108">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearPointKeyFrame> class to move the ellipse along a path at a steady rate from its starting position.</span></span> <span data-ttu-id="b246d-109">之类的线性的关键帧<xref:System.Windows.Media.Animation.LinearPointKeyFrame>创建平滑的线性内插值之间。</span><span class="sxs-lookup"><span data-stu-id="b246d-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearPointKeyFrame> create a smooth linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="b246d-110">在下一步的末尾半秒，将使用的实例<xref:System.Windows.Media.Animation.DiscretePointKeyFrame>类突然将椭圆沿路径移动到下一个位置。</span><span class="sxs-lookup"><span data-stu-id="b246d-110">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> class to suddenly move the ellipse along the path to the next position.</span></span> <span data-ttu-id="b246d-111">之类的离散的关键帧<xref:System.Windows.Media.Animation.DiscretePointKeyFrame>突变值。</span><span class="sxs-lookup"><span data-stu-id="b246d-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> create sudden jumps between values.</span></span>  
  
3.  <span data-ttu-id="b246d-112">在最终的两秒内，使用的是实例<xref:System.Windows.Media.Animation.SplinePointKeyFrame>类将椭圆移回其起始位置。</span><span class="sxs-lookup"><span data-stu-id="b246d-112">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame> class to move the ellipse back to its starting position.</span></span> <span data-ttu-id="b246d-113">之类的样条关键帧<xref:System.Windows.Media.Animation.SplinePointKeyFrame>创建变量的值根据值之间转换<xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="b246d-113">Spline key frames like <xref:System.Windows.Media.Animation.SplinePointKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="b246d-114">在此示例中，动画开始时较为缓慢，然后以指数方式加速，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="b246d-114">In this example, the animation begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="b246d-115">有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="b246d-115">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="b246d-116">与其他动画示例保持一致，对于此示例的代码版本使用<xref:System.Windows.Media.Animation.Storyboard>要应用对象<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>。</span><span class="sxs-lookup"><span data-stu-id="b246d-116">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="b246d-117">但是，当应用单个动画在代码中的，这是使用简单得多<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法而不是使用<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="b246d-117">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="b246d-118">有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)。</span><span class="sxs-lookup"><span data-stu-id="b246d-118">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b246d-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b246d-119">See Also</span></span>  
 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.EllipseGeometry>  
 [<span data-ttu-id="b246d-120">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="b246d-120">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="b246d-121">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="b246d-121">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
