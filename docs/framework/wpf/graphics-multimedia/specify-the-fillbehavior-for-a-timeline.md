---
title: 如何：为已经到达有效期末尾的时间线指定 FillBehavior
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141168"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>如何：为已经到达有效期末尾的时间线指定 FillBehavior
此示例演示如何<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>为动画属性的非活动<xref:System.Windows.Media.Animation.Timeline>指定 。  
  
## <a name="example"></a>示例  
 属性<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A><xref:System.Windows.Media.Animation.Timeline>确定动画属性未进行动画处理时（即 非活动但其父<xref:System.Windows.Media.Animation.Timeline><xref:System.Windows.Media.Animation.Timeline>属性在其活动或保留期间内）的值会发生什么情况。 例如，动画属性在动画结束后是否保持其结束值，还是恢复到动画启动前的值？  
  
 下面的示例使用 为<xref:System.Windows.Media.Animation.DoubleAnimation>两<xref:System.Windows.FrameworkElement.Width%2A>个矩形设置动画。 每个矩形使用不同的<xref:System.Windows.Media.Animation.Timeline>对象。  
  
 一<xref:System.Windows.Media.Animation.Timeline>个设置为<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>的 有<xref:System.Windows.Media.Animation.FillBehavior.Stop>一个 ，这将导致矩形的宽度在<xref:System.Windows.Media.Animation.Timeline>结束时恢复到其非动画值。 另<xref:System.Windows.Media.Animation.Timeline>一个具有<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>， 这将导致宽度在<xref:System.Windows.Media.Animation.Timeline>结束时保持其结束值。  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 有关完整示例，请参阅[动画示例库](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [动画概述](animation-overview.md)
- [动画和计时帮助主题](animation-and-timing-how-to-topics.md)
