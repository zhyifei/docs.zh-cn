---
title: 单个批量复制操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
ms.openlocfilehash: 8cba2201bf8087633103efe45c5236cab3af0a0e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964744"
---
# <a name="single-bulk-copy-operations"></a><span data-ttu-id="2c4ff-102">单个批量复制操作</span><span class="sxs-lookup"><span data-stu-id="2c4ff-102">Single Bulk Copy Operations</span></span>
<span data-ttu-id="2c4ff-103">执行 SQL Server 批量复制操作最简单的方法就是对数据库执行单次操作。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-103">The simplest approach to performing a SQL Server bulk copy operation is to perform a single operation against a database.</span></span> <span data-ttu-id="2c4ff-104">默认情况下，批量复制操作是作为一个独立的操作执行的：该复制操作以非事务处理方式进行，不可进行回滚。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-104">By default, a bulk copy operation is performed as an isolated operation: the copy operation occurs in a non-transacted way, with no opportunity for rolling it back.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c4ff-105">如果需要在出错时回滚批量复制的全部或部分，可以使用 <xref:System.Data.SqlClient.SqlBulkCopy> 管理的事务，或在现有事务中执行批量复制操作。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-105">If you need to roll back all or part of the bulk copy when an error occurs, you can either use a <xref:System.Data.SqlClient.SqlBulkCopy>-managed transaction, or perform the bulk copy operation within an existing transaction.</span></span> <span data-ttu-id="2c4ff-106">如果连接已 (隐<xref:System.Transactions>式或显式) 登记到**SqlBulkCopy**事务中, 则也可以使用。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-106">**SqlBulkCopy** will also work with <xref:System.Transactions> if the connection is enlisted (implicitly or explicitly) into a **System.Transactions** transaction.</span></span>  
>   
>  <span data-ttu-id="2c4ff-107">有关详细信息, 请参阅[事务和大容量复制操作](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-107">For more information, see [Transaction and Bulk Copy Operations](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).</span></span>  
  
 <span data-ttu-id="2c4ff-108">执行批量复制操作的一般步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="2c4ff-108">The general steps for performing a bulk copy operation are as follows:</span></span>  
  
1. <span data-ttu-id="2c4ff-109">连接到源服务器上并获取要复制的数据。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-109">Connect to the source server and obtain the data to be copied.</span></span> <span data-ttu-id="2c4ff-110">如果可以从 <xref:System.Data.IDataReader> 或 <xref:System.Data.DataTable> 对象检索数据，则这些数据还可能来自其他源。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-110">Data can also come from other sources, if it can be retrieved from an <xref:System.Data.IDataReader> or <xref:System.Data.DataTable> object.</span></span>  
  
2. <span data-ttu-id="2c4ff-111">连接到目标服务器 (除非你希望**SqlBulkCopy**为你建立连接)。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-111">Connect to the destination server (unless you want **SqlBulkCopy** to establish a connection for you).</span></span>  
  
3. <span data-ttu-id="2c4ff-112">创建一个 <xref:System.Data.SqlClient.SqlBulkCopy> 对象，设置任何必要的属性。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-112">Create a <xref:System.Data.SqlClient.SqlBulkCopy> object, setting any necessary properties.</span></span>  
  
4. <span data-ttu-id="2c4ff-113">设置**DestinationTableName**属性以指示大容量插入操作的目标表。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-113">Set the **DestinationTableName** property to indicate the target table for the bulk insert operation.</span></span>  
  
5. <span data-ttu-id="2c4ff-114">调用**WriteToServer**方法之一。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-114">Call one of the **WriteToServer** methods.</span></span>  
  
6. <span data-ttu-id="2c4ff-115">根据需要更新属性并再次调用**WriteToServer** 。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-115">Optionally, update properties and call **WriteToServer** again as necessary.</span></span>  
  
7. <span data-ttu-id="2c4ff-116">调用 <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>，或将批量复制操作包装在 `Using` 语句中。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-116">Call <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>, or wrap the bulk copy operations within a `Using` statement.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="2c4ff-117">我们建议源列和目标列的数据类型匹配。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-117">We recommend that the source and target column data types match.</span></span> <span data-ttu-id="2c4ff-118">如果数据类型不匹配, 则**SqlBulkCopy**会尝试使用所采用<xref:System.Data.SqlClient.SqlParameter.Value%2A>的规则将每个源值转换为目标数据类型。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-118">If the data types do not match, **SqlBulkCopy** attempts to convert each source value to the target data type, using the rules employed by <xref:System.Data.SqlClient.SqlParameter.Value%2A>.</span></span> <span data-ttu-id="2c4ff-119">转换可能会影响性能，还可能会导致意外的错误。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-119">Conversions can affect performance, and also can result in unexpected errors.</span></span> <span data-ttu-id="2c4ff-120">例如，大多数情况下，`Double` 数据类型可以转换为 `Decimal` 数据类型，但是有时就不能。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-120">For example, a `Double` data type can be converted to a `Decimal` data type most of the time, but not always.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c4ff-121">示例</span><span class="sxs-lookup"><span data-stu-id="2c4ff-121">Example</span></span>  
 <span data-ttu-id="2c4ff-122">以下控制台应用程序演示如何使用 <xref:System.Data.SqlClient.SqlBulkCopy> 类加载数据。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-122">The following console application demonstrates how to load data using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="2c4ff-123">在此示例中, <xref:System.Data.SqlClient.SqlDataReader>用于将数据从 SQL Server **AdventureWorks**数据库中的**Product**表复制到同一个数据库中的类似表。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-123">In this example, a <xref:System.Data.SqlClient.SqlDataReader> is used to copy data from the **Production.Product** table in the SQL Server **AdventureWorks** database to a similar table in the same database.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2c4ff-124">除非已按照[大容量复制示例设置](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)中所述创建了工作表, 否则此示例将不会运行。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-124">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span></span> <span data-ttu-id="2c4ff-125">提供此代码是为了演示仅使用**SqlBulkCopy**的语法。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-125">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="2c4ff-126">如果源表和目标表位于同一个 SQL Server 实例中，则使用 Transact-SQL `INSERT … SELECT` 语句复制数据会更加容易、更加迅速。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-126">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
 [!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]  
  
## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a><span data-ttu-id="2c4ff-127">使用 Transact-SQL 和命令类执行批量复制操作</span><span class="sxs-lookup"><span data-stu-id="2c4ff-127">Performing a Bulk Copy Operation Using Transact-SQL and the Command Class</span></span>  
 <span data-ttu-id="2c4ff-128">以下示例说明如何使用 <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> 方法执行 BULK INSERT 语句。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-128">The following example illustrates how to use the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method to execute the BULK INSERT statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c4ff-129">数据源的文件路径相对于服务器。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-129">The file path for the data source is relative to the server.</span></span> <span data-ttu-id="2c4ff-130">要成功执行批量复制操作，服务器进程必须具有对该路径的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2c4ff-130">The server process must have access to that path in order for the bulk copy operation to succeed.</span></span>  
  
```vb  
Using connection As SqlConnection = New SqlConnection(connectionString)  
Dim queryString As String = _  
    "BULK INSERT Northwind.dbo.[Order Details] FROM " & _  
    "'f:\mydata\data.tbl' WITH (FORMATFILE='f:\mydata\data.fmt' )"  
connection.Open()  
SqlCommand command = New SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery()  
End Using  
```  
  
```csharp  
using (SqlConnection connection = New SqlConnection(connectionString))  
{  
string queryString =  "BULK INSERT Northwind.dbo.[Order Details] " +  
    "FROM 'f:\mydata\data.tbl' " +  
    "WITH ( FORMATFILE='f:\mydata\data.fmt' )";  
connection.Open();  
SqlCommand command = new SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c4ff-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c4ff-131">See also</span></span>

- [<span data-ttu-id="2c4ff-132">SQL Server 中的大容量复制操作</span><span class="sxs-lookup"><span data-stu-id="2c4ff-132">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="2c4ff-133">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="2c4ff-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
