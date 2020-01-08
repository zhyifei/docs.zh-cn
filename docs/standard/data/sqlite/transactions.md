---
title: 事务
ms.date: 12/13/2019
description: 了解如何使用事务。
ms.openlocfilehash: 4b72a1573a560ffd1bfd0f54d46ab3b135280976
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450380"
---
# <a name="transactions"></a>事务

通过事务可以将多个 SQL 语句组合成单个工作单元，并将其作为一个原子单元提交到数据库。 如果事务中的任何语句失败，则可以回滚前面语句所做的更改。 当事务开始时，数据库的初始状态为 "已启动"。 如果对数据库进行了大量更改，则使用事务还可以提高 SQLite 的性能。

## <a name="concurrency"></a>并发

在 SQLite 中，一次只允许一个事务在数据库中具有挂起的更改。 因此，如果另一个事务需要很长时间才能完成，则对 <xref:Microsoft.Data.Sqlite.SqliteCommand> 的调用 <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> 和 `Execute` 方法可能会超时。

有关锁定、重试和超时的详细信息，请参阅[数据库错误](database-errors.md)。

## <a name="isolation-levels"></a>隔离级别

默认情况下，在 SQLite 中**可序列化**事务。 此隔离级别保证在事务中所做的任何更改都是完全隔离的。 在事务之外执行的其他语句不受事务更改的影响。

SQLite 还支持使用共享缓存时**未提交读**。 此级别允许脏读、不可重复读取和幻像：

- 当事务外部的查询返回一个事务中的挂起的更改，但该事务中的更改将回滚时，将发生*脏读*。 结果包含从不实际提交到数据库的数据。

- 当事务两次查询相同的行时，将发生*不可重复读取*，但结果不同，因为它在两个查询之间由另一个事务更改。

- *幻像*是在事务期间更改或添加以满足查询的 where 子句的行。 如果允许，同一查询在同一事务中执行两次时，可能返回不同的行。

IsolationLevel 将传递给 <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> 的视为最低级别。 实际隔离级别将提升为读取未提交或可序列化。

下面的代码模拟脏读。 请注意，连接字符串必须包括 `Cache=Shared`。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DirtyReadSample/Program.cs?name=snippet_DirtyRead)]
