---
title: 如何：指定时间线是否自动反转
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 498aefa16b8a76262c01965b8992ef9a94b7ce28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560060"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a>如何：指定时间线是否自动反转
时间线的<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性确定是否它播放按相反的顺序完成向前迭代后。 下面的示例演示使用相同的持续时间和目标值，但使用不同的几个动画<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>设置。 为了演示如何<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性具有不同的行为<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>设置，某些动画都设置为重复。 最后一个的动画演示如何<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性适用于嵌套的时间线。  
  
## <a name="example"></a>示例  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
