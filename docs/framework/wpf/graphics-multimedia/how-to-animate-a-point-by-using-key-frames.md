---
title: "如何：使用关键帧对点进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f574f85a5840e8bbe2d6c026d57a4cc28bd8a797
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a>如何：使用关键帧对点进行动画处理
此示例演示如何使用<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Point>。  
  
## <a name="example"></a>示例  
 以下示例沿三角形路径移动椭圆形。 该示例使用<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性<xref:System.Windows.Media.EllipseGeometry>。 此动画按以下方式使用三个关键帧：  
  
1.  第一个半秒内使用的是实例<xref:System.Windows.Media.Animation.LinearPointKeyFrame>类以恒定速率将沿路径椭圆，从它的起始位置。 之类的线性的关键帧<xref:System.Windows.Media.Animation.LinearPointKeyFrame>创建平滑的线性内插值之间。  
  
2.  在下一步的末尾半秒，将使用的实例<xref:System.Windows.Media.Animation.DiscretePointKeyFrame>类突然将椭圆沿路径移动到下一个位置。 之类的离散的关键帧<xref:System.Windows.Media.Animation.DiscretePointKeyFrame>突变值。  
  
3.  在最终的两秒内，使用的是实例<xref:System.Windows.Media.Animation.SplinePointKeyFrame>类将椭圆移回其起始位置。 之类的样条关键帧<xref:System.Windows.Media.Animation.SplinePointKeyFrame>创建变量的值根据值之间转换<xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A>属性。 在此示例中，动画开始时较为缓慢，然后以指数方式加速，直到时间段结束。  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。  
  
 与其他动画示例保持一致，对于此示例的代码版本使用<xref:System.Windows.Media.Animation.Storyboard>要应用对象<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>。 但是，当应用单个动画在代码中的，这是使用简单得多<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法而不是使用<xref:System.Windows.Media.Animation.Storyboard>。 有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.EllipseGeometry>  
 [关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [关键帧操作说明主题](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
