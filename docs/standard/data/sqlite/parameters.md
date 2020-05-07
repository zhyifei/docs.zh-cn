---
title: 参数
ms.date: 12/13/2019
description: 了解如何使用 SQL 参数。
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401201"
---
# <a name="parameters"></a><span data-ttu-id="d1d79-103">参数</span><span class="sxs-lookup"><span data-stu-id="d1d79-103">Parameters</span></span>

<span data-ttu-id="d1d79-104">可以使用参数来防范 SQL 注入攻击。</span><span class="sxs-lookup"><span data-stu-id="d1d79-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="d1d79-105">与其将用户输入与 SQL 语句连接起来，不如使用参数来确保输入只被视为文本值，而不会执行。</span><span class="sxs-lookup"><span data-stu-id="d1d79-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="d1d79-106">在 SQLite 中，通常允许在 SQL 语句中允许文本的任何位置使用参数。</span><span class="sxs-lookup"><span data-stu-id="d1d79-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="d1d79-107">参数可以使用 `:`、`@` 或 `$` 作为前缀。</span><span class="sxs-lookup"><span data-stu-id="d1d79-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="d1d79-108">若要详细了解如何将 .NET 值映射到 SQLite 值，请参阅[数据类型](types.md)。</span><span class="sxs-lookup"><span data-stu-id="d1d79-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="d1d79-109">截断</span><span class="sxs-lookup"><span data-stu-id="d1d79-109">Truncation</span></span>

<span data-ttu-id="d1d79-110">使用 <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> 属性可截断 TEXT 和 BLOB 值。</span><span class="sxs-lookup"><span data-stu-id="d1d79-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="d1d79-111">替代类型</span><span class="sxs-lookup"><span data-stu-id="d1d79-111">Alternative types</span></span>

<span data-ttu-id="d1d79-112">有时，你可能想要使用替代的 SQLite 类型。</span><span class="sxs-lookup"><span data-stu-id="d1d79-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="d1d79-113">通过设置 <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> 属性可实现此目的。</span><span class="sxs-lookup"><span data-stu-id="d1d79-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="d1d79-114">可以使用以下替代类型映射。</span><span class="sxs-lookup"><span data-stu-id="d1d79-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="d1d79-115">有关默认映射，请参阅[数据类型](types.md)。</span><span class="sxs-lookup"><span data-stu-id="d1d79-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="d1d79-116">“值”</span><span class="sxs-lookup"><span data-stu-id="d1d79-116">Value</span></span>          | <span data-ttu-id="d1d79-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="d1d79-117">SqliteType</span></span> | <span data-ttu-id="d1d79-118">备注</span><span class="sxs-lookup"><span data-stu-id="d1d79-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="d1d79-119">Char</span><span class="sxs-lookup"><span data-stu-id="d1d79-119">Char</span></span>           | <span data-ttu-id="d1d79-120">整数</span><span class="sxs-lookup"><span data-stu-id="d1d79-120">Integer</span></span>    | <span data-ttu-id="d1d79-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="d1d79-121">UTF-16</span></span>           |
| <span data-ttu-id="d1d79-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="d1d79-122">DateTime</span></span>       | <span data-ttu-id="d1d79-123">Real</span><span class="sxs-lookup"><span data-stu-id="d1d79-123">Real</span></span>       | <span data-ttu-id="d1d79-124">儒略日值</span><span class="sxs-lookup"><span data-stu-id="d1d79-124">Julian day value</span></span> |
| <span data-ttu-id="d1d79-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d1d79-125">DateTimeOffset</span></span> | <span data-ttu-id="d1d79-126">Real</span><span class="sxs-lookup"><span data-stu-id="d1d79-126">Real</span></span>       | <span data-ttu-id="d1d79-127">儒略日值</span><span class="sxs-lookup"><span data-stu-id="d1d79-127">Julian day value</span></span> |
| <span data-ttu-id="d1d79-128">GUID</span><span class="sxs-lookup"><span data-stu-id="d1d79-128">Guid</span></span>           | <span data-ttu-id="d1d79-129">Blob</span><span class="sxs-lookup"><span data-stu-id="d1d79-129">Blob</span></span>       |                  |
| <span data-ttu-id="d1d79-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="d1d79-130">TimeSpan</span></span>       | <span data-ttu-id="d1d79-131">Real</span><span class="sxs-lookup"><span data-stu-id="d1d79-131">Real</span></span>       | <span data-ttu-id="d1d79-132">以天为单位</span><span class="sxs-lookup"><span data-stu-id="d1d79-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="d1d79-133">输出参数</span><span class="sxs-lookup"><span data-stu-id="d1d79-133">Output parameters</span></span>

<span data-ttu-id="d1d79-134">SQLite 不支持输出参数。</span><span class="sxs-lookup"><span data-stu-id="d1d79-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="d1d79-135">改为返回查询结果中的值。</span><span class="sxs-lookup"><span data-stu-id="d1d79-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1d79-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1d79-136">See also</span></span>

* [<span data-ttu-id="d1d79-137">数据类型</span><span class="sxs-lookup"><span data-stu-id="d1d79-137">Data types</span></span>](types.md)
