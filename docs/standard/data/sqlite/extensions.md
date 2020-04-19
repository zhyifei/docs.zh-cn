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
# <a name="extensions"></a>扩展

SQLite 支持在运行时加载扩展。 扩展包括其他 SQL 函数、排序规则、虚拟表等。

.NET Core 包括用于在引用的 NuGet 包等其他位置定位本机库的其他逻辑。 不幸的是，SQLite不能利用这个逻辑;它直接调用平台 API 来加载库。 因此，您可能需要在加载 SQLite 扩展之前修改 PATH、LD_LIBRARY_PATH 或DYLD_LIBRARY_PATH环境变量。 GitHub 上有[一个示例](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs)，该示例演示了在引用的 NuGet 包中查找当前运行时的二进制文件。

要加载分机，请调用<xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>方法。 Microsoft.Data.Sqlite 将确保扩展保持加载状态，即使连接已关闭并重新打开也是如此。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>另请参阅

* [运行时可加载扩展](https://www.sqlite.org/loadext.html)
