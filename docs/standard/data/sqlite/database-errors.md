---
title: 数据库错误
ms.date: 12/13/2019
description: 介绍库如何处理数据库错误和停用。
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450488"
---
# <a name="database-errors"></a><span data-ttu-id="9d91d-103">数据库错误</span><span class="sxs-lookup"><span data-stu-id="9d91d-103">Database errors</span></span>

<span data-ttu-id="9d91d-104">遇到 SQLite 错误时会引发 <xref:Microsoft.Data.Sqlite.SqliteException>。</span><span class="sxs-lookup"><span data-stu-id="9d91d-104"><xref:Microsoft.Data.Sqlite.SqliteException> is thrown when a SQLite error is encountered.</span></span> <span data-ttu-id="9d91d-105">消息由 SQLite 提供。</span><span class="sxs-lookup"><span data-stu-id="9d91d-105">The message is provided by SQLite.</span></span> <span data-ttu-id="9d91d-106">`SqliteErrorCode` 和 `SqliteExtendedErrorCode` 属性包含错误的 SQLite [结果代码](https://www.sqlite.org/rescode.html)。</span><span class="sxs-lookup"><span data-stu-id="9d91d-106">The `SqliteErrorCode` and `SqliteExtendedErrorCode` properties contain the SQLite [result code](https://www.sqlite.org/rescode.html) of the error.</span></span>

<span data-ttu-id="9d91d-107">在 Microsoft.Data.Sqlite 与本机 SQLite 库进行交互的任何时候，都可能会遇到错误。</span><span class="sxs-lookup"><span data-stu-id="9d91d-107">Errors may be encountered any time the Microsoft.Data.Sqlite interacts with the native SQLite library.</span></span> <span data-ttu-id="9d91d-108">以下列表显示可能发生错误的常见情况：</span><span class="sxs-lookup"><span data-stu-id="9d91d-108">The following list shows the common scenarios where errors can occur:</span></span>

* <span data-ttu-id="9d91d-109">打开连接。</span><span class="sxs-lookup"><span data-stu-id="9d91d-109">Opening a connection.</span></span>
* <span data-ttu-id="9d91d-110">启动事务。</span><span class="sxs-lookup"><span data-stu-id="9d91d-110">Beginning a transaction.</span></span>
* <span data-ttu-id="9d91d-111">执行命令。</span><span class="sxs-lookup"><span data-stu-id="9d91d-111">Executing a command.</span></span>
* <span data-ttu-id="9d91d-112">调用 <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>。</span><span class="sxs-lookup"><span data-stu-id="9d91d-112">Calling <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.</span></span>

<span data-ttu-id="9d91d-113">仔细考虑应用将如何处理这些错误。</span><span class="sxs-lookup"><span data-stu-id="9d91d-113">Consider carefully how your app will handle these errors.</span></span>

## <a name="locking-retries-and-timeouts"></a><span data-ttu-id="9d91d-114">锁定、重试和超时</span><span class="sxs-lookup"><span data-stu-id="9d91d-114">Locking, retries, and timeouts</span></span>

<span data-ttu-id="9d91d-115">当涉及锁定表和数据库文件时，SQLite 会比较主动。</span><span class="sxs-lookup"><span data-stu-id="9d91d-115">SQLite is aggressive when it comes to locking tables and database files.</span></span> <span data-ttu-id="9d91d-116">如果应用启用了任何并发数据库访问，则可能会遇到繁忙和锁定错误。</span><span class="sxs-lookup"><span data-stu-id="9d91d-116">If your app enables any concurrent database access, you'll likely encounter busy and locked errors.</span></span> <span data-ttu-id="9d91d-117">可以使用[共享缓存](connection-strings.md#cache)和[预写日志记录](async.md)来缓解大量错误。</span><span class="sxs-lookup"><span data-stu-id="9d91d-117">You can mitigate many errors by using a [shared cache](connection-strings.md#cache) and [write-ahead logging](async.md).</span></span>

<span data-ttu-id="9d91d-118">每当 Microsoft.Data.Sqlite 遇到繁忙或锁定错误时，它会自动重试，直到它成功或达到命令超时值。</span><span class="sxs-lookup"><span data-stu-id="9d91d-118">Whenever Microsoft.Data.Sqlite encounters a busy or locked error, it will automatically retry until it succeeds or the command timeout is reached.</span></span>

<span data-ttu-id="9d91d-119">可以通过设置 <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A> 来增加命令的超时值。</span><span class="sxs-lookup"><span data-stu-id="9d91d-119">You can increase the timeout of command by setting <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>.</span></span> <span data-ttu-id="9d91d-120">默认超时值为 30 秒。</span><span class="sxs-lookup"><span data-stu-id="9d91d-120">The default timeout is 30 seconds.</span></span> <span data-ttu-id="9d91d-121">值 `0` 意味着无超时。</span><span class="sxs-lookup"><span data-stu-id="9d91d-121">A value of `0` means no timeout.</span></span>

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

<span data-ttu-id="9d91d-122">Microsoft.Data.Sqlite 有时需要创建隐式命令对象。</span><span class="sxs-lookup"><span data-stu-id="9d91d-122">Microsoft.Data.Sqlite sometimes needs to create an implicit command object.</span></span> <span data-ttu-id="9d91d-123">例如，在 BeginTransaction 期间。</span><span class="sxs-lookup"><span data-stu-id="9d91d-123">For example, during BeginTransaction.</span></span> <span data-ttu-id="9d91d-124">若要为这些命令设置超时值，请使用 <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>。</span><span class="sxs-lookup"><span data-stu-id="9d91d-124">To set the timeout for these commands, use <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.</span></span>

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a><span data-ttu-id="9d91d-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d91d-125">See also</span></span>

* [<span data-ttu-id="9d91d-126">SQLite 错误代码</span><span class="sxs-lookup"><span data-stu-id="9d91d-126">SQLite Error Codes</span></span>](https://www.sqlite.org/rescode.html)
* [<span data-ttu-id="9d91d-127">SQLite 中的文件锁定</span><span class="sxs-lookup"><span data-stu-id="9d91d-127">File Locking In SQLite</span></span>](https://www.sqlite.org/lockingv3.html)
* [<span data-ttu-id="9d91d-128">共享缓存模式</span><span class="sxs-lookup"><span data-stu-id="9d91d-128">Shared-Cache Mode</span></span>](https://www.sqlite.org/sharedcache.html)
* [<span data-ttu-id="9d91d-129">预写日志记录</span><span class="sxs-lookup"><span data-stu-id="9d91d-129">Write-Ahead Logging</span></span>](https://www.sqlite.org/wal.html)
