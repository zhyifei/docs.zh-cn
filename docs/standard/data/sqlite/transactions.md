---
title: 事务
ms.date: 12/13/2019
description: 了解如何使用事务。
ms.openlocfilehash: 4b72a1573a560ffd1bfd0f54d46ab3b135280976
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450380"
---
# <a name="transactions"></a><span data-ttu-id="f4f06-103">事务</span><span class="sxs-lookup"><span data-stu-id="f4f06-103">Transactions</span></span>

<span data-ttu-id="f4f06-104">通过事务可以将多个 SQL 语句组合成一个工作单元，并将其作为一个原子单元提交到数据库。</span><span class="sxs-lookup"><span data-stu-id="f4f06-104">Transactions let you group multiple SQL statements into a single unit of work that is committed to the database as one atomic unit.</span></span> <span data-ttu-id="f4f06-105">如果事务中的任何语句失败，可以回滚前面语句所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f4f06-105">If any statement in the transaction fails, changes made by the previous statements can be rolled back.</span></span> <span data-ttu-id="f4f06-106">事务启动时的数据库初始状态会予以保留。</span><span class="sxs-lookup"><span data-stu-id="f4f06-106">The initial state of the database when the transaction was started is preserved.</span></span> <span data-ttu-id="f4f06-107">当一次对数据库进行大量修改时，使用事务也可以提高 SQLite 上的性能。</span><span class="sxs-lookup"><span data-stu-id="f4f06-107">Using a transaction can also improve performance on SQLite when making numerous changes to the database at once.</span></span>

## <a name="concurrency"></a><span data-ttu-id="f4f06-108">并发</span><span class="sxs-lookup"><span data-stu-id="f4f06-108">Concurrency</span></span>

<span data-ttu-id="f4f06-109">在 SQLite 中，数据库中一次只允许有一个事务具有挂起的更改。</span><span class="sxs-lookup"><span data-stu-id="f4f06-109">In SQLite, only one transaction is allowed to have changes pending in the database at a time.</span></span> <span data-ttu-id="f4f06-110">因此，如果另一个事务需要很长时间才能完成，则对 <xref:Microsoft.Data.Sqlite.SqliteCommand> 调用 <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> 和 `Execute` 方法可能会超时。</span><span class="sxs-lookup"><span data-stu-id="f4f06-110">Because of this, calls to <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> and the `Execute` methods on <xref:Microsoft.Data.Sqlite.SqliteCommand> may time out if another transaction takes too long to complete.</span></span>

<span data-ttu-id="f4f06-111">有关锁定、重试和超时的详细信息，请参阅[数据库错误](database-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="f4f06-111">For more information about locking, retries, and timeouts, see [Database errors](database-errors.md).</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="f4f06-112">隔离级别</span><span class="sxs-lookup"><span data-stu-id="f4f06-112">Isolation levels</span></span>

<span data-ttu-id="f4f06-113">默认情况下，在 SQLite 中，事务是**可序列化**的。</span><span class="sxs-lookup"><span data-stu-id="f4f06-113">Transactions are **serializable** by default in SQLite.</span></span> <span data-ttu-id="f4f06-114">此隔离级别可确保完全隔离事务中所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="f4f06-114">This isolation level guarantees that any changes made within a transaction are completely isolated.</span></span> <span data-ttu-id="f4f06-115">在事务之外执行的其他语句不受事务更改的影响。</span><span class="sxs-lookup"><span data-stu-id="f4f06-115">Other statements executed outside of the transaction aren't affected by the transaction's changes.</span></span>

<span data-ttu-id="f4f06-116">SQLite 还支持在使用共享缓存时读取未提交的内容  。</span><span class="sxs-lookup"><span data-stu-id="f4f06-116">SQLite also supports **read uncommitted** when using a shared cache.</span></span> <span data-ttu-id="f4f06-117">此级别允许脏读、不可重复读和幻像：</span><span class="sxs-lookup"><span data-stu-id="f4f06-117">This level allows dirty reads, nonrepeatable reads, and phantoms:</span></span>

- <span data-ttu-id="f4f06-118">当事务外部的查询返回一个事务中挂起的更改，但事务中的更改被回滚时，会发生“脏读”  。</span><span class="sxs-lookup"><span data-stu-id="f4f06-118">A *dirty read* occurs when changes pending in one transaction are returned by a query outside of the transaction, but the changes in the transaction are rolled back.</span></span> <span data-ttu-id="f4f06-119">结果包含从不实际提交到数据库的数据。</span><span class="sxs-lookup"><span data-stu-id="f4f06-119">The results contain data that was never actually committed to the database.</span></span>

- <span data-ttu-id="f4f06-120">如果某一事务两次查询相同的行，但由于在两个查询之间另一个事务进行了更改导致结果不同，这时会发生“不可重复读”  。</span><span class="sxs-lookup"><span data-stu-id="f4f06-120">A *nonrepeatable read* occurs when a transaction queries same row twice, but the results are different because it was changed between the two queries by another transaction.</span></span>

- <span data-ttu-id="f4f06-121">“幻像”  在事务过程中为满足查询的 where 子句而更改或添加的行。</span><span class="sxs-lookup"><span data-stu-id="f4f06-121">*Phantoms* are rows that get changed or added to meet the where clause of a query during a transaction.</span></span> <span data-ttu-id="f4f06-122">如果允许的话，同一查询在同一事务中执行两次时可能返回不同的行。</span><span class="sxs-lookup"><span data-stu-id="f4f06-122">If allowed, the same query could return different rows when executed twice in the same transaction.</span></span>

<span data-ttu-id="f4f06-123">Microsoft.Data.Sqlite 将传递给 <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> 的 IsolationLevel 视为最低级别。</span><span class="sxs-lookup"><span data-stu-id="f4f06-123">Microsoft.Data.Sqlite treats the IsolationLevel passed to <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> as a minimum level.</span></span> <span data-ttu-id="f4f06-124">实际隔离级别将提升为读取未提交内容或可序列化。</span><span class="sxs-lookup"><span data-stu-id="f4f06-124">The actual isolation level will be promoted to either read uncommitted or serializable.</span></span>

<span data-ttu-id="f4f06-125">下面的代码模拟脏读。</span><span class="sxs-lookup"><span data-stu-id="f4f06-125">The following code simulates a dirty read.</span></span> <span data-ttu-id="f4f06-126">请注意，连接字符串必须包含 `Cache=Shared`。</span><span class="sxs-lookup"><span data-stu-id="f4f06-126">Note, the connection string must include `Cache=Shared`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DirtyReadSample/Program.cs?name=snippet_DirtyRead)]
