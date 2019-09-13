---
title: 在 ADO.NET 中修改大值 (max) 数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
ms.openlocfilehash: 0f029c81dd6ba5cd5202e6e59f33edd7cf8c0b90
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894444"
---
# <a name="modifying-large-value-max-data-in-adonet"></a><span data-ttu-id="9d215-102">在 ADO.NET 中修改大值 (max) 数据</span><span class="sxs-lookup"><span data-stu-id="9d215-102">Modifying Large-Value (max) Data in ADO.NET</span></span>
<span data-ttu-id="9d215-103">大型对象 (LOB) 数据类型是那些超过 8 千字节 (KB) 最大行大小的数据类型。</span><span class="sxs-lookup"><span data-stu-id="9d215-103">Large object (LOB) data types are those that exceed the maximum row size of 8 kilobytes (KB).</span></span> <span data-ttu-id="9d215-104">SQL Server 为 `max`、`varchar` 和 `nvarchar` 数据类型提供了 `varbinary` 说明符以允许存储最大为 2^32 字节的值。</span><span class="sxs-lookup"><span data-stu-id="9d215-104">SQL Server provides a `max` specifier for `varchar`, `nvarchar`, and `varbinary` data types to allow storage of values as large as 2^32 bytes.</span></span> <span data-ttu-id="9d215-105">表列和 Transact-SQL 变量可以指定 `varchar(max)`、`nvarchar(max)` 或 `varbinary(max)` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="9d215-105">Table columns and Transact-SQL variables may specify `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` data types.</span></span> <span data-ttu-id="9d215-106">在 ADO.NET 中，`max` 数据类型可通过 `DataReader` 来提取，并可指定为输入和输出参数值而无需任何特殊处理。</span><span class="sxs-lookup"><span data-stu-id="9d215-106">In ADO.NET, the `max` data types can be fetched by a `DataReader`, and can also be specified as both input and output parameter values without any special handling.</span></span> <span data-ttu-id="9d215-107">对于大型 `varchar` 数据类型，可以增量检索和更新数据。</span><span class="sxs-lookup"><span data-stu-id="9d215-107">For large `varchar` data types, data can be retrieved and updated incrementally.</span></span>  
  
 <span data-ttu-id="9d215-108">可以使用 `max` 数据类型进行比较（作为 Transact-SQL 变量）和进行串联。</span><span class="sxs-lookup"><span data-stu-id="9d215-108">The `max` data types can be used for comparisons, as Transact-SQL variables, and for concatenation.</span></span> <span data-ttu-id="9d215-109">它们还可以用于 SELECT 语句的 DISTINCT、ORDER BY、GROUP BY 子句中，以及用于聚合、联接和子查询中。</span><span class="sxs-lookup"><span data-stu-id="9d215-109">They can also be used in the DISTINCT, ORDER BY, GROUP BY clauses of a SELECT statement as well as in aggregates, joins, and subqueries.</span></span>  
  
 <span data-ttu-id="9d215-110">下表提供指向 SQL Server 联机丛书中的文档的链接。</span><span class="sxs-lookup"><span data-stu-id="9d215-110">The following table provides links to the documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="9d215-111">**SQL Server 联机丛书**</span><span class="sxs-lookup"><span data-stu-id="9d215-111">**SQL Server Books Online**</span></span>  
  
1. [<span data-ttu-id="9d215-112">使用大值数据类型</span><span class="sxs-lookup"><span data-stu-id="9d215-112">Using Large-Value Data Types</span></span>](https://go.microsoft.com/fwlink/?LinkId=120498)  
  
## <a name="large-value-type-restrictions"></a><span data-ttu-id="9d215-113">大值类型限制</span><span class="sxs-lookup"><span data-stu-id="9d215-113">Large-Value Type Restrictions</span></span>  
 <span data-ttu-id="9d215-114">下面的限制适用于 `max` 数据类型，但对于较小的数据类型则不存在此限制：</span><span class="sxs-lookup"><span data-stu-id="9d215-114">The following restrictions apply to the `max` data types, which do not exist for smaller data types:</span></span>  
  
- <span data-ttu-id="9d215-115">`sql_variant` 不能包含大型 `varchar` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="9d215-115">A `sql_variant` cannot contain a large `varchar` data type.</span></span>  
  
- <span data-ttu-id="9d215-116">大型 `varchar` 列不能指定为索引中的键列。</span><span class="sxs-lookup"><span data-stu-id="9d215-116">Large `varchar` columns cannot be specified as a key column in an index.</span></span> <span data-ttu-id="9d215-117">它们可以存在于非聚集索引中包含的列中。</span><span class="sxs-lookup"><span data-stu-id="9d215-117">They are allowed in an included column in a non-clustered index.</span></span>  
  
- <span data-ttu-id="9d215-118">大型 `varchar` 列不能用作分区键列。</span><span class="sxs-lookup"><span data-stu-id="9d215-118">Large `varchar` columns cannot be used as partitioning key columns.</span></span>  
  
## <a name="working-with-large-value-types-in-transact-sql"></a><span data-ttu-id="9d215-119">在 Transact-SQL 中使用大值类型</span><span class="sxs-lookup"><span data-stu-id="9d215-119">Working with Large-Value Types in Transact-SQL</span></span>  
 <span data-ttu-id="9d215-120">Transact-SQL `OPENROWSET` 函数是一个用于连接和访问远程数据的一次性方法。</span><span class="sxs-lookup"><span data-stu-id="9d215-120">The Transact-SQL `OPENROWSET` function is a one-time method of connecting and accessing remote data.</span></span> <span data-ttu-id="9d215-121">它包含从 OLE DB 数据源访问远程数据所需的所有连接信息。</span><span class="sxs-lookup"><span data-stu-id="9d215-121">It includes all of the connection information necessary to access remote data from an OLE DB data source.</span></span> <span data-ttu-id="9d215-122">可以在某一查询的 FROM 子句中像表名称一样引用 `OPENROWSET`。</span><span class="sxs-lookup"><span data-stu-id="9d215-122">`OPENROWSET` can be referenced in the FROM clause of a query as though it were a table name.</span></span> <span data-ttu-id="9d215-123">根据 OLE DB 提供程序的功能，它还可作为 INSERT、UPDATE 或 DELETE 语句的目标表被引用。</span><span class="sxs-lookup"><span data-stu-id="9d215-123">It can also be referenced as the target table of an INSERT, UPDATE, or DELETE statement, subject to the capabilities of the OLE DB provider.</span></span>  
  
 <span data-ttu-id="9d215-124">`OPENROWSET` 功能包含 `BULK` 行集提供程序，通过此提供程序，您可以直接从文件读取数据而不必将数据加载到目标表</span><span class="sxs-lookup"><span data-stu-id="9d215-124">The `OPENROWSET` function includes the `BULK` rowset provider, which allows you to read data directly from a file without loading the data into a target table.</span></span> <span data-ttu-id="9d215-125">这使您可以在简单的 INSERT SELECT 语句中使用 `OPENROWSET`。</span><span class="sxs-lookup"><span data-stu-id="9d215-125">This enables you to use `OPENROWSET` in a simple INSERT SELECT statement.</span></span>  
  
 <span data-ttu-id="9d215-126">选项`OPENROWSET BULK`参数提供对在何处开始和结束读取数据、如何处理错误以及如何解释数据的有效控制。</span><span class="sxs-lookup"><span data-stu-id="9d215-126">The `OPENROWSET BULK` option arguments provide significant control over where to begin and end reading data, how to deal with errors, and how data is interpreted.</span></span> <span data-ttu-id="9d215-127">例如，可以指定将数据文件作为 `varbinary`、`varchar` 或 `nvarchar` 类型的单行单列行集合进行读取。</span><span class="sxs-lookup"><span data-stu-id="9d215-127">For example, you can specify that the data file be read as a single-row, single-column rowset of type `varbinary`, `varchar`, or `nvarchar`.</span></span> <span data-ttu-id="9d215-128">有关完整语法和选项，请参见 SQL Server 联机图书。</span><span class="sxs-lookup"><span data-stu-id="9d215-128">For the complete syntax and options, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="9d215-129">下面的示例将一幅照片插入 AdventureWorks 示例数据库的 ProductPhoto 表中。</span><span class="sxs-lookup"><span data-stu-id="9d215-129">The following example inserts a photo into the ProductPhoto table in the AdventureWorks sample database.</span></span> <span data-ttu-id="9d215-130">使用`BULK OPENROWSET`提供程序时，即使不将值插入每个列中，也必须提供列的命名列表。</span><span class="sxs-lookup"><span data-stu-id="9d215-130">When using the `BULK OPENROWSET` provider, you must supply the named list of columns even if you aren't inserting values into every column.</span></span> <span data-ttu-id="9d215-131">在本例中，主键定义为标识列，并可从列的列表中省略。</span><span class="sxs-lookup"><span data-stu-id="9d215-131">The primary key in this case is defined as an identity column, and may be omitted from the column list.</span></span> <span data-ttu-id="9d215-132">请注意，您还必须在 `OPENROWSET` 语句的末尾提供一个相关名称，在本例中该名称是 ThumbnailPhoto。</span><span class="sxs-lookup"><span data-stu-id="9d215-132">Note that you must also supply a correlation name at the end of the `OPENROWSET` statement, which in this case is ThumbnailPhoto.</span></span> <span data-ttu-id="9d215-133">该名称与文件要加载到的 `ProductPhoto` 表中的列关联。</span><span class="sxs-lookup"><span data-stu-id="9d215-133">This correlates with the column in the `ProductPhoto` table into which the file is being loaded.</span></span>  
  
```sql  
INSERT Production.ProductPhoto (  
    ThumbnailPhoto,   
    ThumbnailPhotoFilePath,   
    LargePhoto,   
    LargePhotoFilePath)  
SELECT ThumbnailPhoto.*, null, null, N'tricycle_pink.gif'  
FROM OPENROWSET   
    (BULK 'c:\images\tricycle.jpg', SINGLE_BLOB) ThumbnailPhoto  
```  
  
## <a name="updating-data-using-update-write"></a><span data-ttu-id="9d215-134">使用 UPDATE .WRITE 更新数据</span><span class="sxs-lookup"><span data-stu-id="9d215-134">Updating Data Using UPDATE .WRITE</span></span>  
 <span data-ttu-id="9d215-135">Transact-SQL UPDATE 语句具有新的 WRITE 语法，用于修改 `varchar(max)`、`nvarchar(max)` 或 `varbinary(max)` 列的内容。</span><span class="sxs-lookup"><span data-stu-id="9d215-135">The Transact-SQL UPDATE statement has new WRITE syntax for modifying the contents of `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` columns.</span></span> <span data-ttu-id="9d215-136">它允许您对数据执行部分更新。</span><span class="sxs-lookup"><span data-stu-id="9d215-136">This allows you to perform partial updates of the data.</span></span> <span data-ttu-id="9d215-137">此处所示的 UPDATE .WRITE 语法为缩写形式：</span><span class="sxs-lookup"><span data-stu-id="9d215-137">The UPDATE .WRITE syntax is shown here in abbreviated form:</span></span>  
  
 <span data-ttu-id="9d215-138">UPDATE</span><span class="sxs-lookup"><span data-stu-id="9d215-138">UPDATE</span></span>  
  
 <span data-ttu-id="9d215-139">{ *\<object>* }</span><span class="sxs-lookup"><span data-stu-id="9d215-139">{ *\<object>* }</span></span>  
  
 <span data-ttu-id="9d215-140">SET</span><span class="sxs-lookup"><span data-stu-id="9d215-140">SET</span></span>  
  
 <span data-ttu-id="9d215-141">{ *column_name* = { .WRITE ( *expression* , @Offset , @Length ) }</span><span class="sxs-lookup"><span data-stu-id="9d215-141">{ *column_name* = { .WRITE ( *expression* , @Offset , @Length ) }</span></span>  
  
 <span data-ttu-id="9d215-142">WRITE 方法指定将修改*column_name*的值的一部分。</span><span class="sxs-lookup"><span data-stu-id="9d215-142">The WRITE method specifies that a section of the value of the *column_name* will be modified.</span></span> <span data-ttu-id="9d215-143">表达式是将复制到*column_name*中的值， `@Offset`是将`@Length`写入表达式的开始点，而参数是列中的节的长度。</span><span class="sxs-lookup"><span data-stu-id="9d215-143">The expression is the value that will be copied to the *column_name*, the `@Offset` is the beginning point at which the expression will be written, and the `@Length` argument is the length of the section in the column.</span></span>  
  
|<span data-ttu-id="9d215-144">如果</span><span class="sxs-lookup"><span data-stu-id="9d215-144">If</span></span>|<span data-ttu-id="9d215-145">Then</span><span class="sxs-lookup"><span data-stu-id="9d215-145">Then</span></span>|  
|--------|----------|  
|<span data-ttu-id="9d215-146">表达式设置为 NULL</span><span class="sxs-lookup"><span data-stu-id="9d215-146">The expression is set to NULL</span></span>|<span data-ttu-id="9d215-147">`@Length`将被忽略，并且*column_name*中的值将在指定`@Offset`的处截断。</span><span class="sxs-lookup"><span data-stu-id="9d215-147">`@Length` is ignored and the value in *column_name* is truncated at the specified `@Offset`.</span></span>|  
|<span data-ttu-id="9d215-148">`@Offset`为 NULL</span><span class="sxs-lookup"><span data-stu-id="9d215-148">`@Offset` is NULL</span></span>|<span data-ttu-id="9d215-149">更新操作将表达式追加到现有*column_name*值的末尾，并`@Length`将其忽略。</span><span class="sxs-lookup"><span data-stu-id="9d215-149">The update operation appends the expression at the end of the existing *column_name* value and `@Length` is ignored.</span></span>|  
|<span data-ttu-id="9d215-150">`@Offset` 大于 column_name 值的长度</span><span class="sxs-lookup"><span data-stu-id="9d215-150">`@Offset` is greater than the length of the column_name value</span></span>|<span data-ttu-id="9d215-151">SQL Server 返回一个错误。</span><span class="sxs-lookup"><span data-stu-id="9d215-151">SQL Server returns an error.</span></span>|  
|<span data-ttu-id="9d215-152">`@Length`为 NULL</span><span class="sxs-lookup"><span data-stu-id="9d215-152">`@Length` is NULL</span></span>|<span data-ttu-id="9d215-153">更新操作移除从 `@Offset` 到 `column_name` 值末尾的所有数据。</span><span class="sxs-lookup"><span data-stu-id="9d215-153">The update operation removes all data from `@Offset` to the end of the `column_name` value.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="9d215-154">`@Offset` 和 `@Length` 都不能是负数。</span><span class="sxs-lookup"><span data-stu-id="9d215-154">Neither `@Offset` nor `@Length` can be a negative number.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d215-155">示例</span><span class="sxs-lookup"><span data-stu-id="9d215-155">Example</span></span>  
 <span data-ttu-id="9d215-156">此 Transact-SQL 示例更新 DocumentSummary（AdventureWorks 数据库的 Document 表中的 `nvarchar(max)` 列）中的部分值。</span><span class="sxs-lookup"><span data-stu-id="9d215-156">This Transact-SQL example updates a partial value in DocumentSummary, an `nvarchar(max)` column in the Document table in the AdventureWorks database.</span></span> <span data-ttu-id="9d215-157">通过指定替换单词、现有数据中要替换的单词的开始位置（偏移量）以及要替换的字符数（长度），单词“components”将被替换为“features”。</span><span class="sxs-lookup"><span data-stu-id="9d215-157">The word 'components' is replaced by the word 'features' by specifying the replacement word, the beginning location (offset) of the word to be replaced in the existing data, and the number of characters to be replaced (length).</span></span> <span data-ttu-id="9d215-158">该示例在 UPDATE 语句之前和之后都包含 SELECT 语句以便比较结果。</span><span class="sxs-lookup"><span data-stu-id="9d215-158">The example includes SELECT statements before and after the UPDATE statement to compare results.</span></span>  
  
```sql
USE AdventureWorks;  
GO  
--View the existing value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety components of your bicycle.  
  
--Modify a single word in the DocumentSummary column  
UPDATE Production.Document  
SET DocumentSummary .WRITE (N'features',28,10)  
WHERE DocumentID = 3 ;  
GO   
--View the modified value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety features of your bicycle.  
```  
  
## <a name="working-with-large-value-types-in-adonet"></a><span data-ttu-id="9d215-159">在 ADO.NET 中使用大值类型</span><span class="sxs-lookup"><span data-stu-id="9d215-159">Working with Large-Value Types in ADO.NET</span></span>  
 <span data-ttu-id="9d215-160">可以通过将大值类型<xref:System.Data.SqlClient.SqlParameter>指定为<xref:System.Data.SqlClient.SqlDataReader>中的对象以返回结果集<xref:System.Data.SqlClient.SqlDataAdapter> ，或者`DataSet` / `DataTable`使用填充来处理 ADO.NET 中的大值类型。</span><span class="sxs-lookup"><span data-stu-id="9d215-160">You can work with large value types in ADO.NET by specifying large value types as <xref:System.Data.SqlClient.SqlParameter> objects in a <xref:System.Data.SqlClient.SqlDataReader> to return a result set, or by using a <xref:System.Data.SqlClient.SqlDataAdapter> to fill a `DataSet`/`DataTable`.</span></span> <span data-ttu-id="9d215-161">使用大值类型的方式和使用其相关的较小值数据类型的方式之间没有什么不同。</span><span class="sxs-lookup"><span data-stu-id="9d215-161">There is no difference between the way you work with a large value type and its related, smaller value data type.</span></span>  
  
### <a name="using-getsqlbytes-to-retrieve-data"></a><span data-ttu-id="9d215-162">使用 GetSqlBytes 检索数据</span><span class="sxs-lookup"><span data-stu-id="9d215-162">Using GetSqlBytes to Retrieve Data</span></span>  
 <span data-ttu-id="9d215-163">`GetSqlBytes` 的 <xref:System.Data.SqlClient.SqlDataReader> 方法可用于检索 `varbinary(max)` 列的内容。</span><span class="sxs-lookup"><span data-stu-id="9d215-163">The `GetSqlBytes` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="9d215-164">下面的代码段假定一个名为 <xref:System.Data.SqlClient.SqlCommand> 的 `cmd` 对象（该对象可从表中选择 `varbinary(max)` 数据）和一个名为 <xref:System.Data.SqlClient.SqlDataReader> 的 `reader` 对象（该对象可将该数据检索为 <xref:System.Data.SqlTypes.SqlBytes>）。</span><span class="sxs-lookup"><span data-stu-id="9d215-164">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as <xref:System.Data.SqlTypes.SqlBytes>.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim bytes As SqlBytes = reader.GetSqlBytes(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBytes bytes = reader.GetSqlBytes(0);  
    }  
```  
  
### <a name="using-getsqlchars-to-retrieve-data"></a><span data-ttu-id="9d215-165">使用 GetSqlChars 检索数据</span><span class="sxs-lookup"><span data-stu-id="9d215-165">Using GetSqlChars to Retrieve Data</span></span>  
 <span data-ttu-id="9d215-166">`GetSqlChars` 的 <xref:System.Data.SqlClient.SqlDataReader> 方法可用于检索 `varchar(max)` 或 `nvarchar(max)` 列的内容。</span><span class="sxs-lookup"><span data-stu-id="9d215-166">The `GetSqlChars` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varchar(max)` or `nvarchar(max)` column.</span></span> <span data-ttu-id="9d215-167">下面的代码段假定一个名为 <xref:System.Data.SqlClient.SqlCommand> 的 `cmd` 对象（该对象可从表中选择 `nvarchar(max)` 数据）和一个名为 <xref:System.Data.SqlClient.SqlDataReader> 的 `reader` 对象（该对象可检索该数据）。</span><span class="sxs-lookup"><span data-stu-id="9d215-167">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `nvarchar(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim buffer As SqlChars = reader.GetSqlChars(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
{  
    SqlChars buffer = reader.GetSqlChars(0);  
}  
```  
  
### <a name="using-getsqlbinary-to-retrieve-data"></a><span data-ttu-id="9d215-168">使用 GetSqlBinary 检索数据</span><span class="sxs-lookup"><span data-stu-id="9d215-168">Using GetSqlBinary to Retrieve Data</span></span>  
 <span data-ttu-id="9d215-169">`GetSqlBinary` 的 <xref:System.Data.SqlClient.SqlDataReader> 方法可用于检索 `varbinary(max)` 列的内容。</span><span class="sxs-lookup"><span data-stu-id="9d215-169">The `GetSqlBinary` method of a <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="9d215-170">下面的代码段假定一个名为 <xref:System.Data.SqlClient.SqlCommand> 的 `cmd` 对象（该对象可从表中选择 `varbinary(max)` 数据）和一个名为 <xref:System.Data.SqlClient.SqlDataReader> 的 `reader` 对象（该对象可将该数据检索为 <xref:System.Data.SqlTypes.SqlBinary> 流）。</span><span class="sxs-lookup"><span data-stu-id="9d215-170">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as a <xref:System.Data.SqlTypes.SqlBinary> stream.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim binaryStream As SqlBinary = reader.GetSqlBinary(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBinary binaryStream = reader.GetSqlBinary(0);  
    }  
```  
  
### <a name="using-getbytes-to-retrieve-data"></a><span data-ttu-id="9d215-171">使用 GetBytes 检索数据</span><span class="sxs-lookup"><span data-stu-id="9d215-171">Using GetBytes to Retrieve Data</span></span>  
 <span data-ttu-id="9d215-172">`GetBytes` 的 <xref:System.Data.SqlClient.SqlDataReader> 方法将从指定列偏移量开始的字节流读入到数组中从指定数组偏移量开始的位置。</span><span class="sxs-lookup"><span data-stu-id="9d215-172">The `GetBytes` method of a <xref:System.Data.SqlClient.SqlDataReader> reads a stream of bytes from the specified column offset into a byte array starting at the specified array offset.</span></span> <span data-ttu-id="9d215-173">下面的代码段假定一个名为 <xref:System.Data.SqlClient.SqlDataReader> 的 `reader` 对象，该对象可将字节检索到字节数组中。</span><span class="sxs-lookup"><span data-stu-id="9d215-173">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves bytes into a byte array.</span></span> <span data-ttu-id="9d215-174">请注意，与 `GetSqlBytes` 不同，`GetBytes` 要求指定数组缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="9d215-174">Note that, unlike `GetSqlBytes`, `GetBytes` requires a size for the array buffer.</span></span>  
  
```vb  
While reader.Read()  
    Dim buffer(4000) As Byte  
    Dim byteCount As Integer = _  
    CInt(reader.GetBytes(1, 0, buffer, 0, 4000))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    byte[] buffer = new byte[4000];  
    long byteCount = reader.GetBytes(1, 0, buffer, 0, 4000);  
}  
```  
  
### <a name="using-getvalue-to-retrieve-data"></a><span data-ttu-id="9d215-175">使用 GetValue 检索数据</span><span class="sxs-lookup"><span data-stu-id="9d215-175">Using GetValue to Retrieve Data</span></span>  
 <span data-ttu-id="9d215-176">`GetValue` 的 <xref:System.Data.SqlClient.SqlDataReader> 方法将指定列偏移量处的值读入数组。</span><span class="sxs-lookup"><span data-stu-id="9d215-176">The `GetValue` method of a <xref:System.Data.SqlClient.SqlDataReader> reads the value from the specified column offset into an array.</span></span> <span data-ttu-id="9d215-177">下面的代码段假定一个名为 <xref:System.Data.SqlClient.SqlDataReader> 的 `reader` 对象，该对象检索第一个列偏移量处的二进制数据，然后检索第二个列偏移量处的字符串数据。</span><span class="sxs-lookup"><span data-stu-id="9d215-177">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves binary data from the first column offset, and then string data from the second column offset.</span></span>  
  
```vb  
While reader.Read()  
    ' Read the data from varbinary(max) column  
    Dim binaryData() As Byte = CByte(reader.GetValue(0))  
  
    ' Read the data from varchar(max) or nvarchar(max) column  
    Dim stringData() As String = Cstr((reader.GetValue(1))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    // Read the data from varbinary(max) column  
    byte[] binaryData = (byte[])reader.GetValue(0);  
  
    // Read the data from varchar(max) or nvarchar(max) column  
    String stringData = (String)reader.GetValue(1);  
}  
```  
  
## <a name="converting-from-large-value-types-to-clr-types"></a><span data-ttu-id="9d215-178">从大值类型转换为 CLR 类型</span><span class="sxs-lookup"><span data-stu-id="9d215-178">Converting from Large Value Types to CLR Types</span></span>  
 <span data-ttu-id="9d215-179">可以使用任何字符串转换方法（例如 `varchar(max)`）来转换 `nvarchar(max)` 或 `ToString` 列的内容。</span><span class="sxs-lookup"><span data-stu-id="9d215-179">You can convert the contents of a `varchar(max)` or `nvarchar(max)` column using any of the string conversion methods, such as `ToString`.</span></span> <span data-ttu-id="9d215-180">下面的代码段假定一个可检索数据的名为 <xref:System.Data.SqlClient.SqlDataReader> 的 `reader` 对象。</span><span class="sxs-lookup"><span data-stu-id="9d215-180">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
```vb  
While reader.Read()  
    Dim str as String = reader(0).ToString()  
    Console.WriteLine(str)  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
     string str = reader[0].ToString();  
     Console.WriteLine(str);  
}  
```  
  
### <a name="example"></a><span data-ttu-id="9d215-181">示例</span><span class="sxs-lookup"><span data-stu-id="9d215-181">Example</span></span>  
 <span data-ttu-id="9d215-182">下面的代码检索 `LargePhoto` 数据库的 `ProductPhoto` 表中的名称和 `AdventureWorks` 对象，并将其保存到文件。</span><span class="sxs-lookup"><span data-stu-id="9d215-182">The following code retrieves the name and the `LargePhoto` object from the `ProductPhoto` table in the `AdventureWorks` database and saves it to a file.</span></span> <span data-ttu-id="9d215-183">编译程序集时需要引用 <xref:System.Drawing> 命名空间。</span><span class="sxs-lookup"><span data-stu-id="9d215-183">The assembly needs to be compiled with a reference to the <xref:System.Drawing> namespace.</span></span>  <span data-ttu-id="9d215-184"><xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> 的 <xref:System.Data.SqlClient.SqlDataReader> 方法返回一个 <xref:System.Data.SqlTypes.SqlBytes> 对象，该对象公开 `Stream` 属性。</span><span class="sxs-lookup"><span data-stu-id="9d215-184">The <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> method of the <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.SqlTypes.SqlBytes> object that exposes a `Stream` property.</span></span> <span data-ttu-id="9d215-185">代码使用此方法创建一个新`Bitmap`的对象，然后将其保存在 Gif `ImageFormat`中。</span><span class="sxs-lookup"><span data-stu-id="9d215-185">The code uses this to create a new `Bitmap` object, and then saves it in the Gif `ImageFormat`.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## <a name="using-large-value-type-parameters"></a><span data-ttu-id="9d215-186">使用大值类型参数</span><span class="sxs-lookup"><span data-stu-id="9d215-186">Using Large Value Type Parameters</span></span>  
 <span data-ttu-id="9d215-187">在 <xref:System.Data.SqlClient.SqlParameter> 对象中使用大型值类型的方法与在 <xref:System.Data.SqlClient.SqlParameter> 对象中使用较小值类型的方法相同。</span><span class="sxs-lookup"><span data-stu-id="9d215-187">Large value types can be used in <xref:System.Data.SqlClient.SqlParameter> objects the same way you use smaller value types in <xref:System.Data.SqlClient.SqlParameter> objects.</span></span> <span data-ttu-id="9d215-188">可以将大值类型作为<xref:System.Data.SqlClient.SqlParameter>值进行检索，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="9d215-188">You can retrieve large value types as <xref:System.Data.SqlClient.SqlParameter> values, as shown in the following example.</span></span> <span data-ttu-id="9d215-189">代码假定在 AdventureWorks 示例数据库中存在以下 GetDocumentSummary 存储过程。</span><span class="sxs-lookup"><span data-stu-id="9d215-189">The code assumes that the following GetDocumentSummary stored procedure exists in the AdventureWorks sample database.</span></span> <span data-ttu-id="9d215-190">该存储过程采用一个名为@DocumentID的输入参数，并返回@DocumentSummary output 参数中 DocumentSummary 列的内容。</span><span class="sxs-lookup"><span data-stu-id="9d215-190">The stored procedure takes an input parameter named @DocumentID and returns the contents of the DocumentSummary column in the @DocumentSummary output parameter.</span></span>  
  
```sql
CREATE PROCEDURE GetDocumentSummary   
(  
    @DocumentID int,  
    @DocumentSummary nvarchar(MAX) OUTPUT  
)  
AS  
SET NOCOUNT ON  
SELECT  @DocumentSummary=Convert(nvarchar(MAX), DocumentSummary)  
FROM    Production.Document  
WHERE   DocumentID=@DocumentID  
```  
  
### <a name="example"></a><span data-ttu-id="9d215-191">示例</span><span class="sxs-lookup"><span data-stu-id="9d215-191">Example</span></span>  
 <span data-ttu-id="9d215-192">ADO.NET 代码创建 <xref:System.Data.SqlClient.SqlConnection> 和 <xref:System.Data.SqlClient.SqlCommand> 对象，以执行 GetDocumentSummary 存储过程并检索以大值类型存储的文档摘要。</span><span class="sxs-lookup"><span data-stu-id="9d215-192">The ADO.NET code creates <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to execute the GetDocumentSummary stored procedure and retrieve the document summary, which is stored as a large value type.</span></span> <span data-ttu-id="9d215-193">代码传递@DocumentID输入参数的值，并在控制台窗口中的@DocumentSummary输出参数中显示传回的结果。</span><span class="sxs-lookup"><span data-stu-id="9d215-193">The code passes a value for the @DocumentID input parameter, and displays the results passed back in the @DocumentSummary output parameter in the Console window.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="9d215-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d215-194">See also</span></span>

- [<span data-ttu-id="9d215-195">SQL Server 二进制和大值数据</span><span class="sxs-lookup"><span data-stu-id="9d215-195">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="9d215-196">SQL Server 数据类型映射</span><span class="sxs-lookup"><span data-stu-id="9d215-196">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="9d215-197">ADO.NET 中的 SQL Server 数据操作</span><span class="sxs-lookup"><span data-stu-id="9d215-197">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="9d215-198">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="9d215-198">ADO.NET Overview</span></span>](../ado-net-overview.md)
