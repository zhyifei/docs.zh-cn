---
title: 加载方法
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: f1c819333225c22efb85946001a1fc8340d57989
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150722"
---
# <a name="the-load-method"></a>加载方法
可以使用 <xref:System.Data.DataTable.Load%2A> 方法为 <xref:System.Data.DataTable> 加载数据源中行。 这是一个重载方法，其最简单的形式是接受单个参数 **，即 DataReader**。 在此窗体中，它只需使用行加载**DataTable**即可。 或者，您可以指定**LoadOption**参数来控制将数据添加到**DataTable**中的方式。  
  
 **LoadOption**参数在**DataTable**已包含数据行的情况下特别有用，因为它描述了数据源的传入数据如何与表中已有的数据组合。 例如，**保留当前值**（默认值）指定在**数据表中**将行标记为 **"已添加**"的情况下，**原始**值或每列将设置为数据源中匹配行的内容。 "**当前**"值将保留添加行时分配的值，行的**RowState**将设置为 **"已更改**"。  
  
 下表给出了对 <xref:System.Data.LoadOption> 枚举值的简要说明。  
  
|LoadOption 值|说明|  
|----------------------|-----------------|  
|**OverwriteRow**|如果传入行具有与**DataTable**中已有的行相同的**主键**值，则每列**的原始**值和**当前**值将替换为传入行中的值，并且**RowState**属性设置为 **"未更改**"。<br /><br /> **数据表中**不存在的数据源中的行添加的**RowState**值**为"未更改**"。<br /><br /> 此选项实际上刷新**了 DataTable**的内容，以便它与数据源的内容匹配。|  
|**PreserveCurrentValues（默认值）**|如果传入行具有与**DataTable**中已有的行相同的**主键**值，则**原始**值将设置为传入行的内容，并且不会更改 **"当前"** 值。<br /><br /> 如果 **"行状态**已**添加**或**修改**"，则将其设置为 **"已修改**"。<br /><br /> 如果**RowState** **已删除**，则保留**为 "已删除**"。<br /><br /> 将添加**DataTable**中不存在的数据源中的行，并将**RowState**设置为 **"未更改**"。|  
|**UpdateCurrentValues**|如果传入行具有与**DataTable**中已有的行相同的**主键**值，则**当前**值将复制到**原始**值，然后将 **"当前**"值设置为传入行的内容。<br /><br /> 如果**已添加** **DataTable**中的**行状态**，则 **"行状态**"将保持**已添加**。 对于标记为 **"已修改**或删除"**的**行，将**修改****"行状态**"。<br /><br /> 将添加**DataTable**中不存在的数据源中的行，并将**RowState**设置为 **"已添加**"。|  
  
 以下示例使用**Load**方法显示**Northwind**数据库中员工的生日列表。  
  
```vb  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## <a name="see-also"></a>另请参阅

- [操作数据表中的数据](manipulating-data-in-a-datatable.md)
- [ADO.NET 概述](../ado-net-overview.md)
