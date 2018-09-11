---
title: 如何：指定演示图板动画之间的 HandoffBehavior
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: 6846cde9fd0aa93a0ce57fd2da0f9e1df85ec5a4
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44264449"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="09148-102">如何：指定演示图板动画之间的 HandoffBehavior</span><span class="sxs-lookup"><span data-stu-id="09148-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="09148-103">此示例演示如何指定演示图板动画之间的切换行为。</span><span class="sxs-lookup"><span data-stu-id="09148-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="09148-104"><xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>属性的<xref:System.Windows.Media.Animation.BeginStoryboard>指定新动画已应用于属性的任何现有与之交互。</span><span class="sxs-lookup"><span data-stu-id="09148-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09148-105">示例</span><span class="sxs-lookup"><span data-stu-id="09148-105">Example</span></span>  
 <span data-ttu-id="09148-106">以下示例创建两个按钮放大鼠标光标移动到它们上方时，将光标移开时变得更小。</span><span class="sxs-lookup"><span data-stu-id="09148-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="09148-107">如果将鼠标移到一个按钮，然后快速删除光标，第一个完成之前，将应用第二个动画。</span><span class="sxs-lookup"><span data-stu-id="09148-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="09148-108">像这样，您可以看到之间的差异的两个动画重叠时，它是<xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>的值<xref:System.Windows.Media.Animation.HandoffBehavior.Compose>和<xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>。</span><span class="sxs-lookup"><span data-stu-id="09148-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="09148-109">值为<xref:System.Windows.Media.Animation.HandoffBehavior.Compose>结合了导致由于可以顺利过渡动画时的值之间的重叠动画<xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>使新动画立即替换之前的重叠的动画。</span><span class="sxs-lookup"><span data-stu-id="09148-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="09148-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="09148-110">See Also</span></span>  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [<span data-ttu-id="09148-111">动画概述</span><span class="sxs-lookup"><span data-stu-id="09148-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="09148-112">动画和计时</span><span class="sxs-lookup"><span data-stu-id="09148-112">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="09148-113">帮助主题</span><span class="sxs-lookup"><span data-stu-id="09148-113">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
