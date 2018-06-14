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
ms.openlocfilehash: 4adeb858ab1b69ef1b00f7bf3b6868dbcbbc4154
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557428"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>如何：使用关键帧对双精度属性值进行动画处理
此示例演示如何采用的属性值进行动画处理<xref:System.Double>使用关键帧。  
  
## <a name="example"></a>示例  
 以下示例将在屏幕上移动矩形。 该示例使用<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.TranslateTransform.X%2A>属性<xref:System.Windows.Media.TranslateTransform>应用于<xref:System.Windows.Shapes.Rectangle>。 此无限重复的动画通过以下方式使用三个关键帧：  
  
1.  在第一个三秒内，使用的是实例<xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>类将沿路径矩形以恒定速率从它的起始位置到 500 的位置。 之类的线性的关键帧<xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>创建平滑的值之间的线性转换。  
  
2.  在第四个第二个结束时，使用的是实例<xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>类突然移动到下一个位置的矩形。 之类的离散的关键帧<xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>突变值。 在该示例中，矩形位于起始位置，然后突然出现在 500 位置。  
  
3.  在最后两秒内，使用的实例<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>类将矩形移回其起始位置。 之类的样条关键帧<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>创建变量的值根据值之间转换<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>属性。 在本示例中，矩形开始时缓慢移动，然后以指数级加速，直到时间段结束。  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。  
  
 与其他动画示例保持一致，对于此示例的代码版本使用<xref:System.Windows.Media.Animation.Storyboard>要应用对象<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>。 或者，应用单个动画时在代码中，它是使用简单得多<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法而不是使用<xref:System.Windows.Media.Animation.Storyboard>。 有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Shapes.Rectangle>  
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>  
 [关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [关键帧操作说明主题](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
