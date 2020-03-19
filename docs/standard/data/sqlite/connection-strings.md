---
title: 连接字符串
ms.date: 12/13/2019
description: 支持的关键字和连接字符串的值。
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401195"
---
# <a name="connection-strings"></a><span data-ttu-id="a5a0d-103">连接字符串</span><span class="sxs-lookup"><span data-stu-id="a5a0d-103">Connection strings</span></span>

<span data-ttu-id="a5a0d-104">连接字符串用于指定如何连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-104">A connection string is used to specify how to connect to the database.</span></span> <span data-ttu-id="a5a0d-105">Microsoft.Data.Sqlite 中的连接字符串遵循标准[ADO.NET语法](../../../framework/data/adonet/connection-strings.md)作为关键字和值的分号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-105">Connection strings in Microsoft.Data.Sqlite follow the standard [ADO.NET syntax](../../../framework/data/adonet/connection-strings.md) as a semicolon-separated list of keywords and values.</span></span>

## <a name="keywords"></a><span data-ttu-id="a5a0d-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="a5a0d-106">Keywords</span></span>

<span data-ttu-id="a5a0d-107">以下连接字符串关键字可用于 Microsoft.Data.Sqlite：</span><span class="sxs-lookup"><span data-stu-id="a5a0d-107">The following connection string keywords can be used with Microsoft.Data.Sqlite:</span></span>

### <a name="data-source"></a><span data-ttu-id="a5a0d-108">数据源</span><span class="sxs-lookup"><span data-stu-id="a5a0d-108">Data source</span></span>

<span data-ttu-id="a5a0d-109">数据库文件的路径。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-109">The path to the database file.</span></span> <span data-ttu-id="a5a0d-110">*数据源*（没有空格）和*文件名*是此关键字的别名。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-110">*DataSource* (without a space) and *Filename* are aliases of this keyword.</span></span>

<span data-ttu-id="a5a0d-111">SQLite 处理相对于当前工作目录的路径。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-111">SQLite treats paths relative to the current working directory.</span></span> <span data-ttu-id="a5a0d-112">也可以指定绝对路径。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-112">Absolute paths can also be specified.</span></span>

<span data-ttu-id="a5a0d-113">如果**为空**，SQLite 将创建一个临时磁盘数据库，该数据库在连接关闭时被删除。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-113">If **empty**, SQLite creates a temporary on-disk database that's deleted when the connection is closed.</span></span>

<span data-ttu-id="a5a0d-114">如果`:memory:`使用 内存中数据库。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-114">If `:memory:`, an in-memory database is used.</span></span> <span data-ttu-id="a5a0d-115">有关详细信息，请参阅[内存中数据库](in-memory-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-115">For more information, see [In-Memory databases](in-memory-databases.md).</span></span>

<span data-ttu-id="a5a0d-116">以替换字符串开头的`|DataDirectory|`路径与相对路径相同。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-116">Paths that start with the `|DataDirectory|` substitution string are treated the same as relative paths.</span></span> <span data-ttu-id="a5a0d-117">如果设置，则根据 DataDirectory 应用程序域属性值制作路径。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-117">If set, paths are made relative to the DataDirectory application domain property value.</span></span>

<span data-ttu-id="a5a0d-118">此关键字还支持[URI 文件名](https://www.sqlite.org/uri.html)。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-118">This keyword also supports [URI Filenames](https://www.sqlite.org/uri.html).</span></span>

### <a name="mode"></a><span data-ttu-id="a5a0d-119">“模式”</span><span class="sxs-lookup"><span data-stu-id="a5a0d-119">Mode</span></span>

<span data-ttu-id="a5a0d-120">连接模式。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-120">The connection mode.</span></span>

| <span data-ttu-id="a5a0d-121">值</span><span class="sxs-lookup"><span data-stu-id="a5a0d-121">Value</span></span>           | <span data-ttu-id="a5a0d-122">说明</span><span class="sxs-lookup"><span data-stu-id="a5a0d-122">Description</span></span>                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="a5a0d-123">读取写入创建</span><span class="sxs-lookup"><span data-stu-id="a5a0d-123">ReadWriteCreate</span></span> | <span data-ttu-id="a5a0d-124">打开数据库进行读取和写入，如果数据库不存在，请创建它。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-124">Opens the database for reading and writing, and creates it if it doesn't exist.</span></span> <span data-ttu-id="a5a0d-125">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-125">This is the default.</span></span> |
| <span data-ttu-id="a5a0d-126">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a5a0d-126">ReadWrite</span></span>       | <span data-ttu-id="a5a0d-127">打开用于读取和写入的数据库。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-127">Opens the database for reading and writing.</span></span>                                                        |
| <span data-ttu-id="a5a0d-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="a5a0d-128">ReadOnly</span></span>        | <span data-ttu-id="a5a0d-129">以只读模式打开数据库。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-129">Opens the database in read-only mode.</span></span>                                                              |
| <span data-ttu-id="a5a0d-130">内存</span><span class="sxs-lookup"><span data-stu-id="a5a0d-130">Memory</span></span>          | <span data-ttu-id="a5a0d-131">打开内存中数据库。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-131">Opens an in-memory database.</span></span>                                                                       |

### <a name="cache"></a><span data-ttu-id="a5a0d-132">缓存</span><span class="sxs-lookup"><span data-stu-id="a5a0d-132">Cache</span></span>

<span data-ttu-id="a5a0d-133">连接使用的缓存模式。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-133">The caching mode used by the connection.</span></span>

| <span data-ttu-id="a5a0d-134">值</span><span class="sxs-lookup"><span data-stu-id="a5a0d-134">Value</span></span>   | <span data-ttu-id="a5a0d-135">说明</span><span class="sxs-lookup"><span data-stu-id="a5a0d-135">Description</span></span>                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| <span data-ttu-id="a5a0d-136">默认</span><span class="sxs-lookup"><span data-stu-id="a5a0d-136">Default</span></span> | <span data-ttu-id="a5a0d-137">使用基础 SQLite 库的默认模式。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-137">Uses the default mode of the underlying SQLite library.</span></span> <span data-ttu-id="a5a0d-138">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-138">This is the default.</span></span>                   |
| <span data-ttu-id="a5a0d-139">专用</span><span class="sxs-lookup"><span data-stu-id="a5a0d-139">Private</span></span> | <span data-ttu-id="a5a0d-140">每个连接都使用专用缓存。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-140">Each connection uses a private cache.</span></span>                                                          |
| <span data-ttu-id="a5a0d-141">共享</span><span class="sxs-lookup"><span data-stu-id="a5a0d-141">Shared</span></span>  | <span data-ttu-id="a5a0d-142">连接共享缓存。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-142">Connections share a cache.</span></span> <span data-ttu-id="a5a0d-143">此模式可以更改事务和表锁定的行为。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-143">This mode can change the behavior of transaction and table locking.</span></span> |

### <a name="password"></a><span data-ttu-id="a5a0d-144">密码</span><span class="sxs-lookup"><span data-stu-id="a5a0d-144">Password</span></span>

<span data-ttu-id="a5a0d-145">加密密钥。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-145">The encryption key.</span></span> <span data-ttu-id="a5a0d-146">指定后，`PRAGMA key`将立即在打开连接后发送。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-146">When specified, `PRAGMA key` is sent immediately after opening the connection.</span></span>

> [!WARNING]
> <span data-ttu-id="a5a0d-147">当本机 SQLite 库不支持加密时，密码不起作用。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-147">Password has no effect when encryption isn't supported by the native SQLite library.</span></span>

### <a name="foreign-keys"></a><span data-ttu-id="a5a0d-148">Foreign Keys</span><span class="sxs-lookup"><span data-stu-id="a5a0d-148">Foreign Keys</span></span>

<span data-ttu-id="a5a0d-149">指示是否启用外键约束的值。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-149">A value indicating whether to enable foreign key constraints.</span></span>

| <span data-ttu-id="a5a0d-150">值</span><span class="sxs-lookup"><span data-stu-id="a5a0d-150">Value</span></span>   | <span data-ttu-id="a5a0d-151">说明</span><span class="sxs-lookup"><span data-stu-id="a5a0d-151">Description</span></span>
| ------- | --- |
| <span data-ttu-id="a5a0d-152">True</span><span class="sxs-lookup"><span data-stu-id="a5a0d-152">True</span></span>    | <span data-ttu-id="a5a0d-153">打开`PRAGMA foreign_keys = 1`连接后立即发送。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-153">Sends `PRAGMA foreign_keys = 1` immediately after opening the connection.</span></span>
| <span data-ttu-id="a5a0d-154">False</span><span class="sxs-lookup"><span data-stu-id="a5a0d-154">False</span></span>   | <span data-ttu-id="a5a0d-155">打开`PRAGMA foreign_keys = 0`连接后立即发送。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-155">Sends `PRAGMA foreign_keys = 0` immediately after opening the connection.</span></span>
| <span data-ttu-id="a5a0d-156">(empty)</span><span class="sxs-lookup"><span data-stu-id="a5a0d-156">(empty)</span></span> | <span data-ttu-id="a5a0d-157">不发送`PRAGMA foreign_keys`。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-157">Doesn't send `PRAGMA foreign_keys`.</span></span> <span data-ttu-id="a5a0d-158">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-158">This is the default.</span></span> |

<span data-ttu-id="a5a0d-159">e_sqlite3 如果SQLITE_DEFAULT_FOREIGN_KEYS用于编译本机 SQLite 库，则无需启用外键。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-159">There's no need enable foreign keys if, like in e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS was used to compile the native SQLite library.</span></span>

### <a name="recursive-triggers"></a><span data-ttu-id="a5a0d-160">递归触发器</span><span class="sxs-lookup"><span data-stu-id="a5a0d-160">Recursive triggers</span></span>

<span data-ttu-id="a5a0d-161">指示是否启用递归触发器的值。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-161">A value that indicates whether to enable recursive triggers.</span></span>

| <span data-ttu-id="a5a0d-162">值</span><span class="sxs-lookup"><span data-stu-id="a5a0d-162">Value</span></span> | <span data-ttu-id="a5a0d-163">说明</span><span class="sxs-lookup"><span data-stu-id="a5a0d-163">Description</span></span>                                                                 |
| ----- | --------------------------------------------------------------------------- |
| <span data-ttu-id="a5a0d-164">True</span><span class="sxs-lookup"><span data-stu-id="a5a0d-164">True</span></span>  | <span data-ttu-id="a5a0d-165">打开`PRAGMA recursive_triggers`连接后立即发送。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-165">Sends `PRAGMA recursive_triggers` immediately after opening the connection.</span></span> |
| <span data-ttu-id="a5a0d-166">False</span><span class="sxs-lookup"><span data-stu-id="a5a0d-166">False</span></span> | <span data-ttu-id="a5a0d-167">不发送`PRAGMA recursive_triggers`。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-167">Doesn't send `PRAGMA recursive_triggers`.</span></span> <span data-ttu-id="a5a0d-168">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-168">This is the default.</span></span>              |

## <a name="connection-string-builder"></a><span data-ttu-id="a5a0d-169">连接字符串生成器</span><span class="sxs-lookup"><span data-stu-id="a5a0d-169">Connection string builder</span></span>

<span data-ttu-id="a5a0d-170">可以使用<xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>作为创建连接字符串的强类型方法。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-170">You can use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> as a strongly typed way of creating connection strings.</span></span> <span data-ttu-id="a5a0d-171">它还可用于防止连接字符串注入攻击。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-171">It can also be used to prevent connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a><span data-ttu-id="a5a0d-172">示例</span><span class="sxs-lookup"><span data-stu-id="a5a0d-172">Examples</span></span>

### <a name="basic"></a><span data-ttu-id="a5a0d-173">基本</span><span class="sxs-lookup"><span data-stu-id="a5a0d-173">Basic</span></span>

<span data-ttu-id="a5a0d-174">具有共享缓存的基本连接字符串，用于改进并发性。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-174">A basic connection string with a shared cache for improved concurrency.</span></span>

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a><span data-ttu-id="a5a0d-175">加密</span><span class="sxs-lookup"><span data-stu-id="a5a0d-175">Encrypted</span></span>

<span data-ttu-id="a5a0d-176">加密的数据库。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-176">An encrypted database.</span></span>

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a><span data-ttu-id="a5a0d-177">只读</span><span class="sxs-lookup"><span data-stu-id="a5a0d-177">Read-only</span></span>

<span data-ttu-id="a5a0d-178">应用无法修改的只读数据库。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-178">A read-only database that cannot be modified by the app.</span></span>

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a><span data-ttu-id="a5a0d-179">内存中</span><span class="sxs-lookup"><span data-stu-id="a5a0d-179">In-memory</span></span>

<span data-ttu-id="a5a0d-180">专用内存数据库。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-180">A private, in-memory database.</span></span>

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a><span data-ttu-id="a5a0d-181">可共享内存</span><span class="sxs-lookup"><span data-stu-id="a5a0d-181">Sharable in-memory</span></span>

<span data-ttu-id="a5a0d-182">由名称 *"可共享*"标识的可共享内存数据库。</span><span class="sxs-lookup"><span data-stu-id="a5a0d-182">A sharable, in-memory database identified by the name *Sharable*.</span></span>

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a><span data-ttu-id="a5a0d-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5a0d-183">See also</span></span>

* [<span data-ttu-id="a5a0d-184">在 ADO.NET 中的连接字符串</span><span class="sxs-lookup"><span data-stu-id="a5a0d-184">Connection Strings in ADO.NET</span></span>](../../../framework/data/adonet/connection-strings.md)
* [<span data-ttu-id="a5a0d-185">内存中数据库</span><span class="sxs-lookup"><span data-stu-id="a5a0d-185">In-Memory databases</span></span>](in-memory-databases.md)
* [<span data-ttu-id="a5a0d-186">事务</span><span class="sxs-lookup"><span data-stu-id="a5a0d-186">Transactions</span></span>](transactions.md)
