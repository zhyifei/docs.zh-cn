---
title: 格式化数据网格控制
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
ms.openlocfilehash: 180f837c7d60f49af880faefc05da262be061d12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182136"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>如何：设置 Windows 窗体 DataGrid 控件的格式
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 将不同颜色应用于<xref:System.Windows.Forms.DataGrid>控件的各个部分有助于使其中的信息更易于阅读和解释。 颜色可以应用于行和列。 行和列也可以隐藏或显示由您自行决定。  
  
 设置<xref:System.Windows.Forms.DataGrid>控件的格式有三个基本方面。 您可以设置属性以建立显示数据的默认样式。 然后，您可以自定义运行时显示某些表的方式。 最后，您可以修改数据网格中显示的列以及显示的颜色和其他格式。  
  
 作为设置数据网格格式的第一步，可以设置<xref:System.Windows.Forms.DataGrid>自身的属性。 这些颜色和格式选项构成了一个基础，然后根据显示的数据表和列进行更改。  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>为 DataGrid 控件建立默认样式  
  
1. 根据需要设置以下属性：  
  
    |properties|说明|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|属性<xref:System.Windows.Forms.DataGrid.BackColor%2A>定义网格偶数行的颜色。 将<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>属性设置为其他颜色时，其他行将设置为此新颜色（行 1、3、5 等）。|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|网格偶数行的背景颜色（行 0、2、4、6 等）。|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|<xref:System.Windows.Forms.DataGrid.BackColor%2A>和<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>属性确定网格中的行颜色，<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>而属性确定非行区域的颜色，仅当网格滚动到底部时，或者如果网格中仅包含几行，则该区域可见。|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|网格的边框样式，枚举值之<xref:System.Windows.Forms.BorderStyle>一。|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|网格窗口标题的背景颜色，该颜色显示在网格的紧要上方。|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|网格顶部的标题字体。|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|网格窗口标题的背景颜色。|  
    |<xref:System.Windows.Forms.Control.Font%2A>|用于在网格中显示文本的字体。|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|数据网格行中显示的字体颜色。|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|数据网格的网格线的颜色。|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|分隔网格单元格的行的样式，即枚举值之<xref:System.Windows.Forms.DataGridLineStyle>一。|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|行标题和列标题的背景颜色。|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|用于列标题的字体。|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|网格的列标题的前景颜色，包括列标题文本和加/减字形（在显示多个相关表时展开行）。|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|数据网格中所有链接的文本颜色，包括指向子表的链接、关系名称等。|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|在子表中，这是父行的背景颜色。|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|在子表中，这是父行的前景颜色。|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|通过枚<xref:System.Windows.Forms.DataGridParentRowsLabelStyle>举确定表和列名称是否显示在父行中。|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|网格中列的默认宽度（以像素为单位）。 在重置<xref:System.Windows.Forms.DataGrid.DataSource%2A>和<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性之前设置此属性（单独或通过<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法），否则该属性将不起作用。<br /><br /> 属性不能设置为小于 0 的值。|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|网格中行的行高度（以像素为单位）。 在重置<xref:System.Windows.Forms.DataGrid.DataSource%2A>和<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性之前设置此属性（单独或通过<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法），否则该属性将不起作用。<br /><br /> 属性不能设置为小于 0 的值。|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|网格的行标题的宽度。|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|选择行或单元格时，这是背景颜色。|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|选择行或单元格时，这是前景颜色。|  
  
    > [!NOTE]
    > 请记住，在自定义控件的颜色时，由于颜色选择不佳（例如红色和绿色），因此可以使控件无法访问。 使用 **"系统颜色**"调色板上可用的颜色以避免此问题。  
  
     以下过程假定窗体具有绑定到数据<xref:System.Windows.Forms.DataGrid>表的控件。 有关详细信息，请参阅将[Windows 窗体数据网格控件绑定到数据源](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)。  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>以编程方式设置数据表的表和列样式  
  
1. 创建新的表样式并设置其属性。  
  
2. 创建列样式并设置其属性。  
  
3. 将列样式添加到表样式的列样式集合中。  
  
4. 将表样式添加到数据网格的表样式集合中。  
  
5. 在下面的示例中，创建 new<xref:System.Windows.Forms.DataGridTableStyle>的实例并设置其<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>属性。  
  
6. 创建**GridColumnStyle**的新实例并设置其**映射名称**（以及一些其他布局和显示属性）。  
  
7. 对于要创建的每个列样式，重复步骤 2 到 6。  
  
     下面的示例说明了如何创建<xref:System.Windows.Forms.DataGridTextBoxColumn>， 因为名称将在列中显示。 此外，您将列样式添加到<xref:System.Windows.Forms.GridColumnStylesCollection>表样式，并将表样式添加到数据网格的。 <xref:System.Windows.Forms.GridTableStylesCollection>  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid 控件](datagrid-control-windows-forms.md)
