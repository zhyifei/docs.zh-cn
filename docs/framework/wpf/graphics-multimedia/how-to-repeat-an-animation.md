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
ms.workload: dotnet
ms.openlocfilehash: 591053d479b7d26757eb071f08ed4216fc0d57fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-repeat-an-animation"></a>如何：重复动画
此示例演示如何使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性<xref:System.Windows.Media.Animation.Timeline>以便控制动画的重复行为。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性<xref:System.Windows.Media.Animation.Timeline>控制动画重复其简单持续时间的次数。 通过使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>，你可以指定<xref:System.Windows.Media.Animation.Timeline>一定次数的重复 （迭代计数） 或指定的时间段内。 在任一情况下，动画将经历填充的请求的计数或持续时间所需的尽可能多开头的端到端运行。  
  
 默认情况下，时间线具有重复次数为 1.0，这意味着它们播放一次，不进行重复。 但是，如果你设置<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性<xref:System.Windows.Media.Animation.Timeline>到<xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>，时间线无限期地重复。  
  
 下面的示例演示如何使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性来控制动画的重复行为。 该示例进行动画处理<xref:System.Windows.FrameworkElement.Width%2A>的每个矩形使用不同类型的重复行为的五个矩形的属性。  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 有关完整的示例，请参阅[动画计时行为示例](http://go.microsoft.com/fwlink/?LinkID=159970)。  
  
## <a name="see-also"></a>请参阅  
 [在重复循环过程中累积动画值](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [指定时间线是否自动反转](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [动画和计时](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [动画计时行为示例](http://go.microsoft.com/fwlink/?LinkID=159970)
