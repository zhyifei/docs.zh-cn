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
# <a name="connection-strings"></a>连接字符串

连接字符串用于指定如何连接到数据库。 ADO.NET 中的连接字符串将标准的[语法](../../../framework/data/adonet/connection-strings.md)作为分号分隔的关键字和值列表。

## <a name="keywords"></a>关键字

以下连接字符串关键字可以与 Microsoft. Sqlite 一起使用：

### <a name="data-source"></a>数据源

数据库文件的路径。 *数据源*（无空格）和*文件名*是此关键字的别名。

SQLite 处理相对于当前工作目录的路径。 还可以指定绝对路径。

如果**为空**，则 SQLite 会创建一个临时磁盘上的数据库，该数据库在关闭连接时被删除。

如果 `:memory:`，则使用内存中数据库。 有关详细信息，请参阅[内存中数据库](in-memory-databases.md)。

以 `|DataDirectory|` 替换字符串开头的路径与相对路径相同。 如果设置，则相对于 DataDirectory 应用程序域属性值建立路径。

此关键字还支持[URI 文件名](https://www.sqlite.org/uri.html)。

### <a name="mode"></a>模式

连接模式。

| {2&gt;值&lt;2}           | 描述                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| ReadWriteCreate | 打开数据库以进行读取和写入，如果数据库不存在，则创建数据库。 这是默认设置。 |
| ReadWrite       | 打开数据库以进行读取和写入。                                                        |
| ReadOnly        | 在只读模式下打开该数据库。                                                              |
| 内存          | 打开内存中数据库。                                                                       |

### <a name="cache"></a>高速缓存

连接使用的缓存模式。

| {2&gt;值&lt;2}   | 描述                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| 默认值 | 使用基础 SQLite 库的默认模式。 这是默认设置。                   |
| Private | 每个连接使用一个专用缓存。                                                          |
| 共享  | 连接共享缓存。 此模式可以更改事务和表锁定的行为。 |

### <a name="password"></a>密码

加密密钥。 指定后，将立即在打开连接后发送 `PRAGMA key`。

> [!WARNING]
> 如果本机 SQLite 库不支持加密，则密码不起作用。

### <a name="foreign-keys"></a>Foreign Keys

一个值，该值指示是否启用 foreign key 约束。

| {2&gt;值&lt;2}   | 描述
| ------- | --- |
| True    | 打开连接后立即发送 `PRAGMA foreign_keys = 1`。
| False   | 打开连接后立即发送 `PRAGMA foreign_keys = 0`。
| （空） | 不发送 `PRAGMA foreign_keys`。 这是默认设置。 |

如果 e_sqlite3，则无需启用外键，SQLITE_DEFAULT_FOREIGN_KEYS 用于编译本机 SQLite 库。

### <a name="recursive-triggers"></a>递归触发器

一个值，该值指示是否启用递归触发器。

| {2&gt;值&lt;2} | 描述                                                                 |
| ----- | --------------------------------------------------------------------------- |
| True  | 打开连接后立即发送 `PRAGMA recursive_triggers`。 |
| False | 不发送 `PRAGMA recursive_triggers`。 这是默认设置。              |

## <a name="connection-string-builder"></a>连接字符串生成器

您可以使用 <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> 作为创建连接字符串的强类型方式。 它还可用于阻止连接字符串注入攻击。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a>示例

### <a name="basic"></a>Basic

一个包含共享缓存的基本连接字符串，用于改进并发性。

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a>已加密

加密的数据库。

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a>只读

应用无法修改的只读数据库。

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a>内存中

一个专用的内存中数据库。

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a>可共享内存中

由可*共享*的名称标识的可共享内存中数据库。

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a>另请参阅

* [ADO.NET 中的连接字符串](../../../framework/data/adonet/connection-strings.md)
* [内存中数据库](in-memory-databases.md)
* [事务](transactions.md)
