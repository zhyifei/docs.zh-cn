---
title: 元数据
ms.date: 12/13/2019
description: 了解如何检索有关数据库的元数据。
ms.openlocfilehash: b2f2704a748627d9943943fa2fa7b1b7e9f3007f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450428"
---
# <a name="metadata"></a><span data-ttu-id="6a148-103">元数据</span><span class="sxs-lookup"><span data-stu-id="6a148-103">Metadata</span></span>

<span data-ttu-id="6a148-104">提供两种用于检索 ADO.NET 中元数据的 API。</span><span class="sxs-lookup"><span data-stu-id="6a148-104">There are two APIs for retrieving metadata in ADO.NET.</span></span> <span data-ttu-id="6a148-105">一个检索有关查询结果的元数据。</span><span class="sxs-lookup"><span data-stu-id="6a148-105">One retrieves metadata about query results.</span></span> <span data-ttu-id="6a148-106">另一个检索有关数据库架构的元数据。</span><span class="sxs-lookup"><span data-stu-id="6a148-106">The other retrieves metadata about the database schema.</span></span>

## <a name="query-result-metadata"></a><span data-ttu-id="6a148-107">查询结果元数据</span><span class="sxs-lookup"><span data-stu-id="6a148-107">Query result metadata</span></span>

<span data-ttu-id="6a148-108">可以及使用 `SqliteDataReader` 上的 <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> 方法检索有关查询结果的元数据。</span><span class="sxs-lookup"><span data-stu-id="6a148-108">You can retrieve metadata about the results of a query using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method on `SqliteDataReader`.</span></span> <span data-ttu-id="6a148-109">返回的 <xref:System.Data.DataTable> 包含以下列：</span><span class="sxs-lookup"><span data-stu-id="6a148-109">The returned <xref:System.Data.DataTable> contains the following columns:</span></span>

| <span data-ttu-id="6a148-110">列</span><span class="sxs-lookup"><span data-stu-id="6a148-110">Column</span></span>             | <span data-ttu-id="6a148-111">类型</span><span class="sxs-lookup"><span data-stu-id="6a148-111">Type</span></span>    | <span data-ttu-id="6a148-112">描述</span><span class="sxs-lookup"><span data-stu-id="6a148-112">Description</span></span>                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | <span data-ttu-id="6a148-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="6a148-113">Boolean</span></span> | <span data-ttu-id="6a148-114">如果原点列可以为 NULL，则为 True。</span><span class="sxs-lookup"><span data-stu-id="6a148-114">True if the origin column may be NULL.</span></span>                                    |
| `BaseCatalogName`  | <span data-ttu-id="6a148-115">String</span><span class="sxs-lookup"><span data-stu-id="6a148-115">String</span></span>  | <span data-ttu-id="6a148-116">原点列的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="6a148-116">The name of the origin column's database.</span></span> <span data-ttu-id="6a148-117">表达式始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6a148-117">Always NULL for expressions.</span></span>    |
| `BaseColumnName`   | <span data-ttu-id="6a148-118">String</span><span class="sxs-lookup"><span data-stu-id="6a148-118">String</span></span>  | <span data-ttu-id="6a148-119">原点列的真实名称。</span><span class="sxs-lookup"><span data-stu-id="6a148-119">The unaliased name of the origin column.</span></span> <span data-ttu-id="6a148-120">表达式始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6a148-120">Always NULL for expressions.</span></span>    |
| `BaseSchemaName`   | <span data-ttu-id="6a148-121">String</span><span class="sxs-lookup"><span data-stu-id="6a148-121">String</span></span>  | <span data-ttu-id="6a148-122">始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6a148-122">Always NULL.</span></span> <span data-ttu-id="6a148-123">SQLite 不支持架构。</span><span class="sxs-lookup"><span data-stu-id="6a148-123">SQLite doesn't support schemas.</span></span>                              |
| `BaseServerName`   | <span data-ttu-id="6a148-124">String</span><span class="sxs-lookup"><span data-stu-id="6a148-124">String</span></span>  | <span data-ttu-id="6a148-125">在连接字符串中指定的数据库文件的路径。</span><span class="sxs-lookup"><span data-stu-id="6a148-125">The path to the database file specified in the connection string.</span></span>         |
| `BaseTableName`    | <span data-ttu-id="6a148-126">String</span><span class="sxs-lookup"><span data-stu-id="6a148-126">String</span></span>  | <span data-ttu-id="6a148-127">原点列的表的名称。</span><span class="sxs-lookup"><span data-stu-id="6a148-127">The name of the origin column's table.</span></span> <span data-ttu-id="6a148-128">表达式始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6a148-128">Always NULL for expressions.</span></span>       |
| `ColumnName`       | <span data-ttu-id="6a148-129">String</span><span class="sxs-lookup"><span data-stu-id="6a148-129">String</span></span>  | <span data-ttu-id="6a148-130">结果集中列的名称或别名。</span><span class="sxs-lookup"><span data-stu-id="6a148-130">The name or alias of the column in the result set.</span></span>                        |
| `ColumnOrdinal`    | <span data-ttu-id="6a148-131">Int32</span><span class="sxs-lookup"><span data-stu-id="6a148-131">Int32</span></span>   | <span data-ttu-id="6a148-132">结果集中列的序号。</span><span class="sxs-lookup"><span data-stu-id="6a148-132">The ordinal of the column in the result set.</span></span>                              |
| `ColumnSize`       | <span data-ttu-id="6a148-133">Int32</span><span class="sxs-lookup"><span data-stu-id="6a148-133">Int32</span></span>   | <span data-ttu-id="6a148-134">始终为 -1。</span><span class="sxs-lookup"><span data-stu-id="6a148-134">Always -1.</span></span> <span data-ttu-id="6a148-135">在将来的 `Microsoft.Data.Sqlite` 版本中这可能会发生变化。</span><span class="sxs-lookup"><span data-stu-id="6a148-135">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span>   |
| `DataType`         | <span data-ttu-id="6a148-136">类型</span><span class="sxs-lookup"><span data-stu-id="6a148-136">Type</span></span>    | <span data-ttu-id="6a148-137">列的默认 .NET 数据类型。</span><span class="sxs-lookup"><span data-stu-id="6a148-137">The default .NET data type of the column.</span></span>                                 |
| `DataTypeName`     | <span data-ttu-id="6a148-138">String</span><span class="sxs-lookup"><span data-stu-id="6a148-138">String</span></span>  | <span data-ttu-id="6a148-139">列的 SQLite 数据类型。</span><span class="sxs-lookup"><span data-stu-id="6a148-139">The SQLite data type of the column.</span></span>                                       |
| `IsAliased`        | <span data-ttu-id="6a148-140">Boolean</span><span class="sxs-lookup"><span data-stu-id="6a148-140">Boolean</span></span> | <span data-ttu-id="6a148-141">如果列名在结果集中具有别名，则为 True。</span><span class="sxs-lookup"><span data-stu-id="6a148-141">True if the column name is aliased in the result set.</span></span>                     |
| `IsAutoIncrement`  | <span data-ttu-id="6a148-142">Boolean</span><span class="sxs-lookup"><span data-stu-id="6a148-142">Boolean</span></span> | <span data-ttu-id="6a148-143">如果原点列是使用 AUTOINCREMENT 关键字创建的，则为 True。</span><span class="sxs-lookup"><span data-stu-id="6a148-143">True if the origin column was created with the AUTOINCREMENT keyword.</span></span>     |
| `IsExpression`     | <span data-ttu-id="6a148-144">Boolean</span><span class="sxs-lookup"><span data-stu-id="6a148-144">Boolean</span></span> | <span data-ttu-id="6a148-145">如果列源自查询中的表达式，则为 True。</span><span class="sxs-lookup"><span data-stu-id="6a148-145">True if the column originates from an expression in the query.</span></span>            |
| `IsKey`            | <span data-ttu-id="6a148-146">Boolean</span><span class="sxs-lookup"><span data-stu-id="6a148-146">Boolean</span></span> | <span data-ttu-id="6a148-147">如果原点列是主键的一部分，则为 True。</span><span class="sxs-lookup"><span data-stu-id="6a148-147">True if the origin column is part of the PRIMARY KEY.</span></span>                     |
| `IsUnique`         | <span data-ttu-id="6a148-148">Boolean</span><span class="sxs-lookup"><span data-stu-id="6a148-148">Boolean</span></span> | <span data-ttu-id="6a148-149">如果原点列是唯一的，则为 True。</span><span class="sxs-lookup"><span data-stu-id="6a148-149">True if the origin column is UNIQUE.</span></span>                                      |
| `NumericPrecision` | <span data-ttu-id="6a148-150">Int16</span><span class="sxs-lookup"><span data-stu-id="6a148-150">Int16</span></span>   | <span data-ttu-id="6a148-151">始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6a148-151">Always NULL.</span></span> <span data-ttu-id="6a148-152">在将来的 `Microsoft.Data.Sqlite` 版本中这可能会发生变化。</span><span class="sxs-lookup"><span data-stu-id="6a148-152">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |
| `NumericScale`     | <span data-ttu-id="6a148-153">Int16</span><span class="sxs-lookup"><span data-stu-id="6a148-153">Int16</span></span>   | <span data-ttu-id="6a148-154">始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6a148-154">Always NULL.</span></span> <span data-ttu-id="6a148-155">在将来的 `Microsoft.Data.Sqlite` 版本中这可能会发生变化。</span><span class="sxs-lookup"><span data-stu-id="6a148-155">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |

<span data-ttu-id="6a148-156">以下示例显示如何使用 `GetSchemaTable` 创建显示有关结果的元数据的调试字符串：</span><span class="sxs-lookup"><span data-stu-id="6a148-156">The following example shows how to use `GetSchemaTable` to create a debug string that shows metadata about a result:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

<span data-ttu-id="6a148-157">例如，此查询将产生以下调试字符串：</span><span class="sxs-lookup"><span data-stu-id="6a148-157">For example, this query would produce the following debug string:</span></span>

```sql
SELECT id AS post_id,
       title,
       body,
       random() AS random
FROM post
```

```output
post.id AS post_id INTEGER PRIMARY KEY AUTOINCREMENT
post.title TEXT NOT NULL UNIQUE
post.body TEXT
(expression) AS random BLOB
```

## <a name="schema-metadata"></a><span data-ttu-id="6a148-158">架构元数据</span><span class="sxs-lookup"><span data-stu-id="6a148-158">Schema metadata</span></span>

<span data-ttu-id="6a148-159">Microsoft.Data.Sqlite 未在 DbConnection 上实现 GetSchema 方法。</span><span class="sxs-lookup"><span data-stu-id="6a148-159">Microsoft.Data.Sqlite doesn't implement the GetSchema method on DbConnection.</span></span> <span data-ttu-id="6a148-160">相反，可以使用 [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) 表和 PRAGMA 语句（如 [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) 和 [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list)）直接查询架构信息。</span><span class="sxs-lookup"><span data-stu-id="6a148-160">Instead, you can query directly for schema information using the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and PRAGMA statements like [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) and [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span></span>

<span data-ttu-id="6a148-161">例如，此查询将检索数据库中所有列的元数据。</span><span class="sxs-lookup"><span data-stu-id="6a148-161">For example, this query will retrieve metadata about all the columns in the database.</span></span>

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a><span data-ttu-id="6a148-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a148-162">See also</span></span>

* [<span data-ttu-id="6a148-163">SQL 数据库架构的存储</span><span class="sxs-lookup"><span data-stu-id="6a148-163">Storage of the SQL Database Schema</span></span>](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [<span data-ttu-id="6a148-164">PRAGMA 语句</span><span class="sxs-lookup"><span data-stu-id="6a148-164">PRAGMA Statements</span></span>](https://www.sqlite.org/pragma.html)
* [<span data-ttu-id="6a148-165">数据类型</span><span class="sxs-lookup"><span data-stu-id="6a148-165">Data types</span></span>](types.md)
