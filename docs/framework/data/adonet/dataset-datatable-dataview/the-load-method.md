---
title: "加载方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e6c6ce0b722d901e38b728a710e3c49848fb918a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="the-load-method"></a>加载方法
可以使用 <xref:System.Data.DataTable.Load%2A> 方法为 <xref:System.Data.DataTable> 加载数据源中行。 这是重载的方法，其最简单的形式，接受一个参数， **DataReader**。 在这种形式，它只需加载**DataTable**行。 或者，可以指定**LoadOption**参数，用于控制如何将数据添加到**DataTable**。  
  
 **LoadOption**参数会在情况下特别有用其中**DataTable**已包含的数据行，因为它说明了如何传入数据从数据源都将合并的数据已在表中。 例如， **PreserveCurrentValues** （默认） 指定在其中将行标记为的情况下**Added**中**DataTable**、**原始**值或每个列设置为匹配的行的内容从数据源。 **当前**值将保留时添加行，，分配的值与**RowState**的行都将它设置为**Changed**。  
  
 下表给出了对 <xref:System.Data.LoadOption> 枚举值的简要说明。  
  
|LoadOption 值|描述|  
|----------------------|-----------------|  
|**OverwriteRow**|如果传入行具有相同**PrimaryKey**为已在一行的值**DataTable**、**原始**和**当前**每个值列替换由传入行中的值与**RowState**属性设置为**Unchanged**。<br /><br /> 从数据源中不存在的行**DataTable**添加与**RowState**值**Unchanged**。<br /><br /> 此选项的作用是刷新的内容**DataTable** ，使其匹配数据源的内容。|  
|**PreserveCurrentValues （默认值）**|如果传入行具有相同**PrimaryKey**为已在一行的值**DataTable**、**原始**值设置为传入行中和的内容**当前**值不会更改。<br /><br /> 如果**RowState**是**Added**或**已修改**，设置为**已修改**。<br /><br /> 如果**RowState**已**已删除**，它就会一直**已删除**。<br /><br /> 从数据源中不存在的行**DataTable**添加，和**RowState**设置为**Unchanged**。|  
|**UpdateCurrentValues**|如果传入行具有相同**PrimaryKey**为已在一行的值**DataTable**、**当前**值复制到**原始**值，与**当前**然后，将值设置为传入行的内容。<br /><br /> 如果**RowState**中**DataTable**已**Added**、 **RowState**保持**Added**。 为行标记为**已修改**或**已删除**、 **RowState**是**已修改**。<br /><br /> 从数据源中不存在的行**DataTable**添加，和**RowState**设置为**Added**。|  
  
 下面的示例使用**负载**方法以显示中的员工的生日列表**Northwind**数据库。  
  
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
  
## <a name="see-also"></a>请参阅  
 [操作数据表中的数据](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
