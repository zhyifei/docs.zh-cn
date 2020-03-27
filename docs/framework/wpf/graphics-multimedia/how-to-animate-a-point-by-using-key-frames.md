---
title: 如何：使用关键帧对点进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: edcba36644cf78d6e98f934d9bd8b593af38b328
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344878"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a>如何：使用关键帧对点进行动画处理
此示例演示如何使用 类<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>为 。 <xref:System.Windows.Point>  
  
## <a name="example"></a>示例  
 以下示例沿三角形路径移动椭圆形。 该示例使用<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>类对 属性<xref:System.Windows.Media.EllipseGeometry.Center%2A><xref:System.Windows.Media.EllipseGeometry>进行动画处理。 此动画按以下方式使用三个关键帧：  
  
1. 在前半秒，使用<xref:System.Windows.Media.Animation.LinearPointKeyFrame>类的实例以稳定速率从起始位置沿路径移动椭圆。 线性关键帧（<xref:System.Windows.Media.Animation.LinearPointKeyFrame>如在值之间创建平滑线性插值）。  
  
2. 在下半秒结束时，使用<xref:System.Windows.Media.Animation.DiscretePointKeyFrame>类的实例突然沿路径将椭圆移动到下一个位置。 离散的关键帧（<xref:System.Windows.Media.Animation.DiscretePointKeyFrame>如在值之间创建突然跳转）  
  
3. 在最后两秒钟内，使用<xref:System.Windows.Media.Animation.SplinePointKeyFrame>类的实例将椭圆移回其起始位置。 样条线键帧，<xref:System.Windows.Media.Animation.SplinePointKeyFrame>如根据<xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A>属性的值在值之间创建可变转换。 在此示例中，动画开始时较为缓慢，然后以指数方式加速，直到时间段结束。  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
 为了与其他动画示例保持一致，此示例的代码版本使用<xref:System.Windows.Media.Animation.Storyboard>对象来应用 。 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> 但是，在代码中应用单个动画时，使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法而不是 使用 更简单。 <xref:System.Windows.Media.Animation.Storyboard> 有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
