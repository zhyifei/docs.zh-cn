---
title: 如何：设置元素的高度属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: 6500af3c637092820e538d79894d600d617953bf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124281"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>如何：设置元素的高度属性
## <a name="example"></a>示例  
 此示例直观地显示了 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]中四个与高度相关的属性之间的呈现行为差异。  
  
 <xref:System.Windows.FrameworkElement> 类公开了四个属性，这些属性描述元素的高度特性。 这四个属性可能会发生冲突，当发生这种情况时，将按如下所示确定优先级值： <xref:System.Windows.FrameworkElement.MinHeight%2A> 值优先于 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 值，而后者又优先于 <xref:System.Windows.FrameworkElement.Height%2A> 值。 第四个属性 <xref:System.Windows.FrameworkElement.ActualHeight%2A>为只读，并报告与布局过程的交互确定的实际高度。  
  
 以下 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 示例将 <xref:System.Windows.Shapes.Rectangle> 元素（`rect1`）绘制为 <xref:System.Windows.Controls.Canvas>的子项。 您可以通过使用一系列表示 <xref:System.Windows.FrameworkElement.MinHeight%2A>、<xref:System.Windows.FrameworkElement.MaxHeight%2A>和 <xref:System.Windows.FrameworkElement.Height%2A>属性值的 <xref:System.Windows.Controls.ListBox> 元素，来更改 <xref:System.Windows.Shapes.Rectangle> 的高度属性。 通过这种方式，可直观显示每个属性的优先级。  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 下面的代码隐藏示例处理 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 事件引发的事件。 每个处理程序都从 <xref:System.Windows.Controls.ListBox>获取输入，将值分析为 <xref:System.Double>，并将值应用于指定的与高度相关的属性。 高度值还会转换为字符串并写入各种 <xref:System.Windows.Controls.TextBlock> 元素（所选 XAML 中不显示这些元素的定义）。  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 有关完整示例，请参阅[高度属性示例](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [设置元素的宽度属性](how-to-set-the-width-properties-of-an-element.md)
- [面板概述](panels-overview.md)
- [Height 属性示例](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)
