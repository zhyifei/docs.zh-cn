---
title: 内存中数据库
ms.date: 12/13/2019
description: 了解如何使用内存中 SQLite 数据库。
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391203"
---
# <a name="in-memory-databases"></a><span data-ttu-id="655e0-103">内存中数据库</span><span class="sxs-lookup"><span data-stu-id="655e0-103">In-memory databases</span></span>

<span data-ttu-id="655e0-104">SQLite 内存中数据库是完全存储在内存中的数据库，而不是存储在磁盘上。</span><span class="sxs-lookup"><span data-stu-id="655e0-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="655e0-105">使用特殊的数据源文件名`:memory:`创建内存中数据库。</span><span class="sxs-lookup"><span data-stu-id="655e0-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="655e0-106">关闭连接时，将删除数据库。</span><span class="sxs-lookup"><span data-stu-id="655e0-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="655e0-107">使用`:memory:`时，每个连接将创建其自己的数据库。</span><span class="sxs-lookup"><span data-stu-id="655e0-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="655e0-108">可共享内存中数据库</span><span class="sxs-lookup"><span data-stu-id="655e0-108">Shareable in-memory databases</span></span>

<span data-ttu-id="655e0-109">内存中数据库可以通过使用`Mode=Memory`和`Cache=Shared`在连接字符串中在多个连接之间共享。</span><span class="sxs-lookup"><span data-stu-id="655e0-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="655e0-110">关键字`Data Source`用于为内存中数据库指定名称。</span><span class="sxs-lookup"><span data-stu-id="655e0-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="655e0-111">使用相同名称的连接字符串将访问相同的内存内数据库。</span><span class="sxs-lookup"><span data-stu-id="655e0-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="655e0-112">只要数据库至少保持一个连接保持打开状态，数据库就将保持不变。</span><span class="sxs-lookup"><span data-stu-id="655e0-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="655e0-113">GitHub 上提供了演示此[示例](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs)。</span><span class="sxs-lookup"><span data-stu-id="655e0-113">A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
