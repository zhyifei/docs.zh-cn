---
title: 如何：使用关键帧对边框的粗细进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 884b62e88c347449ae39caa9c028d09db39b9f4b
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344693"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>如何：使用关键帧对边框的粗细进行动画处理
此示例演示如何为<xref:System.Windows.Controls.Control.BorderThickness%2A>属性设置动画<xref:System.Windows.Controls.Border>。  
  
## <a name="example"></a>示例  
 下面的示例使用 类<xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>为 属性<xref:System.Windows.Controls.Border>设置<xref:System.Windows.Controls.Control.BorderThickness%2A>动画。 此动画按以下方式使用三个关键帧：  
  
1. 在上半部，使用<xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>类实例逐渐增加边框的厚度。 该示例用于<xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>在值之间创建平滑线性增加。  
  
2. 在下半秒结束时，使用<xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>类的实例突然增加边框的厚度。 离散的关键帧，如那些派生<xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>自创建值之间的突然跳转，即动画的运动是抖动的。  
  
3. 在最后两秒钟内，使用<xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>类的实例来减小边框的厚度。 样条线键帧（如从派生<xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>中派生的帧）根据<xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A>属性的值在值之间创建可变转换。 在此关键帧中，动画开始时缓慢，然后以指数方式加速，直到时间段结束。  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
- [对 BorderThickness 值进行动画处理](../controls/how-to-animate-a-borderthickness-value.md)
