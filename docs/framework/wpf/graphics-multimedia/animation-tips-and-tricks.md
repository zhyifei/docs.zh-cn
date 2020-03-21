---
title: 动画提示和技巧
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting [WPF], animation
- animations [WPF], FillBehavior property
- troubleshooting animation [WPF]
- animating objects [WPF], troubleshooting
- animation tips and tricks [WPF]
- tips and tricks [WPF], animation
- performance troubleshooting [WPF], animation
- animations [WPF], use of system resources
ms.assetid: e467796b-d5d4-45a6-a108-8c5d7ff69a0f
ms.openlocfilehash: 6b540448599c1e1083ed367a312ef60fceacd0d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187649"
---
# <a name="animation-tips-and-tricks"></a>动画提示和技巧
在 WPF 中处理动画时，有许多提示和技巧可以使动画更好地执行，并节省您的挫折感。  
  
<a name="generalissuessection"></a>
## <a name="general-issues"></a>一般问题  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>对滚动条或滑块的位置进行动画处理将冻结它  
 如果使用具有 的<xref:System.Windows.Media.Animation.FillBehavior><xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>动画（默认值）为滚动条或滑块的位置设置动画，则用户将无法再移动滚动条或滑块。 这是因为，即使动画已结束，它仍然在重写目标属性的基值。 要阻止动画重写属性的当前值，请将其删除，或将其<xref:System.Windows.Media.Animation.FillBehavior>为 。 <xref:System.Windows.Media.Animation.FillBehavior.Stop> 有关详细信息和示例，请参阅[使用情节提要设置属性后设置属性](how-to-set-a-property-after-animating-it-with-a-storyboard.md)。  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>对动画的输出进行动画处理没有效果  
 如果某个对象是另一个动画的输出，则无法对该对象进行动画处理。 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>例如，如果使用 的 动画从<xref:System.Windows.Shapes.Shape.Fill%2A><xref:System.Windows.Shapes.Rectangle><xref:System.Windows.Media.RadialGradientBrush><xref:System.Windows.Media.SolidColorBrush><xref:System.Windows.Media.RadialGradientBrush><xref:System.Windows.Media.SolidColorBrush>  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>在对属性进行动画处理后无法更改该属性的值  
 在某些情况下，在对属性进行动画处理后，即使在动画结束后，看起来仍无法更改该属性的值。 这是因为即使动画已结束，它仍然在重写该属性的基值。 要阻止动画重写属性的当前值，请将其删除，或将其<xref:System.Windows.Media.Animation.FillBehavior>为 。 <xref:System.Windows.Media.Animation.FillBehavior.Stop> 有关详细信息和示例，请参阅[使用情节提要设置属性后设置属性](how-to-set-a-property-after-animating-it-with-a-storyboard.md)。  
  
### <a name="changing-a-timeline-has-no-effect"></a>更改时间线没有效果  
 尽管大多数<xref:System.Windows.Media.Animation.Timeline>属性都是可动画的，并且可以绑定数据，但更改活动的属性<xref:System.Windows.Media.Animation.Timeline>值似乎不起作用。 这是因为，当 开始 时<xref:System.Windows.Media.Animation.Timeline>，计时系统会复制 并<xref:System.Windows.Media.Animation.Timeline>用它来创建<xref:System.Windows.Media.Animation.Clock>对象。 修改原件对系统的副本没有影响。  
  
 <xref:System.Windows.Media.Animation.Timeline>要反映更改，必须重新生成其时钟，并用于替换以前创建的时钟。 时钟不会自动重新生成。 以下是应用时间线更改的几种方法：  
  
- 如果时间线是 或 属于<xref:System.Windows.Media.Animation.Storyboard>， 则可以通过使用<xref:System.Windows.Media.Animation.BeginStoryboard>或<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>方法重新应用其情节提要来使其反映更改。 这还会产生重新启动动画的附带影响。 在代码中，可以使用 方法<xref:System.Windows.Media.Animation.Storyboard.Seek%2A>将情节提要推进回其以前的位置。  
  
- 如果使用 方法将动画直接应用于属性<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>，请再次调用 该方法<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>并传递已修改的动画。  
  
- 如果要直接在时钟级别上工作，请创建并应用一组新的时钟，然后用它们替换之前生成的一组时钟。  
  
 有关时间线和时钟的详细信息，请参阅[动画和计时系统概述](animation-and-timing-system-overview.md)。  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop 不按预期方式工作  
 有时，<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>将属性设置为<xref:System.Windows.Media.Animation.FillBehavior.Stop>似乎不起作用，例如，当一个动画由于具有 的<xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A><xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>设置而"手离"另一个动画时，它具有 。  
  
 下面的示例创建 和<xref:System.Windows.Controls.Canvas><xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Media.TranslateTransform>。 <xref:System.Windows.Media.TranslateTransform>将进行动画移动。 <xref:System.Windows.Controls.Canvas> <xref:System.Windows.Shapes.Rectangle>  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 本节中的示例使用前面的对象来演示<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性未按预期表现的几个情况。  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>针对多个动画的 FillBehavior="Stop" 和 HandoffBehavior  
 有时，当动画被第二个动画替换<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>时，它似乎会忽略其属性。 以以下示例为例，该示例创建<xref:System.Windows.Media.Animation.Storyboard>两个对象，并使用它们为上<xref:System.Windows.Media.TranslateTransform>一个示例所示的相同对象设置动画。  
  
 第一<xref:System.Windows.Media.Animation.Storyboard>个`B1`，为<xref:System.Windows.Media.TranslateTransform.X%2A>从<xref:System.Windows.Media.TranslateTransform>0 到 350 的属性设置动画，该属性将矩形向右移动 350 像素。 当动画达到其持续时间的末尾并停止播放时，<xref:System.Windows.Media.TranslateTransform.X%2A>属性将恢复为其原始值 0。 因此，矩形向右移动 350 像素，然后跳回其原始位置。  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 第二<xref:System.Windows.Media.Animation.Storyboard>个`B2`，还对相同的<xref:System.Windows.Media.TranslateTransform.X%2A><xref:System.Windows.Media.TranslateTransform>属性进行动画处理。 由于仅<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>设置动画<xref:System.Windows.Media.Animation.Storyboard>的属性，因此动画使用其动画属性的当前值作为其起始值。  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 如果在播放第一个按钮时单击第<xref:System.Windows.Media.Animation.Storyboard>二个按钮，则可能预期会出现以下行为：  
  
1. 第一个情节提要结束，并将矩形发送回其原始位置，因为动画具有<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>的<xref:System.Windows.Media.Animation.FillBehavior.Stop>。  
  
2. 第二个情节提要生效，从当前位置（现在为 0）播放动画到 500。  
  
 **但情况并非如此。** 矩形没有跳回，而是继续向右移动。 这是因为第二个动画使用第一个动画的当前值作为其起始值，并从该值开始播放动画到 500。 当第二个动画替换第一个动画<xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace><xref:System.Windows.Media.Animation.HandoffBehavior>时，因为使用了<xref:System.Windows.Media.Animation.FillBehavior>，第一个动画的则无关紧要。  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior 和 Completed 事件  
 接下来的示例演示了另一个场景，<xref:System.Windows.Media.Animation.FillBehavior.Stop><xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>其中似乎没有效果。 同样，该示例使用情节提要为<xref:System.Windows.Media.TranslateTransform.X%2A><xref:System.Windows.Media.TranslateTransform>从 0 到 350 的属性设置动画。 但是，这一次，该示例注册该<xref:System.Windows.Media.Animation.Timeline.Completed>事件。  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 事件<xref:System.Windows.Media.Animation.Timeline.Completed>处理程序启动另一<xref:System.Windows.Media.Animation.Storyboard>个将同一属性从当前值动画到 500 的动画。  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 以下是将第二<xref:System.Windows.Media.Animation.Storyboard>个标记定义为资源。  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 运行 时<xref:System.Windows.Media.Animation.Storyboard><xref:System.Windows.Media.TranslateTransform.X%2A>，您可能希望 的属性<xref:System.Windows.Media.TranslateTransform>从 0 到 350 进行动画处理，然后在它完成后还原为 0（因为它具有<xref:System.Windows.Media.Animation.FillBehavior><xref:System.Windows.Media.Animation.FillBehavior.Stop>的设置），然后从 0 到 500 进行动画处理。 相反，<xref:System.Windows.Media.TranslateTransform>动画从 0 到 350，然后到 500。  
  
 这是因为 WPF 引发事件的顺序，以及属性值被缓存，并且除非属性无效，否则不会重新计算。 首先<xref:System.Windows.Media.Animation.Timeline.Completed>处理事件，因为它是由根时间线（第一个<xref:System.Windows.Media.Animation.Storyboard>）触发的。 此时，<xref:System.Windows.Media.TranslateTransform.X%2A>该属性仍返回其动画值，因为它尚未失效。 第二<xref:System.Windows.Media.Animation.Storyboard>个使用缓存的值作为其起始值，并开始进行动画处理。  
  
<a name="performancesection"></a>
## <a name="performance"></a>性能  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>在导航离开页面后动画继续运行  
 当您从包含正在运行的动画的<xref:System.Windows.Controls.Page>导航时，这些动画将继续播放，<xref:System.Windows.Controls.Page>直到垃圾回收。 根据正在使用的导航系统，导航离开的页面可能无限期地保留在内存中，在此期间始终通过动画消耗资源。 当页面包含不断运行的（“氛围”）动画时，这一点最明显。  
  
 因此，最好在<xref:System.Windows.FrameworkElement.Unloaded>远离页面时使用事件删除动画。  
  
 删除动画有多种不同的方法。 以下技术可用于删除属于 的<xref:System.Windows.Media.Animation.Storyboard>动画。  
  
- 要删除<xref:System.Windows.Media.Animation.Storyboard>从事件触发器开始，请参阅[如何：删除情节提要](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90))。  
  
- 要使用代码删除 ，<xref:System.Windows.Media.Animation.Storyboard>请参阅<xref:System.Windows.Media.Animation.Storyboard.Remove%2A>方法。  
  
 无论动画如何启动，都可以使用下一个技术。  
  
- 要从特定属性中删除动画，请使用 方法<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>。 将正在动画处理的属性指定为第一个参数`null`，并将第二个参数指定为第二个参数。 这将从该属性中删除所有动画时钟。  
  
 有关设置属性动画的不同方法的详细信息，请参阅[属性动画技术概述](property-animation-techniques-overview.md)。  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>使用组合 HandoffBehavior 会消耗系统资源  
 <xref:System.Windows.Media.Animation.Storyboard>当您使用<xref:System.Windows.Media.Animation.AnimationTimeline><xref:System.Windows.Media.Animation.HandoffBehavior.Compose><xref:System.Windows.Media.Animation.AnimationClock>对 属性应用 ，时，以前与该<xref:System.Windows.Media.Animation.Clock>属性关联的任何对象将继续使用系统资源;因此，使用<xref:System.Windows.Media.Animation.HandoffBehavior>计时系统不会自动删除这些时钟。  
  
 为了避免使用<xref:System.Windows.Media.Animation.HandoffBehavior.Compose>应用大量时钟时的性能问题，应在动画属性完成后从动画属性中删除组合时钟。 删除时钟有多种方法。  
  
- 要从属性中删除所有时钟，请使用动画对象的<xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29>或<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>方法。 将正在动画处理的属性指定为第一个参数`null`，并将第二个参数指定为第二个参数。 这将从该属性中删除所有动画时钟。  
  
- 若要从时钟列表中<xref:System.Windows.Media.Animation.AnimationClock>删除特定<xref:System.Windows.Media.Animation.Clock.Controller%2A>项，请使用 的属性<xref:System.Windows.Media.Animation.AnimationClock>来检索<xref:System.Windows.Media.Animation.ClockController>， 然后调用<xref:System.Windows.Media.Animation.ClockController.Remove%2A>的方法<xref:System.Windows.Media.Animation.ClockController>。 这通常在时钟<xref:System.Windows.Media.Animation.Clock.Completed>的事件处理程序中完成。 请注意，只有根时钟可以由<xref:System.Windows.Media.Animation.ClockController>。子<xref:System.Windows.Media.Animation.Clock.Controller%2A>时钟的属性将返回`null`。 另请注意，如果<xref:System.Windows.Media.Animation.Clock.Completed>时钟的有效持续时间是永远的，将不会调用该事件。  在这种情况下，用户将需要确定何时调用<xref:System.Windows.Media.Animation.ClockController.Remove%2A>。  
  
 此动画问题主要出现在生存期较长的对象上。  当对某个对象进行垃圾回收时，它的时钟也会断开连接并进行垃圾回收。  
  
 有关时钟对象的详细信息，请参阅[动画和计时系统概述](animation-and-timing-system-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
