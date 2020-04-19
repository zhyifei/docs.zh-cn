---
title: 排序规则
ms.date: 12/13/2019
description: 了解如何创建自定义整理序列。
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242967"
---
# <a name="collation"></a>排序规则

SQLite 在比较 TEXT 值以确定顺序和相等性时使用分字序列。 您可以指定在 SQL 查询中创建列或每个操作时要使用的排序规则。 默认情况下，SQLite 包括三个整理序列。

| 排序规则 | 说明                               |
| --------- | ----------------------------------------- |
| RTRIM     | 忽略尾随空格               |
| 无案例    | ASCII 字符 A-Z 不区分大小写 |
| BINARY    | 区分大小写。 直接比较字节   |

## <a name="custom-collation"></a>自定义排序规则

您还可以定义自己的整理序列或使用 重写的序列<xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>。 下面的示例显示覆盖 NOCASE 排序规则以支持 Unicode 字符。 [完整的示例代码](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs)在 GitHub 上可用。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like 运算符

SQLite 中的 LIKE 运算符不遵循排序规则。 默认实现具有与 NOCASE 排序规则相同的语义。 它仅对 ASCII 字符 A 到 Z 不区分大小写。

通过使用以下杂注语句，可以轻松地使 LIKE 运算符区分大小写：

```sql
PRAGMA case_sensitive_like = 1
```

有关重写 LIKE 运算符实现的详细信息，请参阅[用户定义的函数](user-defined-functions.md)。

## <a name="see-also"></a>另请参阅

* [用户定义的函数](user-defined-functions.md)
* [SQL 语法](https://www.sqlite.org/lang.html)
