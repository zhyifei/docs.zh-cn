---
title: 如何：使用关键帧对矩形几何形状进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344682"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>如何：使用关键帧对矩形几何形状进行动画处理
此示例演示如何使用关键帧对<xref:System.Windows.Media.RectangleGeometry.Rect%2A>属性<xref:System.Windows.Media.RectangleGeometry>进行动画处理。  
  
## <a name="example"></a>示例  
 下面的示例使用 类<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>为 属性<xref:System.Windows.Media.RectangleGeometry>设置<xref:System.Windows.Media.RectangleGeometry.Rect%2A>动画。 此动画按以下方式使用三个关键帧：  
  
1. 在前两秒钟内<xref:System.Windows.Media.Animation.LinearRectKeyFrame>，使用类的实例对矩形的位置、宽度和高度进行动画处理。 线性关键帧（<xref:System.Windows.Media.Animation.LinearRectKeyFrame>如在值之间创建平滑线性过渡）  
  
2. 在下半秒结束时，使用<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>类的实例突然降低矩形的高度。 离散的关键帧（<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>如在值之间创建突然变化）表示，高度的降低会迅速发生，并且不微妙。  
  
3. 在最后两秒钟内<xref:System.Windows.Media.Animation.SplineRectKeyFrame>，使用类的实例将矩形更改回其原始大小和位置。 样条线键帧，<xref:System.Windows.Media.Animation.SplineRectKeyFrame>如根据<xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A>属性的值在值之间创建可变转换。 在此示例中，变化开始时缓慢，然后以指数级加速，直到时间段结束。  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
