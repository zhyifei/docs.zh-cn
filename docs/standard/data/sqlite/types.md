---
title: 数据类型
ms.date: 12/13/2019
description: 描述支持的数据类型及其周围的一些限制。
ms.openlocfilehash: a11ff382f80cd979506d6195c299c8234c3eb8ea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389041"
---
# <a name="data-types"></a>数据类型

SQLite 只有四种原始数据类型：INTEGER、真实、文本和 BLOB。 将数据库值作为 返回的`object`API 将仅返回这四种类型之一。 Microsoft.Data.Sqlite 支持其他 .NET 类型，但最终在这些类型的和四种基元类型之一之间强制使用值。

| .NET           | SQLite  | 备注                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| Boolean        | INTEGER | `0` 或 `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| DateTime       | TEXT    | yyyy-MM-dd HH：mm：sss.森林论坛                                   |
| DateTimeOffset | TEXT    | yyyy-MM-dd HH：mm：sss.FFFFFFFfzzz                                |
| Decimal        | TEXT    | `0.0###########################`格式。 雷亚尔是亏损的。 |
| Double         | real    |                                                               |
| Guid           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| Single         | real    |                                                               |
| 字符串         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | d.hh：mm：s.fffffff                                            |
| UInt16         | INTEGER |                                                               |
| UInt32         | INTEGER |                                                               |
| UInt64         | INTEGER | 大值溢出                                         |

## <a name="alternative-types"></a>替代类型

某些 .NET 类型可以从其他 SQLite 类型读取。 参数也可以配置为使用这些替代类型。 有关详细信息，请参阅[参数](parameters.md#alternative-types)。

| .NET           | SQLite  | 备注          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| DateTime       | real    | 朱利安日值 |
| DateTimeOffset | real    | 朱利安日值 |
| Guid           | BLOB    |                  |
| TimeSpan       | real    | 在几天内          |

例如，以下查询从结果集中的 REAL 列读取 TimeSpan 值。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>列类型

SQLite 使用动态类型系统，其中值的类型与值本身相关联，而不是与存储值的列相关联。 您可以自由使用所需的任何列类型名称。 Microsoft.Data.Sqlite 不会对这些名称应用任何其他语义。

列类型名称确实对[类型相关性](https://www.sqlite.org/datatype3.html#type_affinity)有影响。 一个常见的错误是，使用 STRING 的列类型将尝试将值转换为 INTEGER 或 REAL，这可能导致意外的结果。 我们建议仅使用四个原始 SQLite 类型名称：INTEGER、真实名称、文本名称和 BLOB。

SQLite 允许您指定长度、精度和比例等类型方面，但它们不是由数据库引擎强制执行的。 你的应用负责执行这些。

## <a name="see-also"></a>另请参阅

- [SQLite 中的数据类型](https://www.sqlite.org/datatype3.html)
