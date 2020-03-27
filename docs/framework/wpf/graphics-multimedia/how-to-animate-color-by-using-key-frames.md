---
title: 如何：使用关键帧对颜色进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344752"
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="1fcde-102">如何：使用关键帧对颜色进行动画处理</span><span class="sxs-lookup"><span data-stu-id="1fcde-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="1fcde-103">此示例演示如何使用关键帧对<xref:System.Windows.Media.SolidColorBrush.Color%2A>的<xref:System.Windows.Media.SolidColorBrush>动画设置。</span><span class="sxs-lookup"><span data-stu-id="1fcde-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fcde-104">示例</span><span class="sxs-lookup"><span data-stu-id="1fcde-104">Example</span></span>  
 <span data-ttu-id="1fcde-105">下面的示例使用 类<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>为 属性<xref:System.Windows.Media.SolidColorBrush>设置<xref:System.Windows.Media.SolidColorBrush.Color%2A>动画。</span><span class="sxs-lookup"><span data-stu-id="1fcde-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="1fcde-106">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="1fcde-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="1fcde-107">在前两秒钟中<xref:System.Windows.Media.Animation.LinearColorKeyFrame>，使用类的实例逐渐将颜色从绿色更改为红色。</span><span class="sxs-lookup"><span data-stu-id="1fcde-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="1fcde-108">线性关键帧（<xref:System.Windows.Media.Animation.LinearColorKeyFrame>如在值之间创建平滑线性过渡）</span><span class="sxs-lookup"><span data-stu-id="1fcde-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="1fcde-109">在下半秒结束时，使用<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>类的实例快速将颜色从红色更改为黄色。</span><span class="sxs-lookup"><span data-stu-id="1fcde-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="1fcde-110">离散的关键帧（<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>如在值之间创建突然变化）表示，动画的这一部分中的颜色变化会迅速发生，并且不微妙。</span><span class="sxs-lookup"><span data-stu-id="1fcde-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="1fcde-111">在最后两秒钟内<xref:System.Windows.Media.Animation.SplineColorKeyFrame>，使用类的实例再次更改颜色 - 这一次从黄色返回为绿色。</span><span class="sxs-lookup"><span data-stu-id="1fcde-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="1fcde-112">样条线键帧，<xref:System.Windows.Media.Animation.SplineColorKeyFrame>如根据<xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A>属性的值在值之间创建可变转换。</span><span class="sxs-lookup"><span data-stu-id="1fcde-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="1fcde-113">在此示例中，颜色变化开始时缓慢，然后以指数方式加速，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="1fcde-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="1fcde-114">有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。</span><span class="sxs-lookup"><span data-stu-id="1fcde-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fcde-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1fcde-115">See also</span></span>

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [<span data-ttu-id="1fcde-116">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="1fcde-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="1fcde-117">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="1fcde-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
