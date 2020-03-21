---
title: TreeView 概述
ms.date: 03/30/2017
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
ms.openlocfilehash: 267e870e13d26439e4fbcbba3c5741ff84cabe3c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187369"
---
# <a name="treeview-overview"></a>TreeView 概述
该<xref:System.Windows.Controls.TreeView>控件提供了一种通过使用可折叠节点在分层结构中显示信息的方法。 本主题介绍<xref:System.Windows.Controls.TreeView>和<xref:System.Windows.Controls.TreeViewItem>控件，并提供其使用的简单示例。  

<a name="Simple_TreeView_Control"></a>
## <a name="what-is-a-treeview"></a>什么是 TreeView？  
 <xref:System.Windows.Controls.TreeView>是<xref:System.Windows.Controls.ItemsControl>使用<xref:System.Windows.Controls.TreeViewItem>控件嵌套项的 。 下面的示例创建 一<xref:System.Windows.Controls.TreeView>个 。  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>
## <a name="creating-a-treeview"></a>创建 TreeView  
 该<xref:System.Windows.Controls.TreeView>控件包含控件的<xref:System.Windows.Controls.TreeViewItem>层次结构。 控件<xref:System.Windows.Controls.TreeViewItem>是<xref:System.Windows.Controls.HeaderedItemsControl>具有<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>和 集合的<xref:System.Windows.Controls.ItemsControl.Items%2A>控件。  
  
 如果使用 来定义<xref:System.Windows.Controls.TreeView>。 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> <xref:System.Windows.Controls.TreeViewItem> 上图演示了此方法。  
  
 还可以将<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>指定 为数据源，然后指定 和<xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A><xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>来定义<xref:System.Windows.Controls.TreeViewItem>内容。  
  
 要定义控件的布局，<xref:System.Windows.Controls.TreeViewItem>还可以使用<xref:System.Windows.HierarchicalDataTemplate>对象。 有关详细信息和示例，请参阅[使用 SelectedValue、SelectedValuePath 和 SelectedItem](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)。  
  
 如果项不是<xref:System.Windows.Controls.TreeViewItem>控件，则当<xref:System.Windows.Controls.TreeViewItem><xref:System.Windows.Controls.TreeView>显示控件时，控件会自动将其封闭。  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>
## <a name="expanding-and-collapsing-a-treeviewitem"></a>展开和折叠 TreeViewItem  
 如果用户展开 的 ，<xref:System.Windows.Controls.TreeViewItem>属性<xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A>设置为`true`。 <xref:System.Windows.Controls.TreeViewItem>还可以通过将<xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A>属性设置为`true`（展开）或`false`（折叠）来展开或折叠 ，而无需任何直接的用户操作。 当此属性更改时，将<xref:System.Windows.Controls.TreeViewItem.Expanded>发生<xref:System.Windows.Controls.TreeViewItem.Collapsed>或 事件。  
  
 在<xref:System.Windows.FrameworkElement.BringIntoView%2A><xref:System.Windows.Controls.TreeViewItem>控件上调用方法时， 及其<xref:System.Windows.Controls.TreeViewItem>父<xref:System.Windows.Controls.TreeViewItem>控件将展开。 如果<xref:System.Windows.Controls.TreeViewItem>不可见或部分可见，则<xref:System.Windows.Controls.TreeView>滚动使其可见。  
  
<a name="TreeViewItem_Selection"></a>
## <a name="treeviewitem-selection"></a>TreeViewItem 选择  
 当用户单击<xref:System.Windows.Controls.TreeViewItem>控件以选择它时，将发生该<xref:System.Windows.Controls.TreeViewItem.Selected>事件，其<xref:System.Windows.Controls.TreeViewItem.IsSelected%2A>属性设置为`true`。 也<xref:System.Windows.Controls.TreeViewItem>将成为控件<xref:System.Windows.Controls.TreeView.SelectedItem%2A>的<xref:System.Windows.Controls.TreeView>。 相反，当选择<xref:System.Windows.Controls.TreeViewItem>从控件更改时，将发生其<xref:System.Windows.Controls.TreeViewItem.Unselected>事件并将其<xref:System.Windows.Controls.TreeViewItem.IsSelected%2A>属性设置为`false`。  
  
 控件<xref:System.Windows.Controls.TreeView.SelectedItem%2A>上的<xref:System.Windows.Controls.TreeView>属性是只读属性;因此，您不能显式设置它。 如果用户<xref:System.Windows.Controls.TreeView.SelectedItem%2A>单击<xref:System.Windows.Controls.TreeViewItem>控件或将<xref:System.Windows.Controls.TreeViewItem.IsSelected%2A>该属性设置为`true`<xref:System.Windows.Controls.TreeViewItem>控件，则设置该属性。  
  
 使用<xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>属性指定 的<xref:System.Windows.Controls.TreeView.SelectedValue%2A>。 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 有关详细信息，请参阅[使用 SelectedValue、SelectedValuePath 和 SelectedItem](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)。  
  
 您可以在<xref:System.Windows.Controls.TreeView.SelectedItemChanged>事件上注册事件处理程序，以确定所选<xref:System.Windows.Controls.TreeViewItem>更改的次序。 <xref:System.Windows.RoutedPropertyChangedEventArgs%601>提供给事件处理程序的 指定 ，<xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>是 上一个选择， 和<xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>， 是当前选择。 如果应用程序或用户未进行上一个或当前选择，则任一值都可能为 `null`。  
  
<a name="TreeView_Style"></a>
## <a name="treeview-style"></a>TreeView 样式  
 控件的<xref:System.Windows.Controls.TreeView>默认样式将其置于包含<xref:System.Windows.Controls.StackPanel><xref:System.Windows.Controls.ScrollViewer>控件的对象中。 设置<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性时<xref:System.Windows.Controls.TreeView>，这些值用于调整 显示<xref:System.Windows.Controls.StackPanel>的对象<xref:System.Windows.Controls.TreeView>的大小。 如果要显示的内容大于显示区域，则会自动显示，<xref:System.Windows.Controls.ScrollViewer>以便用户可以滚动浏览<xref:System.Windows.Controls.TreeView>内容。  
  
 要自定义控件的外观，<xref:System.Windows.Controls.TreeViewItem>请将<xref:System.Windows.FrameworkElement.Style%2A>属性设置为自定义<xref:System.Windows.Style>。  
  
 下面的示例演示如何使用<xref:System.Windows.Controls.Control.Foreground%2A>设置<xref:System.Windows.Controls.Control.FontSize%2A><xref:System.Windows.Controls.TreeViewItem>控件 的 和 属性值。 <xref:System.Windows.FrameworkElement.Style%2A>  
  
 [!code-xaml[TreeViewSimple#8](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>
## <a name="adding-images-and-other-content-to-treeview-items"></a>向 TreeView 项添加图像和其他内容  
 可以在 中包含多个对象<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A><xref:System.Windows.Controls.TreeViewItem>。 要在内容中<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>包含多个对象，请将对象包含在布局控件中，如 或<xref:System.Windows.Controls.Panel><xref:System.Windows.Controls.StackPanel>。  
  
 下面的<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>示例演示如何将 和 和<xref:System.Windows.Controls.TreeViewItem><xref:System.Windows.Controls.CheckBox><xref:System.Windows.Controls.TextBlock>的 将 定义为 和，它们都<xref:System.Windows.Controls.DockPanel>包含在控件中。  
  
 [!code-xaml[TreeViewSnips#TVIHeader](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 下面的示例<xref:System.Windows.DataTemplate>演示如何定义 包含<xref:System.Windows.Controls.Image>和 的 控件中<xref:System.Windows.Controls.TextBlock><xref:System.Windows.Controls.DockPanel>包含 的 。 <xref:System.Windows.DataTemplate>可以使用 设置<xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A>或<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>。 <xref:System.Windows.Controls.TreeViewItem>  
  
 [!code-xaml[TreeViewDataBinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [如何使用主题](treeview-how-to-topics.md)
- [WPF 内容模型](wpf-content-model.md)
