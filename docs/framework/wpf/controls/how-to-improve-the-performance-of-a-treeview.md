---
title: "如何：提高 TreeView 的性能"
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
helpviewer_keywords: TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 209f2c5645758aba4d1e10fc36fe773faa975e6b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
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
  
## <a name="see-also"></a>另请参阅  
 [控件](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
