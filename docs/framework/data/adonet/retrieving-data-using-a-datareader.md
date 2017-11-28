---
title: "使用 DataReader 检索 ADO 数据"
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
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0b66ca2fbcc760598b771b4c02a46acc3c9c1d4e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-data-using-a-datareader"></a>使用 DataReader 检索 ADO 数据
检索数据使用**DataReader**涉及到创建的实例**命令**对象，然后创建**DataReader**通过调用**Command.ExecuteReader**从数据源中检索行。 下面的示例演示如何使用**DataReader**其中`reader`表示有效的 DataReader 和`command`表示有效的命令对象。  
  
```  
reader = command.ExecuteReader();  
```  
  
 你使用**读取**方法**DataReader**对象从查询结果中获取行。 你可以通过传递的名称或序号引用的列访问返回的行的每一列**DataReader**。 但是，为了获得最佳性能， **DataReader**提供使你能够访问其本机数据类型中的列值的方法的一系列 (**GetDateTime**， **GetDouble**， **GetGuid**， **GetInt32**，依次类推)。 有关的数据提供程序特定的类型化访问器方法列表**DataReaders**，请参阅<xref:System.Data.OleDb.OleDbDataReader>和<xref:System.Data.SqlClient.SqlDataReader>。 假定基础数据类型为已知，如果使用类型化访问器方法，将减少在检索列值时所需的类型转换量。  
  
> [!NOTE]
>  Windows Server 2003 版本的.NET Framework 包括的其他属性**DataReader**， **HasRows**，这使您能够确定如果**DataReader**已从其返回之前读取任何结果。  
  
 下面的代码示例循环访问**DataReader**对象，并从每个行中的返回两个列。  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 **DataReader**提供未缓冲的数据流，使过程逻辑可以有效地按顺序处理数据源的结果。 **DataReader**是一个不错的选择，因为数据不在内存中缓存中检索大量数据时。  
  
## <a name="closing-the-datareader"></a>关闭 DataReader  
 始终应调用**关闭**方法时使用完**DataReader**对象。  
  
 如果你**命令**包含输出参数或返回值，它们将不可用之前**DataReader**已关闭。  
  
 请注意，当**DataReader**处于打开状态，**连接**正在独占方式使用**DataReader**。 无法执行任何命令**连接**，包括创建另一个**DataReader**，直到原始**DataReader**已关闭。  
  
> [!NOTE]
>  不要调用**关闭**或**释放**上**连接**、 **DataReader**，或在任何其他托管的对象**Finalize**你类的方法。 在终结器中，仅释放类直接拥有的非托管资源。 如果你的类不拥有任何非托管的资源，不包括**Finalize**在类定义的方法。 有关详细信息，请参阅[垃圾回收](../../../../docs/standard/garbage-collection/index.md)。  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>使用 NextResult 检索多个结果集  
 如果返回了多个结果集， **DataReader**提供**NextResult**方法来循环访问结果以设置顺序。 以下示例显示 <xref:System.Data.SqlClient.SqlDataReader> 如何使用 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 方法处理两个 SELECT 语句的结果。  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>从 DataReader 中获取架构信息  
 虽然**DataReader**是打开，你可以检索有关当前结果集使用的架构信息**GetSchemaTable**方法。 **GetSchemaTable**返回<xref:System.Data.DataTable>具有行和列包含当前结果集的架构信息填充的对象。 **DataTable**结果集的每一列中对应一行。 架构表行的每一列都映射到属性中返回的列的结果集，其中**ColumnName**是属性的名称和列的值是属性的值。 下面的代码示例将写出的架构信息**DataReader**。  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>使用 OLE DB 章节  
 分层行集或章节 (OLE DB 类型**DBTYPE_HCHAPTER**，ADO 类型**adChapter**) 可以使用检索<xref:System.Data.OleDb.OleDbDataReader>。 当为返回包含某章节的查询时**DataReader**，作为中列的返回章**DataReader**和公开为**DataReader**对象。  
  
 ADO.NET**数据集**还用于表示分层行集使用父-子表之间的关系。 有关详细信息，请参阅[数据集、 数据表和数据视图](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)。  
  
 以下代码示例使用 MSDataShape 提供程序来为客户列表中的每个客户生成订单的章节列。  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")  
  
Dim custCMD As OleDbCommand = New OleDbCommand( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
connection.Open()  
  
Dim custReader As OleDbDataReader = custCMD.ExecuteReader()  
Dim orderReader As OleDbDataReader  
  
Do While custReader.Read()  
  Console.WriteLine("Orders for " & custReader.GetString(1))   
  ' custReader.GetString(1) = CompanyName  
  
  orderReader = custReader.GetValue(2)  
  ' custReader.GetValue(2) = Orders chapter as DataReader  
  
  Do While orderReader.Read()  
    Console.WriteLine(vbTab & orderReader.GetInt32(1))  
    ' orderReader.GetInt32(1) = OrderID  
  Loop  
  orderReader.Close()  
Loop  
' Make sure to always close readers and connections.  
custReader.Close()  
End Using  
```  
  
```csharp  
Using (OleDbConnection connection = new OleDbConnection(  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"));  
{  
OleDbCommand custCMD = new OleDbCommand(  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
connection.Open();  
  
OleDbDataReader custReader = custCMD.ExecuteReader();  
OleDbDataReader orderReader;  
  
while (custReader.Read())  
{  
  Console.WriteLine("Orders for " + custReader.GetString(1));   
  // custReader.GetString(1) = CompanyName  
  
  orderReader = (OleDbDataReader)custReader.GetValue(2);        
  // custReader.GetValue(2) = Orders chapter as DataReader  
  
  while (orderReader.Read())  
    Console.WriteLine("\t" + orderReader.GetInt32(1));          
    // orderReader.GetInt32(1) = OrderID  
  orderReader.Close();  
}  
// Make sure to always close readers and connections.  
custReader.Close();  
}  
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a>使用 Oracle REF CURSOR 返回结果  
 Oracle .NET Framework 数据提供程序支持使用 Oracle REF CURSOR 返回查询结果。 Oracle REF CURSOR 以 <xref:System.Data.OracleClient.OracleDataReader> 的形式返回。  
  
 你可以检索**OracleDataReader**对象，表示使用 Oracle REF CURSOR<xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>方法，并且你还可以指定<xref:System.Data.OracleClient.OracleCommand>返回一个或多个 Oracle REF Cursor 作为**SelectCommand**为<xref:System.Data.OracleClient.OracleDataAdapter>用来填充<xref:System.Data.DataSet>。  
  
 若要访问从 Oracle 数据源返回的 REF CURSOR，创建**OracleCommand**查询并添加引用到 REF CURSOR 的输出参数**参数**你的集合**OracleCommand**。 该参数的名称必须与查询中的 REF CURSOR 参数名称相匹配。 设置的参数的类型**OracleType.Cursor**。 **ExecuteReader**方法你**OracleCommand**将返回**OracleDataReader**为 REF CURSOR。  
  
 如果你**OracleCommand**返回多个 REF CURSOR，添加多个输出参数。 你可以通过调用访问不同的 REF Cursor **OracleCommand.ExecuteReader**方法。 调用**ExecuteReader**返回**OracleDataReader**引用第一个 REF CURSOR。 然后，你可以调用**OracleDataReader.NextResult**方法访问随后的 REF Cursor。 尽管中的参数你**OracleCommand.Parameters**集合匹配 REF CURSOR 输出参数名称， **OracleDataReader**中它们已添加到的顺序对它们进行访问**参数**集合。  
  
 例如，请看下面这个 Oracle 包和包正文。  
  
```  
CREATE OR REPLACE PACKAGE CURSPKG AS   
  TYPE T_CURSOR IS REF CURSOR;   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR);   
END CURSPKG;  
  
CREATE OR REPLACE PACKAGE BODY CURSPKG AS   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR)   
  IS   
  BEGIN   
    OPEN EMPCURSOR FOR SELECT * FROM DEMO.EMPLOYEE;   
    OPEN DEPTCURSOR FOR SELECT * FROM DEMO.DEPARTMENT;   
  END OPEN_TWO_CURSORS;   
END CURSPKG;   
```  
  
 下面的代码创建**OracleCommand** ，通过添加两个参数的类型从先前的 Oracle 包返回 REF Cursor **OracleType.Cursor**到**参数**集合。  
  
```vb  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
```  
  
```csharp  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
```  
  
 以下代码将返回的结果的上一个命令使用**读取**和**NextResult**方法**OracleDataReader**。 REF CURSOR 参数按顺序返回。  
  
```vb  
oraConn.Open()  
  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.CommandType = CommandType.StoredProcedure  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
  
Dim reader As OracleDataReader = cursCmd.ExecuteReader()  
  
Console.WriteLine(vbCrLf & "Emp ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2))  
Loop  
  
reader.NextResult()  
  
Console.WriteLine(vbCrLf & "Dept ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}", reader.GetOracleNumber(0), reader.GetString(1))  
Loop  
' Make sure to always close readers and connections.  
reader.Close()  
oraConn.Close()  
```  
  
```csharp  
oraConn.Open();  
  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.CommandType = CommandType.StoredProcedure;  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
  
OracleDataReader reader = cursCmd.ExecuteReader();  
  
Console.WriteLine("\nEmp ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2));  
  
reader.NextResult();  
  
Console.WriteLine("\nDept ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}", reader.GetOracleNumber(0), reader.GetString(1));  
// Make sure to always close readers and connections.  
reader.Close();  
oraConn.Close();  
```  
  
 下面的示例使用前一个命令来填充**数据集**使用 Oracle 包的结果。  
  
> [!NOTE]
>  若要避免**OverflowException**，我们建议你还处理任何从 Oracle NUMBER 类型转换为有效的.NET Framework 类型之前将值存储在**DataRow**。 你可以使用**FillError**事件来确定是否**OverflowException**发生。 有关详细信息**FillError**事件，请参阅[处理 DataAdapter 事件](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)。  
  
```vb  
Dim ds As DataSet = New DataSet()  
  
Dim adapter As OracleDataAdapter = New OracleDataAdapter(cursCmd)  
adapter.TableMappings.Add("Table", "Employees")  
adapter.TableMappings.Add("Table1", "Departments")  
  
adapter.Fill(ds)  
```  
  
```csharp  
DataSet ds = new DataSet();  
  
OracleDataAdapter adapter = new OracleDataAdapter(cursCmd);  
adapter.TableMappings.Add("Table", "Employees");  
adapter.TableMappings.Add("Table1", "Departments");  
  
adapter.Fill(ds);  
```  
  
## <a name="see-also"></a>另请参阅  
 [使用 Datareader](http://msdn.microsoft.com/en-us/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [Dataadapter 和 Datareader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [命令和参数](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [检索数据库架构信息](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
