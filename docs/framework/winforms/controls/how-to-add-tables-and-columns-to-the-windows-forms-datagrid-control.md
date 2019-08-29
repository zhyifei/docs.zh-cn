---
title: 如何：向 Windows 窗体 DataGrid 控件添加表和列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: bfb0296566fecc2029df16d91c9c04d7daa4b4b5
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046157"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>如何：向 Windows 窗体 DataGrid 控件添加表和列

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。

可以通过创建**DataGridTableStyle**对象并将<xref:System.Windows.Forms.DataGrid>其添加到**system.windows.forms.gridtablestylescollection>** 对象<xref:System.Windows.Forms.DataGrid> , 在表和列的 Windows 窗体控件中显示数据, 并将这些对象添加到对象, 该对象可通过控件的**System.windows.forms.datagrid.tablestyles**属性。 每个表样式显示在**DataGridTableStyle**对象的**MappingName**属性中指定的任何数据表的内容。 默认情况下, 未指定列样式的表样式将显示该数据表中的所有列。 您可以通过将**system.windows.forms.datagridcolumnstyle>** 对象添加到**system.windows.forms.gridcolumnstylescollection>** 对象中来限制表中的哪些列的显示, 该对象可通过每个**DataGridTableStyle**的**system.windows.forms.datagridtablestyle.gridcolumnstyles**属性进行访问。对象.

### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>以编程方式向 DataGrid 添加表和列

1. 若要在表中显示数据, 必须先将<xref:System.Windows.Forms.DataGrid>控件绑定到数据集。 有关详细信息，请参阅[如何：将 Windows 窗体 DataGrid 控件绑定到数据源](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)。

    > [!CAUTION]
    > 以编程方式指定列样式时, 请始终创建**system.windows.forms.datagridcolumnstyle>** 对象并将其添加到**system.windows.forms.gridcolumnstylescollection>** 对象, 然后将**DataGridTableStyle**对象添加到**System.windows.forms.gridtablestylescollection>** 对象。 将空的**DataGridTableStyle**对象添加到集合时, 会自动为你生成**system.windows.forms.datagridcolumnstyle>** 对象。 因此, 如果尝试将具有重复**MappingName**值的新**system.windows.forms.datagridcolumnstyle>** 对象添加到**system.windows.forms.gridcolumnstylescollection>** 对象, 将引发异常。

2. 声明新的表样式并设置其映射名称。

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

3. 声明新的列样式, 并设置其映射名称和其他属性。

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

4. 调用**system.windows.forms.gridcolumnstylescollection>** 对象的**add**方法, 将该列添加到表样式中

    ```vb
    ts1.GridColumnStyles.Add(myDataCol)
    ```

    ```csharp
    ts1.GridColumnStyles.Add(myDataCol);
    ```

    ```cpp
    ts1->GridColumnStyles->Add(myDataCol);
    ```

5. 调用**system.windows.forms.gridtablestylescollection>** 对象的**add**方法, 将表样式添加到数据网格。

    ```vb
    DataGrid1.TableStyles.Add(ts1)
    ```

    ```csharp
    dataGrid1.TableStyles.Add(ts1);
    ```

    ```cpp
    dataGrid1->TableStyles->Add(ts1);
    ```

## <a name="see-also"></a>请参阅

- [DataGrid 控件](datagrid-control-windows-forms.md)
- [如何：删除或隐藏 Windows 窗体 DataGrid 控件中的列](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
