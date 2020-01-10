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
# <a name="extensions"></a>扩展

SQLite 支持在运行时加载扩展。 扩展包括诸如附加的 SQL 函数、排序规则、虚拟表等。

.NET Core 包含用于在其他位置（如引用的 NuGet 包）查找本机库的其他逻辑。 遗憾的是，SQLite 无法利用此逻辑;它直接调用平台 API 来加载库。 因此，在加载 SQLite 扩展之前，应用可能需要修改路径、LD_LIBRARY_PATH 或 DYLD_LIBRARY_PATH 环境变量。 GitHub 上[提供了一个示例](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs)，演示如何在引用的 NuGet 包内查找当前运行时的二进制文件。

若要加载扩展，请调用 <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> 方法。 即使连接已关闭和重新打开，也会确保扩展仍处于加载状态。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>另请参阅

* [运行时可加载扩展](https://www.sqlite.org/loadext.html)
