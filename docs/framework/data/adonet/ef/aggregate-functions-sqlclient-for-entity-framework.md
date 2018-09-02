---
title: 聚合函数（用于实体框架的 SqlClient）
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 8ed9a58da9914724fe312876d6594cb526f2e0e9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43452894"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="a2e23-102">聚合函数（用于实体框架的 SqlClient）</span><span class="sxs-lookup"><span data-stu-id="a2e23-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="a2e23-103">SQL Server .NET Framework 数据提供程序 (SqlClient) 提供聚合函数。</span><span class="sxs-lookup"><span data-stu-id="a2e23-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="a2e23-104">聚合函数对一组输入值执行计算并返回一个值。</span><span class="sxs-lookup"><span data-stu-id="a2e23-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="a2e23-105">这些函数位于 SqlServer 命名空间中，该命名空间在您使用 SqlClient 时可用。</span><span class="sxs-lookup"><span data-stu-id="a2e23-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="a2e23-106">提供程序的命名空间属性使实体框架可以确定此提供程序对特定构造（如类型和函数）使用哪个前缀。</span><span class="sxs-lookup"><span data-stu-id="a2e23-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="a2e23-107">以下是 SqlClient 聚合函数。</span><span class="sxs-lookup"><span data-stu-id="a2e23-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="a2e23-108">AVG(expression)</span><span class="sxs-lookup"><span data-stu-id="a2e23-108">AVG(expression)</span></span>

<span data-ttu-id="a2e23-109">返回集合中各值的平均值。</span><span class="sxs-lookup"><span data-stu-id="a2e23-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="a2e23-110">空值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="a2e23-110">Null values are ignored.</span></span>

<span data-ttu-id="a2e23-111">**参数**</span><span class="sxs-lookup"><span data-stu-id="a2e23-111">**Arguments**</span></span>

<span data-ttu-id="a2e23-112">`Int32`， `Int64`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="a2e23-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="a2e23-113">**返回值**</span><span class="sxs-lookup"><span data-stu-id="a2e23-113">**Return Value**</span></span>

<span data-ttu-id="a2e23-114">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="a2e23-114">The type of `expression`.</span></span>

<span data-ttu-id="a2e23-115">**示例**</span><span class="sxs-lookup"><span data-stu-id="a2e23-115">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksumaggcollection"></a><span data-ttu-id="a2e23-116">CHECKSUM_AGG(collection)</span><span class="sxs-lookup"><span data-stu-id="a2e23-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="a2e23-117">返回集合中各值的校验和。</span><span class="sxs-lookup"><span data-stu-id="a2e23-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="a2e23-118">空值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="a2e23-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="a2e23-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="a2e23-119">**Arguments**</span></span>
 
 <span data-ttu-id="a2e23-120">集合 (`Int32`)。</span><span class="sxs-lookup"><span data-stu-id="a2e23-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="a2e23-121">**返回值**</span><span class="sxs-lookup"><span data-stu-id="a2e23-121">**Return Value**</span></span>
 
 <span data-ttu-id="a2e23-122">一个 `Int32`。</span><span class="sxs-lookup"><span data-stu-id="a2e23-122">An `Int32`.</span></span>
 
 <span data-ttu-id="a2e23-123">**示例**</span><span class="sxs-lookup"><span data-stu-id="a2e23-123">**Example**</span></span>
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="a2e23-124">COUNT(expression)</span><span class="sxs-lookup"><span data-stu-id="a2e23-124">COUNT(expression)</span></span>

<span data-ttu-id="a2e23-125">以 `Int32` 形式返回集合中的项数。</span><span class="sxs-lookup"><span data-stu-id="a2e23-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="a2e23-126">**参数**</span><span class="sxs-lookup"><span data-stu-id="a2e23-126">**Arguments**</span></span>

<span data-ttu-id="a2e23-127">集合\<T >，其中 T 为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="a2e23-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="a2e23-128">`Guid` （在 SQL Server 2000 中不返回）</span><span class="sxs-lookup"><span data-stu-id="a2e23-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="a2e23-129">**返回值**</span><span class="sxs-lookup"><span data-stu-id="a2e23-129">**Return Value**</span></span>

<span data-ttu-id="a2e23-130">一个 `Int32`。</span><span class="sxs-lookup"><span data-stu-id="a2e23-130">An `Int32`.</span></span>

<span data-ttu-id="a2e23-131">**示例**</span><span class="sxs-lookup"><span data-stu-id="a2e23-131">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
<span data-ttu-id="a2e23-132">[！ 代码 sql[DP EntityServices 概念 #SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span><span class="sxs-lookup"><span data-stu-id="a2e23-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span></span>
 
## <a name="countbigexpression"></a><span data-ttu-id="a2e23-133">COUNT_BIG(expression)</span><span class="sxs-lookup"><span data-stu-id="a2e23-133">COUNT_BIG(expression)</span></span>
 
 <span data-ttu-id="a2e23-134">以 `bigint` 形式返回集合中的项数。</span><span class="sxs-lookup"><span data-stu-id="a2e23-134">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="a2e23-135">**参数**</span><span class="sxs-lookup"><span data-stu-id="a2e23-135">**Arguments**</span></span>
 
 <span data-ttu-id="a2e23-136">Collection(T)，其中 T 为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="a2e23-136">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="a2e23-137">`Guid` （在 SQL Server 2000 中不返回）</span><span class="sxs-lookup"><span data-stu-id="a2e23-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="a2e23-138">**返回值**</span><span class="sxs-lookup"><span data-stu-id="a2e23-138">**Return Value**</span></span>

<span data-ttu-id="a2e23-139">一个 `Int64`。</span><span class="sxs-lookup"><span data-stu-id="a2e23-139">An `Int64`.</span></span>

<span data-ttu-id="a2e23-140">**示例**</span><span class="sxs-lookup"><span data-stu-id="a2e23-140">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="a2e23-141">MAX(expression)</span><span class="sxs-lookup"><span data-stu-id="a2e23-141">MAX(expression)</span></span>

<span data-ttu-id="a2e23-142">返回集合中的最大值。</span><span class="sxs-lookup"><span data-stu-id="a2e23-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="a2e23-143">**参数**</span><span class="sxs-lookup"><span data-stu-id="a2e23-143">**Arguments**</span></span>

<span data-ttu-id="a2e23-144">Collection(T)，其中 T 为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="a2e23-144">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="a2e23-145">**返回值**</span><span class="sxs-lookup"><span data-stu-id="a2e23-145">**Return Value**</span></span>

<span data-ttu-id="a2e23-146">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="a2e23-146">The type of `expression`.</span></span>

<span data-ttu-id="a2e23-147">**示例**</span><span class="sxs-lookup"><span data-stu-id="a2e23-147">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="a2e23-148">MIN(expression)</span><span class="sxs-lookup"><span data-stu-id="a2e23-148">MIN(expression)</span></span>

<span data-ttu-id="a2e23-149">返回集合中的最小值。</span><span class="sxs-lookup"><span data-stu-id="a2e23-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="a2e23-150">**参数**</span><span class="sxs-lookup"><span data-stu-id="a2e23-150">**Arguments**</span></span>

<span data-ttu-id="a2e23-151">Collection(T)，其中 T 为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="a2e23-151">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="a2e23-152">**返回值**</span><span class="sxs-lookup"><span data-stu-id="a2e23-152">**Return Value**</span></span>

<span data-ttu-id="a2e23-153">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="a2e23-153">The type of `expression`.</span></span>

<span data-ttu-id="a2e23-154">**示例**</span><span class="sxs-lookup"><span data-stu-id="a2e23-154">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="a2e23-155">STDEV(expression)</span><span class="sxs-lookup"><span data-stu-id="a2e23-155">STDEV(expression)</span></span>

<span data-ttu-id="a2e23-156">返回指定表达式中所有值的统计标准偏差。</span><span class="sxs-lookup"><span data-stu-id="a2e23-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="a2e23-157">**参数**</span><span class="sxs-lookup"><span data-stu-id="a2e23-157">**Arguments**</span></span>

<span data-ttu-id="a2e23-158">集合 (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="a2e23-158">A Collection(`Double`).</span></span>

<span data-ttu-id="a2e23-159">**返回值**</span><span class="sxs-lookup"><span data-stu-id="a2e23-159">**Return Value**</span></span>

<span data-ttu-id="a2e23-160">`Double`。</span><span class="sxs-lookup"><span data-stu-id="a2e23-160">A `Double`.</span></span>

<span data-ttu-id="a2e23-161">**示例**</span><span class="sxs-lookup"><span data-stu-id="a2e23-161">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="a2e23-162">STDEVP(expression)</span><span class="sxs-lookup"><span data-stu-id="a2e23-162">STDEVP(expression)</span></span>

<span data-ttu-id="a2e23-163">返回指定表达式中所有值的总体标准偏差。</span><span class="sxs-lookup"><span data-stu-id="a2e23-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="a2e23-164">**参数**</span><span class="sxs-lookup"><span data-stu-id="a2e23-164">**Arguments**</span></span>

<span data-ttu-id="a2e23-165">集合 (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="a2e23-165">A Collection(`Double`).</span></span>

<span data-ttu-id="a2e23-166">**返回值**</span><span class="sxs-lookup"><span data-stu-id="a2e23-166">**Return Value**</span></span>

<span data-ttu-id="a2e23-167">`Double`。</span><span class="sxs-lookup"><span data-stu-id="a2e23-167">A `Double`.</span></span>

<span data-ttu-id="a2e23-168">**示例**</span><span class="sxs-lookup"><span data-stu-id="a2e23-168">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="a2e23-169">SUM(expression)</span><span class="sxs-lookup"><span data-stu-id="a2e23-169">SUM(expression)</span></span>

<span data-ttu-id="a2e23-170">返回集合中所有值的总和。</span><span class="sxs-lookup"><span data-stu-id="a2e23-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="a2e23-171">**参数**</span><span class="sxs-lookup"><span data-stu-id="a2e23-171">**Arguments**</span></span>

<span data-ttu-id="a2e23-172">其中 T 为以下类型之一 Collection(T): `Int32`， `Int64`， `Double`， `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="a2e23-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="a2e23-173">**返回值**</span><span class="sxs-lookup"><span data-stu-id="a2e23-173">**Return Value**</span></span>

<span data-ttu-id="a2e23-174">`expression` 的类型。</span><span class="sxs-lookup"><span data-stu-id="a2e23-174">The type of `expression`.</span></span>

<span data-ttu-id="a2e23-175">**示例**</span><span class="sxs-lookup"><span data-stu-id="a2e23-175">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="a2e23-176">VAR(expression)</span><span class="sxs-lookup"><span data-stu-id="a2e23-176">VAR(expression)</span></span>

<span data-ttu-id="a2e23-177">返回指定表达式中所有值的方差。</span><span class="sxs-lookup"><span data-stu-id="a2e23-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="a2e23-178">**参数**</span><span class="sxs-lookup"><span data-stu-id="a2e23-178">**Arguments**</span></span>

<span data-ttu-id="a2e23-179">集合 (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="a2e23-179">A Collection(`Double`).</span></span>

<span data-ttu-id="a2e23-180">**返回值**</span><span class="sxs-lookup"><span data-stu-id="a2e23-180">**Return Value**</span></span>

<span data-ttu-id="a2e23-181">`Double`。</span><span class="sxs-lookup"><span data-stu-id="a2e23-181">A `Double`.</span></span>

<span data-ttu-id="a2e23-182">**示例**</span><span class="sxs-lookup"><span data-stu-id="a2e23-182">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="a2e23-183">VARP(expression)</span><span class="sxs-lookup"><span data-stu-id="a2e23-183">VARP(expression)</span></span>

<span data-ttu-id="a2e23-184">返回指定表达式中所有值的总体方差。</span><span class="sxs-lookup"><span data-stu-id="a2e23-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="a2e23-185">**参数**</span><span class="sxs-lookup"><span data-stu-id="a2e23-185">**Arguments**</span></span>

<span data-ttu-id="a2e23-186">集合 (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="a2e23-186">A Collection(`Double`).</span></span>

<span data-ttu-id="a2e23-187">**返回值**</span><span class="sxs-lookup"><span data-stu-id="a2e23-187">**Return Value**</span></span>

<span data-ttu-id="a2e23-188">`Double`。</span><span class="sxs-lookup"><span data-stu-id="a2e23-188">A `Double`.</span></span>

<span data-ttu-id="a2e23-189">**示例**</span><span class="sxs-lookup"><span data-stu-id="a2e23-189">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="a2e23-190">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2e23-190">See also</span></span>

<span data-ttu-id="a2e23-191">有关 SqlClient 支持的聚合函数的更多信息，请参见 SqlClient 提供程序清单中所指定的 SQL Server 版本的相应文档：</span><span class="sxs-lookup"><span data-stu-id="a2e23-191">For more information about the aggregate functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  
  
<span data-ttu-id="a2e23-192">**SQL Server 2005**:[聚合函数 (Transact SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="a2e23-192">**SQL Server 2005**: [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span></span>  
<span data-ttu-id="a2e23-193">**SQL Server 2008 和更高版本**:[聚合函数 (Transact SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="a2e23-193">**SQL Server 2008 and later**:  [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span></span>  
[<span data-ttu-id="a2e23-194">实体 SQL 语言</span><span class="sxs-lookup"><span data-stu-id="a2e23-194">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
[<span data-ttu-id="a2e23-195">聚合 Canonical 函数</span><span class="sxs-lookup"><span data-stu-id="a2e23-195">Aggregate Canonical Functions</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
