---
title: 元数据
ms.date: 12/13/2019
description: 了解如何检索有关数据库的元数据。
ms.openlocfilehash: b2f2704a748627d9943943fa2fa7b1b7e9f3007f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450428"
---
# <a name="metadata"></a>元数据

有两个 Api 可用于在 ADO.NET 中检索元数据。 一个检索有关查询结果的元数据。 另一个检索有关数据库架构的元数据。

## <a name="query-result-metadata"></a>查询结果元数据

您可以使用 `SqliteDataReader`上的 <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> 方法检索有关查询结果的元数据。 返回的 <xref:System.Data.DataTable> 包含以下列：

| 列             | 类型    | 描述                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | Boolean | 如果源列可以为 NULL，则为 True。                                    |
| `BaseCatalogName`  | 字符串  | 源列数据库的名称。 表达式始终为 NULL。    |
| `BaseColumnName`   | 字符串  | 源列的非别名名称。 表达式始终为 NULL。    |
| `BaseSchemaName`   | 字符串  | 始终为 NULL。 SQLite 不支持架构。                              |
| `BaseServerName`   | 字符串  | 连接字符串中指定的数据库文件的路径。         |
| `BaseTableName`    | 字符串  | 源列的表的名称。 表达式始终为 NULL。       |
| `ColumnName`       | 字符串  | 结果集中列的名称或别名。                        |
| `ColumnOrdinal`    | Int32   | 结果集中列的序号。                              |
| `ColumnSize`       | Int32   | 始终为-1。 在 `Microsoft.Data.Sqlite`的将来版本中可能会发生更改。   |
| `DataType`         | 类型    | 列的默认 .NET 数据类型。                                 |
| `DataTypeName`     | 字符串  | 列的 SQLite 数据类型。                                       |
| `IsAliased`        | Boolean | 如果列名称在结果集中具有别名，则为 True。                     |
| `IsAutoIncrement`  | Boolean | 如果源列是用自动增量关键字创建的，则为 True。     |
| `IsExpression`     | Boolean | 如果列源自查询中的表达式，则为 True。            |
| `IsKey`            | Boolean | 如果源列是主键的一部分，则为 True。                     |
| `IsUnique`         | Boolean | 如果源列是唯一的，则为 True。                                      |
| `NumericPrecision` | Int16   | 始终为 NULL。 在 `Microsoft.Data.Sqlite`的将来版本中可能会发生更改。 |
| `NumericScale`     | Int16   | 始终为 NULL。 在 `Microsoft.Data.Sqlite`的将来版本中可能会发生更改。 |

下面的示例演示如何使用 `GetSchemaTable` 来创建一个显示有关结果的元数据的调试字符串：

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

例如，此查询将生成以下调试字符串：

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

## <a name="schema-metadata"></a>架构元数据

GetSchema 不在 DbConnection 上实现 "" 方法。 相反，您可以使用[sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)表和杂注语句（如[table_info](https://www.sqlite.org/pragma.html#pragma_table_info)和[foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list)）直接查询架构信息。

例如，此查询将检索有关数据库中所有列的元数据。

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a>另请参阅

* [SQL 数据库架构的存储](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [PRAGMA 语句](https://www.sqlite.org/pragma.html)
* [数据类型](types.md)
