---
title: 设置 DataGrid 控件的格式
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
ms.openlocfilehash: 30342a89f3176255fa7217ccbbbd91c166ff7f35
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732959"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>방법: Windows Forms DataGrid 컨트롤 서식 지정
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件将替换功能并将其添加到 <xref:System.Windows.Forms.DataGrid> 控件;但是，如果您选择，则会保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容性和将来使用。 자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하세요.  
  
 将不同的颜色应用到 <xref:System.Windows.Forms.DataGrid> 控件的各个部分，有助于更轻松地读取和解释信息。 颜色可以应用于行和列。 还可以根据自己的意愿隐藏或显示行和列。  
  
 <xref:System.Windows.Forms.DataGrid> 控件的格式设置有三个基本方面。 可以设置属性来建立显示数据的默认样式。 然后，你可以在运行时自定义某些表的显示方式。 最后，您可以修改在数据网格中显示的列，以及所显示的颜色和其他格式设置。  
  
 作为对数据网格进行格式设置的第一步，可以设置 <xref:System.Windows.Forms.DataGrid> 本身的属性。 这些颜色和格式选项构成一个基础，您可以根据所显示的数据表和列进行更改。  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>为 DataGrid 控件建立默认样式  
  
1. 根据需要设置以下属性：  
  
    |속성|설명|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<xref:System.Windows.Forms.DataGrid.BackColor%2A> 属性定义网格中偶数行的颜色。 将 <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> 属性设置为其他颜色时，会将每个其他行设置为此新颜色（第1行、第3、第5行等）。|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|网格中偶数行的背景色（行0、2、4、6，等等）。|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|"<xref:System.Windows.Forms.DataGrid.BackColor%2A>" 和 "<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>" 属性确定网格中的行颜色，而 "<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>" 属性确定 nonrow 区域的颜色，该区域仅在网格滚动到底部时可见，或在网格中只包含几行时可见。|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|网格的边框样式，<xref:System.Windows.Forms.BorderStyle> 枚举值之一。|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|网格窗口标题紧上方显示的背景色。|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|网格顶部的标题的字体。|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|网格窗口标题的背景色。|  
    |<xref:System.Windows.Forms.Control.Font%2A>|用于在网格中显示文本的字体。|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|数据网格的行中的数据所显示的字体颜色。|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|数据网格网格线的颜色。|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|分隔网格中的单元格的线条样式，是 <xref:System.Windows.Forms.DataGridLineStyle> 枚举值之一。|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|行标题和列标题的背景色。|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|列标题所用的字体。|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|网格的列标题的前景色，包括列标题文本和加/减标志符号（在显示多个相关表时展开行）。|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|数据网格中所有链接的文本颜色，包括指向子表的链接、关系名称，等等。|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|在子表中，这是父行的背景色。|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|在子表中，这是父行的前景色。|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|通过 <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> 枚举确定是否在父行中显示表和列的名称。|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|网格中列的默认宽度（以像素为单位）。 在重置 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 和 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 属性（单独或通过 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 方法）之前设置此属性，否则属性将不起作用。<br /><br /> 不能将属性设置为小于0的值。|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|网格中的行的高度（以像素为单位）。 在重置 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 和 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 属性（单独或通过 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 方法）之前设置此属性，否则属性将不起作用。<br /><br /> 不能将属性设置为小于0的值。|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|网格行标题的宽度。|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|选择行或单元格时，这是背景色。|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|选择行或单元格时，这是前景色。|  
  
    > [!NOTE]
    > 请记住，在自定义控件的颜色时，可能会由于颜色选择（例如红色和绿色）而使控件不可访问。 使用 "**系统颜色**" 调色板中的可用颜色来避免此问题。  
  
     下面的过程假设窗体具有一个绑定到数据表的 <xref:System.Windows.Forms.DataGrid> 控件。 有关详细信息，请参阅将[Windows 窗体 DataGrid 控件绑定到数据源](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)。  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>以编程方式设置数据表的表和列样式  
  
1. 创建新的表样式并设置其属性。  
  
2. 创建列样式并设置其属性。  
  
3. 将列样式添加到表样式的列样式集合。  
  
4. 将表样式添加到数据网格的表样式集合。  
  
5. 在下面的示例中，创建一个新 <xref:System.Windows.Forms.DataGridTableStyle> 的实例并设置其 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 属性。  
  
6. 创建**GridColumnStyle**的新实例并设置其**MappingName** （以及其他一些布局和显示属性）。  
  
7. 对于要创建的每个列样式，重复步骤2到6。  
  
     下面的示例演示如何创建 <xref:System.Windows.Forms.DataGridTextBoxColumn>，因为将在列中显示一个名称。 此外，您还可以将该列样式添加到表样式的 <xref:System.Windows.Forms.GridColumnStylesCollection> 中，并将该表样式添加到数据网格的 <xref:System.Windows.Forms.GridTableStylesCollection> 中。  
  
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
- [방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid 컨트롤](datagrid-control-windows-forms.md)
