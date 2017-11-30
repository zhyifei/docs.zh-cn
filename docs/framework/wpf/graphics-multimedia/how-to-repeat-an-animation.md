---
title: "如何：重复动画"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d2f942771e01c2b7fae989f73779672edb8ba2f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="9769c-102">如何：重复动画</span><span class="sxs-lookup"><span data-stu-id="9769c-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="9769c-103">此示例演示如何使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性<xref:System.Windows.Media.Animation.Timeline>以便控制动画的重复行为。</span><span class="sxs-lookup"><span data-stu-id="9769c-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9769c-104">示例</span><span class="sxs-lookup"><span data-stu-id="9769c-104">Example</span></span>  
 <span data-ttu-id="9769c-105"><xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性<xref:System.Windows.Media.Animation.Timeline>控制动画重复其简单持续时间的次数。</span><span class="sxs-lookup"><span data-stu-id="9769c-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="9769c-106">通过使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>，你可以指定<xref:System.Windows.Media.Animation.Timeline>一定次数的重复 （迭代计数） 或指定的时间段内。</span><span class="sxs-lookup"><span data-stu-id="9769c-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="9769c-107">在任一情况下，动画将经历填充的请求的计数或持续时间所需的尽可能多开头的端到端运行。</span><span class="sxs-lookup"><span data-stu-id="9769c-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="9769c-108">默认情况下，时间线具有重复次数为 1.0，这意味着它们播放一次，不进行重复。</span><span class="sxs-lookup"><span data-stu-id="9769c-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="9769c-109">但是，如果你设置<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性<xref:System.Windows.Media.Animation.Timeline>到<xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>，时间线无限期地重复。</span><span class="sxs-lookup"><span data-stu-id="9769c-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="9769c-110">下面的示例演示如何使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性来控制动画的重复行为。</span><span class="sxs-lookup"><span data-stu-id="9769c-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="9769c-111">该示例进行动画处理<xref:System.Windows.FrameworkElement.Width%2A>的每个矩形使用不同类型的重复行为的五个矩形的属性。</span><span class="sxs-lookup"><span data-stu-id="9769c-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="9769c-112">有关完整的示例，请参阅[动画计时行为示例](http://go.microsoft.com/fwlink/?LinkID=159970)。</span><span class="sxs-lookup"><span data-stu-id="9769c-112">For the complete sample, see [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9769c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9769c-113">See Also</span></span>  
 [<span data-ttu-id="9769c-114">在重复循环过程中累积动画值</span><span class="sxs-lookup"><span data-stu-id="9769c-114">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [<span data-ttu-id="9769c-115">指定时间线是否自动反转</span><span class="sxs-lookup"><span data-stu-id="9769c-115">Specify Whether a Timeline Automatically Reverses</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)  
 [<span data-ttu-id="9769c-116">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="9769c-116">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [<span data-ttu-id="9769c-117">动画和计时</span><span class="sxs-lookup"><span data-stu-id="9769c-117">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="9769c-118">动画概述</span><span class="sxs-lookup"><span data-stu-id="9769c-118">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="9769c-119">动画计时行为示例</span><span class="sxs-lookup"><span data-stu-id="9769c-119">Animation Timing Behavior Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159970)
