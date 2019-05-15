---
title: 从 DataAdapter 填充数据集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3fa0ac7d-e266-4954-bfac-3fbe2f913153
ms.openlocfilehash: c49e810b830ecb7327f400d9ef183f4db9c7d736
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65584565"
---
# <a name="populating-a-dataset-from-a-dataadapter"></a><span data-ttu-id="fd9fb-102">从 DataAdapter 填充数据集</span><span class="sxs-lookup"><span data-stu-id="fd9fb-102">Populating a DataSet from a DataAdapter</span></span>
<span data-ttu-id="fd9fb-103">[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] <xref:System.Data.DataSet>是提供一致关系编程模型独立于数据源的数据的驻留内存表示形式。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-103">The [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model independent of the data source.</span></span> <span data-ttu-id="fd9fb-104">`DataSet` 表示整个数据集，其中包含表、约束和表之间的关系。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-104">The `DataSet` represents a complete set of data that includes tables, constraints, and relationships among the tables.</span></span> <span data-ttu-id="fd9fb-105">由于 `DataSet` 独立于数据源，因此 `DataSet` 可以包含应用程序本地的数据，也可以包含来自多个数据源的数据。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-105">Because the `DataSet` is independent of the data source, a `DataSet` can include data local to the application, and data from multiple data sources.</span></span> <span data-ttu-id="fd9fb-106">与现有数据源的交互通过 `DataAdapter`来控制。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-106">Interaction with existing data sources is controlled through the `DataAdapter`.</span></span>  
  
 <span data-ttu-id="fd9fb-107">`SelectCommand` 的 `DataAdapter` 属性是一个 `Command` 对象，用于从数据源中检索数据。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-107">The `SelectCommand` property of the `DataAdapter` is a `Command` object that retrieves data from the data source.</span></span> <span data-ttu-id="fd9fb-108">`InsertCommand`的 `UpdateCommand`、 `DeleteCommand` 和 `DataAdapter` 属性是 `Command` 对象，用于按照对 `DataSet`中数据的修改来管理对数据源中数据的更新。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-108">The `InsertCommand`, `UpdateCommand`, and `DeleteCommand` properties of the `DataAdapter` are `Command` objects that manage updates to the data in the data source according to modifications made to the data in the `DataSet`.</span></span> <span data-ttu-id="fd9fb-109">中更详细地介绍这些属性[使用 Dataadapter 更新数据源](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-109">These properties are covered in more detail in [Updating Data Sources with DataAdapters](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="fd9fb-110">`Fill` 的 `DataAdapter` 方法用于使用 `DataSet` 的 `SelectCommand` 结果填充 `DataAdapter`。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-110">The `Fill` method of the `DataAdapter` is used to populate a `DataSet` with the results of the `SelectCommand` of the `DataAdapter`.</span></span> <span data-ttu-id="fd9fb-111">`Fill` 将要填充的 `DataSet` 、和 `DataTable` 对象（或要使用从 `DataTable` 中返回的行来填充的 `SelectCommand`的名称）作为它的参数。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-111">`Fill` takes as its arguments a `DataSet` to be populated, and a `DataTable` object, or the name of the `DataTable` to be filled with the rows returned from the `SelectCommand`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd9fb-112">使用 `DataAdapter` 检索表的全部内容会花费些时间，尤其是在表中有很多行时。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-112">Using the `DataAdapter` to retrieve all of a table takes time, especially if there are many rows in the table.</span></span> <span data-ttu-id="fd9fb-113">这是因为访问数据库，定位和处理数据，然后将数据传输到客户端是需要很长时间的。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-113">This is because accessing the database, locating and processing the data, and then transferring the data to the client is time-consuming.</span></span> <span data-ttu-id="fd9fb-114">将表中全部内容提取到客户端还会在服务器上锁定所有行。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-114">Pulling all of the table to the client also locks all of the rows on the server.</span></span> <span data-ttu-id="fd9fb-115">若要提高性能，您可以使用 `WHERE` 子句使返回客户端的行数大为减少。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-115">To improve performance, you can use the `WHERE` clause to greatly reduce the number of rows returned to the client.</span></span> <span data-ttu-id="fd9fb-116">还可以通过只显式列出 `SELECT` 语句要求的列减少返回到客户端的数据量。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-116">You can also reduce the amount of data returned to the client by only explicitly listing required columns in the `SELECT` statement.</span></span> <span data-ttu-id="fd9fb-117">另一种好的变通方法是以批次检索行（例如一次检索几百行），并且在客户端完成当前批次后只检索下一批次。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-117">Another good workaround is to retrieve the rows in batches (such as several hundred rows at a time) and only retrieve the next batch when the client is finished with the current batch.</span></span>  
  
 <span data-ttu-id="fd9fb-118">`Fill` 方法使用 `DataReader` 对象来隐式地返回用于在 `DataSet`中创建表的列名称和类型，以及用于填充 `DataSet`中的表行的数据。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-118">The `Fill` method uses the `DataReader` object implicitly to return the column names and types that are used to create the tables in the `DataSet`, and the data to populate the rows of the tables in the `DataSet`.</span></span> <span data-ttu-id="fd9fb-119">表和列仅在不存在时才创建；否则， `Fill` 将使用现有的 `DataSet` 架构。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-119">Tables and columns are only created if they do not already exist; otherwise `Fill` uses the existing `DataSet` schema.</span></span> <span data-ttu-id="fd9fb-120">列类型创建为.NET Framework 类型中的表根据[ADO.NET 中的数据类型映射](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-120">Column types are created as .NET Framework types according to the tables in [Data Type Mappings in ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md).</span></span> <span data-ttu-id="fd9fb-121">除非数据源中存在主键且 `DataAdapter`**来控制。**`MissingSchemaAction`</span><span class="sxs-lookup"><span data-stu-id="fd9fb-121">Primary keys are not created unless they exist in the data source and `DataAdapter`**.**`MissingSchemaAction`</span></span> <span data-ttu-id="fd9fb-122">设置为 `MissingSchemaAction`**来控制。**`AddWithKey`来控制。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-122">is set to `MissingSchemaAction`**.**`AddWithKey`.</span></span> <span data-ttu-id="fd9fb-123">如果 `Fill` 发现某个表存在主键，对于主键列的值与从数据源返回的行的主键列的值匹配的行，将使用数据源中的数据重写 `DataSet` 中的数据。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-123">If `Fill` finds that a primary key exists for a table, it will overwrite data in the `DataSet` with data from the data source for rows where the primary key column values match those of the row returned from the data source.</span></span> <span data-ttu-id="fd9fb-124">如果未找到任何主键，则将数据追加到 `DataSet`中的表。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-124">If no primary key is found, the data is appended to the tables in the `DataSet`.</span></span> <span data-ttu-id="fd9fb-125">`Fill` 使用填充时可能存在的任何映射`DataSet`(请参阅[DataAdapter 数据表和 DataColumn 映射](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md))。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-125">`Fill` uses any mappings that may exist when you populate the `DataSet` (see [DataAdapter DataTable and DataColumn Mappings](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd9fb-126">如果 `SelectCommand` 返回 OUTER JOIN 的结果，则 `DataAdapter` 不会为生成的 `PrimaryKey` 设置 `DataTable`值。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-126">If the `SelectCommand` returns the results of an OUTER JOIN, the `DataAdapter` does not set a `PrimaryKey` value for the resulting `DataTable`.</span></span> <span data-ttu-id="fd9fb-127">您必须自己定义 `PrimaryKey` 以确保正确解析重复行。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-127">You must define the `PrimaryKey` yourself to make sure that duplicate rows are resolved correctly.</span></span> <span data-ttu-id="fd9fb-128">有关详细信息，请参阅[定义主键](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-128">For more information, see [Defining Primary Keys](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="fd9fb-129">以下代码示例创建了一个 <xref:System.Data.SqlClient.SqlDataAdapter> 实例，使用 Microsoft SQL Server <xref:System.Data.SqlClient.SqlConnection> 数据库的 `Northwind` 并使用客户列表填充 <xref:System.Data.DataTable> 中的 `DataSet` 。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-129">The following code example creates an instance of a <xref:System.Data.SqlClient.SqlDataAdapter> that uses a <xref:System.Data.SqlClient.SqlConnection> to the Microsoft SQL Server `Northwind` database and populates a <xref:System.Data.DataTable> in a `DataSet` with the list of customers.</span></span> <span data-ttu-id="fd9fb-130">向 <xref:System.Data.SqlClient.SqlConnection> 构造函数传递的 SQL 语句和 <xref:System.Data.SqlClient.SqlDataAdapter> 参数用于创建 <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A> 的 <xref:System.Data.SqlClient.SqlDataAdapter>属性。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-130">The SQL statement and <xref:System.Data.SqlClient.SqlConnection> arguments passed to the <xref:System.Data.SqlClient.SqlDataAdapter> constructor are used to create the <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A> property of the <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd9fb-131">示例</span><span class="sxs-lookup"><span data-stu-id="fd9fb-131">Example</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim queryString As String = _  
  "SELECT CustomerID, CompanyName FROM dbo.Customers"  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  queryString, connection)  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
string queryString =   
  "SELECT CustomerID, CompanyName FROM dbo.Customers";  
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
> [!NOTE]
>  <span data-ttu-id="fd9fb-132">此示例中所示的代码不显式打开和关闭 `Connection`。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-132">The code shown in this example does not explicitly open and close the `Connection`.</span></span> <span data-ttu-id="fd9fb-133">如果 `Fill` 方法发现连接尚未打开，它将隐式地打开 `Connection` 正在使用的 `DataAdapter` 。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-133">The `Fill` method implicitly opens the `Connection` that the `DataAdapter` is using if it finds that the connection is not already open.</span></span> <span data-ttu-id="fd9fb-134">如果 `Fill` 已打开连接，则它还将在 `Fill` 完成时关闭连接。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-134">If `Fill` opened the connection, it also closes the connection when `Fill` is finished.</span></span> <span data-ttu-id="fd9fb-135">当处理单一操作（如 `Fill` 或 `Update`）时，这可以简化您的代码。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-135">This can simplify your code when you deal with a single operation such as a `Fill` or an `Update`.</span></span> <span data-ttu-id="fd9fb-136">但是，如果您在执行多项需要打开连接的操作，则可以通过以下方式提高应用程序的性能：显式调用 `Open` 的 `Connection`方法，对数据源执行操作，然后调用 `Close` 的 `Connection`方法。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-136">However, if you are performing multiple operations that require an open connection, you can improve the performance of your application by explicitly calling the `Open` method of the `Connection`, performing the operations against the data source, and then calling the `Close` method of the `Connection`.</span></span> <span data-ttu-id="fd9fb-137">应尝试使数据源的连接打开的时间尽可能短，以便释放资源供其他客户端应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-137">You should try to keep connections to the data source open as briefly as possible to free resources for use by other client applications.</span></span>  
  
## <a name="multiple-result-sets"></a><span data-ttu-id="fd9fb-138">多个结果集</span><span class="sxs-lookup"><span data-stu-id="fd9fb-138">Multiple Result Sets</span></span>  
 <span data-ttu-id="fd9fb-139">如果 `DataAdapter` 遇到多个结果集，则将在 `DataSet`中创建多个表。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-139">If the `DataAdapter` encounters multiple result sets, it creates multiple tables in the `DataSet`.</span></span> <span data-ttu-id="fd9fb-140">这些表的命名方式为默认名称 Table 加上*N*，N 从 0 开始递增，如以 Table0 为第一个表名，依次类推。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-140">The tables are given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span> <span data-ttu-id="fd9fb-141">如果以参数形式向 `Fill` 方法传递表名，则这些表的命名方式为默认名称 TableName 加上*N*，N 从 0 开始递增，如以 TableName0 为第一个表名，依次类推。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-141">If a table name is passed as an argument to the `Fill` method, the tables are given an incremental default name of TableName*N*, starting with "TableName" for TableName0.</span></span>  
  
## <a name="populating-a-dataset-from-multiple-dataadapters"></a><span data-ttu-id="fd9fb-142">从多个 DataAdapter 填充 DataSet</span><span class="sxs-lookup"><span data-stu-id="fd9fb-142">Populating a DataSet from Multiple DataAdapters</span></span>  
 <span data-ttu-id="fd9fb-143">任意数量的`DataAdapter`对象可以一起使用`DataSet`。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-143">Any number of `DataAdapter` objects can be used with a `DataSet`.</span></span> <span data-ttu-id="fd9fb-144">每个 `DataAdapter` 都可用于填充一个或多个 `DataTable` 对象并将更新解析回相关数据源。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-144">Each `DataAdapter` can be used to fill one or more `DataTable` objects and resolve updates back to the relevant data source.</span></span> <span data-ttu-id="fd9fb-145">`DataRelation` 和 `Constraint` 对象可以在本地添加到 `DataSet` ，这样您就可以关联来自不同数据源的数据。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-145">`DataRelation` and `Constraint` objects can be added to the `DataSet` locally, which enables you to relate data from dissimilar data sources.</span></span> <span data-ttu-id="fd9fb-146">例如， `DataSet` 可以包含来自 Microsoft SQL Server 数据库、通过 OLE DB 公开的 IBM DB2 数据库以及对 XML 进行流处理的数据源的数据。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-146">For example, a `DataSet` can contain data from a Microsoft SQL Server database, an IBM DB2 database exposed through OLE DB, and a data source that streams XML.</span></span> <span data-ttu-id="fd9fb-147">一个或多个 `DataAdapter` 对象可以处理与每个数据源的通信。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-147">One or more `DataAdapter` objects can handle communication to each data source.</span></span>  
  
### <a name="example"></a><span data-ttu-id="fd9fb-148">示例</span><span class="sxs-lookup"><span data-stu-id="fd9fb-148">Example</span></span>  
 <span data-ttu-id="fd9fb-149">以下代码示例从 Microsoft SQL Server 上的 `Northwind` 数据库填充客户列表，从存储在 Microsoft Access 2000 上的 `Northwind` 数据库填充订单列表。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-149">The following code example populates a list of customers from the `Northwind` database on Microsoft SQL Server, and a list of orders from the `Northwind` database stored in Microsoft Access 2000.</span></span> <span data-ttu-id="fd9fb-150">已填充的表通过 `DataRelation`相关联，这样，客户列表将与相应客户的订单一起显示出来。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-150">The filled tables are related with a `DataRelation`, and the list of customers is then displayed with the orders for that customer.</span></span> <span data-ttu-id="fd9fb-151">有关详细信息`DataRelation`对象，请参阅[添加 Datarelation](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)并[导航 Datarelation](../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md)。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-151">For more information about `DataRelation` objects, see [Adding DataRelations](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md) and [Navigating DataRelations](../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md).</span></span>  
  
```vb  
' Assumes that customerConnection is a valid SqlConnection object.  
' Assumes that orderConnection is a valid OleDbConnection object.  
Dim custAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers", customerConnection)  
  
Dim ordAdapter As OleDbDataAdapter = New OleDbDataAdapter( _  
  "SELECT * FROM Orders", orderConnection)  
  
Dim customerOrders As DataSet = New DataSet()  
custAdapter.Fill(customerOrders, "Customers")  
ordAdapter.Fill(customerOrders, "Orders")  
  
Dim relation As DataRelation = _  
  customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustomerID"), _   
  customerOrders.Tables("Orders").Columns("CustomerID"))  
  
Dim pRow, cRow As DataRow  
For Each pRow In customerOrders.Tables("Customers").Rows  
  Console.WriteLine(pRow("CustomerID").ToString())  
  
  For Each cRow In pRow.GetChildRows(relation)  
    Console.WriteLine(vbTab & cRow("OrderID").ToString())  
  Next  
Next  
```  
  
```csharp  
// Assumes that customerConnection is a valid SqlConnection object.  
// Assumes that orderConnection is a valid OleDbConnection object.  
SqlDataAdapter custAdapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers", customerConnection);  
OleDbDataAdapter ordAdapter = new OleDbDataAdapter(  
  "SELECT * FROM Orders", orderConnection);  
  
DataSet customerOrders = new DataSet();  
  
custAdapter.Fill(customerOrders, "Customers");  
ordAdapter.Fill(customerOrders, "Orders");  
  
DataRelation relation = customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustomerID"],  
  customerOrders.Tables["Orders"].Columns["CustomerID"]);  
  
foreach (DataRow pRow in customerOrders.Tables["Customers"].Rows)  
{  
  Console.WriteLine(pRow["CustomerID"]);  
   foreach (DataRow cRow in pRow.GetChildRows(relation))  
    Console.WriteLine("\t" + cRow["OrderID"]);  
}  
```  
  
## <a name="sql-server-decimal-type"></a><span data-ttu-id="fd9fb-152">SQL Server Decimal 类型</span><span class="sxs-lookup"><span data-stu-id="fd9fb-152">SQL Server Decimal Type</span></span>  
 <span data-ttu-id="fd9fb-153">默认情况下，`DataSet`使用.NET Framework 数据类型存储数据。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-153">By default, the `DataSet` stores data by using .NET Framework data types.</span></span> <span data-ttu-id="fd9fb-154">对于大多数应用程序，这些类型都提供了一种方便的数据源信息表示形式。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-154">For most applications, these provide a convenient representation of data source information.</span></span> <span data-ttu-id="fd9fb-155">但是，当数据源中的数据类型是 SQL Server decimal 或 numeric 数据类型时，这种表示形式可能会导致问题。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-155">However, this representation may cause a problem when the data type in the data source is a SQL Server decimal or numeric data type.</span></span> <span data-ttu-id="fd9fb-156">.NET Framework`decimal`数据类型的 28 个有效位，最多允许，而 SQL Server`decimal`数据类型则允许 38 个有效位。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-156">The .NET Framework `decimal` data type allows a maximum of 28 significant digits, whereas the SQL Server `decimal` data type allows 38 significant digits.</span></span> <span data-ttu-id="fd9fb-157">如果 `SqlDataAdapter` 在 `Fill` 操作过程中确定 SQL Server `decimal` 字段的精度大于 28 个字符，则不会将当前行添加到 `DataTable`。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-157">If the `SqlDataAdapter` determines during a `Fill` operation that the precision of a SQL Server `decimal` field is larger than 28 characters, the current row is not added to the `DataTable`.</span></span> <span data-ttu-id="fd9fb-158">此时将发生 `FillError` 事件，使您能够确定是否将发生精度损失并作出适当的响应。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-158">Instead the `FillError` event occurs, which enables you to determine whether a loss of precision will occur, and respond appropriately.</span></span> <span data-ttu-id="fd9fb-159">有关详细信息`FillError`事件，请参阅[处理 DataAdapter 事件](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-159">For more information about the `FillError` event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span> <span data-ttu-id="fd9fb-160">若要获取 SQL Server `decimal` 值，还可以使用 <xref:System.Data.SqlClient.SqlDataReader> 对象并调用 <xref:System.Data.SqlClient.SqlDataReader.GetSqlDecimal%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-160">To get the SQL Server `decimal` value, you can also use a <xref:System.Data.SqlClient.SqlDataReader> object and call the <xref:System.Data.SqlClient.SqlDataReader.GetSqlDecimal%2A> method.</span></span>  
  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] <span data-ttu-id="fd9fb-161">2.0 增强了对 <xref:System.Data.SqlTypes> 中的 `DataSet`的支持。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-161">2.0 introduced enhanced support for <xref:System.Data.SqlTypes> in the `DataSet`.</span></span> <span data-ttu-id="fd9fb-162">有关详细信息，请参阅 [SqlTypes and the DataSet](../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md)。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-162">For more information, see [SqlTypes and the DataSet](../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md).</span></span>  
  
## <a name="ole-db-chapters"></a><span data-ttu-id="fd9fb-163">OLE DB 章节</span><span class="sxs-lookup"><span data-stu-id="fd9fb-163">OLE DB Chapters</span></span>  
 <span data-ttu-id="fd9fb-164">分层行集或章节（OLE DB 类型 `DBTYPE_HCHAPTER`、ADO 类型 `adChapter`）可用于填充 `DataSet`的内容。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-164">Hierarchical rowsets, or chapters (OLE DB type `DBTYPE_HCHAPTER`, ADO type `adChapter`) can be used to fill the contents of a `DataSet`.</span></span> <span data-ttu-id="fd9fb-165">当 <xref:System.Data.OleDb.OleDbDataAdapter> 在 `Fill` 操作过程中遇到章节列时，将为章节列创建一个 `DataTable` ，并使用章节中的列和行填充该表。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-165">When the <xref:System.Data.OleDb.OleDbDataAdapter> encounters a chaptered column during a `Fill` operation, a `DataTable` is created for the chaptered column, and that table is filled with the columns and rows from the chapter.</span></span> <span data-ttu-id="fd9fb-166">为章节列创建的表使用父表名称和章节列名称来命名，其形式为“*ParentTableNameChapteredColumnName*”。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-166">The table created for the chaptered column is named by using both the parent table name and the chaptered column name in the form "*ParentTableNameChapteredColumnName*".</span></span> <span data-ttu-id="fd9fb-167">如果 `DataSet` 中已存在与章节列的名称相匹配的表，则将使用章节数据填充当前表。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-167">If a table already exists in the `DataSet` that matches the name of the chaptered column, the current table is filled with the chapter data.</span></span> <span data-ttu-id="fd9fb-168">如果现有表中不存在与章节中的列相匹配的列，则将添加新列。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-168">If there is no column in an existing table that matches a column found in the chapter, a new column is added.</span></span>  
  
 <span data-ttu-id="fd9fb-169">在使用章节列中的数据填充 `DataSet` 中的表之前，将创建分层行集的父表和子表之间的关系，方法是向父表和子表添加一个整数列，将父列设置为自动递增，然后使用两个表中所添加的列来创建 `DataRelation` 。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-169">Before the tables in the `DataSet` are filled with the data in the chaptered columns, a relation is created between the parent and child tables of the hierarchical rowset by adding an integer column to both the parent and child table, setting the parent column to auto-increment, and creating a `DataRelation` using the added columns from both tables.</span></span> <span data-ttu-id="fd9fb-170">所添加的关系使用父表和章节列名称来命名，其形式为“*ParentTableNameChapterColumnName*”。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-170">The added relation is named by using the parent table and chapter column names in the form "*ParentTableNameChapterColumnName*".</span></span>  
  
 <span data-ttu-id="fd9fb-171">请注意，相关列仅存在于 `DataSet`中。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-171">Note that the related column only exists in the `DataSet`.</span></span> <span data-ttu-id="fd9fb-172">如果在随后从数据源进行填充，则将使新行被添加到表中，而不是使更改被并入现有行。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-172">Subsequent fills from the data source can cause new rows to be added to the tables instead of changes being merged into existing rows.</span></span>  
  
 <span data-ttu-id="fd9fb-173">另请注意，如果使用采用 `DataAdapter.Fill` 的 `DataTable`重载，则将只填充该表。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-173">Note also that, if you use the `DataAdapter.Fill` overload that takes a `DataTable`, only that table will be filled.</span></span> <span data-ttu-id="fd9fb-174">仍会将自动递增整数列添加到该表中，但不会创建或填充任何子表并且不会创建任何关系。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-174">An auto-incrementing integer column will still be added to the table, but no child table will be created or filled, and no relation will be created.</span></span>  
  
 <span data-ttu-id="fd9fb-175">以下示例使用 MSDataShape 提供程序为客户列表中的每个客户生成订单的章节列。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-175">The following example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span> <span data-ttu-id="fd9fb-176">然后使用相应数据来填充 `DataSet` 。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-176">A `DataSet` is then filled with the data.</span></span>  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=northwind")  
  
Dim adapter As OleDbDataAdapter = New OleDbDataAdapter( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS Orders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
  
Dim customers As DataSet = New DataSet()  
  
adapter.Fill(customers, "Customers")  
End Using  
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection("Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=(local);Integrated Security=SSPI;Initial Catalog=northwind"))  
{  
OleDbDataAdapter adapter = new OleDbDataAdapter("SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS Orders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
}  
```  
  
 <span data-ttu-id="fd9fb-177">完成 `Fill` 操作后， `DataSet` 包含两个表： `Customers` 和 `CustomersOrders`，其中 `CustomersOrders` 表示章节列。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-177">When the `Fill` operation is complete, the `DataSet` contains two tables: `Customers` and `CustomersOrders`, where `CustomersOrders` represents the chaptered column.</span></span> <span data-ttu-id="fd9fb-178">将名为 `Orders` 的附加列添加到 `Customers` 表中，将名为 `CustomersOrders` 的附加列添加到 `CustomersOrders` 表中。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-178">An additional column named `Orders` is added to the `Customers` table, and an additional column named `CustomersOrders` is added to the `CustomersOrders` table.</span></span> <span data-ttu-id="fd9fb-179">将 `Orders` 表中的 `Customers` 列设置为自动递增。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-179">The `Orders` column in the `Customers` table is set to auto-increment.</span></span> <span data-ttu-id="fd9fb-180">`DataRelation`这个 `CustomersOrders`是通过向上述两个表添加列创建的，其中以 `Customers` 表作为父表。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-180">A `DataRelation`, `CustomersOrders`, is created by using the columns that were added to the tables with `Customers` as the parent table.</span></span> <span data-ttu-id="fd9fb-181">下表显示了一些示例结果。</span><span class="sxs-lookup"><span data-stu-id="fd9fb-181">The following tables show some sample results.</span></span>  
  
### <a name="tablename-customers"></a><span data-ttu-id="fd9fb-182">TableName：Customers</span><span class="sxs-lookup"><span data-stu-id="fd9fb-182">TableName: Customers</span></span>  
  
|<span data-ttu-id="fd9fb-183">CustomerID</span><span class="sxs-lookup"><span data-stu-id="fd9fb-183">CustomerID</span></span>|<span data-ttu-id="fd9fb-184">CompanyName</span><span class="sxs-lookup"><span data-stu-id="fd9fb-184">CompanyName</span></span>|<span data-ttu-id="fd9fb-185">Orders</span><span class="sxs-lookup"><span data-stu-id="fd9fb-185">Orders</span></span>|  
|----------------|-----------------|------------|  
|<span data-ttu-id="fd9fb-186">ALFKI</span><span class="sxs-lookup"><span data-stu-id="fd9fb-186">ALFKI</span></span>|<span data-ttu-id="fd9fb-187">Alfreds Futterkiste</span><span class="sxs-lookup"><span data-stu-id="fd9fb-187">Alfreds Futterkiste</span></span>|<span data-ttu-id="fd9fb-188">0</span><span class="sxs-lookup"><span data-stu-id="fd9fb-188">0</span></span>|  
|<span data-ttu-id="fd9fb-189">ANATR</span><span class="sxs-lookup"><span data-stu-id="fd9fb-189">ANATR</span></span>|<span data-ttu-id="fd9fb-190">Ana Trujillo Emparedados y helados</span><span class="sxs-lookup"><span data-stu-id="fd9fb-190">Ana Trujillo Emparedados y helados</span></span>|<span data-ttu-id="fd9fb-191">1</span><span class="sxs-lookup"><span data-stu-id="fd9fb-191">1</span></span>|  
  
### <a name="tablename-customersorders"></a><span data-ttu-id="fd9fb-192">TableName：CustomersOrders</span><span class="sxs-lookup"><span data-stu-id="fd9fb-192">TableName: CustomersOrders</span></span>  
  
|<span data-ttu-id="fd9fb-193">CustomerID</span><span class="sxs-lookup"><span data-stu-id="fd9fb-193">CustomerID</span></span>|<span data-ttu-id="fd9fb-194">OrderID</span><span class="sxs-lookup"><span data-stu-id="fd9fb-194">OrderID</span></span>|<span data-ttu-id="fd9fb-195">CustomersOrders</span><span class="sxs-lookup"><span data-stu-id="fd9fb-195">CustomersOrders</span></span>|  
|----------------|-------------|---------------------|  
|<span data-ttu-id="fd9fb-196">ALFKI</span><span class="sxs-lookup"><span data-stu-id="fd9fb-196">ALFKI</span></span>|<span data-ttu-id="fd9fb-197">10643</span><span class="sxs-lookup"><span data-stu-id="fd9fb-197">10643</span></span>|<span data-ttu-id="fd9fb-198">0</span><span class="sxs-lookup"><span data-stu-id="fd9fb-198">0</span></span>|  
|<span data-ttu-id="fd9fb-199">ALFKI</span><span class="sxs-lookup"><span data-stu-id="fd9fb-199">ALFKI</span></span>|<span data-ttu-id="fd9fb-200">10692</span><span class="sxs-lookup"><span data-stu-id="fd9fb-200">10692</span></span>|<span data-ttu-id="fd9fb-201">0</span><span class="sxs-lookup"><span data-stu-id="fd9fb-201">0</span></span>|  
|<span data-ttu-id="fd9fb-202">ANATR</span><span class="sxs-lookup"><span data-stu-id="fd9fb-202">ANATR</span></span>|<span data-ttu-id="fd9fb-203">10308</span><span class="sxs-lookup"><span data-stu-id="fd9fb-203">10308</span></span>|<span data-ttu-id="fd9fb-204">1</span><span class="sxs-lookup"><span data-stu-id="fd9fb-204">1</span></span>|  
|<span data-ttu-id="fd9fb-205">ANATR</span><span class="sxs-lookup"><span data-stu-id="fd9fb-205">ANATR</span></span>|<span data-ttu-id="fd9fb-206">10625</span><span class="sxs-lookup"><span data-stu-id="fd9fb-206">10625</span></span>|<span data-ttu-id="fd9fb-207">1</span><span class="sxs-lookup"><span data-stu-id="fd9fb-207">1</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd9fb-208">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd9fb-208">See also</span></span>

- [<span data-ttu-id="fd9fb-209">DataAdapters 和 DataReaders</span><span class="sxs-lookup"><span data-stu-id="fd9fb-209">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="fd9fb-210">ADO.NET 中的数据类型映射</span><span class="sxs-lookup"><span data-stu-id="fd9fb-210">Data Type Mappings in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="fd9fb-211">使用 DbDataAdapter 修改数据</span><span class="sxs-lookup"><span data-stu-id="fd9fb-211">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)
- [<span data-ttu-id="fd9fb-212">多重活动结果集 (MARS)</span><span class="sxs-lookup"><span data-stu-id="fd9fb-212">Multiple Active Result Sets (MARS)</span></span>](../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)
- [<span data-ttu-id="fd9fb-213">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="fd9fb-213">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
