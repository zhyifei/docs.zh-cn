---
title: 如何：对元素或画笔的不透明度进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
ms.openlocfilehash: 2f18861eb18f81b631245d1d933b7acb1b3e0e42
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950511"
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>如何：对元素或画笔的不透明度进行动画处理
若要使框架元素淡入和淡出视图, 可以对其<xref:System.Windows.UIElement.Opacity%2A>属性进行动画处理, 也可以对用于绘制它的<xref:System.Windows.Media.Brush> (或画笔) <xref:System.Windows.Media.Brush.Opacity%2A>属性进行动画处理。 对元素的不透明度进行动画处理会使其及其子级淡入和淡出视图, 但对用于绘制元素的画笔进行动画处理使你可以更好地了解元素的哪部分淡化。 例如, 您可以对用于绘制按钮背景的画笔的不透明度进行动画处理。 这会导致按钮的背景淡入和淡出, 同时使其文本完全不透明。  
  
> [!NOTE]
> 对 a 的属性<xref:System.Windows.Media.Brush>进行动画处理可提供性能<xref:System.Windows.UIElement.Opacity%2A>优势, 而不是对元素的属性进行动画处理。 <xref:System.Windows.Media.Brush.Opacity%2A>  
  
 在下面的示例中, 将对两个按钮进行动画处理, 使其淡入和淡出查看。 第一<xref:System.Windows.Controls.Button>种的不透明度在5秒`0.0`内<xref:System.Windows.Media.Animation.Timeline.Duration%2A>从`1.0`到的动画处理。 第二个按钮还进行了动画处理, 但用于绘制它<xref:System.Windows.Controls.Control.Background%2A>的 system.windows.media.solidcolorbrush> 的不透明度是动画的, 而不是整个按钮的不透明度。 运行该示例时, 第一个按钮会完全淡入和移出视图, 而只有第二个按钮的背景淡入和淡出视图。 其文本和边框保持完全不透明。  
  
## <a name="example"></a>示例  
 [!code-xaml[timingbehaviors_snip#10](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 此示例中省略了代码。 完整示例还演示如何对<xref:System.Windows.Media.Color> <xref:System.Windows.Media.LinearGradientBrush>中的的不透明度进行动画处理。  有关完整示例, 请参阅对[元素示例的不透明度进行动画处理](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/OpacityAnimation)。
