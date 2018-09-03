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
# <a name="retrieving-data-using-a-datareader"></a><span data-ttu-id="a5ee4-102">使用 DataReader 检索 ADO 数据</span><span class="sxs-lookup"><span data-stu-id="a5ee4-102">Retrieving Data Using a DataReader</span></span>
<span data-ttu-id="a5ee4-103">使用检索的数据**DataReader**涉及到创建的实例**命令**对象，然后创建**DataReader**通过调用**Command.ExecuteReader**从数据源中检索行。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-103">Retrieving data using a **DataReader** involves creating an instance of the **Command** object and then creating a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="a5ee4-104">下面的示例演示如何使用**DataReader**其中`reader`表示有效的 DataReader 和`command`表示有效的命令对象。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-104">The following example illustrates using a **DataReader** where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  
  
```  
reader = command.ExecuteReader();  
```  
  
 <span data-ttu-id="a5ee4-105">您使用**读**方法**DataReader**要从查询的结果获取某一行对象。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-105">You use the **Read** method of the **DataReader** object to obtain a row from the results of the query.</span></span> <span data-ttu-id="a5ee4-106">可以通过传递的名称或序号引用的列访问每个列返回行**DataReader**。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-106">You can access each column of the returned row by passing the name or ordinal reference of the column to the **DataReader**.</span></span> <span data-ttu-id="a5ee4-107">但是，为了获得最佳性能， **DataReader**提供了一系列的方法，可用于访问本机数据类型中的列值 (**GetDateTime**， **GetDouble**， **GetGuid**， **GetInt32**，依此类推)。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-107">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="a5ee4-108">有关数据提供程序特定的类型化取值函数方法的列表**Datareader**，请参阅<xref:System.Data.OleDb.OleDbDataReader>和<xref:System.Data.SqlClient.SqlDataReader>。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-108">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="a5ee4-109">假定基础数据类型为已知，如果使用类型化访问器方法，将减少在检索列值时所需的类型转换量。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-109">Using the typed accessor methods, assuming the underlying data type is known, reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5ee4-110">Windows Server 2003 版本的.NET Framework 包括的其他属性**DataReader**， **HasRows**，这样您就可以确定如果**DataReader**已经从其返回任何结果之前读取。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-110">The Windows Server 2003 release of the .NET Framework includes an additional property for the **DataReader**, **HasRows**, which enables you to determine if the **DataReader** has returned any results before reading from it.</span></span>  
  
 <span data-ttu-id="a5ee4-111">下面的代码示例循环访问**DataReader**对象，并从每个行返回两个列。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-111">The following code example iterates through a **DataReader** object, and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 <span data-ttu-id="a5ee4-112">**DataReader**提供未缓冲的数据流使过程逻辑可以有效地按顺序处理数据源的结果的数据。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-112">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="a5ee4-113">**DataReader**是一个不错的选择，因为这些数据不在内存中缓存检索大量数据时。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-113">The **DataReader** is a good choice when retrieving large amounts of data because the data is not cached in memory.</span></span>  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="a5ee4-114">关闭 DataReader</span><span class="sxs-lookup"><span data-stu-id="a5ee4-114">Closing the DataReader</span></span>  
 <span data-ttu-id="a5ee4-115">应始终调用**关闭**方法时使用完**DataReader**对象。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-115">You should always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="a5ee4-116">如果你**命令**包含输出参数或返回值，它们将不可用之前**DataReader**已关闭。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-116">If your **Command** contains output parameters or return values, they will not be available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="a5ee4-117">请注意，当**DataReader**处于打开状态，**连接**处于独占方式使用**DataReader**。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-117">Note that while a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="a5ee4-118">不能执行任何命令**连接**，包括创建另一个**DataReader**，直到原始**DataReader**已关闭。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-118">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5ee4-119">不要调用**关闭**或**Dispose**上**连接**即**DataReader**，或在任何其他托管的对象**Finalize**类的方法。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-119">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="a5ee4-120">在终结器中，仅释放类直接拥有的非托管资源。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-120">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="a5ee4-121">如果您的类不拥有任何非托管的资源，不包括**Finalize**在类定义中的方法。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-121">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="a5ee4-122">有关详细信息，请参阅[垃圾回收](../../../../docs/standard/garbage-collection/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-122">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="a5ee4-123">使用 NextResult 检索多个结果集</span><span class="sxs-lookup"><span data-stu-id="a5ee4-123">Retrieving Multiple Result Sets using NextResult</span></span>  
 <span data-ttu-id="a5ee4-124">如果返回多个结果集， **DataReader**提供**NextResult**方法来循环访问结果按顺序设置。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-124">If multiple result sets are returned, the **DataReader** provides the **NextResult** method to iterate through the result sets in order.</span></span> <span data-ttu-id="a5ee4-125">以下示例显示 <xref:System.Data.SqlClient.SqlDataReader> 如何使用 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 方法处理两个 SELECT 语句的结果。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-125">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="a5ee4-126">从 DataReader 中获取架构信息</span><span class="sxs-lookup"><span data-stu-id="a5ee4-126">Getting Schema Information from the DataReader</span></span>  
 <span data-ttu-id="a5ee4-127">虽然**DataReader**是打开状态，可以检索有关当前结果集使用的架构信息**GetSchemaTable**方法。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-127">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="a5ee4-128">**GetSchemaTable**返回<xref:System.Data.DataTable>包含行和列包含当前结果集的架构信息填充的对象。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-128">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="a5ee4-129">**DataTable**结果集的每一列中对应一行。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-129">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="a5ee4-130">架构表行的每个列都映射到列中返回的属性的结果集，其中**ColumnName**属性名称和列的值是属性的值。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-130">Each column of the schema table row maps to a property of the column returned in the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="a5ee4-131">下面的代码示例写出的架构信息**DataReader**。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-131">The following code example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="a5ee4-132">使用 OLE DB 章节</span><span class="sxs-lookup"><span data-stu-id="a5ee4-132">Working with OLE DB Chapters</span></span>  
 <span data-ttu-id="a5ee4-133">分层行集或章节 (OLE DB 类型**DBTYPE_HCHAPTER**，ADO 类型**adChapter**) 可以使用检索<xref:System.Data.OleDb.OleDbDataReader>。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-133">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**) can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="a5ee4-134">当包含某章节的查询返回作为**DataReader**，一章中列的形式返回**DataReader** ，并作为公开**DataReader**对象。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-134">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="a5ee4-135">ADO.NET**数据集**还用于表示分层行集使用表之间的父-子关系。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-135">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets using parent-child relationships between tables.</span></span> <span data-ttu-id="a5ee4-136">有关详细信息，请参阅[数据集、 数据表和数据视图](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-136">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="a5ee4-137">以下代码示例使用 MSDataShape 提供程序来为客户列表中的每个客户生成订单的章节列。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-137">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="a5ee4-138">使用 Oracle REF CURSOR 返回结果</span><span class="sxs-lookup"><span data-stu-id="a5ee4-138">Returning Results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="a5ee4-139">Oracle .NET Framework 数据提供程序支持使用 Oracle REF CURSOR 返回查询结果。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-139">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="a5ee4-140">Oracle REF CURSOR 以 <xref:System.Data.OracleClient.OracleDataReader> 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-140">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="a5ee4-141">可以检索**OracleDataReader**对象，表示使用 Oracle REF CURSOR<xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>方法，并且你还可以指定<xref:System.Data.OracleClient.OracleCommand>，它返回一个或多个 Oracle REF Cursor 作为**SelectCommand**有关<xref:System.Data.OracleClient.OracleDataAdapter>用来填充<xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-141">You can retrieve an **OracleDataReader** object, that represents an Oracle REF CURSOR using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method, and you can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="a5ee4-142">若要访问从 Oracle 数据源返回的 REF CURSOR，创建**OracleCommand**查询，并添加引用到 REF CURSOR 的输出参数**参数**你的集合**OracleCommand**。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-142">To access a REF CURSOR returned from an Oracle data source, create an **OracleCommand** for your query and add an output parameter that references the REF CURSOR to the **Parameters** collection of your **OracleCommand**.</span></span> <span data-ttu-id="a5ee4-143">该参数的名称必须与查询中的 REF CURSOR 参数名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="a5ee4-144">设置的参数的类型**OracleType.Cursor**。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-144">Set the type of the parameter to **OracleType.Cursor**.</span></span> <span data-ttu-id="a5ee4-145">**ExecuteReader**方法的你**OracleCommand**将返回**OracleDataReader**的 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-145">The **ExecuteReader** method of your **OracleCommand** will return an **OracleDataReader** for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="a5ee4-146">如果你**OracleCommand**返回多个 REF CURSOR，添加多个输出参数。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-146">If your **OracleCommand** returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="a5ee4-147">可以通过调用访问不同的 REF Cursor **OracleCommand.ExecuteReader**方法。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-147">You can access the different REF CURSORs by calling the **OracleCommand.ExecuteReader** method.</span></span> <span data-ttu-id="a5ee4-148">在调用**ExecuteReader**返回**OracleDataReader**引用第一个 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-148">The call to **ExecuteReader** returns an **OracleDataReader** referencing the first REF CURSOR.</span></span> <span data-ttu-id="a5ee4-149">然后，可以调用**OracleDataReader.NextResult**方法访问随后的 REF Cursor。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-149">You can then call the **OracleDataReader.NextResult** method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="a5ee4-150">尽管中的参数在**OracleCommand.Parameters**集合匹配 REF CURSOR 输出参数的名称， **OracleDataReader**它们已添加到中的顺序访问它们**参数**集合。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-150">Although the parameters in your **OracleCommand.Parameters** collection match the REF CURSOR output parameters by name, the **OracleDataReader** accesses them in the order that they were added to the **Parameters** collection.</span></span>  
  
 <span data-ttu-id="a5ee4-151">例如，请看下面这个 Oracle 包和包正文。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-151">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="a5ee4-152">下面的代码创建**OracleCommand**通过添加两个参数的类型从先前的 Oracle 包返回 REF Cursor **OracleType.Cursor**到**参数**集合。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-152">The following code creates an **OracleCommand** that returns the REF CURSORs from the previous Oracle package by adding two parameters of type **OracleType.Cursor** to the **Parameters** collection.</span></span>  
  
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
  
 <span data-ttu-id="a5ee4-153">以下代码将返回上一个命令使用的结果**读**并**NextResult**方法**OracleDataReader**。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-153">The following code returns the results of the previous command using the **Read** and **NextResult** methods of the **OracleDataReader**.</span></span> <span data-ttu-id="a5ee4-154">REF CURSOR 参数按顺序返回。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="a5ee4-155">下面的示例使用前一命令来填充**数据集**与 Oracle 包的结果。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-155">The following example uses the previous command to populate a **DataSet** with the results of the Oracle package.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5ee4-156">若要避免**OverflowException**，我们建议你还处理任何从 Oracle NUMBER 类型转换为有效的.NET Framework 类型存储中的值之前**DataRow**。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a **DataRow**.</span></span> <span data-ttu-id="a5ee4-157">可以使用**FillError**事件来确定是否**OverflowException**已发生。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-157">You can use the **FillError** event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="a5ee4-158">有关详细信息**FillError**事件，请参阅[处理 DataAdapter 事件](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)。</span><span class="sxs-lookup"><span data-stu-id="a5ee4-158">For more information on the **FillError** event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a5ee4-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5ee4-159">See Also</span></span>  
 [<span data-ttu-id="a5ee4-160">使用 Datareader</span><span class="sxs-lookup"><span data-stu-id="a5ee4-160">Working with DataReaders</span></span>](https://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [<span data-ttu-id="a5ee4-161">DataAdapters 和 DataReaders</span><span class="sxs-lookup"><span data-stu-id="a5ee4-161">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="a5ee4-162">命令和参数</span><span class="sxs-lookup"><span data-stu-id="a5ee4-162">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="a5ee4-163">检索数据库架构信息</span><span class="sxs-lookup"><span data-stu-id="a5ee4-163">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [<span data-ttu-id="a5ee4-164">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="a5ee4-164">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
