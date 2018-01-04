---
title: "Windows 窗体 DataGridView 控件中的列类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- columns [Windows Forms], types
- DataGridView control [Windows Forms], column types
- data grids [Windows Forms], columns
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 92c6881fe876bba3fe0224a358a9b12767d53f0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="column-types-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的列类型
<xref:System.Windows.Forms.DataGridView>控件使用几种列类型来显示其信息，并且使用户能够修改或添加信息。  
  
 当绑定<xref:System.Windows.Forms.DataGridView>控件并设置<xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A>属性`true`，列会自动生成使用适合包含在绑定的数据源中的数据类型的默认列类型。  
  
 也可以自己创建的任何列类的实例，然后将它们添加到返回的集合<xref:System.Windows.Forms.DataGridView.Columns%2A>属性。 可以创建为未绑定列，这些实例以供使用，或者你可以手动将其绑定。 手动绑定的列非常有用，例如，如果你想要将替换为另一种类型的列的一种类型的自动生成的列。  
  
 下表描述了可在中使用的各个列类<xref:System.Windows.Forms.DataGridView>控件。  
  
|类|描述|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|与基于文本的值一起使用。 绑定到数字和字符串时自动生成。|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|与使用<xref:System.Boolean>和<xref:System.Windows.Forms.CheckState>值。 绑定到这些类型的值时自动生成。|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|用于显示图像。 绑定到字节数组时自动生成<xref:System.Drawing.Image>对象，或<xref:System.Drawing.Icon>对象。|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|用于在单元格中显示按钮。 绑定时，不自动生成。 通常用作未绑定的列。|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|用于显示在单元格中下拉列表。 绑定时，不自动生成。 通常手动进行数据绑定。|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|用于在单元格中显示链接。 绑定时，不自动生成。 通常手动进行数据绑定。|  
|你的自定义列类型|你可以通过继承来创建您自己的列类<xref:System.Windows.Forms.DataGridViewColumn>类或任何其派生的类来提供自定义外观、 行为或托管的控件。 有关详细信息，请参阅[如何： 自定义单元格和扩展他们行为和外观由 Windows 窗体 DataGridView 控件中的列](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)|  
  
 下列部分中的更详细地介绍了这些列类型。  
  
## <a name="datagridviewtextboxcolumn"></a>DataGridViewTextBoxColumn  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn>是用于基于文本的值，例如数字和字符串的通用的列类型。 在编辑模式下，<xref:System.Windows.Forms.TextBox>控件将显示在活动的单元格，使用户能够修改单元格的值。  
  
 单元格的值自动转换为字符串以供显示。 输入或修改的用户的值是自动进行分析以创建相应的数据类型的一个单元格值。 您可以通过处理来自定义这些转换<xref:System.Windows.Forms.DataGridView.CellFormatting>和<xref:System.Windows.Forms.DataGridView.CellParsing>的事件<xref:System.Windows.Forms.DataGridView>控件。  
  
 中指定列的单元格值数据类型<xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A>列属性。  
  
## <a name="datagridviewcheckboxcolumn"></a>DataGridViewCheckBoxColumn  
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>用于<xref:System.Boolean>和<xref:System.Windows.Forms.CheckState>值。 <xref:System.Boolean>值显示为两个状态或三态复选框，具体取决于值<xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A>属性。 当列绑定到<xref:System.Windows.Forms.CheckState>值，<xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A>属性值是`true`默认情况下。  
  
 通常情况下，复选框单元格值旨在用于存储，如任何其他数据，或执行大容量操作。 如果你想要立即当用户单击复选框单元格，你可以处理响应<xref:System.Windows.Forms.DataGridView.CellClick>事件，但此事件发生之前更新单元格的值。 如果在单击时需要的新值，一个选项是计算所需的值将是基于当前值。 另一种方法是立即提交更改并处理<xref:System.Windows.Forms.DataGridView.CellValueChanged>事件以对其做出响应。 若要在单击单元格时，请提交更改，你必须处理<xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged>事件。 在处理程序中，如果当前单元格，复选框单元格调用<xref:System.Windows.Forms.DataGridView.CommitEdit%2A>方法并传入<xref:System.Windows.Forms.DataGridViewDataErrorContexts.Commit>值。  
  
## <a name="datagridviewimagecolumn"></a>DataGridViewImageColumn  
 <xref:System.Windows.Forms.DataGridViewImageColumn>用于显示图像。 图像列可以从数据源将自动填充、 手动填充对于未绑定列，或在处理程序中动态填充<xref:System.Windows.Forms.DataGridView.CellFormatting>事件。  
  
 数据源的 image 列自动填充适用于在多个映像格式，包括支持的所有格式的字节数组<xref:System.Drawing.Image>类和使用 Microsoft® Access 和 Northwind 示例数据库的 OLE 图片格式。  
  
 手动填充 image 列很有用，当你想要提供的功能时<xref:System.Windows.Forms.DataGridViewButtonColumn>，但与自定义的外观。 你可以处理<xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType>事件能够响应图像单元格中的单击。  
  
 填充的处理程序中的图像列的单元格<xref:System.Windows.Forms.DataGridView.CellFormatting>事件非常有用，如果你想要为计算出的值或非图像格式的值提供映像。 例如，可能必须具有字符串值的"风险"列如`"high"`， `"middle"`，和`"low"`你想要以图标形式显示。 或者，你可能拥有"Image"列包含必须加载而不是映像的二进制内容的映像的位置。  
  
## <a name="datagridviewbuttoncolumn"></a>DataGridViewButtonColumn  
 与<xref:System.Windows.Forms.DataGridViewButtonColumn>，可以显示一列包含按钮的单元格。 当你想要提供用于轻松对用户执行特定的记录，例如下单，或在单独的窗口中显示子记录的操作时，这非常有用。  
  
 数据绑定时，不会自动生成按钮列<xref:System.Windows.Forms.DataGridView>控件。 若要使用按钮列，你必须手动创建它们，并将它们添加到返回的集合<xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>属性。  
  
 可以通过处理来响应用户单击按钮单元格中<xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType>事件。  
  
## <a name="datagridviewcomboboxcolumn"></a>DataGridViewComboBoxColumn  
 与<xref:System.Windows.Forms.DataGridViewComboBoxColumn>，可以显示包含下拉列表框的单元格的列。 这可用于在只能包含特定值，例如 Northwind 示例数据库中的产品表的分类列的字段中输入数据。  
  
 你可以填充下拉列表用于在相同的方式将填充所有单元格<xref:System.Windows.Forms.ComboBox>下拉列表中，手动通过返回的集合<xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>属性，或通过将其绑定到数据源通过<xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>， <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>，和<xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>属性。 有关详细信息，请参阅[ComboBox 控件](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)。  
  
 你可以将实际的单元值绑定到使用的数据源<xref:System.Windows.Forms.DataGridView>通过设置<xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A>属性<xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType>。  
  
 数据绑定时，不会自动生成组合框列<xref:System.Windows.Forms.DataGridView>控件。 若要使用组合框列，你必须手动创建它们，并将它们添加到返回的集合<xref:System.Windows.Forms.DataGridView.Columns%2A>属性。  
  
## <a name="datagridviewlinkcolumn"></a>DataGridViewLinkColumn  
 与<xref:System.Windows.Forms.DataGridViewLinkColumn>，可以显示一列包含超链接的单元格。 这可用于 URL 值中的数据源或作为特殊的行为，例如使用子记录打开一个窗口按钮列的替代方法。  
  
 数据绑定时，不会自动生成链接列<xref:System.Windows.Forms.DataGridView>控件。 若要使用链接列，你必须手动创建它们，并将它们添加到返回的集合<xref:System.Windows.Forms.DataGridView.Columns%2A>属性。  
  
 可以通过处理来响应用户单击链接上<xref:System.Windows.Forms.DataGridView.CellContentClick>事件。 此事件是不同于<xref:System.Windows.Forms.DataGridView.CellClick>和<xref:System.Windows.Forms.DataGridView.CellMouseClick>用户单击单元格中的任何位置时发生的事件。  
  
 <xref:System.Windows.Forms.DataGridViewLinkColumn>类提供了几个属性用于修改链接的外观之前,、 之中以及之后在被单击。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewButtonColumn>  
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewImageColumn>  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewLinkColumn>  
 [DataGridView 控件](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [如何：在 Windows 窗体 DataGridView 控件的单元格中显示图像](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 [如何：使用 Windows 窗体 DataGridView 控件中的图像列](../../../../docs/framework/winforms/controls/how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)  
 [自定义 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
