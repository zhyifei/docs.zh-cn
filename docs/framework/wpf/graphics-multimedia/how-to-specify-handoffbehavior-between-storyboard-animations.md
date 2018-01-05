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
ms.openlocfilehash: 21d4a39b9cbd2ee563edd22818630c18658e1d6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a>如何：指定演示图板动画之间的 HandoffBehavior
此示例演示如何指定情节提要动画之间的切换行为。 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>属性<xref:System.Windows.Media.Animation.BeginStoryboard>指定如何新动画进行交互的任何现有已应用于属性。  
  
## <a name="example"></a>示例  
 下面的示例创建两个按钮扩大当鼠标光标将移到它们并当光标移开时变得更小。 如果你将鼠标移到按钮，然后快速删除光标，在第一个完成之前，将应用第二个动画。 两个动画像这样你可以看到之间的区别重叠时，它是<xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>值<xref:System.Windows.Media.Animation.HandoffBehavior.Compose>和<xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>。 值为<xref:System.Windows.Media.Animation.HandoffBehavior.Compose>导致之间的值时的动画的更流畅转换在出现动画<xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>使新动画立即替换之前的重叠的动画。  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [动画和计时](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
