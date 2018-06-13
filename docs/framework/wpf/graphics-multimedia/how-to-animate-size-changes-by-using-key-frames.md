---
title: 如何：使用关键帧对大小变化进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 0c2828215527a285943a79920de51fa42fe7a8a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559887"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="93cd1-102">如何：使用关键帧对大小变化进行动画处理</span><span class="sxs-lookup"><span data-stu-id="93cd1-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="93cd1-103">此示例演示如何使用关键帧对大小变化进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="93cd1-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93cd1-104">示例</span><span class="sxs-lookup"><span data-stu-id="93cd1-104">Example</span></span>  
 <span data-ttu-id="93cd1-105">下面的示例使用<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.ArcSegment.Size%2A>属性<xref:System.Windows.Media.ArcSegment>。</span><span class="sxs-lookup"><span data-stu-id="93cd1-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="93cd1-106">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="93cd1-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="93cd1-107">在第一个半秒的动画，使用的是实例<xref:System.Windows.Media.Animation.LinearSizeKeyFrame>类，以逐渐增加弧的大小。之类的线性的关键帧<xref:System.Windows.Media.Animation.LinearSizeKeyFrame>创建平滑的值之间的线性转换。</span><span class="sxs-lookup"><span data-stu-id="93cd1-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="93cd1-108">在下一步的末尾半秒，将使用的实例<xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>类突然增加弧的大小。之类的离散的关键帧<xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>突变值，即，大小更改突然发生，并且不是细微。</span><span class="sxs-lookup"><span data-stu-id="93cd1-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3.  <span data-ttu-id="93cd1-109">通过最后两秒内，使用的实例<xref:System.Windows.Media.Animation.SplineSizeKeyFrame>类以增加弧的大小。之类的样条关键帧<xref:System.Windows.Media.Animation.SplineSizeKeyFrame>创建变量的值根据值之间转换<xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="93cd1-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="93cd1-110">在本例中，弧的大小开始时缓慢增加，然后以指数方式增加，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="93cd1-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="93cd1-111">有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="93cd1-111">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93cd1-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="93cd1-112">See Also</span></span>  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.ArcSegment.Size%2A>  
 <xref:System.Windows.Media.ArcSegment>  
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>  
 [<span data-ttu-id="93cd1-113">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="93cd1-113">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="93cd1-114">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="93cd1-114">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
