---
title: 扩展
ms.date: 12/13/2019
description: 了解如何加载 SQLite 扩展。
ms.openlocfilehash: a85b1227be4274dd20156d2475d6d2d68e250f99
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901298"
---
# <a name="extensions"></a><span data-ttu-id="bbaf0-103">扩展</span><span class="sxs-lookup"><span data-stu-id="bbaf0-103">Extensions</span></span>

<span data-ttu-id="bbaf0-104">SQLite 支持在运行时加载扩展。</span><span class="sxs-lookup"><span data-stu-id="bbaf0-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="bbaf0-105">扩展包括诸如附加的 SQL 函数、排序规则、虚拟表等。</span><span class="sxs-lookup"><span data-stu-id="bbaf0-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="bbaf0-106">.NET Core 包含用于在其他位置（如引用的 NuGet 包）查找本机库的其他逻辑。</span><span class="sxs-lookup"><span data-stu-id="bbaf0-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="bbaf0-107">遗憾的是，SQLite 无法利用此逻辑;它直接调用平台 API 来加载库。</span><span class="sxs-lookup"><span data-stu-id="bbaf0-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="bbaf0-108">因此，你可能需要在加载 SQLite 扩展之前修改路径、LD_LIBRARY_PATH 或 DYLD_LIBRARY_PATH 环境变量。</span><span class="sxs-lookup"><span data-stu-id="bbaf0-108">Because of this, you may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="bbaf0-109">GitHub 上[提供了一个示例](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs)，演示如何在引用的 NuGet 包内查找当前运行时的二进制文件。</span><span class="sxs-lookup"><span data-stu-id="bbaf0-109">There's [a sample](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="bbaf0-110">若要加载扩展，请调用 <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="bbaf0-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="bbaf0-111">即使连接已关闭和重新打开，也会确保扩展仍处于加载状态。</span><span class="sxs-lookup"><span data-stu-id="bbaf0-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="bbaf0-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbaf0-112">See also</span></span>

* [<span data-ttu-id="bbaf0-113">运行时可加载扩展</span><span class="sxs-lookup"><span data-stu-id="bbaf0-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
