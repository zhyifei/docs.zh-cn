---
title: 如何：使用设计器向 Windows 窗体 DataGrid 控件添加表和列
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: b2e8f962ed7fb9d205a9061bdc1b32c3a2f8b0bd
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873409"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>如何：使用设计器向 Windows 窗体 DataGrid 控件添加表和列

> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 可以在 Windows 窗体中显示数据<xref:System.Windows.Forms.DataGrid>控件中的表和列创建<xref:System.Windows.Forms.DataGridTableStyle>对象并将它们添加到<xref:System.Windows.Forms.GridTableStylesCollection>对象，通过访问<xref:System.Windows.Forms.DataGrid>控件的<xref:System.Windows.Forms.DataGrid.TableStyles%2A>属性。 每个表样式显示任何数据的表中指定的内容<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>属性的<xref:System.Windows.Forms.DataGridTableStyle>。 默认情况下，未指定列样式的表样式将显示该数据表中的所有列。 你可以限制在表中的哪些列显示通过添加<xref:System.Windows.Forms.DataGridColumnStyle>对象添加到<xref:System.Windows.Forms.GridColumnStylesCollection>，这通过访问<xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>每个属性<xref:System.Windows.Forms.DataGridTableStyle>。  
  
 下面的过程要求**Windows 应用程序**包含一个窗体项目<xref:System.Windows.Forms.DataGrid>控件。 有关如何设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)并[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。 在 Visual Studio 2005 中，默认情况下<xref:System.Windows.Forms.DataGrid>控件不在**工具箱**。 考虑将其添加信息，请参阅[如何： 将项添加到工具箱](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>若要将表添加到设计器中的 DataGrid 控件  
  
1.  若要在表中显示数据，您必须首先绑定<xref:System.Windows.Forms.DataGrid>控件向数据集。 有关详细信息，请参阅[如何： 将 Windows 窗体 DataGrid 控件绑定到数据源使用的设计器](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)。  
  
2.  选择<xref:System.Windows.Forms.DataGrid>控件的<xref:System.Windows.Forms.DataGrid.TableStyles%2A>属性窗口中的属性，然后单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边要显示的属性**DataGridTableStyle 集合编辑器**。  
  
3.  在集合编辑器中单击**添加**插入表样式。  
  
4.  单击**确定**以关闭集合编辑器，然后重新打开它的旁边单击省略号按钮<xref:System.Windows.Forms.DataGrid.TableStyles%2A>属性。  
  
     当你重新打开集合编辑器中时，绑定到控件的任何数据表将显示的下拉列表中<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>表样式的属性。  
  
5.  在中**成员**框的集合编辑器中，单击表样式。  
  
6.  在中**属性**框中的集合编辑器中，选择<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>想要显示的表的值。  
  
### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>若要将列添加到设计器中的 DataGrid 控件  
  
1.  在中**成员**的框**DataGridTableStyle 集合编辑器**，选择适当的表样式。 在中**属性**框中的集合编辑器中，选择<xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>集合，然后单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 以显示在属性旁边**DataGridColumnStyle 集合编辑器**。  
  
2.  在集合编辑器中单击**外**插入列样式，或单击向下箭头旁边**添加**指定列类型。  
  
     在下拉列表框中，可以选择<xref:System.Windows.Forms.DataGridTextBoxColumn>或<xref:System.Windows.Forms.DataGridBoolColumn>类型。  
  
3.  单击确定以关闭**DataGridColumnStyle 集合编辑器**，然后重新打开它的旁边单击省略号按钮<xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>属性。  
  
     当你重新打开集合编辑器中时，绑定的数据的表中的任何数据列将显示的下拉列表中<xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A>列样式的属性。  
  
4.  在中**成员**框的集合编辑器中，单击列样式。  
  
5.  在中**属性**框中的集合编辑器中，选择<xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A>你想要显示的列的值。  
  
## <a name="see-also"></a>请参阅  
 [DataGrid 控件](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
