---
title: 如何：在 TreeView 中查找 TreeViewItem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
ms.openlocfilehash: ad72c7a7fb11dfe605db4119dde831b47dd7c5a4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962098"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a>如何：在 TreeView 中查找 TreeViewItem
<xref:System.Windows.Controls.TreeView>控件提供了一种简便的方法来显示分层数据。 如果将绑定到数据源<xref:System.Windows.Controls.TreeView.SelectedItem%2A> , 则属性提供了一种方便的方法来快速检索所选的数据对象。 <xref:System.Windows.Controls.TreeView> 通常情况下, 最好使用基础数据对象, 但有时你可能需要以编程方式操作包含<xref:System.Windows.Controls.TreeViewItem>的数据。 例如, 你可能需要以编程方式展开<xref:System.Windows.Controls.TreeViewItem>, 或<xref:System.Windows.Controls.TreeView>在中选择其他项。  
  
 若要查找<xref:System.Windows.Controls.TreeViewItem>包含特定数据对象的, 必须遍历的<xref:System.Windows.Controls.TreeView>每个级别。 还<xref:System.Windows.Controls.TreeView>可以对中的项进行虚拟化以提高性能。 如果项可能虚拟化, 还必须实现<xref:System.Windows.Controls.TreeViewItem> , 以检查其是否包含数据对象。  
  
## <a name="example"></a>示例  
  
## <a name="description"></a>描述  
 下面的示例在中<xref:System.Windows.Controls.TreeView>搜索特定对象, 并返回包含<xref:System.Windows.Controls.TreeViewItem>的对象。 该示例确保每个<xref:System.Windows.Controls.TreeViewItem>实例化后, 才能搜索其子项。 此示例也适用于不<xref:System.Windows.Controls.TreeView>使用虚拟化项的情况。  
  
> [!NOTE]
> 下面的示例适用于任何<xref:System.Windows.Controls.TreeView>, 而不考虑基础数据模型, 并在每<xref:System.Windows.Controls.TreeViewItem>次找到该对象之前搜索。 性能更好的另一种方法是, 在数据模型中搜索指定的对象, 记录其在数据层次结构中的位置, 然后<xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.Controls.TreeView>在中查找相应的。 但是, 具有更好性能的技术需要了解数据模型, 并且不能对任何给定<xref:System.Windows.Controls.TreeView>的进行通用化。  
  
## <a name="code"></a>代码  
 [!code-csharp[TreeViewFindTVI#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 前面的代码依赖于公开一个<xref:System.Windows.Controls.VirtualizingStackPanel>名为`BringIntoView`的方法的自定义。 下面的代码定义了自<xref:System.Windows.Controls.VirtualizingStackPanel>定义。  
  
 [!code-csharp[TreeViewFindTVI#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 下面的 XAML 演示如何创建<xref:System.Windows.Controls.TreeView>使用自定义<xref:System.Windows.Controls.VirtualizingStackPanel>的。  
  
 [!code-xaml[TreeViewFindTVI#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a>请参阅

- [提升 TreeView 的性能](how-to-improve-the-performance-of-a-treeview.md)
