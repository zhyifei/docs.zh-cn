---
title: DataGridView 控件中的列类型
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], types
- DataGridView control [Windows Forms], column types
- data grids [Windows Forms], columns
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
ms.openlocfilehash: e918394cca6350854074d4c1567890138b2a1462
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743850"
---
# <a name="column-types-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的列类型
<xref:System.Windows.Forms.DataGridView> 控件使用多种列类型来显示其信息，并使用户能够修改或添加信息。  
  
 绑定 <xref:System.Windows.Forms.DataGridView> 控件并将 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> 属性设置为 `true`时，将使用适用于绑定数据源中包含的数据类型的默认列类型自动生成列。  
  
 你还可以自行创建任何列类的实例，并将它们添加到 <xref:System.Windows.Forms.DataGridView.Columns%2A> 属性返回的集合中。 您可以创建用作未绑定列的这些实例，也可以手动绑定它们。 手动绑定列很有用，例如，当您想要将一种类型的自动生成列替换为另一种类型的列时。  
  
 下表描述了可在 <xref:System.Windows.Forms.DataGridView> 控件中使用的各种列类。  
  
|类|描述|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|与基于文本的值一起使用。 当绑定到数字和字符串时自动生成。|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|与 <xref:System.Boolean> 和 <xref:System.Windows.Forms.CheckState> 值一起使用。 当绑定到这些类型的值时自动生成。|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|用于显示图像。 绑定到字节数组、<xref:System.Drawing.Image> 对象或 <xref:System.Drawing.Icon> 对象时自动生成。|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|用于显示单元中的按钮。 绑定时不自动生成。 通常用作未绑定的列。|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|用于在单元格中显示下拉列表。 绑定时不自动生成。 通常，手动进行数据绑定。|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|用于显示单元中的链接。 绑定时不自动生成。 通常，手动进行数据绑定。|  
|自定义列类型|你可以通过继承 <xref:System.Windows.Forms.DataGridViewColumn> 类或它的任何派生类来创建自己的列类，以提供自定义外观、行为或托管控件。 有关详细信息，请参阅[如何：通过扩展其行为和外观自定义 Windows 窗体 DataGridView 控件中的单元格和列](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)|  
  
 以下各节将更详细地介绍这些列类型。  
  
## <a name="datagridviewtextboxcolumn"></a>DataGridViewTextBoxColumn  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn> 是一种通用列类型，适用于基于文本的值（如数字和字符串）。 在编辑模式下，<xref:System.Windows.Forms.TextBox> 控件显示在活动单元格中，使用户能够修改单元值。  
  
 单元值自动转换为字符串以显示。 系统会自动分析输入或修改的值，以创建适当数据类型的单元值。 您可以通过处理 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.CellFormatting> 和 <xref:System.Windows.Forms.DataGridView.CellParsing> 事件来自定义这些转换。  
  
 列的单元格值数据类型在列的 <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> 属性中指定。  
  
## <a name="datagridviewcheckboxcolumn"></a>DataGridViewCheckBoxColumn  
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> 与 <xref:System.Boolean> 和 <xref:System.Windows.Forms.CheckState> 值一起使用。 <xref:System.Boolean> 值显示为两状态或三状态复选框，具体取决于 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> 属性的值。 将列绑定到 <xref:System.Windows.Forms.CheckState> 值后，默认情况下将 `true` <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> 属性值。  
  
 通常，复选框单元值适用于存储（如任何其他数据）或用于执行批量操作。 如果希望在用户单击复选框单元时立即做出响应，可以处理 <xref:System.Windows.Forms.DataGridView.CellClick> 事件，但此事件发生在更新单元格值之前。 如果在单击时需要新值，一个选项是根据当前值计算预期值的值。 另一种方法是立即提交更改，并处理 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 事件来对其进行响应。 若要在单击单元格时提交更改，必须处理 <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged> 事件。 在处理程序中，如果当前单元格为复选框单元，则调用 <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> 方法，并传入 <xref:System.Windows.Forms.DataGridViewDataErrorContexts.Commit> 值。  
  
## <a name="datagridviewimagecolumn"></a>DataGridViewImageColumn  
 <xref:System.Windows.Forms.DataGridViewImageColumn> 用于显示图像。 可以从数据源自动填充图像列，手动填充未绑定的列，或在 <xref:System.Windows.Forms.DataGridView.CellFormatting> 事件的处理程序中动态填充。  
  
 数据源中的图像列的自动填充可处理多种图像格式的字节数组，包括 <xref:System.Drawing.Image> 类支持的所有格式和 Microsoft® Access 和 Northwind 示例数据库所使用的 OLE 图片格式。  
  
 如果希望提供 <xref:System.Windows.Forms.DataGridViewButtonColumn>的功能，但具有自定义外观，则手动填充 image 列很有用。 您可以处理 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 事件以响应图像单元内的单击。  
  
 如果要为计算值或非图像格式的值提供图像，则在 <xref:System.Windows.Forms.DataGridView.CellFormatting> 事件的处理程序中填充 image 列的单元格非常有用。 例如，您可能有一个 "风险" 列，其中包含要显示为图标 `"high"`、`"middle"`和 `"low"` 的字符串值。 或者，您可能有一个 "图像" 列包含必须加载的映像的位置，而不是映像的二进制内容。  
  
## <a name="datagridviewbuttoncolumn"></a>DataGridViewButtonColumn  
 使用 <xref:System.Windows.Forms.DataGridViewButtonColumn>，可以显示包含按钮的单元格的列。 当你希望为用户提供一种简单的方法来对特定记录执行操作（例如，在单独的窗口中放置订单或显示子记录）时，这非常有用。  
  
 在对 <xref:System.Windows.Forms.DataGridView> 控件进行数据绑定时，不会自动生成按钮列。 若要使用按钮列，必须手动创建它们，并将它们添加到 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType> 属性返回的集合中。  
  
 您可以通过处理 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 事件来响应按钮单元中的用户单击。  
  
## <a name="datagridviewcomboboxcolumn"></a>DataGridViewComboBoxColumn  
 使用 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>，可以显示包含下拉列表框的单元格的列。 这对于只能包含特定值的字段中的数据输入很有用，如 Northwind 示例数据库中 Products 表的 "类别" 列。  
  
 您可以使用与填充 <xref:System.Windows.Forms.ComboBox> 下拉列表相同的方式来填充用于所有单元格的下拉列表，方法是：手动通过 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> 属性返回的集合，或通过 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>、<xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>和 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 属性将其绑定到数据源。 有关详细信息，请参阅[ComboBox 控件](combobox-control-windows-forms.md)。  
  
 通过设置 <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType>的 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> 属性，可以将实际单元值绑定到 <xref:System.Windows.Forms.DataGridView> 控件所使用的数据源。  
  
 在对 <xref:System.Windows.Forms.DataGridView> 控件进行数据绑定时，不会自动生成组合框列。 若要使用组合框列，必须手动创建它们，并将它们添加到 <xref:System.Windows.Forms.DataGridView.Columns%2A> 属性返回的集合中。  
  
## <a name="datagridviewlinkcolumn"></a>DataGridViewLinkColumn  
 使用 <xref:System.Windows.Forms.DataGridViewLinkColumn>，可以显示包含超链接的单元格的列。 这适用于数据源中的 URL 值或作为特殊行为（如打开包含子记录的窗口）的 "按钮" 列的替代项。  
  
 在对 <xref:System.Windows.Forms.DataGridView> 控件进行数据绑定时，不会自动生成链接列。 若要使用链接列，必须手动创建它们，并将它们添加到 <xref:System.Windows.Forms.DataGridView.Columns%2A> 属性返回的集合中。  
  
 可以通过处理 <xref:System.Windows.Forms.DataGridView.CellContentClick> 事件来响应用户单击的链接。 此事件与 <xref:System.Windows.Forms.DataGridView.CellClick> 和 <xref:System.Windows.Forms.DataGridView.CellMouseClick> 事件不同，用户单击单元格中的任意位置时发生此事件。  
  
 <xref:System.Windows.Forms.DataGridViewLinkColumn> 类提供多个属性，用于修改单击之前、期间和之后的链接的外观。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewButtonColumn>
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewImageColumn>
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>
- <xref:System.Windows.Forms.DataGridViewLinkColumn>
- [DataGridView 控件](datagridview-control-windows-forms.md)
- [如何：在 Windows 窗体 DataGridView 控件的单元格中显示图像](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)
- [如何：使用 Windows 窗体 DataGridView 控件中的图像列](how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)
- [自定义 Windows 窗体 DataGridView 控件](customizing-the-windows-forms-datagridview-control.md)
