---
title: "如何：设置元素的高度属性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ae66e60375cfbc45a4f1e8834b6420bc5c0b70a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>如何：设置元素的高度属性
## <a name="example"></a>示例  
 此示例以可视方式显示在之间的四个高度相关的属性中的呈现行为的差异[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]。  
  
 <xref:System.Windows.FrameworkElement>类公开描述的元素的高度特征的四个属性。 这四个属性可能会发生冲突，并且当他们执行，将优先的值确定，如下所示：<xref:System.Windows.FrameworkElement.MinHeight%2A>值优先于<xref:System.Windows.FrameworkElement.MaxHeight%2A>值，后者又优先于<xref:System.Windows.FrameworkElement.Height%2A>值。 第四个属性， <xref:System.Windows.FrameworkElement.ActualHeight%2A>，是只读的并将报告由与在布局流程交互的实际高度。  
  
 以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]示例绘制<xref:System.Windows.Shapes.Rectangle>元素 (`rect1`) 的子级<xref:System.Windows.Controls.Canvas>。 你可以更改的高度属性<xref:System.Windows.Shapes.Rectangle>通过使用一系列<xref:System.Windows.Controls.ListBox>表示的属性值的元素<xref:System.Windows.FrameworkElement.MinHeight%2A>， <xref:System.Windows.FrameworkElement.MaxHeight%2A>，和<xref:System.Windows.FrameworkElement.Height%2A>。 这种方式，可以直观地显示每个属性的优先级。  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 下面的代码隐藏示例处理事件的<xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>事件引发。 每个处理程序将使用从输入<xref:System.Windows.Controls.ListBox>，将值作为分析<xref:System.Double>，并将值应用于指定高度相关的属性。 高度值也是转换为字符串，并且写入到各种<xref:System.Windows.Controls.TextBlock>（这些元素的定义未显示在所选 XAML） 的元素。  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 有关完整的示例，请参阅[高度属性示例](http://go.microsoft.com/fwlink/?LinkID=159993)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.ActualHeight%2A>  
 <xref:System.Windows.FrameworkElement.MaxHeight%2A>  
 <xref:System.Windows.FrameworkElement.MinHeight%2A>  
 <xref:System.Windows.FrameworkElement.Height%2A>  
 [设置元素的宽度属性](../../../../docs/framework/wpf/controls/how-to-set-the-width-properties-of-an-element.md)  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [高度属性示例](http://go.microsoft.com/fwlink/?LinkID=159993)
