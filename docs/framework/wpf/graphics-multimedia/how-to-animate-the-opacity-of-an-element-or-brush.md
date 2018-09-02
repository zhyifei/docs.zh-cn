---
title: 如何：对元素或画笔的不透明度进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
ms.openlocfilehash: 549d3eab0d6d75403e962eeb146be8d7995cc931
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421797"
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>如何：对元素或画笔的不透明度进行动画处理
若要使框架元素淡入和移出视图，您可以动态显示其<xref:System.Windows.UIElement.Opacity%2A>属性也可以进行动画处理<xref:System.Windows.Media.Brush.Opacity%2A>属性的<xref:System.Windows.Media.Brush>（或画笔） 用来绘制它。 对元素的不透明度进行动画处理可以和其子淡入和移出视图中，但对用于绘制元素的画笔进行动画处理，可更谨慎淡元素的哪个部分。 例如，您无法对用于绘制按钮的背景画笔的不透明度进行动画处理。 这将导致该按钮的背景以淡入淡出视图，同时使其文本完全不透明。  
  
> [!NOTE]
>  对进行动画处理<xref:System.Windows.Media.Brush.Opacity%2A>的<xref:System.Windows.Media.Brush>相比进行动画处理的性能优势<xref:System.Windows.UIElement.Opacity%2A>元素的属性。  
  
 在以下示例中，两个按钮进行动画处理，以使它们淡入和移出视图。 第一个不透明度<xref:System.Windows.Controls.Button>从动画`1.0`到`0.0`转移<xref:System.Windows.Media.Animation.Timeline.Duration%2A>为五秒。 第二个按钮也进行动画处理，但 SolidColorBrush 的不透明度用来绘制其<xref:System.Windows.Controls.Control.Background%2A>而不是整个按钮的不透明度进行动画处理。 运行示例时，第一个按钮完全淡入淡出视图中，而只有第二个按钮的背景淡入淡出视图。 其文本和边框将保持完全不透明。  
  
## <a name="example"></a>示例  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 此示例中省略了代码。 完整的示例还演示如何进行动画处理的不透明度<xref:System.Windows.Media.Color>内<xref:System.Windows.Media.LinearGradientBrush>。  有关完整示例，请参阅[元素示例的不透明度进行动画处理](https://go.microsoft.com/fwlink/?LinkID=159968)。
