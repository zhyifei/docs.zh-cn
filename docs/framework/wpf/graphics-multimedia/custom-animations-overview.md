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
ms.openlocfilehash: c5f315992e8ae37bc79602e6986d90e7af591fb2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186552"
---
# <a name="custom-animations-overview"></a>自定义动画概述
本主题介绍如何以及何时通过以下方法来扩展 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画系统：创建自定义关键帧、动画类或者使用每帧回叫来绕过它。  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>系统必备  
 若要了解本主题，用户应当熟悉 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供的不同动画类型。 有关详细信息，请参阅 From/To/By 动画概述、[关键帧动画概述](key-frame-animations-overview.md)和[路径动画概述](path-animations-overview.md)。  
  
 由于动画类从<xref:System.Windows.Freezable>类继承，因此应熟悉<xref:System.Windows.Freezable>对象以及如何从<xref:System.Windows.Freezable>继承。 有关详细信息，请参阅 [Freezable 对象概述](../advanced/freezable-objects-overview.md)。  
  
<a name="extendingtheanimationsystem"></a>
## <a name="extending-the-animation-system"></a>扩展动画系统  
 扩展 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画系统有多种方法，具体取决于要使用的内置功能的级别。  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画引擎中有三个主要的扩展点：  
  
- 通过从*\<类型>* KeyFrame 类之一（如<xref:System.Windows.Media.Animation.DoubleKeyFrame>）继承来创建自定义关键帧对象。 此方法使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画引擎的大部分内置功能。  
  
- 通过继承或<xref:System.Windows.Media.Animation.AnimationTimeline>从*\<类型>* 动画基础类之一创建自己的动画类。  
  
- 使用每帧回叫针对每个帧生成动画。 此方法完全绕过动画和计时系统。  
  
 下表介绍了扩展动画系统的一些方案。  
  
|要执行此操作...|使用此方法|  
|-------------------------|-----------------------|  
|自定义具有相应*\<类型>* 动画使用关键帧的类型的值之间的插值|创建自定义关键帧。 有关详细信息，请参阅[创建自定义关键帧](#createacustomkeyframe)部分。|  
|自定义的不仅仅是具有相应*\<类型>* 动画的类型的值之间的插值。|创建从*\<类型>* 动画基础类继承的自定义动画类，该类对应于要设置动画的类型。 有关详细信息，请参阅[创建自定义动画类](#createacustomanimationtype)部分。|  
|对没有对应 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画的类型进行动画处理|使用<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>或 创建从<xref:System.Windows.Media.Animation.AnimationTimeline>继承的类。 有关详细信息，请参阅[创建自定义动画类](#createacustomanimationtype)部分。|  
|对多个对象进行动画处理，这些对象带有按每个帧进行计算并基于最后一组对象交互的值|使用每帧回叫。 有关详细信息，请参阅[使用每帧回叫](#useperframecallback)部分。|  
  
<a name="createacustomkeyframe"></a>
## <a name="create-a-custom-key-frame"></a>创建自定义关键帧  
 创建自定义关键帧类是扩展动画系统的最简单方法。 当希望为关键帧动画使用不同的内插方法时，请使用此方法。  如[关键帧动画概述](key-frame-animations-overview.md)中所述，关键帧动画使用关键帧对象生成器输出值。 每个关键帧对象都执行三个功能：  
  
- 使用其<xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>属性指定目标值。  
  
- 指定应使用其<xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>属性达到该值的时间。  
  
- 通过实现 InterpolateValueCore 方法在上一个关键帧的值和它自己的值之间内插。  
  
 **实现说明**  
  
 派生自*\<类型>* KeyFrame 抽象类，并实现插值ValueCore方法。 InterpolateValueCore 方法返回关键帧的当前值。 它采用两个参数：上一个关键帧的值和范围是从 0 到 1 的进度值。 进度 0 表示关键帧刚刚启动，值 1 表示关键帧刚刚完成，应返回其<xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>属性指定的值。  
  
 由于*\<类型>* KeyFrame 类从<xref:System.Windows.Freezable>类继承，因此还必须重写<xref:System.Windows.Freezable.CreateInstanceCore%2A>内核才能返回类的新实例。 如果该类不使用依赖属性存储其数据，或者它在创建后需要额外初始化，则可能需要重写其他方法；有关详细信息，请参阅 [Freezable 对象概述](../advanced/freezable-objects-overview.md)。  
  
 创建自定义*\<类型>* KeyFrame 动画后，可以将该类型>动画使用关键帧*\<的类型*用于该类型。  
  
<a name="createacustomanimationtype"></a>
## <a name="create-a-custom-animation-class"></a>创建自定义动画类  
 创建自己的动画类型可以更好地控制对某个对象进行动画处理的方法。 有两种建议的方法可以创建自己的动画类型：可以从<xref:System.Windows.Media.Animation.AnimationTimeline>类派生*\<>* 动画基础类。 不建议从*\<"动画类型>"* 或*\<"动画>类型*>动画使用关键帧类派生。  
  
### <a name="derive-from-typeanimationbase"></a>从 \<Type>AnimationBase 派生  
 从*\<类型>* 动画基础类派生是创建新动画类型的最简单方法。 如果要为已具有相应*\<类型>* 动画基础类的类型创建新动画，请使用此方法。  
  
 **实现说明**  
  
 派生自*\<>* 动画类，并实现 GetCurrentValueCore 方法。 GetCurrentValueCore 方法返回动画的当前值。 它需要三个参数：建议的起始值、建议的结束值和 用于<xref:System.Windows.Media.Animation.AnimationClock>确定动画进度的 参数。  
  
 由于*\<类型>* 动画基础类从<xref:System.Windows.Freezable>类继承，因此还必须重写<xref:System.Windows.Freezable.CreateInstanceCore%2A>核心才能返回类的新实例。 如果该类不使用依赖属性存储其数据，或者它在创建后需要额外初始化，则可能需要重写其他方法；有关详细信息，请参阅 [Freezable 对象概述](../advanced/freezable-objects-overview.md)。  
  
 有关详细信息，请参阅要设置动画*\<的类型>* 动画基础类的 GetCurrentValueCore 方法文档。 有关示例，请参阅[自定义动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)  
  
 **替代方法**  
  
 如果只想更改动画值的插值方式，则考虑派生自*\<类型>* KeyFrame 类之一。 您创建的关键帧可与提供的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]相应*\<类型>* 动画使用关键帧一起使用。  
  
### <a name="derive-from-animationtimeline"></a>从 AnimationTimeline 派生  
 如果要为尚未<xref:System.Windows.Media.Animation.AnimationTimeline>具有匹配[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]动画的类型创建动画，或者希望创建未强类型类型的动画，则从类派生。  
  
 **实现说明**  
  
 派生自类<xref:System.Windows.Media.Animation.AnimationTimeline>并重写以下成员：  
  
- <xref:System.Windows.Freezable.CreateInstanceCore%2A>• 如果新类是具体的，则必须重写<xref:System.Windows.Freezable.CreateInstanceCore%2A>才能返回类的新实例。  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>• 重写此方法以返回动画的当前值。 它需要三个参数：默认原点值、默认目标值和<xref:System.Windows.Media.Animation.AnimationClock>。 使用<xref:System.Windows.Media.Animation.AnimationClock>获取动画的当前时间或进度。 可以选择是否使用默认的原始和目标值。  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>• 重写此属性以指示动画是否使用<xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>方法指定的默认目标值。  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>• 重写此属性以指示<xref:System.Type>动画生成的输出。  
  
 如果该类不使用依赖属性存储其数据，或者它在创建后需要额外初始化，则可能需要重写其他方法；有关详细信息，请参阅 [Freezable 对象概述](../advanced/freezable-objects-overview.md)。  
  
 推荐的范例（由 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画使用）是使用两个继承级别：  
  
1. 创建派生自<xref:System.Windows.Media.Animation.AnimationTimeline>的抽象*\<类型>* 动画基础类。 类应重写 方法<xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>。 它还应引入一种新的抽象方法 GetCurrentValueCore 和重写<xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>，以便验证默认原点值和默认目标值参数的类型，然后调用 GetCurrentValueCore。  
  
2. 创建从新*\<类型>* 动画基础类继承的另一个类，并重写<xref:System.Windows.Freezable.CreateInstanceCore%2A>方法、引入的 GetCurrentValueCore 方法和<xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>属性。  
  
 **替代方法**  
  
 如果要为没有相应"从/到/由"动画或关键帧动画的类型设置动画，请考虑使用<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>。 由于类型较弱，因此<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>可以为任何类型的值设置动画。 此方法的缺点是<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>仅支持离散插值。  
  
<a name="useperframecallback"></a>
## <a name="use-per-frame-callback"></a>使用每帧回叫  
 在需要完全绕过 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画系统时使用此方法。 此方法的一个方案是物理动画，其中的每个动画步都需要基于最后一组对象交互重新计算动画处理对象的新方向或位置。  
  
 **实现说明**  
  
 和本概述中所述的其他方法不同，要使用每帧回叫，无需创建自定义动画或关键帧类。  
  
 相反，您可以注册包含要<xref:System.Windows.Media.CompositionTarget.Rendering>设置动画的对象的对象的事件。 每帧调用一次此事件处理程序方法。 每次 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 将可视化树中的持久呈现数据封送到复合树时，都将调用事件处理程序方法。  
  
 在事件处理程序中，执行动画效果所需的任何计算，并设置要使用这些值进行动画处理的对象的属性。  
  
 要获取当前帧的表示时间，<xref:System.EventArgs>与此事件关联的可以强制转换为<xref:System.Windows.Media.RenderingEventArgs>，该<xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A>属性可用于获取当前帧的渲染时间。  
  
 有关详细信息，请参阅 <xref:System.Windows.Media.CompositionTarget.Rendering> 页。  
  
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
