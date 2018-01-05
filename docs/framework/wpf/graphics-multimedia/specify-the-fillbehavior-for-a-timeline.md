---
title: "如何：为已经到达有效期末尾的时间线指定 FillBehavior"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2c1d65ec9fad94fed02bee1f018ae1aa00a8591
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="efe6a-102">如何：为已经到达有效期末尾的时间线指定 FillBehavior</span><span class="sxs-lookup"><span data-stu-id="efe6a-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="efe6a-103">此示例演示如何指定<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>的非活动<xref:System.Windows.Media.Animation.Timeline>的动画的属性。</span><span class="sxs-lookup"><span data-stu-id="efe6a-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efe6a-104">示例</span><span class="sxs-lookup"><span data-stu-id="efe6a-104">Example</span></span>  
 <span data-ttu-id="efe6a-105"><xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性<xref:System.Windows.Media.Animation.Timeline>确定时它将不会动画属性的值会发生什么情况进行动画处理，即，当<xref:System.Windows.Media.Animation.Timeline>处于非活动状态，但其父级<xref:System.Windows.Media.Animation.Timeline>仍处于其有效期或保持期内。</span><span class="sxs-lookup"><span data-stu-id="efe6a-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="efe6a-106">例如，未经过动画处理的属性保留为其结束后动画结束或不它的值还原为动画启动之前的值？</span><span class="sxs-lookup"><span data-stu-id="efe6a-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="efe6a-107">下面的示例使用<xref:System.Windows.Media.Animation.DoubleAnimation>要进行动画处理<xref:System.Windows.FrameworkElement.Width%2A>两个矩形。</span><span class="sxs-lookup"><span data-stu-id="efe6a-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="efe6a-108">每个矩形都使用不同<xref:System.Windows.Media.Animation.Timeline>对象。</span><span class="sxs-lookup"><span data-stu-id="efe6a-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="efe6a-109">一个<xref:System.Windows.Media.Animation.Timeline>具有<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>设置为<xref:System.Windows.Media.Animation.FillBehavior.Stop>，这将导致产生要还原为其非动画的矩形的宽度值时<xref:System.Windows.Media.Animation.Timeline>结束。</span><span class="sxs-lookup"><span data-stu-id="efe6a-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="efe6a-110">其他<xref:System.Windows.Media.Animation.Timeline>具有<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>的<xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>，这将导致产生宽度将保留在其一端值时<xref:System.Windows.Media.Animation.Timeline>结束。</span><span class="sxs-lookup"><span data-stu-id="efe6a-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="efe6a-111">有关完整的示例，请参阅[动画示例库](http://go.microsoft.com/fwlink/?LinkID=159969)。</span><span class="sxs-lookup"><span data-stu-id="efe6a-111">For the complete sample, see [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efe6a-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="efe6a-112">See Also</span></span>  
 <xref:System.Windows.Media.Animation.DoubleAnimation>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>  
 [<span data-ttu-id="efe6a-113">动画概述</span><span class="sxs-lookup"><span data-stu-id="efe6a-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="efe6a-114">动画和计时</span><span class="sxs-lookup"><span data-stu-id="efe6a-114">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="efe6a-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="efe6a-115">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
