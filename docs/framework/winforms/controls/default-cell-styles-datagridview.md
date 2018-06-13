---
title: 如何：使用设计器设置 Windows 窗体 DataGridView 控件的默认单元格样式和数据格式
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: 47e15afe71ed3497b634e965c96badcee2fe3ed4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529933"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器设置 Windows 窗体 DataGridView 控件的默认单元格样式和数据格式
<xref:System.Windows.Forms.DataGridView>控制可用于指定默认单元格样式和单元格为整个控件、 特定列的、 行和列标题和为交替行创建帐目型效果的数据格式。 设置整个控件的默认样式中被重写默认列和交替行样式设置中。 此外，在单独的行和单元格的代码中设置的样式重写默认样式。  
  
 单元格样式有关的详细信息，请参阅[在 Windows 窗体 DataGridView 控件中的单元格样式](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)。 若要设置交替行样式，请参阅[如何： 设置 Windows 窗体 DataGridView 控件使用设计器交替行样式](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)。  
  
 你还可以设置使用的样式<xref:System.Windows.Forms.DataGridView.RowTemplate%2A>属性以影响将添加到控件的所有行。 有关行模板的详细信息，请参阅[如何： 在 Windows 窗体 DataGridView 控件中使用行模板自定义行](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)。  
  
 下面的过程要求**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.DataGridView>控件。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>若要设置控件中的所有单元格的默认样式  
  
1.  选择<xref:System.Windows.Forms.DataGridView>设计器中的控件。  
  
2.  在**属性**窗口中，单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>， <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>，或<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>属性。 **CellStyle 生成器**对话框随即出现。  
  
3.  通过设置属性，请使用定义样式**预览**窗格中，以确认你的选择。  
  
> [!NOTE]
>  如果启用了可视样式，行和列标题 (除<xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) 样式将自动由当前的主题中，重写<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>和<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>属性值。  
>   
>  你可以设置为多个选定的单元格样式<xref:System.Windows.Forms.DataGridView>控制使用设计器中的，但仅，如果它们具有你想要修改的单元格样式属性的相同值。 如果任何单元格样式不同于该属性，**属性**的 windows **CellStyle 生成器**对话框中将为空。  
  
### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>在单个列中设置单元格的默认样式  
  
1.  右键单击<xref:System.Windows.Forms.DataGridView>控制在设计器并选择**编辑列**。  
  
2.  选择从列**选定的列**列表。  
  
3.  在**列属性**网格中，单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>属性。 **CellStyle 生成器**对话框随即出现。  
  
4.  通过设置属性，请使用定义样式**预览**窗格中，以确认你的选择。  
  
### <a name="to-format-data-in-cells"></a>若要设置单元格中的数据的格式  
  
1.  使用前面的过程之一来显示**CellStyle 生成器**对话框相关的默认单元格样式属性。  
  
2.  在**CellStyle 生成器**对话框框中，单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>属性。 **格式字符串**对话框随即出现。  
  
3.  选择一个格式类型，然后修改的类型 （例如要显示的小数位数） 的详细信息使用**示例**框以确认你的选择。  
  
4.  如果你正在绑定<xref:System.Windows.Forms.DataGridView>控件添加到数据源都可能包含 null 值、 填写**Null 值**文本框。 此值将显示当单元格的值等于空引用 (`Nothing`在 Visual Basic 中) 或<xref:System.DBNull.Value?displayProperty=nameWithType>。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>  
 [Windows 窗体 DataGridView 控件中的单元格样式](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [如何：使用设计器设置 Windows 窗体 DataGridView 控件的交替行样式](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 [如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [如何：向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
