---
title: "GetSchema 和架构集合"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4790195d5f02ac1f68f8ab4c5ef39499052cd725
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="getschema-and-schema-collections"></a>GetSchema 和架构集合
**连接**中每个.NET Framework 托管提供程序实现的类**GetSchema**方法用于检索有关与当前连接的数据库的架构信息和从返回的架构信息**GetSchema**方法采用的形式<xref:System.Data.DataTable>。 **GetSchema**方法属于重载的方法，提供可选参数来指定要返回的架构集合以及限制返回的信息量。  
  
## <a name="specifying-the-schema-collections"></a>指定架构集合  
 第一个可选参数**GetSchema**方法是指定为一个字符串的集合名称。 有两种类型的架构集合：所有提供程序通用的通用架构集合以及每个提供程序特定的特定架构集合。  
  
 您可以查询由.NET Framework 托管提供程序以确定支持的架构集合列表，通过调用**GetSchema**不带任何参数，或包含架构集合名称"MetaDataCollections"的方法。 此时将返回 <xref:System.Data.DataTable>，包含支持的架构集合列表、每个架构集合支持的限制数以及所使用的标识符部分数。  
  
### <a name="retrieving-schema-collections-example"></a>检索架构集合示例  
 下面的示例演示如何使用<xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>SQL Server 的.NET Framework 数据提供程序方法<xref:System.Data.SqlClient.SqlConnection>类检索有关的所有表中包含的架构信息**AdventureWorks**示例数据库：  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
   Sub Main()  
      Dim connectionString As String = GetConnectionString()  
      Using connection As New SqlConnection(connectionString)  
         'Connect to the database then retrieve the schema information.  
         connection.Open()  
         Dim table As DataTable = connection.GetSchema("Tables")  
  
         ' Display the contents of the table.  
         DisplayData(table)  
         Console.WriteLine("Press any key to continue.")  
         Console.ReadKey()  
      End Using  
   End Sub  
  
   Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,    
      ' you can retrieve it from a configuration file.  
      Return "Data Source=(local);Database=AdventureWorks;" _  
         & "Integrated Security=true;"  
   End Function  
  
   Private Sub DisplayData(ByVal table As DataTable)  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
   End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
  string connectionString = GetConnectionString();  
  using (SqlConnection connection = new SqlConnection(connectionString))  
  {  
   // Connect to the database then retrieve the schema information.  
   connection.Open();  
   DataTable table = connection.GetSchema("Tables");  
  
   // Display the contents of the table.  
   DisplayData(table);  
   Console.WriteLine("Press any key to continue.");  
   Console.ReadKey();  
   }  
 }  
  
  private static string GetConnectionString()  
  {  
   // To avoid storing the connection string in your code,  
   // you can retrieve it from a configuration file.  
   return "Data Source=(local);Database=AdventureWorks;" +  
      "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [检索数据库架构信息](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
