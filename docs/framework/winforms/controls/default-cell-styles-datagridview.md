---
title: 如何：使用设计器设置 Windows 窗体 DataGridView 控件的默认单元格样式和数据格式
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: 6d7d867b7c9e83b68589e046565bfb0199692f5f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658504"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器设置 Windows 窗体 DataGridView 控件的默认单元格样式和数据格式

使用<xref:System.Windows.Forms.DataGridView>控件, 可以为整个控件指定默认的单元格样式和单元数据格式, 对于行标题和列标题, 还可以指定用于交替行的默认单元格样式和单元数据格式。 为列和交替行设置的默认样式会重写为整个控件设置的默认样式。 此外, 在代码中为单个行和单元格设置的样式会重写默认样式。

有关单元格样式的详细信息, 请参阅[Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。 若要为交替行设置样式, [请参阅如何:使用设计器](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)为 Windows 窗体 DataGridView 控件设置交替行样式。

你还可以使用<xref:System.Windows.Forms.DataGridView.RowTemplate%2A>属性设置样式, 以影响将添加到控件中的所有行。 有关行模板的详细信息, 请参阅[如何:使用行模板自定义 Windows 窗体 DataGridView 控件](use-the-row-template-to-customize-rows-in-the-datagrid.md)中的行。

下面的过程需要一个**Windows 应用程序**项目, 该项目具有<xref:System.Windows.Forms.DataGridView>包含控件的窗体。 有关设置此类项目的信息, 请参阅[如何:创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)以及[如何:将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。

### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>设置控件中所有单元格的默认样式

1. 在设计器中选择控件。<xref:System.Windows.Forms.DataGridView>

2. 在 "**属性**" 窗口![中, 单击<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>、 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>或<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>属性旁边的省略号按钮 (Visual Studio](./media/visual-studio-ellipsis-button.png)的属性窗口中的省略号按钮 (...)。 此时将显示 " **CellStyle 生成器**" 对话框。

3. 通过设置属性来定义样式, 并使用**预览**窗格来确认你的选择。

> [!NOTE]
> 如果启用了视觉样式, 则行标题和列标题 (除外<xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) 将按当前主题自动样式, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>并覆盖和<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>属性值。
>
> 您可以使用设计器为多个<xref:System.Windows.Forms.DataGridView>选定的控件设置单元格样式, 但前提是它们对于要修改的单元格样式属性具有相同的值。 如果该属性的任何单元格样式不同, 则 " **CellStyle 生成器**" 对话框的 "**属性**" 窗口将为空白。

### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>设置单个列中单元格的默认样式

1. 在设计器中<xref:System.Windows.Forms.DataGridView>右键单击控件, 然后选择 "**编辑列**"。

2. 从 "**选定的列**" 列表中选择一列。

3. 在 "**列属性**" 网格中, 单击![ <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>属性旁边的省略号按钮 (Visual Studio](./media/visual-studio-ellipsis-button.png)的属性窗口中的省略号按钮 (...)。 此时将显示 " **CellStyle 生成器**" 对话框。

4. 通过设置属性来定义样式, 并使用**预览**窗格来确认你的选择。

### <a name="to-format-data-in-cells"></a>设置单元格中数据的格式

1. 使用上述过程之一来显示与默认单元格样式属性相关的 " **CellStyle Builder** " 对话框。

2. 在 " **CellStyle 生成器**" 对话框中, 单击![ <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>属性旁边的省略号按钮 (Visual Studio](./media/visual-studio-ellipsis-button.png)的属性窗口中的省略号按钮 (...)。 此时将显示 "**格式字符串**" 对话框。

3. 选择格式类型, 然后修改类型的详细信息 (例如要显示的小数位数), 并使用**示例**框确认所做的选择。

4. 如果要将该<xref:System.Windows.Forms.DataGridView>控件绑定到可能包含 null 值的数据源, 请在 " **null 值**" 文本框中填充。 当单元格值等于空引用 (`Nothing`在 Visual Basic 中) 或<xref:System.DBNull.Value?displayProperty=nameWithType>时, 将显示此值。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)
- [如何：使用设计器为 Windows 窗体 DataGridView 控件设置交替行样式](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)
