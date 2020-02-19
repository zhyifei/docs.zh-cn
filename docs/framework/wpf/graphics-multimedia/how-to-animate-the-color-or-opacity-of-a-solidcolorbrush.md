---
title: 如何：对 SolidColorBrush 的颜色或不透明度进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 08b85935e0cb1ababd1fb63b9d02518ea3fcfa17
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452878"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>如何：对 SolidColorBrush 的颜色或不透明度进行动画处理
此示例演示如何对 <xref:System.Windows.Media.SolidColorBrush>的 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 和 <xref:System.Windows.Media.Brush.Opacity%2A> 进行动画处理。  
  
## <a name="example"></a>示例  
 下面的示例使用三个动画对 <xref:System.Windows.Media.SolidColorBrush>的 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 和 <xref:System.Windows.Media.Brush.Opacity%2A> 进行动画处理。  
  
- 第一个动画（<xref:System.Windows.Media.Animation.ColorAnimation>）会将画笔的颜色更改为鼠标进入矩形时 <xref:System.Windows.Media.Colors.Gray%2A>。  
  
- 接下来的动画（另一 <xref:System.Windows.Media.Animation.ColorAnimation>）会将画笔的颜色更改为鼠标离开矩形时 <xref:System.Windows.Media.Colors.Orange%2A>。  
  
- 当按下鼠标左键时，最后一个动画（<xref:System.Windows.Media.Animation.DoubleAnimation>）会将画笔的不透明度更改为0.0。  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 有关演示如何对不同类型的画笔进行动画处理的更完整示例，请参阅[画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。 有关动画的详细信息，请参阅[动画概述](animation-overview.md)。  
  
 为了与其他动画示例保持一致，此示例的代码版本使用 <xref:System.Windows.Media.Animation.Storyboard> 对象应用其动画。 但是，在代码中应用单个动画时，使用 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 方法比使用 <xref:System.Windows.Media.Animation.Storyboard>更为简单。 有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)。  
  
## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
- [演示图板概述](storyboards-overview.md)
- [画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
