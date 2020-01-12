---
title: 与 System.object 的比较
ms.date: 12/13/2019
description: 描述了 Microsoft 数据库和 System.object 库之间的一些差异。
ms.openlocfilehash: 076bbc6f746cf9296c96ec73047397a21a3b2558
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900715"
---
# <a name="comparison-to-systemdatasqlite"></a><span data-ttu-id="4893e-103">与 System.object 的比较</span><span class="sxs-lookup"><span data-stu-id="4893e-103">Comparison to System.Data.SQLite</span></span>

<span data-ttu-id="4893e-104">在2005中，Robert Simpson 创建了一个 ADO.NET 2.0 的 SQLite 提供程序。</span><span class="sxs-lookup"><span data-stu-id="4893e-104">In 2005, Robert Simpson created System.Data.SQLite, a SQLite provider for ADO.NET 2.0.</span></span> <span data-ttu-id="4893e-105">在2010中，SQLite 团队接管了项目的维护和开发工作。</span><span class="sxs-lookup"><span data-stu-id="4893e-105">In 2010, the SQLite team took over maintenance and development of the project.</span></span> <span data-ttu-id="4893e-106">还值得注意的是，Mono 团队将2007中的代码分叉为单声道。</span><span class="sxs-lookup"><span data-stu-id="4893e-106">It's also worth noting that the Mono team forked the code in 2007 as Mono.Data.Sqlite.</span></span> <span data-ttu-id="4893e-107">ADO.NET 具有较长的历史记录，并已发展为完整的、功能齐全的提供程序，并具有 Visual Studio 工具。</span><span class="sxs-lookup"><span data-stu-id="4893e-107">System.Data.SQLite has a long history and has evolved into a stable and full-featured ADO.NET provider complete with Visual Studio tooling.</span></span> <span data-ttu-id="4893e-108">新版本会继续将与每个版本的 .NET Framework 兼容的程序集传送回版本2.0，甚至 .NET Compact Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="4893e-108">New releases continue to ship assemblies compatible with every version of .NET Framework back to version 2.0 and even .NET Compact Framework 3.5.</span></span>

<span data-ttu-id="4893e-109">.NET Core 的第一个版本（在2016中发布）是 .NET 的单个、轻型、新式和跨平台实现。</span><span class="sxs-lookup"><span data-stu-id="4893e-109">The first version of .NET Core (released in 2016) was a single, lightweight, modern, and cross-platform implementation of .NET.</span></span> <span data-ttu-id="4893e-110">特意删除了具有更多新式替代项的过时 Api 和 Api。</span><span class="sxs-lookup"><span data-stu-id="4893e-110">Obsolete APIs and APIs with more modern alternatives were intentionally removed.</span></span> <span data-ttu-id="4893e-111">ADO.NET 不包括任何数据集 Api （包括 DataTable 和 DataAdapter）。</span><span class="sxs-lookup"><span data-stu-id="4893e-111">ADO.NET didn't include any of the DataSet APIs (including DataTable and DataAdapter).</span></span>

<span data-ttu-id="4893e-112">实体框架团队在某种程度上熟悉了 system.exception 基本代码。</span><span class="sxs-lookup"><span data-stu-id="4893e-112">The Entity Framework team was somewhat familiar with the System.Data.SQLite codebase.</span></span> <span data-ttu-id="4893e-113">Brice Lambson 是 EF 团队的成员，以前已帮助 SQLite 团队添加对实体框架版本5和6的支持。</span><span class="sxs-lookup"><span data-stu-id="4893e-113">Brice Lambson, a member of the EF team, had previously helped the SQLite team add support for Entity Framework versions 5 and 6.</span></span> <span data-ttu-id="4893e-114">此外，Brice 还试验了其在计划 .NET Core 的同时，其自己的 SQLite ADO.NET 提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="4893e-114">Brice was also experimenting with his own implementation of a SQLite ADO.NET provider around the same time that .NET Core was being planned.</span></span> <span data-ttu-id="4893e-115">在长时间讨论后，实体框架团队决定根据 Brice 的原型创建。</span><span class="sxs-lookup"><span data-stu-id="4893e-115">After a long discussion, the Entity Framework team decided to create Microsoft.Data.Sqlite based on Brice's prototype.</span></span> <span data-ttu-id="4893e-116">这使他们能够创建新的轻型和新式实现，使其与 .NET Core 的目标保持一致。</span><span class="sxs-lookup"><span data-stu-id="4893e-116">This would allow them to create a new lightweight and modern implementation that would align with the goals of .NET Core.</span></span>

<span data-ttu-id="4893e-117">作为我们所说的更多新式的示例，这里是在 system.exception 和数据表中创建[用户定义函数](user-defined-functions.md)的代码。</span><span class="sxs-lookup"><span data-stu-id="4893e-117">As an example of what we mean by more modern, here is code to create a [user-defined function](user-defined-functions.md) in both System.Data.SQLite and Microsoft.Data.Sqlite.</span></span>

```csharp
// System.Data.SQLite
connection.BindFunction(
    new SQLiteFunctionAttribute("ceiling", 1, FunctionType.Scalar),
    (Func<object[], object>)((object[] args) => Math.Ceiling((double)((object[])args[1])[0])),
    null);

// Microsoft.Data.Sqlite
connection.CreateFunction(
    "ceiling",
    (double arg) => Math.Ceiling(arg));
```

<span data-ttu-id="4893e-118">在2017中，.NET Core 2.0 经历了策略更改。</span><span class="sxs-lookup"><span data-stu-id="4893e-118">In 2017, .NET Core 2.0 experienced a change in strategy.</span></span> <span data-ttu-id="4893e-119">它决定了与 .NET Framework 的兼容性对于 .NET Core 的成功至关重要。</span><span class="sxs-lookup"><span data-stu-id="4893e-119">It was decided that compatibility with .NET Framework was vital to the success of .NET Core.</span></span> <span data-ttu-id="4893e-120">许多已删除的 Api （包括数据集 Api）已添加回。</span><span class="sxs-lookup"><span data-stu-id="4893e-120">Many of the removed APIs, including the DataSet APIs, were added back.</span></span> <span data-ttu-id="4893e-121">与许多其他方法一样，这种解除阻止的 System.object 也允许它移植到 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="4893e-121">Like it did for many others, this unblocked System.Data.SQLite allowing it to also be ported to .NET Core.</span></span> <span data-ttu-id="4893e-122">然而，在轻型和新式情况下，Microsoft 数据的原始目标仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="4893e-122">The original goal of Microsoft.Data.Sqlite to be lightweight and modern, however, still remains.</span></span> <span data-ttu-id="4893e-123">有关不是由 ADO.NET 实现的 ADO.NET Api 的详细信息，请参阅相关[限制](adonet-limitations.md)。</span><span class="sxs-lookup"><span data-stu-id="4893e-123">See [ADO.NET limitations](adonet-limitations.md) for details about ADO.NET APIs not implemented by Microsoft.Data.Sqlite.</span></span>

<span data-ttu-id="4893e-124">将新功能添加到了 node.js 后，会考虑到系统的设计。</span><span class="sxs-lookup"><span data-stu-id="4893e-124">When new features are added to Microsoft.Data.Sqlite, the design of System.Data.SQLite is taken into account.</span></span> <span data-ttu-id="4893e-125">尽可能将两个更改减至最小，以便在两者之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="4893e-125">We try, when possible, to minimize changes between the two to ease transitioning between them.</span></span>

## <a name="data-types"></a><span data-ttu-id="4893e-126">数据类型</span><span class="sxs-lookup"><span data-stu-id="4893e-126">Data types</span></span>

<span data-ttu-id="4893e-127">数据类型的处理方式与数据类型的处理方式最大。</span><span class="sxs-lookup"><span data-stu-id="4893e-127">The biggest difference between Microsoft.Data.Sqlite and System.Data.SQLite is how data types are handled.</span></span> <span data-ttu-id="4893e-128">如[数据类型](types.md)中所述，quirkiness 不会尝试隐藏 Sqlite 的基础，这允许将任意字符串指定为列类型，并且只有四个基元类型：整数、实数、文本和 BLOB。</span><span class="sxs-lookup"><span data-stu-id="4893e-128">As described in [Data types](types.md), Microsoft.Data.Sqlite doesn't try to hide the underlying quirkiness of SQLite, which allows any arbitrary string to be specified as the column type, and only has four primitive types: INTEGER, REAL, TEXT, and BLOB.</span></span>

<span data-ttu-id="4893e-129">对于列类型，则将其他语义直接映射到 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="4893e-129">System.Data.SQLite applies additional semantics to column types mapping them directly to .NET types.</span></span> <span data-ttu-id="4893e-130">这为提供程序提供了一种更强类型的外观，但它具有一些粗糙的边缘。</span><span class="sxs-lookup"><span data-stu-id="4893e-130">This gives the provider a more strongly typed feel, but it has some rough edges.</span></span> <span data-ttu-id="4893e-131">例如，它们必须引入一个新的 SQL 语句（类型）来指定 SELECT 语句中表达式的列类型。</span><span class="sxs-lookup"><span data-stu-id="4893e-131">For example, they had to introduce a new SQL statement (TYPES) to specify the column types of expressions in SELECT statements.</span></span>

## <a name="connection-strings"></a><span data-ttu-id="4893e-132">连接字符串</span><span class="sxs-lookup"><span data-stu-id="4893e-132">Connection strings</span></span>

<span data-ttu-id="4893e-133">-Sqlite 的[连接字符串](connection-strings.md)关键字少很多。</span><span class="sxs-lookup"><span data-stu-id="4893e-133">Microsoft.Data.Sqlite has a lot fewer [connection string](connection-strings.md) keywords.</span></span> <span data-ttu-id="4893e-134">下表显示了可改为使用的替代项。</span><span class="sxs-lookup"><span data-stu-id="4893e-134">The following table shows alternatives that can be used instead.</span></span>

| <span data-ttu-id="4893e-135">关键字</span><span class="sxs-lookup"><span data-stu-id="4893e-135">Keyword</span></span>          | <span data-ttu-id="4893e-136">替代项</span><span class="sxs-lookup"><span data-stu-id="4893e-136">Alternative</span></span>                                         |
| ---------------- | --------------------------------------------------- |
| <span data-ttu-id="4893e-137">缓存大小</span><span class="sxs-lookup"><span data-stu-id="4893e-137">Cache Size</span></span>       | <span data-ttu-id="4893e-138">发送 `PRAGMA cache_size = <pages>`</span><span class="sxs-lookup"><span data-stu-id="4893e-138">Send `PRAGMA cache_size = <pages>`</span></span>                  |
| <span data-ttu-id="4893e-139">默认超时</span><span class="sxs-lookup"><span data-stu-id="4893e-139">Default Timeout</span></span>  | <span data-ttu-id="4893e-140">使用 SqliteConnection 上的 DefaultTimeout 属性</span><span class="sxs-lookup"><span data-stu-id="4893e-140">Use the DefaultTimeout property on SqliteConnection</span></span> |
| <span data-ttu-id="4893e-141">FailIfMissing</span><span class="sxs-lookup"><span data-stu-id="4893e-141">FailIfMissing</span></span>    | <span data-ttu-id="4893e-142">使用 `Mode=ReadWrite`</span><span class="sxs-lookup"><span data-stu-id="4893e-142">Use `Mode=ReadWrite`</span></span>                                |
| <span data-ttu-id="4893e-143">FullUri</span><span class="sxs-lookup"><span data-stu-id="4893e-143">FullUri</span></span>          | <span data-ttu-id="4893e-144">使用数据源关键字</span><span class="sxs-lookup"><span data-stu-id="4893e-144">Use the Data Source keyword</span></span>                         |
| <span data-ttu-id="4893e-145">日志模式</span><span class="sxs-lookup"><span data-stu-id="4893e-145">Journal Mode</span></span>     | <span data-ttu-id="4893e-146">发送 `PRAGMA journal_mode = <mode>`</span><span class="sxs-lookup"><span data-stu-id="4893e-146">Send `PRAGMA journal_mode = <mode>`</span></span>                 |
| <span data-ttu-id="4893e-147">旧格式</span><span class="sxs-lookup"><span data-stu-id="4893e-147">Legacy Format</span></span>    | <span data-ttu-id="4893e-148">发送 `PRAGMA legacy_file_format = 1`</span><span class="sxs-lookup"><span data-stu-id="4893e-148">Send `PRAGMA legacy_file_format = 1`</span></span>                |
| <span data-ttu-id="4893e-149">最大页计数</span><span class="sxs-lookup"><span data-stu-id="4893e-149">Max Page Count</span></span>   | <span data-ttu-id="4893e-150">发送 `PRAGMA max_page_count = <pages>`</span><span class="sxs-lookup"><span data-stu-id="4893e-150">Send `PRAGMA max_page_count = <pages>`</span></span>              |
| <span data-ttu-id="4893e-151">页面大小</span><span class="sxs-lookup"><span data-stu-id="4893e-151">Page Size</span></span>        | <span data-ttu-id="4893e-152">发送 `PRAGMA page_size = <bytes>`</span><span class="sxs-lookup"><span data-stu-id="4893e-152">Send `PRAGMA page_size = <bytes>`</span></span>                   |
| <span data-ttu-id="4893e-153">只读</span><span class="sxs-lookup"><span data-stu-id="4893e-153">Read Only</span></span>        | <span data-ttu-id="4893e-154">使用 `Mode=ReadOnly`</span><span class="sxs-lookup"><span data-stu-id="4893e-154">Use `Mode=ReadOnly`</span></span>                                 |
| <span data-ttu-id="4893e-155">Synchronous</span><span class="sxs-lookup"><span data-stu-id="4893e-155">Synchronous</span></span>      | <span data-ttu-id="4893e-156">发送 `PRAGMA synchronous = <mode>`</span><span class="sxs-lookup"><span data-stu-id="4893e-156">Send `PRAGMA synchronous = <mode>`</span></span>                  |
| <span data-ttu-id="4893e-157">URI</span><span class="sxs-lookup"><span data-stu-id="4893e-157">Uri</span></span>              | <span data-ttu-id="4893e-158">使用数据源关键字</span><span class="sxs-lookup"><span data-stu-id="4893e-158">Use the Data Source keyword</span></span>                         |
| <span data-ttu-id="4893e-159">UseUTF16Encoding</span><span class="sxs-lookup"><span data-stu-id="4893e-159">UseUTF16Encoding</span></span> | <span data-ttu-id="4893e-160">发送 `PRAGMA encoding = 'UTF-16'`</span><span class="sxs-lookup"><span data-stu-id="4893e-160">Send `PRAGMA encoding = 'UTF-16'`</span></span>                   |

## <a name="authorization"></a><span data-ttu-id="4893e-161">授权</span><span class="sxs-lookup"><span data-stu-id="4893e-161">Authorization</span></span>

<span data-ttu-id="4893e-162">Node.js 没有任何 API 公开 SQLite 的授权回调。</span><span class="sxs-lookup"><span data-stu-id="4893e-162">Microsoft.Data.Sqlite doesn't have any API exposing SQLite's authorization callback.</span></span> <span data-ttu-id="4893e-163">使用问题[#13835](https://github.com/dotnet/efcore/issues/13835)提供有关此功能的反馈。</span><span class="sxs-lookup"><span data-stu-id="4893e-163">Use issue [#13835](https://github.com/dotnet/efcore/issues/13835) to provide feedback about this feature.</span></span>

## <a name="data-change-notifications"></a><span data-ttu-id="4893e-164">数据更改通知</span><span class="sxs-lookup"><span data-stu-id="4893e-164">Data change notifications</span></span>

<span data-ttu-id="4893e-165">Node.js 没有任何 API 公开 SQLite 的数据更改通知。</span><span class="sxs-lookup"><span data-stu-id="4893e-165">Microsoft.Data.Sqlite doesn't have any API exposing SQLite's data change notifications.</span></span> <span data-ttu-id="4893e-166">使用问题[#13827](https://github.com/dotnet/efcore/issues/13827)提供有关此功能的反馈。</span><span class="sxs-lookup"><span data-stu-id="4893e-166">Use issue [#13827](https://github.com/dotnet/efcore/issues/13827) to provide feedback about this feature.</span></span>

## <a name="virtual-table-modules"></a><span data-ttu-id="4893e-167">虚拟表模块</span><span class="sxs-lookup"><span data-stu-id="4893e-167">Virtual table modules</span></span>

<span data-ttu-id="4893e-168">Node.js 没有用于创建虚拟表模块的任何 API。</span><span class="sxs-lookup"><span data-stu-id="4893e-168">Microsoft.Data.Sqlite doesn't have any API for creating virtual table modules.</span></span> <span data-ttu-id="4893e-169">使用问题[#13823](https://github.com/dotnet/efcore/issues/13823)提供有关此功能的反馈。</span><span class="sxs-lookup"><span data-stu-id="4893e-169">Use issue [#13823](https://github.com/dotnet/efcore/issues/13823) to provide feedback about this feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="4893e-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4893e-170">See also</span></span>

* [<span data-ttu-id="4893e-171">数据类型</span><span class="sxs-lookup"><span data-stu-id="4893e-171">Data types</span></span>](types.md)
* [<span data-ttu-id="4893e-172">连接字符串</span><span class="sxs-lookup"><span data-stu-id="4893e-172">Connection strings</span></span>](connection-strings.md)
* [<span data-ttu-id="4893e-173">加密</span><span class="sxs-lookup"><span data-stu-id="4893e-173">Encryption</span></span>](encryption.md)
* [<span data-ttu-id="4893e-174">ADO.NET 限制</span><span class="sxs-lookup"><span data-stu-id="4893e-174">ADO.NET limitations</span></span>](adonet-limitations.md)
* [<span data-ttu-id="4893e-175">Dapper 限制</span><span class="sxs-lookup"><span data-stu-id="4893e-175">Dapper limitations</span></span>](dapper-limitations.md)
