---
title: "如何：设置动画的持续时间"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e8d15a1b8432b3dae5bee73396bdec9fc9d50f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-duration-for-an-animation"></a>如何：设置动画的持续时间
A<xref:System.Windows.Media.Animation.Timeline>表示的时间段和段的长度由时间线的<xref:System.Windows.Duration>。 当<xref:System.Windows.Media.Animation.Timeline>到达结尾的其持续时间，就会停止播放。 如果<xref:System.Windows.Media.Animation.Timeline>具有子时间线，它们也会停止播放。 对于动画，<xref:System.Windows.Duration>指定动画的时间转换从其起始值为其结束的值。  
  
 你可以指定<xref:System.Windows.Duration>与特定的有限时间或特殊值<xref:System.Windows.Duration.Automatic%2A>或<xref:System.Windows.Duration.Forever%2A>。 动画的持续时间必须始终为时间值，因为动画必须始终具有已定义的有限的长度-否则，动画将不知道如何其目标值之间进行转换。 容器时间线 (<xref:System.Windows.Media.Animation.TimelineGroup>对象)，如<xref:System.Windows.Media.Animation.Storyboard>和<xref:System.Windows.Media.Animation.ParallelTimeline>，默认持续时间为<xref:System.Windows.Duration.Automatic%2A>，这意味着它们将自动结束时其最后一个子级停止播放。  
  
 中的以下示例、 宽度、 高度和填充颜色<xref:System.Windows.Shapes.Rectangle>进行动画处理。 导致包括控制动画的感觉的速度和重写的子时间线容器时间线的持续时间的持续时间的动画效果的动画和容器时间线上设置的持续时间。  
  
## <a name="example"></a>示例  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Duration>  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
