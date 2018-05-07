---
title: Windows 窗体 DataGridView 控件中的数据显示模式
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
ms.openlocfilehash: f97576218df651553ed1ac5f681d1ec0b4ab5ef3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的数据显示模式
<xref:System.Windows.Forms.DataGridView>控件可以在三种不同模式中显示数据： 绑定、 未绑定，和虚拟。 选择最合适的模式，基于你的要求。  
  
## <a name="unbound"></a>未绑定  
 未绑定的模式适合于显示相对较少量的编程方式管理的数据。 你不附加<xref:System.Windows.Forms.DataGridView>直接与数据源如下所示绑定模式的控件。 相反，你必须亲自填充该控件，通常通过使用<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType>方法。  
  
 未绑定的模式可以是静态的只读数据，或当你想要自己进行交互的代码提供外部数据存储时特别有用。 如果你想你与外部数据源进行交互的用户，但是，你通常会使用绑定的模式。  
  
 使用只读的示例，未绑定<xref:System.Windows.Forms.DataGridView>，请参阅[如何： 创建未绑定的 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)。  
  
## <a name="bound"></a>绑定  
 绑定的模式是适用于管理使用与数据存储区的自动交互的数据。 你可以将附加<xref:System.Windows.Forms.DataGridView>直接到通过设置其数据源的控件<xref:System.Windows.Forms.DataGridView.DataSource%2A>属性。 数据绑定控件时，推送和拉取而无需显式管理您的数据行。 当<xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A>属性是`true`，每个列中数据源将导致控件中创建相对应的列。 如果想要创建自己的列，可以将此属性设置为`false`并用<xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A>属性可将每个列绑定时将其配置。 当你想要使用的列类型不默认生成的类型时，这非常有用。 有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的列类型](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)。  
  
 有关示例，使用绑定<xref:System.Windows.Forms.DataGridView>控制，请参阅[演练： 验证 Windows 窗体 DataGridView 控件中的数据](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)。  
  
 你还可以添加到未绑定的列<xref:System.Windows.Forms.DataGridView>中绑定模式的控件。 当你想要显示一列的按钮或链接，使用户能够在特定行上执行操作时，这非常有用。 也很有用，与值计算的值绑定的列中显示列。 你可以填充的处理程序中的计算列的单元格值<xref:System.Windows.Forms.DataGridView.CellFormatting>事件。 如果你使用<xref:System.Data.DataSet>或<xref:System.Data.DataTable>作为数据源，但是，你可能想要使用<xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>属性改为创建计算的列。 在这种情况下，<xref:System.Windows.Forms.DataGridView>控件会将计算的列就像任何其他列中的数据源一样。  
  
 不支持按在绑定模式下的未绑定列进行排序。 如果在包含用户可编辑值的绑定模式下创建的未绑定的列，则必须实现虚拟模式来维护这些值，当对控件进行排序的绑定的列。  
  
## <a name="virtual"></a>虚拟  
 虚拟模式中，你可以实现你自己的数据管理操作。 这是必要时对控件进行排序的绑定的列保持在绑定模式下的未绑定列的值。 但是，虚拟模式的主要用途是在与大量的数据进行交互时优化性能。  
  
 您附加<xref:System.Windows.Forms.DataGridView>控制对缓存的管理和你的代码控制何时推送和拉取数据行。 若要减少内存占用量，缓存应在大小上类似于当前显示的行数。 当用户滚动到视图中新行时，你的代码将从缓存请求新数据，并 （可选） 从内存刷新旧的数据。  
  
 在实现虚拟模式时，你将需要跟踪新行回滚新行添加到需要在数据模型且时。 此功能的正确实现将取决于数据模型的实现以及数据模型中; 的事务语义是否提交作用域是单元格或行级别。  
  
 有关虚拟模式的详细信息，请参阅[Windows 窗体 DataGridView 控件中的虚拟模式](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)。 有关演示如何使用虚拟模式事件示例，请参阅[演练： 在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>  
 [在 Windows 窗体 DataGridView 控件中显示数据](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的列类型](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 [演练：创建未绑定 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 [如何：将数据绑定到 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的虚拟模式](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)
