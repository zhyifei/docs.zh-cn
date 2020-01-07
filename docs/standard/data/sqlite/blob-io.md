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
# <a name="blob-io"></a><span data-ttu-id="cbaf3-103">Blob i/o</span><span class="sxs-lookup"><span data-stu-id="cbaf3-103">Blob I/O</span></span>

<span data-ttu-id="cbaf3-104">在读取和写入大型对象时，可以通过将数据流入和流出数据库来减少内存使用量。</span><span class="sxs-lookup"><span data-stu-id="cbaf3-104">You can reduce memory usage while reading and writing large objects by streaming the data into and out of the database.</span></span> <span data-ttu-id="cbaf3-105">这在分析或转换数据时特别有用。</span><span class="sxs-lookup"><span data-stu-id="cbaf3-105">This can be especially useful when parsing or transforming the data.</span></span>

<span data-ttu-id="cbaf3-106">首先，将行插入正常。</span><span class="sxs-lookup"><span data-stu-id="cbaf3-106">Start by inserting a row as normal.</span></span> <span data-ttu-id="cbaf3-107">使用 `zeroblob()` SQL 函数可在数据库中分配空间，以容纳大型对象。</span><span class="sxs-lookup"><span data-stu-id="cbaf3-107">Use the `zeroblob()` SQL function to allocate space in the database to hold the large object.</span></span> <span data-ttu-id="cbaf3-108">`last_insert_rowid()` 函数提供了一种简便的方法来获取其 rowid。</span><span class="sxs-lookup"><span data-stu-id="cbaf3-108">The `last_insert_rowid()` function provides a convenient way to get its rowid.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

<span data-ttu-id="cbaf3-109">插入行后，打开一个流以使用 <xref:Microsoft.Data.Sqlite.SqliteBlob>写入大型对象。</span><span class="sxs-lookup"><span data-stu-id="cbaf3-109">After inserting the row, open a stream to write the large object using <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

<span data-ttu-id="cbaf3-110">若要将大型对象从数据库中流式传输出去，则除了在大对象的列之外，你还必须在此处选择 rowid 或它的其中一个别名。</span><span class="sxs-lookup"><span data-stu-id="cbaf3-110">To stream the large object out of the database, you must select the rowid or one of its aliases as show here in addition to the large object's column.</span></span> <span data-ttu-id="cbaf3-111">如果未选择 rowid，则整个对象将加载到内存中。</span><span class="sxs-lookup"><span data-stu-id="cbaf3-111">If you don't select the rowid, the entire object will be loaded into memory.</span></span> <span data-ttu-id="cbaf3-112">当正确完成时，`GetStream()` 返回的对象将是一个 `SqliteBlob`。</span><span class="sxs-lookup"><span data-stu-id="cbaf3-112">The object returned by `GetStream()` will be a `SqliteBlob` when done correctly.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
