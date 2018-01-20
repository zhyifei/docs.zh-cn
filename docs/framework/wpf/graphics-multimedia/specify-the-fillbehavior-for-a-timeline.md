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
ms.openlocfilehash: 4b890d121cf06dc377a3bbc1dc569d9dac7c011b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>如何：为已经到达有效期末尾的时间线指定 FillBehavior
此示例演示如何指定<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>的非活动<xref:System.Windows.Media.Animation.Timeline>的动画的属性。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性<xref:System.Windows.Media.Animation.Timeline>确定时它将不会动画属性的值会发生什么情况进行动画处理，即，当<xref:System.Windows.Media.Animation.Timeline>处于非活动状态，但其父级<xref:System.Windows.Media.Animation.Timeline>仍处于其有效期或保持期内。 例如，未经过动画处理的属性保留为其结束后动画结束或不它的值还原为动画启动之前的值？  
  
 下面的示例使用<xref:System.Windows.Media.Animation.DoubleAnimation>要进行动画处理<xref:System.Windows.FrameworkElement.Width%2A>两个矩形。 每个矩形都使用不同<xref:System.Windows.Media.Animation.Timeline>对象。  
  
 一个<xref:System.Windows.Media.Animation.Timeline>具有<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>设置为<xref:System.Windows.Media.Animation.FillBehavior.Stop>，这将导致产生要还原为其非动画的矩形的宽度值时<xref:System.Windows.Media.Animation.Timeline>结束。 其他<xref:System.Windows.Media.Animation.Timeline>具有<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>的<xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>，这将导致产生宽度将保留在其一端值时<xref:System.Windows.Media.Animation.Timeline>结束。  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 有关完整的示例，请参阅[动画示例库](http://go.microsoft.com/fwlink/?LinkID=159969)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Animation.DoubleAnimation>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [动画和计时](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
