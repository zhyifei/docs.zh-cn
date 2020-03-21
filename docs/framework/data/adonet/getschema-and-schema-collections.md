---
title: GetSchema 和架构集合
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: e18c23e9bbec97a64110aba6eb7241761ecece06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149552"
---
# <a name="getschema-and-schema-collections"></a>GetSchema 和架构集合
每个 .NET 框架托管提供程序中的**Connect**类实现**GetSchema**方法，该方法用于检索有关当前连接的数据库的架构信息，并且从**GetSchema**方法返回的架构信息以 形式<xref:System.Data.DataTable>出现。 **GetSchema**方法是一种重载方法，它提供了用于指定要返回的架构集合和限制返回的信息量的可选参数。  
  
## <a name="specifying-the-schema-collections"></a>指定架构集合  
 **GetSchema**方法的第一个可选参数是指定为字符串的集合名称。 有两种类型的架构集合：所有提供程序通用的通用架构集合以及每个提供程序特定的特定架构集合。  
  
 您可以查询 .NET Framework 托管提供程序，通过调用没有参数的**GetSchema**方法或使用架构集合名称"MetaDataCollection"来确定支持的架构集合的列表。 此时将返回 <xref:System.Data.DataTable>，包含支持的架构集合列表、每个架构集合支持的限制数以及所使用的标识符部分数。  
  
### <a name="retrieving-schema-collections-example"></a>检索架构集合示例  
 以下示例演示如何使用 SQL Server<xref:System.Data.SqlClient.SqlConnection.GetSchema%2A><xref:System.Data.SqlClient.SqlConnection>类的 .NET 框架数据提供程序的方法检索有关**AdventureWorks**示例数据库中包含的所有表的架构信息：  
  
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

- [检索数据库架构信息](retrieving-database-schema-information.md)
- [ADO.NET 概述](ado-net-overview.md)
