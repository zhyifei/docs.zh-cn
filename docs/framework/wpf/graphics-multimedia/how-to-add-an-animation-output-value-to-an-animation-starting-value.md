---
title: "如何：向动画起始值添加动画输出值"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1a6a5923655c5857b813df778b36b6c7fd208b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a>如何：向动画起始值添加动画输出值
此示例演示如何将动画输出值添加到动画起始值。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A>属性指定是否希望添加到动画属性的起始值 （基本值） 动画的输出值。 你可以使用<xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A>具有最基本的动画和大多数关键帧动画属性。 有关详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)和[关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)。  
  
 下面的示例演示使用的效果<xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType>具有属性<xref:System.Windows.Media.Animation.DoubleAnimation>和使用<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType>具有属性<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>。  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a>请参阅  
 [在重复循环过程中累积动画值](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [动画和计时](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
