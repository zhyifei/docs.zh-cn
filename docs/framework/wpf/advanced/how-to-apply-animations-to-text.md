---
title: 如何：向文本应用动画
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: ed2f3beb904f724ac93e2c4033aa6b2eb3fa1290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174623"
---
# <a name="how-to-apply-animations-to-text"></a>如何：向文本应用动画
动画可以更改应用程序中文本的显示和外观。 以下示例使用不同类型的动画来影响<xref:System.Windows.Controls.TextBlock>控件中文本的显示。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.Animation.DoubleAnimation>为文本块的宽度设置动画。 宽度值从文本块的宽度更改为 0，持续时间为 10 秒，然后再改回其宽度值并继续。 这种动画会创建一个擦除效果。  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 下面的示例使用 动画<xref:System.Windows.Media.Animation.DoubleAnimation>处理文本块的不动性。 不透明度值从 1.0 更改为 0，持续时间为 5 秒，然后再改回其不透明度值并继续。  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 下图显示了<xref:System.Windows.Controls.TextBlock>控件在 定义的 5 秒间隔`1.00``0.00`内将其不恰当性更改为的效果。 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>  
  
 ![文本将不一性从 1.00 更改为 0.00。](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  

 下面的示例使用<xref:System.Windows.Media.Animation.ColorAnimation>为文本块的前景颜色设置动画。 前景色值从一种颜色更改为另一种颜色，持续时间为 5 秒，然后返回到原来的颜色值并继续。  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 下面的示例使用 旋转<xref:System.Windows.Media.Animation.DoubleAnimation>文本块。 文本块旋转一圈，持续时间为 20 秒，然后继续重复该旋转。  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>另请参阅

- [动画概述](../graphics-multimedia/animation-overview.md)
