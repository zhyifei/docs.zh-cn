---
title: "如何：在使用演示图板对属性进行动画处理后设置该属性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3ffc534549f5b114a07f09326be72c1968d178a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a>如何：在使用演示图板对属性进行动画处理后设置该属性
在某些情况下，它可能显示，你不能更改属性的值后进行动画处理。  
  
## <a name="example"></a>示例  
 在下面的示例中，<xref:System.Windows.Media.Animation.Storyboard>用于进行动画处理的颜色<xref:System.Windows.Media.SolidColorBrush>。 单击该按钮时，将触发情节提要。 <xref:System.Windows.Media.Animation.Timeline.Completed>以便通知程序处理事件时<xref:System.Windows.Media.Animation.ColorAnimation>完成。  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a>示例  
 后<xref:System.Windows.Media.Animation.ColorAnimation>完成后，该程序尝试更改画笔的颜色为蓝色。  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 前面的代码不会显示为执行任何操作： 画笔仍然保持为黄色，即的值提供<xref:System.Windows.Media.Animation.ColorAnimation>基值画笔。 基础属性值 （基本值） 实际更改为蓝色。 但是，有效，或者说当前值仍保持为黄色因为<xref:System.Windows.Media.Animation.ColorAnimation>仍将重写的基础价值。 如果你想要再次变得有效的值的基础值，你必须停止动画影响该属性。 有三种方法可以使用情节提要动画执行此操作：  
  
-   设置动画的<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性<xref:System.Windows.Media.Animation.FillBehavior.Stop>  
  
-   删除整个情节提要。  
  
-   动画移除单个属性。  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a>将动画的 FillBehavior 属性设置为停止  
 通过设置<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>到<xref:System.Windows.Media.Animation.FillBehavior.Stop>，告诉动画停止它到达其有效期末尾后影响其目标属性。  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a>删除整个情节提要  
 通过使用<xref:System.Windows.Media.Animation.RemoveStoryboard>触发器或<xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>方法，你可以判断停止影响其目标属性的情节提要动画。 此方法与设置之间的差异<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性是你可以删除情节提要在任何时候，而<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>时动画到达其有效期末尾后，属性将仅才有效。  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a>动画移除的单个属性  
 若要停止动画影响属性的另一种方法是使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>正进行动画处理的对象的方法。 指定正进行动画处理的第一个参数的属性和`null`为第二个。  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 此方法也适用于非情节提要的动画。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.Animation.RemoveStoryboard>  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [属性动画技术概述](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
