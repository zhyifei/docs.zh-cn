---
title: 如何：使用关键帧对对象进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: ffbe1845b634c8f94eb6a10dfa44fcf9903e0cd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933912"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>如何：使用关键帧对对象进行动画处理
此示例演示如何使用关键帧对对象 (在此示例中为<xref:System.Windows.Controls.Page.Background%2A> <xref:System.Windows.Controls.Page>控件的属性) 进行动画处理。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>类对<xref:System.Windows.Controls.Page>控件的<xref:System.Windows.Controls.Page.Background%2A>属性的颜色更改进行动画处理。 该示例动画会按固定的时间间隔更改为不同的背景画笔。 此动画使用<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>类创建三个不同的关键帧。 动画按以下方式使用关键帧:  
  
1. 在第一秒结束时, 对<xref:System.Windows.Media.LinearGradientBrush>类的实例进行动画处理。 此部分示例对背景色应用线性渐变, 使颜色从黄色转换为橙色。  
  
2. 在下一秒结束时, 对<xref:System.Windows.Media.RadialGradientBrush>类的实例进行动画处理。 此部分示例对背景色应用径向渐变, 使颜色从白色过渡到蓝色。  
  
3. 在第三秒结束时, 对<xref:System.Windows.Media.DrawingBrush>类的实例进行动画处理。 此部分示例将棋盘模式应用于背景。  
  
4. 动画将再次开始, 并无限期地重复。  
  
> [!NOTE]
> <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>是唯一可与<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>类一起使用的关键帧类型。 关键帧 ( <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>如创建值的突然变化) 即, 此示例中的颜色更改突然发生。  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。  
  
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
