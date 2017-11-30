---
title: "如何：使用子时间线简化动画"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: daa4caac0046293e8b86a773bfffd46cf30e835b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a><span data-ttu-id="bd352-102">如何：使用子时间线简化动画</span><span class="sxs-lookup"><span data-stu-id="bd352-102">How to: Simplify Animations by Using Child Timelines</span></span>
<span data-ttu-id="bd352-103">此示例演示如何通过使用子简化动画<xref:System.Windows.Media.Animation.ParallelTimeline>对象。</span><span class="sxs-lookup"><span data-stu-id="bd352-103">This example shows how to simplify animations by using child <xref:System.Windows.Media.Animation.ParallelTimeline> objects.</span></span> <span data-ttu-id="bd352-104">A<xref:System.Windows.Media.Animation.Storyboard>是一种<xref:System.Windows.Media.Animation.Timeline>提供为它包含的时间线的目标信息。</span><span class="sxs-lookup"><span data-stu-id="bd352-104">A <xref:System.Windows.Media.Animation.Storyboard> is a type of <xref:System.Windows.Media.Animation.Timeline> that provides targeting information for the timelines it contains.</span></span> <span data-ttu-id="bd352-105">使用<xref:System.Windows.Media.Animation.Storyboard>提供时间线目标信息，包括对象和属性的信息。</span><span class="sxs-lookup"><span data-stu-id="bd352-105">Use a <xref:System.Windows.Media.Animation.Storyboard> to provide timeline targeting information, including object and property information.</span></span>  
  
 <span data-ttu-id="bd352-106">若要开始动画，使用一个或多<xref:System.Windows.Media.Animation.ParallelTimeline>对象作为嵌套的子元素的<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="bd352-106">To begin an animation, use one or more <xref:System.Windows.Media.Animation.ParallelTimeline> objects as nested child elements of a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="bd352-107">这些<xref:System.Windows.Media.Animation.ParallelTimeline>对象可以包含其他动画，因此，可以更好地封装复杂的动画中的计时序列。</span><span class="sxs-lookup"><span data-stu-id="bd352-107">These <xref:System.Windows.Media.Animation.ParallelTimeline> objects can contain other animations and therefore, can better encapsulate the timing sequences in complex animations.</span></span> <span data-ttu-id="bd352-108">例如，如果进行动画处理<xref:System.Windows.Controls.TextBlock>和中相同的多个形状<xref:System.Windows.Media.Animation.Storyboard>，你可以分隔为动画<xref:System.Windows.Controls.TextBlock>和形状，将放入一个单独的每个<xref:System.Windows.Media.Animation.ParallelTimeline>。</span><span class="sxs-lookup"><span data-stu-id="bd352-108">For example, if you are animating a <xref:System.Windows.Controls.TextBlock> and several shapes in the same <xref:System.Windows.Media.Animation.Storyboard>, you can separate the animations for the <xref:System.Windows.Controls.TextBlock> and the shapes, putting each into a separate <xref:System.Windows.Media.Animation.ParallelTimeline>.</span></span> <span data-ttu-id="bd352-109">因为每个<xref:System.Windows.Media.Animation.ParallelTimeline>都具有其自己<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>和的所有子元素<xref:System.Windows.Media.Animation.ParallelTimeline>开始相对于此<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>，更好地封装计时。</span><span class="sxs-lookup"><span data-stu-id="bd352-109">Because each <xref:System.Windows.Media.Animation.ParallelTimeline> has its own <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> and all child elements of the <xref:System.Windows.Media.Animation.ParallelTimeline> begin relative to this <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, timing is better encapsulated.</span></span>  
  
 <span data-ttu-id="bd352-110">下面的示例进行动画处理的文本的两个片段 (<xref:System.Windows.Controls.TextBlock>对象) 从在同一<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="bd352-110">The following example animates two pieces of text (<xref:System.Windows.Controls.TextBlock> objects) from within the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="bd352-111">A<xref:System.Windows.Media.Animation.ParallelTimeline>封装之一的动画<xref:System.Windows.Controls.TextBlock>对象。</span><span class="sxs-lookup"><span data-stu-id="bd352-111">A <xref:System.Windows.Media.Animation.ParallelTimeline> encapsulates the animations of one of the <xref:System.Windows.Controls.TextBlock> objects.</span></span>  
  
 <span data-ttu-id="bd352-112">**性能注意：**虽然可以嵌套<xref:System.Windows.Media.Animation.Storyboard>时间线内彼此之上，<xref:System.Windows.Media.Animation.ParallelTimeline>是更适合嵌套因为它们需要较少的开销。</span><span class="sxs-lookup"><span data-stu-id="bd352-112">**Performance Note:** Although you can nest <xref:System.Windows.Media.Animation.Storyboard> timelines inside each other, <xref:System.Windows.Media.Animation.ParallelTimeline>s are more suitable for nesting because they require less overhead.</span></span> <span data-ttu-id="bd352-113">(<xref:System.Windows.Media.Animation.Storyboard>类继承自<xref:System.Windows.Media.Animation.ParallelTimeline>类。)</span><span class="sxs-lookup"><span data-stu-id="bd352-113">(The <xref:System.Windows.Media.Animation.Storyboard> class inherits from the <xref:System.Windows.Media.Animation.ParallelTimeline> class.)</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd352-114">示例</span><span class="sxs-lookup"><span data-stu-id="bd352-114">Example</span></span>  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="bd352-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd352-115">See Also</span></span>  
 [<span data-ttu-id="bd352-116">动画概述</span><span class="sxs-lookup"><span data-stu-id="bd352-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="bd352-117">指定演示图板动画之间的 HandoffBehavior</span><span class="sxs-lookup"><span data-stu-id="bd352-117">Specify HandoffBehavior Between Storyboard Animations</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)
