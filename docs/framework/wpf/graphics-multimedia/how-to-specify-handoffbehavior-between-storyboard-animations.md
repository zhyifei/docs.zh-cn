---
title: "如何：指定演示图板动画之间的 HandoffBehavior"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9d11c559679b67c22eeed87893bf2e362084034c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="b419d-102">如何：指定演示图板动画之间的 HandoffBehavior</span><span class="sxs-lookup"><span data-stu-id="b419d-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="b419d-103">此示例演示如何指定情节提要动画之间的切换行为。</span><span class="sxs-lookup"><span data-stu-id="b419d-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="b419d-104"><xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>属性<xref:System.Windows.Media.Animation.BeginStoryboard>指定如何新动画进行交互的任何现有已应用于属性。</span><span class="sxs-lookup"><span data-stu-id="b419d-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b419d-105">示例</span><span class="sxs-lookup"><span data-stu-id="b419d-105">Example</span></span>  
 <span data-ttu-id="b419d-106">下面的示例创建两个按钮扩大当鼠标光标将移到它们并当光标移开时变得更小。</span><span class="sxs-lookup"><span data-stu-id="b419d-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="b419d-107">如果你将鼠标移到按钮，然后快速删除光标，在第一个完成之前，将应用第二个动画。</span><span class="sxs-lookup"><span data-stu-id="b419d-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="b419d-108">两个动画像这样你可以看到之间的区别重叠时，它是<xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>值<xref:System.Windows.Media.Animation.HandoffBehavior.Compose>和<xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>。</span><span class="sxs-lookup"><span data-stu-id="b419d-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="b419d-109">值为<xref:System.Windows.Media.Animation.HandoffBehavior.Compose>导致之间的值时的动画的更流畅转换在出现动画<xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>使新动画立即替换之前的重叠的动画。</span><span class="sxs-lookup"><span data-stu-id="b419d-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b419d-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="b419d-110">See Also</span></span>  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [<span data-ttu-id="b419d-111">动画概述</span><span class="sxs-lookup"><span data-stu-id="b419d-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="b419d-112">动画和计时</span><span class="sxs-lookup"><span data-stu-id="b419d-112">Animation and Timing</span></span>](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="b419d-113">帮助主题</span><span class="sxs-lookup"><span data-stu-id="b419d-113">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
