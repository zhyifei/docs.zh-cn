---
title: 与 System.object 的比较
ms.date: 12/13/2019
description: 描述了 Microsoft 数据库和 System.object 库之间的一些差异。
ms.openlocfilehash: dee90c132b108f2c876c0d8becc1b02035a47b61
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450278"
---
# <a name="comparison-to-systemdatasqlite"></a>与 System.object 的比较

在2005中，Robert Simpson 创建了一个 ADO.NET 2.0 的 SQLite 提供程序。 在2010中，SQLite 团队接管了项目的维护和开发工作。 还值得注意的是，Mono 团队将2007中的代码分叉为单声道。 ADO.NET 具有较长的历史记录，并已发展为完整的、功能齐全的提供程序，并具有 Visual Studio 工具。 新版本会继续将与每个版本的 .NET Framework 兼容的程序集传送回版本2.0，甚至 .NET Compact Framework 3.5。

.NET Core 的第一个版本（在2016中发布）是 .NET 的单个、轻型、新式和跨平台实现。 特意删除了具有更多新式替代项的过时 Api 和 Api。 ADO.NET 不包括任何数据集 Api （包括 DataTable 和 DataAdapter）。

实体框架团队在某种程度上熟悉了 system.exception 基本代码。 Brice Lambson 是 EF 团队的成员，以前已帮助 SQLite 团队添加对实体框架版本5和6的支持。 此外，Brice 还试验了其在计划 .NET Core 的同时，其自己的 SQLite ADO.NET 提供程序实现。 在长时间讨论后，实体框架团队决定根据 Brice 的原型创建。 这使他们能够创建新的轻型和新式实现，使其与 .NET Core 的目标保持一致。

作为我们所说的更多新式的示例，这里是在 system.exception 和数据表中创建[用户定义函数](user-defined-functions.md)的代码。

```csharp
// System.Data.SQLite
connection.BindFunction(
    new SQLiteFunctionAttribute("ceiling", 1, FunctionType.Scalar),
    (Func<object[], object>)((object[] args) => Math.Ceiling((double)((object[])args[1])[0])),
    null);

// Microsoft.Data.Sqlite
connection.CreateFunction(
    "ceiling",
    (double arg) => Math.Ceiling(arg));
```

在2017中，.NET Core 2.0 经历了策略更改。 它决定了与 .NET Framework 的兼容性对于 .NET Core 的成功至关重要。 许多已删除的 Api （包括数据集 Api）已添加回。 与许多其他方法一样，这种解除阻止的 System.object 也允许它移植到 .NET Core。 然而，在轻型和新式情况下，Microsoft 数据的原始目标仍保持不变。 有关不是由 ADO.NET 实现的 ADO.NET Api 的详细信息，请参阅相关[限制](adonet-limitations.md)。

将新功能添加到了 node.js 后，会考虑到系统的设计。 尽可能将两个更改减至最小，以便在两者之间进行转换。

## <a name="data-types"></a>数据类型

数据类型的处理方式与数据类型的处理方式最大。 如[数据类型](types.md)中所述，quirkiness 不会尝试隐藏 Sqlite 的基础，这允许将任意字符串指定为列类型，并且只有四个基元类型：整数、实数、文本和 BLOB。

对于列类型，则将其他语义直接映射到 .NET 类型。 这为提供程序提供了一种更强类型的外观，但它具有一些粗糙的边缘。 例如，它们必须引入一个新的 SQL 语句（类型）来指定 SELECT 语句中表达式的列类型。

## <a name="connection-strings"></a>连接字符串

-Sqlite 的[连接字符串](connection-strings.md)关键字少很多。 下表显示了可改为使用的替代项。

| 关键字          | 替代项                                         |
| ---------------- | --------------------------------------------------- |
| 缓存大小       | 发送 `PRAGMA cache_size = <pages>`                  |
| 默认超时  | 使用 SqliteConnection 上的 DefaultTimeout 属性 |
| FailIfMissing    | 使用 `Mode=ReadWrite`                                |
| FullUri          | 使用数据源关键字                         |
| 日志模式     | 发送 `PRAGMA journal_mode = <mode>`                 |
| 旧格式    | 发送 `PRAGMA legacy_file_format = 1`                |
| 最大页计数   | 发送 `PRAGMA max_page_count = <pages>`              |
| 页面大小        | 发送 `PRAGMA page_size = <bytes>`                   |
| 只读        | 使用 `Mode=ReadOnly`                                 |
| Synchronous      | 发送 `PRAGMA synchronous = <mode>`                  |
| URI              | 使用数据源关键字                         |
| UseUTF16Encoding | 发送 `PRAGMA encoding = 'UTF-16'`                   |

## <a name="authorization"></a>授权

Node.js 没有任何 API 公开 SQLite 的授权回调。 使用问题[#13835](https://github.com/aspnet/EntityFrameworkCore/issues/13835)提供有关此功能的反馈。

## <a name="data-change-notifications"></a>数据更改通知

Node.js 没有任何 API 公开 SQLite 的数据更改通知。 使用问题[#13827](https://github.com/aspnet/EntityFrameworkCore/issues/13827)提供有关此功能的反馈。

## <a name="virtual-table-modules"></a>虚拟表模块

Node.js 没有用于创建虚拟表模块的任何 API。 使用问题[#13823](https://github.com/aspnet/EntityFrameworkCore/issues/13823)提供有关此功能的反馈。

## <a name="see-also"></a>另请参阅

* [数据类型](types.md)
* [连接字符串](connection-strings.md)
* [加密](encryption.md)
* [ADO.NET 限制](adonet-limitations.md)
* [Dapper 限制](dapper-limitations.md)
