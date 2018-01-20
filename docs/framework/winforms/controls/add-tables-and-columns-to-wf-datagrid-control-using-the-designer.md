---
title: "如何：使用设计器向 Windows 窗体 DataGrid 控件添加表和列"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ccc310303c7edb968b43f4d529782979024e8e73
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>如何：使用设计器向 Windows 窗体 DataGrid 控件添加表和列
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 你可以在 Windows 窗体中显示数据<xref:System.Windows.Forms.DataGrid>中表和列通过创建控件<xref:System.Windows.Forms.DataGridTableStyle>对象并将它们添加到<xref:System.Windows.Forms.GridTableStylesCollection>对象，可通过<xref:System.Windows.Forms.DataGrid>控件的<xref:System.Windows.Forms.DataGrid.TableStyles%2A>属性。 每个表样式显示任何数据表中指定的内容<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>属性<xref:System.Windows.Forms.DataGridTableStyle>。 默认情况下，但未列样式指定了表样式将显示该数据表中的所有列。 你可以限制表中的哪些列显示通过添加<xref:System.Windows.Forms.DataGridColumnStyle>对象添加到<xref:System.Windows.Forms.GridColumnStylesCollection>，通过访问的哪一<xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>每个属性<xref:System.Windows.Forms.DataGridTableStyle>。  
  
 下面的过程要求**Windows 应用程序**具有一个包含窗体项目<xref:System.Windows.Forms.DataGrid>控件。 有关如何设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。 在默认情况下[!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]、<xref:System.Windows.Forms.DataGrid>控件将不处于**工具箱**。 有关将其添加的信息，请参阅[如何： 将项添加到工具箱](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>若要将表添加到设计器中的 DataGrid 控件  
  
1.  为了在表中显示数据，必须首先将绑定<xref:System.Windows.Forms.DataGrid>控件添加到数据集。 有关详细信息，请参阅[如何： 将 Windows 窗体 DataGrid 控件绑定到数据源使用的设计器](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)。  
  
2.  选择<xref:System.Windows.Forms.DataGrid>控件的<xref:System.Windows.Forms.DataGrid.TableStyles%2A>属性在属性窗口中，然后单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边要显示的属性**DataGridTableStyle 集合编辑器**。  
  
3.  在集合编辑器中，单击**添加**以插入表样式。  
  
4.  单击**确定**以关闭集合编辑器，然后重新打开它的旁边单击省略号按钮<xref:System.Windows.Forms.DataGrid.TableStyles%2A>属性。  
  
     当重新打开集合编辑器时，所有绑定到控件的数据表将显示的下拉列表中<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>属性表样式。  
  
5.  在**成员**框集合编辑器中，单击表样式。  
  
6.  在**属性**框的集合编辑器中，选择<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>要显示的表的值。  
  
### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>若要将列添加到设计器中的 DataGrid 控件  
  
1.  在**成员**框**DataGridTableStyle 集合编辑器**，选择适当的表样式。 在**属性**框的集合编辑器中，选择<xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>集合，然后单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 以显示在属性旁边**DataGridColumnStyle 集合编辑器**。  
  
2.  在集合编辑器中，单击**添加**插入列样式，或单击向下箭头旁边**添加**指定列类型。  
  
     在下拉列表框中，可以选择<xref:System.Windows.Forms.DataGridTextBoxColumn>或<xref:System.Windows.Forms.DataGridBoolColumn>类型。  
  
3.  单击确定以关闭**DataGridColumnStyle 集合编辑器**，然后重新打开它的旁边单击省略号按钮<xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>属性。  
  
     当重新打开集合编辑器时，绑定的数据表中的任何数据列将显示的下拉列表中<xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A>列样式的属性。  
  
4.  在**成员**框集合编辑器中，单击列样式。  
  
5.  在**属性**框的集合编辑器中，选择<xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A>想要显示的列的值。  
  
## <a name="see-also"></a>请参阅  
 [DataGrid 控件](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
