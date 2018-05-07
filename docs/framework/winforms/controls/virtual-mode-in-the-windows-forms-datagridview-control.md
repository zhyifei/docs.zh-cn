---
title: Windows 窗体 DataGridView 控件中的虚拟模式
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], virtual mode
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
ms.openlocfilehash: 2e5724da4442bbfcb0928c864f78744b946acc18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="virtual-mode-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的虚拟模式
虚拟模式中，你可以管理之间的交互<xref:System.Windows.Forms.DataGridView>控制和自定义数据缓存。 若要实现虚拟模式，设置<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性`true`并处理一个或多个本主题中所述的事件。 通常，你需要处理至少`CellValueNeeded`事件，它使查找数据缓存中的值的控件。  
  
## <a name="bound-mode-and-virtual-mode"></a>绑定的模式和虚拟模式  
 仅在需要来补充或取代绑定的模式时，才需要虚拟模式。 在绑定模式下，你将设置<xref:System.Windows.Forms.DataGridView.DataSource%2A>属性和控件自动将数据加载从指定的源，然后提交用户返回到该更改。 可以控制哪些绑定的列会显示，并且数据源本身通常会处理如排序操作。  
  
## <a name="supplementing-bound-mode"></a>补充绑定的模式  
 你可以通过显示未绑定的列，以及绑定的列来补充绑定的模式。 这有时称为"混合的模式"，可用于显示某些操作，如计算的值或用户界面 (UI) 控制。  
  
 由于未绑定的列是外部数据源，它们将忽略由数据源的排序操作。 因此，当你启用排序在混合模式下时，你必须管理在本地缓存中的未绑定的数据和实现虚拟模式以使<xref:System.Windows.Forms.DataGridView>控件与之进行交互。  
  
 有关使用虚拟模式来维护未绑定列中的值的详细信息，请参阅中的示例<xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType>属性和<xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType>类参考主题。  
  
## <a name="replacing-bound-mode"></a>替换绑定的模式  
 如果绑定的模式不满足性能需求，你可以管理通过虚拟模式事件处理程序自定义缓存中的所有数据。 例如，可以使用的虚拟模式以实现在实时数据加载机制，以仅检索多的数据从联网数据库需要的最佳性能。 这种情况下使用大量的数据通过慢速网络连接或使用具有有限的 RAM 或存储空间的客户端计算机时特别有用。  
  
 有关在实时方案中使用的虚拟模式的详细信息，请参阅[实时数据加载在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)。  
  
## <a name="virtual-mode-events"></a>虚拟模式事件  
 如果你的数据是只读的`CellValueNeeded`事件可能是你将需要处理的唯一事件。 其他虚拟模式事件，可以启用特定功能，例如，用户编辑、 添加行和删除和行级事务。  
  
 某些标准<xref:System.Windows.Forms.DataGridView>事件 （如用户添加或删除行，或单元格时值时发生的事件是编辑、 分析、 验证，或格式化） 可在虚拟模式。 你还可以处理可以维护中的绑定的数据源，如单元格工具提示文本、 单元格和行错误文本、 单元格和行快捷菜单数据和行高度数据通常不存储的值的事件。  
  
 有关实现虚拟模式来管理与行级提交作用域的读/写数据的详细信息，请参阅[演练： 在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)。  
  
 有关实现虚拟模式与单元格级提交作用域示例，请参阅<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性参考主题。  
  
 仅发生以下事件时<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性设置为`true`。  
  
|事件|描述|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|由该控件用于从显示的数据缓存中检索一个单元格值。 仅对未绑定的列中的单元格的发生此事件。|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|使用控件来提交到数据缓存的单元格的用户输入。 仅对未绑定的列中的单元格的发生此事件。<br /><br /> 调用<xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A>方法时更改缓存的值之外的<xref:System.Windows.Forms.DataGridView.CellValuePushed>事件处理程序以确保，在控件中显示的当前值并应用当前有效的任何自动调整大小模式。|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|该控件用于指示数据缓存中的新行的需求。|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|该控件用于确定行是否有任何未提交的更改。|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|该控件用于指示一个行应恢复到其缓存的值。|  
  
 以下事件可在虚拟模式下，但可以使用而不考虑<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性设置。  
  
|事件|描述|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|该控件用于指示当删除行，或添加，从而相应地更新数据缓存。|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|值的格式单元格控件使用它进行显示，以及进行分析和验证用户输入。|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|该控件用于检索单元格工具提示文本时<xref:System.Windows.Forms.DataGridView.DataSource%2A>设置属性或<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性是`true`。<br /><br /> 显示单元格工具提示时，才<xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A>属性值是`true`。|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|该控件用于检索单元格或行错误文本时<xref:System.Windows.Forms.DataGridView.DataSource%2A>设置属性或<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性是`true`。<br /><br /> 调用<xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A>方法或<xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A>方法时更改单元格或行错误文本，以确保在控件中显示的当前值。<br /><br /> 显示单元格和行错误标志符号时<xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A>和<xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A>属性的值为`true`。|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|该控件用于检索单元格或行<xref:System.Windows.Forms.ContextMenuStrip>时控件<xref:System.Windows.Forms.DataGridView.DataSource%2A>设置属性或<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性是`true`。|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|使用控件来检索或存储的数据缓存中的行高度信息。 调用<xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A>方法更改之外的缓存的行高度信息时<xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>事件处理程序来确保，在显示控件中使用的当前值。|  
  
## <a name="best-practices-in-virtual-mode"></a>中的虚拟模式的最佳做法  
 如果你要实现虚拟模式，若要有效地使用大量的数据，你也要确保与你也会有效地工作<xref:System.Windows.Forms.DataGridView>控件本身。 有关有效地使用的单元格样式、 自动调整大小、 选择和行共享的详细信息，请参阅[缩放 Windows 窗体 DataGridView 控件的最佳做法](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 [Windows 窗体 DataGridView 控件中的性能调整](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [有关缩放 Windows 窗体 DataGridView 控件的最佳做法](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 [在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
