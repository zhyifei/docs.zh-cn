---
title: Blob I/O
ms.date: 12/13/2019
description: 了解如何使用 SQLite 的 BLOB I/O 功能。
ms.openlocfilehash: 0c133deacdc19684eca3a6724fb398dc01fda558
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450302"
---
# <a name="blob-io"></a><span data-ttu-id="29c25-103">Blob I/O</span><span class="sxs-lookup"><span data-stu-id="29c25-103">Blob I/O</span></span>

<span data-ttu-id="29c25-104">通过将数据流式传输到以及流式传输出数据库，可以在读写大型对象的同时减少内存使用量。</span><span class="sxs-lookup"><span data-stu-id="29c25-104">You can reduce memory usage while reading and writing large objects by streaming the data into and out of the database.</span></span> <span data-ttu-id="29c25-105">在分析或转换数据时，此功能特别有用。</span><span class="sxs-lookup"><span data-stu-id="29c25-105">This can be especially useful when parsing or transforming the data.</span></span>

<span data-ttu-id="29c25-106">首先像往常一样插入一个行。</span><span class="sxs-lookup"><span data-stu-id="29c25-106">Start by inserting a row as normal.</span></span> <span data-ttu-id="29c25-107">使用 `zeroblob()` SQL 函数分配数据库空间，用于保存大型对象。</span><span class="sxs-lookup"><span data-stu-id="29c25-107">Use the `zeroblob()` SQL function to allocate space in the database to hold the large object.</span></span> <span data-ttu-id="29c25-108">通过 `last_insert_rowid()` 函数，可快捷地获得其 rowid。</span><span class="sxs-lookup"><span data-stu-id="29c25-108">The `last_insert_rowid()` function provides a convenient way to get its rowid.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

<span data-ttu-id="29c25-109">插入行后，打开一个流，以使用 <xref:Microsoft.Data.Sqlite.SqliteBlob> 写入大型对象。</span><span class="sxs-lookup"><span data-stu-id="29c25-109">After inserting the row, open a stream to write the large object using <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

<span data-ttu-id="29c25-110">若要将大型对象流式传输出数据库，除了选中大型对象的列之外，还必须选中 rowid 或它的一个别名，如此处所示。</span><span class="sxs-lookup"><span data-stu-id="29c25-110">To stream the large object out of the database, you must select the rowid or one of its aliases as show here in addition to the large object's column.</span></span> <span data-ttu-id="29c25-111">若未选中 rowid，则会将整个对象加载到内存。</span><span class="sxs-lookup"><span data-stu-id="29c25-111">If you don't select the rowid, the entire object will be loaded into memory.</span></span> <span data-ttu-id="29c25-112">如果操作正确，`GetStream()` 返回的对象将为 `SqliteBlob`。</span><span class="sxs-lookup"><span data-stu-id="29c25-112">The object returned by `GetStream()` will be a `SqliteBlob` when done correctly.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
