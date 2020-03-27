---
title: 如何：使用关键帧对大小变化进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344657"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>如何：使用关键帧对大小变化进行动画处理
此示例演示如何使用关键帧对大小变化进行动画处理。  
  
## <a name="example"></a>示例  
 下面的示例使用 类<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>为 属性<xref:System.Windows.Media.ArcSegment>设置<xref:System.Windows.Media.ArcSegment.Size%2A>动画。 此动画按以下方式使用三个关键帧：  
  
1. 在动画的前半秒，使用<xref:System.Windows.Media.Animation.LinearSizeKeyFrame>类的实例逐渐增加圆弧的大小。线性关键帧（<xref:System.Windows.Media.Animation.LinearSizeKeyFrame>如在值之间创建平滑线性过渡）  
  
2. 在下半秒结束时，使用<xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>类的实例突然增加圆弧的大小。离散的关键帧（<xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>如在值之间创建突然跳转），即大小更改突然发生，并且不微妙。  
  
3. 在最后两秒钟内<xref:System.Windows.Media.Animation.SplineSizeKeyFrame>，使用类的实例来增加圆弧的大小。样条线键帧，<xref:System.Windows.Media.Animation.SplineSizeKeyFrame>如根据<xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A>属性的值在值之间创建可变转换。 在本例中，弧的大小开始时缓慢增加，然后以指数方式增加，直到时间段结束。  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
