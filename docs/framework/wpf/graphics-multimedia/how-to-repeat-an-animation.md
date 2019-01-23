---
title: 如何：重复动画
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 213fca0796840ae87035be4f474cfdf4648460a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609637"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="9562e-102">如何：重复动画</span><span class="sxs-lookup"><span data-stu-id="9562e-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="9562e-103">此示例演示如何使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性的<xref:System.Windows.Media.Animation.Timeline>为了控制动画的重复行为。</span><span class="sxs-lookup"><span data-stu-id="9562e-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9562e-104">示例</span><span class="sxs-lookup"><span data-stu-id="9562e-104">Example</span></span>  
 <span data-ttu-id="9562e-105"><xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性的<xref:System.Windows.Media.Animation.Timeline>控制动画重复其简单持续时间的次数。</span><span class="sxs-lookup"><span data-stu-id="9562e-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="9562e-106">通过使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>，可以指定<xref:System.Windows.Media.Animation.Timeline>重复特定次数 （迭代计数） 或指定的时间段内。</span><span class="sxs-lookup"><span data-stu-id="9562e-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="9562e-107">在任一情况下，动画将经历填充请求的计数或持续时间所需的任意多个开始到结束运行。</span><span class="sxs-lookup"><span data-stu-id="9562e-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="9562e-108">默认情况下，时间线具有值为 1.0，这意味着它们播放一次，不进行重复的重复计数。</span><span class="sxs-lookup"><span data-stu-id="9562e-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="9562e-109">但是，如果您设置<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>的属性<xref:System.Windows.Media.Animation.Timeline>到<xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>，无限期地重复时间线。</span><span class="sxs-lookup"><span data-stu-id="9562e-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="9562e-110">下面的示例演示如何使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性来控制动画的重复行为。</span><span class="sxs-lookup"><span data-stu-id="9562e-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="9562e-111">该示例进行动画处理<xref:System.Windows.FrameworkElement.Width%2A>的每个矩形使用不同类型的重复行为的五个矩形的属性。</span><span class="sxs-lookup"><span data-stu-id="9562e-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="9562e-112">有关完整示例，请参阅[动画计时行为示例](https://go.microsoft.com/fwlink/?LinkID=159970)。</span><span class="sxs-lookup"><span data-stu-id="9562e-112">For the complete sample, see [Animation Timing Behavior Sample](https://go.microsoft.com/fwlink/?LinkID=159970).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9562e-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="9562e-113">See also</span></span>
- [<span data-ttu-id="9562e-114">在重复循环过程中累积动画值</span><span class="sxs-lookup"><span data-stu-id="9562e-114">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="9562e-115">指定时间线是否自动反转</span><span class="sxs-lookup"><span data-stu-id="9562e-115">Specify Whether a Timeline Automatically Reverses</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="9562e-116">帮助主题</span><span class="sxs-lookup"><span data-stu-id="9562e-116">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="9562e-117">动画和计时</span><span class="sxs-lookup"><span data-stu-id="9562e-117">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)
- [<span data-ttu-id="9562e-118">动画概述</span><span class="sxs-lookup"><span data-stu-id="9562e-118">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="9562e-119">动画计时行为示例</span><span class="sxs-lookup"><span data-stu-id="9562e-119">Animation Timing Behavior Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159970)
