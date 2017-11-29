---
title: "表值参数"
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
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 47009516d4118fec1a075a2dbccfa747f9a63131
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="table-valued-parameters"></a><span data-ttu-id="ca867-102">表值参数</span><span class="sxs-lookup"><span data-stu-id="ca867-102">Table-Valued Parameters</span></span>
<span data-ttu-id="ca867-103">表值参数提供一种将客户端应用程序中的多行数据封送到 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 的简单方式，而不需要多次往返或特殊服务器端逻辑来处理数据。</span><span class="sxs-lookup"><span data-stu-id="ca867-103">Table-valued parameters provide an easy way to marshal multiple rows of data from a client application to [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] without requiring multiple round trips or special server-side logic for processing the data.</span></span> <span data-ttu-id="ca867-104">您可以使用表值参数来包装客户端应用程序中的数据行，并使用单个参数化命令将数据发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="ca867-104">You can use table-valued parameters to encapsulate rows of data in a client application and send the data to the server in a single parameterized command.</span></span> <span data-ttu-id="ca867-105">传入的数据行存储在一个表变量中，然后您可以通过使用 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 对该表变量进行操作。</span><span class="sxs-lookup"><span data-stu-id="ca867-105">The incoming data rows are stored in a table variable that can then be operated on by using [!INCLUDE[tsql](../../../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ca867-106">可以使用标准的 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] SELECT 语句来访问表值参数中的列值。</span><span class="sxs-lookup"><span data-stu-id="ca867-106">Column values in table-valued parameters can be accessed using standard [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] SELECT statements.</span></span> <span data-ttu-id="ca867-107">表值参数为强类型，其结构会自动进行验证。</span><span class="sxs-lookup"><span data-stu-id="ca867-107">Table-valued parameters are strongly typed and their structure is automatically validated.</span></span> <span data-ttu-id="ca867-108">表值参数的大小仅受服务器内存的限制。</span><span class="sxs-lookup"><span data-stu-id="ca867-108">The size of table-valued parameters is limited only by server memory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca867-109">无法在表值参数中返回数据。</span><span class="sxs-lookup"><span data-stu-id="ca867-109">You cannot return data in a table-valued parameter.</span></span> <span data-ttu-id="ca867-110">表值参数是只可输入的参数；不支持 OUTPUT 关键字。</span><span class="sxs-lookup"><span data-stu-id="ca867-110">Table-valued parameters are input-only; the OUTPUT keyword is not supported.</span></span>  
  
 <span data-ttu-id="ca867-111">有关表值参数的更多信息，请参见下列资源。</span><span class="sxs-lookup"><span data-stu-id="ca867-111">For more information about table-valued parameters, see the following resources.</span></span>  
  
|<span data-ttu-id="ca867-112">资源</span><span class="sxs-lookup"><span data-stu-id="ca867-112">Resource</span></span>|<span data-ttu-id="ca867-113">描述</span><span class="sxs-lookup"><span data-stu-id="ca867-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="ca867-114">[表值参数 （数据库引擎）](http://go.microsoft.com/fwlink/?LinkId=98363)中[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]联机丛书</span><span class="sxs-lookup"><span data-stu-id="ca867-114">[Table-Valued Parameters (Database Engine)](http://go.microsoft.com/fwlink/?LinkId=98363) in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online</span></span>|<span data-ttu-id="ca867-115">说明如何创建和使用表值参数。</span><span class="sxs-lookup"><span data-stu-id="ca867-115">Describes how to create and use table-valued parameters.</span></span>|  
|<span data-ttu-id="ca867-116">[用户定义的表类型](http://go.microsoft.com/fwlink/?LinkId=98364)中[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]联机丛书</span><span class="sxs-lookup"><span data-stu-id="ca867-116">[User-Defined Table Types](http://go.microsoft.com/fwlink/?LinkId=98364) in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online</span></span>|<span data-ttu-id="ca867-117">说明用于声明表值参数的用户定义的表类型。</span><span class="sxs-lookup"><span data-stu-id="ca867-117">Describes user-defined table types that are used to declare table-valued parameters.</span></span>|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a><span data-ttu-id="ca867-118">在 SQL Server 的早期版本中传递多行</span><span class="sxs-lookup"><span data-stu-id="ca867-118">Passing Multiple Rows in Previous Versions of SQL Server</span></span>  
 <span data-ttu-id="ca867-119">在 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2008 中引入表值参数之前，用于将多行数据传递到存储过程或参数化 SQL 命令的选项受到限制。</span><span class="sxs-lookup"><span data-stu-id="ca867-119">Before table-valued parameters were introduced to [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2008, the options for passing multiple rows of data to a stored procedure or a parameterized SQL command were limited.</span></span> <span data-ttu-id="ca867-120">开发人员可以选择使用以下选项，将多个行传递给服务器：</span><span class="sxs-lookup"><span data-stu-id="ca867-120">A developer could choose from the following options for passing multiple rows to the server:</span></span>  
  
-   <span data-ttu-id="ca867-121">使用一系列单个参数表示多个数据列和行中的值。</span><span class="sxs-lookup"><span data-stu-id="ca867-121">Use a series of individual parameters to represent the values in multiple columns and rows of data.</span></span> <span data-ttu-id="ca867-122">使用此方法传递的数据量受所允许的参数数量的限制。</span><span class="sxs-lookup"><span data-stu-id="ca867-122">The amount of data that can be passed by using this method is limited by the number of parameters allowed.</span></span> [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="ca867-123"> 过程最多可以有 2100 个参数。</span><span class="sxs-lookup"><span data-stu-id="ca867-123"> procedures can have, at most, 2100 parameters.</span></span> <span data-ttu-id="ca867-124">必须使用服务器端逻辑才能将这些单个值组合到表变量或临时表中以进行处理。</span><span class="sxs-lookup"><span data-stu-id="ca867-124">Server-side logic is required to assemble these individual values into a table variable or a temporary table for processing.</span></span>  
  
-   <span data-ttu-id="ca867-125">将多个数据值捆绑到分隔字符串或 XML 文档中，然后将这些文本值传递给过程或语句。</span><span class="sxs-lookup"><span data-stu-id="ca867-125">Bundle multiple data values into delimited strings or XML documents and then pass those text values to a procedure or statement.</span></span> <span data-ttu-id="ca867-126">此过程要求相应的过程或语句包括验证数据结构和取消捆绑值所需的逻辑。</span><span class="sxs-lookup"><span data-stu-id="ca867-126">This requires the procedure or statement to include the logic necessary for validating the data structures and unbundling the values.</span></span>  
  
-   <span data-ttu-id="ca867-127">针对影响多个行的数据修改创建一系列的单个 SQL 语句，例如通过调用 `Update` 的 <xref:System.Data.SqlClient.SqlDataAdapter> 方法创建的内容。</span><span class="sxs-lookup"><span data-stu-id="ca867-127">Create a series of individual SQL statements for data modifications that affect multiple rows, such as those created by calling the `Update` method of a <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="ca867-128">可将更改单独提交给服务器，也可以将其作为组进行批处理。</span><span class="sxs-lookup"><span data-stu-id="ca867-128">Changes can be submitted to the server individually or batched into groups.</span></span> <span data-ttu-id="ca867-129">不过，即使是以包含多个语句的批处理形式提交的，每个语句在服务器上还是会单独执行。</span><span class="sxs-lookup"><span data-stu-id="ca867-129">However, even when submitted in batches that contain multiple statements, each statement is executed separately on the server.</span></span>  
  
-   <span data-ttu-id="ca867-130">使用 `bcp` 实用工具程序或 <xref:System.Data.SqlClient.SqlBulkCopy> 对象将很多行数据加载到表中。</span><span class="sxs-lookup"><span data-stu-id="ca867-130">Use the `bcp` utility program or the <xref:System.Data.SqlClient.SqlBulkCopy> object to load many rows of data into a table.</span></span> <span data-ttu-id="ca867-131">尽管这项技术非常有效，但不支持服务器端处理，除非将数据加载到临时表或表变量中。</span><span class="sxs-lookup"><span data-stu-id="ca867-131">Although this technique is very efficient, it does not support server-side processing unless the data is loaded into a temporary table or table variable.</span></span>  
  
## <a name="creating-table-valued-parameter-types"></a><span data-ttu-id="ca867-132">创建表值参数类型</span><span class="sxs-lookup"><span data-stu-id="ca867-132">Creating Table-Valued Parameter Types</span></span>  
 <span data-ttu-id="ca867-133">表值参数以通过使用 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] CREATE TYPE 语句定义的强类型表结构为基础。</span><span class="sxs-lookup"><span data-stu-id="ca867-133">Table-valued parameters are based on strongly-typed table structures that are defined by using [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] CREATE TYPE statements.</span></span> <span data-ttu-id="ca867-134">您必须先在 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 中创建一个表类型并定义结构，才能在客户端应用程序中使用表值参数。</span><span class="sxs-lookup"><span data-stu-id="ca867-134">You have to create a table type and define the structure in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] before you can use table-valued parameters in your client applications.</span></span> <span data-ttu-id="ca867-135">有关创建表类型的详细信息，请参阅[用户定义表类型](http://go.microsoft.com/fwlink/?LinkID=98364)中[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]联机丛书。</span><span class="sxs-lookup"><span data-stu-id="ca867-135">For more information about creating table types, see [User-Defined Table Types](http://go.microsoft.com/fwlink/?LinkID=98364) in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="ca867-136">下面的语句可创建一个名为 CategoryTableType 的表类型，其中包括 CategoryID 和 CategoryName 列：</span><span class="sxs-lookup"><span data-stu-id="ca867-136">The following statement creates a table type named CategoryTableType that consists of CategoryID and CategoryName columns:</span></span>  
  
```  
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 <span data-ttu-id="ca867-137">创建一个表类型后，您可以基于该类型声明表值参数。</span><span class="sxs-lookup"><span data-stu-id="ca867-137">After you create a table type, you can declare table-valued parameters based on that type.</span></span> <span data-ttu-id="ca867-138">下面的 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 片段演示如何在存储过程定义中声明表值参数。</span><span class="sxs-lookup"><span data-stu-id="ca867-138">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] fragment demonstrates how to declare a table-valued parameter in a stored procedure definition.</span></span> <span data-ttu-id="ca867-139">请注意，声明表值参数时需要使用 READONLY 关键字。</span><span class="sxs-lookup"><span data-stu-id="ca867-139">Note that the READONLY keyword is required for declaring a table-valued parameter.</span></span>  
  
```  
CREATE PROCEDURE usp_UpdateCategories   
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a><span data-ttu-id="ca867-140">通过表值参数修改数据 (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ca867-140">Modifying Data with Table-Valued Parameters (Transact-SQL)</span></span>  
 <span data-ttu-id="ca867-141">表值参数可在基于集的数据修改中使用，这些数据修改可通过执行单个语句影响多个行。</span><span class="sxs-lookup"><span data-stu-id="ca867-141">Table-valued parameters can be used in set-based data modifications that affect multiple rows by executing a single statement.</span></span> <span data-ttu-id="ca867-142">例如，您可以选择表值参数中的所有行，然后将它们插入到数据库表中；您也可以通过将表值参数联接到要更新的表中来创建更新语句。</span><span class="sxs-lookup"><span data-stu-id="ca867-142">For example, you can select all the rows in a table-valued parameter and insert them into a database table, or you can create an update statement by joining a table-valued parameter to the table you want to update.</span></span>  
  
 <span data-ttu-id="ca867-143">下面的 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] UPDATE 语句演示如何通过将表值参数联接到 Categories 表来使用它。</span><span class="sxs-lookup"><span data-stu-id="ca867-143">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] UPDATE statement demonstrates how to use a table-valued parameter by joining it to the Categories table.</span></span> <span data-ttu-id="ca867-144">在 FROM 子句中将表值参数与 JOIN 一起使用时，您还必须为其提供一个别名，如此处所示，表值参数的别名为“ec”：</span><span class="sxs-lookup"><span data-stu-id="ca867-144">When you use a table-valued parameter with a JOIN in a FROM clause, you must also alias it, as shown here, where the table-valued parameter is aliased as "ec":</span></span>  
  
```  
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 <span data-ttu-id="ca867-145">此 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 示例演示如何从表值参数中选择行以在单个基于集的操作中执行 INSERT。</span><span class="sxs-lookup"><span data-stu-id="ca867-145">This [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] example demonstrates how to select rows from a table-valued parameter to perform an INSERT in a single set-based operation.</span></span>  
  
```  
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a><span data-ttu-id="ca867-146">表值参数的限制</span><span class="sxs-lookup"><span data-stu-id="ca867-146">Limitations of Table-Valued Parameters</span></span>  
 <span data-ttu-id="ca867-147">以下是表值参数的几个限制：</span><span class="sxs-lookup"><span data-stu-id="ca867-147">There are several limitations to table-valued parameters:</span></span>  
  
-   <span data-ttu-id="ca867-148">不能将传递到表值参数[CLR 用户定义函数](http://msdn.microsoft.com/library/ms131077.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ca867-148">You cannot pass table-valued parameters to [CLR user-defined functions](http://msdn.microsoft.com/library/ms131077.aspx).</span></span>  
  
-   <span data-ttu-id="ca867-149">只有对表值参数进行索引才能支持 UNIQUE 或 PRIMARY KEY 约束。</span><span class="sxs-lookup"><span data-stu-id="ca867-149">Table-valued parameters can only be indexed to support UNIQUE or PRIMARY KEY constraints.</span></span> [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="ca867-150"> 不维护有关表值参数的统计信息。</span><span class="sxs-lookup"><span data-stu-id="ca867-150"> does not maintain statistics on table-valued parameters.</span></span>  
  
-   <span data-ttu-id="ca867-151">在 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 代码中表值参数是只读的。</span><span class="sxs-lookup"><span data-stu-id="ca867-151">Table-valued parameters are read-only in [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="ca867-152">无法更新表值参数的行中的列值且无法插入或删除行。</span><span class="sxs-lookup"><span data-stu-id="ca867-152">You cannot update the column values in the rows of a table-valued parameter and you cannot insert or delete rows.</span></span> <span data-ttu-id="ca867-153">若要修改传递给表值参数中的存储过程或参数化语句的数据，则必须将数据插入到临时表或表变量中。</span><span class="sxs-lookup"><span data-stu-id="ca867-153">To modify the data that is passed to a stored procedure or parameterized statement in table-valued parameter, you must insert the data into a temporary table or into a table variable.</span></span>  
  
-   <span data-ttu-id="ca867-154">无法使用 ALTER TABLE 语句来修改表值参数的设计。</span><span class="sxs-lookup"><span data-stu-id="ca867-154">You cannot use ALTER TABLE statements to modify the design of table-valued parameters.</span></span>  
  
## <a name="configuring-a-sqlparameter-example"></a><span data-ttu-id="ca867-155">配置 SqlParameter 示例</span><span class="sxs-lookup"><span data-stu-id="ca867-155">Configuring a SqlParameter Example</span></span>  
 <span data-ttu-id="ca867-156"><xref:System.Data.SqlClient>支持填充表值参数从<xref:System.Data.DataTable>，<xref:System.Data.Common.DbDataReader>或如\<<xref:Microsoft.SqlServer.Server.SqlDataRecord>> (<xref:System.Collections.Generic.IEnumerable%601>？ qualifyHint = False 自动升级 = True) 对象。</span><span class="sxs-lookup"><span data-stu-id="ca867-156"><xref:System.Data.SqlClient> supports populating table-valued parameters from <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> or System.Collections.Generic.IEnumerable\<<xref:Microsoft.SqlServer.Server.SqlDataRecord>> (<xref:System.Collections.Generic.IEnumerable%601>?qualifyHint=False&autoUpgrade=True) objects.</span></span> <span data-ttu-id="ca867-157">必须通过使用 <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> 的 <xref:System.Data.SqlClient.SqlParameter> 属性指定表值参数的类型名称。</span><span class="sxs-lookup"><span data-stu-id="ca867-157">You must specify a type name for the table-valued parameter by using the <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="ca867-158">`TypeName` 必须与以前在服务器上创建的兼容类型的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="ca867-158">The `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="ca867-159">下面的代码段演示如何配置 <xref:System.Data.SqlClient.SqlParameter> 以插入数据。</span><span class="sxs-lookup"><span data-stu-id="ca867-159">The following code fragment demonstrates how to configure <xref:System.Data.SqlClient.SqlParameter> to insert data.</span></span>  
  
```csharp  
// Configure the command and parameter.  
SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
tvpParam.SqlDbType = SqlDbType.Structured;  
tvpParam.TypeName = "dbo.CategoryTableType";  
```  
  
```vb  
' Configure the command and parameter.  
Dim insertCommand As New SqlCommand(sqlInsert, connection)  
Dim tvpParam As SqlParameter = _  
   insertCommand.Parameters.AddWithValue( _  
  "@tvpNewCategories", addedCategories)  
tvpParam.SqlDbType = SqlDbType.Structured  
tvpParam.TypeName = "dbo.CategoryTableType"  
```  
  
 <span data-ttu-id="ca867-160">您也可以使用从 <xref:System.Data.Common.DbDataReader> 中派生的任何对象，将数据行流处理到表值参数，如本代码段所示：</span><span class="sxs-lookup"><span data-stu-id="ca867-160">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter, as shown in this fragment:</span></span>  
  
```csharp  
// Configure the SqlCommand and table-valued parameter.  
SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
insertCommand.CommandType = CommandType.StoredProcedure;  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", dataReader);  
tvpParam.SqlDbType = SqlDbType.Structured;  
```  
  
```vb  
' Configure the SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  dataReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
```  
  
## <a name="passing-a-table-valued-parameter-to-a-stored-procedure"></a><span data-ttu-id="ca867-161">将表值参数传递给存储过程</span><span class="sxs-lookup"><span data-stu-id="ca867-161">Passing a Table-Valued Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="ca867-162">此示例演示如何将表值参数数据传递给存储过程。</span><span class="sxs-lookup"><span data-stu-id="ca867-162">This example demonstrates how to pass table-valued parameter data to a stored procedure.</span></span> <span data-ttu-id="ca867-163">示例代码通过使用 <xref:System.Data.DataTable> 方法，将已添加的行提取到新的 <xref:System.Data.DataTable.GetChanges%2A> 中。</span><span class="sxs-lookup"><span data-stu-id="ca867-163">The code extracts added rows into a new <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.GetChanges%2A> method.</span></span> <span data-ttu-id="ca867-164">然后，示例代码定义一个 <xref:System.Data.SqlClient.SqlCommand>，并将 <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> 属性设置为 <xref:System.Data.CommandType.StoredProcedure>。</span><span class="sxs-lookup"><span data-stu-id="ca867-164">The code then defines a <xref:System.Data.SqlClient.SqlCommand>, setting the <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> property to <xref:System.Data.CommandType.StoredProcedure>.</span></span> <span data-ttu-id="ca867-165">示例代码通过使用 <xref:System.Data.SqlClient.SqlParameter> 方法对 <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> 进行填充，并将 <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> 设置为 `Structured`。</span><span class="sxs-lookup"><span data-stu-id="ca867-165">The <xref:System.Data.SqlClient.SqlParameter> is populated by using the <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> method and the <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> is set to `Structured`.</span></span> <span data-ttu-id="ca867-166">然后，通过使用 <xref:System.Data.SqlClient.SqlCommand> 方法执行 <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>。</span><span class="sxs-lookup"><span data-stu-id="ca867-166">The <xref:System.Data.SqlClient.SqlCommand> is then executed by using the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection object.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Configure the SqlCommand and SqlParameter.  
  SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
  insertCommand.CommandType = CommandType.StoredProcedure;  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection object.  
Using connection  
   '  Create a DataTable with the modified rows.  
   Dim addedCategories As DataTable = _  
     CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Configure the SqlCommand and SqlParameter.  
   Dim insertCommand As New SqlCommand( _  
     "usp_InsertCategories", connection)  
   insertCommand.CommandType = CommandType.StoredProcedure  
   Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
     "@tvpNewCategories", addedCategories)  
   tvpParam.SqlDbType = SqlDbType.Structured  
  
   '  Execute the command.  
   insertCommand.ExecuteNonQuery()  
End Using  
```  
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a><span data-ttu-id="ca867-167">将表值参数传递给参数化 SQL 语句</span><span class="sxs-lookup"><span data-stu-id="ca867-167">Passing a Table-Valued Parameter to a Parameterized SQL Statement</span></span>  
 <span data-ttu-id="ca867-168">下面的示例演示如何通过使用带有 SELECT 子查询（具有作为数据源的表值参数）的 INSERT 语句将数据插入 dbo.Categories 表中。</span><span class="sxs-lookup"><span data-stu-id="ca867-168">The following example demonstrates how to insert data into the dbo.Categories table by using an INSERT statement with a SELECT subquery that has a table-valued parameter as the data source.</span></span> <span data-ttu-id="ca867-169">将表值参数传递给参数化 SQL 语句时，必须通过使用 <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> 的新 <xref:System.Data.SqlClient.SqlParameter> 属性指定表值参数的类型名称。</span><span class="sxs-lookup"><span data-stu-id="ca867-169">When passing a table-valued parameter to a parameterized SQL statement, you must specify a type name for the table-valued parameter by using the new <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="ca867-170">此 `TypeName` 必须与以前在服务器上创建的兼容类型的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="ca867-170">This `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="ca867-171">此示例中的代码使用 `TypeName` 属性来引用 dbo.CategoryTableType 中定义的类型结构。</span><span class="sxs-lookup"><span data-stu-id="ca867-171">The code in this example uses the `TypeName` property to reference the type structure defined in dbo.CategoryTableType.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca867-172">如果为表值参数中的标识列提供值，则必须为该会话发出 SET IDENTITY_INSERT 语句。</span><span class="sxs-lookup"><span data-stu-id="ca867-172">If you supply a value for an identity column in a table-valued parameter, you must issue the SET IDENTITY_INSERT statement for the session.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Define the INSERT-SELECT statement.  
  string sqlInsert =   
      "INSERT INTO dbo.Categories (CategoryID, CategoryName)"  
      + " SELECT nc.CategoryID, nc.CategoryName"  
      + " FROM @tvpNewCategories AS nc;"  

  // Configure the command and parameter.  
  SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  
  tvpParam.TypeName = "dbo.CategoryTableType";  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
Using connection  
  ' Create a DataTable with the modified rows.  
  Dim addedCategories As DataTable = _  
    CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Define the INSERT-SELECT statement.  
  Dim sqlInsert As String = _  
  "INSERT INTO dbo.Categories (CategoryID, CategoryName)" _  
  & " SELECT nc.CategoryID, nc.CategoryName" _  
  & " FROM @tvpNewCategories AS nc;"  
  
  ' Configure the command and parameter.  
  Dim insertCommand As New SqlCommand(sqlInsert, connection)  
  Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
    "@tvpNewCategories", addedCategories)  
  tvpParam.SqlDbType = SqlDbType.Structured  
  tvpParam.TypeName = "dbo.CategoryTableType"  
  
  ' Execute the query  
  insertCommand.ExecuteNonQuery()  
End Using  
```  
  
## <a name="streaming-rows-with-a-datareader"></a><span data-ttu-id="ca867-173">使用 DataReader 对行进行流处理</span><span class="sxs-lookup"><span data-stu-id="ca867-173">Streaming Rows with a DataReader</span></span>  
 <span data-ttu-id="ca867-174">您也可以使用从 <xref:System.Data.Common.DbDataReader> 中派生的任何对象，将数据行流处理到表值参数。</span><span class="sxs-lookup"><span data-stu-id="ca867-174">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter.</span></span> <span data-ttu-id="ca867-175">下面的代码段演示如何使用 <xref:System.Data.OracleClient.OracleCommand> 和 <xref:System.Data.OracleClient.OracleDataReader> 来检索 Oracle 数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="ca867-175">The following code fragment demonstrates retrieving data from an Oracle database by using an <xref:System.Data.OracleClient.OracleCommand> and an <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="ca867-176">然后，示例代码配置 <xref:System.Data.SqlClient.SqlCommand> 以使用单个输入参数调用存储过程。</span><span class="sxs-lookup"><span data-stu-id="ca867-176">The code then configures a <xref:System.Data.SqlClient.SqlCommand> to invoke a stored procedure with a single input parameter.</span></span> <span data-ttu-id="ca867-177"><xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> 的 <xref:System.Data.SqlClient.SqlParameter> 属性设置为 `Structured`。</span><span class="sxs-lookup"><span data-stu-id="ca867-177">The <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> property of the <xref:System.Data.SqlClient.SqlParameter> is set to `Structured`.</span></span> <span data-ttu-id="ca867-178"><xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> 将 `OracleDataReader` 结果集作为表值参数传递给存储过程。</span><span class="sxs-lookup"><span data-stu-id="ca867-178">The <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> passes the `OracleDataReader` result set to the stored procedure as a table-valued parameter.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection.  
// Retrieve data from Oracle.  
OracleCommand selectCommand = new OracleCommand(  
   "Select CategoryID, CategoryName FROM Categories;",  
   oracleConnection);  
OracleDataReader oracleReader = selectCommand.ExecuteReader(  
   CommandBehavior.CloseConnection);  
  
 // Configure the SqlCommand and table-valued parameter.  
 SqlCommand insertCommand = new SqlCommand(  
   "usp_InsertCategories", connection);  
 insertCommand.CommandType = CommandType.StoredProcedure;  
 SqlParameter tvpParam =  
    insertCommand.Parameters.AddWithValue(  
    "@tvpNewCategories", oracleReader);  
 tvpParam.SqlDbType = SqlDbType.Structured;  
  
 // Execute the command.  
 insertCommand.ExecuteNonQuery();  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
' Retrieve data from Oracle.  
Dim selectCommand As New OracleCommand( _  
  "Select CategoryID, CategoryName FROM Categories;", _  
  oracleConnection)  
Dim oracleReader As OracleDataReader = _  
  selectCommand.ExecuteReader(CommandBehavior.CloseConnection)  
  
' Configure SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  oracleReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
  
' Execute the command.  
insertCommand.ExecuteNonQuery()  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca867-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca867-179">See Also</span></span>  
 [<span data-ttu-id="ca867-180">配置参数和参数数据类型</span><span class="sxs-lookup"><span data-stu-id="ca867-180">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="ca867-181">命令和参数</span><span class="sxs-lookup"><span data-stu-id="ca867-181">Commands and Parameters</span></span>](../../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="ca867-182">DataAdapter 参数</span><span class="sxs-lookup"><span data-stu-id="ca867-182">DataAdapter Parameters</span></span>](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 [<span data-ttu-id="ca867-183">ADO.NET 中的 SQL Server 数据操作</span><span class="sxs-lookup"><span data-stu-id="ca867-183">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [<span data-ttu-id="ca867-184">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="ca867-184">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
