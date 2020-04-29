---
title: 内存中数据库
ms.date: 12/13/2019
description: 了解如何使用内存中 SQLite 数据库。
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391203"
---
# <a name="in-memory-databases"></a><span data-ttu-id="a5f9c-103">内存中数据库</span><span class="sxs-lookup"><span data-stu-id="a5f9c-103">In-memory databases</span></span>

<span data-ttu-id="a5f9c-104">SQLite 内存中数据库是完全存储在内存中（而不是磁盘上）的数据库。</span><span class="sxs-lookup"><span data-stu-id="a5f9c-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="a5f9c-105">使用特殊数据源文件名 `:memory:` 可创建内存中数据库。</span><span class="sxs-lookup"><span data-stu-id="a5f9c-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="a5f9c-106">连接关闭后，数据库会被删除。</span><span class="sxs-lookup"><span data-stu-id="a5f9c-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="a5f9c-107">使用 `:memory:` 时，每个连接都会创建自己的数据库。</span><span class="sxs-lookup"><span data-stu-id="a5f9c-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="a5f9c-108">可共享的内存中数据库</span><span class="sxs-lookup"><span data-stu-id="a5f9c-108">Shareable in-memory databases</span></span>

<span data-ttu-id="a5f9c-109">在连接字符串中使用 `Mode=Memory` 和 `Cache=Shared` 可以在多个连接之间共享内存中数据库。</span><span class="sxs-lookup"><span data-stu-id="a5f9c-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="a5f9c-110">`Data Source` 关键字用于为内存中数据库提供名称。</span><span class="sxs-lookup"><span data-stu-id="a5f9c-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="a5f9c-111">使用相同名称的连接字符串将访问相同的内存中数据库。</span><span class="sxs-lookup"><span data-stu-id="a5f9c-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="a5f9c-112">只要至少有一个与之相连的连接保持打开状态，数据库便会保持。</span><span class="sxs-lookup"><span data-stu-id="a5f9c-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="a5f9c-113">GitHub 上提供了对此进行演示的[示例](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs)。</span><span class="sxs-lookup"><span data-stu-id="a5f9c-113">A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
