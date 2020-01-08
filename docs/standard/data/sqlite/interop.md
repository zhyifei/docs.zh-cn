---
title: 互操作性
ms.date: 12/13/2019
description: 了解如何与其他 SQLite 库互操作。
ms.openlocfilehash: 486e2a8e00999b8ebe9c85a5fcc1539c514676d3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450458"
---
# <a name="interoperability"></a>互操作性

SQLitePCLRaw 使用与本机 SQLite 库交互。 SQLitePCLRaw 通过本机 SQLite API 提供瘦 .NET API。 SqliteConnection 和 SqliteDataReader 提供对基础 SQLitePCLRaw 对象的访问权限，让你直接调用这些 Api。

下面的示例演示如何调用 `sqlite3_trace` 以将已执行的 SQL 语句写入控制台：

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

下面的示例演示了如何调用 `sqlite3_stmt_status` 来查看 SQL 语句编译到的 SQLite 虚拟机的数目：

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

SQLitePCLRaw 对象甚至公开指向本地对象的指针，使你可以 P/调用其他本机 SQLite Api。
