---
title: From To By 动画概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 661c035f55ba1fb550726d75921cd01a72b2eecc
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448995"
---
# <a name="fromtoby-animations-overview"></a>From/To/By 动画概述
本主题介绍如何使用 From/To/By 动画对依赖属性进行动画处理。 From/To/By 动画创建两个值之间的转换。  
  
<a name="prereq"></a>   
## <a name="prerequisites"></a>先决条件  
 若要了解本主题，应熟悉 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画功能。 有关动画功能的简介，请参阅[动画概述](animation-overview.md)。  
  
<a name="whatisanimation"></a>   
## <a name="what-is-a-fromtoby-animation"></a>什么是 From/To/By 动画？  
 From/To/By 动画是 <xref:System.Windows.Media.Animation.AnimationTimeline> 的一种类型，它在起始值和结束值之间创建过渡。 完成转换所需的时间取决于动画的 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>。  
  
 可以通过在标记和代码中使用 <xref:System.Windows.Media.Animation.Storyboard>，或在代码中使用 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 方法，将 From/To/By 动画应用到属性。 还可以使用 From/To/By 动画创建 <xref:System.Windows.Media.Animation.AnimationClock>，并将其应用于一个或多个属性。 有关应用动画的不同方法的详细信息，请参阅[属性动画技术概述](property-animation-techniques-overview.md)。  
  
 From/To/By 动画的目标值不能超过两个。 如果需要具有两个以上目标值的动画，请使用关键帧。 关键帧动画[概述](key-frame-animations-overview.md)中介绍了关键帧动画。  
  
<a name="animation_types"></a>   
## <a name="fromtoby-animation-types"></a>From/To/By 动画类型  
 由于动画生成属性值，因此不同的属性类型有不同的动画类型。 若要对采用 <xref:System.Double>的属性（如元素的 <xref:System.Windows.FrameworkElement.Width%2A> 属性）进行动画处理，请使用生成 <xref:System.Double> 值的动画。 若要对采用 <xref:System.Windows.Point>的属性进行动画处理，请使用生成 <xref:System.Windows.Point> 值的动画等。  
  
 From/To/By 动画类属于 <xref:System.Windows.Media.Animation> 命名空间，并使用以下命名约定：  
  
 *\<类型 >* `Animation`  
  
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
 From/To/By 动画创建两个目标值之间的转换。 常见的方法是指定起始值（使用 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性设置该值）和结束值（使用 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 属性进行设置）。 但是，还可以仅指定起始值、目标值或偏移值。 在这些类中，动画从要进行动画处理的属性中获取缺少的目标值。 以下列表描述了指定动画目标值的各种方法。  
  
- **起始值**  
  
     如果要显式指定动画的起始值，请使用 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性。 您可以单独使用 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性，也可以使用 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 或 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性。 如果仅指定 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性，则动画将从该值转换为经过动画处理的属性的基值。  
  
- **终止值**  
  
     若要指定动画的结束值，请使用它的 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 属性。 如果单独使用 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 属性，则动画从正在进行动画处理的属性或从应用于同一属性的另一个动画的输出获取其起始值。 可以结合使用 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 属性和 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性来显式指定动画的起始值和终止值。  
  
- **偏移值**  
  
     利用 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性，您可以为动画指定偏移量，而不是显式起始值或终止值。 动画的 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性指定动画在其持续时间内更改值的程度。 可以单独使用 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性，也可以通过 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性使用。 如果仅指定 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性，则动画会将偏移值添加到属性的基值或另一个动画的输出。  
  
<a name="examples"></a>   
## <a name="using-fromtoby-values"></a>使用 From/To/By 值  
 以下部分介绍如何一起使用 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>、<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性。  
  
 本节中的示例每个都使用 <xref:System.Windows.Media.Animation.DoubleAnimation>，这是 From/To/By 动画的一种类型，用于对一个 <xref:System.Windows.Shapes.Rectangle> 为10个与设备无关的像素（高和100与设备无关的像素）的的 <xref:System.Windows.FrameworkElement.Width%2A> 属性进行动画处理。  
  
 尽管每个示例都使用 <xref:System.Windows.Media.Animation.DoubleAnimation>，但所有 From/To/By 动画的 From、To 和 By 属性的行为都是相同的。 尽管上述每个示例都使用 <xref:System.Windows.Media.Animation.Storyboard>，但你可以通过其他方式使用 From/To/By 动画。 有关详细信息，请参阅[属性动画技术概述](property-animation-techniques-overview.md)。  
  
### <a name="fromto"></a>从/到  
 同时设置 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 值时，动画将从 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性指定的值继续到 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 属性指定的值。  
  
 下面的示例将 <xref:System.Windows.Media.Animation.DoubleAnimation> 的 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性设置为50，并将其 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 属性设置为300。 因此，<xref:System.Windows.Shapes.Rectangle> 的 <xref:System.Windows.FrameworkElement.Width%2A> 从50到300进行动画处理。  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>至  
 当只设置 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 属性时，动画将从已进行动画处理的属性的基值开始，或从先前应用于同一属性的组合动画的输出到由 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 属性指定的值进行。  
  
 （"组合动画" 指的是以前应用到同一个属性的 <xref:System.Windows.Media.Animation.ClockState.Active> 或 <xref:System.Windows.Media.Animation.ClockState.Filling> 动画，该属性在使用 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> 移交行为应用当前动画时仍有效。）  
  
 下面的示例仅将 <xref:System.Windows.Media.Animation.DoubleAnimation> 的 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 属性设置为300。 由于未指定起始值，因此 <xref:System.Windows.Media.Animation.DoubleAnimation> 使用 <xref:System.Windows.FrameworkElement.Width%2A> 属性的基值（100）作为其起始值。 <xref:System.Windows.Shapes.Rectangle> 的 <xref:System.Windows.FrameworkElement.Width%2A> 从100动画的目标值300。  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>通过  
 当只设置动画的 "<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>" 属性时，动画将从要进行动画处理的属性的基值开始，或者从组合动画的输出到该值的总和和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性指定的值进行。  
  
 下面的示例仅将 <xref:System.Windows.Media.Animation.DoubleAnimation> 的 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性设置为300。 由于该示例未指定起始值，因此 <xref:System.Windows.Media.Animation.DoubleAnimation> 使用 <xref:System.Windows.FrameworkElement.Width%2A> 属性的基值（100）作为其起始值。 结束值通过将动画的 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 值300添加到其起始值100：400来确定。 因此，<xref:System.Windows.Shapes.Rectangle> 的 <xref:System.Windows.FrameworkElement.Width%2A> 从100到400进行动画处理。  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 设置动画的 "<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>" 和 "<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性" 时，动画将从 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性指定的值前进到 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 和 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性的总和指定的值。  
  
 下面的示例将 <xref:System.Windows.Media.Animation.DoubleAnimation> 的 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性设置为50，并将其 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 属性设置为300。 结束值通过将动画的 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 值300添加到其起始值50：350来确定。 因此，<xref:System.Windows.Shapes.Rectangle> 的 <xref:System.Windows.FrameworkElement.Width%2A> 从50到350进行动画处理。  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>From  
 当您仅指定动画的 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 值时，动画将从 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性指定的值前进到要进行动画处理的属性的基值或组合动画的输出。  
  
 下面的示例仅将 <xref:System.Windows.Media.Animation.DoubleAnimation> 的 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 属性设置为50。 由于未指定终止值，因此 <xref:System.Windows.Media.Animation.DoubleAnimation> 使用 <xref:System.Windows.FrameworkElement.Width%2A> 属性的基值100作为其结束值。 <xref:System.Windows.Shapes.Rectangle> 的 <xref:System.Windows.FrameworkElement.Width%2A> 从50动画处理到 <xref:System.Windows.FrameworkElement.Width%2A> 属性100的基值。  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 如果同时设置动画的 "<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>" 和 "<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>" 属性，则将忽略 "<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>" 属性。  
  
<a name="otheranimationtypes"></a>   
## <a name="other-animation-types"></a>其他动画类型  
 From/To/By 动画不是 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供的唯一动画类型：它还提供关键帧动画和路径动画。  
  
- 关键帧动画沿使用关键帧描述的任意数量的目标值进行动画处理。 有关详细信息，请参阅[关键帧动画概述](key-frame-animations-overview.md)。  
  
- 路径动画从 <xref:System.Windows.Media.PathGeometry>生成输出值。 有关详细信息，请参阅[路径动画概述](path-animations-overview.md)。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 还支持创建自己的自定义动画类型。 有关详细信息，请参阅[自定义动画概述](custom-animations-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [动画概述](animation-overview.md)
- [演示图板概述](storyboards-overview.md)
- [关键帧动画概述](key-frame-animations-overview.md)
- [路径动画概述](path-animations-overview.md)
- [自定义动画概述](custom-animations-overview.md)
- [From、To 和 By 动画目标值示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
