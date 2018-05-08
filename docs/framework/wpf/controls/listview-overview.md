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
ms.openlocfilehash: 5a7e640b7398c2034933688ea6356ef14692f8f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="listview-overview"></a>ListView 概述
<xref:System.Windows.Controls.ListView>控件提供的基础结构在不同的布局或视图中显示的数据项目集。 例如，用户可能需要在表格中显示数据项，并同时对表格的列进行排序。  
  
  
<a name="WhatisaListView"></a>   
## <a name="what-is-a-listview"></a>什么是 ListView？  
 <xref:System.Windows.Controls.ListView>控件是<xref:System.Windows.Controls.ItemsControl>、 派生自<xref:System.Windows.Controls.ListBox>。 通常情况下，其项是数据集合的成员，表示为<xref:System.Windows.Controls.ListViewItem>对象。 A<xref:System.Windows.Controls.ListViewItem>是<xref:System.Windows.Controls.ContentControl>，并且可以包含单个子元素。 但是，该子元素可以是任何视觉元素。  
  
<a name="DefiningaListViewView"></a>   
## <a name="defining-a-view-mode-for-a-listview"></a>为 ListView 定义视图模式  
 若要指定的内容视图模式<xref:System.Windows.Controls.ListView>控件，则设置<xref:System.Windows.Controls.ListView.View%2A>属性。 一个视图模式，[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]提供是<xref:System.Windows.Controls.GridView>，它具有可自定义列的表中会显示数据项的集合。  
  
 下面的示例演示如何定义<xref:System.Windows.Controls.GridView>为<xref:System.Windows.Controls.ListView>显示员工信息的控件。  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 下图演示上一个示例的数据显示方式。  
  
 ![具有 GridView 输出的 ListView](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")  
  
 你可以通过定义继承自的类创建自定义视图模式<xref:System.Windows.Controls.ViewBase>类。 <xref:System.Windows.Controls.ViewBase>类提供你需要创建自定义视图的基础结构。 有关如何创建自定义视图的详细信息，请参阅[为 ListView 创建自定义视图模式](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md)。  
  
<a name="BindingDatatoaListView"></a>   
## <a name="binding-data-to-a-listview"></a>将数据绑定到 ListView  
 使用<xref:System.Windows.Controls.ItemsControl.Items%2A>和<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性以指定项<xref:System.Windows.Controls.ListView>控件。 下面的示例设置<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>属性数据集合，它称为`EmployeeInfoDataSource`。  
  
 [!code-xaml[ListViewCode#ItemsSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 在<xref:System.Windows.Controls.GridView>，<xref:System.Windows.Controls.GridViewColumn>对象将绑定到指定的数据字段。 下面的示例将绑定<xref:System.Windows.Controls.GridViewColumn>到通过指定数据字段的对象<xref:System.Windows.Data.Binding>为<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>属性。  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 你还可以指定<xref:System.Windows.Data.Binding>作为的一部分<xref:System.Windows.DataTemplate>使用来设置列中的单元格的样式的定义。 在下面的示例中，<xref:System.Windows.DataTemplate>识别具有以下<xref:System.Windows.ResourceKey>设置<xref:System.Windows.Data.Binding>为<xref:System.Windows.Controls.GridViewColumn>。 请注意，此示例不会定义<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>因为这样做将覆盖由指定的绑定<xref:System.Windows.DataTemplate>。  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>   
## <a name="styling-a-listview-that-implements-a-gridview"></a>为实现 GridView 的 ListView 设置样式  
 <xref:System.Windows.Controls.ListView>控件包含<xref:System.Windows.Controls.ListViewItem>对象，表示显示的数据项。 可使用以下属性定义数据项的内容和样式：  
  
-   上<xref:System.Windows.Controls.ListView>控制，请使用<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>， <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>，和<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>属性。  
  
-   上<xref:System.Windows.Controls.ListViewItem>控制，请使用<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>和<xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>属性。  
  
 若要避免中单元格之间的对齐方式问题<xref:System.Windows.Controls.GridView>，不要使用<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>设置属性或将影响中的项的宽度的内容添加<xref:System.Windows.Controls.ListView>。 例如，对齐问题可能会导致当您设置<xref:System.Windows.FrameworkElement.Margin%2A>中的属性<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>。 若要指定属性或定义中的项的宽度有影响的内容<xref:System.Windows.Controls.GridView>，使用的属性<xref:System.Windows.Controls.GridView>类和相关的类，如<xref:System.Windows.Controls.GridViewColumn>。  
  
 有关如何使用<xref:System.Windows.Controls.GridView>和其支持的类，请参阅[GridView 概述](../../../../docs/framework/wpf/controls/gridview-overview.md)。  
  
 如果你定义<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>为<xref:System.Windows.Controls.ListView>控制，还可定义<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>，必须包括<xref:System.Windows.Controls.ContentPresenter>顺序样式<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>正常工作。  
  
 不要使用<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>和<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>属性<xref:System.Windows.Controls.ListView>通过使用显示的内容<xref:System.Windows.Controls.GridView>。 若要指定的列中的内容的对齐方式<xref:System.Windows.Controls.GridView>，定义<xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>。  
  
<a name="UsingtheSameViewMoreThanOnce"></a>   
## <a name="sharing-the-same-view-mode"></a>共享同一视图模式  
 两个<xref:System.Windows.Controls.ListView>控件不能在同一时间共享相同的视图模式。 如果你尝试使用带有多个相同的视图模式<xref:System.Windows.Controls.ListView>控制，则会发生异常。  
  
 若要指定可同时由多个视图模式<xref:System.Windows.Controls.ListView>，使用模板或样式。 有关如何定义为视图的示例<xref:System.Windows.FrameworkElement.Resources%2A>，请参阅[与多个视图示例 ListView](http://go.microsoft.com/fwlink/?LinkID=160013)。  
  
<a name="CreatingaCustomView"></a>   
## <a name="creating-a-custom-view-mode"></a>创建自定义视图模式  
 自定义等视图与<xref:System.Windows.Controls.GridView>派生自<xref:System.Windows.Controls.ViewBase>抽象类，该类提供的工具来显示表示为数据项目<xref:System.Windows.Controls.ListViewItem>对象。  
  
 有关自定义视图模式的示例，请参阅[具有多个视图的 ListView 示例](http://go.microsoft.com/fwlink/?LinkID=160013)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.GridView>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.ListViewItem>  
 <xref:System.Windows.Data.Binding>  
 [GridView 概述](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [控件](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
