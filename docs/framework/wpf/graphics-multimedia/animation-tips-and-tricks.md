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
ms.openlocfilehash: 2fcabf178eb9d1b56582422204c6a745c6388a85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558351"
---
# <a name="animation-tips-and-tricks"></a>动画提示和技巧
在处理中的动画时[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]，有大量的提示和技巧，可使动画更好地执行，并避免出现挫折。  
  
<a name="generalissuessection"></a>   
## <a name="general-issues"></a>一般问题  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>对滚动条或滑块的位置进行动画处理将冻结它  
 如果动态显示的滚动条或使用具有动画的滑块的位置<xref:System.Windows.Media.Animation.FillBehavior>的<xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>（默认值），用户将不再能够移动滑块的滚动条。 这是因为，即使动画已结束，它仍然在重写目标属性的基值。 若要停止动画重写属性的当前值，将其删除，或向其提供<xref:System.Windows.Media.Animation.FillBehavior>的<xref:System.Windows.Media.Animation.FillBehavior.Stop>。 有关详细信息及示例，请参阅[属性后进行动画处理将其设置与情节提要](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md)。  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>对动画的输出进行动画处理没有效果  
 如果某个对象是另一个动画的输出，则无法对该对象进行动画处理。 例如，如果你使用<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>要进行动画处理<xref:System.Windows.Shapes.Shape.Fill%2A>的<xref:System.Windows.Shapes.Rectangle>从<xref:System.Windows.Media.RadialGradientBrush>到<xref:System.Windows.Media.SolidColorBrush>，无法进行动画处理的任何属性<xref:System.Windows.Media.RadialGradientBrush>或<xref:System.Windows.Media.SolidColorBrush>。  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>在对属性进行动画处理后无法更改该属性的值  
 在某些情况下，在对属性进行动画处理后，即使在动画结束后，看起来仍无法更改该属性的值。 这是因为即使动画已结束，它仍然在重写该属性的基值。 若要停止动画重写属性的当前值，将其删除，或向其提供<xref:System.Windows.Media.Animation.FillBehavior>的<xref:System.Windows.Media.Animation.FillBehavior.Stop>。 有关详细信息及示例，请参阅[属性后进行动画处理将其设置与情节提要](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md)。  
  
### <a name="changing-a-timeline-has-no-effect"></a>更改时间线没有效果  
 虽然大多数<xref:System.Windows.Media.Animation.Timeline>属性可进行动画处理，并且可以将数据绑定，更改活动的属性值<xref:System.Windows.Media.Animation.Timeline>似乎不起作用。 这是因为，当<xref:System.Windows.Media.Animation.Timeline>是开始，计时系统会进行一份<xref:System.Windows.Media.Animation.Timeline>并使用它来创建<xref:System.Windows.Media.Animation.Clock>对象。 修改原件对系统的副本没有影响。  
  
 有关<xref:System.Windows.Media.Animation.Timeline>以反映更改，其时钟必须重新生成并用于替换以前创建的时钟。 时钟不会自动重新生成。 以下是应用时间线更改的几种方法：  
  
-   如果时间线或属于<xref:System.Windows.Media.Animation.Storyboard>，你可以通过重新应用其情节提要使用反映更改<xref:System.Windows.Media.Animation.BeginStoryboard>或<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>方法。 这还会产生重新启动动画的附带影响。 在代码中，你可以使用<xref:System.Windows.Media.Animation.Storyboard.Seek%2A>方法向前移动情节提要重新为其以前的位置。  
  
-   如果你将动画应用于属性使用直接<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法中，调用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>再次方法并将其传递已修改动画。  
  
-   如果要直接在时钟级别上工作，请创建并应用一组新的时钟，然后用它们替换之前生成的一组时钟。  
  
 有关时间线和时钟的详细信息，请参阅[动画和计时系统概述](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)。  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop 不按预期方式工作  
 有时设置时<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性<xref:System.Windows.Media.Animation.FillBehavior.Stop>似乎不起作用，例如，当一个动画"将传递"到另一个因为它具有<xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>设置<xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>。  
  
 下面的示例创建<xref:System.Windows.Controls.Canvas>、<xref:System.Windows.Shapes.Rectangle>和<xref:System.Windows.Media.TranslateTransform>。 <xref:System.Windows.Media.TranslateTransform>将对其进行动画处理，将<xref:System.Windows.Shapes.Rectangle>围绕<xref:System.Windows.Controls.Canvas>。  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 此部分中的示例使用上述对象来演示几种情况，其中<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>属性的行为与不可能预计。  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>针对多个动画的 FillBehavior="Stop" 和 HandoffBehavior  
 有时它看起来就像动画将忽略其<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>时它替换为第二个动画的属性。 执行下面的示例创建两个<xref:System.Windows.Media.Animation.Storyboard>对象并使用它们进行动画处理相同<xref:System.Windows.Media.TranslateTransform>前面示例中所示。  
  
 第一个<xref:System.Windows.Media.Animation.Storyboard>， `B1`，进行动画处理<xref:System.Windows.Media.TranslateTransform.X%2A>属性<xref:System.Windows.Media.TranslateTransform>从 0 到 350，其中矩形 350 像素向右移动。 当动画达到其持续时间的末尾，并停止播放，<xref:System.Windows.Media.TranslateTransform.X%2A>属性将恢复到其原始值为 0。 因此，矩形向右移动 350 像素，然后跳回其原始位置。  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 第二个<xref:System.Windows.Media.Animation.Storyboard>， `B2`，还进行动画处理<xref:System.Windows.Media.TranslateTransform.X%2A>的相同属性<xref:System.Windows.Media.TranslateTransform>。 因为仅<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>属性在此动画<xref:System.Windows.Media.Animation.Storyboard>设置，动画使用它进行动画处理的属性的当前值作为其起始值。  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 如果单击第二个按钮时第一个<xref:System.Windows.Media.Animation.Storyboard>是播放，你可能会出现以下行为：  
  
1.  第一个情节提要结束，并将该矩形发送回其原始位置，因为动画具有<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>的<xref:System.Windows.Media.Animation.FillBehavior.Stop>。  
  
2.  第二个情节提要生效，从当前位置（现在为 0）播放动画到 500。  
  
 **但情况并非如此。** 矩形没有跳回，而是继续向右移动。 这是因为第二个动画使用第一个动画的当前值作为其起始值，并从该值开始播放动画到 500。 当第二个动画替换第一个，因为<xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace><xref:System.Windows.Media.Animation.HandoffBehavior>使用时，<xref:System.Windows.Media.Animation.FillBehavior>的第一个动画并不重要。  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior 和 Completed 事件  
 下一步的示例演示在其中的另一个方案<xref:System.Windows.Media.Animation.FillBehavior.Stop><xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>似乎不起作用。 同样，该示例使用情节提要要进行动画处理<xref:System.Windows.Media.TranslateTransform.X%2A>属性<xref:System.Windows.Media.TranslateTransform>从 0 到 350。 但是，此时该示例会注册<xref:System.Windows.Media.Animation.Timeline.Completed>事件。  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 <xref:System.Windows.Media.Animation.Timeline.Completed>事件处理程序启动另一个进程<xref:System.Windows.Media.Animation.Storyboard>从其当前值为 500 相同的属性进行动画处理。  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 下面是定义第二个的标记<xref:System.Windows.Media.Animation.Storyboard>作为资源。  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 当你运行<xref:System.Windows.Media.Animation.Storyboard>，你所料<xref:System.Windows.Media.TranslateTransform.X%2A>属性<xref:System.Windows.Media.TranslateTransform>进行动画处理从 0 到 350，然后还原成 0 它完成后 (因为它具有<xref:System.Windows.Media.Animation.FillBehavior>设置<xref:System.Windows.Media.Animation.FillBehavior.Stop>)，然后从动态变化 0 到 500 和。 相反， <xref:System.Windows.Media.TranslateTransform> 0 动画应用到 350，然后再为 500。  
  
 这是因为的顺序[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]引发的事件，并且因为属性值将缓存且不重新评估，除非该属性无效。 <xref:System.Windows.Media.Animation.Timeline.Completed>事件第一次处理，因为它由根时间线触发 (第一个<xref:System.Windows.Media.Animation.Storyboard>)。 在此期间，<xref:System.Windows.Media.TranslateTransform.X%2A>属性仍返回其动画的值，因为它尚且有效。 第二个<xref:System.Windows.Media.Animation.Storyboard>使用缓存的值作为其起始值和开始进行动画处理。  
  
<a name="performancesection"></a>   
## <a name="performance"></a>性能  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>在导航离开页面后动画继续运行  
 当您导航离开<xref:System.Windows.Controls.Page>包含正在运行的动画，则这些动画将继续播放，直到<xref:System.Windows.Controls.Page>进行垃圾回收。 根据正在使用的导航系统，导航离开的页面可能无限期地保留在内存中，在此期间始终通过动画消耗资源。 当页面包含不断运行的（“氛围”）动画时，这一点最明显。  
  
 为此，它是一个好办法使用<xref:System.Windows.FrameworkElement.Unloaded>事件来移除动画，当你离开页面。  
  
 删除动画有多种不同的方法。 可以使用以下方法来移除属于的动画<xref:System.Windows.Media.Animation.Storyboard>。  
  
-   若要删除<xref:System.Windows.Media.Animation.Storyboard>入门事件的触发器，请参阅[如何： 删除情节提要](http://msdn.microsoft.com/library/7fe39531-de2f-46a0-a69f-b783d04235ee)。  
  
-   若要使用代码以删除<xref:System.Windows.Media.Animation.Storyboard>，请参阅<xref:System.Windows.Media.Animation.Storyboard.Remove%2A>方法。  
  
 无论动画如何启动，都可以使用下一个技术。  
  
-   若要从特定的属性中删除动画，使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>方法。 指定正进行动画处理的第一个参数的属性和`null`为第二个。 这将从该属性中删除所有动画时钟。  
  
 属性进行动画处理的不同方法的详细信息，请参阅[属性动画技术概述](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)。  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>使用组合 HandoffBehavior 会消耗系统资源  
 当你将<xref:System.Windows.Media.Animation.Storyboard>， <xref:System.Windows.Media.Animation.AnimationTimeline>，或<xref:System.Windows.Media.Animation.AnimationClock>属性使用<xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior>、 任何<xref:System.Windows.Media.Animation.Clock>以前与该属性关联的对象可继续使用系统资源; 计时系统不会自动删除这些时钟。  
  
 若要避免出现性能问题，当应用大量使用的时钟<xref:System.Windows.Media.Animation.HandoffBehavior.Compose>，完成后，应从属性的基值移除组合时钟。 删除时钟有多种方法。  
  
-   若要从属性中移除所有时钟，请使用<xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29>或<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>动画对象的方法。 指定正进行动画处理的第一个参数的属性和`null`为第二个。 这将从该属性中删除所有动画时钟。  
  
-   若要删除特定<xref:System.Windows.Media.Animation.AnimationClock>时钟的列表，从使用<xref:System.Windows.Media.Animation.Clock.Controller%2A>属性<xref:System.Windows.Media.Animation.AnimationClock>检索<xref:System.Windows.Media.Animation.ClockController>，然后调用<xref:System.Windows.Media.Animation.ClockController.Remove%2A>方法<xref:System.Windows.Media.Animation.ClockController>。 这通常是<xref:System.Windows.Media.Animation.Clock.Completed>时钟的事件处理程序。 请注意，仅根时钟可以受<xref:System.Windows.Media.Animation.ClockController>;<xref:System.Windows.Media.Animation.Clock.Controller%2A>子时钟属性将返回`null`。 另请注意，<xref:System.Windows.Media.Animation.Clock.Completed>如果时钟的有效持续时间都是永久性的不会调用事件。  在这种情况下，用户将需要确定何时调用<xref:System.Windows.Media.Animation.ClockController.Remove%2A>。  
  
 此动画问题主要出现在生存期较长的对象上。  当对某个对象进行垃圾回收时，它的时钟也会断开连接并进行垃圾回收。  
  
 有关时钟对象的详细信息，请参阅[动画和计时系统概述](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
