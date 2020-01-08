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
# <a name="batching"></a><span data-ttu-id="7b876-103">批处理</span><span class="sxs-lookup"><span data-stu-id="7b876-103">Batching</span></span>

<span data-ttu-id="7b876-104">SQLite 不以本机方式支持将 SQL 语句批处理到单个命令中。</span><span class="sxs-lookup"><span data-stu-id="7b876-104">SQLite doesn't natively support batching SQL statements together into a single command.</span></span> <span data-ttu-id="7b876-105">但由于不涉及网络，因此仍不会真正帮助性能。</span><span class="sxs-lookup"><span data-stu-id="7b876-105">But because there's no network involved, it wouldn't really help performance anyway.</span></span> <span data-ttu-id="7b876-106">不过，ADO.NET 实现语句批处理，使其行为更像其他提供程序。</span><span class="sxs-lookup"><span data-stu-id="7b876-106">Microsoft.Data.Sqlite does, however, implement statement batching as a convenience to make it behave more like other ADO.NET providers.</span></span>

<span data-ttu-id="7b876-107">调用 <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>时，语句将执行到第一个返回结果的语句上。</span><span class="sxs-lookup"><span data-stu-id="7b876-107">When calling <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, statements are executed up to the first one that returns results.</span></span> <span data-ttu-id="7b876-108">调用 <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> 将继续执行语句，直到下一个语句返回结果，或直到到达批处理的末尾。</span><span class="sxs-lookup"><span data-stu-id="7b876-108">Calling <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> continues executing statements until the next one that returns results or until it reaches the end of the batch.</span></span> <span data-ttu-id="7b876-109">调用 <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> 或 <xref:System.Data.Common.DbDataReader.Close%2A> 会执行 `NextResult()`未使用的所有剩余语句。</span><span class="sxs-lookup"><span data-stu-id="7b876-109">Calling <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> or <xref:System.Data.Common.DbDataReader.Close%2A> executes any remaining statements that haven't been consumed by `NextResult()`.</span></span> <span data-ttu-id="7b876-110">如果未释放数据读取器，则终结器将尝试执行剩余的语句，但会忽略它遇到的任何错误。</span><span class="sxs-lookup"><span data-stu-id="7b876-110">If you don't dispose a data reader, the finalizer tries to execute the remaining statements, but any errors it encounters are ignored.</span></span> <span data-ttu-id="7b876-111">因此，在使用批处理时释放 `DbDataReader` 对象非常重要。</span><span class="sxs-lookup"><span data-stu-id="7b876-111">Because of this, it's important to dispose `DbDataReader` objects when using batches.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a><span data-ttu-id="7b876-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b876-112">See also</span></span>

* [<span data-ttu-id="7b876-113">大容量插入</span><span class="sxs-lookup"><span data-stu-id="7b876-113">Bulk Insert</span></span>](bulk-insert.md)
