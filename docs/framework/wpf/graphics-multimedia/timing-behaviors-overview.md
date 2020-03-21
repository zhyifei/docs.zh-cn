---
title: 计时行为概述
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: 3bb42ddd991d3ae1221cc794afdd4aafc74a6046
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145392"
---
# <a name="timing-behaviors-overview"></a>计时行为概述
本主题介绍动画和其他<xref:System.Windows.Media.Animation.Timeline>对象的计时行为。  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>系统必备  
 若要了解本主题，应熟悉基本动画功能。 有关详细信息，请参阅[动画概述](animation-overview.md)。  
  
<a name="timelinetypes"></a>
## <a name="timeline-types"></a>时间线类型  
 A<xref:System.Windows.Media.Animation.Timeline>表示时间段。 它提供的属性让你可以指定该时间段的长度、开始时间、重复次数、该时间段内时间进度的快慢等。  
  
 从时间线类继承的类可提供附加功能，例如动画和媒体播放。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供了以下<xref:System.Windows.Media.Animation.Timeline>类型。  
  
|时间线类型|说明|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|为属性生成输出<xref:System.Windows.Media.Animation.Timeline>值的对象的抽象基类。|  
|<xref:System.Windows.Media.MediaTimeline>|从媒体文件生成输出。|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.TimelineGroup>该组和控制子<xref:System.Windows.Media.Animation.Timeline>对象的一种类型。|  
|<xref:System.Windows.Media.Animation.Storyboard>|提供<xref:System.Windows.Media.Animation.ParallelTimeline>其包含的时间线对象的定位信息的类型。|  
|<xref:System.Windows.Media.Animation.Timeline>|定义计时行为的抽象基类。|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|可以包含其他<xref:System.Windows.Media.Animation.Timeline><xref:System.Windows.Media.Animation.Timeline>对象的对象的抽象类。|  
  
<a name="propertiesthatcontroltimelinelength"></a>
## <a name="properties-that-control-the-length-of-a-timeline"></a>用于控制时间线长度的属性  
 表示<xref:System.Windows.Media.Animation.Timeline>时间段，可以以不同的方式描述时间线的长度。 下表定义了几个用于描述时间线长度的术语。  
  
|术语|说明|属性||||  
|----------|-----------------|----------------|-|-|-|  
|简单持续时间|时间线向前迭代一次所需的时间长度。|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|一次重复|时间线向前播放一次所需的时间长度，如果<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>属性为 true，则向后播放一次。|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|活动期|时间线完成其<xref:System.Windows.Media.Animation.RepeatBehavior>属性指定的所有重复所需的时间长度。|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>
### <a name="the-duration-property"></a>Duration 属性  
 如前文所述，时间线表示时间段。 该段的长度由时间线的<xref:System.Windows.Media.Animation.Timeline.Duration%2A>确定。 当时间线到达其持续时间的终点时，就会停止播放。 如果时间线具有子时间线，这些子时间线也会停止播放。 在动画的情况下， 指定<xref:System.Windows.Media.Animation.Timeline.Duration%2A>动画从起始值过渡到其结束值所需的时间。 时间线的持续时间有时称为*其简单持续时间*，以区分单个迭代的持续时间和动画播放的总时间长度（包括重复）。 可以使用有限时间值或特殊值<xref:System.Windows.Duration.Automatic%2A>或<xref:System.Windows.Duration.Forever%2A>指定持续时间。 动画的持续时间应解析为<xref:System.Windows.Duration.TimeSpan%2A>值，以便它可以在值之间转换。  
  
 下面的示例显示 a<xref:System.Windows.Media.Animation.DoubleAnimation><xref:System.Windows.Media.Animation.Timeline.Duration%2A>的五秒。  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 容器时间线（如<xref:System.Windows.Media.Animation.Storyboard>和<xref:System.Windows.Media.Animation.ParallelTimeline>）的默认持续时间为<xref:System.Windows.Duration.Automatic%2A>，这意味着它们在最后一个子级停止播放时会自动结束。 下面的示例显示其<xref:System.Windows.Media.Animation.Storyboard><xref:System.Windows.Media.Animation.Timeline.Duration%2A>解析为五秒的 a，即完成其所有子<xref:System.Windows.Media.Animation.DoubleAnimation>对象所需的时间长度。  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>通过将容器时间线设置为<xref:System.Windows.Duration.TimeSpan%2A>值，可以强制播放比其子<xref:System.Windows.Media.Animation.Timeline>对象播放的时间更长或短。 如果将 设置为<xref:System.Windows.Media.Animation.Timeline.Duration%2A>小于容器时间线子<xref:System.Windows.Media.Animation.Timeline>对象长度的值，则子<xref:System.Windows.Media.Animation.Timeline>对象在容器时间线时停止播放。 下面的示例将<xref:System.Windows.Media.Animation.Timeline.Duration%2A>上述示例中的<xref:System.Windows.Media.Animation.Storyboard>的 将 集 到三秒。 因此，第一个<xref:System.Windows.Media.Animation.DoubleAnimation>停止在三秒钟后前进，当它已动画的目标矩形的宽度到60。  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>
### <a name="the-repeatbehavior-property"></a>RepeatBehavior 属性  
 属性<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A><xref:System.Windows.Media.Animation.Timeline>控制它重复其简单持续时间的次数。 使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性，可以指定时间线播放的次数（迭代<xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>）或时间线应播放的总时间长度（重复）。 <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A> 无论是哪一种情况，动画都将从头到尾运行很多次，直到完成要求的次数或经历完所需的一段时间。 默认情况下，时间线的迭代计数为`1.0`，这意味着它们播放一次，并且根本不重复。  
  
 下面的示例使用 属性<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>通过指定迭代计数<xref:System.Windows.Media.Animation.DoubleAnimation>使播放具有两倍的简单持续时间。  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 下一个示例使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性使<xref:System.Windows.Media.Animation.DoubleAnimation>该游戏的一半简单持续时间。  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 如果将<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>属性<xref:System.Windows.Media.Animation.Timeline>设置为<xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>，则<xref:System.Windows.Media.Animation.Timeline>重复，直到以交互方式或由计时系统停止。 下面的示例使用 属性<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>无限期地进行<xref:System.Windows.Media.Animation.DoubleAnimation>播放。  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 有关其他示例，请参阅[重复动画](how-to-repeat-an-animation.md)。  
  
<a name="autoreverseproperty"></a>
### <a name="the-autoreverse-property"></a>AutoReverse 属性  
 属性<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>指定 将在<xref:System.Windows.Media.Animation.Timeline>每次向前迭代结束时向后播放 。 下面的示例将设置到<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>的 属性<xref:System.Windows.Media.Animation.DoubleAnimation> `true`。因此，它将动画从零到 100，然后从 100 到零。 它的总播放时长为 10 秒。  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>当使用 值指定 的<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A><xref:System.Windows.Media.Animation.Timeline><xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>和 属性时<xref:System.Windows.Media.Animation.Timeline>`true`，单个重复由一个向前迭代组成，后跟一个向后迭代。  下面的示例将<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A><xref:System.Windows.Media.Animation.DoubleAnimation>上一个示例的 将 的<xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>将 集的 2 个集。 结果，<xref:System.Windows.Media.Animation.DoubleAnimation>播放 20 秒：向前 5 秒，向后 5 秒，再次向前前进 5 秒，然后向后向后 5 秒。  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 如果容器时间线具有子<xref:System.Windows.Media.Animation.Timeline>对象，则当容器时间线执行时，它们会反转。 有关其他示例，请参阅[指定时间线是否自动反转](how-to-specify-whether-a-timeline-automatically-reverses.md)。  
  
<a name="timelinebegin"></a>
## <a name="the-begintime-property"></a>BeginTime 属性  
 属性<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>使您能够指定时间线何时启动。  时间线的开始时间相对于其父时间线。 如果开始时间为零秒，则表示其父时间线开始后，该时间线立即开始；如果开始时间为其他值，会在父时间线和子时间线的开始播放时间之间产生时间偏差。 例如，如果开始时间为两秒，则表示在其父时间线到达两秒后，该时间线才开始播放。 默认情况下，所有时间线的开始时间都为零秒。 您还可以将时间线的开始时间设置为`null`，这可以防止时间线启动。 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中，使用[x：空标记扩展名](../../../desktop-wpf/xaml-services/xnull-markup-extension.md)指定 null。  
  
 请注意，每次时间线因其<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>设置而重复时，不会应用开始时间。 如果要创建具有<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>10 秒和 1<xref:System.Windows.Media.Animation.RepeatBehavior>的<xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>动画，则在首次播放动画之前会有 10 秒的延迟，但每次连续重复时不会延迟。 但是，如果动画的父时间线重新开始或重复，则会延迟 10 秒。  
  
 该<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>属性可用于惊人的时间线。 下面的示例创建具有两<xref:System.Windows.Media.Animation.Storyboard>个子<xref:System.Windows.Media.Animation.DoubleAnimation>对象的 。 第一<xref:System.Windows.Media.Animation.Timeline.Duration%2A>个动画有 5 秒，第二个<xref:System.Windows.Media.Animation.Timeline.Duration%2A>动画有 3 秒。 该示例将第<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>二<xref:System.Windows.Media.Animation.DoubleAnimation>秒设置为 5 秒，以便它在第一<xref:System.Windows.Media.Animation.DoubleAnimation>端后开始播放。  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>
## <a name="the-fillbehavior-property"></a>FillBehavior 属性  
 当<xref:System.Windows.Media.Animation.Timeline>达到其总活动持续时间的末尾时，<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性指定它是停止还是保留其最后一个值。 具有"保留"<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>其<xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>输出值的动画：正在动画的属性将保留动画的最后一个值。 动画结束后<xref:System.Windows.Media.Animation.FillBehavior.Stop>停止影响其目标属性的值。  
  
 下面的示例创建具有两<xref:System.Windows.Media.Animation.Storyboard>个子<xref:System.Windows.Media.Animation.DoubleAnimation>对象的 。 两<xref:System.Windows.Media.Animation.DoubleAnimation>个对象为<xref:System.Windows.FrameworkElement.Width%2A>0<xref:System.Windows.Shapes.Rectangle>到 100 的 动画。 元素<xref:System.Windows.Shapes.Rectangle>的非动画<xref:System.Windows.FrameworkElement.Width%2A>值为 500 [设备无关像素]。  
  
- 第<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>一<xref:System.Windows.Media.Animation.DoubleAnimation>个的属性设置为<xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>，默认值。 因此，矩形的宽度在<xref:System.Windows.Media.Animation.DoubleAnimation>结束后保持在 100。  
  
- 第<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>二<xref:System.Windows.Media.Animation.DoubleAnimation>个属性设置为<xref:System.Windows.Media.Animation.FillBehavior.Stop>。 因此，第<xref:System.Windows.FrameworkElement.Width%2A>二<xref:System.Windows.Shapes.Rectangle>个在<xref:System.Windows.Media.Animation.DoubleAnimation>结束后将恢复为 500。  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>
## <a name="properties-that-control-the-speed-of-a-timeline"></a>用于控制时间线速度的属性  
 类<xref:System.Windows.Media.Animation.Timeline>提供了三个属性来指定其速度：  
  
- <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>• 指定相对于其父级的速率，此时将进行<xref:System.Windows.Media.Animation.Timeline>。 大于 1 的值会增加<xref:System.Windows.Media.Animation.Timeline>及其子<xref:System.Windows.Media.Animation.Timeline>对象的速度;零和 1 之间的值减慢速度。 值 1 表示<xref:System.Windows.Media.Animation.Timeline>以与其父值相同的速率前进。 容器<xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>时间线的设置也会影响其所有子<xref:System.Windows.Media.Animation.Timeline>对象。  
  
- <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>• 指定加速花费的时间<xref:System.Windows.Media.Animation.Timeline.Duration%2A>轴的百分比。 例如，请参阅[如何：加速或减速动画](how-to-accelerate-or-decelerate-an-animation.md)。
  
- <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>- 指定时间轴的<xref:System.Windows.Media.Animation.Timeline.Duration%2A>百分比，用于减速。 例如，请参阅[如何：加速或减速动画](how-to-accelerate-or-decelerate-an-animation.md)。  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
- [动画和计时系统概述](animation-and-timing-system-overview.md)
- [计时事件概述](timing-events-overview.md)
- [如何使用主题](animation-and-timing-how-to-topics.md)
- [动画计时行为示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
