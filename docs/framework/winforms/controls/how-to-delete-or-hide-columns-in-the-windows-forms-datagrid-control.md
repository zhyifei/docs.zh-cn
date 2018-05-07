---
title: 如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: 6541ffff1149e5df13c43ee392ffa8b221c8407d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 你可以以编程方式删除或隐藏 Windows 窗体中的列<xref:System.Windows.Forms.DataGrid>控件使用的属性和方法<xref:System.Windows.Forms.GridColumnStylesCollection>和<xref:System.Windows.Forms.DataGridColumnStyle>对象 (的成员<xref:System.Windows.Forms.DataGridTableStyle>类)。  
  
 在网格绑定到和仍可以通过编程方式访问数据源中仍存在已删除或隐藏列。 它们将只需不再在数据网格中可见。  
  
> [!NOTE]
>  如果你的应用程序不会访问数据，某些列，并且不希望它们显示在数据网格，然后它不可能需要首先将其包含在数据源中。  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>若要以编程方式从数据网格中删除列  
  
1.  在你的窗体声明区域中，声明的新实例<xref:System.Windows.Forms.DataGridTableStyle>类。  
  
2.  设置<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType>到您想要应用该样式的数据源中的表的属性。 下面的示例使用<xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>属性，假设已设置了它。  
  
3.  添加新<xref:System.Windows.Forms.DataGridTableStyle>到 datagrid 的表样式集合的对象。  
  
4.  调用<xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A>方法<xref:System.Windows.Forms.DataGrid>的<xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>集合，指定要删除的列的列索引。  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>若要以编程方式隐藏 DataGrid 中的列  
  
1.  在你的窗体声明区域中，声明的新实例<xref:System.Windows.Forms.DataGridTableStyle>类。  
  
2.  设置<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>属性<xref:System.Windows.Forms.DataGridTableStyle>到您想要应用该样式的数据源中的表。 下面的代码示例使用<xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>属性，假设已设置了它。  
  
3.  添加新<xref:System.Windows.Forms.DataGridTableStyle>到 datagrid 的表样式集合的对象。  
  
4.  通过设置隐藏列其`Width`属性设置为 0，并指定要隐藏的列的列索引。  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a>请参阅  
 [如何：在运行时更改 Windows 窗体 DataGrid 控件中显示的数据](../../../../docs/framework/winforms/controls/change-displayed-data-at-run-time-wf-datagrid-control.md)  
 [如何：向 Windows 窗体 DataGrid 控件添加表和列](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
