---
title: 参数
ms.date: 12/13/2019
description: 了解如何使用 SQL 参数。
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450422"
---
# <a name="parameters"></a><span data-ttu-id="5f82f-103">参数</span><span class="sxs-lookup"><span data-stu-id="5f82f-103">Parameters</span></span>

<span data-ttu-id="5f82f-104">参数用于防范 SQL 注入式攻击。</span><span class="sxs-lookup"><span data-stu-id="5f82f-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="5f82f-105">使用参数可以确保输入只被视为文本值，而永远不会执行，而不是使用 SQL 语句连接用户输入。</span><span class="sxs-lookup"><span data-stu-id="5f82f-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="5f82f-106">在 SQLite 中，SQL 语句中允许使用文本的任何位置通常都允许使用参数。</span><span class="sxs-lookup"><span data-stu-id="5f82f-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="5f82f-107">参数可以为 `:`、`@`或 `$`加前缀。</span><span class="sxs-lookup"><span data-stu-id="5f82f-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="5f82f-108">有关如何将 .NET 值映射到 SQLite 值的详细信息，请参阅[数据类型](types.md)。</span><span class="sxs-lookup"><span data-stu-id="5f82f-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="5f82f-109">截断</span><span class="sxs-lookup"><span data-stu-id="5f82f-109">Truncation</span></span>

<span data-ttu-id="5f82f-110">使用 <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> 属性可截断文本和 BLOB 值。</span><span class="sxs-lookup"><span data-stu-id="5f82f-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="5f82f-111">替代类型</span><span class="sxs-lookup"><span data-stu-id="5f82f-111">Alternative types</span></span>

<span data-ttu-id="5f82f-112">有时，你可能想要使用备用 SQLite 类型。</span><span class="sxs-lookup"><span data-stu-id="5f82f-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="5f82f-113">通过设置 <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> 属性来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5f82f-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="5f82f-114">可以使用以下替代类型映射。</span><span class="sxs-lookup"><span data-stu-id="5f82f-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="5f82f-115">有关默认映射的详细数据类型，请参阅[数据类型](types.md)。</span><span class="sxs-lookup"><span data-stu-id="5f82f-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="5f82f-116">{2&gt;值&lt;2}</span><span class="sxs-lookup"><span data-stu-id="5f82f-116">Value</span></span>          | <span data-ttu-id="5f82f-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="5f82f-117">SqliteType</span></span> | <span data-ttu-id="5f82f-118">备注</span><span class="sxs-lookup"><span data-stu-id="5f82f-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="5f82f-119">Char</span><span class="sxs-lookup"><span data-stu-id="5f82f-119">Char</span></span>           | <span data-ttu-id="5f82f-120">整数</span><span class="sxs-lookup"><span data-stu-id="5f82f-120">Integer</span></span>    | <span data-ttu-id="5f82f-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="5f82f-121">UTF-16</span></span>           |
| <span data-ttu-id="5f82f-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="5f82f-122">DateTime</span></span>       | <span data-ttu-id="5f82f-123">Real</span><span class="sxs-lookup"><span data-stu-id="5f82f-123">Real</span></span>       | <span data-ttu-id="5f82f-124">儒略历日值</span><span class="sxs-lookup"><span data-stu-id="5f82f-124">Julian day value</span></span> |
| <span data-ttu-id="5f82f-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="5f82f-125">DateTimeOffset</span></span> | <span data-ttu-id="5f82f-126">Real</span><span class="sxs-lookup"><span data-stu-id="5f82f-126">Real</span></span>       | <span data-ttu-id="5f82f-127">儒略历日值</span><span class="sxs-lookup"><span data-stu-id="5f82f-127">Julian day value</span></span> |
| <span data-ttu-id="5f82f-128">GUID</span><span class="sxs-lookup"><span data-stu-id="5f82f-128">Guid</span></span>           | <span data-ttu-id="5f82f-129">Blob</span><span class="sxs-lookup"><span data-stu-id="5f82f-129">Blob</span></span>       |                  |
| <span data-ttu-id="5f82f-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="5f82f-130">TimeSpan</span></span>       | <span data-ttu-id="5f82f-131">Real</span><span class="sxs-lookup"><span data-stu-id="5f82f-131">Real</span></span>       | <span data-ttu-id="5f82f-132">（天）</span><span class="sxs-lookup"><span data-stu-id="5f82f-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="5f82f-133">输出参数</span><span class="sxs-lookup"><span data-stu-id="5f82f-133">Output parameters</span></span>

<span data-ttu-id="5f82f-134">SQLite 不支持输出参数。</span><span class="sxs-lookup"><span data-stu-id="5f82f-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="5f82f-135">改为返回查询结果中的值。</span><span class="sxs-lookup"><span data-stu-id="5f82f-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f82f-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f82f-136">See also</span></span>

* [<span data-ttu-id="5f82f-137">数据类型</span><span class="sxs-lookup"><span data-stu-id="5f82f-137">Data types</span></span>](types.md)
