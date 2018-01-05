---
title: "如何：使用关键帧对颜色进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c6b4dc6ee04b20f47599bad84dda4648da255ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="85ae1-102">如何：使用关键帧对颜色进行动画处理</span><span class="sxs-lookup"><span data-stu-id="85ae1-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="85ae1-103">此示例演示如何进行动画处理<xref:System.Windows.Media.SolidColorBrush.Color%2A>的<xref:System.Windows.Media.SolidColorBrush>使用关键帧。</span><span class="sxs-lookup"><span data-stu-id="85ae1-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85ae1-104">示例</span><span class="sxs-lookup"><span data-stu-id="85ae1-104">Example</span></span>  
 <span data-ttu-id="85ae1-105">下面的示例使用<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.SolidColorBrush.Color%2A>属性<xref:System.Windows.Media.SolidColorBrush>。</span><span class="sxs-lookup"><span data-stu-id="85ae1-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="85ae1-106">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="85ae1-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="85ae1-107">在第一个的两秒内，使用的是实例<xref:System.Windows.Media.Animation.LinearColorKeyFrame>类来从绿色到红色逐渐改变颜色。</span><span class="sxs-lookup"><span data-stu-id="85ae1-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="85ae1-108">之类的线性的关键帧<xref:System.Windows.Media.Animation.LinearColorKeyFrame>创建平滑的值之间的线性转换。</span><span class="sxs-lookup"><span data-stu-id="85ae1-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="85ae1-109">在下一步的末尾半秒，将使用的实例<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>类，以快速地将从红色的颜色更改为黄色。</span><span class="sxs-lookup"><span data-stu-id="85ae1-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="85ae1-110">之类的离散的关键帧<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>突变值，即，在动画的此部分的颜色更改快速发生的不是细微。</span><span class="sxs-lookup"><span data-stu-id="85ae1-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3.  <span data-ttu-id="85ae1-111">在最终的两秒内，使用的是实例<xref:System.Windows.Media.Animation.SplineColorKeyFrame>类重新更改颜色 — 这一次从黄色变回为绿色。</span><span class="sxs-lookup"><span data-stu-id="85ae1-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="85ae1-112">之类的样条关键帧<xref:System.Windows.Media.Animation.SplineColorKeyFrame>创建变量的值根据值之间转换<xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="85ae1-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="85ae1-113">在此示例中，颜色变化开始时缓慢，然后以指数方式加速，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="85ae1-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="85ae1-114">有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="85ae1-114">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85ae1-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="85ae1-115">See Also</span></span>  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>  
 <xref:System.Windows.Media.SolidColorBrush>  
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>  
 [<span data-ttu-id="85ae1-116">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="85ae1-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="85ae1-117">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="85ae1-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
