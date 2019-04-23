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
ms.openlocfilehash: 03953b79127ffceeb49e4ece2070d09f382448a5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311339"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>如何：使用关键帧对矩形几何形状进行动画处理
此示例演示如何进行动画处理<xref:System.Windows.Media.RectangleGeometry.Rect%2A>属性的<xref:System.Windows.Media.RectangleGeometry>使用关键帧。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.RectangleGeometry.Rect%2A>属性的<xref:System.Windows.Media.RectangleGeometry>。 此动画按以下方式使用三个关键帧：  
  
1. 在前两秒中，使用的实例<xref:System.Windows.Media.Animation.LinearRectKeyFrame>类进行动画处理中的位置、 宽度和的矩形的高度变化。 之类的线性关键帧<xref:System.Windows.Media.Animation.LinearRectKeyFrame>创建值之间平滑的线性转换。  
  
2. 在结束时的下一个前半秒中，使用的实例<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>类突然降低矩形的高度。 之类的离散关键帧<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>之间创建突然变化的值，也就是说，快速发生高度减小，而不是。  
  
3. 在最后两秒内，使用的实例<xref:System.Windows.Media.Animation.SplineRectKeyFrame>类将矩形更改回其原始大小和位置。 之类的自由绘制曲线关键帧<xref:System.Windows.Media.Animation.SplineRectKeyFrame>创建根据的值在值之间的变量转换<xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A>属性。 在此示例中，变化开始时缓慢，然后以指数级加速，直到时间段结束。  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
