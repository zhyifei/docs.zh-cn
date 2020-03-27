---
title: 如何：使用关键帧针对对象进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0bc33b189fd856dbe8106c1db35bc18e27ea131e
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344708"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>如何：使用关键帧针对对象进行动画处理
此示例演示如何使用关键帧为对象设置动画，在此示例中，对象是<xref:System.Windows.Controls.Page.Background%2A><xref:System.Windows.Controls.Page>控件的属性。  
  
## <a name="example"></a>示例  
 下面的示例使用 类<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>为控件<xref:System.Windows.Controls.Page.Background%2A>的属性的颜色更改设置<xref:System.Windows.Controls.Page>动画。 示例动画会定期更改为不同的背景画笔。 此动画使用<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>类创建三个不同的关键帧。 动画使用关键帧的方式如下：  
  
1. 在第一秒结束时，为<xref:System.Windows.Media.LinearGradientBrush>类的实例设置动画。 此示例的这一部分将线性渐变应用于背景颜色，以便颜色从黄色转换为橙色转换为红色。  
  
2. 在下一秒结束时，为<xref:System.Windows.Media.RadialGradientBrush>类的实例设置动画。 此示例的这一部分将径向渐变应用于背景颜色，以便颜色从白色转换为蓝色转换为黑色。  
  
3. 在第三秒结束时，为<xref:System.Windows.Media.DrawingBrush>类的实例设置动画。 此示例的这一部分将棋盘图案应用于背景。  
  
4. 动画再次开始并无限期重复。  
  
> [!NOTE]
> <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>是可用于<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>类的唯一类型的关键帧。 关键帧（<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>如创建值的突然更改）即此示例中的颜色更改突然发生。  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
