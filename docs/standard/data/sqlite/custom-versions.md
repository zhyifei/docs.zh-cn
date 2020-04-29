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
# <a name="custom-sqlite-versions"></a>自定义 SQLite 版本

Microsoft.Data.Sqlite 基于 SQLitePCLRaw 而构建。 可以通过使用捆绑或配置 SQLitePCLRaw 提供程序来使用本机 SQLite 库的自定义版本。

## <a name="bundles"></a>捆绑

SQLitePCLRaw 提供捆绑包，使你可以轻松地在不同平台间引入正确的依赖项。

默认情况下，主 Microsoft.Data.Sqlite 包会引入 SQLitePCLRaw.bundle_e_sqlite3。

若要使用不同的捆绑，请改为安装 `Microsoft.Data.Sqlite.Core` 包以及要使用的捆绑包。 捆绑由 Microsoft.Data.Sqlite 自动初始化。

| 捆绑 | 描述 |
| --- | --- |
| SQLitePCLRaw.bundle_e_sqlite3 | 在所有平台上提供一致版本的 SQLite。 包括 FTS4、FTS5、JSON1 和 R* 树扩展。 这是默认设置。 |
| SQLitePCLRaw.bundle_green | 与 bundle_e_sqlite3 相同，不同之处是在 iOS 上使用系统 SQLite 库。 |
| SQLitePCLRaw.bundle_zetetic | 使用 Zetetic 提供的官方 SQLCipher 内部版本（不包括在内）。 |
| SQLitePCLRaw.bundle_winsqlite3 | 使用 winsqlite3.dll（Windows 10 上的系统 SQLite 库）。 |
| SQLitePCLRaw.bundle_e_sqlcipher | 提供 SQLCipher 的非官方开放源代码内部版本。 |

例如，若要使用 SQLCipher 的非官方开放源代码版本，请使用以下命令。

### <a name="net-core-cli"></a>[.NET Core CLI](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a>SQLitePCLRaw 提供程序

通过利用 `SQLitePCLRaw.provider.dynamic_cdecl` 包，可以使用自己的 SQLite 内部版本。 在这种情况下，由你负责随应用部署本机库。 请注意，根据所使用的 .NET 平台和运行时，随应用部署本机库的详细信息差异很大。

首先，需要实现 IGetFunctionPointer。 .NET Core 上的实现非常简单。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

接下来，配置 SQLitePCLRaw 提供程序。 确保在应用中使用 Microsoft.Data.Sqlite 之前完成此操作。 另外，请避免使用可能替代提供程序的 SQLitePCLRaw 捆绑包。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
