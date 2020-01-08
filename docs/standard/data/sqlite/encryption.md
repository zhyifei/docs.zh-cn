---
title: 加密
ms.date: 12/13/2019
description: 了解如何加密数据库文件。
ms.openlocfilehash: ccdd4b6b8642b3cde1c2667c9ca432a9b0ef21f2
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450482"
---
# <a name="encryption"></a>加密

SQLite 默认情况下不支持加密数据库文件。 相反，需要使用 SQLite 的修改版本，如[参阅](https://www.hwaci.com/sw/sqlite/see.html)、 [SQLCipher](https://www.zetetic.net/sqlcipher/)、 [SQLiteCrypt](http://www.sqlite-crypt.com/)或[wxSQLite3](https://utelle.github.io/wxsqlite3)。 本文演示如何使用 SQLCipher 的不受支持的开源版本，但该信息也适用于其他解决方案，因为这些解决方案通常遵循相同的模式。

## <a name="installation"></a>安装

### <a name="net-core-clitabnetcore-cli"></a>[.NET Core CLI](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

有关使用不同的本机库进行加密的详细信息，请参阅[自定义 SQLite 版本](custom-versions.md)。

## <a name="specify-the-key"></a>指定密钥

要启用加密，请使用 `Password` 连接字符串关键字指定密钥。 使用 <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> 从用户输入添加或更新值，并避免连接字符串注入攻击。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a>重新生成数据库的密钥

如果要更改数据库的加密密钥，请发出 `PRAGMA rekey` 语句。 若要对数据库进行解密，请指定 `NULL`。

遗憾的是，SQLite 不支持 `PRAGMA` 语句中的参数。 请改用 `quote()` 函数来阻止 SQL 注入。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
