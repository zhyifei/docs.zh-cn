---
title: "如何：使用 AnimationClock 对属性进行动画处理"
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
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 145ff1be88f1af6692a8cf374e871479ed38d7bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a>如何：使用 AnimationClock 对属性进行动画处理
此示例演示如何使用<xref:System.Windows.Media.Animation.Clock>对象属性进行动画处理。  
  
 对依赖属性进行动画处理有三种方法：  
  
-   创建<xref:System.Windows.Media.Animation.AnimationTimeline>并将其与该属性使用<xref:System.Windows.Media.Animation.Storyboard>。  
  
-   使用对象的<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法以应用单个<xref:System.Windows.Media.Animation.AnimationTimeline>到目标属性。  
  
-   创建<xref:System.Windows.Media.Animation.AnimationClock>从<xref:System.Windows.Media.Animation.AnimationTimeline>并将其应用到属性。  
  
 <xref:System.Windows.Media.Animation.Storyboard>对象和<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法使您能够对属性进行动画处理不直接创建和分发时钟 (有关示例，请参阅[使用情节提要属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)和[属性不进行动画处理使用情节提要](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md));创建和自动为你分发时钟。  
  
## <a name="example"></a>示例  
 下面的示例演示如何创建<xref:System.Windows.Media.Animation.AnimationClock>并将其应用到两个类似的属性。  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 有关演示如何以交互方式控制的示例<xref:System.Windows.Media.Animation.Clock>启动后，请参阅[以交互方式控制时钟](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用情节提要对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [在不使用情节提要的情况下为属性设置动画效果](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)  
 [属性动画技术概述](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
