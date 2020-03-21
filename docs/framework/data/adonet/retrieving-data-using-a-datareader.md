---
title: 使用 DataReader 检索 ADO 数据
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 88cd85ce343aaab08b944f81c9659918014da0a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149019"
---
# <a name="retrieve-data-using-a-datareader"></a>使用数据读取器检索数据
若要使用**DataReader**检索数据，请创建**命令**对象的实例，然后通过调用**Command.ExecuteReader**从数据源检索行来创建**DataReader。** **DataReader**提供了一个未缓冲的数据流，允许过程逻辑按顺序有效地处理数据源的结果。 当您检索大量数据时 **，DataReader**是一个不错的选择，因为数据未缓存在内存中。

下面的示例演示了使用**DataReader**，`reader`其中表示有效的 DataReader`command`并表示有效的命令对象。  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

使用**DataReader.Read**方法从查询结果中获取行。 通过将列的名称或单位编号传递给**DataReader，** 可以访问返回行的每个列。 但是，为了获得最佳性能 **，DataReader**提供了一系列方法，允许您访问其本机数据类型中的列值（GetDateTime、GetDouble、GetGuid、GetInt32 等）。**GetDateTime** **GetDouble** **GetGuid** **GetInt32** 有关特定于数据提供程序**的数据阅读器**的键入访问器方法的列表，请参阅<xref:System.Data.OleDb.OleDbDataReader>和<xref:System.Data.SqlClient.SqlDataReader>。 当您知道基础数据类型时，使用键入的访问器方法可减少检索列值时所需的类型转换量。  
  
 以下示例通过**DataReader**对象进行遍读，并从每行返回两列。  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a>关闭 DataReader  
 使用完**DataReader**对象后，始终调用**Close**方法。  
  
 如果**命令**包含输出参数或返回值，则在**关闭 DataReader**之前，这些值不可用。  
  
 当**数据阅读器**处于打开状态时，**该连接**仅由该**数据阅读器**使用。 在关闭原始**数据阅读器**之前，您不能执行**连接**的任何命令，包括创建另一个**DataReader。**  
  
> [!NOTE]
> 不要调用**连接****、DataReader**或**Connection**类**的 Finalize**方法中的任何其他托管**对象。** 在终结器中，仅释放类直接拥有的非托管资源。 如果类不拥有任何非托管资源，请不要在类定义中包括**Finalize**方法。 有关详细信息，请参阅[垃圾回收](../../../standard/garbage-collection/index.md)。  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>使用 NextResult 检索多个结果集  
 如果**DataReader**返回多个结果集，请调用**NextResult**方法以按顺序遍读结果集。 以下示例显示 <xref:System.Data.SqlClient.SqlDataReader> 如何使用 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 方法处理两个 SELECT 语句的结果。  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>从数据阅读器获取架构信息  
 打开**DataReader**时，可以使用**GetSchemaTable**方法检索有关当前结果集的架构信息。 **GetSchemaTable**返回<xref:System.Data.DataTable>一个包含当前结果集的架构信息的行和列填充的对象。 **数据表**包含结果集每一列的一行。 架构表的每一列映射到结果集行中返回的列的属性，其中 **"列名称**"是属性的名称，列的值是属性的值。 下面的示例为**DataReader**编写架构信息。  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>使用 OLE DB 章节  
 可以使用 检索<xref:System.Data.OleDb.OleDbDataReader>层次结构行集或章节（OLE DB 类型**DBTYPE_HCHAPTER**ADO 类型**广告章节**）。 当包含章节的查询作为**DataReader**返回时，该章将作为该**数据阅读器**中的列返回，并作为**DataReader**对象公开。  
  
 **DataSetADO.NET**也可用于使用表之间的父子关系来表示分层行集。 有关详细信息，请参阅[数据集、数据表和数据视图](./dataset-datatable-dataview/index.md)。  
  
 以下代码示例使用 MSDataShape 提供程序来为客户列表中的每个客户生成订单的章节列。  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" &
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")

    Using custCMD As OleDbCommand = New OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " &
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " &
        "RELATE CustomerID TO CustomerID)", connection)

        connection.Open()

        Using custReader As OleDbDataReader = custCMD.ExecuteReader()

            Do While custReader.Read()
                Console.WriteLine("Orders for " & custReader.GetString(1))
                ' custReader.GetString(1) = CompanyName  

                Using orderReader As OleDbDataReader = custReader.GetValue(2)
                    ' custReader.GetValue(2) = Orders chapter as DataReader  

                    Do While orderReader.Read()
                        Console.WriteLine(vbTab & orderReader.GetInt32(1))
                        ' orderReader.GetInt32(1) = OrderID  
                    Loop
                    orderReader.Close()
                End Using
            Loop
            ' Make sure to always close readers and connections.  
            custReader.Close()
        End Using
    End Using
End Using
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" +
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"))
{
    using (OleDbCommand custCMD = new OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +
        "RELATE CustomerID TO CustomerID)", connection))
    {
        connection.Open();

        using (OleDbDataReader custReader = custCMD.ExecuteReader())
        {

            while (custReader.Read())
            {
                Console.WriteLine("Orders for " + custReader.GetString(1));
                // custReader.GetString(1) = CompanyName  

                using (OleDbDataReader orderReader = (OleDbDataReader)custReader.GetValue(2))
                {
                    // custReader.GetValue(2) = Orders chapter as DataReader  

                    while (orderReader.Read())
                        Console.WriteLine("\t" + orderReader.GetInt32(1));
                    // orderReader.GetInt32(1) = OrderID  
                    orderReader.Close();
                }
            }
            // Make sure to always close readers and connections.  
            custReader.Close();
        }
    }
}
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a>使用 Oracle REF CURSORs 返回结果  
 Oracle .NET Framework 数据提供程序支持使用 Oracle REF CURSOR 返回查询结果。 Oracle REF CURSOR 以 <xref:System.Data.OracleClient.OracleDataReader> 的形式返回。  
  
 可以使用<xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>方法检索<xref:System.Data.OracleClient.OracleDataReader>表示 Oracle REF CURSOR 的对象。 还可以指定 返回<xref:System.Data.OracleClient.OracleCommand>一个或多个 Oracle REF CURSOR 作为<xref:System.Data.OracleClient.OracleDataAdapter>用于填充 的<xref:System.Data.DataSet>**SelectCommand 的 指定命令**。  
  
 要访问从 Oracle 数据源返回的 REF CURSOR，<xref:System.Data.OracleClient.OracleCommand>请为查询创建 一个，并添加一个输出参数，<xref:System.Data.OracleClient.OracleCommand.Parameters>将 REF <xref:System.Data.OracleClient.OracleCommand>CURSOR 引用到 集合中。 该参数的名称必须与查询中的 REF CURSOR 参数名称相匹配。 将参数的类型设置为<xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>。 <xref:System.Data.OracleClient.OracleCommand>方法<xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType><xref:System.Data.OracleClient.OracleDataReader>返回 REF CURSOR 的  
  
 如果<xref:System.Data.OracleClient.OracleCommand>返回多个 REF CURSORS，请添加多个输出参数。 您可以通过调用<xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType>方法访问不同的 REF CURSOR。 调用 返回<xref:System.Data.OracleClient.OracleCommand.ExecuteReader>引用第<xref:System.Data.OracleClient.OracleDataReader>一个 REF CURSOR。 然后，<xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType>您可以调用 方法以访问后续的 REF CURSOR。 尽管<xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType>集合中的参数按名称与 REF CURSOR 输出参数匹配，但<xref:System.Data.OracleClient.OracleDataReader>访问参数的顺序是添加到集合中<xref:System.Data.OracleClient.OracleCommand.Parameters>的顺序。  
  
 例如，请看下面这个 Oracle 包和包正文。  
  
```sql
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
  
 以下代码创建 一<xref:System.Data.OracleClient.OracleCommand>个，通过向<xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType><xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType>集合添加两个类型的参数来返回上一个 Oracle 包中的 REF CURSOR。  
  
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
  
 以下代码使用 的<xref:System.Data.OracleClient.OracleDataReader.Read>和<xref:System.Data.OracleClient.OracleDataReader.NextResult>返回上一个命令的结果。 <xref:System.Data.OracleClient.OracleDataReader> REF CURSOR 参数按顺序返回。  
  
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
  
 下面的示例使用前面的命令用 Oracle 包<xref:System.Data.DataSet>的结果填充 。  
  
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

> [!NOTE]
> 为了避免**溢出异常**，我们建议您在将值存储在 中之前，还要处理从 Oracle NUMBER 类型到有效的 .NET 框架类型的任何转换<xref:System.Data.DataRow>。 您可以使用该<xref:System.Data.Common.DataAdapter.FillError>事件来确定是否发生了**溢出异常**。 有关事件的详细信息，<xref:System.Data.Common.DataAdapter.FillError>请参阅[处理数据适配器事件](handling-dataadapter-events.md)。  
  
## <a name="see-also"></a>另请参阅

- [DataAdapters 和 DataReaders](dataadapters-and-datareaders.md)
- [命令和参数](commands-and-parameters.md)
- [检索数据库架构信息](retrieving-database-schema-information.md)
- [ADO.NET 概述](ado-net-overview.md)
