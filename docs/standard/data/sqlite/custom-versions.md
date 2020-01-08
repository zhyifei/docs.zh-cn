---
title: 自定义 SQLite 版本
ms.date: 12/13/2019
description: 了解如何使用本机 SQLite 库的自定义版本。
ms.openlocfilehash: 8a2646138ea9dbecf412a2e8e0e347e2d71a5b0b
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450386"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="2abeb-103">自定义 SQLite 版本</span><span class="sxs-lookup"><span data-stu-id="2abeb-103">Custom SQLite versions</span></span>

<span data-ttu-id="2abeb-104">SQLitePCLRaw 构建在其基础之上。</span><span class="sxs-lookup"><span data-stu-id="2abeb-104">Microsoft.Data.Sqlite is built on top of SQLitePCLRaw.</span></span> <span data-ttu-id="2abeb-105">可以通过使用捆绑或配置 SQLitePCLRaw 提供程序来使用本机 SQLite 库的自定义版本。</span><span class="sxs-lookup"><span data-stu-id="2abeb-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a SQLitePCLRaw provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="2abeb-106">捆绑</span><span class="sxs-lookup"><span data-stu-id="2abeb-106">Bundles</span></span>

<span data-ttu-id="2abeb-107">SQLitePCLRaw 提供捆绑包，使你可以轻松地在不同平台之间引入适当的依赖项。</span><span class="sxs-lookup"><span data-stu-id="2abeb-107">SQLitePCLRaw provides bundle packages that make it easy to bring in the right dependencies across different platforms.</span></span>

<span data-ttu-id="2abeb-108">默认情况下，bundle_e_sqlite3 SQLitePCLRaw 包会引入默认值。</span><span class="sxs-lookup"><span data-stu-id="2abeb-108">The main Microsoft.Data.Sqlite package brings in SQLitePCLRaw.bundle_e_sqlite3 by default.</span></span>

<span data-ttu-id="2abeb-109">若要使用不同的捆绑包，请改为安装 `Microsoft.Data.Sqlite.Core` 包以及要使用的捆绑包。</span><span class="sxs-lookup"><span data-stu-id="2abeb-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="2abeb-110">绑定由 Microsoft 自动初始化。</span><span class="sxs-lookup"><span data-stu-id="2abeb-110">Bundles are automatically initialized by Microsoft.Data.Sqlite.</span></span>

| <span data-ttu-id="2abeb-111">捆绑包</span><span class="sxs-lookup"><span data-stu-id="2abeb-111">Bundle</span></span> | <span data-ttu-id="2abeb-112">描述</span><span class="sxs-lookup"><span data-stu-id="2abeb-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="2abeb-113">SQLitePCLRaw bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="2abeb-113">SQLitePCLRaw.bundle_e_sqlite3</span></span> | <span data-ttu-id="2abeb-114">在所有平台上提供一致版本的 SQLite。</span><span class="sxs-lookup"><span data-stu-id="2abeb-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="2abeb-115">包括 FTS4、FTS5、JSON1 和</span><span class="sxs-lookup"><span data-stu-id="2abeb-115">Includes the FTS4, FTS5, JSON1, and</span></span> | <span data-ttu-id="2abeb-116">R \* 树扩展。</span><span class="sxs-lookup"><span data-stu-id="2abeb-116">R\*Tree extensions.</span></span> <span data-ttu-id="2abeb-117">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="2abeb-117">This is the default.</span></span> |
| <span data-ttu-id="2abeb-118">SQLitePCLRaw bundle_green</span><span class="sxs-lookup"><span data-stu-id="2abeb-118">SQLitePCLRaw.bundle_green</span></span> | <span data-ttu-id="2abeb-119">与 bundle_e_sqlite3 相同，不同之处在于使用系统 SQLite 库的 iOS。</span><span class="sxs-lookup"><span data-stu-id="2abeb-119">Same as bundle_e_sqlite3, except on iOS where it uses the system SQLite library.</span></span> |
| <span data-ttu-id="2abeb-120">SQLitePCLRaw bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="2abeb-120">SQLitePCLRaw.bundle_zetetic</span></span> | <span data-ttu-id="2abeb-121">使用 Zetetic 中的官方 SQLCipher 生成（不包括在内）。</span><span class="sxs-lookup"><span data-stu-id="2abeb-121">Uses the official SQLCipher builds from Zetetic (not included).</span></span> |
| <span data-ttu-id="2abeb-122">SQLitePCLRaw bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="2abeb-122">SQLitePCLRaw.bundle_winsqlite3</span></span> | <span data-ttu-id="2abeb-123">使用 Windows 10 上的 winsqlite3 系统 SQLite 库。</span><span class="sxs-lookup"><span data-stu-id="2abeb-123">Uses winsqlite3.dll, the system SQLite library on Windows 10.</span></span> |
| <span data-ttu-id="2abeb-124">SQLitePCLRaw bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="2abeb-124">SQLitePCLRaw.bundle_e_sqlcipher</span></span> | <span data-ttu-id="2abeb-125">提供 SQLCipher 的非正式开源版本。</span><span class="sxs-lookup"><span data-stu-id="2abeb-125">Provides an unofficial, open-source build of SQLCipher.</span></span> |

<span data-ttu-id="2abeb-126">例如，若要使用 SQLCipher 的非官方开源版本，请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="2abeb-126">For example, to use the unofficial, open-source build of SQLCipher use the following commands.</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="2abeb-127">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="2abeb-127">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="2abeb-128">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2abeb-128">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a><span data-ttu-id="2abeb-129">SQLitePCLRaw 提供程序</span><span class="sxs-lookup"><span data-stu-id="2abeb-129">SQLitePCLRaw providers</span></span>

<span data-ttu-id="2abeb-130">通过利用 `SQLitePCLRaw.provider.dynamic_cdecl` 包，你可以使用你自己的 SQLite 版本。</span><span class="sxs-lookup"><span data-stu-id="2abeb-130">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="2abeb-131">在这种情况下，你需要负责在你的应用程序中部署本机库。</span><span class="sxs-lookup"><span data-stu-id="2abeb-131">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="2abeb-132">请注意，根据您使用的 .NET 平台和运行时，使用您的应用程序部署本机库的详细信息有所不同。</span><span class="sxs-lookup"><span data-stu-id="2abeb-132">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="2abeb-133">首先，需要实现 IGetFunctionPointer。</span><span class="sxs-lookup"><span data-stu-id="2abeb-133">First, you'll need to implement IGetFunctionPointer.</span></span> <span data-ttu-id="2abeb-134">.NET Core 上的实现非常简单。</span><span class="sxs-lookup"><span data-stu-id="2abeb-134">The implementation is fairly trivial on .NET Core.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="2abeb-135">接下来，配置 SQLitePCLRaw 提供程序。</span><span class="sxs-lookup"><span data-stu-id="2abeb-135">Next, configure the SQLitePCLRaw provider.</span></span> <span data-ttu-id="2abeb-136">确保在你的应用程序中使用了之前完成此操作。</span><span class="sxs-lookup"><span data-stu-id="2abeb-136">Ensure this is done before Microsoft.Data.Sqlite is used in your app.</span></span> <span data-ttu-id="2abeb-137">另外，请避免使用可能替代提供程序的 SQLitePCLRaw 捆绑包。</span><span class="sxs-lookup"><span data-stu-id="2abeb-137">Also, avoid using a SQLitePCLRaw bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
