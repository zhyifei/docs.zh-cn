---
title: 数据类型
ms.date: 12/13/2019
description: 介绍支持的数据类型以及这些数据类型的一些限制。
ms.openlocfilehash: ae70cb91a5a6d9cfed45a5a47dda25a70362871e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450416"
---
# <a name="data-types"></a>数据类型

SQLite 只有四个基元数据类型：整数、实数、文本和 BLOB。 将数据库值作为 `object` 返回的 Api 只会返回这四种类型中的一种。 其他 .NET 类型都受 Microsoft 的支持，但最终在这些类型和这四种基元类型之一之间强制转换值。

| .NET           | SQLite  | 备注                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| Boolean        | INTEGER | `0` 或 `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| DateTime       | TEXT    | yyyy-mm-dd HH： MM： ss。FFFFFFF                                   |
| DateTimeOffset | TEXT    | yyyy-mm-dd HH： MM： ss。Ss'.'fffffffzzz                                |
| Decimal        | TEXT    | `0.0###########################` 格式。 现实会有损。 |
| Double         | REAL    |                                                               |
| GUID           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| Single         | REAL    |                                                               |
| 字符串         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | d. hh： mm： ss. fffffff                                            |
| UInt16         | INTEGER |                                                               |
| UInt64         | INTEGER | 大值溢出                                         |

## <a name="alternative-types"></a>替代类型

某些 .NET 类型可以从其他 SQLite 类型中读取。 还可以将参数配置为使用这些替代类型。 有关详细信息，请参阅[参数](parameters.md#alternative-types)。

| .NET           | SQLite  | 备注          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| DateTime       | REAL    | 儒略历日值 |
| DateTimeOffset | REAL    | 儒略历日值 |
| GUID           | BLOB    |                  |
| TimeSpan       | REAL    | （天）          |

例如，下面的查询从结果集中的实数列读取 TimeSpan 值。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>列类型

SQLite 使用动态类型系统，其中值的类型与值本身相关联，而不是与存储它的列关联。 您可以随意使用所需的任何列类型名称。 对于这些名称，数据不会应用任何其他语义。

列类型名称对[类型关联](https://www.sqlite.org/datatype3.html#type_affinity)有影响。 一个常见的难点是，使用列类型的字符串会尝试将值转换为 INTEGER 或 REAL，这可能会导致意外的结果。 建议仅使用四个基元类型名称：整数、实数、文本和 BLOB。

SQLite 允许您指定类型方面（如长度、精度和小数位数），但不由数据库引擎强制执行。 应用负责强制执行这些。

## <a name="see-also"></a>另请参阅

- [SQLite 中的数据类型](https://www.sqlite.org/datatype3.html)
