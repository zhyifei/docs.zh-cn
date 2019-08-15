---
title: 如何：使用设计器向 Windows 窗体 DataGrid 控件添加表和列
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: d11c4f7e4cdfb597477bb99f38612ed648849f20
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040043"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>如何：使用设计器向 Windows 窗体 DataGrid 控件添加表和列

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。

<xref:System.Windows.Forms.DataGrid>通过创建<xref:System.Windows.Forms.DataGridTableStyle>对象<xref:System.Windows.Forms.DataGrid>并将其添加到<xref:System.Windows.Forms.DataGrid.TableStyles%2A>对象 (通过控件的属性访问), 可以在表和列的 Windows 窗体控件中显示数据。 <xref:System.Windows.Forms.GridTableStylesCollection> 每个表样式显示在的<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> <xref:System.Windows.Forms.DataGridTableStyle>属性中指定的任何数据表的内容。 默认情况下, 未指定列样式的表样式将显示该数据表中的所有列。 您可以<xref:System.Windows.Forms.DataGridColumnStyle>通过将对象添加<xref:System.Windows.Forms.GridColumnStylesCollection>到来限制表中的哪些列的显示, <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>这可通过每个<xref:System.Windows.Forms.DataGridTableStyle>的属性进行访问。

以下过程需要具有包含<xref:System.Windows.Forms.DataGrid>控件的窗体的**Windows 应用程序**项目。 有关如何设置此类项目的信息, 请参阅[如何:创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)以及[如何:将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。 默认情况下, 在 Visual Studio 2005 <xref:System.Windows.Forms.DataGrid>中, 控件不在**工具箱**中。 有关添加它的信息, 请[参阅如何:向 "工具箱](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))" 添加项。

### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>在设计器中向 DataGrid 控件添加表

1. 若要在表中显示数据, 必须先将<xref:System.Windows.Forms.DataGrid>控件绑定到数据集。 有关详细信息，请参阅[如何：使用设计器](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)将 Windows 窗体 DataGrid 控件绑定到数据源。

2. 在 "属性窗口中<xref:System.Windows.Forms.DataGrid.TableStyles%2A>选择![](./media/visual-studio-ellipsis-button.png)控件的属性, 然后单击省略号按钮 (Visual Studio 的属性窗口中的省略号按钮 (...), 以显示<xref:System.Windows.Forms.DataGrid>**DataGridTableStyle 集合编辑器**。

3. 在集合编辑器中, 单击 "**添加**" 以插入表样式。

4. 单击 **"确定"** 以关闭 "集合编辑器", 然后单击<xref:System.Windows.Forms.DataGrid.TableStyles%2A>属性旁的省略号按钮以重新打开它。

     重新打开 "集合编辑器" 时, 绑定到该控件的任何数据表都将出现在表样式的<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>属性的下拉列表中。

5. 在集合编辑器的 "**成员**" 框中, 单击表样式。

6. 在 "集合编辑器" 的 "**属性**" 框中<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> , 选择要显示的表的值。

### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>在设计器中向 DataGrid 控件添加列

1. 在**DataGridTableStyle 集合编辑器**的 "**成员**" 框中, 选择适当的表样式。 在集合编辑器的 "**属性**" 框中, 选择<xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>集合, 然后单击省略号按钮 (![Visual Studio 的属性窗口中的省略号按钮 (...)。](./media/visual-studio-ellipsis-button.png)显示**System.windows.forms.datagridcolumnstyle> 集合编辑器**。

2. 在集合编辑器中, 单击 "**添加**" 以插入列样式, 或者单击 "**添加**" 旁边的向下箭头以指定列类型。

     在下拉框中, 可以选择<xref:System.Windows.Forms.DataGridTextBoxColumn>或<xref:System.Windows.Forms.DataGridBoolColumn>类型。

3. 单击 "确定" 以关闭 " **system.windows.forms.datagridcolumnstyle> 集合编辑器**", 然后单击<xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>属性旁的省略号按钮以重新打开它。

     重新打开 "集合编辑器" 时, 绑定的数据表中的所有数据列都将显示在该列样式的<xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A>属性的下拉列表中。

4. 在集合编辑器的 "**成员**" 框中, 单击列样式。

5. 在 "集合编辑器" 的 "**属性**" 框中<xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> , 选择要显示的列的值。

## <a name="see-also"></a>请参阅

- [DataGrid 控件](datagrid-control-windows-forms.md)
- [如何：删除或隐藏 Windows 窗体 DataGrid 控件中的列](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
