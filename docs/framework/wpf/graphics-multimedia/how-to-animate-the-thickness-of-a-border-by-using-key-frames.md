---
title: 如何：使用关键帧对边框的粗细进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 101fd077bf125faadbd9a0186c2282e4b20ee78f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301784"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="4f61d-102">如何：使用关键帧对边框的粗细进行动画处理</span><span class="sxs-lookup"><span data-stu-id="4f61d-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="4f61d-103">此示例演示如何进行动画处理<xref:System.Windows.Controls.Control.BorderThickness%2A>属性的<xref:System.Windows.Controls.Border>。</span><span class="sxs-lookup"><span data-stu-id="4f61d-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f61d-104">示例</span><span class="sxs-lookup"><span data-stu-id="4f61d-104">Example</span></span>  
 <span data-ttu-id="4f61d-105">下面的示例使用<xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Controls.Control.BorderThickness%2A>属性的<xref:System.Windows.Controls.Border>。</span><span class="sxs-lookup"><span data-stu-id="4f61d-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="4f61d-106">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="4f61d-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="4f61d-107">在前半秒中，使用的实例<xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>类，以逐渐增加边框的粗细。</span><span class="sxs-lookup"><span data-stu-id="4f61d-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="4f61d-108">该示例使用<xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>创建值之间平滑的线性递增。</span><span class="sxs-lookup"><span data-stu-id="4f61d-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2. <span data-ttu-id="4f61d-109">在下一步末尾前半秒中，使用的实例<xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>类突然增加边框的粗细。</span><span class="sxs-lookup"><span data-stu-id="4f61d-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="4f61d-110">离散关键帧，如派生自<xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>之间创建突然跳跃的值，也就是说，动画的运动是不平稳。</span><span class="sxs-lookup"><span data-stu-id="4f61d-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3. <span data-ttu-id="4f61d-111">在最后两秒内，使用的实例<xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>类，以减小边框的粗细。</span><span class="sxs-lookup"><span data-stu-id="4f61d-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="4f61d-112">自由绘制曲线关键帧，如派生自<xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>创建根据的值在值之间的变量转换<xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="4f61d-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="4f61d-113">在此关键帧中，动画开始时缓慢，然后以指数方式加速，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="4f61d-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="4f61d-114">有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="4f61d-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f61d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f61d-115">See also</span></span>

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [<span data-ttu-id="4f61d-116">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="4f61d-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="4f61d-117">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="4f61d-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
- [<span data-ttu-id="4f61d-118">对 BorderThickness 值进行动画处理</span><span class="sxs-lookup"><span data-stu-id="4f61d-118">Animate a BorderThickness Value</span></span>](../controls/how-to-animate-a-borderthickness-value.md)
