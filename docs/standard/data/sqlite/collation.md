---
title: Collation
ms.date: 12/13/2019
description: 了解如何创建自定义排序序列。
ms.openlocfilehash: 9cc574a75c8f5347dd9bb44e36af72e50afa57b4
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777391"
---
# <a name="collation"></a>Collation

比较文本值以确定顺序和相等性时，SQLite 使用排序序列。 在 SQL 查询中创建列或每个操作时，可以指定要使用的排序规则。 SQLite 默认情况下包含三个排序序列。

| Collation | 描述                               |
| --------- | ----------------------------------------- |
| RTRIM     | 忽略尾随空格               |
| NOCASE    | ASCII 字符 a-z 的不区分大小写 |
| BINARY    | 区分大小写。 直接比较字节   |

## <a name="custom-collation"></a>自定义排序规则

您还可以定义自己的排序规则或使用 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>覆盖内置的排序规则。 下面的示例演示如何重写 NOCASE 排序规则以支持 Unicode 字符。 GitHub 上提供了[完整的示例代码](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs)。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like 运算符

SQLite 中的 LIKE 运算符不服从排序规则。 默认实现的语义与 NOCASE 排序规则的语义相同。 对于 ASCII 字符 A 到 Z，只区分大小写。

您可以使用以下杂注语句轻松地使 LIKE 运算符区分大小写：

```sql
PRAGMA case_sensitive_like = 0
```

有关重写 LIKE 运算符的实现的详细信息，请参阅[用户定义函数](user-defined-functions.md)。

## <a name="see-also"></a>另请参阅

* [用户定义的函数](user-defined-functions.md)
* [SQL 语法](https://www.sqlite.org/lang.html)
