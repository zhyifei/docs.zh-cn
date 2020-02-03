---
title: DataGridView 控件和 DataGrid 控件之间的差异
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: 3552abe55d8e2c1cb4ae372ca64c7ca21f1fed0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745966"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Windows 窗体 DataGridView 控件和 DataGrid 控件之间的区别
<xref:System.Windows.Forms.DataGridView> 控件是替换 <xref:System.Windows.Forms.DataGrid> 控件的新控件。 <xref:System.Windows.Forms.DataGridView> 控件提供了许多在 <xref:System.Windows.Forms.DataGrid> 控件中缺少的基本和高级功能。 此外，<xref:System.Windows.Forms.DataGridView> 控件的体系结构可以比 <xref:System.Windows.Forms.DataGrid> 控件更轻松地进行扩展和自定义。  
  
 下表描述了 <xref:System.Windows.Forms.DataGrid> 控件中缺少 <xref:System.Windows.Forms.DataGridView> 控件中提供的几个主要功能。  
  
|DataGridView 控件功能|说明|  
|----------------------------------|-----------------|  
|多列类型|<xref:System.Windows.Forms.DataGridView> 控件提供的内置列类型比 <xref:System.Windows.Forms.DataGrid> 控件的更多。 这些列类型满足最常见方案的需求，但在 <xref:System.Windows.Forms.DataGrid> 控件中扩展或替换列类型也更容易。 有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的列类型](column-types-in-the-windows-forms-datagridview-control.md)。|  
|显示数据的多种方式|<xref:System.Windows.Forms.DataGrid> 控件仅用于显示来自外部数据源的数据。 但 <xref:System.Windows.Forms.DataGridView> 控件可以显示存储在控件中的未绑定数据、绑定数据源中的数据，或者将绑定和未绑定的数据组合在一起。 你还可以在 <xref:System.Windows.Forms.DataGridView> 控件中实现虚拟模式，以提供自定义数据管理。 有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的数据显示模式](data-display-modes-in-the-windows-forms-datagridview-control.md)。|  
|自定义数据显示的多种方式|<xref:System.Windows.Forms.DataGridView> 控件提供了许多属性和事件，使您可以指定如何对数据进行格式设置和显示。 例如，您可以根据所包含的数据更改单元格、行和列的外观，也可以用另一种类型的等效数据替换一种数据类型的数据。 有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的数据格式设置](data-formatting-in-the-windows-forms-datagridview-control.md)。|  
|用于更改单元格、行、列和标题外观和行为的多种选项|利用 <xref:System.Windows.Forms.DataGridView> 控件，可以通过多种方式处理单个网格组件。 例如，您可以冻结行和列以防止它们滚动;隐藏行、列和标头;更改行、列和标头大小的调整方式;更改用户做出选择的方式;和提供单个单元格、行和列的工具提示和快捷菜单。|  
  
 保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容性和特殊需求。 几乎所有目的都应该使用 <xref:System.Windows.Forms.DataGridView> 控件。 <xref:System.Windows.Forms.DataGrid> 控件中提供的唯一功能是在 <xref:System.Windows.Forms.DataGridView> 控件中不可用的，它是一个控件中两个相关表中的信息的分层显示。 您必须使用两个 <xref:System.Windows.Forms.DataGridView> 控件才能显示处于主/从关系中的两个表中的信息。  
  
## <a name="upgrading-to-the-datagridview-control"></a>升级到 DataGridView 控件  
 如果在没有自定义的简单数据绑定方案中具有使用 <xref:System.Windows.Forms.DataGrid> 控件的现有应用程序，则只需将旧控件替换为新控件即可。 这两个控件都使用标准 Windows 窗体数据绑定体系结构，因此 <xref:System.Windows.Forms.DataGridView> 控件将显示绑定数据，无需其他配置。 不过，您可能希望通过将数据绑定到 <xref:System.Windows.Forms.BindingSource> 组件来利用数据绑定改进，然后将数据绑定到 <xref:System.Windows.Forms.DataGridView> 控件。 有关详细信息，请参阅[BindingSource Component](bindingsource-component.md)。  
  
 由于 <xref:System.Windows.Forms.DataGridView> 控件具有一个全新的体系结构，因此没有直接的转换路径，使您能够将 <xref:System.Windows.Forms.DataGrid> 自定义项用于 <xref:System.Windows.Forms.DataGridView> 控件。 不过，由于新控件中提供了内置功能，因此许多 <xref:System.Windows.Forms.DataGrid> 自定义都不需要使用 <xref:System.Windows.Forms.DataGridView> 控件。 如果为要用于 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGrid> 控件创建了自定义列类型，则必须使用新的体系结构再次实现它们。 有关详细信息，请参阅[自定义 Windows 窗体 DataGridView 控件](customizing-the-windows-forms-datagridview-control.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Windows.Forms.BindingSource>
- [DataGridView 控件](datagridview-control-windows-forms.md)
- [DataGrid 控件](datagrid-control-windows-forms.md)
- [BindingSource 组件](bindingsource-component.md)
- [Windows 窗体 DataGridView 控件中的列类型](column-types-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的数据显示模式](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的数据格式设置](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的重设大小选项](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的列排序模式](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的选择模式](selection-modes-in-the-windows-forms-datagridview-control.md)
- [自定义 Windows 窗体 DataGridView 控件](customizing-the-windows-forms-datagridview-control.md)
