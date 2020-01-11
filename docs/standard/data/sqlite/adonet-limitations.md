---
title: ADO.NET 限制
ms.date: 12/13/2019
description: 描述你可能会遇到的一些 ADO.NET 限制。
ms.openlocfilehash: 8664b73071fc859ed30080f549b05e7d6ed020f4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901252"
---
# <a name="adonet-limitations"></a><span data-ttu-id="e87af-103">ADO.NET 限制</span><span class="sxs-lookup"><span data-stu-id="e87af-103">ADO.NET limitations</span></span>

<span data-ttu-id="e87af-104">ADO.NET 提供许多抽象抽象的实现，但存在一些限制。</span><span class="sxs-lookup"><span data-stu-id="e87af-104">Microsoft.Data.Sqlite provides implementations of many of the ADO.NET abstractions, but there are some limitations.</span></span>

## <a name="database-schema-information"></a><span data-ttu-id="e87af-105">数据库架构信息</span><span class="sxs-lookup"><span data-stu-id="e87af-105">Database schema information</span></span>

<span data-ttu-id="e87af-106">使用 <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> 方法可获取有关查询结果的元数据。</span><span class="sxs-lookup"><span data-stu-id="e87af-106">Metadata about query results is available using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method.</span></span>

<span data-ttu-id="e87af-107">未实现 `DbConnection.GetSchema()`。</span><span class="sxs-lookup"><span data-stu-id="e87af-107">`DbConnection.GetSchema()` isn't implemented.</span></span> <span data-ttu-id="e87af-108">此 API 未定义完善，因此，我们建议使用标准 SQLite Api （如[sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)表和[table_info](https://www.sqlite.org/pragma.html#pragma_table_info)杂注）直接检索数据库元数据。</span><span class="sxs-lookup"><span data-stu-id="e87af-108">This API isn't well-defined, so we recommend retrieving database metadata directly using standard SQLite APIs like the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and the [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) PRAGMA.</span></span>

<span data-ttu-id="e87af-109">有关详细信息，请参阅[元数据](metadata.md)。</span><span class="sxs-lookup"><span data-stu-id="e87af-109">For more information, see [Metadata](metadata.md).</span></span>

## <a name="systemtransactions"></a><span data-ttu-id="e87af-110">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="e87af-110">System.Transactions</span></span>

<span data-ttu-id="e87af-111">Microsoft 尚不支持 System.object。</span><span class="sxs-lookup"><span data-stu-id="e87af-111">Microsoft.Data.Sqlite doesn't yet support System.Transactions.</span></span> <span data-ttu-id="e87af-112">改为使用 ADO.NET 事务。</span><span class="sxs-lookup"><span data-stu-id="e87af-112">Use ADO.NET transactions instead.</span></span> <span data-ttu-id="e87af-113">有关详细信息，请参阅[事务](transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="e87af-113">For more information, see [Transactions](transactions.md).</span></span>

<span data-ttu-id="e87af-114">提供有关在问题[#13825](https://github.com/dotnet/efcore/issues/13825)上缺少对 system.object 的支持的反馈。</span><span class="sxs-lookup"><span data-stu-id="e87af-114">Provide feedback about the lack of support for System.Transactions on issue [#13825](https://github.com/dotnet/efcore/issues/13825).</span></span>

## <a name="data-adapters"></a><span data-ttu-id="e87af-115">数据适配器</span><span class="sxs-lookup"><span data-stu-id="e87af-115">Data adapters</span></span>

<span data-ttu-id="e87af-116">`DbDataAdapter` 尚不是由 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="e87af-116">`DbDataAdapter` isn't yet implemented by Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="e87af-117">这意味着，只能使用 ADO.NET `DataSet` 和 `DataTable` 来加载数据，而不能对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="e87af-117">This means you can only use ADO.NET `DataSet` and `DataTable` to load data and not update it.</span></span>

<span data-ttu-id="e87af-118">使用问题[#13838](https://github.com/dotnet/efcore/issues/13838)提供有关实现 `DbDataAdapter`的反馈。</span><span class="sxs-lookup"><span data-stu-id="e87af-118">Use issue [#13838](https://github.com/dotnet/efcore/issues/13838) to provide feedback about implementing `DbDataAdapter`.</span></span>

## <a name="output-parameters"></a><span data-ttu-id="e87af-119">输出参数</span><span class="sxs-lookup"><span data-stu-id="e87af-119">Output parameters</span></span>

<span data-ttu-id="e87af-120">SQLite 不支持输出参数。</span><span class="sxs-lookup"><span data-stu-id="e87af-120">SQLite doesn't support output parameters.</span></span>

## <a name="positional-parameters"></a><span data-ttu-id="e87af-121">位置参数</span><span class="sxs-lookup"><span data-stu-id="e87af-121">Positional parameters</span></span>

<span data-ttu-id="e87af-122">Node.js 仅支持命名[参数](parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="e87af-122">Microsoft.Data.Sqlite only supports named [parameters](parameters.md).</span></span> <span data-ttu-id="e87af-123">位置参数不受支持。</span><span class="sxs-lookup"><span data-stu-id="e87af-123">Positional parameters aren't supported.</span></span>

## <a name="stored-procedures"></a><span data-ttu-id="e87af-124">存储过程</span><span class="sxs-lookup"><span data-stu-id="e87af-124">Stored procedures</span></span>

<span data-ttu-id="e87af-125">SQLite 不支持存储过程。</span><span class="sxs-lookup"><span data-stu-id="e87af-125">SQLite doesn't support stored procedures.</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="e87af-126">隔离级别</span><span class="sxs-lookup"><span data-stu-id="e87af-126">Isolation levels</span></span>

<span data-ttu-id="e87af-127">SQLite 事务不支持 `Chaos` 和 `Snapshot` 隔离级别。</span><span class="sxs-lookup"><span data-stu-id="e87af-127">The `Chaos` and `Snapshot` isolation levels aren't supported in SQLite transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="e87af-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e87af-128">See also</span></span>

* [<span data-ttu-id="e87af-129">异步限制</span><span class="sxs-lookup"><span data-stu-id="e87af-129">Async limitations</span></span>](async.md)
* [<span data-ttu-id="e87af-130">数据类型</span><span class="sxs-lookup"><span data-stu-id="e87af-130">Data types</span></span>](types.md)
* [<span data-ttu-id="e87af-131">事务</span><span class="sxs-lookup"><span data-stu-id="e87af-131">Transactions</span></span>](transactions.md)
