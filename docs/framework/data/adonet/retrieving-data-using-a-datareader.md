---
title: 使用 DataReader 检索 ADO 数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 4370a7a700a01943548bf067827e6640245caf4e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482159"
---
# <a name="retrieving-data-using-a-datareader"></a>使用 DataReader 检索 ADO 数据
使用检索的数据**DataReader**涉及到创建的实例**命令**对象，然后创建**DataReader**通过调用**Command.ExecuteReader**从数据源中检索行。 下面的示例演示如何使用**DataReader**其中`reader`表示有效的 DataReader 和`command`表示有效的命令对象。  
  
```  
reader = command.ExecuteReader();  
```  
  
 您使用**读**方法**DataReader**要从查询的结果获取某一行对象。 可以通过传递的名称或序号引用的列访问每个列返回行**DataReader**。 但是，为了获得最佳性能， **DataReader**提供了一系列的方法，可用于访问本机数据类型中的列值 (**GetDateTime**， **GetDouble**， **GetGuid**， **GetInt32**，依此类推)。 有关数据提供程序特定的类型化取值函数方法的列表**Datareader**，请参阅<xref:System.Data.OleDb.OleDbDataReader>和<xref:System.Data.SqlClient.SqlDataReader>。 假定基础数据类型为已知，如果使用类型化访问器方法，将减少在检索列值时所需的类型转换量。  
  
> [!NOTE]
>  Windows Server 2003 版本的.NET Framework 包括的其他属性**DataReader**， **HasRows**，这样您就可以确定如果**DataReader**已经从其返回任何结果之前读取。  
  
 下面的代码示例循环访问**DataReader**对象，并从每个行返回两个列。  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 **DataReader**提供未缓冲的数据流使过程逻辑可以有效地按顺序处理数据源的结果的数据。 **DataReader**是一个不错的选择，因为这些数据不在内存中缓存检索大量数据时。  
  
## <a name="closing-the-datareader"></a>关闭 DataReader  
 应始终调用**关闭**方法时使用完**DataReader**对象。  
  
 如果你**命令**包含输出参数或返回值，它们将不可用之前**DataReader**已关闭。  
  
 请注意，当**DataReader**处于打开状态，**连接**处于独占方式使用**DataReader**。 不能执行任何命令**连接**，包括创建另一个**DataReader**，直到原始**DataReader**已关闭。  
  
> [!NOTE]
>  不要调用**关闭**或**Dispose**上**连接**即**DataReader**，或在任何其他托管的对象**Finalize**类的方法。 在终结器中，仅释放类直接拥有的非托管资源。 如果您的类不拥有任何非托管的资源，不包括**Finalize**在类定义中的方法。 有关详细信息，请参阅[垃圾回收](../../../../docs/standard/garbage-collection/index.md)。  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>使用 NextResult 检索多个结果集  
 如果返回多个结果集， **DataReader**提供**NextResult**方法来循环访问结果按顺序设置。 以下示例显示 <xref:System.Data.SqlClient.SqlDataReader> 如何使用 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 方法处理两个 SELECT 语句的结果。  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>从 DataReader 中获取架构信息  
 虽然**DataReader**是打开状态，可以检索有关当前结果集使用的架构信息**GetSchemaTable**方法。 **GetSchemaTable**返回<xref:System.Data.DataTable>包含行和列包含当前结果集的架构信息填充的对象。 **DataTable**结果集的每一列中对应一行。 架构表行的每个列都映射到列中返回的属性的结果集，其中**ColumnName**属性名称和列的值是属性的值。 下面的代码示例写出的架构信息**DataReader**。  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>使用 OLE DB 章节  
 分层行集或章节 (OLE DB 类型**DBTYPE_HCHAPTER**，ADO 类型**adChapter**) 可以使用检索<xref:System.Data.OleDb.OleDbDataReader>。 当包含某章节的查询返回作为**DataReader**，一章中列的形式返回**DataReader** ，并作为公开**DataReader**对象。  
  
 ADO.NET**数据集**还用于表示分层行集使用表之间的父-子关系。 有关详细信息，请参阅[数据集、 数据表和数据视图](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)。  
  
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
  
 可以检索**OracleDataReader**对象，表示使用 Oracle REF CURSOR<xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>方法，并且你还可以指定<xref:System.Data.OracleClient.OracleCommand>，它返回一个或多个 Oracle REF Cursor 作为**SelectCommand**有关<xref:System.Data.OracleClient.OracleDataAdapter>用来填充<xref:System.Data.DataSet>。  
  
 若要访问从 Oracle 数据源返回的 REF CURSOR，创建**OracleCommand**查询，并添加引用到 REF CURSOR 的输出参数**参数**你的集合**OracleCommand**。 该参数的名称必须与查询中的 REF CURSOR 参数名称相匹配。 设置的参数的类型**OracleType.Cursor**。 **ExecuteReader**方法的你**OracleCommand**将返回**OracleDataReader**的 REF CURSOR。  
  
 如果你**OracleCommand**返回多个 REF CURSOR，添加多个输出参数。 可以通过调用访问不同的 REF Cursor **OracleCommand.ExecuteReader**方法。 在调用**ExecuteReader**返回**OracleDataReader**引用第一个 REF CURSOR。 然后，可以调用**OracleDataReader.NextResult**方法访问随后的 REF Cursor。 尽管中的参数在**OracleCommand.Parameters**集合匹配 REF CURSOR 输出参数的名称， **OracleDataReader**它们已添加到中的顺序访问它们**参数**集合。  
  
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
  
 下面的代码创建**OracleCommand**通过添加两个参数的类型从先前的 Oracle 包返回 REF Cursor **OracleType.Cursor**到**参数**集合。  
  
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
  
 以下代码将返回上一个命令使用的结果**读**并**NextResult**方法**OracleDataReader**。 REF CURSOR 参数按顺序返回。  
  
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
  
 下面的示例使用前一命令来填充**数据集**与 Oracle 包的结果。  
  
> [!NOTE]
>  若要避免**OverflowException**，我们建议你还处理任何从 Oracle NUMBER 类型转换为有效的.NET Framework 类型存储中的值之前**DataRow**。 可以使用**FillError**事件来确定是否**OverflowException**已发生。 有关详细信息**FillError**事件，请参阅[处理 DataAdapter 事件](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)。  
  
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
  
## <a name="see-also"></a>请参阅  
 [使用 Datareader](https://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [DataAdapters 和 DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [命令和参数](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [检索数据库架构信息](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
