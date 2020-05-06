---
title: 与 System.Data.SQLite 的比较
ms.date: 12/13/2019
description: 介绍 Microsoft.Data.Sqlite 和 System.Data.SQLite 库之间的一些差异。
ms.openlocfilehash: 076bbc6f746cf9296c96ec73047397a21a3b2558
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900715"
---
# <a name="comparison-to-systemdatasqlite"></a><span data-ttu-id="b985d-103">与 System.Data.SQLite 的比较</span><span class="sxs-lookup"><span data-stu-id="b985d-103">Comparison to System.Data.SQLite</span></span>

<span data-ttu-id="b985d-104">在 2005 年，Robert Simpson 创建了System.Data.SQLite，这是 ADO.NET 2.0 的一个 SQLite 提供程序。</span><span class="sxs-lookup"><span data-stu-id="b985d-104">In 2005, Robert Simpson created System.Data.SQLite, a SQLite provider for ADO.NET 2.0.</span></span> <span data-ttu-id="b985d-105">在 2010 年，SQLite 团队接管了项目的维护和开发工作。</span><span class="sxs-lookup"><span data-stu-id="b985d-105">In 2010, the SQLite team took over maintenance and development of the project.</span></span> <span data-ttu-id="b985d-106">同样值得注意的是，Mono 团队在 2007 年以 Mono.Data.Sqlite 形式为代码创建了分支。</span><span class="sxs-lookup"><span data-stu-id="b985d-106">It's also worth noting that the Mono team forked the code in 2007 as Mono.Data.Sqlite.</span></span> <span data-ttu-id="b985d-107">System.Data.SQLite 历史悠久，并且已发展成为具有 Visual Studio 工具的稳定且功能齐全的 ADO.NET 提供程序。</span><span class="sxs-lookup"><span data-stu-id="b985d-107">System.Data.SQLite has a long history and has evolved into a stable and full-featured ADO.NET provider complete with Visual Studio tooling.</span></span> <span data-ttu-id="b985d-108">新版本会继续将与每个版本的 .NET Framework 兼容的程序集传送回版本 2.0，甚至已涉及 .NET Compact Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="b985d-108">New releases continue to ship assemblies compatible with every version of .NET Framework back to version 2.0 and even .NET Compact Framework 3.5.</span></span>

<span data-ttu-id="b985d-109">.NET Core 的第一个版本（于 2016 年发布）是 .NET 的单一轻量级跨平台新式实现。</span><span class="sxs-lookup"><span data-stu-id="b985d-109">The first version of .NET Core (released in 2016) was a single, lightweight, modern, and cross-platform implementation of .NET.</span></span> <span data-ttu-id="b985d-110">过时的 API 和具有更新式替代项的 API 均已被有意删除。</span><span class="sxs-lookup"><span data-stu-id="b985d-110">Obsolete APIs and APIs with more modern alternatives were intentionally removed.</span></span> <span data-ttu-id="b985d-111">ADO.NET 不包含任何 DataSet API（包括 DataTable 和 DataAdapter 在内）。</span><span class="sxs-lookup"><span data-stu-id="b985d-111">ADO.NET didn't include any of the DataSet APIs (including DataTable and DataAdapter).</span></span>

<span data-ttu-id="b985d-112">实体框架团队对 System.Data.SQLite 代码库多少有些熟悉。</span><span class="sxs-lookup"><span data-stu-id="b985d-112">The Entity Framework team was somewhat familiar with the System.Data.SQLite codebase.</span></span> <span data-ttu-id="b985d-113">Brice Lambson 是 EF 团队的成员，之前曾帮助 SQLite 团队添加对实体框架版本 5 和 6 的支持。</span><span class="sxs-lookup"><span data-stu-id="b985d-113">Brice Lambson, a member of the EF team, had previously helped the SQLite team add support for Entity Framework versions 5 and 6.</span></span> <span data-ttu-id="b985d-114">另外，Brice 在规划 .NET Core 的同时，还试验了自己的 SQLite ADO.NET 提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="b985d-114">Brice was also experimenting with his own implementation of a SQLite ADO.NET provider around the same time that .NET Core was being planned.</span></span> <span data-ttu-id="b985d-115">经过长时间的讨论，实体框架团队决定基于 Brice 的原型创建 Microsoft.Data.Sqlite。</span><span class="sxs-lookup"><span data-stu-id="b985d-115">After a long discussion, the Entity Framework team decided to create Microsoft.Data.Sqlite based on Brice's prototype.</span></span> <span data-ttu-id="b985d-116">这将使他们能够创建一种全新的轻量级新式实现方式，它将与 .NET Core 的目标保持一致。</span><span class="sxs-lookup"><span data-stu-id="b985d-116">This would allow them to create a new lightweight and modern implementation that would align with the goals of .NET Core.</span></span>

<span data-ttu-id="b985d-117">下面的示例展示了它的新式特性，此示例代码同时在 System.Data.SQLite 和 Microsoft.Data.Sqlite 中创建[用户定义函数](user-defined-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="b985d-117">As an example of what we mean by more modern, here is code to create a [user-defined function](user-defined-functions.md) in both System.Data.SQLite and Microsoft.Data.Sqlite.</span></span>

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

<span data-ttu-id="b985d-118">2017 年，.NET Core 2.0 发生了战略变化。</span><span class="sxs-lookup"><span data-stu-id="b985d-118">In 2017, .NET Core 2.0 experienced a change in strategy.</span></span> <span data-ttu-id="b985d-119">团队确定了与 .NET Framework 的兼容性对于 .NET Core 的成功至关重要。</span><span class="sxs-lookup"><span data-stu-id="b985d-119">It was decided that compatibility with .NET Framework was vital to the success of .NET Core.</span></span> <span data-ttu-id="b985d-120">因此，将许多已删除的 API（包括 DataSet API）都重新添加回来。</span><span class="sxs-lookup"><span data-stu-id="b985d-120">Many of the removed APIs, including the DataSet APIs, were added back.</span></span> <span data-ttu-id="b985d-121">就像对其他许多工具所做的一样，这个不受限制的 System.Data.SQLite 也允许将其移植到 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="b985d-121">Like it did for many others, this unblocked System.Data.SQLite allowing it to also be ported to .NET Core.</span></span> <span data-ttu-id="b985d-122">但是，Microsoft.Data.Sqlite 的最初目标是仍保持轻量级的新式特性。</span><span class="sxs-lookup"><span data-stu-id="b985d-122">The original goal of Microsoft.Data.Sqlite to be lightweight and modern, however, still remains.</span></span> <span data-ttu-id="b985d-123">请参阅 [ADO.NET 限制](adonet-limitations.md)，详细了解哪些 ADO.NET API 不是由 Microsoft.Data.Sqlite 实现的。</span><span class="sxs-lookup"><span data-stu-id="b985d-123">See [ADO.NET limitations](adonet-limitations.md) for details about ADO.NET APIs not implemented by Microsoft.Data.Sqlite.</span></span>

<span data-ttu-id="b985d-124">将新功能添加到 Microsoft.Data.Sqlite 后，将考虑 System.Data.SQLite 的设计。</span><span class="sxs-lookup"><span data-stu-id="b985d-124">When new features are added to Microsoft.Data.Sqlite, the design of System.Data.SQLite is taken into account.</span></span> <span data-ttu-id="b985d-125">我们会尽可能尝试将两者之间的变化降到最少，以简化两者之间的过渡。</span><span class="sxs-lookup"><span data-stu-id="b985d-125">We try, when possible, to minimize changes between the two to ease transitioning between them.</span></span>

## <a name="data-types"></a><span data-ttu-id="b985d-126">数据类型</span><span class="sxs-lookup"><span data-stu-id="b985d-126">Data types</span></span>

<span data-ttu-id="b985d-127">Microsoft.Data.Sqlite 和 System.Data.SQLite 之间的最大区别是处理数据类型的方式。</span><span class="sxs-lookup"><span data-stu-id="b985d-127">The biggest difference between Microsoft.Data.Sqlite and System.Data.SQLite is how data types are handled.</span></span> <span data-ttu-id="b985d-128">如[数据类型](types.md)中所述，Microsoft.Data.Sqlite 不会尝试隐藏 SQLite 的基础奇怪特征，此特征允许将任意字符串指定为列类型，并且只有四个基元类型：INTEGER、REAL、TEXT 和 BLOB。</span><span class="sxs-lookup"><span data-stu-id="b985d-128">As described in [Data types](types.md), Microsoft.Data.Sqlite doesn't try to hide the underlying quirkiness of SQLite, which allows any arbitrary string to be specified as the column type, and only has four primitive types: INTEGER, REAL, TEXT, and BLOB.</span></span>

<span data-ttu-id="b985d-129">System.Data.SQLite 将其他语义应用于列类型，从而将它们直接映射到 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="b985d-129">System.Data.SQLite applies additional semantics to column types mapping them directly to .NET types.</span></span> <span data-ttu-id="b985d-130">这为提供程序提供了一种更强类型的外观，但它具有一些粗糙的边缘。</span><span class="sxs-lookup"><span data-stu-id="b985d-130">This gives the provider a more strongly typed feel, but it has some rough edges.</span></span> <span data-ttu-id="b985d-131">例如，它们必须引入一个新的 SQL 语句 (TYPES) 来指定 SELECT 语句中表达式的列类型。</span><span class="sxs-lookup"><span data-stu-id="b985d-131">For example, they had to introduce a new SQL statement (TYPES) to specify the column types of expressions in SELECT statements.</span></span>

## <a name="connection-strings"></a><span data-ttu-id="b985d-132">连接字符串</span><span class="sxs-lookup"><span data-stu-id="b985d-132">Connection strings</span></span>

<span data-ttu-id="b985d-133">Microsoft.Data.Sqlite 的[连接字符串](connection-strings.md)关键字要少很多。</span><span class="sxs-lookup"><span data-stu-id="b985d-133">Microsoft.Data.Sqlite has a lot fewer [connection string](connection-strings.md) keywords.</span></span> <span data-ttu-id="b985d-134">下表显示了可以替代使用的替代方法。</span><span class="sxs-lookup"><span data-stu-id="b985d-134">The following table shows alternatives that can be used instead.</span></span>

| <span data-ttu-id="b985d-135">关键字</span><span class="sxs-lookup"><span data-stu-id="b985d-135">Keyword</span></span>          | <span data-ttu-id="b985d-136">替代项</span><span class="sxs-lookup"><span data-stu-id="b985d-136">Alternative</span></span>                                         |
| ---------------- | --------------------------------------------------- |
| <span data-ttu-id="b985d-137">Cache Size</span><span class="sxs-lookup"><span data-stu-id="b985d-137">Cache Size</span></span>       | <span data-ttu-id="b985d-138">发送 `PRAGMA cache_size = <pages>`</span><span class="sxs-lookup"><span data-stu-id="b985d-138">Send `PRAGMA cache_size = <pages>`</span></span>                  |
| <span data-ttu-id="b985d-139">默认超时</span><span class="sxs-lookup"><span data-stu-id="b985d-139">Default Timeout</span></span>  | <span data-ttu-id="b985d-140">对 SqliteConnection 使用 DefaultTimeout 属性</span><span class="sxs-lookup"><span data-stu-id="b985d-140">Use the DefaultTimeout property on SqliteConnection</span></span> |
| <span data-ttu-id="b985d-141">FailIfMissing</span><span class="sxs-lookup"><span data-stu-id="b985d-141">FailIfMissing</span></span>    | <span data-ttu-id="b985d-142">使用 `Mode=ReadWrite`</span><span class="sxs-lookup"><span data-stu-id="b985d-142">Use `Mode=ReadWrite`</span></span>                                |
| <span data-ttu-id="b985d-143">FullUri</span><span class="sxs-lookup"><span data-stu-id="b985d-143">FullUri</span></span>          | <span data-ttu-id="b985d-144">使用 Data Source 关键字</span><span class="sxs-lookup"><span data-stu-id="b985d-144">Use the Data Source keyword</span></span>                         |
| <span data-ttu-id="b985d-145">Journal Mode</span><span class="sxs-lookup"><span data-stu-id="b985d-145">Journal Mode</span></span>     | <span data-ttu-id="b985d-146">发送 `PRAGMA journal_mode = <mode>`</span><span class="sxs-lookup"><span data-stu-id="b985d-146">Send `PRAGMA journal_mode = <mode>`</span></span>                 |
| <span data-ttu-id="b985d-147">Legacy Format</span><span class="sxs-lookup"><span data-stu-id="b985d-147">Legacy Format</span></span>    | <span data-ttu-id="b985d-148">发送 `PRAGMA legacy_file_format = 1`</span><span class="sxs-lookup"><span data-stu-id="b985d-148">Send `PRAGMA legacy_file_format = 1`</span></span>                |
| <span data-ttu-id="b985d-149">Max Page Count</span><span class="sxs-lookup"><span data-stu-id="b985d-149">Max Page Count</span></span>   | <span data-ttu-id="b985d-150">发送 `PRAGMA max_page_count = <pages>`</span><span class="sxs-lookup"><span data-stu-id="b985d-150">Send `PRAGMA max_page_count = <pages>`</span></span>              |
| <span data-ttu-id="b985d-151">Page Size</span><span class="sxs-lookup"><span data-stu-id="b985d-151">Page Size</span></span>        | <span data-ttu-id="b985d-152">发送 `PRAGMA page_size = <bytes>`</span><span class="sxs-lookup"><span data-stu-id="b985d-152">Send `PRAGMA page_size = <bytes>`</span></span>                   |
| <span data-ttu-id="b985d-153">只读</span><span class="sxs-lookup"><span data-stu-id="b985d-153">Read Only</span></span>        | <span data-ttu-id="b985d-154">使用 `Mode=ReadOnly`</span><span class="sxs-lookup"><span data-stu-id="b985d-154">Use `Mode=ReadOnly`</span></span>                                 |
| <span data-ttu-id="b985d-155">同步</span><span class="sxs-lookup"><span data-stu-id="b985d-155">Synchronous</span></span>      | <span data-ttu-id="b985d-156">发送 `PRAGMA synchronous = <mode>`</span><span class="sxs-lookup"><span data-stu-id="b985d-156">Send `PRAGMA synchronous = <mode>`</span></span>                  |
| <span data-ttu-id="b985d-157">URI</span><span class="sxs-lookup"><span data-stu-id="b985d-157">Uri</span></span>              | <span data-ttu-id="b985d-158">使用 Data Source 关键字</span><span class="sxs-lookup"><span data-stu-id="b985d-158">Use the Data Source keyword</span></span>                         |
| <span data-ttu-id="b985d-159">UseUTF16Encoding</span><span class="sxs-lookup"><span data-stu-id="b985d-159">UseUTF16Encoding</span></span> | <span data-ttu-id="b985d-160">发送 `PRAGMA encoding = 'UTF-16'`</span><span class="sxs-lookup"><span data-stu-id="b985d-160">Send `PRAGMA encoding = 'UTF-16'`</span></span>                   |

## <a name="authorization"></a><span data-ttu-id="b985d-161">授权</span><span class="sxs-lookup"><span data-stu-id="b985d-161">Authorization</span></span>

<span data-ttu-id="b985d-162">Microsoft.Data.Sqlite 没有任何 API 公开 SQLite 的授权回调。</span><span class="sxs-lookup"><span data-stu-id="b985d-162">Microsoft.Data.Sqlite doesn't have any API exposing SQLite's authorization callback.</span></span> <span data-ttu-id="b985d-163">请使用问题 [#13835](https://github.com/dotnet/efcore/issues/13835) 提供有关此功能的反馈。</span><span class="sxs-lookup"><span data-stu-id="b985d-163">Use issue [#13835](https://github.com/dotnet/efcore/issues/13835) to provide feedback about this feature.</span></span>

## <a name="data-change-notifications"></a><span data-ttu-id="b985d-164">数据更改通知</span><span class="sxs-lookup"><span data-stu-id="b985d-164">Data change notifications</span></span>

<span data-ttu-id="b985d-165">Microsoft.Data.Sqlite 没有任何 API 公开 SQLite 的数据更改通知。</span><span class="sxs-lookup"><span data-stu-id="b985d-165">Microsoft.Data.Sqlite doesn't have any API exposing SQLite's data change notifications.</span></span> <span data-ttu-id="b985d-166">请使用问题 [#13827](https://github.com/dotnet/efcore/issues/13827) 提供有关此功能的反馈。</span><span class="sxs-lookup"><span data-stu-id="b985d-166">Use issue [#13827](https://github.com/dotnet/efcore/issues/13827) to provide feedback about this feature.</span></span>

## <a name="virtual-table-modules"></a><span data-ttu-id="b985d-167">虚拟表模块</span><span class="sxs-lookup"><span data-stu-id="b985d-167">Virtual table modules</span></span>

<span data-ttu-id="b985d-168">Microsoft.Data.Sqlite 没有用于创建虚拟表模块的任何 API。</span><span class="sxs-lookup"><span data-stu-id="b985d-168">Microsoft.Data.Sqlite doesn't have any API for creating virtual table modules.</span></span> <span data-ttu-id="b985d-169">请使用问题 [#13823](https://github.com/dotnet/efcore/issues/13823) 提供有关此功能的反馈。</span><span class="sxs-lookup"><span data-stu-id="b985d-169">Use issue [#13823](https://github.com/dotnet/efcore/issues/13823) to provide feedback about this feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="b985d-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="b985d-170">See also</span></span>

* [<span data-ttu-id="b985d-171">数据类型</span><span class="sxs-lookup"><span data-stu-id="b985d-171">Data types</span></span>](types.md)
* [<span data-ttu-id="b985d-172">连接字符串</span><span class="sxs-lookup"><span data-stu-id="b985d-172">Connection strings</span></span>](connection-strings.md)
* [<span data-ttu-id="b985d-173">加密</span><span class="sxs-lookup"><span data-stu-id="b985d-173">Encryption</span></span>](encryption.md)
* [<span data-ttu-id="b985d-174">ADO.NET 限制</span><span class="sxs-lookup"><span data-stu-id="b985d-174">ADO.NET limitations</span></span>](adonet-limitations.md)
* [<span data-ttu-id="b985d-175">Dapper 限制</span><span class="sxs-lookup"><span data-stu-id="b985d-175">Dapper limitations</span></span>](dapper-limitations.md)
