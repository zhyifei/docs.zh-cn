---
title: 在 DataGridView 控件中使用新记录行
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
ms.openlocfilehash: 2fcd35f8c4d04909cdbc26f6a4293fdd570385b8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728333"
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>在 Windows 窗体 DataGridView 控件中使用新记录行
使用 <xref:System.Windows.Forms.DataGridView> 在应用程序中编辑数据时，通常需要为用户提供将新数据行添加到数据存储区的能力。 <xref:System.Windows.Forms.DataGridView> 控件通过为新记录（始终显示为最后一行）提供一行来支持此功能。 它在其行标题中标记有一个星号（*）符号。 以下各节讨论了在对启用了新记录的行进行编程时应考虑的一些事项。  
  
## <a name="displaying-the-row-for-new-records"></a>显示新记录的行  
 使用 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 属性指示是否显示新记录的行。 此属性的默认值为 `true`。  
  
 对于数据绑定事例，如果控件的 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 属性和数据源的 <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> 属性均 `true`，则将显示新记录的行。 如果 `false`，则不会显示该行。  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>用默认数据填充新记录行  
 当用户将新记录的行选为当前行时，<xref:System.Windows.Forms.DataGridView> 控件将引发 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 事件。  
  
 此事件提供对新 <xref:System.Windows.Forms.DataGridViewRow> 的访问，并使你能够使用默认数据填充新行。 有关详细信息，请参阅[如何：在 Windows 窗体 DataGridView 控件中指定新行的默认值](specify-default-values-for-new-rows-in-the-datagrid.md)  
  
## <a name="the-rows-collection"></a>Rows 集合  
 新记录的行包含在 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.Rows%2A> 集合中，但在两个方面具有不同的行为：  
  
- 不能以编程方式从 <xref:System.Windows.Forms.DataGridView.Rows%2A> 集合中删除新记录的行。 如果尝试这样做，则会引发 <xref:System.InvalidOperationException>。 用户也无法删除新记录所在的行。 <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> 方法不会从 <xref:System.Windows.Forms.DataGridView.Rows%2A> 集合中删除此行。  
  
- 不能在新记录行后添加行。 如果尝试，则会引发 <xref:System.InvalidOperationException>。 因此，新记录的行总是 <xref:System.Windows.Forms.DataGridView> 控件中的最后一行。 <xref:System.Windows.Forms.DataGridViewRowCollection> 上的方法添加行（<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>、<xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>和 <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>），所有这些都是在新记录的行出现时在内部调用插入方法。  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>新记录的行的可视化自定义  
 当创建新记录行时，将基于 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 属性指定的行。 未为此行指定的任何单元格样式将从其他属性继承。 有关单元样式继承的详细信息，请参阅[Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。  
  
 将从每个单元格的 <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> 属性检索新记录所在行中的单元格显示的初始值。 对于类型 <xref:System.Windows.Forms.DataGridViewImageCell>的单元格，此属性将返回占位符图像。 否则，此属性将返回 `null`。 您可以重写此属性以返回自定义值。 但是，当焦点进入新记录行时，这些初始值可以由 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 事件处理程序替换。  
  
 此行标题的标准图标（箭头或星号）不公开公开。 如果要自定义图标，将需要创建一个自定义 <xref:System.Windows.Forms.DataGridViewRowHeaderCell> 类。  
  
 标准图标使用由行标题单元格使用 <xref:System.Windows.Forms.DataGridViewCellStyle> 的 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 属性。 如果没有足够的空间来完全显示标准图标，则不会呈现标准图标。  
  
 如果行标题单元格设置了字符串值，并且文本和图标没有足够的空间，则会先删除该图标。  
  
## <a name="sorting"></a>排序  
 在未绑定模式下，即使用户已对 <xref:System.Windows.Forms.DataGridView>的内容进行排序，新记录也将始终添加到 <xref:System.Windows.Forms.DataGridView> 末尾。 用户需要再次应用排序，才能将行排序到正确位置;此行为与 <xref:System.Windows.Forms.ListView> 控件的行为类似。  
  
 在数据绑定和虚拟模式下，应用排序时的插入行为将取决于数据模型的实现。 对于 ADO.NET，该行会立即排序到正确的位置。  
  
## <a name="other-notes-on-the-row-for-new-records"></a>新记录所在行的其他备注  
 不能将此行的 <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> 属性设置为 `false`。 如果尝试，则会引发 <xref:System.InvalidOperationException>。  
  
 新记录的行始终创建为未选定状态。  
  
## <a name="virtual-mode"></a>虚拟模式  
 如果要实现虚拟模式，则需要跟踪数据模型中何时需要新记录的行以及何时回滚行的添加。 此功能的确切实现取决于数据模型的实现及其事务语义，例如，提交作用域是位于单元级还是行级。 有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的虚拟模式](virtual-mode-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Windows 窗体 DataGridView 控件中的数据输入](data-entry-in-the-windows-forms-datagridview-control.md)
- [如何：指定 Windows 窗体 DataGridView 控件中新行的默认值](specify-default-values-for-new-rows-in-the-datagrid.md)
