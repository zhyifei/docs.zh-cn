---
title: Dapper 限制
ms.date: 12/13/2019
description: 描述使用 Dapper 时可能会遇到的一些限制。
ms.openlocfilehash: 90c7fb24f068d663081390bdba9b1b222b4be56e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450494"
---
# <a name="dapper-limitations"></a><span data-ttu-id="04663-103">Dapper 限制</span><span class="sxs-lookup"><span data-stu-id="04663-103">Dapper limitations</span></span>

<span data-ttu-id="04663-104">使用带有[Dapper 的](https://stackexchange.github.io/Dapper/)时，需要注意几个限制。</span><span class="sxs-lookup"><span data-stu-id="04663-104">There are a few limitations you should be aware of when using Microsoft.Data.Sqlite with [Dapper](https://stackexchange.github.io/Dapper/).</span></span>

## <a name="parameters"></a><span data-ttu-id="04663-105">参数</span><span class="sxs-lookup"><span data-stu-id="04663-105">Parameters</span></span>

<span data-ttu-id="04663-106">SQLite 参数名称区分大小写。</span><span class="sxs-lookup"><span data-stu-id="04663-106">SQLite parameter names are case-sensitive.</span></span> <span data-ttu-id="04663-107">确保 SQL 中使用的参数名称与匿名对象属性的大小写匹配。</span><span class="sxs-lookup"><span data-stu-id="04663-107">Ensure that the parameter names used in SQL match the case of the anonymous object's properties.</span></span> <span data-ttu-id="04663-108">问题[#18861](https://github.com/aspnet/EntityFrameworkCore/issues/18861)会改善此体验。</span><span class="sxs-lookup"><span data-stu-id="04663-108">Issue [#18861](https://github.com/aspnet/EntityFrameworkCore/issues/18861) would improve this experience.</span></span>

<span data-ttu-id="04663-109">Dapper 还要求参数使用 `@` 前缀。</span><span class="sxs-lookup"><span data-stu-id="04663-109">Dapper also expects parameters to use the `@` prefix.</span></span> <span data-ttu-id="04663-110">其他前缀不起作用。</span><span class="sxs-lookup"><span data-stu-id="04663-110">Other prefixes won't work.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a><span data-ttu-id="04663-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="04663-111">Data types</span></span>

<span data-ttu-id="04663-112">Dapper 使用 SqliteDataReader 索引器读取值。</span><span class="sxs-lookup"><span data-stu-id="04663-112">Dapper reads values using the SqliteDataReader indexer.</span></span> <span data-ttu-id="04663-113">此索引器的返回类型是 object，这意味着它将只返回 long、double、string 或 byte [] 值。</span><span class="sxs-lookup"><span data-stu-id="04663-113">The return type of this indexer is object, which means it will only ever return long, double, string, or byte[] values.</span></span> <span data-ttu-id="04663-114">有关详细信息，请参阅[数据类型](types.md)。</span><span class="sxs-lookup"><span data-stu-id="04663-114">For more information, see [Data types](types.md).</span></span> <span data-ttu-id="04663-115">Dapper 处理这些基元类型和其他基元类型之间的大多数转换。</span><span class="sxs-lookup"><span data-stu-id="04663-115">Dapper handles most conversions between these and other primitive types.</span></span> <span data-ttu-id="04663-116">遗憾的是，它不处理 `DateTimeOffset`、`Guid`或 `TimeSpan`。</span><span class="sxs-lookup"><span data-stu-id="04663-116">Unfortunately, it doesn't handle `DateTimeOffset`, `Guid`, or `TimeSpan`.</span></span> <span data-ttu-id="04663-117">如果希望在结果中使用这些类型，请创建类型处理程序。</span><span class="sxs-lookup"><span data-stu-id="04663-117">Create type handlers if you want to use these types in your results.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

<span data-ttu-id="04663-118">请不要忘记在查询前添加类型处理程序。</span><span class="sxs-lookup"><span data-stu-id="04663-118">Don't forget to add the type handlers before querying.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a><span data-ttu-id="04663-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04663-119">See also</span></span>

* [<span data-ttu-id="04663-120">数据类型</span><span class="sxs-lookup"><span data-stu-id="04663-120">Data types</span></span>](types.md)
* [<span data-ttu-id="04663-121">异步限制</span><span class="sxs-lookup"><span data-stu-id="04663-121">Async limitations</span></span>](async.md)
