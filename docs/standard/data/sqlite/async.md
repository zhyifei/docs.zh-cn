---
title: 异步限制
ms.date: 12/13/2019
description: 说明异步 Api 的限制和一些可改用的替代项。
ms.openlocfilehash: 350237dc5c03023f60e9680e8b9c94aabb62606f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450332"
---
# <a name="async-limitations"></a>异步限制

SQLite 不支持异步 i/o。 异步 ADO.NET 方法将在中同步执行。 避免调用它们。

相反，请使用[预写日志记录](https://www.sqlite.org/wal.html)来提高性能和并发性。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> 默认情况下，在使用[Entity Framework Core](/ef/core/)创建的数据库上启用预写日志记录。
