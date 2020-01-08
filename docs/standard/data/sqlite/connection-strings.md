---
title: 连接字符串
ms.date: 12/13/2019
description: 支持的连接字符串关键字和值。
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450272"
---
# <a name="connection-strings"></a><span data-ttu-id="ff4a8-103">连接字符串</span><span class="sxs-lookup"><span data-stu-id="ff4a8-103">Connection strings</span></span>

<span data-ttu-id="ff4a8-104">连接字符串用于指定如何连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="ff4a8-105">ADO.NET 中的连接字符串将标准的[语法](../../../framework/data/adonet/connection-strings.md)作为分号分隔的关键字和值列表。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="ff4a8-106">关键字</span><span class="sxs-lookup"><span data-stu-id="ff4a8-106">Keywords</span></span>

<span data-ttu-id="ff4a8-107">以下连接字符串关键字可以与 Microsoft. Sqlite 一起使用：</span><span class="sxs-lookup"><span data-stu-id="ff4a8-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="ff4a8-108">数据源</span><span class="sxs-lookup"><span data-stu-id="ff4a8-108">Data source</span></span>

<span data-ttu-id="ff4a8-109">数据库文件的路径。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-109">The path to the database file.</span></span> <span data-ttu-id="ff4a8-110">*数据源*（无空格）和*文件名*是此关键字的别名。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="ff4a8-111">SQLite 处理相对于当前工作目录的路径。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="ff4a8-112">还可以指定绝对路径。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="ff4a8-113">如果**为空**，则 SQLite 会创建一个临时磁盘上的数据库，该数据库在关闭连接时被删除。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="ff4a8-114">如果 `:memory:`，则使用内存中数据库。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="ff4a8-115">有关详细信息，请参阅[内存中数据库](in-memory-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="ff4a8-116">以 `|DataDirectory|` 替换字符串开头的路径与相对路径相同。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="ff4a8-117">如果设置，则相对于 DataDirectory 应用程序域属性值建立路径。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="ff4a8-118">此关键字还支持[URI 文件名](https://www.sqlite.org/uri.html)。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="ff4a8-119">模式</span><span class="sxs-lookup"><span data-stu-id="ff4a8-119">Mode</span></span>

<span data-ttu-id="ff4a8-120">连接模式。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-120">The connection mode.</span></span>

| <span data-ttu-id="ff4a8-121">{2&gt;值&lt;2}</span><span class="sxs-lookup"><span data-stu-id="ff4a8-121">Value</span></span>           | <span data-ttu-id="ff4a8-122">描述</span><span class="sxs-lookup"><span data-stu-id="ff4a8-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ff4a8-123">ReadWriteCreate</span><span class="sxs-lookup"><span data-stu-id="ff4a8-123">ReadWriteCreate</span></span> | <span data-ttu-id="ff4a8-124">打开数据库以进行读取和写入，如果数据库不存在，则创建数据库。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="ff4a8-125">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-125">This is the default.</span></span> |
| <span data-ttu-id="ff4a8-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ff4a8-126">ReadWrite</span></span>       | <span data-ttu-id="ff4a8-127">打开数据库以进行读取和写入。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="ff4a8-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="ff4a8-128">ReadOnly</span></span>        | <span data-ttu-id="ff4a8-129">在只读模式下打开该数据库。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="ff4a8-130">内存</span><span class="sxs-lookup"><span data-stu-id="ff4a8-130">Memory</span></span>          | <span data-ttu-id="ff4a8-131">打开内存中数据库。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="ff4a8-132">高速缓存</span><span class="sxs-lookup"><span data-stu-id="ff4a8-132">Cache</span></span>

<span data-ttu-id="ff4a8-133">连接使用的缓存模式。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="ff4a8-134">{2&gt;值&lt;2}</span><span class="sxs-lookup"><span data-stu-id="ff4a8-134">Value</span></span>   | <span data-ttu-id="ff4a8-135">描述</span><span class="sxs-lookup"><span data-stu-id="ff4a8-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ff4a8-136">默认值</span><span class="sxs-lookup"><span data-stu-id="ff4a8-136">Default</span></span> | <span data-ttu-id="ff4a8-137">使用基础 SQLite 库的默认模式。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="ff4a8-138">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-138">This is the default.</span></span>                   |
| <span data-ttu-id="ff4a8-139">Private</span><span class="sxs-lookup"><span data-stu-id="ff4a8-139">Private</span></span> | <span data-ttu-id="ff4a8-140">每个连接使用一个专用缓存。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="ff4a8-141">共享</span><span class="sxs-lookup"><span data-stu-id="ff4a8-141">Shared</span></span>  | <span data-ttu-id="ff4a8-142">连接共享缓存。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-142">Connections share a cache.</span></span> <span data-ttu-id="ff4a8-143">此模式可以更改事务和表锁定的行为。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="ff4a8-144">密码</span><span class="sxs-lookup"><span data-stu-id="ff4a8-144">Password</span></span>

<span data-ttu-id="ff4a8-145">加密密钥。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-145">The encryption key.</span></span> <span data-ttu-id="ff4a8-146">指定后，将立即在打开连接后发送 `PRAGMA key`。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="ff4a8-147">如果本机 SQLite 库不支持加密，则密码不起作用。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="ff4a8-148">Foreign Keys</span><span class="sxs-lookup"><span data-stu-id="ff4a8-148">Foreign Keys</span></span>

<span data-ttu-id="ff4a8-149">一个值，该值指示是否启用 foreign key 约束。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="ff4a8-150">{2&gt;值&lt;2}</span><span class="sxs-lookup"><span data-stu-id="ff4a8-150">Value</span></span>   | <span data-ttu-id="ff4a8-151">描述</span><span class="sxs-lookup"><span data-stu-id="ff4a8-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="ff4a8-152">True</span><span class="sxs-lookup"><span data-stu-id="ff4a8-152">True</span></span>    | <span data-ttu-id="ff4a8-153">打开连接后立即发送 `PRAGMA foreign_keys = 1`。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="ff4a8-154">False</span><span class="sxs-lookup"><span data-stu-id="ff4a8-154">False</span></span>   | <span data-ttu-id="ff4a8-155">打开连接后立即发送 `PRAGMA foreign_keys = 0`。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="ff4a8-156">（空）</span><span class="sxs-lookup"><span data-stu-id="ff4a8-156">(empty)</span></span> | <span data-ttu-id="ff4a8-157">不发送 `PRAGMA foreign_keys`。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="ff4a8-158">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-158">This is the default.</span></span> |

<span data-ttu-id="ff4a8-159">如果 e_sqlite3，则无需启用外键，SQLITE_DEFAULT_FOREIGN_KEYS 用于编译本机 SQLite 库。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="ff4a8-160">递归触发器</span><span class="sxs-lookup"><span data-stu-id="ff4a8-160">Recursive triggers</span></span>

<span data-ttu-id="ff4a8-161">一个值，该值指示是否启用递归触发器。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="ff4a8-162">{2&gt;值&lt;2}</span><span class="sxs-lookup"><span data-stu-id="ff4a8-162">Value</span></span> | <span data-ttu-id="ff4a8-163">描述</span><span class="sxs-lookup"><span data-stu-id="ff4a8-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="ff4a8-164">True</span><span class="sxs-lookup"><span data-stu-id="ff4a8-164">True</span></span>  | <span data-ttu-id="ff4a8-165">打开连接后立即发送 `PRAGMA recursive_triggers`。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="ff4a8-166">False</span><span class="sxs-lookup"><span data-stu-id="ff4a8-166">False</span></span> | <span data-ttu-id="ff4a8-167">不发送 `PRAGMA recursive_triggers`。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="ff4a8-168">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="ff4a8-169">连接字符串生成器</span><span class="sxs-lookup"><span data-stu-id="ff4a8-169">Connection string builder</span></span>

<span data-ttu-id="ff4a8-170">您可以使用 <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> 作为创建连接字符串的强类型方式。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="ff4a8-171">它还可用于阻止连接字符串注入攻击。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="ff4a8-172">示例</span><span class="sxs-lookup"><span data-stu-id="ff4a8-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="ff4a8-173">Basic</span><span class="sxs-lookup"><span data-stu-id="ff4a8-173">Basic</span></span>

<span data-ttu-id="ff4a8-174">一个包含共享缓存的基本连接字符串，用于改进并发性。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="ff4a8-175">已加密</span><span class="sxs-lookup"><span data-stu-id="ff4a8-175">Encrypted</span></span>

<span data-ttu-id="ff4a8-176">加密的数据库。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="ff4a8-177">只读</span><span class="sxs-lookup"><span data-stu-id="ff4a8-177">Read-only</span></span>

<span data-ttu-id="ff4a8-178">应用无法修改的只读数据库。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="ff4a8-179">内存中</span><span class="sxs-lookup"><span data-stu-id="ff4a8-179">In-memory</span></span>

<span data-ttu-id="ff4a8-180">一个专用的内存中数据库。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="ff4a8-181">可共享内存中</span><span class="sxs-lookup"><span data-stu-id="ff4a8-181">Sharable in-memory</span></span>

<span data-ttu-id="ff4a8-182">由可*共享*的名称标识的可共享内存中数据库。</span><span class="sxs-lookup"><span data-stu-id="ff4a8-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="ff4a8-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff4a8-183">See also</span></span>

* [<span data-ttu-id="ff4a8-184">ADO.NET 中的连接字符串</span><span class="sxs-lookup"><span data-stu-id="ff4a8-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="ff4a8-185">内存中数据库</span><span class="sxs-lookup"><span data-stu-id="ff4a8-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="ff4a8-186">事务</span><span class="sxs-lookup"><span data-stu-id="ff4a8-186">Transactions</span></span>](transactions.md)
