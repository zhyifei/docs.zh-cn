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
ms.openlocfilehash: cb09a54df3d99e05e89ec0f3d9f17b0e9fe78647
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43419072"
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="9f40c-102">如何：使用关键帧对颜色进行动画处理</span><span class="sxs-lookup"><span data-stu-id="9f40c-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="9f40c-103">此示例演示如何进行动画处理<xref:System.Windows.Media.SolidColorBrush.Color%2A>的<xref:System.Windows.Media.SolidColorBrush>使用关键帧。</span><span class="sxs-lookup"><span data-stu-id="9f40c-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f40c-104">示例</span><span class="sxs-lookup"><span data-stu-id="9f40c-104">Example</span></span>  
 <span data-ttu-id="9f40c-105">下面的示例使用<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.SolidColorBrush.Color%2A>属性的<xref:System.Windows.Media.SolidColorBrush>。</span><span class="sxs-lookup"><span data-stu-id="9f40c-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="9f40c-106">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="9f40c-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="9f40c-107">在前两秒中，使用的实例<xref:System.Windows.Media.Animation.LinearColorKeyFrame>类，以逐渐更改颜色从绿色到红色。</span><span class="sxs-lookup"><span data-stu-id="9f40c-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="9f40c-108">之类的线性关键帧<xref:System.Windows.Media.Animation.LinearColorKeyFrame>创建值之间平滑的线性转换。</span><span class="sxs-lookup"><span data-stu-id="9f40c-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="9f40c-109">在结束时的下一个前半秒中，使用的实例<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>类快速将颜色从红色更改为黄色。</span><span class="sxs-lookup"><span data-stu-id="9f40c-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="9f40c-110">之类的离散关键帧<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>之间创建突然变化的值，也就是说，此部分动画的颜色变化快速发生，而不是。</span><span class="sxs-lookup"><span data-stu-id="9f40c-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3.  <span data-ttu-id="9f40c-111">在最后两秒内，使用的实例<xref:System.Windows.Media.Animation.SplineColorKeyFrame>类，以再次更改颜色，这一次从黄色变回绿色。</span><span class="sxs-lookup"><span data-stu-id="9f40c-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="9f40c-112">之类的自由绘制曲线关键帧<xref:System.Windows.Media.Animation.SplineColorKeyFrame>创建根据的值在值之间的变量转换<xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="9f40c-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="9f40c-113">在此示例中，颜色变化开始时缓慢，然后以指数方式加速，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="9f40c-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="9f40c-114">有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="9f40c-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f40c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f40c-115">See Also</span></span>  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>  
 <xref:System.Windows.Media.SolidColorBrush>  
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>  
 [<span data-ttu-id="9f40c-116">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="9f40c-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="9f40c-117">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="9f40c-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
