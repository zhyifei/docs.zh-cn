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
ms.openlocfilehash: 581dc89d21091ad0ce856d7a7ced84fd7bcea9d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559277"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>如何：使用关键帧对矩形几何形状进行动画处理
此示例演示如何进行动画处理<xref:System.Windows.Media.RectangleGeometry.Rect%2A>属性<xref:System.Windows.Media.RectangleGeometry>使用关键帧。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.RectangleGeometry.Rect%2A>属性<xref:System.Windows.Media.RectangleGeometry>。 此动画按以下方式使用三个关键帧：  
  
1.  在第一个的两秒内，使用的是实例<xref:System.Windows.Media.Animation.LinearRectKeyFrame>类进行动画处理逐步更改位置、 宽度和高度的矩形。 之类的线性的关键帧<xref:System.Windows.Media.Animation.LinearRectKeyFrame>创建平滑的值之间的线性转换。  
  
2.  在下一步的末尾半秒，将使用的实例<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>类突然减小的矩形的高度。 之类的离散的关键帧<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>突变值，即，高度减小快速发生的不是细微。  
  
3.  在最终的两秒内，使用的是实例<xref:System.Windows.Media.Animation.SplineRectKeyFrame>类要更改回为其原始大小和位置的矩形。 之类的样条关键帧<xref:System.Windows.Media.Animation.SplineRectKeyFrame>创建变量的值根据值之间转换<xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A>属性。 在此示例中，变化开始时缓慢，然后以指数级加速，直到时间段结束。  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.RectangleGeometry>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>  
 [关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [关键帧操作说明主题](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
