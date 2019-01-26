---
title: 如何：提高 TreeView 的性能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: 3c7bd151e1c8a5f318660cc45702b5b9c98534a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500689"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>如何：提高 TreeView 的性能
如果<xref:System.Windows.Controls.TreeView>包含很多项所花费的时间量可能会导致明显的延迟导致用户界面中。 可以通过设置缩短加载时间`VirtualizingStackPanel.IsVirtualizing`附加属性设置为`true`。  UI 也可能较慢时用户滚动做出反应<xref:System.Windows.Controls.TreeView>通过使用鼠标滚轮或拖动滚动条的滚动块。 您可以提高的性能<xref:System.Windows.Controls.TreeView>通过设置在用户滚动时`VirtualizingStackPanel.VirtualizationMode`附加属性设置为<xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>。  
  
## <a name="example"></a>示例  
  
## <a name="description"></a>描述  
下面的示例创建<xref:System.Windows.Controls.TreeView>，用于设置`VirtualizingStackPanel.IsVirtualizing`附加属性设置为 true 并`VirtualizingStackPanel.VirtualizationMode`附加到属性<xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>以优化其性能。  
  
## <a name="code"></a>代码  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 下面的示例显示了前面的示例使用的数据。  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>请参阅
- [控件](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
