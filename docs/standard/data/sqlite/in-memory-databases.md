---
title: 内存中数据库
ms.date: 12/13/2019
description: 了解如何使用内存中 SQLite 数据库。
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391203"
---
# <a name="in-memory-databases"></a>内存中数据库

SQLite 内存中数据库是完全存储在内存中（而不是磁盘上）的数据库。 使用特殊数据源文件名 `:memory:` 可创建内存中数据库。 连接关闭后，数据库会被删除。 使用 `:memory:` 时，每个连接都会创建自己的数据库。

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>可共享的内存中数据库

在连接字符串中使用 `Mode=Memory` 和 `Cache=Shared` 可以在多个连接之间共享内存中数据库。 `Data Source` 关键字用于为内存中数据库提供名称。 使用相同名称的连接字符串将访问相同的内存中数据库。 只要至少有一个与之相连的连接保持打开状态，数据库便会保持。 GitHub 上提供了对此进行演示的[示例](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs)。

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
