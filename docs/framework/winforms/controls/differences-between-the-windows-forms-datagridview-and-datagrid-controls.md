---
title: Windows 窗体 DataGridView 控件和 DataGrid 控件之间的区别
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: d0a82d5724ebe142ae080fc930665733e701e237
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528703"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Windows 窗体 DataGridView 控件和 DataGrid 控件之间的区别
<xref:System.Windows.Forms.DataGridView>控件是一个新控件，替换<xref:System.Windows.Forms.DataGrid>控件。 <xref:System.Windows.Forms.DataGridView>控件提供了许多的基本和高级功能，中缺少<xref:System.Windows.Forms.DataGrid>控件。 此外的体系结构<xref:System.Windows.Forms.DataGridView>控件，可以更轻松地扩展和自定义比<xref:System.Windows.Forms.DataGrid>控件。  
  
 下表描述中提供的主要功能的一些<xref:System.Windows.Forms.DataGridView>控件中缺少<xref:System.Windows.Forms.DataGrid>控件。  
  
|DataGridView 控件功能|描述|  
|----------------------------------|-----------------|  
|多个列类型|<xref:System.Windows.Forms.DataGridView>控件提供了内置了更多的列类型，而不<xref:System.Windows.Forms.DataGrid>控件。 这些列类型满足需求的最常见的方案，但也是更轻松地扩展或替换中的列类型比<xref:System.Windows.Forms.DataGrid>控件。 有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的列类型](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)。|  
|多个方式显示数据|<xref:System.Windows.Forms.DataGrid>控件仅限于从外部数据源显示数据。 <xref:System.Windows.Forms.DataGridView>控件，但是，可以显示在控件、 绑定的数据源或绑定和未绑定的数据存储在一起的未绑定的数据。 你也可以实现中的虚拟模式<xref:System.Windows.Forms.DataGridView>控件提供自定义数据管理。 有关详细信息，请参阅[在 Windows 窗体 DataGridView 控件中的数据显示模式](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)。|  
|自定义数据的显示多个方法|<xref:System.Windows.Forms.DataGridView>控件提供了很多属性和事件，您可以指定如何格式化和显示数据。 例如，你可以更改的单元格、 行和列具体取决于它们所包含的数据的外观或一个数据类型的数据替换为等效的另一种类型的数据。 有关详细信息，请参阅[数据格式在 Windows 窗体 DataGridView 控件中](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)。|  
|多个选项用于更改单元格、 行、 列和标头的外观和行为|<xref:System.Windows.Forms.DataGridView>控制，你可以使用单个网格组件以各种方式。 例如，可以冻结行和列，以防止它们滚动，则为隐藏行、 列和标头;更改调整行、 列和标头大小; 方法更改用户选择的方式并提供各个单元格、 行和列的工具提示和快捷菜单。|  
  
 <xref:System.Windows.Forms.DataGrid>控件将保留向后兼容性和特殊的需要。 对于几乎所有的用途，你应使用<xref:System.Windows.Forms.DataGridView>控件。 唯一的功能中提供<xref:System.Windows.Forms.DataGrid>中不可用的控件<xref:System.Windows.Forms.DataGridView>控件是在单个控件的两个相关表中的信息的层次结构显示。 您必须使用两个<xref:System.Windows.Forms.DataGridView>控件以显示的主/从关系中的两个表中的信息。  
  
## <a name="upgrading-to-the-datagridview-control"></a>升级到 DataGridView 控件  
 如果你的现有应用程序使用<xref:System.Windows.Forms.DataGrid>控件在简单数据绑定方案中不使用自定义项的情况下，只需可以有新的控件将旧的控件。 两个控件使用的标准的 Windows 窗体数据绑定体系结构，因此<xref:System.Windows.Forms.DataGridView>控件将显示绑定的数据无需额外配置。 你可能想要考虑利用数据绑定改进，但是，通过将绑定到数据<xref:System.Windows.Forms.BindingSource>组件，然后你可以将其绑定到<xref:System.Windows.Forms.DataGridView>控件。 有关详细信息，请参阅[BindingSource 组件](../../../../docs/framework/winforms/controls/bindingsource-component.md)。  
  
 因为<xref:System.Windows.Forms.DataGridView>控件具有全新的体系结构，将使你能够使用没有简单的转换路径<xref:System.Windows.Forms.DataGrid>包自定义<xref:System.Windows.Forms.DataGridView>控件。 许多<xref:System.Windows.Forms.DataGrid>自定义项都是使用不必要<xref:System.Windows.Forms.DataGridView>控制，但是，由于新控件中提供的内置功能。 如果你已创建的自定义列类型<xref:System.Windows.Forms.DataGrid>你想要使用的控件<xref:System.Windows.Forms.DataGridView>控件，你将需要实现它们再次使用新的体系结构。 有关详细信息，请参阅[自定义 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGrid>  
 <xref:System.Windows.Forms.BindingSource>  
 [DataGridView 控件](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [DataGrid 控件](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [BindingSource 组件](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Windows 窗体 DataGridView 控件中的列类型](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的单元格样式](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的数据显示模式](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的数据格式设置](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的重设大小选项](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的列排序模式](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的选择模式](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)  
 [自定义 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
