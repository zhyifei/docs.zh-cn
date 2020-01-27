---
title: 사용자 지정 SQLite 버전
ms.date: 12/13/2019
description: 了解如何使用本机 SQLite 库的自定义版本。
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746989"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="3471a-103">사용자 지정 SQLite 버전</span><span class="sxs-lookup"><span data-stu-id="3471a-103">Custom SQLite versions</span></span>

<span data-ttu-id="3471a-104">SQLitePCLRaw 构建在其基础之上。</span><span class="sxs-lookup"><span data-stu-id="3471a-104">Microsoft.Data.Sqlite is built on top of SQLitePCLRaw.</span></span> <span data-ttu-id="3471a-105">可以通过使用捆绑或配置 SQLitePCLRaw 提供程序来使用本机 SQLite 库的自定义版本。</span><span class="sxs-lookup"><span data-stu-id="3471a-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a SQLitePCLRaw provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="3471a-106">捆绑</span><span class="sxs-lookup"><span data-stu-id="3471a-106">Bundles</span></span>

<span data-ttu-id="3471a-107">SQLitePCLRaw 提供捆绑包，使你可以轻松地在不同平台之间引入适当的依赖项。</span><span class="sxs-lookup"><span data-stu-id="3471a-107">SQLitePCLRaw provides bundle packages that make it easy to bring in the right dependencies across different platforms.</span></span>

<span data-ttu-id="3471a-108">默认情况下，bundle_e_sqlite3 SQLitePCLRaw 包会引入默认值。</span><span class="sxs-lookup"><span data-stu-id="3471a-108">The main Microsoft.Data.Sqlite package brings in SQLitePCLRaw.bundle_e_sqlite3 by default.</span></span>

<span data-ttu-id="3471a-109">若要使用不同的捆绑包，请改为安装 `Microsoft.Data.Sqlite.Core` 包以及要使用的捆绑包。</span><span class="sxs-lookup"><span data-stu-id="3471a-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="3471a-110">绑定由 Microsoft 自动初始化。</span><span class="sxs-lookup"><span data-stu-id="3471a-110">Bundles are automatically initialized by Microsoft.Data.Sqlite.</span></span>

| <span data-ttu-id="3471a-111">软件包</span><span class="sxs-lookup"><span data-stu-id="3471a-111">Bundle</span></span> | <span data-ttu-id="3471a-112">설명</span><span class="sxs-lookup"><span data-stu-id="3471a-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="3471a-113">SQLitePCLRaw bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="3471a-113">SQLitePCLRaw.bundle_e_sqlite3</span></span> | <span data-ttu-id="3471a-114">在所有平台上提供一致版本的 SQLite。</span><span class="sxs-lookup"><span data-stu-id="3471a-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="3471a-115">包括 FTS4、FTS5、JSON1 和 R \* 树扩展。</span><span class="sxs-lookup"><span data-stu-id="3471a-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="3471a-116">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="3471a-116">This is the default.</span></span> |
| <span data-ttu-id="3471a-117">SQLitePCLRaw bundle_green</span><span class="sxs-lookup"><span data-stu-id="3471a-117">SQLitePCLRaw.bundle_green</span></span> | <span data-ttu-id="3471a-118">与 bundle_e_sqlite3 相同，不同之处在于使用系统 SQLite 库的 iOS。</span><span class="sxs-lookup"><span data-stu-id="3471a-118">Same as bundle_e_sqlite3, except on iOS where it uses the system SQLite library.</span></span> |
| <span data-ttu-id="3471a-119">SQLitePCLRaw bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="3471a-119">SQLitePCLRaw.bundle_zetetic</span></span> | <span data-ttu-id="3471a-120">使用 Zetetic 中的官方 SQLCipher 生成（不包括在内）。</span><span class="sxs-lookup"><span data-stu-id="3471a-120">Uses the official SQLCipher builds from Zetetic (not included).</span></span> |
| <span data-ttu-id="3471a-121">SQLitePCLRaw bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="3471a-121">SQLitePCLRaw.bundle_winsqlite3</span></span> | <span data-ttu-id="3471a-122">使用 Windows 10 上的 winsqlite3 系统 SQLite 库。</span><span class="sxs-lookup"><span data-stu-id="3471a-122">Uses winsqlite3.dll, the system SQLite library on Windows 10.</span></span> |
| <span data-ttu-id="3471a-123">SQLitePCLRaw bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="3471a-123">SQLitePCLRaw.bundle_e_sqlcipher</span></span> | <span data-ttu-id="3471a-124">提供 SQLCipher 的非正式开源版本。</span><span class="sxs-lookup"><span data-stu-id="3471a-124">Provides an unofficial, open-source build of SQLCipher.</span></span> |

<span data-ttu-id="3471a-125">例如，若要使用 SQLCipher 的非官方开源版本，请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="3471a-125">For example, to use the unofficial, open-source build of SQLCipher use the following commands.</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="3471a-126">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="3471a-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="3471a-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3471a-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a><span data-ttu-id="3471a-128">SQLitePCLRaw 提供程序</span><span class="sxs-lookup"><span data-stu-id="3471a-128">SQLitePCLRaw providers</span></span>

<span data-ttu-id="3471a-129">通过利用 `SQLitePCLRaw.provider.dynamic_cdecl` 包，你可以使用你自己的 SQLite 版本。</span><span class="sxs-lookup"><span data-stu-id="3471a-129">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="3471a-130">在这种情况下，你需要负责在你的应用程序中部署本机库。</span><span class="sxs-lookup"><span data-stu-id="3471a-130">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="3471a-131">请注意，根据您使用的 .NET 平台和运行时，使用您的应用程序部署本机库的详细信息有所不同。</span><span class="sxs-lookup"><span data-stu-id="3471a-131">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="3471a-132">首先，需要实现 IGetFunctionPointer。</span><span class="sxs-lookup"><span data-stu-id="3471a-132">First, you'll need to implement IGetFunctionPointer.</span></span> <span data-ttu-id="3471a-133">.NET Core 上的实现非常简单。</span><span class="sxs-lookup"><span data-stu-id="3471a-133">The implementation is fairly trivial on .NET Core.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="3471a-134">接下来，配置 SQLitePCLRaw 提供程序。</span><span class="sxs-lookup"><span data-stu-id="3471a-134">Next, configure the SQLitePCLRaw provider.</span></span> <span data-ttu-id="3471a-135">确保在你的应用程序中使用了之前完成此操作。</span><span class="sxs-lookup"><span data-stu-id="3471a-135">Ensure this is done before Microsoft.Data.Sqlite is used in your app.</span></span> <span data-ttu-id="3471a-136">另外，请避免使用可能替代提供程序的 SQLitePCLRaw 捆绑包。</span><span class="sxs-lookup"><span data-stu-id="3471a-136">Also, avoid using a SQLitePCLRaw bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
