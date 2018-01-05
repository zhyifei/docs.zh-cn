---
title: "From-到-By 动画概述"
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
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c4c2c3b9cabb630b5762fdc49f6cb62eef28f71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="fromtoby-animations-overview"></a>From/To/By 动画概述
本主题介绍如何使用 From/To/By 动画对依赖属性进行动画处理。 From/To/By 动画创建两个值之间的转换。  
  
<a name="prereq"></a>   
## <a name="prerequisites"></a>系统必备  
 若要了解本主题，你应熟悉[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]动画功能。 动画功能的简介，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。  
  
<a name="whatisanimation"></a>   
## <a name="what-is-a-fromtoby-animation"></a>什么是 From/To/By 动画？  
 From/To/By 动画，则一种<xref:System.Windows.Media.Animation.AnimationTimeline>创建起始值和结束值之间的转换。 转换完成所需的时间量由<xref:System.Windows.Media.Animation.Timeline.Duration%2A>该动画。  
  
 你可以从/到/的应用到属性时使用动画<xref:System.Windows.Media.Animation.Storyboard>在标记和代码，或使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>代码中的方法。 此外可以使用 From/To/By 动画来创建<xref:System.Windows.Media.Animation.AnimationClock>并将其应用到一个或多个属性。 有关应用动画的不同方法的详细信息，请参阅[属性动画技术概述](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)。  
  
 From/To/By 动画的目标值不能超过两个。 如果需要具有两个以上目标值的动画，请使用关键帧。 关键帧动画进行了介绍[关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)。  
  
<a name="animation_types"></a>   
## <a name="fromtoby-animation-types"></a>From/To/By 动画类型  
 由于动画会生成属性值，因此不同的属性类型具有不同的动画类型。 要进行动画处理的属性<xref:System.Double>，如<xref:System.Windows.FrameworkElement.Width%2A>属性的元素，使用动画生成<xref:System.Double>值。 要进行动画处理的属性<xref:System.Windows.Point>，使用动画生成<xref:System.Windows.Point>值，等等。  
  
 From/To/By 动画类属于<xref:System.Windows.Media.Animation>命名空间并使用以下命名约定：  
  
 *\<Type>* `Animation`  
  
 其中 *\<Type>* 为该类进行动画处理的值的类型。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供以下 From/To/By 动画类。  
  
|属性类型|对应的 From/To/By 动画类|  
|-------------------|------------------------------------------------|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimation>|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimation>|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16Animation>|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32Animation>|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64Animation>|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimation>|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimation>|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimation>|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimation>|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimation>|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimation>|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimation>|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimation>|  
  
<a name="anim_values"></a>   
## <a name="target-values"></a>目标值  
 From/To/By 动画创建两个目标值之间的转换。 它是常见的是指定起始值 (通过设置<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性) 和结束值 (通过设置<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性)。 但是，还可以仅指定起始值、目标值或偏移值。 在这些类中，动画从要进行动画处理的属性中获取缺少的目标值。 以下列表描述了指定动画目标值的各种方法。  
  
-   **起始值**  
  
     使用<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性，当你想要显式指定动画的起始值。 你可以使用<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性本身，或与<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>或<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性。 如果只指定<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性，在动画转换从该值到基础值的动画的属性。  
  
-   **终止值**  
  
     若要指定动画的结束值，使用其<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性。 如果你使用<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>本身的属性，从正在进行动画处理的属性或输出中将应用到相同的属性的另一个动画的动画获取其起始值。 你可以使用<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性连同<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性来显式指定开始和结束用于动画的值。  
  
-   **偏移值**  
  
     <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性使您能够指定偏移量而不是显式启动或终止用于动画的值。 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>的动画的属性指定由多少动画更改其持续时间内的某个值。 你可以使用<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性本身或与<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性。 如果只指定<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性，动画将偏移量的值添加到属性的基值或另一个动画的输出。  
  
<a name="examples"></a>   
## <a name="using-fromtoby-values"></a>使用 From/To/By 值  
 下列各节描述如何使用<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>， <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>，和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性单独或一起。  
  
 本节中的示例的每次使用<xref:System.Windows.Media.Animation.DoubleAnimation>，这是一种 From/To/By 动画，要进行动画处理<xref:System.Windows.FrameworkElement.Width%2A>属性<xref:System.Windows.Shapes.Rectangle>即 10 设备无关的像素高和 100 设备独立像素宽。  
  
 虽然每个示例使用<xref:System.Windows.Media.Animation.DoubleAnimation>，则从，，以及属性的所有 From/To/By 动画具有相同行为。 尽管上述每个示例使用<xref:System.Windows.Media.Animation.Storyboard>，你可以通过其他方式使用 From/To/By 动画。 有关详细信息，请参阅[属性动画技术概述](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)。  
  
### <a name="fromto"></a>从/到  
 当你将设置<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>和<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>值一起使用，从指定的值的动画<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性，通过指定的值<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性。  
  
 下面的示例设置<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性<xref:System.Windows.Media.Animation.DoubleAnimation>为 50 及其<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>和 300 之间的属性。 因此，<xref:System.Windows.FrameworkElement.Width%2A>的<xref:System.Windows.Shapes.Rectangle>动画处理的来自 50 台和 300 之间。  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>到  
 如果只设置<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性，则从的动画的属性的基值或以前应用的同一属性，指定的值的组合动画的输出中的动画继续<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性。  
  
 ("撰写动画"指<xref:System.Windows.Media.Animation.ClockState.Active>或<xref:System.Windows.Media.Animation.ClockState.Filling>之前应用于当前的动画应用通过使用时所做的更改的相同属性的动画<xref:System.Windows.Media.Animation.HandoffBehavior.Compose>切换行为。)  
  
 下面的示例只需设置<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性<xref:System.Windows.Media.Animation.DoubleAnimation>和 300 之间。 未不指定任何起始值，因为<xref:System.Windows.Media.Animation.DoubleAnimation>使用的是基本值 (100) 的<xref:System.Windows.FrameworkElement.Width%2A>属性作为其起始值。 <xref:System.Windows.FrameworkElement.Width%2A>的<xref:System.Windows.Shapes.Rectangle>进行动画处理，从 100 到 300 动画的目标值。  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>间距  
 如果只设置<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>的动画的属性，则动画继续从正在进行动画处理，该属性的基值或来自于该值与由指定的值之和组合动画的输出<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性。  
  
 下面的示例只需设置<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性<xref:System.Windows.Media.Animation.DoubleAnimation>和 300 之间。 该示例并不指定一个起始值，因为<xref:System.Windows.Media.Animation.DoubleAnimation>使用的基础价值<xref:System.Windows.FrameworkElement.Width%2A>属性，100，作为其起始值。 结束值确定通过添加<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>动画 300，其起始值，100: 400 到值。 因此，<xref:System.Windows.FrameworkElement.Width%2A>的<xref:System.Windows.Shapes.Rectangle>进行动画处理，从 100 到 400。  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 当你将设置<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>动画的属性，从指定的值则动画继续<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性，指定的总和值<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性。  
  
 下面的示例设置<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性<xref:System.Windows.Media.Animation.DoubleAnimation>为 50 及其<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>和 300 之间的属性。 结束值确定通过添加<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>动画 300，其起始值，50: 350 到值。 因此，<xref:System.Windows.FrameworkElement.Width%2A>的<xref:System.Windows.Shapes.Rectangle>从 50 到 350 动态显示。  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>From  
 如果只指定<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>动画的值、 动画由指定的值从<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性，到正进行动画处理的属性的基值或组合动画的输出。  
  
 下面的示例只需设置<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性<xref:System.Windows.Media.Animation.DoubleAnimation>为 50。 未不指定任何结束值，因为<xref:System.Windows.Media.Animation.DoubleAnimation>使用的基础价值<xref:System.Windows.FrameworkElement.Width%2A>属性，100，作为其结束的值。 <xref:System.Windows.FrameworkElement.Width%2A>的<xref:System.Windows.Shapes.Rectangle>动画形式从 50 到的基础价值<xref:System.Windows.FrameworkElement.Width%2A>属性，100。  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 如果同时设置<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>动画，属性<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>忽略属性。  
  
<a name="otheranimationtypes"></a>   
## <a name="other-animation-types"></a>其他动画类型  
 从/到/By 动画不是唯一的动画类型的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供： 它还提供了关键帧动画和路径动画。  
  
-   关键帧动画沿使用关键帧描述的任意数量的目标值进行动画处理。 有关详细信息，请参阅[关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)。  
  
-   路径动画生成输出值从<xref:System.Windows.Media.PathGeometry>。 有关详细信息，请参阅[路径动画概述](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 还支持创建自己的自定义动画类型。 有关详细信息，请参阅[自定义动画概述](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [演示图板概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [路径动画概述](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)  
 [自定义动画概述](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)  
 [From、To 和 By 动画目标值示例](http://go.microsoft.com/fwlink/?LinkID=159988)
