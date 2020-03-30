---
title: 内存中数据库
ms.date: 12/13/2019
description: 了解如何使用内存中 SQLite 数据库。
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391203"
---
# <a name="in-memory-databases"></a>内存中数据库

SQLite 内存中数据库是完全存储在内存中的数据库，而不是存储在磁盘上。 使用特殊的数据源文件名`:memory:`创建内存中数据库。 关闭连接时，将删除数据库。 使用`:memory:`时，每个连接将创建其自己的数据库。

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>可共享内存中数据库

内存中数据库可以通过使用`Mode=Memory`和`Cache=Shared`在连接字符串中在多个连接之间共享。 关键字`Data Source`用于为内存中数据库指定名称。 使用相同名称的连接字符串将访问相同的内存内数据库。 只要数据库至少保持一个连接保持打开状态，数据库就将保持不变。 GitHub 上提供了演示此[示例](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs)。

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
