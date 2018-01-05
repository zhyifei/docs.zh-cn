---
title: "如何：在重复循环过程中累积动画值"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96a91856cdfcf1ca7ae87e8e571306170feecb7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a>如何：在重复循环过程中累积动画值
此示例演示如何使用<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>属性通过重复循环累积动画值。  
  
## <a name="example"></a>示例  
 使用<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>属性通过重复循环累积的动画基值。 例如，如果你设置重复 9 次的动画 (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> ="9 x") 并设置要 10 到 15 之间进行动画处理的属性 (从 = 10 到 = 15)，该属性进行动画处理从 10 到 15 在第一个周期中，从 15 到 20 在第二个周期从 20%到 25 期间第三个周期，依次类推。 因此，每个动画循环使用从以前的动画循环结束的动画值作为其基础值。  
  
 你可以使用`IsCumulative`具有最基本的动画和大多数关键帧动画属性。 有关详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)和[关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)。  
  
 下面的示例演示此行为通过进行动画处理的四个矩形的宽度。 下面的示例：  
  
-   与第一个矩形进行动画处理<xref:System.Windows.Media.Animation.DoubleAnimation>和设置<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>属性`true`。  
  
-   与第二个矩形进行动画处理<xref:System.Windows.Media.Animation.DoubleAnimation>和设置<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>属性的默认值`false`。  
  
-   与第三个矩形进行动画处理<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>和设置<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A>属性`true`。  
  
-   进行动画处理的最后一个矩形与<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>和设置<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A>属性`false`。  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a>请参阅  
 [向动画起始值添加动画输出值](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)  
 [重复动画](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
