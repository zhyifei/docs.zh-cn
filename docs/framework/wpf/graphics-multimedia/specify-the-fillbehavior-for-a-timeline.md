---
title: 如何：为已经到达有效期末尾的时间线指定 FillBehavior
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 6745cf5d57a341068e93784d5487f21e34f8a64a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530086"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="e23a0-102">如何：为已经到达有效期末尾的时间线指定 FillBehavior</span><span class="sxs-lookup"><span data-stu-id="e23a0-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="e23a0-103">此示例演示如何指定<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>的非活动<xref:System.Windows.Media.Animation.Timeline>的动画属性。</span><span class="sxs-lookup"><span data-stu-id="e23a0-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e23a0-104">示例</span><span class="sxs-lookup"><span data-stu-id="e23a0-104">Example</span></span>  
 <span data-ttu-id="e23a0-105"><xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>的属性<xref:System.Windows.Media.Animation.Timeline>确定未被时，动画属性的值会发生什么情况进行动画处理，即，当<xref:System.Windows.Media.Animation.Timeline>处于非活动状态，但其父级<xref:System.Windows.Media.Animation.Timeline>仍处于其有效期或保持期内。</span><span class="sxs-lookup"><span data-stu-id="e23a0-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="e23a0-106">例如，动画的属性仍然可在其一端后动画结束或它的值还原为动画启动之前的值？</span><span class="sxs-lookup"><span data-stu-id="e23a0-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="e23a0-107">下面的示例使用<xref:System.Windows.Media.Animation.DoubleAnimation>进行动画处理<xref:System.Windows.FrameworkElement.Width%2A>的两个矩形。</span><span class="sxs-lookup"><span data-stu-id="e23a0-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="e23a0-108">每个矩形都使用不同<xref:System.Windows.Media.Animation.Timeline>对象。</span><span class="sxs-lookup"><span data-stu-id="e23a0-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="e23a0-109">一个<xref:System.Windows.Media.Animation.Timeline>已<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>设置为<xref:System.Windows.Media.Animation.FillBehavior.Stop>，这将导致要还原为其非动画的矩形的宽度时值<xref:System.Windows.Media.Animation.Timeline>结束。</span><span class="sxs-lookup"><span data-stu-id="e23a0-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="e23a0-110">另<xref:System.Windows.Media.Animation.Timeline>已<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>的<xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>，这将导致保留为其结束的宽度时值<xref:System.Windows.Media.Animation.Timeline>结束。</span><span class="sxs-lookup"><span data-stu-id="e23a0-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="e23a0-111">有关完整示例，请参阅[动画示例库](https://go.microsoft.com/fwlink/?LinkID=159969)。</span><span class="sxs-lookup"><span data-stu-id="e23a0-111">For the complete sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e23a0-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="e23a0-112">See also</span></span>
- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="e23a0-113">动画概述</span><span class="sxs-lookup"><span data-stu-id="e23a0-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="e23a0-114">动画和计时</span><span class="sxs-lookup"><span data-stu-id="e23a0-114">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)
- [<span data-ttu-id="e23a0-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="e23a0-115">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
