---
title: 聚合函数（用于实体框架的 SqlClient）
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 3dbd4c0a24a5fc41153ea16747325e824669b0e5
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700046"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="40f3b-102">聚合函数（用于实体框架的 SqlClient）</span><span class="sxs-lookup"><span data-stu-id="40f3b-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="40f3b-103">SQL Server .NET Framework 数据提供程序 (SqlClient) 提供聚合函数。</span><span class="sxs-lookup"><span data-stu-id="40f3b-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="40f3b-104">聚合函数对一组输入值执行计算并返回一个值。</span><span class="sxs-lookup"><span data-stu-id="40f3b-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="40f3b-105">这些函数位于 SqlServer 命名空间中，该命名空间在您使用 SqlClient 时可用。</span><span class="sxs-lookup"><span data-stu-id="40f3b-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="40f3b-106">提供程序的命名空间属性使实体框架可以确定此提供程序对特定构造（如类型和函数）使用哪个前缀。</span><span class="sxs-lookup"><span data-stu-id="40f3b-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="40f3b-107">下面是 SqlClient 聚合函数。</span><span class="sxs-lookup"><span data-stu-id="40f3b-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="40f3b-108">AVG （expression）</span><span class="sxs-lookup"><span data-stu-id="40f3b-108">AVG(expression)</span></span>

<span data-ttu-id="40f3b-109">返回集合中各值的平均值。</span><span class="sxs-lookup"><span data-stu-id="40f3b-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="40f3b-110">空值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="40f3b-110">Null values are ignored.</span></span>

<span data-ttu-id="40f3b-111">**参数**</span><span class="sxs-lookup"><span data-stu-id="40f3b-111">**Arguments**</span></span>

<span data-ttu-id="40f3b-112">@No__t-0、`Int64`、`Double` 和 @no__t。</span><span class="sxs-lookup"><span data-stu-id="40f3b-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="40f3b-113">**返回值**</span><span class="sxs-lookup"><span data-stu-id="40f3b-113">**Return Value**</span></span>

<span data-ttu-id="40f3b-114">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="40f3b-114">The type of `expression`.</span></span>

<span data-ttu-id="40f3b-115">**示例**</span><span class="sxs-lookup"><span data-stu-id="40f3b-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="40f3b-116">CHECKSUM_AGG （集合）</span><span class="sxs-lookup"><span data-stu-id="40f3b-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="40f3b-117">返回集合中各值的校验和。</span><span class="sxs-lookup"><span data-stu-id="40f3b-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="40f3b-118">空值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="40f3b-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="40f3b-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="40f3b-119">**Arguments**</span></span>
 
 <span data-ttu-id="40f3b-120">集合（`Int32`）。</span><span class="sxs-lookup"><span data-stu-id="40f3b-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="40f3b-121">**返回值**</span><span class="sxs-lookup"><span data-stu-id="40f3b-121">**Return Value**</span></span>
 
 <span data-ttu-id="40f3b-122">一个 `Int32`。</span><span class="sxs-lookup"><span data-stu-id="40f3b-122">An `Int32`.</span></span>
 
 <span data-ttu-id="40f3b-123">**示例**</span><span class="sxs-lookup"><span data-stu-id="40f3b-123">**Example**</span></span>
 
[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="40f3b-124">COUNT （expression）</span><span class="sxs-lookup"><span data-stu-id="40f3b-124">COUNT(expression)</span></span>

<span data-ttu-id="40f3b-125">以 `Int32` 形式返回集合中的项数。</span><span class="sxs-lookup"><span data-stu-id="40f3b-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="40f3b-126">**参数**</span><span class="sxs-lookup"><span data-stu-id="40f3b-126">**Arguments**</span></span>

<span data-ttu-id="40f3b-127">集合 @ no__t-0T >，其中 T 为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="40f3b-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="40f3b-128">`Guid` （在 SQL Server 2000 中未返回）</span><span class="sxs-lookup"><span data-stu-id="40f3b-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="40f3b-129">**返回值**</span><span class="sxs-lookup"><span data-stu-id="40f3b-129">**Return Value**</span></span>

<span data-ttu-id="40f3b-130">一个 `Int32`。</span><span class="sxs-lookup"><span data-stu-id="40f3b-130">An `Int32`.</span></span>

<span data-ttu-id="40f3b-131">**示例**</span><span class="sxs-lookup"><span data-stu-id="40f3b-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]
 
## <a name="count_bigexpression"></a><span data-ttu-id="40f3b-132">COUNT_BIG （expression）</span><span class="sxs-lookup"><span data-stu-id="40f3b-132">COUNT_BIG(expression)</span></span>
 
<span data-ttu-id="40f3b-133">以 `bigint` 形式返回集合中的项数。</span><span class="sxs-lookup"><span data-stu-id="40f3b-133">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="40f3b-134">**参数**</span><span class="sxs-lookup"><span data-stu-id="40f3b-134">**Arguments**</span></span>
 
 <span data-ttu-id="40f3b-135">集合（T），其中 T 为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="40f3b-135">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="40f3b-136">`Guid` （在 SQL Server 2000 中未返回）</span><span class="sxs-lookup"><span data-stu-id="40f3b-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="40f3b-137">**返回值**</span><span class="sxs-lookup"><span data-stu-id="40f3b-137">**Return Value**</span></span>

<span data-ttu-id="40f3b-138">一个 `Int64`。</span><span class="sxs-lookup"><span data-stu-id="40f3b-138">An `Int64`.</span></span>

<span data-ttu-id="40f3b-139">**示例**</span><span class="sxs-lookup"><span data-stu-id="40f3b-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="40f3b-140">MAX （expression）</span><span class="sxs-lookup"><span data-stu-id="40f3b-140">MAX(expression)</span></span>

<span data-ttu-id="40f3b-141">返回集合中的最大值。</span><span class="sxs-lookup"><span data-stu-id="40f3b-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="40f3b-142">**参数**</span><span class="sxs-lookup"><span data-stu-id="40f3b-142">**Arguments**</span></span>

<span data-ttu-id="40f3b-143">集合（T），其中 T 为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="40f3b-143">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="40f3b-144">**返回值**</span><span class="sxs-lookup"><span data-stu-id="40f3b-144">**Return Value**</span></span>

<span data-ttu-id="40f3b-145">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="40f3b-145">The type of `expression`.</span></span>

<span data-ttu-id="40f3b-146">**示例**</span><span class="sxs-lookup"><span data-stu-id="40f3b-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="40f3b-147">MIN （expression）</span><span class="sxs-lookup"><span data-stu-id="40f3b-147">MIN(expression)</span></span>

<span data-ttu-id="40f3b-148">返回集合中的最小值。</span><span class="sxs-lookup"><span data-stu-id="40f3b-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="40f3b-149">**参数**</span><span class="sxs-lookup"><span data-stu-id="40f3b-149">**Arguments**</span></span>

<span data-ttu-id="40f3b-150">集合（T），其中 T 为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="40f3b-150">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="40f3b-151">**返回值**</span><span class="sxs-lookup"><span data-stu-id="40f3b-151">**Return Value**</span></span>

<span data-ttu-id="40f3b-152">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="40f3b-152">The type of `expression`.</span></span>

<span data-ttu-id="40f3b-153">**示例**</span><span class="sxs-lookup"><span data-stu-id="40f3b-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="40f3b-154">STDEV （expression）</span><span class="sxs-lookup"><span data-stu-id="40f3b-154">STDEV(expression)</span></span>

<span data-ttu-id="40f3b-155">返回指定表达式中所有值的统计标准偏差。</span><span class="sxs-lookup"><span data-stu-id="40f3b-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="40f3b-156">**参数**</span><span class="sxs-lookup"><span data-stu-id="40f3b-156">**Arguments**</span></span>

<span data-ttu-id="40f3b-157">集合（`Double`）。</span><span class="sxs-lookup"><span data-stu-id="40f3b-157">A Collection(`Double`).</span></span>

<span data-ttu-id="40f3b-158">**返回值**</span><span class="sxs-lookup"><span data-stu-id="40f3b-158">**Return Value**</span></span>

<span data-ttu-id="40f3b-159">`Double`。</span><span class="sxs-lookup"><span data-stu-id="40f3b-159">A `Double`.</span></span>

<span data-ttu-id="40f3b-160">**示例**</span><span class="sxs-lookup"><span data-stu-id="40f3b-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="40f3b-161">STDEVP （expression）</span><span class="sxs-lookup"><span data-stu-id="40f3b-161">STDEVP(expression)</span></span>

<span data-ttu-id="40f3b-162">返回指定表达式中所有值的总体标准偏差。</span><span class="sxs-lookup"><span data-stu-id="40f3b-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="40f3b-163">**参数**</span><span class="sxs-lookup"><span data-stu-id="40f3b-163">**Arguments**</span></span>

<span data-ttu-id="40f3b-164">集合（`Double`）。</span><span class="sxs-lookup"><span data-stu-id="40f3b-164">A Collection(`Double`).</span></span>

<span data-ttu-id="40f3b-165">**返回值**</span><span class="sxs-lookup"><span data-stu-id="40f3b-165">**Return Value**</span></span>

<span data-ttu-id="40f3b-166">`Double`。</span><span class="sxs-lookup"><span data-stu-id="40f3b-166">A `Double`.</span></span>

<span data-ttu-id="40f3b-167">**示例**</span><span class="sxs-lookup"><span data-stu-id="40f3b-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="40f3b-168">SUM （expression）</span><span class="sxs-lookup"><span data-stu-id="40f3b-168">SUM(expression)</span></span>

<span data-ttu-id="40f3b-169">返回集合中所有值的总和。</span><span class="sxs-lookup"><span data-stu-id="40f3b-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="40f3b-170">**参数**</span><span class="sxs-lookup"><span data-stu-id="40f3b-170">**Arguments**</span></span>

<span data-ttu-id="40f3b-171">集合（T），其中 T 为以下类型之一： `Int32`，`Int64`，`Double`，@no__t 为3。</span><span class="sxs-lookup"><span data-stu-id="40f3b-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="40f3b-172">**返回值**</span><span class="sxs-lookup"><span data-stu-id="40f3b-172">**Return Value**</span></span>

<span data-ttu-id="40f3b-173">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="40f3b-173">The type of `expression`.</span></span>

<span data-ttu-id="40f3b-174">**示例**</span><span class="sxs-lookup"><span data-stu-id="40f3b-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="40f3b-175">VAR （expression）</span><span class="sxs-lookup"><span data-stu-id="40f3b-175">VAR(expression)</span></span>

<span data-ttu-id="40f3b-176">返回指定表达式中所有值的方差。</span><span class="sxs-lookup"><span data-stu-id="40f3b-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="40f3b-177">**参数**</span><span class="sxs-lookup"><span data-stu-id="40f3b-177">**Arguments**</span></span>

<span data-ttu-id="40f3b-178">集合（`Double`）。</span><span class="sxs-lookup"><span data-stu-id="40f3b-178">A Collection(`Double`).</span></span>

<span data-ttu-id="40f3b-179">**返回值**</span><span class="sxs-lookup"><span data-stu-id="40f3b-179">**Return Value**</span></span>

<span data-ttu-id="40f3b-180">`Double`。</span><span class="sxs-lookup"><span data-stu-id="40f3b-180">A `Double`.</span></span>

<span data-ttu-id="40f3b-181">**示例**</span><span class="sxs-lookup"><span data-stu-id="40f3b-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="40f3b-182">VARP （expression）</span><span class="sxs-lookup"><span data-stu-id="40f3b-182">VARP(expression)</span></span>

<span data-ttu-id="40f3b-183">返回指定表达式中所有值的总体方差。</span><span class="sxs-lookup"><span data-stu-id="40f3b-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="40f3b-184">**参数**</span><span class="sxs-lookup"><span data-stu-id="40f3b-184">**Arguments**</span></span>

<span data-ttu-id="40f3b-185">集合（`Double`）。</span><span class="sxs-lookup"><span data-stu-id="40f3b-185">A Collection(`Double`).</span></span>

<span data-ttu-id="40f3b-186">**返回值**</span><span class="sxs-lookup"><span data-stu-id="40f3b-186">**Return Value**</span></span>

<span data-ttu-id="40f3b-187">`Double`。</span><span class="sxs-lookup"><span data-stu-id="40f3b-187">A `Double`.</span></span>

<span data-ttu-id="40f3b-188">**示例**</span><span class="sxs-lookup"><span data-stu-id="40f3b-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="40f3b-189">请参阅</span><span class="sxs-lookup"><span data-stu-id="40f3b-189">See also</span></span>

- [<span data-ttu-id="40f3b-190">聚合函数（Transact-sql）</span><span class="sxs-lookup"><span data-stu-id="40f3b-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="40f3b-191">实体 SQL 语言</span><span class="sxs-lookup"><span data-stu-id="40f3b-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="40f3b-192">聚合 Canonical 函数</span><span class="sxs-lookup"><span data-stu-id="40f3b-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
