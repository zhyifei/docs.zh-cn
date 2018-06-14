---
title: 如何：设置 Windows 窗体 DataGrid 控件的格式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: ffcb84059dfceb85cdb347c3ddf1b80ab96c2aac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540444"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>如何：设置 Windows 窗体 DataGrid 控件的格式
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 将不同的颜色应用于各个部分的<xref:System.Windows.Forms.DataGrid>控件可以帮助将在其中的信息以易于读取和解释。 颜色可以应用于行和列。 行和列可以还显示或隐藏根据你的判断。  
  
 有三个基本方面的格式设置<xref:System.Windows.Forms.DataGrid>控件。 你可以设置属性以建立数据显示为默认样式。 以此为基础，你可以然后自定义在运行时显示某些表的方式。 最后，您可以修改哪些列显示在数据网格以及颜色和其他格式显示。  
  
 在格式设置数据网格中执行初始步骤，你可以设置的属性<xref:System.Windows.Forms.DataGrid>本身。 这些颜色和格式选项的窗体的基从中然后可以根据的数据表和显示的列的更改。  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>若要建立的 DataGrid 控件的默认样式  
  
1.  根据需要设置以下属性：  
  
    |属性|描述|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<xref:System.Windows.Forms.DataGrid.BackColor%2A>属性定义的网格中偶数行的颜色。 当你将设置<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>为不同的颜色的属性，所有其他行设置为此新的颜色 （行 1、 3、 5 和等等）。|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|网格中偶数行的背景色 （行 0、 2、 4、 6 和等等）。|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|而<xref:System.Windows.Forms.DataGrid.BackColor%2A>和<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>属性确定在网格中，行的颜色<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>属性确定中行区域，该网格滚动到底部，或只在包含少量的行时才可见区域的颜色网格。|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|网格的边框样式，之一<xref:System.Windows.Forms.BorderStyle>枚举值。|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|正上方网格的网格窗口标题的背景色。|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|在顶部网格标题的字体。|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|网格的窗口标题的背景色。|  
    |<xref:System.Windows.Forms.Control.Font%2A>|用于在网格中显示文本的字体。|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|数据网格行中的数据显示字体的颜色。|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|数据网格的网格线的颜色。|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|网格，其中一个单元格进行分隔线的样式<xref:System.Windows.Forms.DataGridLineStyle>枚举值。|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|行和列标题的背景色。|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|用于列标题的字体。|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|网格的列标题，包括列标题文本和加/减标志符号，（若要显示多个相关的表时，请展开行） 的前景色。|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|在数据网格中，包括指向子表、 关系名称和等等的所有链接的文本的颜色。|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|在子表中，这是父行的背景色。|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|在子表中，这是父行的前景色。|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|确定是否表和列名称显示在父行中，通过<xref:System.Windows.Forms.DataGridParentRowsLabelStyle>枚举。|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|网格中列的默认宽度（以像素为单位）。 重置之前设置此属性<xref:System.Windows.Forms.DataGrid.DataSource%2A>和<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性 (或者单独，或通过<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法)，或者该属性将产生任何效果。<br /><br /> 属性不能设置为小于 0 的值。|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|行的高度 （以像素为单位） 的网格中的行。 重置之前设置此属性<xref:System.Windows.Forms.DataGrid.DataSource%2A>和<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性 (或者单独，或通过<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法)，或者该属性将产生任何效果。<br /><br /> 属性不能设置为小于 0 的值。|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|网格的行标题的宽度。|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|选择行或单元格时，这是背景色。|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|选择行或单元格时，这是的前景色。|  
  
    > [!NOTE]
    >  请记住，当自定义控件，就可以使控件无法访问，由于较差的颜色选择 （例如，红色和绿色） 的颜色。 使用提供的颜色**系统颜色**调色板，若要避免此问题。  
  
     以下过程假定你的窗体具有<xref:System.Windows.Forms.DataGrid>控件绑定到数据表。 有关详细信息，请参阅[将 Windows 窗体 DataGrid 控件绑定到数据源](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)。  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>以编程方式设置数据表的表和列样式  
  
1.  创建一个新的表样式并设置其属性。  
  
2.  创建列样式并设置其属性。  
  
3.  向表样式列样式集合添加列样式。  
  
4.  将表样式添加到数据网格表样式集合。  
  
5.  在下面的示例中，创建新的实例<xref:System.Windows.Forms.DataGridTableStyle>并设置其<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>属性。  
  
6.  创建的新实例**GridColumnStyle**并设置其**MappingName** （和一些其他布局和显示属性）。  
  
7.  重复步骤 2 到 6 个你想要创建每个列样式。  
  
     下面的示例演示如何<xref:System.Windows.Forms.DataGridTextBoxColumn>创建，因为名称列中显示。 此外，你将添加到列样式<xref:System.Windows.Forms.GridColumnStylesCollection>的表样式，并添加到的表样式<xref:System.Windows.Forms.GridTableStylesCollection>的数据网格。  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName   
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName   
       ' to the name of a DataColumn in the DataTable.   
       ' Set the HeaderText and Width properties.   
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to   
       ' the GridTableStylesCollection.   
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName   
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName   
       // to the name of a DataColumn in the DataTable.   
       // Set the HeaderText and Width properties.   
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to   
       // the GridTableStylesCollection.   
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName   
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName   
          // to the name of a DataColumn in the DataTable.   
          // Set the HeaderText and Width properties.   
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to   
          // the GridTableStylesCollection.   
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.GridTableStylesCollection>  
 <xref:System.Windows.Forms.GridColumnStylesCollection>  
 <xref:System.Windows.Forms.DataGrid>  
 [如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [DataGrid 控件](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
