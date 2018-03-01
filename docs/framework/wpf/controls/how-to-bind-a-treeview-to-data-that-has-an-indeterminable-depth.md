---
title: "如何：将 TreeView 绑定到深度无法确定的数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: be21ecb75420b6499e5b95d5f4d93a5f079f9646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>如何：将 TreeView 绑定到深度无法确定的数据
可能有的时候你想要将绑定<xref:System.Windows.Controls.TreeView>到数据源不已知其深度。  这会时发生数据具有递归性质，例如文件系统，其中文件夹可以包含文件夹或公司的组织结构，其中员工的直接下属作为其他员工。  
  
 数据源必须具有层次结构的对象模型。 例如，`Employee`类可能包含的是直接下属的员工的员工对象的集合。 如果不是分层的方式表示数据，则必须生成的分层表示形式的数据。  
  
 当你将设置<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType>属性如果<xref:System.Windows.Controls.ItemsControl>生成<xref:System.Windows.Controls.ItemsControl>每个子项，则子<xref:System.Windows.Controls.ItemsControl>使用相同<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>与父项。 例如，如果你设置<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>数据绑定属性<xref:System.Windows.Controls.TreeView>，每个<xref:System.Windows.Controls.TreeViewItem>，它是生成的使用<xref:System.Windows.DataTemplate>，已分配给<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>属性<xref:System.Windows.Controls.TreeView>。  
  
 <xref:System.Windows.HierarchicalDataTemplate>使您能够指定<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>为<xref:System.Windows.Controls.TreeViewItem>，或任何<xref:System.Windows.Controls.HeaderedItemsControl>，数据模板。 当你将设置<xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType>属性的值时使用<xref:System.Windows.HierarchicalDataTemplate>应用。 通过使用<xref:System.Windows.HierarchicalDataTemplate>，你可以以递归方式集<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>每个<xref:System.Windows.Controls.TreeViewItem>中<xref:System.Windows.Controls.TreeView>。  
  
## <a name="example"></a>示例  
 下面的示例演示如何将绑定<xref:System.Windows.Controls.TreeView>到层次结构数据，然后使用<xref:System.Windows.HierarchicalDataTemplate>指定<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>每个<xref:System.Windows.Controls.TreeViewItem>。  <xref:System.Windows.Controls.TreeView>将绑定到表示一家公司中的员工的 XML 数据。  每个`Employee`元素可以包含其他`Employee`元素以指示隶属关系。 因为数据是递归的<xref:System.Windows.HierarchicalDataTemplate>可以应用于每个级别。  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>请参阅  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [数据模板化概述](../../../../docs/framework/wpf/data/data-templating-overview.md)
