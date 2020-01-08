---
title: 参数
ms.date: 12/13/2019
description: 了解如何使用 SQL 参数。
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450422"
---
# <a name="parameters"></a>参数

参数用于防范 SQL 注入式攻击。 使用参数可以确保输入只被视为文本值，而永远不会执行，而不是使用 SQL 语句连接用户输入。 在 SQLite 中，SQL 语句中允许使用文本的任何位置通常都允许使用参数。

参数可以为 `:`、`@`或 `$`加前缀。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

有关如何将 .NET 值映射到 SQLite 值的详细信息，请参阅[数据类型](types.md)。

## <a name="truncation"></a>截断

使用 <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> 属性可截断文本和 BLOB 值。

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a>替代类型

有时，你可能想要使用备用 SQLite 类型。 通过设置 <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> 属性来执行此操作。

可以使用以下替代类型映射。 有关默认映射的详细数据类型，请参阅[数据类型](types.md)。

| {2&gt;值&lt;2}          | SqliteType | 备注          |
| -------------- | ---------- | ---------------- |
| Char           | 整数    | UTF-16           |
| DateTime       | Real       | 儒略历日值 |
| DateTimeOffset | Real       | 儒略历日值 |
| GUID           | Blob       |                  |
| TimeSpan       | Real       | （天）          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>输出参数

SQLite 不支持输出参数。 改为返回查询结果中的值。

## <a name="see-also"></a>另请参阅

* [数据类型](types.md)
