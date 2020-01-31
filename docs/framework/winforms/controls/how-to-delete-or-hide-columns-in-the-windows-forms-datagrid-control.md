---
title: 删除或隐藏 DataGrid 控件中的列
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
ms.openlocfilehash: c730be934e9b978bdaf09bc7e668b4318077fba5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743297"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件将替换功能并将其添加到 <xref:System.Windows.Forms.DataGrid> 控件;但是，如果您选择，则会保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容性和将来使用。 자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하세요.  
  
 您可以通过使用 <xref:System.Windows.Forms.GridColumnStylesCollection> 和 <xref:System.Windows.Forms.DataGridColumnStyle> 对象（这是 <xref:System.Windows.Forms.DataGridTableStyle> 类的成员）的属性和方法，以编程方式删除或隐藏 Windows 窗体 <xref:System.Windows.Forms.DataGrid> 控件中的列。  
  
 已删除或隐藏的列仍然存在于网格绑定到的数据源中，并且仍可通过编程方式进行访问。 它们只在 datagrid 中不可见。  
  
> [!NOTE]
> 如果您的应用程序不访问某些数据列，并且您不希望它们显示在数据网格中，则可能不需要先将它们包含在数据源中。  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>以编程方式从 DataGrid 中删除列  
  
1. 在窗体的声明区域中，声明 <xref:System.Windows.Forms.DataGridTableStyle> 类的新实例。  
  
2. 将 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> 属性设置为您要应用样式的数据源中的表。 下面的示例使用 <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> 属性，该属性假定已设置。  
  
3. 将新的 <xref:System.Windows.Forms.DataGridTableStyle> 对象添加到 datagrid 的表样式集合。  
  
4. 调用 <xref:System.Windows.Forms.DataGrid>的 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 集合的 <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> 方法，并指定要删除的列的列索引。  
  
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
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>以编程方式隐藏 DataGrid 中的列  
  
1. 在窗体的声明区域中，声明 <xref:System.Windows.Forms.DataGridTableStyle> 类的新实例。  
  
2. 将 <xref:System.Windows.Forms.DataGridTableStyle> 的 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 属性设置为您要应用样式的数据源中的表。 下面的代码示例使用 <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> 属性，该属性假定已设置。  
  
3. 将新的 <xref:System.Windows.Forms.DataGridTableStyle> 对象添加到 datagrid 的表样式集合。  
  
4. 通过将列的 `Width` 属性设置为0来隐藏该列，指定要隐藏的列的列索引。  
  
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
  
## <a name="see-also"></a>另请参阅

- [방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [방법: Windows Forms DataGrid 컨트롤에 테이블 및 열 추가](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
