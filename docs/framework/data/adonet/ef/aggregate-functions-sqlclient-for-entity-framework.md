---
title: 聚合函数（用于实体框架的 SqlClient）
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 55a10b82ffc189f5cf4118cb225a96963226256e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724182"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="2ed5c-102">聚合函数（用于实体框架的 SqlClient）</span><span class="sxs-lookup"><span data-stu-id="2ed5c-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="2ed5c-103">SQL Server .NET Framework 数据提供程序 (SqlClient) 提供聚合函数。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="2ed5c-104">聚合函数对一组输入值执行计算并返回一个值。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="2ed5c-105">这些函数位于 SqlServer 命名空间中，该命名空间在您使用 SqlClient 时可用。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="2ed5c-106">提供程序的命名空间属性使实体框架可以确定此提供程序对特定构造（如类型和函数）使用哪个前缀。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="2ed5c-107">以下是 SqlClient 聚合函数。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="2ed5c-108">AVG(expression)</span><span class="sxs-lookup"><span data-stu-id="2ed5c-108">AVG(expression)</span></span>

<span data-ttu-id="2ed5c-109">返回集合中各值的平均值。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="2ed5c-110">空值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-110">Null values are ignored.</span></span>

<span data-ttu-id="2ed5c-111">**参数**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-111">**Arguments**</span></span>

<span data-ttu-id="2ed5c-112">`Int32`， `Int64`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="2ed5c-113">**返回值**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-113">**Return Value**</span></span>

<span data-ttu-id="2ed5c-114">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-114">The type of `expression`.</span></span>

<span data-ttu-id="2ed5c-115">**示例**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-115">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksumaggcollection"></a><span data-ttu-id="2ed5c-116">CHECKSUM_AGG(collection)</span><span class="sxs-lookup"><span data-stu-id="2ed5c-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="2ed5c-117">返回集合中各值的校验和。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="2ed5c-118">空值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="2ed5c-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-119">**Arguments**</span></span>
 
 <span data-ttu-id="2ed5c-120">集合 (`Int32`)。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="2ed5c-121">**返回值**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-121">**Return Value**</span></span>
 
 <span data-ttu-id="2ed5c-122">一个 `Int32`。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-122">An `Int32`.</span></span>
 
 <span data-ttu-id="2ed5c-123">**示例**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-123">**Example**</span></span>
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="2ed5c-124">COUNT(expression)</span><span class="sxs-lookup"><span data-stu-id="2ed5c-124">COUNT(expression)</span></span>

<span data-ttu-id="2ed5c-125">以 `Int32` 形式返回集合中的项数。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="2ed5c-126">**参数**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-126">**Arguments**</span></span>

<span data-ttu-id="2ed5c-127">集合\<T >，其中 T 为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="2ed5c-128">`Guid` （在 SQL Server 2000 中不返回）</span><span class="sxs-lookup"><span data-stu-id="2ed5c-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="2ed5c-129">**返回值**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-129">**Return Value**</span></span>

<span data-ttu-id="2ed5c-130">一个 `Int32`。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-130">An `Int32`.</span></span>

<span data-ttu-id="2ed5c-131">**示例**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-131">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
<span data-ttu-id="2ed5c-132">[！ 代码 sql[DP EntityServices 概念 #SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span><span class="sxs-lookup"><span data-stu-id="2ed5c-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span></span>
 
## <a name="countbigexpression"></a><span data-ttu-id="2ed5c-133">COUNT_BIG(expression)</span><span class="sxs-lookup"><span data-stu-id="2ed5c-133">COUNT_BIG(expression)</span></span>
 
 <span data-ttu-id="2ed5c-134">以 `bigint` 形式返回集合中的项数。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-134">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="2ed5c-135">**参数**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-135">**Arguments**</span></span>
 
 <span data-ttu-id="2ed5c-136">Collection(T)，其中 T 为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-136">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="2ed5c-137">`Guid` （在 SQL Server 2000 中不返回）</span><span class="sxs-lookup"><span data-stu-id="2ed5c-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="2ed5c-138">**返回值**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-138">**Return Value**</span></span>

<span data-ttu-id="2ed5c-139">一个 `Int64`。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-139">An `Int64`.</span></span>

<span data-ttu-id="2ed5c-140">**示例**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-140">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="2ed5c-141">MAX(expression)</span><span class="sxs-lookup"><span data-stu-id="2ed5c-141">MAX(expression)</span></span>

<span data-ttu-id="2ed5c-142">返回集合中的最大值。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="2ed5c-143">**参数**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-143">**Arguments**</span></span>

<span data-ttu-id="2ed5c-144">Collection(T)，其中 T 为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-144">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="2ed5c-145">**返回值**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-145">**Return Value**</span></span>

<span data-ttu-id="2ed5c-146">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-146">The type of `expression`.</span></span>

<span data-ttu-id="2ed5c-147">**示例**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-147">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="2ed5c-148">MIN(expression)</span><span class="sxs-lookup"><span data-stu-id="2ed5c-148">MIN(expression)</span></span>

<span data-ttu-id="2ed5c-149">返回集合中的最小值。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="2ed5c-150">**参数**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-150">**Arguments**</span></span>

<span data-ttu-id="2ed5c-151">Collection(T)，其中 T 为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-151">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="2ed5c-152">**返回值**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-152">**Return Value**</span></span>

<span data-ttu-id="2ed5c-153">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-153">The type of `expression`.</span></span>

<span data-ttu-id="2ed5c-154">**示例**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-154">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="2ed5c-155">STDEV(expression)</span><span class="sxs-lookup"><span data-stu-id="2ed5c-155">STDEV(expression)</span></span>

<span data-ttu-id="2ed5c-156">返回指定表达式中所有值的统计标准偏差。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="2ed5c-157">**参数**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-157">**Arguments**</span></span>

<span data-ttu-id="2ed5c-158">集合 (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-158">A Collection(`Double`).</span></span>

<span data-ttu-id="2ed5c-159">**返回值**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-159">**Return Value**</span></span>

<span data-ttu-id="2ed5c-160">`Double`。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-160">A `Double`.</span></span>

<span data-ttu-id="2ed5c-161">**示例**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-161">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="2ed5c-162">STDEVP(expression)</span><span class="sxs-lookup"><span data-stu-id="2ed5c-162">STDEVP(expression)</span></span>

<span data-ttu-id="2ed5c-163">返回指定表达式中所有值的总体标准偏差。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="2ed5c-164">**参数**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-164">**Arguments**</span></span>

<span data-ttu-id="2ed5c-165">集合 (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-165">A Collection(`Double`).</span></span>

<span data-ttu-id="2ed5c-166">**返回值**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-166">**Return Value**</span></span>

<span data-ttu-id="2ed5c-167">`Double`。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-167">A `Double`.</span></span>

<span data-ttu-id="2ed5c-168">**示例**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-168">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="2ed5c-169">SUM(expression)</span><span class="sxs-lookup"><span data-stu-id="2ed5c-169">SUM(expression)</span></span>

<span data-ttu-id="2ed5c-170">返回集合中所有值的总和。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="2ed5c-171">**参数**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-171">**Arguments**</span></span>

<span data-ttu-id="2ed5c-172">其中 T 为以下类型之一 Collection(T): `Int32`， `Int64`， `Double`， `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="2ed5c-173">**返回值**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-173">**Return Value**</span></span>

<span data-ttu-id="2ed5c-174">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-174">The type of `expression`.</span></span>

<span data-ttu-id="2ed5c-175">**示例**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-175">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="2ed5c-176">VAR(expression)</span><span class="sxs-lookup"><span data-stu-id="2ed5c-176">VAR(expression)</span></span>

<span data-ttu-id="2ed5c-177">返回指定表达式中所有值的方差。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="2ed5c-178">**参数**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-178">**Arguments**</span></span>

<span data-ttu-id="2ed5c-179">集合 (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-179">A Collection(`Double`).</span></span>

<span data-ttu-id="2ed5c-180">**返回值**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-180">**Return Value**</span></span>

<span data-ttu-id="2ed5c-181">`Double`。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-181">A `Double`.</span></span>

<span data-ttu-id="2ed5c-182">**示例**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-182">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="2ed5c-183">VARP(expression)</span><span class="sxs-lookup"><span data-stu-id="2ed5c-183">VARP(expression)</span></span>

<span data-ttu-id="2ed5c-184">返回指定表达式中所有值的总体方差。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="2ed5c-185">**参数**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-185">**Arguments**</span></span>

<span data-ttu-id="2ed5c-186">集合 (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-186">A Collection(`Double`).</span></span>

<span data-ttu-id="2ed5c-187">**返回值**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-187">**Return Value**</span></span>

<span data-ttu-id="2ed5c-188">`Double`。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-188">A `Double`.</span></span>

<span data-ttu-id="2ed5c-189">**示例**</span><span class="sxs-lookup"><span data-stu-id="2ed5c-189">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="2ed5c-190">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ed5c-190">See also</span></span>

<span data-ttu-id="2ed5c-191">有关 SqlClient 支持的聚合函数的更多信息，请参见 SqlClient 提供程序清单中所指定的 SQL Server 版本的相应文档：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-191">For more information about the aggregate functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  

<span data-ttu-id="2ed5c-192">**SQL Server 2005**:[聚合函数 (Transact SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="2ed5c-192">**SQL Server 2005**: [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span></span>  
<span data-ttu-id="2ed5c-193">**SQL Server 2008 和更高版本**:[聚合函数 (Transact SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="2ed5c-193">**SQL Server 2008 and later**:  [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span></span>  
- [<span data-ttu-id="2ed5c-194">实体 SQL 语言</span><span class="sxs-lookup"><span data-stu-id="2ed5c-194">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [<span data-ttu-id="2ed5c-195">聚合 Canonical 函数</span><span class="sxs-lookup"><span data-stu-id="2ed5c-195">Aggregate Canonical Functions</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
