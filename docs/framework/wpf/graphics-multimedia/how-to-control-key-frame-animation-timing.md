---
title: 如何：控制关键帧动画的计时
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344739"
---
# <a name="how-to-control-key-frame-animation-timing"></a>如何：控制关键帧动画的计时

此示例演示如何控制关键帧动画中关键帧的计时。 与其他动画一样，关键帧动画具有属性<xref:System.Windows.Media.Animation.Timeline.Duration%2A>。 除了指定动画的持续时间外，还需要指定将该持续时间的哪一部分分配给其每个关键帧。 要指定时间，请为动画中的每个关键<xref:System.Windows.Media.Animation.KeyTime>帧指定 a。

每个<xref:System.Windows.Media.Animation.KeyTime>关键帧指定关键帧何时结束（它不指定关键帧播放的时间长度）。 <xref:System.Windows.Media.Animation.KeyTime>您可以将 指定<xref:System.TimeSpan>为值、百分比或 或<xref:System.Windows.Media.Animation.KeyTime.Uniform%2A><xref:System.Windows.Media.Animation.KeyTime.Paced%2A>特殊值。

## <a name="example"></a>示例

下面的示例使用<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>在屏幕上为矩形设置动画。 关键帧的键时间设置的值<xref:System.TimeSpan>。

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

下图显示了何时达到每个关键帧的值。

![在 3、4 和 10 秒时达到的关键值](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")

下一个示例显示相同的动画，只不过关键帧的键时间设置的百分比值。

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

下图显示了何时达到每个关键帧的值。

![在 3、4 和 10 秒时达到的关键值](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")

下一个示例<xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>使用关键时间值。

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

下图显示了何时达到每个关键帧的值。

![在 3.3、6.6 和 9.9 秒时达到的关键值](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")

最后一个示例<xref:System.Windows.Media.Animation.KeyTime.Paced%2A>使用关键时间值。

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

下图显示了何时达到每个关键帧的值。

![在 0、5 和 10 秒时达到的关键值](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")

为简单起见，此示例的代码版本使用本地动画，而不是情节提要，因为只有单个动画应用于单个属性，但可以修改示例以改用情节提要。 有关如何在代码中声明情节提要的示例，请参阅[使用情节提要对属性进行动画处理](how-to-animate-a-property-by-using-a-storyboard.md)。

有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。 有关关键帧动画的详细信息，请参阅[关键帧动画概述](key-frame-animations-overview.md)。

## <a name="see-also"></a>请参阅

- [关键帧动画概述](key-frame-animations-overview.md)
- [动画概述](animation-overview.md)
- [帮助主题](animation-and-timing-how-to-topics.md)
