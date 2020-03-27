---
title: 如何：使用关键帧对双精度属性值进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
ms.openlocfilehash: 9eab794cc8411230226cddc97beaa13c1bdd9405
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344933"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>如何：使用关键帧对双精度属性值进行动画处理
此示例演示如何使用关键帧对 获取 的属性<xref:System.Double>的值设置动画。  
  
## <a name="example"></a>示例  
 以下示例将在屏幕上移动矩形。 该示例使用<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>类为应用于<xref:System.Windows.Media.TranslateTransform.X%2A>的属性<xref:System.Windows.Media.TranslateTransform>设置动画<xref:System.Windows.Shapes.Rectangle>。 此无限重复的动画通过以下方式使用三个关键帧：  
  
1. 在前三秒内，使用<xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>类的实例以稳定速率沿路径移动矩形，从起始位置移动到 500 位置。 线性关键帧（<xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>如在值之间创建平滑线性过渡）  
  
2. 在第四秒结束时，使用<xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>类的实例突然将矩形移动到下一个位置。 离散的关键帧（<xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>如在值之间创建突然跳转） 在该示例中，矩形位于起始位置，然后突然出现在 500 位置。  
  
3. 在最后两秒钟中，使用类的<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>实例将矩形移回其起始位置。 样条线键帧，<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>如根据<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>属性的值在值之间创建可变转换。 在本示例中，矩形开始时缓慢移动，然后以指数级加速，直到时间段结束。  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
 为了与其他动画示例保持一致，此示例的代码版本使用<xref:System.Windows.Media.Animation.Storyboard>对象来应用 。 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 或者，在代码中应用单个动画时，使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法而不是 使用 更简单。 <xref:System.Windows.Media.Animation.Storyboard> 有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Shapes.Rectangle>
- <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
