---
title: 自定义 SQLite 版本
ms.date: 12/13/2019
description: 了解如何使用本机 SQLite 库的自定义版本。
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746989"
---
# <a name="custom-sqlite-versions"></a>自定义 SQLite 版本

SQLitePCLRaw 构建在其基础之上。 可以通过使用捆绑或配置 SQLitePCLRaw 提供程序来使用本机 SQLite 库的自定义版本。

## <a name="bundles"></a>捆绑

SQLitePCLRaw 提供捆绑包，使你可以轻松地在不同平台之间引入适当的依赖项。

默认情况下，bundle_e_sqlite3 SQLitePCLRaw 包会引入默认值。

若要使用不同的捆绑包，请改为安装 `Microsoft.Data.Sqlite.Core` 包以及要使用的捆绑包。 绑定由 Microsoft 自动初始化。

| 捆绑 | 说明 |
| --- | --- |
| SQLitePCLRaw bundle_e_sqlite3 | 在所有平台上提供一致版本的 SQLite。 包括 FTS4、FTS5、JSON1 和 R * 树扩展。 这是默认值。 |
| SQLitePCLRaw bundle_green | 与 bundle_e_sqlite3 相同，不同之处在于使用系统 SQLite 库的 iOS。 |
| SQLitePCLRaw bundle_zetetic | 使用 Zetetic 中的官方 SQLCipher 生成（不包括在内）。 |
| SQLitePCLRaw bundle_winsqlite3 | 使用 Windows 10 上的 winsqlite3 系统 SQLite 库。 |
| SQLitePCLRaw bundle_e_sqlcipher | 提供 SQLCipher 的非正式开源版本。 |

例如，若要使用 SQLCipher 的非官方开源版本，请使用以下命令。

### <a name="net-core-clitabnetcore-cli"></a>[.NET Core CLI](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a>SQLitePCLRaw 提供程序

通过利用 `SQLitePCLRaw.provider.dynamic_cdecl` 包，你可以使用你自己的 SQLite 版本。 在这种情况下，你需要负责在你的应用程序中部署本机库。 请注意，根据您使用的 .NET 平台和运行时，使用您的应用程序部署本机库的详细信息有所不同。

首先，需要实现 IGetFunctionPointer。 .NET Core 上的实现非常简单。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

接下来，配置 SQLitePCLRaw 提供程序。 确保在你的应用程序中使用了之前完成此操作。 另外，请避免使用可能替代提供程序的 SQLitePCLRaw 捆绑包。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
