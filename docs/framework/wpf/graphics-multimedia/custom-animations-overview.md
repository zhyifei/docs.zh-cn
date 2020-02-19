---
title: 自定义动画概述
ms.date: 03/30/2017
helpviewer_keywords:
- custom classes [WPF], animation
- key frames [WPF], custom
- custom key frames [WPF]
- animation [WPF], custom classes
- custom animation classes [WPF]
ms.assetid: 9be69d50-3384-4938-886f-08ce00e4a7a6
ms.openlocfilehash: 5a9ca51b87f73a24b90d0bd843ee306f8a1b970a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453086"
---
# <a name="custom-animations-overview"></a>自定义动画概述
本主题介绍如何以及何时通过以下方法来扩展 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画系统：创建自定义关键帧、动画类或者使用每帧回叫来绕过它。  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>先决条件  
 若要了解本主题，用户应当熟悉 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供的不同动画类型。 有关详细信息，请参阅 From/To/By 动画概述、[关键帧动画概述](key-frame-animations-overview.md)和[路径动画概述](path-animations-overview.md)。  
  
 由于动画类从 <xref:System.Windows.Freezable> 类继承，因此您应该熟悉 <xref:System.Windows.Freezable> 对象以及如何从 <xref:System.Windows.Freezable>继承。 有关详细信息，请参阅 [Freezable 对象概述](../advanced/freezable-objects-overview.md)。  
  
<a name="extendingtheanimationsystem"></a>   
## <a name="extending-the-animation-system"></a>扩展动画系统  
 扩展 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画系统有多种方法，具体取决于要使用的内置功能的级别。  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画引擎中有三个主要的扩展点：  
  
- 通过从某个 *\<类型 >* 关键帧类（如 <xref:System.Windows.Media.Animation.DoubleKeyFrame>）继承来创建自定义关键帧对象。 此方法使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画引擎的大部分内置功能。  
  
- 通过从 <xref:System.Windows.Media.Animation.AnimationTimeline> 或 *\<类型 >* AnimationBase 类之一继承来创建自己的动画类。  
  
- 使用每帧回叫针对每个帧生成动画。 此方法完全绕过动画和计时系统。  
  
 下表介绍了扩展动画系统的一些方案。  
  
|要执行此操作...|使用此方法|  
|-------------------------|-----------------------|  
|自定义具有对应 *\<Type>* AnimationUsingKeyFrames 的类型值之间的内插|创建自定义关键帧。 有关详细信息，请参阅[创建自定义关键帧](#createacustomkeyframe)部分。|  
|除了自定义具有对应 *\<Type>* Animation 的类型值之间的内插外，还要自定义其他内容。|创建自定义动画类，该类继承自对应于要进行动画处理的类型的 *\<Type>* AnimationBase 类。 有关详细信息，请参阅[创建自定义动画类](#createacustomanimationtype)部分。|  
|对没有对应 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画的类型进行动画处理|使用 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 或创建从 <xref:System.Windows.Media.Animation.AnimationTimeline>继承的类。 有关详细信息，请参阅[创建自定义动画类](#createacustomanimationtype)部分。|  
|对多个对象进行动画处理，这些对象带有按每个帧进行计算并基于最后一组对象交互的值|使用每帧回叫。 有关详细信息，请参阅[使用每帧回叫](#useperframecallback)部分。|  
  
<a name="createacustomkeyframe"></a>   
## <a name="create-a-custom-key-frame"></a>创建自定义关键帧  
 创建自定义关键帧类是扩展动画系统的最简单方法。 当希望为关键帧动画使用不同的内插方法时，请使用此方法。  如[关键帧动画概述](key-frame-animations-overview.md)中所述，关键帧动画使用关键帧对象生成器输出值。 每个关键帧对象都执行三个功能：  
  
- 使用其 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 属性指定目标值。  
  
- 指定使用其 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> 属性访问该值的时间。  
  
- 通过实现 InterpolateValueCore 方法在上一个关键帧的值和它自己的值之间内插。  
  
 **实现说明**  
  
 从 *\<Type>* KeyFrame 抽象类派生，并实现 InterpolateValueCore 方法。 InterpolateValueCore 方法返回关键帧的当前值。 它采用两个参数：上一个关键帧的值和范围是从 0 到 1 的进度值。 进度0指示关键帧刚开始，值为1指示关键帧刚完成并且应返回由其 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 属性指定的值。  
  
 由于 > 关键帧类 *\<类型*继承自 <xref:System.Windows.Freezable> 类，因此还必须重写 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 核心才能返回类的新实例。 如果该类不使用依赖属性存储其数据，或者它在创建后需要额外初始化，则可能需要重写其他方法；有关详细信息，请参阅 [Freezable 对象概述](../advanced/freezable-objects-overview.md)。  
  
 创建自定义 *\<Type>* KeyFrame 动画后，可以将其与该类型的 *\<Type>* AnimationUsingKeyFrames 结合使用。  
  
<a name="createacustomanimationtype"></a>   
## <a name="create-a-custom-animation-class"></a>创建自定义动画类  
 创建自己的动画类型可以更好地控制对某个对象进行动画处理的方法。 可通过两种方法创建自己的动画类型：可从 <xref:System.Windows.Media.Animation.AnimationTimeline> 类或 *\<类型 >* AnimationBase 类派生。 不建议从 *\<Type>* Animation 或 *\<Type>* AnimationUsingKeyFrames 类派生。  
  
### <a name="derive-from-typeanimationbase"></a>从 \<Type>AnimationBase 派生  
 从 *\<Type>* AnimationBase 类派生是创建新动画类型的最简单方法。 要为已经具有对应 *\<Type>* AnimationBase 类的类型创建新动画时，请使用此方法。  
  
 **实现说明**  
  
 从 *\<Type>* Animation 类派生并实现 GetCurrentValueCore 方法。 GetCurrentValueCore 方法返回动画的当前值。 它采用三个参数：一个建议的起始值、一个建议的结束值和一个用于确定动画进度的 <xref:System.Windows.Media.Animation.AnimationClock>。  
  
 由于 *\<类型 >* AnimationBase 类继承自 <xref:System.Windows.Freezable> 类，因此还必须重写 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 核心才能返回类的新实例。 如果该类不使用依赖属性存储其数据，或者它在创建后需要额外初始化，则可能需要重写其他方法；有关详细信息，请参阅 [Freezable 对象概述](../advanced/freezable-objects-overview.md)。  
  
 有关详细信息，请参阅要进行动画处理的类型的 *\<Type>* AnimationBase 类的 GetCurrentValueCore 方法文档。 有关示例，请参阅[自定义动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)  
  
 **替代方法**  
  
 如果只需更改动画值的内插方式，请考虑从某个 *\<Type>* KeyFrame 类派生。 可以将所创建的关键帧与  *提供的对应 \<* Type>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]AnimationUsingKeyFrames 结合使用。  
  
### <a name="derive-from-animationtimeline"></a>从 AnimationTimeline 派生  
 如果要为尚未与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画匹配的类型创建动画，或要创建不是强类型的动画，请从 <xref:System.Windows.Media.Animation.AnimationTimeline> 类派生。  
  
 **实现说明**  
  
 从 <xref:System.Windows.Media.Animation.AnimationTimeline> 类派生并重写以下成员：  
  
- <xref:System.Windows.Freezable.CreateInstanceCore%2A> –如果新类是具体类，则必须重写 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 才能返回类的新实例。  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> –重写此方法以返回动画的当前值。 它使用三个参数：默认的原始值、默认目标值和 <xref:System.Windows.Media.Animation.AnimationClock>。 使用 <xref:System.Windows.Media.Animation.AnimationClock> 获取动画的当前时间或进度。 可以选择是否使用默认的原始和目标值。  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> –重写此属性，以指示动画是否使用 <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> 方法指定的默认目标值。  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> –重写此属性，以指示动画生成的输出的 <xref:System.Type>。  
  
 如果该类不使用依赖属性存储其数据，或者它在创建后需要额外初始化，则可能需要重写其他方法；有关详细信息，请参阅 [Freezable 对象概述](../advanced/freezable-objects-overview.md)。  
  
 推荐的范例（由 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画使用）是使用两个继承级别：  
  
1. 创建从 <xref:System.Windows.Media.Animation.AnimationTimeline>派生的 > AnimationBase 类的抽象 *\<类型*。 此类应重写 <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> 方法。 它还应引入一个新的抽象方法 GetCurrentValueCore，并覆盖 <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> 以便验证默认原始值和默认目标值参数的类型，然后调用 GetCurrentValueCore。  
  
2. 创建另一个从新 *\<类型*继承的类 > AnimationBase 类，并重写 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 方法、引入的 GetCurrentValueCore 方法和 <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> 属性。  
  
 **替代方法**  
  
 如果要对没有对应的 From/To/By 动画或关键帧动画的类型进行动画处理，请考虑使用 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>。 由于它是弱类型，因此 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 可以对任何类型的值进行动画处理。 此方法的缺点是 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 仅支持离散内插。  
  
<a name="useperframecallback"></a>   
## <a name="use-per-frame-callback"></a>使用每帧回叫  
 如果需要完全绕过 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画系统，可以使用此方法。 此方法的一个方案是物理动画，其中的每个动画步都需要基于最后一组对象交互重新计算动画处理对象的新方向或位置。  
  
 **实现说明**  
  
 和本概述中所述的其他方法不同，要使用每帧回叫，无需创建自定义动画或关键帧类。  
  
 而是注册对象的 <xref:System.Windows.Media.CompositionTarget.Rendering> 事件，该对象包含要进行动画处理的对象。 每帧会调用一次此事件处理程序方法。 每次 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 将可视化树中的持久呈现数据封送到复合树时，都将调用事件处理程序方法。  
  
 在事件处理程序中，执行动画效果所需的任何计算，并设置要使用这些值进行动画处理的对象的属性。  
  
 若要获取当前帧的显示时间，可以将与此事件相关联的 <xref:System.EventArgs> 转换为 <xref:System.Windows.Media.RenderingEventArgs>，这将提供可用于获取当前帧呈现时间的 <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> 属性。  
  
 有关详细信息，请参阅 "<xref:System.Windows.Media.CompositionTarget.Rendering>" 页。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.IKeyFrame>
- [属性动画技术概述](property-animation-techniques-overview.md)
- [Freezable 对象概述](../advanced/freezable-objects-overview.md)
- [关键帧动画概述](key-frame-animations-overview.md)
- [路径动画概述](path-animations-overview.md)
- [动画概述](animation-overview.md)
- [动画和计时系统概述](animation-and-timing-system-overview.md)
- [自定义动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)
