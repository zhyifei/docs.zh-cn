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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 60328d766a931abd7a1a3e9dc08c68928e01f2d2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="retrieving-data-using-a-datareader"></a><span data-ttu-id="e5498-102">使用 DataReader 检索 ADO 数据</span><span class="sxs-lookup"><span data-stu-id="e5498-102">Retrieving Data Using a DataReader</span></span>
<span data-ttu-id="e5498-103">检索数据使用**DataReader**涉及到创建的实例**命令**对象，然后创建**DataReader**通过调用**Command.ExecuteReader**从数据源中检索行。</span><span class="sxs-lookup"><span data-stu-id="e5498-103">Retrieving data using a **DataReader** involves creating an instance of the **Command** object and then creating a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="e5498-104">下面的示例演示如何使用**DataReader**其中`reader`表示有效的 DataReader 和`command`表示有效的命令对象。</span><span class="sxs-lookup"><span data-stu-id="e5498-104">The following example illustrates using a **DataReader** where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  
  
```  
reader = command.ExecuteReader();  
```  
  
 <span data-ttu-id="e5498-105">你使用**读取**方法**DataReader**对象从查询结果中获取行。</span><span class="sxs-lookup"><span data-stu-id="e5498-105">You use the **Read** method of the **DataReader** object to obtain a row from the results of the query.</span></span> <span data-ttu-id="e5498-106">你可以通过传递的名称或序号引用的列访问返回的行的每一列**DataReader**。</span><span class="sxs-lookup"><span data-stu-id="e5498-106">You can access each column of the returned row by passing the name or ordinal reference of the column to the **DataReader**.</span></span> <span data-ttu-id="e5498-107">但是，为了获得最佳性能， **DataReader**提供使你能够访问其本机数据类型中的列值的方法的一系列 (**GetDateTime**， **GetDouble**， **GetGuid**， **GetInt32**，依次类推)。</span><span class="sxs-lookup"><span data-stu-id="e5498-107">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="e5498-108">有关的数据提供程序特定的类型化访问器方法列表**DataReaders**，请参阅<xref:System.Data.OleDb.OleDbDataReader>和<xref:System.Data.SqlClient.SqlDataReader>。</span><span class="sxs-lookup"><span data-stu-id="e5498-108">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="e5498-109">假定基础数据类型为已知，如果使用类型化访问器方法，将减少在检索列值时所需的类型转换量。</span><span class="sxs-lookup"><span data-stu-id="e5498-109">Using the typed accessor methods, assuming the underlying data type is known, reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5498-110">Windows Server 2003 版本的.NET Framework 包括的其他属性**DataReader**， **HasRows**，这使您能够确定如果**DataReader**已从其返回之前读取任何结果。</span><span class="sxs-lookup"><span data-stu-id="e5498-110">The Windows Server 2003 release of the .NET Framework includes an additional property for the **DataReader**, **HasRows**, which enables you to determine if the **DataReader** has returned any results before reading from it.</span></span>  
  
 <span data-ttu-id="e5498-111">下面的代码示例循环访问**DataReader**对象，并从每个行中的返回两个列。</span><span class="sxs-lookup"><span data-stu-id="e5498-111">The following code example iterates through a **DataReader** object, and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 <span data-ttu-id="e5498-112">**DataReader**提供未缓冲的数据流，使过程逻辑可以有效地按顺序处理数据源的结果。</span><span class="sxs-lookup"><span data-stu-id="e5498-112">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="e5498-113">**DataReader**是一个不错的选择，因为数据不在内存中缓存中检索大量数据时。</span><span class="sxs-lookup"><span data-stu-id="e5498-113">The **DataReader** is a good choice when retrieving large amounts of data because the data is not cached in memory.</span></span>  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="e5498-114">关闭 DataReader</span><span class="sxs-lookup"><span data-stu-id="e5498-114">Closing the DataReader</span></span>  
 <span data-ttu-id="e5498-115">始终应调用**关闭**方法时使用完**DataReader**对象。</span><span class="sxs-lookup"><span data-stu-id="e5498-115">You should always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="e5498-116">如果你**命令**包含输出参数或返回值，它们将不可用之前**DataReader**已关闭。</span><span class="sxs-lookup"><span data-stu-id="e5498-116">If your **Command** contains output parameters or return values, they will not be available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="e5498-117">请注意，当**DataReader**处于打开状态，**连接**正在独占方式使用**DataReader**。</span><span class="sxs-lookup"><span data-stu-id="e5498-117">Note that while a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="e5498-118">无法执行任何命令**连接**，包括创建另一个**DataReader**，直到原始**DataReader**已关闭。</span><span class="sxs-lookup"><span data-stu-id="e5498-118">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5498-119">不要调用**关闭**或**释放**上**连接**、 **DataReader**，或在任何其他托管的对象**Finalize**你类的方法。</span><span class="sxs-lookup"><span data-stu-id="e5498-119">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="e5498-120">在终结器中，仅释放类直接拥有的非托管资源。</span><span class="sxs-lookup"><span data-stu-id="e5498-120">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="e5498-121">如果你的类不拥有任何非托管的资源，不包括**Finalize**在类定义的方法。</span><span class="sxs-lookup"><span data-stu-id="e5498-121">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="e5498-122">有关详细信息，请参阅[垃圾回收](../../../../docs/standard/garbage-collection/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e5498-122">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="e5498-123">使用 NextResult 检索多个结果集</span><span class="sxs-lookup"><span data-stu-id="e5498-123">Retrieving Multiple Result Sets using NextResult</span></span>  
 <span data-ttu-id="e5498-124">如果返回了多个结果集， **DataReader**提供**NextResult**方法来循环访问结果以设置顺序。</span><span class="sxs-lookup"><span data-stu-id="e5498-124">If multiple result sets are returned, the **DataReader** provides the **NextResult** method to iterate through the result sets in order.</span></span> <span data-ttu-id="e5498-125">以下示例显示 <xref:System.Data.SqlClient.SqlDataReader> 如何使用 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 方法处理两个 SELECT 语句的结果。</span><span class="sxs-lookup"><span data-stu-id="e5498-125">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="e5498-126">从 DataReader 中获取架构信息</span><span class="sxs-lookup"><span data-stu-id="e5498-126">Getting Schema Information from the DataReader</span></span>  
 <span data-ttu-id="e5498-127">虽然**DataReader**是打开，你可以检索有关当前结果集使用的架构信息**GetSchemaTable**方法。</span><span class="sxs-lookup"><span data-stu-id="e5498-127">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="e5498-128">**GetSchemaTable**返回<xref:System.Data.DataTable>具有行和列包含当前结果集的架构信息填充的对象。</span><span class="sxs-lookup"><span data-stu-id="e5498-128">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="e5498-129">**DataTable**结果集的每一列中对应一行。</span><span class="sxs-lookup"><span data-stu-id="e5498-129">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="e5498-130">架构表行的每一列都映射到属性中返回的列的结果集，其中**ColumnName**是属性的名称和列的值是属性的值。</span><span class="sxs-lookup"><span data-stu-id="e5498-130">Each column of the schema table row maps to a property of the column returned in the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="e5498-131">下面的代码示例将写出的架构信息**DataReader**。</span><span class="sxs-lookup"><span data-stu-id="e5498-131">The following code example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="e5498-132">使用 OLE DB 章节</span><span class="sxs-lookup"><span data-stu-id="e5498-132">Working with OLE DB Chapters</span></span>  
 <span data-ttu-id="e5498-133">分层行集或章节 (OLE DB 类型**DBTYPE_HCHAPTER**，ADO 类型**adChapter**) 可以使用检索<xref:System.Data.OleDb.OleDbDataReader>。</span><span class="sxs-lookup"><span data-stu-id="e5498-133">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**) can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="e5498-134">当为返回包含某章节的查询时**DataReader**，作为中列的返回章**DataReader**和公开为**DataReader**对象。</span><span class="sxs-lookup"><span data-stu-id="e5498-134">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="e5498-135">ADO.NET**数据集**还用于表示分层行集使用父-子表之间的关系。</span><span class="sxs-lookup"><span data-stu-id="e5498-135">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets using parent-child relationships between tables.</span></span> <span data-ttu-id="e5498-136">有关详细信息，请参阅[数据集、 数据表和数据视图](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e5498-136">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="e5498-137">以下代码示例使用 MSDataShape 提供程序来为客户列表中的每个客户生成订单的章节列。</span><span class="sxs-lookup"><span data-stu-id="e5498-137">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="e5498-138">使用 Oracle REF CURSOR 返回结果</span><span class="sxs-lookup"><span data-stu-id="e5498-138">Returning Results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="e5498-139">Oracle .NET Framework 数据提供程序支持使用 Oracle REF CURSOR 返回查询结果。</span><span class="sxs-lookup"><span data-stu-id="e5498-139">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="e5498-140">Oracle REF CURSOR 以 <xref:System.Data.OracleClient.OracleDataReader> 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="e5498-140">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="e5498-141">你可以检索**OracleDataReader**对象，表示使用 Oracle REF CURSOR<xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>方法，并且你还可以指定<xref:System.Data.OracleClient.OracleCommand>返回一个或多个 Oracle REF Cursor 作为**SelectCommand**为<xref:System.Data.OracleClient.OracleDataAdapter>用来填充<xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="e5498-141">You can retrieve an **OracleDataReader** object, that represents an Oracle REF CURSOR using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method, and you can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="e5498-142">若要访问从 Oracle 数据源返回的 REF CURSOR，创建**OracleCommand**查询并添加引用到 REF CURSOR 的输出参数**参数**你的集合**OracleCommand**。</span><span class="sxs-lookup"><span data-stu-id="e5498-142">To access a REF CURSOR returned from an Oracle data source, create an **OracleCommand** for your query and add an output parameter that references the REF CURSOR to the **Parameters** collection of your **OracleCommand**.</span></span> <span data-ttu-id="e5498-143">该参数的名称必须与查询中的 REF CURSOR 参数名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="e5498-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="e5498-144">设置的参数的类型**OracleType.Cursor**。</span><span class="sxs-lookup"><span data-stu-id="e5498-144">Set the type of the parameter to **OracleType.Cursor**.</span></span> <span data-ttu-id="e5498-145">**ExecuteReader**方法你**OracleCommand**将返回**OracleDataReader**为 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="e5498-145">The **ExecuteReader** method of your **OracleCommand** will return an **OracleDataReader** for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="e5498-146">如果你**OracleCommand**返回多个 REF CURSOR，添加多个输出参数。</span><span class="sxs-lookup"><span data-stu-id="e5498-146">If your **OracleCommand** returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="e5498-147">你可以通过调用访问不同的 REF Cursor **OracleCommand.ExecuteReader**方法。</span><span class="sxs-lookup"><span data-stu-id="e5498-147">You can access the different REF CURSORs by calling the **OracleCommand.ExecuteReader** method.</span></span> <span data-ttu-id="e5498-148">调用**ExecuteReader**返回**OracleDataReader**引用第一个 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="e5498-148">The call to **ExecuteReader** returns an **OracleDataReader** referencing the first REF CURSOR.</span></span> <span data-ttu-id="e5498-149">然后，你可以调用**OracleDataReader.NextResult**方法访问随后的 REF Cursor。</span><span class="sxs-lookup"><span data-stu-id="e5498-149">You can then call the **OracleDataReader.NextResult** method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="e5498-150">尽管中的参数你**OracleCommand.Parameters**集合匹配 REF CURSOR 输出参数名称， **OracleDataReader**中它们已添加到的顺序对它们进行访问**参数**集合。</span><span class="sxs-lookup"><span data-stu-id="e5498-150">Although the parameters in your **OracleCommand.Parameters** collection match the REF CURSOR output parameters by name, the **OracleDataReader** accesses them in the order that they were added to the **Parameters** collection.</span></span>  
  
 <span data-ttu-id="e5498-151">例如，请看下面这个 Oracle 包和包正文。</span><span class="sxs-lookup"><span data-stu-id="e5498-151">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="e5498-152">下面的代码创建**OracleCommand** ，通过添加两个参数的类型从先前的 Oracle 包返回 REF Cursor **OracleType.Cursor**到**参数**集合。</span><span class="sxs-lookup"><span data-stu-id="e5498-152">The following code creates an **OracleCommand** that returns the REF CURSORs from the previous Oracle package by adding two parameters of type **OracleType.Cursor** to the **Parameters** collection.</span></span>  
  
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
  
 <span data-ttu-id="e5498-153">以下代码将返回的结果的上一个命令使用**读取**和**NextResult**方法**OracleDataReader**。</span><span class="sxs-lookup"><span data-stu-id="e5498-153">The following code returns the results of the previous command using the **Read** and **NextResult** methods of the **OracleDataReader**.</span></span> <span data-ttu-id="e5498-154">REF CURSOR 参数按顺序返回。</span><span class="sxs-lookup"><span data-stu-id="e5498-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="e5498-155">下面的示例使用前一个命令来填充**数据集**使用 Oracle 包的结果。</span><span class="sxs-lookup"><span data-stu-id="e5498-155">The following example uses the previous command to populate a **DataSet** with the results of the Oracle package.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5498-156">若要避免**OverflowException**，我们建议你还处理任何从 Oracle NUMBER 类型转换为有效的.NET Framework 类型之前将值存储在**DataRow**。</span><span class="sxs-lookup"><span data-stu-id="e5498-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a **DataRow**.</span></span> <span data-ttu-id="e5498-157">你可以使用**FillError**事件来确定是否**OverflowException**发生。</span><span class="sxs-lookup"><span data-stu-id="e5498-157">You can use the **FillError** event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="e5498-158">有关详细信息**FillError**事件，请参阅[处理 DataAdapter 事件](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)。</span><span class="sxs-lookup"><span data-stu-id="e5498-158">For more information on the **FillError** event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e5498-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5498-159">See Also</span></span>  
 [<span data-ttu-id="e5498-160">使用 Datareader</span><span class="sxs-lookup"><span data-stu-id="e5498-160">Working with DataReaders</span></span>](http://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [<span data-ttu-id="e5498-161">DataAdapters 和 DataReaders</span><span class="sxs-lookup"><span data-stu-id="e5498-161">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="e5498-162">命令和参数</span><span class="sxs-lookup"><span data-stu-id="e5498-162">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="e5498-163">检索数据库架构信息</span><span class="sxs-lookup"><span data-stu-id="e5498-163">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [<span data-ttu-id="e5498-164">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="e5498-164">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
