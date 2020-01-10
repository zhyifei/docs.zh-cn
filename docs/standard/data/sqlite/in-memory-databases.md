---
title: 内存中数据库
ms.date: 12/13/2019
description: 了解如何使用内存中 SQLite 数据库。
ms.openlocfilehash: 16a9b6536fbfede203c24b757e96e28e7c49dc05
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777415"
---
# <a name="in-memory-databases"></a><span data-ttu-id="81812-103">内存中数据库</span><span class="sxs-lookup"><span data-stu-id="81812-103">In-memory databases</span></span>

<span data-ttu-id="81812-104">SQLite 内存中数据库完全存储在内存中，而不是存储在磁盘上。</span><span class="sxs-lookup"><span data-stu-id="81812-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="81812-105">使用特殊的数据源文件名 `:memory:` 来创建内存中数据库。</span><span class="sxs-lookup"><span data-stu-id="81812-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="81812-106">连接关闭后，该数据库将被删除。</span><span class="sxs-lookup"><span data-stu-id="81812-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="81812-107">使用 `:memory:`时，每个连接都将创建其自己的数据库。</span><span class="sxs-lookup"><span data-stu-id="81812-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="81812-108">可共享的内存中数据库</span><span class="sxs-lookup"><span data-stu-id="81812-108">Shareable in-memory databases</span></span>

<span data-ttu-id="81812-109">在连接字符串中使用 `Mode=Memory` 和 `Cache=Shared`，可以在多个连接之间共享内存中数据库。</span><span class="sxs-lookup"><span data-stu-id="81812-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="81812-110">`Data Source` 关键字用于为内存中数据库指定一个名称。</span><span class="sxs-lookup"><span data-stu-id="81812-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="81812-111">使用相同名称的连接字符串将访问相同的内存中数据库。</span><span class="sxs-lookup"><span data-stu-id="81812-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="81812-112">只要至少有一个连接保持打开状态，数据库就会保持不变。</span><span class="sxs-lookup"><span data-stu-id="81812-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="81812-113">GitHub 上提供了演示此功能的[示例](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/InMemorySample/Program.cs)。</span><span class="sxs-lookup"><span data-stu-id="81812-113">A [sample](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
