---
title: "如何：使用关键帧针对对象进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71feb0ecef7a6356c95b843fbc2657ad2e4a7996
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>如何：使用关键帧针对对象进行动画处理
此示例演示如何进行动画处理的对象，它在此示例中为<xref:System.Windows.Controls.Page.Background%2A>属性<xref:System.Windows.Controls.Page>控件，通过使用关键帧。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>颜色进行动画处理的类更改<xref:System.Windows.Controls.Page.Background%2A>属性<xref:System.Windows.Controls.Page>控件。 示例动画定期将更改为不同的背景画笔。 此动画使用<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>类，以创建三个不同的关键帧。 动画按以下方式使用关键帧：  
  
1.  在第一秒结束时，进行动画处理的实例<xref:System.Windows.Media.LinearGradientBrush>类。 此部分的示例适用范围线性渐变的背景色，以便颜色从黄色转换为红色的橙色。  
  
2.  在下一步的第二个结束时，进行动画处理的实例<xref:System.Windows.Media.RadialGradientBrush>类。 此部分的示例适用范围径向渐变的背景色，以便从空白为蓝色为黑色转换颜色。  
  
3.  在第三个第二个结束时，进行动画处理的实例<xref:System.Windows.Media.DrawingBrush>类。 此部分的示例适用于后台呈现为棋盘样式。  
  
4.  动画将重新开始计算，无限期地重复。  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>是你可以使用的关键帧的唯一类型<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>类。 关键帧如<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>值，即创建突然变化、 突然发生在此示例中的颜色更改。  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.Page.Background%2A>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>  
 <xref:System.Windows.Media.LinearGradientBrush>  
 <xref:System.Windows.Media.RadialGradientBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 [关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [关键帧操作说明主题](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
