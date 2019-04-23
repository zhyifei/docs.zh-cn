---
title: 使用 DataReader 检索 ADO 数据
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 8063f239123ec1a2f2650adf9d76f7ceaaa50673
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128673"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="04536-102">使用 DataReader 检索数据</span><span class="sxs-lookup"><span data-stu-id="04536-102">Retrieve data using a DataReader</span></span>
<span data-ttu-id="04536-103">若要检索的数据使用**DataReader**，创建的实例**命令**对象，并创建**DataReader**通过调用**Command.ExecuteReader**从数据源中检索行。</span><span class="sxs-lookup"><span data-stu-id="04536-103">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="04536-104">**DataReader**提供未缓冲的数据流使过程逻辑可以有效地按顺序处理数据源的结果的数据。</span><span class="sxs-lookup"><span data-stu-id="04536-104">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="04536-105">**DataReader**时要检索的数据量大，因为这些数据不在内存中缓存是一个不错的选择。</span><span class="sxs-lookup"><span data-stu-id="04536-105">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="04536-106">下面的示例演示如何使用**DataReader**，其中`reader`表示有效的 DataReader 和`command`表示有效的命令对象。</span><span class="sxs-lookup"><span data-stu-id="04536-106">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="04536-107">使用**DataReader.Read**方法从查询结果中获取某一行。</span><span class="sxs-lookup"><span data-stu-id="04536-107">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="04536-108">可以通过传递的名称或序号的列访问每个列返回行**DataReader**。</span><span class="sxs-lookup"><span data-stu-id="04536-108">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="04536-109">但是，为了获得最佳性能， **DataReader**提供了一系列的方法，可用于访问本机数据类型中的列值 (**GetDateTime**， **GetDouble**， **GetGuid**， **GetInt32**，依此类推)。</span><span class="sxs-lookup"><span data-stu-id="04536-109">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="04536-110">有关数据提供程序特定的类型化取值函数方法的列表**Datareader**，请参阅<xref:System.Data.OleDb.OleDbDataReader>和<xref:System.Data.SqlClient.SqlDataReader>。</span><span class="sxs-lookup"><span data-stu-id="04536-110">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="04536-111">使用类型化取值函数方法，当您知道基础数据类型可减少检索列值时所需的类型转换量。</span><span class="sxs-lookup"><span data-stu-id="04536-111">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="04536-112">下面的示例循环访问**DataReader**对象并从每个行返回两个列。</span><span class="sxs-lookup"><span data-stu-id="04536-112">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="04536-113">关闭 DataReader</span><span class="sxs-lookup"><span data-stu-id="04536-113">Closing the DataReader</span></span>  
 <span data-ttu-id="04536-114">始终调用**关闭**方法时使用完**DataReader**对象。</span><span class="sxs-lookup"><span data-stu-id="04536-114">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="04536-115">如果你**命令**包含输出参数或返回值，这些值不是后才可**DataReader**已关闭。</span><span class="sxs-lookup"><span data-stu-id="04536-115">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="04536-116">虽然**DataReader**处于打开状态，**连接**处于独占方式使用**DataReader**。</span><span class="sxs-lookup"><span data-stu-id="04536-116">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="04536-117">不能执行任何命令**连接**，包括创建另一个**DataReader**，直到原始**DataReader**已关闭。</span><span class="sxs-lookup"><span data-stu-id="04536-117">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04536-118">不要调用**关闭**或**Dispose**上**连接**即**DataReader**，或在任何其他托管的对象**Finalize**类的方法。</span><span class="sxs-lookup"><span data-stu-id="04536-118">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="04536-119">在终结器中，仅释放类直接拥有的非托管资源。</span><span class="sxs-lookup"><span data-stu-id="04536-119">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="04536-120">如果您的类不拥有任何非托管的资源，不包括**Finalize**在类定义中的方法。</span><span class="sxs-lookup"><span data-stu-id="04536-120">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="04536-121">有关详细信息，请参阅[垃圾回收](../../../../docs/standard/garbage-collection/index.md)。</span><span class="sxs-lookup"><span data-stu-id="04536-121">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="04536-122">使用 NextResult 检索多个结果集</span><span class="sxs-lookup"><span data-stu-id="04536-122">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="04536-123">如果**DataReader**返回多个结果集，调用**NextResult**方法来循环访问结果按顺序设置。</span><span class="sxs-lookup"><span data-stu-id="04536-123">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="04536-124">以下示例显示 <xref:System.Data.SqlClient.SqlDataReader> 如何使用 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 方法处理两个 SELECT 语句的结果。</span><span class="sxs-lookup"><span data-stu-id="04536-124">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="04536-125">从 DataReader 中获取架构信息</span><span class="sxs-lookup"><span data-stu-id="04536-125">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="04536-126">虽然**DataReader**是打开状态，可以检索有关当前结果集使用的架构信息**GetSchemaTable**方法。</span><span class="sxs-lookup"><span data-stu-id="04536-126">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="04536-127">**GetSchemaTable**返回<xref:System.Data.DataTable>包含行和列包含当前结果集的架构信息填充的对象。</span><span class="sxs-lookup"><span data-stu-id="04536-127">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="04536-128">**DataTable**结果集的每一列中对应一行。</span><span class="sxs-lookup"><span data-stu-id="04536-128">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="04536-129">架构表的每个列都映射到属性中返回的列的结果的行设置，其中**ColumnName**属性名称和列的值是属性的值。</span><span class="sxs-lookup"><span data-stu-id="04536-129">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="04536-130">下面的示例写出的架构信息**DataReader**。</span><span class="sxs-lookup"><span data-stu-id="04536-130">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="04536-131">使用 OLE DB 章节</span><span class="sxs-lookup"><span data-stu-id="04536-131">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="04536-132">分层行集或章节 (OLE DB 类型**DBTYPE_HCHAPTER**，ADO 类型**adChapter**)，可以使用检索<xref:System.Data.OleDb.OleDbDataReader>。</span><span class="sxs-lookup"><span data-stu-id="04536-132">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="04536-133">当包含某章节的查询返回作为**DataReader**，一章中列的形式返回**DataReader** ，并作为公开**DataReader**对象。</span><span class="sxs-lookup"><span data-stu-id="04536-133">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="04536-134">ADO.NET**数据集**还可用于通过使用表之间的父-子关系，表示分层行集。</span><span class="sxs-lookup"><span data-stu-id="04536-134">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="04536-135">有关详细信息，请参阅[数据集、 数据表和数据视图](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)。</span><span class="sxs-lookup"><span data-stu-id="04536-135">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="04536-136">以下代码示例使用 MSDataShape 提供程序来为客户列表中的每个客户生成订单的章节列。</span><span class="sxs-lookup"><span data-stu-id="04536-136">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="04536-137">使用 Oracle REF Cursor 返回结果</span><span class="sxs-lookup"><span data-stu-id="04536-137">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="04536-138">Oracle .NET Framework 数据提供程序支持使用 Oracle REF CURSOR 返回查询结果。</span><span class="sxs-lookup"><span data-stu-id="04536-138">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="04536-139">Oracle REF CURSOR 以 <xref:System.Data.OracleClient.OracleDataReader> 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="04536-139">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="04536-140">可以检索<xref:System.Data.OracleClient.OracleDataReader>对象，表示通过使用 Oracle REF CURSOR<xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="04536-140">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="04536-141">此外可以指定<xref:System.Data.OracleClient.OracleCommand>返回一个或多个 Oracle REF Cursor 作为**SelectCommand**有关<xref:System.Data.OracleClient.OracleDataAdapter>用来填充<xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="04536-141">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="04536-142">若要访问从 Oracle 数据源返回的 REF CURSOR，创建<xref:System.Data.OracleClient.OracleCommand>为您的查询，并添加引用到 REF CURSOR 的输出参数<xref:System.Data.OracleClient.OracleCommand.Parameters>的集合在<xref:System.Data.OracleClient.OracleCommand>。</span><span class="sxs-lookup"><span data-stu-id="04536-142">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="04536-143">该参数的名称必须与查询中的 REF CURSOR 参数名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="04536-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="04536-144">参数的类型设置<xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="04536-144">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="04536-145"><xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType>方法将<xref:System.Data.OracleClient.OracleCommand>返回<xref:System.Data.OracleClient.OracleDataReader>的 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="04536-145">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="04536-146">如果你<xref:System.Data.OracleClient.OracleCommand>返回多个 REF CURSOR，添加多个输出参数。</span><span class="sxs-lookup"><span data-stu-id="04536-146">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="04536-147">可以通过调用访问不同的 REF Cursor<xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="04536-147">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="04536-148">在调用<xref:System.Data.OracleClient.OracleCommand.ExecuteReader>返回<xref:System.Data.OracleClient.OracleDataReader>引用第一个 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="04536-148">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="04536-149">然后，可以调用<xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType>方法访问随后的 REF Cursor。</span><span class="sxs-lookup"><span data-stu-id="04536-149">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="04536-150">尽管中的参数在<xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType>集合匹配 REF CURSOR 输出参数的名称，<xref:System.Data.OracleClient.OracleDataReader>添加到中的顺序访问这些<xref:System.Data.OracleClient.OracleCommand.Parameters>集合。</span><span class="sxs-lookup"><span data-stu-id="04536-150">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="04536-151">例如，请看下面这个 Oracle 包和包正文。</span><span class="sxs-lookup"><span data-stu-id="04536-151">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="04536-152">下面的代码创建<xref:System.Data.OracleClient.OracleCommand>类型的两个参数添加从先前的 Oracle 包返回 REF Cursor<xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>到<xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType>集合。</span><span class="sxs-lookup"><span data-stu-id="04536-152">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
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
  
 <span data-ttu-id="04536-153">以下代码将返回上一个命令使用的结果<xref:System.Data.OracleClient.OracleDataReader.Read>并<xref:System.Data.OracleClient.OracleDataReader.NextResult>方法的<xref:System.Data.OracleClient.OracleDataReader>。</span><span class="sxs-lookup"><span data-stu-id="04536-153">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="04536-154">REF CURSOR 参数按顺序返回。</span><span class="sxs-lookup"><span data-stu-id="04536-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="04536-155">下面的示例使用前一命令来填充<xref:System.Data.DataSet>与 Oracle 包的结果。</span><span class="sxs-lookup"><span data-stu-id="04536-155">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
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
>  <span data-ttu-id="04536-156">若要避免**OverflowException**，我们建议你还处理任何从 Oracle NUMBER 类型转换为有效的.NET Framework 类型存储中的值之前<xref:System.Data.DataRow>。</span><span class="sxs-lookup"><span data-stu-id="04536-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="04536-157">可以使用<xref:System.Data.Common.DataAdapter.FillError>事件来确定是否**OverflowException**已发生。</span><span class="sxs-lookup"><span data-stu-id="04536-157">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="04536-158">有关详细信息<xref:System.Data.Common.DataAdapter.FillError>事件，请参阅[处理 DataAdapter 事件](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)。</span><span class="sxs-lookup"><span data-stu-id="04536-158">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04536-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="04536-159">See also</span></span>

- [<span data-ttu-id="04536-160">DataAdapters 和 DataReaders</span><span class="sxs-lookup"><span data-stu-id="04536-160">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="04536-161">命令和参数</span><span class="sxs-lookup"><span data-stu-id="04536-161">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="04536-162">检索数据库架构信息</span><span class="sxs-lookup"><span data-stu-id="04536-162">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [<span data-ttu-id="04536-163">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="04536-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
