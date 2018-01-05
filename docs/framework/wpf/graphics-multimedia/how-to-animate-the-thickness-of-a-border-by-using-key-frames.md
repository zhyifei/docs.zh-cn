---
title: "如何：使用关键帧对边框的粗细进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f255ff38ec7ee79f02a0cd40a3f0143c36e1c58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="78a5b-102">如何：使用关键帧对边框的粗细进行动画处理</span><span class="sxs-lookup"><span data-stu-id="78a5b-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="78a5b-103">此示例演示如何进行动画处理<xref:System.Windows.Controls.Control.BorderThickness%2A>属性<xref:System.Windows.Controls.Border>。</span><span class="sxs-lookup"><span data-stu-id="78a5b-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78a5b-104">示例</span><span class="sxs-lookup"><span data-stu-id="78a5b-104">Example</span></span>  
 <span data-ttu-id="78a5b-105">下面的示例使用<xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Controls.Control.BorderThickness%2A>属性<xref:System.Windows.Controls.Border>。</span><span class="sxs-lookup"><span data-stu-id="78a5b-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="78a5b-106">此动画按以下方式使用三个关键帧：</span><span class="sxs-lookup"><span data-stu-id="78a5b-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="78a5b-107">第一个半秒内使用的是实例<xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>类，以逐渐增加边框的粗细。</span><span class="sxs-lookup"><span data-stu-id="78a5b-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="78a5b-108">该示例使用<xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>创建值之间平滑线性增加。</span><span class="sxs-lookup"><span data-stu-id="78a5b-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2.  <span data-ttu-id="78a5b-109">在下一步的末尾半秒，将使用的实例<xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>类突然增加边框的粗细。</span><span class="sxs-lookup"><span data-stu-id="78a5b-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="78a5b-110">如离散关键帧派生自<xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>突变值，即，动画的移动是不平稳。</span><span class="sxs-lookup"><span data-stu-id="78a5b-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3.  <span data-ttu-id="78a5b-111">在最终的两秒内，使用的是实例<xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>类以减少边框的粗细。</span><span class="sxs-lookup"><span data-stu-id="78a5b-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="78a5b-112">如样条关键帧派生自<xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>创建变量的值根据值之间转换<xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="78a5b-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="78a5b-113">在此关键帧中，动画开始时缓慢，然后以指数方式加速，直到时间段结束。</span><span class="sxs-lookup"><span data-stu-id="78a5b-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="78a5b-114">有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。</span><span class="sxs-lookup"><span data-stu-id="78a5b-114">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a5b-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="78a5b-115">See Also</span></span>  
 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>  
 [<span data-ttu-id="78a5b-116">关键帧动画概述</span><span class="sxs-lookup"><span data-stu-id="78a5b-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="78a5b-117">关键帧操作说明主题</span><span class="sxs-lookup"><span data-stu-id="78a5b-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)  
 [<span data-ttu-id="78a5b-118">对 BorderThickness 值进行动画处理</span><span class="sxs-lookup"><span data-stu-id="78a5b-118">Animate a BorderThickness Value</span></span>](../../../../docs/framework/wpf/controls/how-to-animate-a-borderthickness-value.md)
