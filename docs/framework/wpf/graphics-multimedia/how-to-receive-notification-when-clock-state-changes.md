---
title: "如何： 接收通知时时钟 &#39; s 状态更改"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f59fddb1add29d52ccba6fc8b8ce84938b53a1c2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-receive-notification-when-a-clock39s-state-changes"></a>如何： 接收通知时时钟 &#39; s 状态更改
时钟的<xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated>事件发生时其<xref:System.Windows.Media.Animation.Clock.CurrentState%2A>将变为无效，如时钟时启动或停止。 你可以直接使用此事件注册<xref:System.Windows.Media.Animation.Clock>，或者也可以注册使用<xref:System.Windows.Media.Animation.Timeline>。  
  
 在下面的示例中，<xref:System.Windows.Media.Animation.Storyboard>和两个<xref:System.Windows.Media.Animation.DoubleAnimation>使用对象进行动画处理的两个矩形的宽度。 <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>事件用于侦听的时钟状态更改。  
  
## <a name="example"></a>示例  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 下图显示的不同状态动画输入作为父时间线 (*情节提要*) 进行。  
  
 ![具有两个动画的演示图板的时钟状态](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")  
  
 下表显示时间从该处*Animation1*的<xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>事件将触发：  
  
||||||||  
|-|-|-|-|-|-|-|  
|时间 （秒）|1|10|19|21|30|39|  
|状态|活动|活动|已停止|活动|活动|已停止|  
  
 下表显示时间从该处*Animation2*的<xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>事件将触发：  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|时间 （秒）|1|9|11|19|21|29|31|39|  
|状态|活动|填充|活动|已停止|活动|填充|活动|已停止|  
  
 请注意， *Animation1*的<xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>在 10 秒，将激发的事件，即使其状态保持<xref:System.Windows.Media.Animation.ClockState.Active>。 这是因为在 10 秒，更改其状态，但它从更改<xref:System.Windows.Media.Animation.ClockState.Active>到<xref:System.Windows.Media.Animation.ClockState.Filling>和再转回<xref:System.Windows.Media.Animation.ClockState.Active>中相同的刻度。
