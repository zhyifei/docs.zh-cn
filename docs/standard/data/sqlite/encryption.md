---
title: 加密
ms.date: 12/13/2019
description: 了解如何加密数据库文件。
ms.openlocfilehash: ccdd4b6b8642b3cde1c2667c9ca432a9b0ef21f2
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450482"
---
# <a name="encryption"></a><span data-ttu-id="2a21c-103">加密</span><span class="sxs-lookup"><span data-stu-id="2a21c-103">Encryption</span></span>

<span data-ttu-id="2a21c-104">SQLite 在默认情况下不支持加密数据库文件。</span><span class="sxs-lookup"><span data-stu-id="2a21c-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="2a21c-105">而是需要使用修改后的 SQLite 版本，如 [SEE](https://www.hwaci.com/sw/sqlite/see.html)、[SQLCipher](https://www.zetetic.net/sqlcipher/)、[SQLiteCrypt](http://www.sqlite-crypt.com/) 或 [wxSQLite3](https://utelle.github.io/wxsqlite3)。</span><span class="sxs-lookup"><span data-stu-id="2a21c-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="2a21c-106">本文演示如何使用 SQLCipher 的不受支持的开放源代码内部版本，但该信息也适用于其他解决方案，因为它们通常遵循相同的模式。</span><span class="sxs-lookup"><span data-stu-id="2a21c-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="2a21c-107">安装</span><span class="sxs-lookup"><span data-stu-id="2a21c-107">Installation</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="2a21c-108">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="2a21c-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="2a21c-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2a21c-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="2a21c-110">有关使用不同的本机库进行加密的详细信息，请参阅[自定义 SQLite 版本](custom-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="2a21c-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="2a21c-111">指定密钥</span><span class="sxs-lookup"><span data-stu-id="2a21c-111">Specify the key</span></span>

<span data-ttu-id="2a21c-112">若要启用加密，请使用 `Password` 连接字符串关键字指定密钥。</span><span class="sxs-lookup"><span data-stu-id="2a21c-112">To enable encryption, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="2a21c-113">使用 <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> 可从用户输入添加或更新值，并避免连接字符串注入攻击。</span><span class="sxs-lookup"><span data-stu-id="2a21c-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a><span data-ttu-id="2a21c-114">对数据库重新生成密钥</span><span class="sxs-lookup"><span data-stu-id="2a21c-114">Rekeying the database</span></span>

<span data-ttu-id="2a21c-115">如果要更改数据库的加密密钥，请发出 `PRAGMA rekey` 语句。</span><span class="sxs-lookup"><span data-stu-id="2a21c-115">If you want to change the encryption key of a database, issue a `PRAGMA rekey` statement.</span></span> <span data-ttu-id="2a21c-116">若要解密数据库，请指定 `NULL`。</span><span class="sxs-lookup"><span data-stu-id="2a21c-116">To decrypt the database, specify `NULL`.</span></span>

<span data-ttu-id="2a21c-117">遗憾的是，SQLite 在 `PRAGMA` 语句中不支持参数。</span><span class="sxs-lookup"><span data-stu-id="2a21c-117">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="2a21c-118">请改用 `quote()` 函数防止 SQL 注入。</span><span class="sxs-lookup"><span data-stu-id="2a21c-118">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
