---
title: 逐个动画概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 135f01823d374b30f8d4d41762d2267a254f98c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186452"
---
# <a name="fromtoby-animations-overview"></a>From/To/By 动画概述
本主题介绍如何使用 From/To/By 动画对依赖属性进行动画处理。 From/To/By 动画创建两个值之间的转换。  
  
<a name="prereq"></a>
## <a name="prerequisites"></a>系统必备  
 要理解本主题，您应该熟悉[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]动画功能。 有关动画功能的简介，请参阅[动画概述](animation-overview.md)。  
  
<a name="whatisanimation"></a>
## <a name="what-is-a-fromtoby-animation"></a>什么是 From/To/By 动画？  
 From/To/By 动画是在起始值和<xref:System.Windows.Media.Animation.AnimationTimeline>结束值之间创建过渡的类型。 过渡完成所需的时间由该动画<xref:System.Windows.Media.Animation.Timeline.Duration%2A>的由该动画确定。  
  
 可以通过在标记和代码中使用 或<xref:System.Windows.Media.Animation.Storyboard>在代码中使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法对属性应用"从/到/通过"动画动画。 您还可以使用"从/到/按动画"创建 ，<xref:System.Windows.Media.Animation.AnimationClock>并将其应用于一个或多个属性。 有关应用动画的不同方法的详细信息，请参阅[属性动画技术概述](property-animation-techniques-overview.md)。  
  
 From/To/By 动画的目标值不能超过两个。 如果需要具有两个以上目标值的动画，请使用关键帧。 关键帧动画在[关键帧动画概述](key-frame-animations-overview.md)中描述。  
  
<a name="animation_types"></a>
## <a name="fromtoby-animation-types"></a>From/To/By 动画类型  
 由于动画会生成属性值，因此不同的属性类型具有不同的动画类型。 要为采用<xref:System.Double>的属性（如元素<xref:System.Windows.FrameworkElement.Width%2A>的属性）设置动画，请使用生成<xref:System.Double>值的动画。 要为 采用<xref:System.Windows.Point>的属性设置动画，请使用生成<xref:System.Windows.Point>值的动画，等等。  
  
 从/到/按动画类属于<xref:System.Windows.Media.Animation>命名空间，并使用以下命名约定：  
  
 *\<键入>*`Animation`  
  
 *\<类型>* 是类动画的值类型。  
  
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
 From/To/By 动画创建两个目标值之间的转换。 通常指定起始值（使用<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性设置它）和结束值（使用 属性<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>设置）。 但是，还可以仅指定起始值、目标值或偏移值。 在这些类中，动画从要进行动画处理的属性中获取缺少的目标值。 以下列表描述了指定动画目标值的各种方法。  
  
- **起始值**  
  
     如果要显式<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>指定动画的起始值，请使用 该属性。 您可以自行使用<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>该属性，也可以使用 或<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A><xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性。 如果仅指定该<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性，动画将从该值转换为动画属性的基值。  
  
- **终止值**  
  
     要指定动画的结束值，请使用其<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性。 如果本身使用该<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性，动画将从正在进行动画处理的属性或应用于同一属性的另一个动画的输出中获取其起始值。 可以将 属性<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>与<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性一起使用，以显式指定动画的开始和结束值。  
  
- **偏移值**  
  
     属性<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>使您能够为动画指定偏移，而不是显式起始值或结束值。 动画<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>的属性按动画在其持续时间内更改值的数量指定。 您可以自行使用该<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性，也可以使用 属性<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>。 如果仅指定该<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性，则动画会将偏移值添加到属性的基值或其他动画的输出。  
  
<a name="examples"></a>
## <a name="using-fromtoby-values"></a>使用 From/To/By 值  
 以下各节介绍如何一起使用<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>和<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>或单独使用。  
  
 本节中的示例每个示例都使用<xref:System.Windows.Media.Animation.DoubleAnimation>一个 ，这是一种"从/到/按"动画，<xref:System.Windows.FrameworkElement.Width%2A>为 10 个设备独立像素高和 100 个与设备无关的像素宽的属性<xref:System.Windows.Shapes.Rectangle>进行动画处理。  
  
 尽管每个示例使用<xref:System.Windows.Media.Animation.DoubleAnimation>的 "从"、To 和"按"属性的所有"从/到/按"动画的行为相同。 尽管每个示例都使用<xref:System.Windows.Media.Animation.Storyboard>，但可以通过其他方式使用"从/到/按"动画。 有关详细信息，请参阅[属性动画技术概述](property-animation-techniques-overview.md)。  
  
### <a name="fromto"></a>从/到  
 将<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>和<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>值一起设置时，动画将从<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性指定的值到<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性指定的值进行。  
  
 下面的示例将 属性<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A><xref:System.Windows.Media.Animation.DoubleAnimation>设置为 50，其<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性将设置为 300。 因此，的<xref:System.Windows.FrameworkElement.Width%2A><xref:System.Windows.Shapes.Rectangle>动画从 50 到 300。  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>目标  
 仅设置<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性时，动画将从动画属性的基值或以前应用于同一属性的合成动画的输出到<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性指定的值进行。  
  
 （"组合动画"是指以前应用于使用<xref:System.Windows.Media.Animation.ClockState.Active>移交<xref:System.Windows.Media.Animation.ClockState.Filling>行为应用当前动画时仍然有效的同一属性的<xref:System.Windows.Media.Animation.HandoffBehavior.Compose>动画或动画。  
  
 下面的示例仅设置 到<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A><xref:System.Windows.Media.Animation.DoubleAnimation>300 的属性。 由于没有指定起始值，因此<xref:System.Windows.Media.Animation.DoubleAnimation>使用<xref:System.Windows.FrameworkElement.Width%2A>属性的基值 （100） 作为其起始值。 的<xref:System.Windows.FrameworkElement.Width%2A><xref:System.Windows.Shapes.Rectangle>动画从 100 到动画的目标值 300。  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>通过  
 仅设置动画<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>的属性时，动画将从要动画的属性的基值或合成动画的输出到该值和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性指定的值的总和。  
  
 下面的示例仅设置 到<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A><xref:System.Windows.Media.Animation.DoubleAnimation>300 的属性。 由于该示例未指定起始值，因此<xref:System.Windows.Media.Animation.DoubleAnimation>使用<xref:System.Windows.FrameworkElement.Width%2A>属性 100 的基值作为其起始值。 结束值是通过将动画 300<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>的值添加到其起始值 100： 400 来确定的。 因此，的<xref:System.Windows.FrameworkElement.Width%2A><xref:System.Windows.Shapes.Rectangle>动画从 100 到 400。  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 设置 动画<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>的<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>和 属性时，动画将从<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性指定的值到 由<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性的总和指定的值。  
  
 下面的示例将 属性<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A><xref:System.Windows.Media.Animation.DoubleAnimation>设置为 50，其<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性将设置为 300。 结束值是通过将动画 300<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>的值添加到其起始值 50：350 来确定的。 因此，的<xref:System.Windows.FrameworkElement.Width%2A><xref:System.Windows.Shapes.Rectangle>动画从 50 到 350。  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>源  
 仅指定动画<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>的值时，动画将从<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>属性指定的值、正在动画的属性的基值或合成动画的输出前进。  
  
 下面的示例仅设置 到<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A><xref:System.Windows.Media.Animation.DoubleAnimation>50 的属性。 由于没有指定结束值，因此<xref:System.Windows.Media.Animation.DoubleAnimation>使用<xref:System.Windows.FrameworkElement.Width%2A>属性 100 的基值作为其结束值。 的<xref:System.Windows.FrameworkElement.Width%2A><xref:System.Windows.Shapes.Rectangle>动画从 50 到<xref:System.Windows.FrameworkElement.Width%2A>属性的基值 100。  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 如果同时设置<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>动画和<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>动画的属性，则将忽略该<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>属性。  
  
<a name="otheranimationtypes"></a>
## <a name="other-animation-types"></a>其他动画类型  
 "从/到/按"动画不是[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供的唯一动画类型：它还提供关键帧动画和路径动画。  
  
- 关键帧动画沿使用关键帧描述的任意数量的目标值进行动画处理。 有关详细信息，请参阅[关键帧动画概述](key-frame-animations-overview.md)。  
  
- 路径动画从 生成输出值<xref:System.Windows.Media.PathGeometry>。 有关详细信息，请参阅[路径动画概述](path-animations-overview.md)。  
  
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
