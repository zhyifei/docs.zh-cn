---
title: 自定义 SQLite 版本
ms.date: 12/13/2019
description: 了解如何使用本机 SQLite 库的自定义版本。
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746989"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="3ad3c-103">自定义 SQLite 版本</span><span class="sxs-lookup"><span data-stu-id="3ad3c-103">Custom SQLite versions</span></span>

<span data-ttu-id="3ad3c-104">Microsoft.Data.Sqlite 基于 SQLitePCLRaw 而构建。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-104">Microsoft.Data.Sqlite is built on top of SQLitePCLRaw.</span></span> <span data-ttu-id="3ad3c-105">可以通过使用捆绑或配置 SQLitePCLRaw 提供程序来使用本机 SQLite 库的自定义版本。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a SQLitePCLRaw provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="3ad3c-106">捆绑</span><span class="sxs-lookup"><span data-stu-id="3ad3c-106">Bundles</span></span>

<span data-ttu-id="3ad3c-107">SQLitePCLRaw 提供捆绑包，使你可以轻松地在不同平台间引入正确的依赖项。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-107">SQLitePCLRaw provides bundle packages that make it easy to bring in the right dependencies across different platforms.</span></span>

<span data-ttu-id="3ad3c-108">默认情况下，主 Microsoft.Data.Sqlite 包会引入 SQLitePCLRaw.bundle_e_sqlite3。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-108">The main Microsoft.Data.Sqlite package brings in SQLitePCLRaw.bundle_e_sqlite3 by default.</span></span>

<span data-ttu-id="3ad3c-109">若要使用不同的捆绑，请改为安装 `Microsoft.Data.Sqlite.Core` 包以及要使用的捆绑包。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="3ad3c-110">捆绑由 Microsoft.Data.Sqlite 自动初始化。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-110">Bundles are automatically initialized by Microsoft.Data.Sqlite.</span></span>

| <span data-ttu-id="3ad3c-111">捆绑</span><span class="sxs-lookup"><span data-stu-id="3ad3c-111">Bundle</span></span> | <span data-ttu-id="3ad3c-112">描述</span><span class="sxs-lookup"><span data-stu-id="3ad3c-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="3ad3c-113">SQLitePCLRaw.bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="3ad3c-113">SQLitePCLRaw.bundle_e_sqlite3</span></span> | <span data-ttu-id="3ad3c-114">在所有平台上提供一致版本的 SQLite。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="3ad3c-115">包括 FTS4、FTS5、JSON1 和 R\* 树扩展。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="3ad3c-116">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-116">This is the default.</span></span> |
| <span data-ttu-id="3ad3c-117">SQLitePCLRaw.bundle_green</span><span class="sxs-lookup"><span data-stu-id="3ad3c-117">SQLitePCLRaw.bundle_green</span></span> | <span data-ttu-id="3ad3c-118">与 bundle_e_sqlite3 相同，不同之处是在 iOS 上使用系统 SQLite 库。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-118">Same as bundle_e_sqlite3, except on iOS where it uses the system SQLite library.</span></span> |
| <span data-ttu-id="3ad3c-119">SQLitePCLRaw.bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="3ad3c-119">SQLitePCLRaw.bundle_zetetic</span></span> | <span data-ttu-id="3ad3c-120">使用 Zetetic 提供的官方 SQLCipher 内部版本（不包括在内）。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-120">Uses the official SQLCipher builds from Zetetic (not included).</span></span> |
| <span data-ttu-id="3ad3c-121">SQLitePCLRaw.bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="3ad3c-121">SQLitePCLRaw.bundle_winsqlite3</span></span> | <span data-ttu-id="3ad3c-122">使用 winsqlite3.dll（Windows 10 上的系统 SQLite 库）。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-122">Uses winsqlite3.dll, the system SQLite library on Windows 10.</span></span> |
| <span data-ttu-id="3ad3c-123">SQLitePCLRaw.bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="3ad3c-123">SQLitePCLRaw.bundle_e_sqlcipher</span></span> | <span data-ttu-id="3ad3c-124">提供 SQLCipher 的非官方开放源代码内部版本。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-124">Provides an unofficial, open-source build of SQLCipher.</span></span> |

<span data-ttu-id="3ad3c-125">例如，若要使用 SQLCipher 的非官方开放源代码版本，请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-125">For example, to use the unofficial, open-source build of SQLCipher use the following commands.</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="3ad3c-126">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="3ad3c-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="3ad3c-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3ad3c-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a><span data-ttu-id="3ad3c-128">SQLitePCLRaw 提供程序</span><span class="sxs-lookup"><span data-stu-id="3ad3c-128">SQLitePCLRaw providers</span></span>

<span data-ttu-id="3ad3c-129">通过利用 `SQLitePCLRaw.provider.dynamic_cdecl` 包，可以使用自己的 SQLite 内部版本。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-129">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="3ad3c-130">在这种情况下，由你负责随应用部署本机库。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-130">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="3ad3c-131">请注意，根据所使用的 .NET 平台和运行时，随应用部署本机库的详细信息差异很大。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-131">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="3ad3c-132">首先，需要实现 IGetFunctionPointer。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-132">First, you'll need to implement IGetFunctionPointer.</span></span> <span data-ttu-id="3ad3c-133">.NET Core 上的实现非常简单。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-133">The implementation is fairly trivial on .NET Core.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="3ad3c-134">接下来，配置 SQLitePCLRaw 提供程序。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-134">Next, configure the SQLitePCLRaw provider.</span></span> <span data-ttu-id="3ad3c-135">确保在应用中使用 Microsoft.Data.Sqlite 之前完成此操作。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-135">Ensure this is done before Microsoft.Data.Sqlite is used in your app.</span></span> <span data-ttu-id="3ad3c-136">另外，请避免使用可能替代提供程序的 SQLitePCLRaw 捆绑包。</span><span class="sxs-lookup"><span data-stu-id="3ad3c-136">Also, avoid using a SQLitePCLRaw bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
