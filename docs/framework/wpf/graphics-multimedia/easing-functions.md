---
title: 缓动函数
ms.date: 03/30/2017
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
ms.openlocfilehash: a25bde5098af853c3906a174a189fc35f33f0525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186503"
---
# <a name="easing-functions"></a>缓动函数
缓动函数允许将自定义的数学公式应用到动画。 例如，用户可能希望某个对象逼真地弹跳或表现出像在弹簧上一样。 可使用关键帧甚至 From/To/By 动画来近似地实现这些效果，但它将需要大量工作，并且动画不如使用数学公式准确。  
  
 除了通过继承创建自己的自定义缓动函数外<xref:System.Windows.Media.Animation.EasingFunctionBase>，您还可以使用运行时提供的几个缓动函数之一来创建常见效果。  
  
- <xref:System.Windows.Media.Animation.BackEase>：在动画开始在指示的路径中设置动画之前稍微缩回动画的运动。  
  
- <xref:System.Windows.Media.Animation.BounceEase>：创建弹跳效果。  
  
- <xref:System.Windows.Media.Animation.CircleEase>：创建使用圆形函数加速和/或减速的动画。  
  
- <xref:System.Windows.Media.Animation.CubicEase>： 创建使用公式*f*（*t*） = *t*<sup>3</sup>加速和/或减速的动画。  
  
- <xref:System.Windows.Media.Animation.ElasticEase>：创建类似于弹簧来回摆动的动画，直到它开始休息。  
  
- <xref:System.Windows.Media.Animation.ExponentialEase>：创建使用指数公式加速和/或减速的动画。  
  
- <xref:System.Windows.Media.Animation.PowerEase>： 创建使用公式*f*（*t*） = *t*<sup>p</sup>的公式加速和/或减速的动画<xref:System.Windows.Media.Animation.PowerEase.Power%2A>，其中 p 等于属性。  
  
- <xref:System.Windows.Media.Animation.QuadraticEase>： 创建使用公式*f*（*t*） = *t*<sup>2</sup>加速和/或减速的动画。  
  
- <xref:System.Windows.Media.Animation.QuarticEase>： 创建使用公式*f*（*t*） = *t*<sup>4</sup>加速和/或减速的动画。  
  
- <xref:System.Windows.Media.Animation.QuinticEase>： 创建使用公式*f*（*t*） = *t*<sup>5</sup>加速和/或减速的动画。  
  
- <xref:System.Windows.Media.Animation.SineEase>：创建使用子项公式加速和/或减速的动画。  
  
 要将缓动函数应用于动画，请使用动画`EasingFunction`的属性指定要应用于动画的缓动函数。 下面的示例将<xref:System.Windows.Media.Animation.BounceEase>缓动函数应用于<xref:System.Windows.Media.Animation.DoubleAnimation>创建弹跳效果。  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 在上一示例中，缓动函数应用于 From/To/By 动画。 还可以将这些缓动函数应用到关键帧动画。 以下示例显示如何将关键帧与其相关联的缓动函数结合使用，以创建一个协定上升、减速、向下展开（如同下落），然后弹跳至停止的矩形的动画。  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 可以使用 属性<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>更改缓动函数的特性，即更改动画插值的方式。 您可以为<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>：  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseIn>：插值遵循与缓动函数关联的数学公式。  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseOut>：插值遵循 100% 插值减去与缓动函数关联的公式的输出。  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>：插值用于<xref:System.Windows.Media.Animation.EasingMode.EaseIn>动画的上半部分和<xref:System.Windows.Media.Animation.EasingMode.EaseOut>下半场。  
  
 下图显示了*f*（*x* <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> ） 表示动画进度和*t*表示时间的不同值。  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![BackEase EasingMode 图。](./media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![BounceEase EasingMode 图。](./media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![CircleEase EasingMode 图。](./media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![CubicEase EasingMode 图。](./media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![带不同缓动模式图的 ElasticEase。](./media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![具有不同缓动模式的 ExponentialEase 图。](./media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![带不同缓动模式图的 QuarticEase。](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![具有不同缓动模式的图形的二次缓动](./media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![带不同缓动模式图的 QuarticEase。](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![带不同缓动模式图的 QuinticEase。](./media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![不同 EasingMode 值的 SineEase](./media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
> 可以使用 创建<xref:System.Windows.Media.Animation.PowerEase>与<xref:System.Windows.Media.Animation.CubicEase><xref:System.Windows.Media.Animation.QuadraticEase><xref:System.Windows.Media.Animation.QuarticEase>、 和<xref:System.Windows.Media.Animation.QuinticEase>以及 使用 属性<xref:System.Windows.Media.Animation.PowerEase.Power%2A>相同的行为。 例如，如果要使用<xref:System.Windows.Media.Animation.PowerEase>替换<xref:System.Windows.Media.Animation.CubicEase>，请指定<xref:System.Windows.Media.Animation.PowerEase.Power%2A>值 3。  
  
 除了使用运行时中包含的缓动函数外，还可以通过继承 来<xref:System.Windows.Media.Animation.EasingFunctionBase>创建自己的自定义缓动函数。 以下示例演示如何创建简单的自定义缓动函数。 您可以添加您自己的数学逻辑，用于缓动函数如何通过重写<xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A>方法来运行。
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
