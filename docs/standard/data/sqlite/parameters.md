---
title: parameters
ms.date: 12/13/2019
description: 了解如何使用 SQL 参数。
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401201"
---
# <a name="parameters"></a>parameters

参数用于防止 SQL 注入攻击。 使用参数确保输入仅被视为文本值，并且永远不会执行，而不是将用户输入与 SQL 语句串联。 在 SQLite 中，参数通常允许在 SQL 语句中允许文本的任何位置。

参数可以使用`:`或`@``$`的预缀。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

有关如何将 .NET 值映射到 SQLite 值的详细信息，请参阅[数据类型](types.md)。

## <a name="truncation"></a>截断

使用<xref:Microsoft.Data.Sqlite.SqliteParameter.Size>属性截截 TEXT 和 BLOB 值。

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a>替代类型

有时，您可能需要使用替代 SQLite 类型。 通过设置属性来<xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType>执行此操作。

可以使用以下替代类型映射。 有关默认映射，请参阅[数据类型](types.md)。

| 值          | Sqlite 类型 | 备注          |
| -------------- | ---------- | ---------------- |
| Char           | Integer    | UTF-16           |
| DateTime       | Real       | 朱利安日值 |
| DateTimeOffset | Real       | 朱利安日值 |
| Guid           | Blob       |                  |
| TimeSpan       | Real       | 在几天内          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>输出参数

SQLite 不支持输出参数。 返回查询结果中的值。

## <a name="see-also"></a>另请参阅

* [数据类型](types.md)
