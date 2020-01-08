---
title: 计时行为概述
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: a85f980a0cefaa282e9e92d533a2306a9009e3e7
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559945"
---
# <a name="timing-behaviors-overview"></a>计时行为概述
本主题介绍动画和其他 <xref:System.Windows.Media.Animation.Timeline> 对象的计时行为。  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>先决条件  
 若要了解本主题，应熟悉基本动画功能。 有关详细信息，请参阅[动画概述](animation-overview.md)。  
  
<a name="timelinetypes"></a>   
## <a name="timeline-types"></a>时间线类型  
 一个 <xref:System.Windows.Media.Animation.Timeline> 表示时间段。 它提供的属性让你可以指定该时间段的长度、开始时间、重复次数、该时间段内时间进度的快慢等。  
  
 从时间线类继承的类可提供附加功能，例如动画和媒体播放。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供以下 <xref:System.Windows.Media.Animation.Timeline> 类型。  
  
|时间线类型|描述|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|用于生成用于对属性进行动画处理的输出值的 <xref:System.Windows.Media.Animation.Timeline> 对象的抽象基类。|  
|<xref:System.Windows.Media.MediaTimeline>|从媒体文件生成输出。|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|一种用于分组和控制子 <xref:System.Windows.Media.Animation.Timeline> 对象的 <xref:System.Windows.Media.Animation.TimelineGroup> 类型。|  
|<xref:System.Windows.Media.Animation.Storyboard>|一种 <xref:System.Windows.Media.Animation.ParallelTimeline> 类型，它为其包含的时间线对象提供目标信息。|  
|<xref:System.Windows.Media.Animation.Timeline>|定义计时行为的抽象基类。|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|可包含其他 <xref:System.Windows.Media.Animation.Timeline> 对象的 <xref:System.Windows.Media.Animation.Timeline> 对象的抽象类。|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## <a name="properties-that-control-the-length-of-a-timeline"></a>用于控制时间线长度的属性  
 <xref:System.Windows.Media.Animation.Timeline> 表示时间段，并且可以通过不同的方式描述时间线的长度。 下表定义了几个用于描述时间线长度的术语。  
  
|术语|描述|属性||||  
|----------|-----------------|----------------|-|-|-|  
|简单持续时间|时间线向前迭代一次所需的时间长度。|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|一次重复|时间线向前播放一次所花的时间长度，如果 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 属性为 true，则向后播放一次。|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|活动期|时间线完成其 <xref:System.Windows.Media.Animation.RepeatBehavior> 属性指定的所有重复所用的时间长度。|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### <a name="the-duration-property"></a>Duration 属性  
 如前文所述，时间线表示时间段。 该时间段的长度由时间线的 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>确定。 当时间线到达其持续时间的终点时，就会停止播放。 如果时间线具有子时间线，这些子时间线也会停止播放。 对于动画，<xref:System.Windows.Media.Animation.Timeline.Duration%2A> 指定动画从其起始值过渡到其结束值所用的时间。 时间线的持续时间有时称为*简单持续时间*，用于区分单个迭代的持续时间和动画播放的总时间（包括重复）。 您可以使用有限时间值或特殊值 <xref:System.Windows.Duration.Automatic%2A> 或 <xref:System.Windows.Duration.Forever%2A>来指定持续时间。 动画的持续时间应该解析为 <xref:System.Windows.Duration.TimeSpan%2A> 值，因此它可以在值之间过渡。  
  
 下面的示例演示一个 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 为5秒的 <xref:System.Windows.Media.Animation.DoubleAnimation>。  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 容器时间线（如 <xref:System.Windows.Media.Animation.Storyboard> 和 <xref:System.Windows.Media.Animation.ParallelTimeline>）的默认持续时间为 <xref:System.Windows.Duration.Automatic%2A>，这意味着在其最后一个子级停止播放时，它们会自动结束。 下面的示例演示了一个 <xref:System.Windows.Media.Animation.Storyboard>，其 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 解析为5秒，这是其所有子 <xref:System.Windows.Media.Animation.DoubleAnimation> 对象完成所用的时间长度。  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 通过将容器时间线的 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 设置为 <xref:System.Windows.Duration.TimeSpan%2A> 值，你可以强制播放比它的子 <xref:System.Windows.Media.Animation.Timeline> 对象更长或更短的时间。 如果将 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 设置为小于容器时间线的子 <xref:System.Windows.Media.Animation.Timeline> 对象的长度的值，则当容器时间线完成时，子 <xref:System.Windows.Media.Animation.Timeline> 对象将停止播放。 下面的示例将前面的示例中 <xref:System.Windows.Media.Animation.Storyboard> 的 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 设置为三秒。 因此，第一个 <xref:System.Windows.Media.Animation.DoubleAnimation> 在三秒后停止前进，在这种情况下，当动画将目标矩形的宽度设定为60时，就会停止。  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>   
### <a name="the-repeatbehavior-property"></a>RepeatBehavior 属性  
 <xref:System.Windows.Media.Animation.Timeline> 的 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性控制其简单持续时间重复的次数。 使用 "<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>" 属性可以指定时间线播放的次数（迭代 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>）或它应播放的总时间长度（重复 <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>）。 无论是哪一种情况，动画都将从头到尾运行很多次，直到完成要求的次数或经历完所需的一段时间。 默认情况下，时间线的迭代次数为 `1.0`，这意味着它们只播放一次，根本不重复。  
  
 下面的示例使用 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性，通过指定迭代次数，使 <xref:System.Windows.Media.Animation.DoubleAnimation> 播放其简单持续时间的两倍。  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 下一个示例使用 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性，使 <xref:System.Windows.Media.Animation.DoubleAnimation> 的播放时间为其简单持续时间的一半。  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 如果将 <xref:System.Windows.Media.Animation.Timeline> 的 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性设置为 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>，则 <xref:System.Windows.Media.Animation.Timeline> 会重复，直到以交互方式或通过计时系统停止。 下面的示例使用 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 属性，使 <xref:System.Windows.Media.Animation.DoubleAnimation> 无限期播放。  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 有关其他示例，请参阅[重复使用动画](how-to-repeat-an-animation.md)。  
  
<a name="autoreverseproperty"></a>   
### <a name="the-autoreverse-property"></a>AutoReverse 属性  
 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 属性指定 <xref:System.Windows.Media.Animation.Timeline> 在每次向前迭代结束时是否会向后播放。 下面的示例将设置为 <xref:System.Windows.Media.Animation.DoubleAnimation> 的 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 属性 `true`;因此，它将从零动画处理到100，然后从100动画处理到零。 它的总播放时长为 10 秒。  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 当使用 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> 值指定 <xref:System.Windows.Media.Animation.Timeline> 的 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>，并且 <xref:System.Windows.Media.Animation.Timeline> `true`的 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 属性时，单个重复项由一个向前迭代后跟一个向后迭代。  下面的示例将前面的示例中 <xref:System.Windows.Media.Animation.DoubleAnimation> 的 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 设置为2的 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>。 因此，<xref:System.Windows.Media.Animation.DoubleAnimation> 的播放时间为20秒：前进5秒，反向5秒，再前进5秒，然后反向5秒钟。  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 如果容器时间线具有子 <xref:System.Windows.Media.Animation.Timeline> 对象，则当容器时间线时，它们会反转。 有关其他示例，请参阅[指定时间线是否自动反转](how-to-specify-whether-a-timeline-automatically-reverses.md)。  
  
<a name="timelinebegin"></a>   
## <a name="the-begintime-property"></a>BeginTime 属性  
 利用 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 属性可以指定时间线的开始时间。  时间线的开始时间相对于其父时间线。 如果开始时间为零秒，则表示其父时间线开始后，该时间线立即开始；如果开始时间为其他值，会在父时间线和子时间线的开始播放时间之间产生时间偏差。 例如，如果开始时间为两秒，则表示在其父时间线到达两秒后，该时间线才开始播放。 默认情况下，所有时间线的开始时间都为零秒。 你还可以将时间线的开始时间设置为 `null`，这会阻止时间线启动。 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中，使用[X:Null 标记扩展](../../../desktop-wpf/xaml-services/xnull-markup-extension.md)指定 null。  
  
 请注意，每当时间线因为其 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 设置而重复时，就不会应用开始时间。 如果创建的动画的 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 为10秒，而 <xref:System.Windows.Media.Animation.RepeatBehavior> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>，则在第一次播放动画之前会出现10秒的延迟，但对于每个连续的重复，则不会出现。 但是，如果动画的父时间线重新开始或重复，则会延迟 10 秒。  
  
 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 属性适用于交错时间线。 下面的示例创建一个具有两个子 <xref:System.Windows.Media.Animation.DoubleAnimation> 对象的 <xref:System.Windows.Media.Animation.Storyboard>。 第一个动画的 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 为5秒，第二个动画的 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 为3秒。 此示例将第一个 <xref:System.Windows.Media.Animation.DoubleAnimation> 的 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 设置为5秒，使其在第一个 <xref:System.Windows.Media.Animation.DoubleAnimation> 结束后开始播放。  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>   
## <a name="the-fillbehavior-property"></a>FillBehavior 属性  
 当 <xref:System.Windows.Media.Animation.Timeline> 达到其总活动持续时间的终点时，<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 属性指定它是停止还是保留其最后一个值。 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 为 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> "保存" 其输出值的动画：要进行动画处理的属性将保留动画的最后一个值。 值 <xref:System.Windows.Media.Animation.FillBehavior.Stop> 会导致动画结束后，动画停止影响其目标属性。  
  
 下面的示例创建一个具有两个子 <xref:System.Windows.Media.Animation.DoubleAnimation> 对象的 <xref:System.Windows.Media.Animation.Storyboard>。 这两个 <xref:System.Windows.Media.Animation.DoubleAnimation> 对象均对从0到100的 <xref:System.Windows.Shapes.Rectangle> 的 <xref:System.Windows.FrameworkElement.Width%2A> 进行动画处理。 <xref:System.Windows.Shapes.Rectangle> 元素具有非动画 <xref:System.Windows.FrameworkElement.Width%2A> 值 500 [与设备无关的像素]。  
  
- 第一个 <xref:System.Windows.Media.Animation.DoubleAnimation> 的 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 属性设置为 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>，默认值为。 因此，在 <xref:System.Windows.Media.Animation.DoubleAnimation> 结束后，矩形的宽度保持为100。  
  
- 第二个 <xref:System.Windows.Media.Animation.DoubleAnimation> 的 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 属性设置为 <xref:System.Windows.Media.Animation.FillBehavior.Stop>。 因此，第二个 <xref:System.Windows.Shapes.Rectangle> 的 <xref:System.Windows.FrameworkElement.Width%2A> 在 <xref:System.Windows.Media.Animation.DoubleAnimation> 结束后恢复为500。  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>   
## <a name="properties-that-control-the-speed-of-a-timeline"></a>用于控制时间线速度的属性  
 <xref:System.Windows.Media.Animation.Timeline> 类提供了三个用于指定其速度的属性：  
  
- <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> –指定相对于其父级的速率（对于 <xref:System.Windows.Media.Animation.Timeline>的时间前进）。 大于1的值将提高 <xref:System.Windows.Media.Animation.Timeline> 及其子 <xref:System.Windows.Media.Animation.Timeline> 对象的速度;介于0和1之间的值将减慢。 如果值为1，则表示 <xref:System.Windows.Media.Animation.Timeline> 按其父级的相同速率进行。 容器时间线的 <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> 设置也会影响其所有子 <xref:System.Windows.Media.Animation.Timeline> 对象。  
  
- <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> –指定时间线的 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 加速所用时间的百分比。 有关示例，请参阅[如何：加速或减速动画](how-to-accelerate-or-decelerate-an-animation.md)。 
  
- <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>-指定减速所用时间线的 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 百分比。 有关示例，请参阅[如何：加速或减速动画](how-to-accelerate-or-decelerate-an-animation.md)。  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
- [动画和计时系统概述](animation-and-timing-system-overview.md)
- [计时事件概述](timing-events-overview.md)
- [帮助主题](animation-and-timing-how-to-topics.md)
- [动画计时行为示例](https://go.microsoft.com/fwlink/?LinkID=159970)
