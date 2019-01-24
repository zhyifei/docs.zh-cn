---
title: 如何：使用 SelectedValue、SelectedValuePath 和 SelectedItem
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
ms.openlocfilehash: 1bb307009586a5bbf4e9accefb633b97dc837528
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637815"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a>如何：使用 SelectedValue、SelectedValuePath 和 SelectedItem
此示例演示如何使用<xref:System.Windows.Controls.TreeView.SelectedValue%2A>并<xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>属性，以指定的值<xref:System.Windows.Controls.TreeView.SelectedItem%2A>的<xref:System.Windows.Controls.TreeView>。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>属性提供了一种方法来指定<xref:System.Windows.Controls.TreeView.SelectedValue%2A>有关<xref:System.Windows.Controls.TreeView.SelectedItem%2A>中<xref:System.Windows.Controls.TreeView>。 <xref:System.Windows.Controls.TreeView.SelectedItem%2A>表示中的对象<xref:System.Windows.Controls.ItemsControl.Items%2A>集合和<xref:System.Windows.Controls.TreeView>显示选定项的单个属性的值。 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>属性指定用于确定值的属性的路径<xref:System.Windows.Controls.TreeView.SelectedValue%2A>属性。 本主题中的示例演示了这一概念。  
  
 下面的示例演示<xref:System.Windows.Data.XmlDataProvider>包含雇员的信息。  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 下面的示例定义<xref:System.Windows.HierarchicalDataTemplate>，它显示`EmployeeName`并`EmployeeWorkDay`的`Employee`。 请注意，<xref:System.Windows.HierarchicalDataTemplate>未指定`EmployeeNumber`作为模板的一部分。  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 下面的示例演示<xref:System.Windows.Controls.TreeView>，它使用以前定义<xref:System.Windows.HierarchicalDataTemplate>，用于设置和<xref:System.Windows.Controls.TreeView.SelectedValue%2A>属性设置为`EmployeeNumber`。 当选择`EmployeeName`中<xref:System.Windows.Controls.TreeView>，则<xref:System.Windows.Controls.TreeView.SelectedItem%2A>属性将返回`EmployeeInfo`对应于所选的数据项`EmployeeName`。 但是，由于<xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>的这<xref:System.Windows.Controls.TreeView>设置为`EmployeeNumber`，则<xref:System.Windows.Controls.TreeView.SelectedValue%2A>设置为`EmployeeNumber`。  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [TreeView 概述](../../../../docs/framework/wpf/controls/treeview-overview.md)
- [帮助主题](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
