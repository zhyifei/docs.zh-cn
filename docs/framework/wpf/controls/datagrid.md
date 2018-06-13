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
ms.openlocfilehash: a8f267706c1ace02b091329360779711981d01e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557077"
---
# <a name="datagrid"></a>DataGrid
<xref:System.Windows.Controls.DataGrid>控制，你可以显示和编辑数据来自许多不同来源，如从 SQL 数据库、 LINQ 查询或任何其他可绑定数据源。 有关详细信息，请参阅[绑定源概述](../../../../docs/framework/wpf/data/binding-sources-overview.md)。  
  
 列可以显示文本，控件，如<xref:System.Windows.Controls.ComboBox>，或任何其他 WPF 内容，例如图像、 按钮、 或模板中包含的任何内容。 你可以使用<xref:System.Windows.Controls.DataGridTemplateColumn>以显示模板中定义的数据。 下表列出默认情况下提供的列类型。  
  
|生成的列类型|数据类型|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid> 可以自定义的外观，例如设置单元格字体、 颜色和大小。 <xref:System.Windows.Controls.DataGrid> 支持其他 WPF 控件的所有样式和模板化的功能。 <xref:System.Windows.Controls.DataGrid> 此外包括默认和自定义行为的编辑、 排序和验证。  
  
 下表列出了一些常见任务的<xref:System.Windows.Controls.DataGrid>和如何完成它们。 通过查看相关的 API，你可以找到详细信息和示例代码。  
  
|方案|方法|  
|--------------|--------------|  
|交替的背景色|设置<xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A>属性设置为 2 或更多，然后分配<xref:System.Windows.Media.Brush>到<xref:System.Windows.Controls.DataGrid.RowBackground%2A>和<xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A>属性。|  
|定义单元格和行选择行为|设置 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 和 <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> 属性。|  
|自定义可视外观的标头，单元格和行|应用新<xref:System.Windows.Style>到<xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>， <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>， <xref:System.Windows.Controls.DataGrid.CellStyle%2A>，或<xref:System.Windows.Controls.DataGrid.RowStyle%2A>属性。|  
|设置的调整大小选项|设置<xref:System.Windows.FrameworkElement.Height%2A>， <xref:System.Windows.FrameworkElement.MaxHeight%2A>， <xref:System.Windows.FrameworkElement.MinHeight%2A>， <xref:System.Windows.FrameworkElement.Width%2A>， <xref:System.Windows.FrameworkElement.MaxWidth%2A>，或<xref:System.Windows.FrameworkElement.MinWidth%2A>属性。 有关详细信息，请参阅[在 DataGrid 控件中调整选项](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md)。|  
|访问选定项|检查<xref:System.Windows.Controls.DataGrid.SelectedCells%2A>属性可获取选定的单元格和<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A>属性来获取所选的行。 有关详细信息，请参阅<xref:System.Windows.Controls.DataGrid.SelectedCells%2A>。|  
|自定义最终用户交互|设置<xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>， <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>， <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>， <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>， <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A>，和<xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A>属性。|  
|取消或更改自动生成的列|处理<xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn>事件。|  
|冻结列|设置<xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A>属性设置为 1 并将列移动到的最左边的位置通过设置<xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A>属性设为 0。|  
|使用 XML 数据作为数据源|将绑定<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>上<xref:System.Windows.Controls.DataGrid>到表示的项的集合的 XPath 查询。 创建每个列中的<xref:System.Windows.Controls.DataGrid>。 将每个列绑定到项的源获取的属性的查询在绑定上设置 XPath。 有关示例，请参见 <xref:System.Windows.Controls.DataGridTextColumn>。|  
  
## <a name="related-topics"></a>相关主题  
  
|标题|描述|  
|-----------|-----------------|  
|[演练：在 DataGrid 控件中显示 SQL Server 数据库中的数据](../../../../docs/framework/wpf/controls/walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|描述如何设置新的 WPF 项目，添加实体框架元素、 设置源，并显示中的数据<xref:System.Windows.Controls.DataGrid>。|  
|[如何：向 DataGrid 控件添加行详细信息](../../../../docs/framework/wpf/controls/how-to-add-row-details-to-a-datagrid-control.md)|描述如何创建用于行详细信息<xref:System.Windows.Controls.DataGrid>。|  
|[如何：使用 DataGrid 控件实现验证](../../../../docs/framework/wpf/controls/how-to-implement-validation-with-the-datagrid-control.md)|描述如何验证中的值<xref:System.Windows.Controls.DataGrid>单元格和行，以及显示验证反馈。|  
|[DataGrid 控件中的默认键盘和鼠标行为](../../../../docs/framework/wpf/controls/default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|描述如何进行交互与<xref:System.Windows.Controls.DataGrid>通过使用键盘和鼠标的控件。|  
|[如何：在 DataGrid 控件中对数据进行分组、排序和筛选](../../../../docs/framework/wpf/controls/how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|描述如何查看中的数据<xref:System.Windows.Controls.DataGrid>通过分组、 排序和筛选的数据不同的方式。|  
|[DataGrid 控件中的重设大小选项](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md)|介绍如何控制中的绝对和自动大小调整<xref:System.Windows.Controls.DataGrid>。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.DataGrid>  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [数据模板化概述](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [控件](../../../../docs/framework/wpf/controls/index.md)  
 [WPF 内容模型](../../../../docs/framework/wpf/controls/wpf-content-model.md)
