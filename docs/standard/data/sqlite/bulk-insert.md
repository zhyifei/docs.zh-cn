---
title: 大容量插入
ms.date: 12/13/2019
description: 对数据库进行大量更改时可以使用的性能提示。
ms.openlocfilehash: 9d87d5c8d70f8e70479f9aa02b7802f73b88de9e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450296"
---
# <a name="bulk-insert"></a>大容量插入

SQLite 没有任何特殊的大容量插入数据的方法。 若要在插入或更新数据时获得最佳性能，请确保执行以下操作：

- 使用事务。
- 重复使用同一个参数化命令。 后续执行将重新使用第一个的编译。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BulkInsertSample/Program.cs?name=snippet_BulkInsert)]
