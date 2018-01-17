---
title: "如何：使用 From、To 和 By 控制动画"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17f87c8bcf09022aa389df779e29f5e5affabc20
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>如何：使用 From、To 和 By 控制动画
"从/到/者"或"基本动画"创建两个目标值之间的转换 (请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)有关不同类型的动画的简介)。 若要设置的基本动画的目标值，使用其<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>， <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>，和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性。  下表总结了如何<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>， <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>，和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性可能一起使用或单独来确定动画的目标值。  
  
|指定的属性|产生的行为|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|从指定的值的动画<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性设为正在进行动画处理的属性的基值或前一动画的输出值，具体取决于如何配置前一动画。|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|从指定的值的动画<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性设置为指定的值<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性。|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|从指定的值的动画<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>的总和来指定的值的属性<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性。|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|动画转换从动画的属性的基值或前一动画的输出值与指定的值<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性。|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|动画从正在进行动画处理的属性的基值或前一动画的输出值，该值与指定的值的要求和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性。|  
  
> [!NOTE]
>  请勿同时设置<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>上相同的动画的属性。  
  
 若要在两个以上的目标值之间使用内插方法或进行动画处理，请使用关键帧动画。 请参阅[关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)有关详细信息。  
  
 有关将多个动画应用到单个属性的信息，请参阅[关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)。  
  
 下面的示例演示的设置不同的效果<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>， <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>，和<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>动画的属性。  
  
## <a name="example"></a>示例  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>请参阅  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [From、To 和 By 动画目标值示例](http://go.microsoft.com/fwlink/?LinkID=159988)
