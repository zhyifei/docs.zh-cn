---
title: 如何：将 TreeView 绑定到深度无法确定的数据
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
ms.openlocfilehash: cd9a1ee015ebb707a7a06d1c062a1bb3003c96e8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458611"
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>如何：将 TreeView 绑定到深度无法确定的数据
有时可能需要将 <xref:System.Windows.Controls.TreeView> 绑定到深度未知的数据源。  如果数据在本质上是递归的，如文件系统、文件夹可以包含文件夹的位置或公司的组织结构（其中员工将其他员工作为直接下属），就会发生这种情况。  
  
 数据源必须具有分层对象模型。 例如，`Employee` 类可能包含一个员工对象的集合，这些对象是员工的直接下属。 如果以非层次结构的方式表示数据，则必须生成数据的分层表示形式。  
  
 设置 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> 属性并且如果 <xref:System.Windows.Controls.ItemsControl> 为每个子项生成 <xref:System.Windows.Controls.ItemsControl>，子 <xref:System.Windows.Controls.ItemsControl> 将使用与父项相同的 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>。 例如，如果在数据绑定 <xref:System.Windows.Controls.TreeView>上设置 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 属性，则生成的每个 <xref:System.Windows.Controls.TreeViewItem> 都使用分配给 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 的 <xref:System.Windows.Controls.TreeView>属性的 <xref:System.Windows.DataTemplate>。  
  
 使用 <xref:System.Windows.HierarchicalDataTemplate> 可为数据模板指定 <xref:System.Windows.Controls.TreeViewItem>或任何 <xref:System.Windows.Controls.HeaderedItemsControl>的 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>。 设置 <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> 属性时，将在应用 <xref:System.Windows.HierarchicalDataTemplate> 时使用该值。 通过使用 <xref:System.Windows.HierarchicalDataTemplate>，你可以以递归方式为 <xref:System.Windows.Controls.TreeView>中的每个 <xref:System.Windows.Controls.TreeViewItem> 设置 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>。  
  
## <a name="example"></a>示例  
 下面的示例演示如何将 <xref:System.Windows.Controls.TreeView> 绑定到分层数据并使用 <xref:System.Windows.HierarchicalDataTemplate> 为每个 <xref:System.Windows.Controls.TreeViewItem>指定 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>。  <xref:System.Windows.Controls.TreeView> 绑定到表示公司中雇员的 XML 数据。  每个 `Employee` 元素都可以包含其他 `Employee` 元素，以指示向谁报告。 由于数据是递归的，因此 <xref:System.Windows.HierarchicalDataTemplate> 可应用于每个级别。  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>请参阅

- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [数据模板化概述](../data/data-templating-overview.md)
