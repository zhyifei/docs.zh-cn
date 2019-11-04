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
ms.openlocfilehash: f0887f36990de483139a9fde1472a78737cb7b72
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460383"
---
# <a name="datagrid"></a>DataGrid
使用 "<xref:System.Windows.Controls.DataGrid>" 控件，可以显示和编辑来自多种不同源的数据，例如 SQL 数据库、LINQ 查询或任何其他可绑定的数据源。 有关详细信息，请参阅[绑定源概述](../data/binding-sources-overview.md)。  
  
 列可以显示文本、控件（如 <xref:System.Windows.Controls.ComboBox>）或任何其他 WPF 内容（如图像、按钮或模板中包含的任何内容）。 您可以使用 <xref:System.Windows.Controls.DataGridTemplateColumn> 显示模板中定义的数据。 下表列出了默认情况下提供的列类型。  
  
|生成的列类型|数据类型|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 可以在外观中自定义 <xref:System.Windows.Controls.DataGrid>，如单元字体、颜色和大小。 <xref:System.Windows.Controls.DataGrid> 支持其他 WPF 控件的所有样式设置和模板化功能。 <xref:System.Windows.Controls.DataGrid> 还包括用于编辑、排序和验证的默认和可自定义的行为。  
  
 下表列出了一些 <xref:System.Windows.Controls.DataGrid> 的常见任务以及如何完成这些任务。 通过查看相关 API，可以找到详细信息和示例代码。  
  
|方案|方法|  
|--------------|--------------|  
|交替背景色|将 <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> 属性设置为2或更大，然后将 <xref:System.Windows.Media.Brush> 分配到 <xref:System.Windows.Controls.DataGrid.RowBackground%2A> 和 <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> 属性。|  
|定义单元格和行选择行为|设置 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 和 <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> 属性。|  
|自定义标题、单元格和行的视觉外观|将新 <xref:System.Windows.Style> 应用于 <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>、<xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>、<xref:System.Windows.Controls.DataGrid.CellStyle%2A>或 <xref:System.Windows.Controls.DataGrid.RowStyle%2A> 属性。|  
|设置大小调整选项|设置 <xref:System.Windows.FrameworkElement.Height%2A>、<xref:System.Windows.FrameworkElement.MaxHeight%2A>、<xref:System.Windows.FrameworkElement.MinHeight%2A>、<xref:System.Windows.FrameworkElement.Width%2A>、<xref:System.Windows.FrameworkElement.MaxWidth%2A>或 <xref:System.Windows.FrameworkElement.MinWidth%2A> 属性。 有关详细信息，请参阅[DataGrid 控件中的调整大小选项](sizing-options-in-the-datagrid-control.md)。|  
|访问选定项|检查 <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> 属性以获取选定的单元格，并选择 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> 属性以获取选定的行。 有关更多信息，请参见<xref:System.Windows.Controls.DataGrid.SelectedCells%2A>。|  
|自定义最终用户交互|设置 <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>、<xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>、<xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>、<xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>、<xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A>和 <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> 属性。|  
|取消或更改自动生成的列|处理 <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> 事件。|  
|冻结列|将 <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> 属性设置为1，并将 "<xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A>" 属性设置为 "0"，将列移到最左侧的位置。|  
|使用 XML 数据作为数据源|将 <xref:System.Windows.Controls.DataGrid> 上的 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 绑定到表示项集合的 XPath 查询。 在 <xref:System.Windows.Controls.DataGrid>中创建每个列。 绑定每一列，方法是将绑定上的 XPath 设置为可获取项源属性的查询。 有关示例，请参见 <xref:System.Windows.Controls.DataGridTextColumn>。|  
  
## <a name="related-topics"></a>相关主题  
  
|Title|描述|  
|-----------|-----------------|  
|[演练：在 DataGrid 控件中显示 SQL Server 数据库中的数据](walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|描述如何设置新的 WPF 项目，添加实体框架元素，设置源，并在 <xref:System.Windows.Controls.DataGrid>中显示数据。|  
|[如何：向 DataGrid 控件添加行详细信息](how-to-add-row-details-to-a-datagrid-control.md)|描述如何为 <xref:System.Windows.Controls.DataGrid>创建行详细信息。|  
|[如何：使用 DataGrid 控件实现验证](how-to-implement-validation-with-the-datagrid-control.md)|介绍如何验证 <xref:System.Windows.Controls.DataGrid> 单元和行中的值，并显示验证反馈。|  
|[DataGrid 控件中的默认键盘和鼠标行为](default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|描述如何使用键盘和鼠标与 <xref:System.Windows.Controls.DataGrid> 控件交互。|  
|[如何：在 DataGrid 控件中对数据进行分组、排序和筛选](how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|介绍如何通过对数据进行分组、排序和筛选来以不同方式查看 <xref:System.Windows.Controls.DataGrid> 中的数据。|  
|[DataGrid 控件中的重设大小选项](sizing-options-in-the-datagrid-control.md)|描述如何在 <xref:System.Windows.Controls.DataGrid>中控制绝对和自动调整大小。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.DataGrid>
- [样式设置和模板化](styling-and-templating.md)
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [数据模板化概述](../data/data-templating-overview.md)
- [控件](index.md)
- [WPF 内容模型](wpf-content-model.md)
