---
title: "缓动函数"
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
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 198ec8b8cb0b27e009f01f8e60a47e8086a7dbc7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="easing-functions"></a>缓动函数
缓动函数允许将自定义的数学公式应用到动画。 例如，用户可能希望某个对象逼真地弹跳或表现出像在弹簧上一样。 可使用关键帧甚至 From/To/By 动画来近似地实现这些效果，但它将需要大量工作，并且动画不如使用数学公式准确。  
  
 除了通过继承创建你自己的自定义缓动函数外<xref:System.Windows.Media.Animation.EasingFunctionBase>，可以使用运行时提供的若干缓动函数之一来创建常见效果。  
  
-   <xref:System.Windows.Media.Animation.BackEase>： 将收回动画的运动略有开始进行动画处理中指定的路径之前。  
  
-   <xref:System.Windows.Media.Animation.BounceEase>： 创建弹跳效果。  
  
-   <xref:System.Windows.Media.Animation.CircleEase>： 创建动画加速和/或减速使用圆形函数。  
  
-   <xref:System.Windows.Media.Animation.CubicEase>： 创建动画加速和/或减速使用公式*f*(*t*) = *t*<sup>3</sup>。  
  
-   <xref:System.Windows.Media.Animation.ElasticEase>： 创建类似于弹簧 rest 直到显示来回振荡的动画。  
  
-   <xref:System.Windows.Media.Animation.ExponentialEase>： 创建动画加速和/或减速使用指数的公式。  
  
-   <xref:System.Windows.Media.Animation.PowerEase>： 创建动画加速和/或减速使用公式*f*(*t*) = *t*<sup>p</sup> p 等于<xref:System.Windows.Media.Animation.PowerEase.Power%2A>属性。  
  
-   <xref:System.Windows.Media.Animation.QuadraticEase>： 创建动画加速和/或减速使用公式*f*(*t*) = *t*<sup>2</sup>。  
  
-   <xref:System.Windows.Media.Animation.QuarticEase>： 创建动画加速和/或减速使用公式*f*(*t*) = *t*<sup>4</sup>。  
  
-   <xref:System.Windows.Media.Animation.QuinticEase>： 创建动画加速和/或减速使用公式*f*(*t*) = *t*<sup>5</sup>。  
  
-   <xref:System.Windows.Media.Animation.SineEase>： 创建动画加速和/或减速使用正弦值的公式。  
  
 可以通过以下示例探索这些缓动函数的行为。  
  
 [运行此示例](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 若要应用到动画的缓动函数，使用`EasingFunction`动画的属性指定要应用到动画的缓动函数。 下面的示例应用<xref:System.Windows.Media.Animation.BounceEase>缓动函数<xref:System.Windows.Media.Animation.DoubleAnimation>创建弹跳效果。  
  
 [运行此示例](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xaml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 在上一示例中，缓动函数应用于 From/To/By 动画。 还可以将这些缓动函数应用到关键帧动画。 以下示例显示如何将关键帧与其相关联的缓动函数结合使用，以创建一个协定上升、减速、向下展开（如同下落），然后弹跳至停止的矩形的动画。  
  
 [运行此示例](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 你可以使用<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>属性更改的缓动函数的行为方式，即，更改动画的内插。 有三个可能的值会使<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseIn>： 内插遵循的缓动函数与关联的数学公式。  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseOut>： 内插遵循的缓动函数与关联的公式的 100%减去输出的内插。  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>： 内插使用<xref:System.Windows.Media.Animation.EasingMode.EaseIn>动画上半年和<xref:System.Windows.Media.Animation.EasingMode.EaseOut>为第二部分。  
  
 下图演示的不同值<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>其中*f*(*x*) 表示的动画进度和*t*表示时间。  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![BackEase EasingMode 图。](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![BounceEase EasingMode 图。](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![CircleEase EasingMode图。](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![CubicEase EasingMode 图。](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![带不同缓动模式图的 ElasticEase。](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![不同缓动模式的 ExponentialEase 图。](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![带不同缓动模式图的 QuarticEase。](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![带不同缓动模式图的 QuadraticEase](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![带不同缓动模式图的 QuarticEase。](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![带不同缓动模式图的 QuinticEase。](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![不同 EasingMode 值的 SineEase](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
>  你可以使用<xref:System.Windows.Media.Animation.PowerEase>创建相同的行为<xref:System.Windows.Media.Animation.CubicEase>， <xref:System.Windows.Media.Animation.QuadraticEase>， <xref:System.Windows.Media.Animation.QuarticEase>，和<xref:System.Windows.Media.Animation.QuinticEase>使用<xref:System.Windows.Media.Animation.PowerEase.Power%2A>属性。 例如，如果你想要使用<xref:System.Windows.Media.Animation.PowerEase>用于替换<xref:System.Windows.Media.Animation.CubicEase>，指定<xref:System.Windows.Media.Animation.PowerEase.Power%2A>值为 3。  
  
 除了使用运行时中附带的缓动函数，您可以通过继承创建您自己的自定义缓动函数<xref:System.Windows.Media.Animation.EasingFunctionBase>。 以下示例演示如何创建简单的自定义缓动函数。 可以添加您自己的通过重写的缓动函数的行为方式的数学逻辑<xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A>方法。  
  
 [运行此示例](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
