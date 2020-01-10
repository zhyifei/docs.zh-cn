---
title: 扩展
ms.date: 12/13/2019
description: 了解如何加载 SQLite 扩展。
ms.openlocfilehash: 74b207205492bac48c89cb756470326f8e4a13c4
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777376"
---
# <a name="extensions"></a><span data-ttu-id="7429a-103">扩展</span><span class="sxs-lookup"><span data-stu-id="7429a-103">Extensions</span></span>

<span data-ttu-id="7429a-104">SQLite 支持在运行时加载扩展。</span><span class="sxs-lookup"><span data-stu-id="7429a-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="7429a-105">扩展包括诸如附加的 SQL 函数、排序规则、虚拟表等。</span><span class="sxs-lookup"><span data-stu-id="7429a-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="7429a-106">.NET Core 包含用于在其他位置（如引用的 NuGet 包）查找本机库的其他逻辑。</span><span class="sxs-lookup"><span data-stu-id="7429a-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="7429a-107">遗憾的是，SQLite 无法利用此逻辑;它直接调用平台 API 来加载库。</span><span class="sxs-lookup"><span data-stu-id="7429a-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="7429a-108">因此，在加载 SQLite 扩展之前，应用可能需要修改路径、LD_LIBRARY_PATH 或 DYLD_LIBRARY_PATH 环境变量。</span><span class="sxs-lookup"><span data-stu-id="7429a-108">Because of this, your app may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="7429a-109">GitHub 上[提供了一个示例](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs)，演示如何在引用的 NuGet 包内查找当前运行时的二进制文件。</span><span class="sxs-lookup"><span data-stu-id="7429a-109">There's [a sample](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="7429a-110">若要加载扩展，请调用 <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="7429a-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="7429a-111">即使连接已关闭和重新打开，也会确保扩展仍处于加载状态。</span><span class="sxs-lookup"><span data-stu-id="7429a-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="7429a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7429a-112">See also</span></span>

* [<span data-ttu-id="7429a-113">运行时可加载扩展</span><span class="sxs-lookup"><span data-stu-id="7429a-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
