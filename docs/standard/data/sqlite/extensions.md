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
# <a name="extensions"></a>扩展

SQLite 支持在运行时加载扩展。 扩展包括诸如附加的 SQL 函数、排序规则、虚拟表等。

.NET Core 包含用于在其他位置（如引用的 NuGet 包）查找本机库的其他逻辑。 遗憾的是，SQLite 无法利用此逻辑;它直接调用平台 API 来加载库。 因此，你可能需要在加载 SQLite 扩展之前修改路径、LD_LIBRARY_PATH 或 DYLD_LIBRARY_PATH 环境变量。 GitHub 上[提供了一个示例](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs)，演示如何在引用的 NuGet 包内查找当前运行时的二进制文件。

若要加载扩展，请调用 <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> 方法。 即使连接已关闭和重新打开，也会确保扩展仍处于加载状态。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>另请参阅

* [运行时可加载扩展](https://www.sqlite.org/loadext.html)
