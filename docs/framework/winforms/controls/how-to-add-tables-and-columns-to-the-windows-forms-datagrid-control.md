---
title: "如何：向 Windows 窗体 DataGrid 控件添加表和列"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 970c2787bda50bcf0478b64df44176525f839482
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>如何：向 Windows 窗体 DataGrid 控件添加表和列
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 你可以在 Windows 窗体中显示数据<xref:System.Windows.Forms.DataGrid>中表和列通过创建控件**DataGridTableStyle**对象并将它们添加到**GridTableStylesCollection**对象，它是通过访问<xref:System.Windows.Forms.DataGrid>控件的**TableStyles**属性。 每个表样式显示任何数据表中指定的内容**DataGridTableStyle**对象的**MappingName**属性。 默认情况下，具有未指定的列样式的表样式将显示该数据表中的所有列。 你可以限制表中的哪些列显示通过添加**DataGridColumnStyle**对象添加到**GridColumnStylesCollection**对象，可通过**GridColumnStyles**每个属性**DataGridTableStyle**对象。  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>以编程方式将表和列添加到数据网格  
  
1.  为了在表中显示数据，必须首先将绑定<xref:System.Windows.Forms.DataGrid>控件添加到数据集。 有关详细信息，请参阅[如何： 将 Windows 窗体 DataGrid 控件绑定到数据源](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)。  
  
    > [!CAUTION]
    >  以编程方式指定列样式，将始终创建**DataGridColumnStyle**对象，并将其添加到**GridColumnStylesCollection**之前添加的对象**DataGridTableStyle**对象添加到**GridTableStylesCollection**对象。 当你将添加一个空**DataGridTableStyle**对象添加到收藏， **DataGridColumnStyle**自动为你生成的对象。 如果你尝试添加新因此，将引发异常**DataGridColumnStyle**对象具有重复**MappingName**值复制到**GridColumnStylesCollection**对象。  
  
2.  声明一个新的表样式并设置其映射名称。  
  
    ```vb  
    Dim ts1 As New DataGridTableStyle()  
    ts1.MappingName = "Customers"  
    ```  
  
    ```csharp  
    DataGridTableStyle ts1 = new DataGridTableStyle();  
    ts1.MappingName = "Customers";  
    ```  
  
    ```cpp  
    DataGridTableStyle* ts1 = new DataGridTableStyle();  
    ts1->MappingName = S"Customers";  
    ```  
  
3.  声明一个新列样式并设置其映射名称和其他属性。  
  
    ```vb  
    Dim myDataCol As New DataGridBoolColumn()  
    myDataCol.HeaderText = "My New Column"  
    myDataCol.MappingName = "Current"  
    ```  
  
    ```csharp  
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();  
    myDataCol.HeaderText = "My New Column";  
    myDataCol.MappingName = "Current";  
    ```  
  
    ```cpp  
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();  
    myDataCol->HeaderText = "My New Column";  
    myDataCol->MappingName = "Current";  
    ```  
  
4.  调用**添加**方法**GridColumnStylesCollection**对象向表样式添加列  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  调用**添加**方法**GridTableStylesCollection**对象以将表样式添加到数据网格。  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [DataGrid 控件](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
