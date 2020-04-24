---
title: DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid column types [WPF]
- DataGrid scenarios [WPF]
- DataGrid control [WPF]
- controls [WPF], DataGrid
- DataGrid [WPF], common tasks for
- DataGrid [WPF], customizing the appearance of
- DataGrid columns [WPF], using
ms.assetid: bf89ea63-79b6-422b-bc9f-0485ad803216
ms.openlocfilehash: cdf4bfff8182b62d55f56b823c7ff129de4f9f1c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646119"
---
# <a name="datagrid"></a>DataGrid
该<xref:System.Windows.Controls.DataGrid>控件使您能够显示和编辑来自许多不同的源的数据，例如来自 SQL 数据库、LINQ 查询或任何其他可绑定数据源的数据。 有关详细信息，请参阅[绑定源概述](../data/binding-sources-overview.md)。  
  
 列可以显示文本、控件（如 ）<xref:System.Windows.Controls.ComboBox>或任何其他 WPF 内容，如图像、按钮或模板中包含的任何内容。 可以使用 显示<xref:System.Windows.Controls.DataGridTemplateColumn>模板中定义的数据。 下表列出了默认情况下提供的列类型。  
  
|生成的列类型|数据类型|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid>可以在外观（如单元格字体、颜色和大小）中自定义。 <xref:System.Windows.Controls.DataGrid>支持其他 WPF 控件的所有样式和模板化功能。 <xref:System.Windows.Controls.DataGrid>还包括用于编辑、排序和验证的默认和可自定义行为。  
  
 下表列出了一<xref:System.Windows.Controls.DataGrid>些常见任务以及如何完成这些任务。 通过查看相关的 API，您可以找到更多信息和示例代码。  
  
|方案|方法|  
|--------------|--------------|  
|交替背景颜色|将<xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A>属性设置为 2 或更多，然后将 分配<xref:System.Windows.Media.Brush>到<xref:System.Windows.Controls.DataGrid.RowBackground%2A>和<xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A>属性。|  
|定义单元格和行选择行为|设置 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 和 <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> 属性。|  
|自定义标题、单元格和行的可视外观|<xref:System.Windows.Style>将新应用于<xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>、、<xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A><xref:System.Windows.Controls.DataGrid.CellStyle%2A>或<xref:System.Windows.Controls.DataGrid.RowStyle%2A>属性。|  
|设置大小调整选项|设置<xref:System.Windows.FrameworkElement.Height%2A>、 <xref:System.Windows.FrameworkElement.MaxHeight%2A> <xref:System.Windows.FrameworkElement.MinHeight%2A>、 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.MaxWidth%2A>、 <xref:System.Windows.FrameworkElement.MinWidth%2A> 、 、 、 、 、 有关详细信息，请参阅[数据网格控件中的大小调整选项](sizing-options-in-the-datagrid-control.md)。|  
|访问所选项目|检查属性<xref:System.Windows.Controls.DataGrid.SelectedCells%2A>以获取所选单元格和<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A>属性以获取所选行。 有关详细信息，请参阅 <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>。|  
|自定义最终用户交互|设置<xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>、 <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A> <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>、 <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A> <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A>、 <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> 、 和 属性。|  
|取消或更改自动生成的列|处理事件<xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn>。|  
|冻结列|将<xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A>属性设置为 1，并将列移动到最左侧的位置，将<xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A>属性设置为 0。|  
|使用 XML 数据作为数据源|将<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>上绑定<xref:System.Windows.Controls.DataGrid>到表示项集合的 XPath 查询。 在 中创建每<xref:System.Windows.Controls.DataGrid>一列。 通过在绑定上设置 XPath 绑定到获取项源上的属性的查询来绑定每个列。 有关示例，请参见 <xref:System.Windows.Controls.DataGridTextColumn>。|  
  
## <a name="related-topics"></a>相关主题  
  
|Title|说明|  
|-----------|-----------------|  
|[演练：在 DataGrid 控件中显示 SQL Server 数据库中的数据](walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|描述如何设置新的 WPF 项目、添加实体框架元素、设置源并在 中<xref:System.Windows.Controls.DataGrid>显示数据。|  
|[如何：向 DataGrid 控件中添加行详细信息](how-to-add-row-details-to-a-datagrid-control.md)|描述如何为 创建 行<xref:System.Windows.Controls.DataGrid>详细信息。|  
|[如何：使用 DataGrid 控件实现验证](how-to-implement-validation-with-the-datagrid-control.md)|描述如何验证单元格和行<xref:System.Windows.Controls.DataGrid>中的值，并显示验证反馈。|  
|[DataGrid 控件中的默认键盘和鼠标行为](default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|描述如何使用键盘和鼠标与<xref:System.Windows.Controls.DataGrid>控件进行交互。|  
|[如何：在 DataGrid 控件中对数据进行分组、排序和筛选](how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|描述如何通过分组、排序和筛选<xref:System.Windows.Controls.DataGrid>数据以不同的方式查看数据。|  
|[DataGrid 控件中的调整大小选项](sizing-options-in-the-datagrid-control.md)|描述如何在 中控制绝对和自动大小调整<xref:System.Windows.Controls.DataGrid>。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.DataGrid>
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [数据模板化概述](../data/data-templating-overview.md)
- [控件](index.md)
- [WPF 内容模型](wpf-content-model.md)
