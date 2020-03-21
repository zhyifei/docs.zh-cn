---
title: 聚合函数（用于实体框架的 SqlClient）
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 1fad25f2229b4fa810cf82a96dcb8c50a9de3070
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150644"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="8a85a-102">聚合函数（用于实体框架的 SqlClient）</span><span class="sxs-lookup"><span data-stu-id="8a85a-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="8a85a-103">SQL Server .NET Framework 数据提供程序 (SqlClient) 提供聚合函数。</span><span class="sxs-lookup"><span data-stu-id="8a85a-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="8a85a-104">聚合函数对一组输入值执行计算并返回一个值。</span><span class="sxs-lookup"><span data-stu-id="8a85a-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="8a85a-105">这些函数位于 SqlServer 命名空间中，该命名空间在您使用 SqlClient 时可用。</span><span class="sxs-lookup"><span data-stu-id="8a85a-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="8a85a-106">提供程序的命名空间属性使实体框架可以确定此提供程序对特定构造（如类型和函数）使用哪个前缀。</span><span class="sxs-lookup"><span data-stu-id="8a85a-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="8a85a-107">以下是 SqlClient 聚合函数。</span><span class="sxs-lookup"><span data-stu-id="8a85a-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="8a85a-108">AVG（表达式）</span><span class="sxs-lookup"><span data-stu-id="8a85a-108">AVG(expression)</span></span>

<span data-ttu-id="8a85a-109">返回集合中各值的平均值。</span><span class="sxs-lookup"><span data-stu-id="8a85a-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="8a85a-110">Null 值会被忽略。</span><span class="sxs-lookup"><span data-stu-id="8a85a-110">Null values are ignored.</span></span>

<span data-ttu-id="8a85a-111">**参数**</span><span class="sxs-lookup"><span data-stu-id="8a85a-111">**Arguments**</span></span>

<span data-ttu-id="8a85a-112">`Int32`、、`Int64``Double`和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="8a85a-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="8a85a-113">**返回值**</span><span class="sxs-lookup"><span data-stu-id="8a85a-113">**Return Value**</span></span>

<span data-ttu-id="8a85a-114">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="8a85a-114">The type of `expression`.</span></span>

<span data-ttu-id="8a85a-115">**示例**</span><span class="sxs-lookup"><span data-stu-id="8a85a-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="8a85a-116">CHECKSUM_AGG（收藏）</span><span class="sxs-lookup"><span data-stu-id="8a85a-116">CHECKSUM_AGG(collection)</span></span>

 <span data-ttu-id="8a85a-117">返回集合中各值的校验和。</span><span class="sxs-lookup"><span data-stu-id="8a85a-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="8a85a-118">Null 值会被忽略。</span><span class="sxs-lookup"><span data-stu-id="8a85a-118">Null values are ignored.</span></span>

 <span data-ttu-id="8a85a-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="8a85a-119">**Arguments**</span></span>

 <span data-ttu-id="8a85a-120">集合（`Int32`</span><span class="sxs-lookup"><span data-stu-id="8a85a-120">A Collection(`Int32`).</span></span>

 <span data-ttu-id="8a85a-121">**返回值**</span><span class="sxs-lookup"><span data-stu-id="8a85a-121">**Return Value**</span></span>

 <span data-ttu-id="8a85a-122">一个`Int32`。</span><span class="sxs-lookup"><span data-stu-id="8a85a-122">An `Int32`.</span></span>

 <span data-ttu-id="8a85a-123">**示例**</span><span class="sxs-lookup"><span data-stu-id="8a85a-123">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a><span data-ttu-id="8a85a-124">COUNT（表达式）</span><span class="sxs-lookup"><span data-stu-id="8a85a-124">COUNT(expression)</span></span>

<span data-ttu-id="8a85a-125">以 `Int32` 形式返回集合中的项数。</span><span class="sxs-lookup"><span data-stu-id="8a85a-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="8a85a-126">**参数**</span><span class="sxs-lookup"><span data-stu-id="8a85a-126">**Arguments**</span></span>

<span data-ttu-id="8a85a-127">集合\<T>，其中 T 是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="8a85a-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="8a85a-128">`Guid`（未在 SQL Server 2000 中返回）</span><span class="sxs-lookup"><span data-stu-id="8a85a-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="8a85a-129">**返回值**</span><span class="sxs-lookup"><span data-stu-id="8a85a-129">**Return Value**</span></span>

<span data-ttu-id="8a85a-130">一个`Int32`。</span><span class="sxs-lookup"><span data-stu-id="8a85a-130">An `Int32`.</span></span>

<span data-ttu-id="8a85a-131">**示例**</span><span class="sxs-lookup"><span data-stu-id="8a85a-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a><span data-ttu-id="8a85a-132">COUNT_BIG（表达式）</span><span class="sxs-lookup"><span data-stu-id="8a85a-132">COUNT_BIG(expression)</span></span>

<span data-ttu-id="8a85a-133">以 `bigint` 形式返回集合中的项数。</span><span class="sxs-lookup"><span data-stu-id="8a85a-133">Returns the number of items in a collection as a `bigint`.</span></span>

 <span data-ttu-id="8a85a-134">**参数**</span><span class="sxs-lookup"><span data-stu-id="8a85a-134">**Arguments**</span></span>

 <span data-ttu-id="8a85a-135">集合 （T），其中 T 是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="8a85a-135">A Collection(T), where T is one of the following types:</span></span>

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="8a85a-136">`Guid`（未在 SQL Server 2000 中返回）</span><span class="sxs-lookup"><span data-stu-id="8a85a-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="8a85a-137">**返回值**</span><span class="sxs-lookup"><span data-stu-id="8a85a-137">**Return Value**</span></span>

<span data-ttu-id="8a85a-138">一个`Int64`。</span><span class="sxs-lookup"><span data-stu-id="8a85a-138">An `Int64`.</span></span>

<span data-ttu-id="8a85a-139">**示例**</span><span class="sxs-lookup"><span data-stu-id="8a85a-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="8a85a-140">最大（表达式）</span><span class="sxs-lookup"><span data-stu-id="8a85a-140">MAX(expression)</span></span>

<span data-ttu-id="8a85a-141">返回集合中的最大值。</span><span class="sxs-lookup"><span data-stu-id="8a85a-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="8a85a-142">**参数**</span><span class="sxs-lookup"><span data-stu-id="8a85a-142">**Arguments**</span></span>

<span data-ttu-id="8a85a-143">集合 （T），其中 T 是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="8a85a-143">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="8a85a-144">**返回值**</span><span class="sxs-lookup"><span data-stu-id="8a85a-144">**Return Value**</span></span>

<span data-ttu-id="8a85a-145">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="8a85a-145">The type of `expression`.</span></span>

<span data-ttu-id="8a85a-146">**示例**</span><span class="sxs-lookup"><span data-stu-id="8a85a-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="8a85a-147">MIN（表达式）</span><span class="sxs-lookup"><span data-stu-id="8a85a-147">MIN(expression)</span></span>

<span data-ttu-id="8a85a-148">返回集合中的最小值。</span><span class="sxs-lookup"><span data-stu-id="8a85a-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="8a85a-149">**参数**</span><span class="sxs-lookup"><span data-stu-id="8a85a-149">**Arguments**</span></span>

<span data-ttu-id="8a85a-150">集合 （T），其中 T 是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="8a85a-150">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="8a85a-151">**返回值**</span><span class="sxs-lookup"><span data-stu-id="8a85a-151">**Return Value**</span></span>

<span data-ttu-id="8a85a-152">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="8a85a-152">The type of `expression`.</span></span>

<span data-ttu-id="8a85a-153">**示例**</span><span class="sxs-lookup"><span data-stu-id="8a85a-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="8a85a-154">STDEV（表达式）</span><span class="sxs-lookup"><span data-stu-id="8a85a-154">STDEV(expression)</span></span>

<span data-ttu-id="8a85a-155">返回指定表达式中所有值的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="8a85a-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="8a85a-156">**参数**</span><span class="sxs-lookup"><span data-stu-id="8a85a-156">**Arguments**</span></span>

<span data-ttu-id="8a85a-157">集合（`Double`</span><span class="sxs-lookup"><span data-stu-id="8a85a-157">A Collection(`Double`).</span></span>

<span data-ttu-id="8a85a-158">**返回值**</span><span class="sxs-lookup"><span data-stu-id="8a85a-158">**Return Value**</span></span>

<span data-ttu-id="8a85a-159">一个 `Double`。</span><span class="sxs-lookup"><span data-stu-id="8a85a-159">A `Double`.</span></span>

<span data-ttu-id="8a85a-160">**示例**</span><span class="sxs-lookup"><span data-stu-id="8a85a-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="8a85a-161">STDEVP（表达式）</span><span class="sxs-lookup"><span data-stu-id="8a85a-161">STDEVP(expression)</span></span>

<span data-ttu-id="8a85a-162">返回指定表达式中所有值的总体标准偏差。</span><span class="sxs-lookup"><span data-stu-id="8a85a-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="8a85a-163">**参数**</span><span class="sxs-lookup"><span data-stu-id="8a85a-163">**Arguments**</span></span>

<span data-ttu-id="8a85a-164">集合（`Double`</span><span class="sxs-lookup"><span data-stu-id="8a85a-164">A Collection(`Double`).</span></span>

<span data-ttu-id="8a85a-165">**返回值**</span><span class="sxs-lookup"><span data-stu-id="8a85a-165">**Return Value**</span></span>

<span data-ttu-id="8a85a-166">一个 `Double`。</span><span class="sxs-lookup"><span data-stu-id="8a85a-166">A `Double`.</span></span>

<span data-ttu-id="8a85a-167">**示例**</span><span class="sxs-lookup"><span data-stu-id="8a85a-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="8a85a-168">SUM（表达式）</span><span class="sxs-lookup"><span data-stu-id="8a85a-168">SUM(expression)</span></span>

<span data-ttu-id="8a85a-169">返回集合中所有值的总和。</span><span class="sxs-lookup"><span data-stu-id="8a85a-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="8a85a-170">**参数**</span><span class="sxs-lookup"><span data-stu-id="8a85a-170">**Arguments**</span></span>

<span data-ttu-id="8a85a-171">其中 T 是以下类型之一的集合`Int32`（T）： `Int64`、 `Double`、 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="8a85a-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="8a85a-172">**返回值**</span><span class="sxs-lookup"><span data-stu-id="8a85a-172">**Return Value**</span></span>

<span data-ttu-id="8a85a-173">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="8a85a-173">The type of `expression`.</span></span>

<span data-ttu-id="8a85a-174">**示例**</span><span class="sxs-lookup"><span data-stu-id="8a85a-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="8a85a-175">VAR（表达式）</span><span class="sxs-lookup"><span data-stu-id="8a85a-175">VAR(expression)</span></span>

<span data-ttu-id="8a85a-176">返回指定表达式中所有值的方差。</span><span class="sxs-lookup"><span data-stu-id="8a85a-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="8a85a-177">**参数**</span><span class="sxs-lookup"><span data-stu-id="8a85a-177">**Arguments**</span></span>

<span data-ttu-id="8a85a-178">集合（`Double`</span><span class="sxs-lookup"><span data-stu-id="8a85a-178">A Collection(`Double`).</span></span>

<span data-ttu-id="8a85a-179">**返回值**</span><span class="sxs-lookup"><span data-stu-id="8a85a-179">**Return Value**</span></span>

<span data-ttu-id="8a85a-180">一个 `Double`。</span><span class="sxs-lookup"><span data-stu-id="8a85a-180">A `Double`.</span></span>

<span data-ttu-id="8a85a-181">**示例**</span><span class="sxs-lookup"><span data-stu-id="8a85a-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="8a85a-182">VARP（表达式）</span><span class="sxs-lookup"><span data-stu-id="8a85a-182">VARP(expression)</span></span>

<span data-ttu-id="8a85a-183">返回指定表达式中所有值的总体统计方差。</span><span class="sxs-lookup"><span data-stu-id="8a85a-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="8a85a-184">**参数**</span><span class="sxs-lookup"><span data-stu-id="8a85a-184">**Arguments**</span></span>

<span data-ttu-id="8a85a-185">集合（`Double`</span><span class="sxs-lookup"><span data-stu-id="8a85a-185">A Collection(`Double`).</span></span>

<span data-ttu-id="8a85a-186">**返回值**</span><span class="sxs-lookup"><span data-stu-id="8a85a-186">**Return Value**</span></span>

<span data-ttu-id="8a85a-187">一个 `Double`。</span><span class="sxs-lookup"><span data-stu-id="8a85a-187">A `Double`.</span></span>

<span data-ttu-id="8a85a-188">**示例**</span><span class="sxs-lookup"><span data-stu-id="8a85a-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a><span data-ttu-id="8a85a-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a85a-189">See also</span></span>

- [<span data-ttu-id="8a85a-190">聚合函数 (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8a85a-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="8a85a-191">Entity SQL 语言</span><span class="sxs-lookup"><span data-stu-id="8a85a-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="8a85a-192">聚合规范函数</span><span class="sxs-lookup"><span data-stu-id="8a85a-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
