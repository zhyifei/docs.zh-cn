---
title: ListView 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ListView
- ListView controls [WPF], about ListView control
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
ms.openlocfilehash: 2f336d1eb8dcdfec3c3c8059ba865147c6b6c825
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187520"
---
# <a name="listview-overview"></a>ListView 概述
该<xref:System.Windows.Controls.ListView>控件提供基础结构以在不同的布局或视图中显示一组数据项。 例如，用户可能需要在表格中显示数据项，并同时对表格的列进行排序。  

<a name="WhatisaListView"></a>
## <a name="what-is-a-listview"></a>什么是 ListView？  
 控件<xref:System.Windows.Controls.ListView>是从<xref:System.Windows.Controls.ItemsControl>派生的<xref:System.Windows.Controls.ListBox>。 通常，其项是数据收集的成员，并表示为<xref:System.Windows.Controls.ListViewItem>对象。 a<xref:System.Windows.Controls.ListViewItem>是<xref:System.Windows.Controls.ContentControl>，只能包含单个子元素。 但是，该子元素可以是任何视觉元素。  
  
<a name="DefiningaListViewView"></a>
## <a name="defining-a-view-mode-for-a-listview"></a>为 ListView 定义视图模式  
 要为<xref:System.Windows.Controls.ListView>控件的内容指定视图模式，请设置 属性<xref:System.Windows.Controls.ListView.View%2A>。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]提供的一种视图模式是<xref:System.Windows.Controls.GridView>，它显示具有可自定义列的表中的数据项的集合。  
  
 下面的示例演示如何为显示员工信息的<xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView>控件定义 。  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 下图演示上一个示例的数据显示方式。  
  
 ![显示带有 GridView 输出的 ListView 的屏幕截图。](./media/gridview-overview/listview-gridview-output.jpg)  
  
 可以通过定义从类继承的<xref:System.Windows.Controls.ViewBase>类来创建自定义视图模式。 类<xref:System.Windows.Controls.ViewBase>提供创建自定义视图所需的基础结构。 有关如何创建自定义视图的详细信息，请参阅[为 ListView 创建自定义视图模式](how-to-create-a-custom-view-mode-for-a-listview.md)。  
  
<a name="BindingDatatoaListView"></a>
## <a name="binding-data-to-a-listview"></a>将数据绑定到 ListView  
 使用<xref:System.Windows.Controls.ItemsControl.Items%2A>和<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性为控件指定项<xref:System.Windows.Controls.ListView>。 下面的示例将<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性设置到称为`EmployeeInfoDataSource`的数据收集。  
  
 [!code-xaml[ListViewCode#ItemsSource](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 在<xref:System.Windows.Controls.GridView>中<xref:System.Windows.Controls.GridViewColumn>，对象绑定到指定的数据字段。 下面的示例通过为<xref:System.Windows.Controls.GridViewColumn><xref:System.Windows.Data.Binding><xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>属性指定 的 将对象绑定到数据字段。  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 还可以指定 作为<xref:System.Windows.Data.Binding>用于设置列单元格样式<xref:System.Windows.DataTemplate>的定义的一部分。 在下面的<xref:System.Windows.DataTemplate>示例中，使用<xref:System.Windows.ResourceKey>集<xref:System.Windows.Data.Binding>标识 的 。 <xref:System.Windows.Controls.GridViewColumn> 请注意，此示例不定义，<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>因为这样做会覆盖 由<xref:System.Windows.DataTemplate>指定的绑定。  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>
## <a name="styling-a-listview-that-implements-a-gridview"></a>为实现 GridView 的 ListView 设置样式  
 控件<xref:System.Windows.Controls.ListView>包含<xref:System.Windows.Controls.ListViewItem>表示显示的数据项的对象。 可使用以下属性定义数据项的内容和样式：  
  
- 在控件<xref:System.Windows.Controls.ListView>上，使用<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>、<xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>和<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>属性。  
  
- 在控件<xref:System.Windows.Controls.ListViewItem>上，使用<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>和<xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>属性。  
  
 为了避免 在<xref:System.Windows.Controls.GridView>的单元格之间对齐问题，请勿使用<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>来设置 属性或添加影响 中项宽度的内容<xref:System.Windows.Controls.ListView>。 例如，在 中设置<xref:System.Windows.FrameworkElement.Margin%2A>属性时，可能会出现对齐问题。 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 要指定影响 中项宽度的属性或定义内容<xref:System.Windows.Controls.GridView>，请使用<xref:System.Windows.Controls.GridView>类及其相关类的属性，如<xref:System.Windows.Controls.GridViewColumn>。  
  
 有关如何使用<xref:System.Windows.Controls.GridView>及其支持类的详细信息，请参阅[GridView 概述](gridview-overview.md)。  
  
 如果<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>为<xref:System.Windows.Controls.ListView>控件定义 。 ，并且还定义了<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>， 必须在样式<xref:System.Windows.Controls.ContentPresenter><xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>中包括 。  
  
 不要对使用<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>显示<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A><xref:System.Windows.Controls.ListView>的内容使用 和 属性<xref:System.Windows.Controls.GridView>。 要指定 内容在 的列中的对齐方式<xref:System.Windows.Controls.GridView>，请定义<xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>。  
  
<a name="UsingtheSameViewMoreThanOnce"></a>
## <a name="sharing-the-same-view-mode"></a>共享同一视图模式  
 两<xref:System.Windows.Controls.ListView>个控件不能同时共享同一视图模式。 如果尝试对多个<xref:System.Windows.Controls.ListView>控件使用相同的视图模式，则会发生异常。  
  
 要指定可以由多个<xref:System.Windows.Controls.ListView>多个同时使用的视图模式，请使用模板或样式。
  
<a name="CreatingaCustomView"></a>
## <a name="creating-a-custom-view-mode"></a>创建自定义视图模式  
 自定义视图如<xref:System.Windows.Controls.GridView>从<xref:System.Windows.Controls.ViewBase>抽象类派生，它提供了显示表示为<xref:System.Windows.Controls.ListViewItem>对象的数据项的工具。
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.GridView>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Data.Binding>
- [GridView 概述](gridview-overview.md)
- [如何使用主题](listview-how-to-topics.md)
- [控制](../advanced/optimizing-performance-controls.md)
