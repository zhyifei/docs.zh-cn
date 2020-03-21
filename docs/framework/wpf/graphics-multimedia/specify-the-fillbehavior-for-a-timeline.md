---
title: 如何：为已经到达有效期末尾的时间线指定 FillBehavior
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141168"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="b1569-102">如何：为已经到达有效期末尾的时间线指定 FillBehavior</span><span class="sxs-lookup"><span data-stu-id="b1569-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="b1569-103">此示例演示如何<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>为动画属性的非活动<xref:System.Windows.Media.Animation.Timeline>指定 。</span><span class="sxs-lookup"><span data-stu-id="b1569-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1569-104">示例</span><span class="sxs-lookup"><span data-stu-id="b1569-104">Example</span></span>  
 <span data-ttu-id="b1569-105">属性<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A><xref:System.Windows.Media.Animation.Timeline>确定动画属性未进行动画处理时（即 非活动但其父<xref:System.Windows.Media.Animation.Timeline><xref:System.Windows.Media.Animation.Timeline>属性在其活动或保留期间内）的值会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="b1569-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="b1569-106">例如，动画属性在动画结束后是否保持其结束值，还是恢复到动画启动前的值？</span><span class="sxs-lookup"><span data-stu-id="b1569-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="b1569-107">下面的示例使用 为<xref:System.Windows.Media.Animation.DoubleAnimation>两<xref:System.Windows.FrameworkElement.Width%2A>个矩形设置动画。</span><span class="sxs-lookup"><span data-stu-id="b1569-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="b1569-108">每个矩形使用不同的<xref:System.Windows.Media.Animation.Timeline>对象。</span><span class="sxs-lookup"><span data-stu-id="b1569-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="b1569-109">一<xref:System.Windows.Media.Animation.Timeline>个设置为<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>的 有<xref:System.Windows.Media.Animation.FillBehavior.Stop>一个 ，这将导致矩形的宽度在<xref:System.Windows.Media.Animation.Timeline>结束时恢复到其非动画值。</span><span class="sxs-lookup"><span data-stu-id="b1569-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="b1569-110">另<xref:System.Windows.Media.Animation.Timeline>一个具有<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>， 这将导致宽度在<xref:System.Windows.Media.Animation.Timeline>结束时保持其结束值。</span><span class="sxs-lookup"><span data-stu-id="b1569-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="b1569-111">有关完整示例，请参阅[动画示例库](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)。</span><span class="sxs-lookup"><span data-stu-id="b1569-111">For the complete sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1569-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1569-112">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="b1569-113">动画概述</span><span class="sxs-lookup"><span data-stu-id="b1569-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="b1569-114">动画和计时帮助主题</span><span class="sxs-lookup"><span data-stu-id="b1569-114">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
