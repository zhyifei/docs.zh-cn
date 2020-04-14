---
title: 扩展
ms.date: 12/13/2019
description: 了解如何加载 SQLite 扩展。
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242954"
---
# <a name="extensions"></a><span data-ttu-id="38a49-103">扩展</span><span class="sxs-lookup"><span data-stu-id="38a49-103">Extensions</span></span>

<span data-ttu-id="38a49-104">SQLite 支持在运行时加载扩展。</span><span class="sxs-lookup"><span data-stu-id="38a49-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="38a49-105">扩展包括其他 SQL 函数、排序规则、虚拟表等。</span><span class="sxs-lookup"><span data-stu-id="38a49-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="38a49-106">.NET Core 包括用于在引用的 NuGet 包等其他位置定位本机库的其他逻辑。</span><span class="sxs-lookup"><span data-stu-id="38a49-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="38a49-107">不幸的是，SQLite不能利用这个逻辑;它直接调用平台 API 来加载库。</span><span class="sxs-lookup"><span data-stu-id="38a49-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="38a49-108">因此，您可能需要在加载 SQLite 扩展之前修改 PATH、LD_LIBRARY_PATH 或DYLD_LIBRARY_PATH环境变量。</span><span class="sxs-lookup"><span data-stu-id="38a49-108">Because of this, you may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="38a49-109">GitHub 上有[一个示例](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs)，该示例演示了在引用的 NuGet 包中查找当前运行时的二进制文件。</span><span class="sxs-lookup"><span data-stu-id="38a49-109">There's [a sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="38a49-110">要加载分机，请调用<xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="38a49-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="38a49-111">Microsoft.Data.Sqlite 将确保扩展保持加载状态，即使连接已关闭并重新打开也是如此。</span><span class="sxs-lookup"><span data-stu-id="38a49-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="38a49-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38a49-112">See also</span></span>

* [<span data-ttu-id="38a49-113">运行时可加载扩展</span><span class="sxs-lookup"><span data-stu-id="38a49-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
