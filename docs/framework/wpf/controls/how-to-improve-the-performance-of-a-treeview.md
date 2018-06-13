---
title: 如何：提高 TreeView 的性能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: 75f17c770af89f08fedfd3c8193a916901fe6f79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552748"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>如何：提高 TreeView 的性能
如果<xref:System.Windows.Controls.TreeView>包含多个项，用户界面中，它所加载的时间量可能会导致较长的延迟。 你可以通过设置来缩短加载时间`VirtualizingStackPanel.IsVirtualizing`附加到属性`true`。  UI 还可能会很慢时在用户滚动做出反应<xref:System.Windows.Controls.TreeView>通过使用鼠标滚轮或拖动滚动条上的滚动块。 你可以提高的性能<xref:System.Windows.Controls.TreeView>通过设置在用户滚动时`VirtualizingStackPanel.VirtualizationMode`附加到属性<xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>。  
  
## <a name="example"></a>示例  
  
## <a name="description"></a>描述  
下面的示例创建<xref:System.Windows.Controls.TreeView>设置`VirtualizingStackPanel.IsVirtualizing`附加属性为 true 和`VirtualizingStackPanel.VirtualizationMode`附加到属性<xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>以优化其性能。  
  
## <a name="code"></a>代码  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 下面的示例显示了数据，使用前面的示例。  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>请参阅  
 [控件](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
