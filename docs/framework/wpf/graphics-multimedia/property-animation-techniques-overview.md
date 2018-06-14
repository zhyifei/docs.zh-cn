---
title: 属性动画技术概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- animation [WPF], properties [WPF], methods for
- properties [WPF], methods for animating
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
ms.openlocfilehash: 032a26788b9097461cb2270e251ca80c56c1c336
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566738"
---
# <a name="property-animation-techniques-overview"></a>属性动画技术概述
本主题介绍了处理动画属性的不同方法：情节提要、本地动画、时钟和基于帧的动画。  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>系统必备  
 若要了解本主题，应熟悉[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)中描述的基本动画功能。  
  
<a name="summary"></a>   
## <a name="different-ways-to-animate"></a>动画处理的不同方法  
 由于动画处理属性存在多种不同的方案，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供几种动画处理属性的方法。  
  
 对于每种方法，下表指明了每种方法是否可以基于实例在样式、控件模板或数据模板中使用；是否可以在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中使用；以及该方法是否能够以交互方式控制动画。  “基于实例”是指直接将动画或情节提要应用于对象实例（而不是在样式、控件模板或数据模板中应用）的技术。  
  
|动画技术|方案|支持 XAML|可以交互方式控制|  
|-------------------------|---------------|-------------------|--------------------------------|  
|情节提要动画|每个实例<xref:System.Windows.Style>， <xref:System.Windows.Controls.ControlTemplate>， <xref:System.Windows.DataTemplate>|是|是|  
|本地动画|基于实例|否|否|  
|时钟动画|基于实例|否|是|  
|基于帧的动画|基于实例|否|不可用|  
  
<a name="storyboard_animations"></a>   
## <a name="storyboard-animations"></a>情节提要动画  
 使用<xref:System.Windows.Media.Animation.Storyboard>如果想要定义并应用在动画[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]、 以交互方式控制后它们启动、 创建动画，一个复杂树或中创建动画的动画<xref:System.Windows.Style>，<xref:System.Windows.Controls.ControlTemplate>或<xref:System.Windows.DataTemplate>。 若要进行动画处理的对象<xref:System.Windows.Media.Animation.Storyboard>，它必须是<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>，或它必须用于设置<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>。 有关详细信息，请参阅[情节提要概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)。  
  
 A<xref:System.Windows.Media.Animation.Storyboard>是一种特殊类型的容器<xref:System.Windows.Media.Animation.Timeline>提供为它包含的动画的目标信息。 使用进行动画处理<xref:System.Windows.Media.Animation.Storyboard>，完成以下三个步骤。  
  
1.  声明<xref:System.Windows.Media.Animation.Storyboard>和一个或多个动画。  
  
2.  使用<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>和<xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A>附加属性以指定目标对象和每个动画的属性。  
  
3.  （仅代码）定义<xref:System.Windows.NameScope>为<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>。 注册的使用，进行动画处理的对象名称<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>。  
  
4.  开始<xref:System.Windows.Media.Animation.Storyboard>。  
  
 从开始<xref:System.Windows.Media.Animation.Storyboard>将动画应用到它们进行动画处理的属性并将其启动。 若要开始使用两种方式<xref:System.Windows.Media.Animation.Storyboard>： 你可以使用<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>方法提供的<xref:System.Windows.Media.Animation.Storyboard>类，也可以使用<xref:System.Windows.Media.Animation.BeginStoryboard>操作。 要进行动画处理中的唯一方法[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]是使用<xref:System.Windows.Media.Animation.BeginStoryboard>操作。 A<xref:System.Windows.Media.Animation.BeginStoryboard>操作可在<xref:System.Windows.EventTrigger>，属性<xref:System.Windows.Trigger>，或<xref:System.Windows.DataTrigger>。  
  
 下表显示不同的位置其中每个<xref:System.Windows.Media.Animation.Storyboard>开始支持技术： 每个实例、 样式、 控件模板和数据模板。  
  
|开始情节提要所使用的技术|基于实例|样式|控件模板|数据模板|示例|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 和 <xref:System.Windows.EventTrigger>|是|是|是|是|[使用情节提要对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 和属性 <xref:System.Windows.Trigger>|否|是|是|是|[在属性值更改时触发动画](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 和 <xref:System.Windows.DataTrigger>|否|是|是|是|[如何：在数据更改时触发动画](http://msdn.microsoft.com/library/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 方法|是|No|否|否|[使用情节提要对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 有关详细信息<xref:System.Windows.Media.Animation.Storyboard>对象，请参阅[情节提要概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)。  
  
## <a name="local-animations"></a>本地动画  
 本地动画提供要进行动画处理的依赖项属性的任何一种简便方式<xref:System.Windows.Media.Animation.Animatable>对象。 如果想要将单一动画应用到属性中，可以使用本地动画，并且动画启动后不需要以交互方式控制动画。 与不同<xref:System.Windows.Media.Animation.Storyboard>动画，本地动画可以动态显示不与关联的对象<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>。 你还不必定义<xref:System.Windows.NameScope>此类型的动画。  
  
 本地动画可能仅在代码中使用，无法在样式、控件模板或数据模板中定义。 本地动画启动后，无法以交互方式控制。  
  
 若要使用本地动画进行动画处理，应完成以下步骤。  
  
1.  创建<xref:System.Windows.Media.Animation.AnimationTimeline>对象。  
  
2.  使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>你想要进行动画处理，将该对象的方法<xref:System.Windows.Media.Animation.AnimationTimeline>到你指定的属性。  
  
 下面的示例演示如何进行动画处理的宽度和背景颜色<xref:System.Windows.Controls.Button>。  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## <a name="clock-animations"></a>时钟动画  
 使用<xref:System.Windows.Media.MediaPlayer.Clock%2A>对象时要进行动画处理，而无需使用<xref:System.Windows.Media.Animation.Storyboard>并且你想要创建复杂的计时树或启动后启动为交互式控制动画。 可以使用时钟对象进行动画处理的任何依赖项属性<xref:System.Windows.Media.Animation.Animatable>对象。  
  
 不能使用<xref:System.Windows.Media.Animation.Clock>对象直接动画样式、 控制模板或数据模板。 (动画和计时系统确实使用<xref:System.Windows.Media.Animation.Clock>对象要进行动画处理中样式，控件模板，并且数据模板，但它必须创建这些<xref:System.Windows.Media.Animation.Clock>对象为你从<xref:System.Windows.Media.Animation.Storyboard>。 有关之间的关系的详细信息<xref:System.Windows.Media.Animation.Storyboard>对象和<xref:System.Windows.Media.Animation.Clock>对象，请参阅[动画和计时系统概述](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)。)  
  
 将单个<xref:System.Windows.Media.Animation.Clock>给某个属性，完成以下步骤。  
  
1.  创建<xref:System.Windows.Media.Animation.AnimationTimeline>对象。  
  
2.  使用<xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A>方法<xref:System.Windows.Media.Animation.AnimationTimeline>创建<xref:System.Windows.Media.Animation.AnimationClock>。  
  
3.  使用<xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A>你想要进行动画处理，将该对象的方法<xref:System.Windows.Media.Animation.AnimationClock>到你指定的属性。  
  
 下面的示例演示如何创建<xref:System.Windows.Media.Animation.AnimationClock>并将其应用到两个类似的属性。  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 如果想要创建一个计时树并用其处理动画属性，应完成以下几个步骤。  
  
1.  使用<xref:System.Windows.Media.Animation.ParallelTimeline>和<xref:System.Windows.Media.Animation.AnimationTimeline>对象以创建计时树。  
  
2.  使用<xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A>根的<xref:System.Windows.Media.Animation.ParallelTimeline>创建<xref:System.Windows.Media.Animation.ClockGroup>。  
  
3.  循环访问<xref:System.Windows.Media.Animation.ClockGroup.Children%2A>的<xref:System.Windows.Media.Animation.ClockGroup>并应用其子<xref:System.Windows.Media.Animation.Clock>对象。 每个<xref:System.Windows.Media.Animation.AnimationClock>子级，使用<xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A>你想要进行动画处理，将该对象的方法<xref:System.Windows.Media.Animation.AnimationClock>到你指定的属性  
  
 有关时钟对象的详细信息，请参阅[动画和计时系统概述](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)。  
  
## <a name="per-frame-animation-bypass-the-animation-and-timing-system"></a>基于帧的动画：绕过动画和计时系统  
 如果需要完全绕过 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 动画系统，可以使用此方法。 此方法的一个方案是物理动画，其中的每个动画步骤都要求基于最后一组对象交互来重新计算。  
  
 基于帧的动画无法在样式、控件模板或数据模板内定义。  
  
 要进行动画处理请逐个框架，因此你注册<xref:System.Windows.Media.CompositionTarget.Rendering>包含你想要进行动画处理的对象的对象的事件。 每帧会调用一次此事件处理程序方法。 每次 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 将可视化树中的持久呈现数据封送到复合树时，都将调用事件处理程序方法。  
  
 在事件处理程序中，执行动画效果所需的任何计算，并设置想要使用这些值进行动画处理的对象的属性。  
  
 若要获取当前帧，表示时间<xref:System.EventArgs>关联与此事件可以转换为<xref:System.Windows.Media.RenderingEventArgs>，它提供的信息<xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A>属性，可用于获取当前帧的呈现时间。  
  
 有关详细信息，请参阅<xref:System.Windows.Media.CompositionTarget.Rendering>页。  
  
## <a name="see-also"></a>请参阅  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [演示图板概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [动画和计时系统概述](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [依赖项属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
