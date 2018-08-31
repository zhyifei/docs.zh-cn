---
title: 如何：使用关键帧对大小变化进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 69845d1d75f81042bbeb20ee6b1015f5c2f53b81
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2018
ms.locfileid: "43332089"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="2ad03-102">如何：使用关键帧对大小变化进行动画处理</span><span class="sxs-lookup"><span data-stu-id="2ad03-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="2ad03-103">此示例演示如何使用关键帧对大小变化进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="2ad03-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ad03-104">示例</span><span class="sxs-lookup"><span data-stu-id="2ad03-104">Example</span></span>  
 <span data-ttu-id="2ad03-105">下面的示例使用<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.ArcSegment.Size%2A>属性的<xref:System.Windows.Media.ArcSegment>。</span><span class="sxs-lookup"><span data-stu-id="2ad03-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="2ad03-106">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="2ad03-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="2ad03-107">在动画的前半秒，使用的实例<xref:System.Windows.Media.Animation.LinearSizeKeyFrame>类，以逐渐增加弧的大小。之类的线性关键帧<xref:System.Windows.Media.Animation.LinearSizeKeyFrame>创建值之间平滑的线性转换。</span><span class="sxs-lookup"><span data-stu-id="2ad03-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="2ad03-108">在下一步末尾前半秒中，使用的实例<xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>类突然增加弧的大小。之类的离散关键帧<xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>之间创建突然跳跃的值，即，大小变化突然发生，而不是。</span><span class="sxs-lookup"><span data-stu-id="2ad03-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3.  <span data-ttu-id="2ad03-109">通过最后两秒内，使用的实例<xref:System.Windows.Media.Animation.SplineSizeKeyFrame>类，以增加弧的大小。之类的自由绘制曲线关键帧<xref:System.Windows.Media.Animation.SplineSizeKeyFrame>创建根据的值在值之间的变量转换<xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="2ad03-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="2ad03-110">在本例中，弧的大小开始时缓慢增加，然后以指数方式增加，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="2ad03-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="2ad03-111">有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="2ad03-111">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad03-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ad03-112">See Also</span></span>  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.ArcSegment.Size%2A>  
 <xref:System.Windows.Media.ArcSegment>  
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>  
 [<span data-ttu-id="2ad03-113">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="2ad03-113">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="2ad03-114">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="2ad03-114">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
