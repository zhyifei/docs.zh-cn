---
title: 互操作性
ms.date: 12/13/2019
description: 了解如何与其他 SQLite 库进行互操作。
ms.openlocfilehash: 486e2a8e00999b8ebe9c85a5fcc1539c514676d3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450458"
---
# <a name="interoperability"></a><span data-ttu-id="3aced-103">互操作性</span><span class="sxs-lookup"><span data-stu-id="3aced-103">Interoperability</span></span>

<span data-ttu-id="3aced-104">Microsoft.Data.Sqlite 使用 SQLitePCLRaw 与本机 SQLite 库交互。</span><span class="sxs-lookup"><span data-stu-id="3aced-104">Microsoft.Data.Sqlite uses SQLitePCLRaw to interact with the native SQLite library.</span></span> <span data-ttu-id="3aced-105">SQLitePCLRaw 通过本机 SQLite API 提供一个精简 .NET API。</span><span class="sxs-lookup"><span data-stu-id="3aced-105">SQLitePCLRaw provides a thin .NET API over the native SQLite API.</span></span> <span data-ttu-id="3aced-106">SqliteConnection 和 SqliteDataReader 提供对基础 SQLitePCLRaw 对象的访问权限，允许你直接调用这些 API。</span><span class="sxs-lookup"><span data-stu-id="3aced-106">SqliteConnection and SqliteDataReader provide access to the underlying SQLitePCLRaw objects letting you call these APIs directly.</span></span>

<span data-ttu-id="3aced-107">下面的示例演示如何调用 `sqlite3_trace` 以将已执行的 SQL 语句写入控制台：</span><span class="sxs-lookup"><span data-stu-id="3aced-107">The following example shows how to call `sqlite3_trace` to write executed SQL statements to the console:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

<span data-ttu-id="3aced-108">下面的示例演示如何调用 `sqlite3_stmt_status` 来查看 SQL 语句编译为多少个 SQLite 虚拟机步骤：</span><span class="sxs-lookup"><span data-stu-id="3aced-108">And the following example shows calling `sqlite3_stmt_status` to see how many SQLite virtual machine steps a SQL statement compiled into:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

<span data-ttu-id="3aced-109">SQLitePCLRaw 对象甚至公开指向本地对象的指针，使你可以 P/Invoke 其他本机 SQLite API。</span><span class="sxs-lookup"><span data-stu-id="3aced-109">The SQLitePCLRaw objects even expose a pointer to the native objects letting you P/Invoke additional native SQLite APIs.</span></span>
