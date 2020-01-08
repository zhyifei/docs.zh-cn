---
title: 批处理
ms.date: 12/13/2019
description: 了解如何在单个命令中执行一批 SQL 语句。
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450308"
---
# <a name="batching"></a>批处理

SQLite 不以本机方式支持将 SQL 语句批处理到单个命令中。 但由于不涉及网络，因此仍不会真正帮助性能。 不过，ADO.NET 实现语句批处理，使其行为更像其他提供程序。

调用 <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>时，语句将执行到第一个返回结果的语句上。 调用 <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> 将继续执行语句，直到下一个语句返回结果，或直到到达批处理的末尾。 调用 <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> 或 <xref:System.Data.Common.DbDataReader.Close%2A> 会执行 `NextResult()`未使用的所有剩余语句。 如果未释放数据读取器，则终结器将尝试执行剩余的语句，但会忽略它遇到的任何错误。 因此，在使用批处理时释放 `DbDataReader` 对象非常重要。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a>另请参阅

* [大容量插入](bulk-insert.md)
