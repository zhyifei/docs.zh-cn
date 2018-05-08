---
title: 如何：使用 ScrollViewer 的内容滚动方法
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
ms.openlocfilehash: b4da666934be7dd182838d870e54e496b2646901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a>如何：使用 ScrollViewer 的内容滚动方法
此示例演示如何使用的滚动方法<xref:System.Windows.Controls.ScrollViewer>元素。 这些方法提供了增量滚动的内容，行或页上，在<xref:System.Windows.Controls.ScrollViewer>。  
  
## <a name="example"></a>示例  
 下面的示例创建<xref:System.Windows.Controls.ScrollViewer>名为`sv1`，它承载子<xref:System.Windows.Controls.TextBlock>元素。 因为<xref:System.Windows.Controls.TextBlock>大于父级<xref:System.Windows.Controls.ScrollViewer>，为了能够滚动显示滚动条。 <xref:System.Windows.Controls.Button> 其元素表示各种滚动方法停靠在单独的左侧<xref:System.Windows.Controls.StackPanel>。 每个<xref:System.Windows.Controls.Button>中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件调用控制滚动行为中的相关自定义方法<xref:System.Windows.Controls.ScrollViewer>。  
  
 [!code-xaml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 下面的示例使用<xref:System.Windows.Controls.ScrollViewer.LineUp%2A>和<xref:System.Windows.Controls.ScrollViewer.LineDown%2A>方法。  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.StackPanel>
