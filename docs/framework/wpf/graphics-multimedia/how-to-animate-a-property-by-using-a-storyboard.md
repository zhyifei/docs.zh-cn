---
title: 如何：使用演示图板对属性进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: 6cfce9a5b070a23ed9ac03473888bf572b61393b
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559633"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>如何：使用演示图板对属性进行动画处理
此示例演示如何使用 <xref:System.Windows.Media.Animation.Storyboard> 来对属性进行动画处理。 若要使用 <xref:System.Windows.Media.Animation.Storyboard>对属性进行动画处理，请为要进行动画处理的每个属性创建一个动画，同时创建包含动画的 <xref:System.Windows.Media.Animation.Storyboard>。  
  
 属性类型确定要使用的动画类型。 例如，若要对采用 <xref:System.Double> 值的属性进行动画处理，请使用 <xref:System.Windows.Media.Animation.DoubleAnimation>。 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 和 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> 附加属性指定动画应用到的对象和属性。  
  
 若要在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中启动情节提要，请使用 <xref:System.Windows.Media.Animation.BeginStoryboard> 操作和 <xref:System.Windows.EventTrigger>。 <xref:System.Windows.EventTrigger> 在其 <xref:System.Windows.EventTrigger.RoutedEvent%2A> 属性所指定的事件发生时开始 <xref:System.Windows.Media.Animation.BeginStoryboard> 操作。 <xref:System.Windows.Media.Animation.BeginStoryboard> 操作将启动 <xref:System.Windows.Media.Animation.Storyboard>。  
  
 下面的示例使用 <xref:System.Windows.Media.Animation.Storyboard> 对象对两个 <xref:System.Windows.Controls.Button> 控件进行动画处理。 若要将第一个按钮更改为大小，则会对其 <xref:System.Windows.FrameworkElement.Width%2A> 进行动画处理。 若要使第二个按钮更改颜色，则 <xref:System.Windows.Media.SolidColorBrush> 的 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 属性用于设置已进行动画处理的按钮的 <xref:System.Windows.Controls.Control.Background%2A>。  
  
## <a name="example"></a>示例  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
> 尽管动画可以同时面向 <xref:System.Windows.FrameworkElement> 对象（如 <xref:System.Windows.Controls.Control> 或 <xref:System.Windows.Controls.Panel>）和 <xref:System.Windows.Freezable> 对象（如 <xref:System.Windows.Media.Brush> 或 <xref:System.Windows.Media.Transform>），但只有框架元素具有 <xref:System.Windows.FrameworkElement.Name%2A> 属性。 若要向 Freezable 分配名称以便动画可以针对它，请使用 [x:Name 指令](../../../desktop-wpf/xaml-services/xname-directive.md)，如前面的示例所示。  
  
 如果使用代码，则必须为 <xref:System.Windows.FrameworkElement> 创建 <xref:System.Windows.NameScope>，并注册要使用该 <xref:System.Windows.FrameworkElement>进行动画处理的对象的名称。 若要在代码中启动动画，请使用带有 <xref:System.Windows.EventTrigger><xref:System.Windows.Media.Animation.BeginStoryboard> 操作。 还可以选择使用事件处理程序和 <xref:System.Windows.Media.Animation.Storyboard>的 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 方法。 下面的示例显示如何使用 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 方法。  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 有关动画和情节提要的详细信息，请参阅[动画概述](animation-overview.md)。  
  
 如果使用代码，则不限于使用 <xref:System.Windows.Media.Animation.Storyboard> 对象来对属性进行动画处理。 有关详细信息和示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](how-to-animate-a-property-without-using-a-storyboard.md)和[使用 AnimationClock 对属性进行动画处理](how-to-animate-a-property-by-using-an-animationclock.md)。
