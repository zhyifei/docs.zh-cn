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
# <a name="connection-strings"></a>连接字符串

连接字符串用于指定如何连接到数据库。 Microsoft.Data.Sqlite 中的连接字符串遵循标准[ADO.NET语法](../../../framework/data/adonet/connection-strings.md)作为关键字和值的分号分隔列表。

## <a name="keywords"></a>Keywords

以下连接字符串关键字可用于 Microsoft.Data.Sqlite：

### <a name="data-source"></a>数据源

数据库文件的路径。 *数据源*（没有空格）和*文件名*是此关键字的别名。

SQLite 处理相对于当前工作目录的路径。 也可以指定绝对路径。

如果**为空**，SQLite 将创建一个临时磁盘数据库，该数据库在连接关闭时被删除。

如果`:memory:`使用 内存中数据库。 有关详细信息，请参阅[内存中数据库](in-memory-databases.md)。

以替换字符串开头的`|DataDirectory|`路径与相对路径相同。 如果设置，则根据 DataDirectory 应用程序域属性值制作路径。

此关键字还支持[URI 文件名](https://www.sqlite.org/uri.html)。

### <a name="mode"></a>“模式”

连接模式。

| 值           | 说明                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| 读取写入创建 | 打开数据库进行读取和写入，如果数据库不存在，请创建它。 这是默认值。 |
| ReadWrite       | 打开用于读取和写入的数据库。                                                        |
| ReadOnly        | 以只读模式打开数据库。                                                              |
| 内存          | 打开内存中数据库。                                                                       |

### <a name="cache"></a>缓存

连接使用的缓存模式。

| 值   | 说明                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| 默认 | 使用基础 SQLite 库的默认模式。 这是默认值。                   |
| 专用 | 每个连接都使用专用缓存。                                                          |
| 共享  | 连接共享缓存。 此模式可以更改事务和表锁定的行为。 |

### <a name="password"></a>密码

加密密钥。 指定后，`PRAGMA key`将立即在打开连接后发送。

> [!WARNING]
> 当本机 SQLite 库不支持加密时，密码不起作用。

### <a name="foreign-keys"></a>Foreign Keys

指示是否启用外键约束的值。

| 值   | 说明
| ------- | --- |
| True    | 打开`PRAGMA foreign_keys = 1`连接后立即发送。
| False   | 打开`PRAGMA foreign_keys = 0`连接后立即发送。
| (empty) | 不发送`PRAGMA foreign_keys`。 这是默认值。 |

e_sqlite3 如果SQLITE_DEFAULT_FOREIGN_KEYS用于编译本机 SQLite 库，则无需启用外键。

### <a name="recursive-triggers"></a>递归触发器

指示是否启用递归触发器的值。

| 值 | 说明                                                                 |
| ----- | --------------------------------------------------------------------------- |
| True  | 打开`PRAGMA recursive_triggers`连接后立即发送。 |
| False | 不发送`PRAGMA recursive_triggers`。 这是默认值。              |

## <a name="connection-string-builder"></a>连接字符串生成器

可以使用<xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder>作为创建连接字符串的强类型方法。 它还可用于防止连接字符串注入攻击。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a>示例

### <a name="basic"></a>基本

具有共享缓存的基本连接字符串，用于改进并发性。

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a>加密

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

专用内存数据库。

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a>可共享内存

由名称 *"可共享*"标识的可共享内存数据库。

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a>另请参阅

* [在 ADO.NET 中的连接字符串](../../../framework/data/adonet/connection-strings.md)
* [内存中数据库](in-memory-databases.md)
* [事务](transactions.md)
