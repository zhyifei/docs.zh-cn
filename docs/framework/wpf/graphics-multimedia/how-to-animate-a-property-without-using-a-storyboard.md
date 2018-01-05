---
title: "如何：在不使用演示图板的情况下对属性进行动画处理"
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
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a1292dae3a6fc7e86387ecbe3bf2b1da6912cc0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a>如何：在不使用演示图板的情况下对属性进行动画处理
此示例演示一种方法向属性应用动画，而无需使用<xref:System.Windows.Media.Animation.Storyboard>。  
  
> [!NOTE]
>  此功能在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 中不可用。 有关在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中对属性进行动画处理的信息，请参阅[使用情节提要对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)。  
  
 若要将本地动画应用到一个属性，使用<xref:System.Windows.UIElement.BeginAnimation%2A>方法。 此方法采用两个参数： <xref:System.Windows.DependencyProperty> ，它指定属性进行动画处理，并且该动画将应用于该属性。  
  
## <a name="example"></a>示例  
 下面的示例演示如何进行动画处理的宽度和背景颜色<xref:System.Windows.Controls.Button>。  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 中的动画类<xref:System.Windows.Media.Animation>命名空间存在进行动画处理不同类型的属性。 有关对属性进行动画处理的详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。 有关依赖属性（在这些示例中显示的属性类型）及其功能的详细信息，请参阅[依赖项属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)。  
  
 要进行动画处理，而无需使用其他方式<xref:System.Windows.Media.Animation.Storyboard>对象; 有关详细信息，请参阅[属性动画技术概述](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Animation.AnimationTimeline>  
 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>  
 <xref:System.Windows.Media.Animation>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [属性动画技术概述](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
