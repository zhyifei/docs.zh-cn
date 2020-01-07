---
title: Blob i/o
ms.date: 12/13/2019
description: 了解如何使用 SQLite 的 BLOB i/o 功能。
ms.openlocfilehash: 0c133deacdc19684eca3a6724fb398dc01fda558
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450302"
---
# <a name="blob-io"></a>Blob i/o

在读取和写入大型对象时，可以通过将数据流入和流出数据库来减少内存使用量。 这在分析或转换数据时特别有用。

首先，将行插入正常。 使用 `zeroblob()` SQL 函数可在数据库中分配空间，以容纳大型对象。 `last_insert_rowid()` 函数提供了一种简便的方法来获取其 rowid。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

插入行后，打开一个流以使用 <xref:Microsoft.Data.Sqlite.SqliteBlob>写入大型对象。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

若要将大型对象从数据库中流式传输出去，则除了在大对象的列之外，你还必须在此处选择 rowid 或它的其中一个别名。 如果未选择 rowid，则整个对象将加载到内存中。 当正确完成时，`GetStream()` 返回的对象将是一个 `SqliteBlob`。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
