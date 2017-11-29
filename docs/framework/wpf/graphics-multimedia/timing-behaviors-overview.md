---
title: "计时行为概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ac6671033a439051b062ddae70649a63bacd4979
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="timing-behaviors-overview"></a>计时行为概述
本主题介绍动画和其他的计时行为<xref:System.Windows.Media.Animation.Timeline>对象。  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>先决条件  
 若要了解本主题，应熟悉基本动画功能。 有关详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。  
  
<a name="timelinetypes"></a>   
## <a name="timeline-types"></a>时间线类型  
 A<xref:System.Windows.Media.Animation.Timeline>表示的时间段。 它提供的属性让你可以指定该时间段的长度、开始时间、重复次数、该时间段内时间进度的快慢等。  
  
 从时间线类继承的类可提供附加功能，例如动画和媒体播放。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供了以下<xref:System.Windows.Media.Animation.Timeline>类型。  
  
|时间线类型|描述|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|抽象基类<xref:System.Windows.Media.Animation.Timeline>生成属性进行动画处理的输出值的对象。|  
|<xref:System.Windows.Media.MediaTimeline>|从媒体文件生成输出。|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|一种<xref:System.Windows.Media.Animation.TimelineGroup>该组和控件的子级<xref:System.Windows.Media.Animation.Timeline>对象。|  
|<xref:System.Windows.Media.Animation.Storyboard>|一种<xref:System.Windows.Media.Animation.ParallelTimeline>，它提供有关包含的时间线对象的目标信息。|  
|<xref:System.Windows.Media.Animation.Timeline>|定义计时行为的抽象基类。|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|抽象类<xref:System.Windows.Media.Animation.Timeline>可以包含其他对象<xref:System.Windows.Media.Animation.Timeline>对象。|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## <a name="properties-that-control-the-length-of-a-timeline"></a>用于控制时间线长度的属性  
 A<xref:System.Windows.Media.Animation.Timeline>表示的时间段和时间线的长度可以描述不同的方式。 下表定义了几个用于描述时间线长度的术语。  
  
|术语|描述|属性||||  
|----------|-----------------|----------------|-|-|-|  
|简单持续时间|时间线向前迭代一次所需的时间长度。|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|一次重复|时间线向前播放一次，如果它采用的时间长度<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性为 true 时，倒退一次。|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|活动期|总时间所需时间线，以完成由指定的所有重复其<xref:System.Windows.Media.Animation.RepeatBehavior>属性。|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### <a name="the-duration-property"></a>Duration 属性  
 如前文所述，时间线表示时间段。 段的长度由时间线的<xref:System.Windows.Media.Animation.Timeline.Duration%2A>。 当时间线到达其持续时间的终点时，就会停止播放。 如果时间线具有子时间线，这些子时间线也会停止播放。 对于动画，<xref:System.Windows.Media.Animation.Timeline.Duration%2A>指定动画的时间转换从其起始值为其结束的值。 时间线的持续时间有时称为其*简单持续时间*、 来区分一次迭代的持续时间和动画播放包括重复的时间的总长度。 你可以指定一个持续时间，使用有限的时间值或特殊值<xref:System.Windows.Duration.Automatic%2A>或<xref:System.Windows.Duration.Forever%2A>。 动画的持续时间应解析为<xref:System.Windows.Duration.TimeSpan%2A>值，因此它可以转换值之间。  
  
 下面的示例演示<xref:System.Windows.Media.Animation.DoubleAnimation>与<xref:System.Windows.Media.Animation.Timeline.Duration%2A>5 秒。  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 容器时间线，如<xref:System.Windows.Media.Animation.Storyboard>和<xref:System.Windows.Media.Animation.ParallelTimeline>，默认持续时间为<xref:System.Windows.Duration.Automatic%2A>，这意味着它们将自动结束时其最后一个子级停止播放。 下面的示例演示<xref:System.Windows.Media.Animation.Storyboard>其<xref:System.Windows.Media.Animation.Timeline.Duration%2A>可解析为五秒，所有子所都用的时间长度<xref:System.Windows.Media.Animation.DoubleAnimation>对象完成。  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 通过设置<xref:System.Windows.Media.Animation.Timeline.Duration%2A>到容器时间线<xref:System.Windows.Duration.TimeSpan%2A>值，你可以强制播放长于或短于其子<xref:System.Windows.Media.Animation.Timeline>对象播放。 如果你设置<xref:System.Windows.Media.Animation.Timeline.Duration%2A>为小于容器时间线的子的长度值<xref:System.Windows.Media.Animation.Timeline>对象、 子<xref:System.Windows.Media.Animation.Timeline>对象也会停止播放时容器时间线。 下面的示例设置<xref:System.Windows.Media.Animation.Timeline.Duration%2A>的<xref:System.Windows.Media.Animation.Storyboard>从前面的示例中为 3 秒。 因此，第一个<xref:System.Windows.Media.Animation.DoubleAnimation>停止后三秒，当它具有经过动画处理到 60 目标矩形的宽度的进展情况。  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>   
### <a name="the-repeatbehavior-property"></a>RepeatBehavior 属性  
 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性<xref:System.Windows.Media.Animation.Timeline>控制重复其简单持续时间的次数。 使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性，你可以指定在时间线播放的次数 (迭代<xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>) 或它应播放的时间的总长度 (重复<xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>)。 无论是哪一种情况，动画都将从头到尾运行很多次，直到完成要求的次数或经历完所需的一段时间。 默认情况下，时间线具有的迭代次数为`1.0`，这意味着它们播放一次，根本不进行重复。  
  
 下面的示例使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性以使<xref:System.Windows.Media.Animation.DoubleAnimation>播放两次其简单持续时间内通过指定的迭代次数。  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 下一个示例使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性以使<xref:System.Windows.Media.Animation.DoubleAnimation>播放半其简单持续时间。  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 如果你设置<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性<xref:System.Windows.Media.Animation.Timeline>到<xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>、<xref:System.Windows.Media.Animation.Timeline>重复，直到停止以交互方式或计时系统。 下面的示例使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性以使<xref:System.Windows.Media.Animation.DoubleAnimation>无限期地播放。  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 有关其他示例，请参阅[重复动画](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)。  
  
<a name="autoreverseproperty"></a>   
### <a name="the-autoreverse-property"></a>AutoReverse 属性  
 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性指定是否<xref:System.Windows.Media.Animation.Timeline>末尾的每个向前迭代倒退。 下面的示例将设置为<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性<xref:System.Windows.Media.Animation.DoubleAnimation>到`true`; 因此，它进行动画处理，从 0 到 100，，然后从 100 到零。 它的总播放时长为 10 秒。  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 当你使用<xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>要指定的值<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>的<xref:System.Windows.Media.Animation.Timeline>和<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性，<xref:System.Windows.Media.Animation.Timeline>是`true`，一次重复由一个向前迭代后跟一个向后迭代。  下面的示例设置<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>的<xref:System.Windows.Media.Animation.DoubleAnimation>到前面的示例从<xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>两个。 因此，<xref:System.Windows.Media.Animation.DoubleAnimation>播放了 20 秒： 转发为五秒，向后的 5 秒向前 5 秒试，然后再向后的五秒。  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 如果容器时间线具有子<xref:System.Windows.Media.Animation.Timeline>对象，它们反向时容器时间线。 有关其他示例，请参阅[指定是否时间线会自动颠倒](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)。  
  
<a name="timelinebegin"></a>   
## <a name="the-begintime-property"></a>BeginTime 属性  
 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>属性使您能够指定时间线的启动时。  时间线的开始时间相对于其父时间线。 如果开始时间为零秒，则表示其父时间线开始后，该时间线立即开始；如果开始时间为其他值，会在父时间线和子时间线的开始播放时间之间产生时间偏差。 例如，如果开始时间为两秒，则表示在其父时间线到达两秒后，该时间线才开始播放。 默认情况下，所有时间线的开始时间都为零秒。 您还可以设置时间线的开始时间`null`，这样将无法启动时间线。 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，指定 null 使用[X:null 标记扩展](../../../../docs/framework/xaml-services/x-null-markup-extension.md)。  
  
 请注意，开始时间不应用时间线重复时由于每次其<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>设置。 如果你打算创建动画的<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>为 10 秒和<xref:System.Windows.Media.Animation.RepeatBehavior>的<xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>，将有 10 秒延迟之前动画播放第一次，但不是能为每个连续的重复。 但是，如果动画的父时间线重新开始或重复，则会延迟 10 秒。  
  
 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>属性是用于错开时间线。 下面的示例创建<xref:System.Windows.Media.Animation.Storyboard>包含两个子<xref:System.Windows.Media.Animation.DoubleAnimation>对象。 第一个动画<xref:System.Windows.Media.Animation.Timeline.Duration%2A>5 秒，第二个<xref:System.Windows.Media.Animation.Timeline.Duration%2A>3 秒。 该示例设置<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>第二个<xref:System.Windows.Media.Animation.DoubleAnimation>为 5 秒，因此它开始播放后第一个<xref:System.Windows.Media.Animation.DoubleAnimation>结束。  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>   
## <a name="the-fillbehavior-property"></a>FillBehavior 属性  
 当<xref:System.Windows.Media.Animation.Timeline>到达其总的活动持续时间，末尾<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性指定它是停止还是持有其最后一个值。 动画的<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>的<xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>"保存"其输出值： 正在进行动画处理的属性将保留动画的最后一个值。 值为<xref:System.Windows.Media.Animation.FillBehavior.Stop>使动画停止结束之后影响其目标属性。  
  
 下面的示例创建<xref:System.Windows.Media.Animation.Storyboard>包含两个子<xref:System.Windows.Media.Animation.DoubleAnimation>对象。 同时<xref:System.Windows.Media.Animation.DoubleAnimation>对象进行动画处理<xref:System.Windows.FrameworkElement.Width%2A>的<xref:System.Windows.Shapes.Rectangle>从 0 到 100。 <xref:System.Windows.Shapes.Rectangle>元素具有非动画<xref:System.Windows.FrameworkElement.Width%2A>500 [设备无关的像素] 的值。  
  
-   <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性的第一个<xref:System.Windows.Media.Animation.DoubleAnimation>设置为<xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>，默认值。 因此，矩形的宽度后保持为 100<xref:System.Windows.Media.Animation.DoubleAnimation>结束。  
  
-   <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>第二个属性<xref:System.Windows.Media.Animation.DoubleAnimation>设置为<xref:System.Windows.Media.Animation.FillBehavior.Stop>。 因此，<xref:System.Windows.FrameworkElement.Width%2A>第二个<xref:System.Windows.Shapes.Rectangle>后还原为 500<xref:System.Windows.Media.Animation.DoubleAnimation>结束。  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>   
## <a name="properties-that-control-the-speed-of-a-timeline"></a>用于控制时间线速度的属性  
 <xref:System.Windows.Media.Animation.Timeline>类提供三个属性用于指定其速度：  
  
-   <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>-指定该速率，相对于其父级，在该时间转换为<xref:System.Windows.Media.Animation.Timeline>。 大于 1 的值增加的速度<xref:System.Windows.Media.Animation.Timeline>及其子<xref:System.Windows.Media.Animation.Timeline>对象; 0 和 1 之间的值速度下降。 一个值，该值指示<xref:System.Windows.Media.Animation.Timeline>时为其父级的相同速率进行。 <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>容器时间线的设置会影响其所有子<xref:System.Windows.Media.Animation.Timeline>以及对象。  
  
-   <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>– 指定的百分比<xref:System.Windows.Media.Animation.Timeline.Duration%2A>以时间线所用的加速。 有关示例，请参阅[如何： 加速或减速动画](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md)。 
  
-   <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>-指定的百分比<xref:System.Windows.Media.Animation.Timeline.Duration%2A>以时间线所用的减速。 有关示例，请参阅[如何： 加速或减速动画](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md)。  
  
## <a name="see-also"></a>另请参阅  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [动画和计时系统概述](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [计时事件概述](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)  
 [操作说明主题](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [动画计时行为示例](http://go.microsoft.com/fwlink/?LinkID=159970)
