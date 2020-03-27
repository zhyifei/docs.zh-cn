---
title: 如何：使用关键帧对颜色进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344752"
---
# <a name="how-to-animate-color-by-using-key-frames"></a>如何：使用关键帧对颜色进行动画处理
此示例演示如何使用关键帧对<xref:System.Windows.Media.SolidColorBrush.Color%2A>的<xref:System.Windows.Media.SolidColorBrush>动画设置。  
  
## <a name="example"></a>示例  
 下面的示例使用 类<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>为 属性<xref:System.Windows.Media.SolidColorBrush>设置<xref:System.Windows.Media.SolidColorBrush.Color%2A>动画。 此动画按以下方式使用三个关键帧：  
  
1. 在前两秒钟中<xref:System.Windows.Media.Animation.LinearColorKeyFrame>，使用类的实例逐渐将颜色从绿色更改为红色。 线性关键帧（<xref:System.Windows.Media.Animation.LinearColorKeyFrame>如在值之间创建平滑线性过渡）  
  
2. 在下半秒结束时，使用<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>类的实例快速将颜色从红色更改为黄色。 离散的关键帧（<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>如在值之间创建突然变化）表示，动画的这一部分中的颜色变化会迅速发生，并且不微妙。  
  
3. 在最后两秒钟内<xref:System.Windows.Media.Animation.SplineColorKeyFrame>，使用类的实例再次更改颜色 - 这一次从黄色返回为绿色。 样条线键帧，<xref:System.Windows.Media.Animation.SplineColorKeyFrame>如根据<xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A>属性的值在值之间创建可变转换。 在此示例中，颜色变化开始时缓慢，然后以指数方式加速，直到时间段结束。  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
