---
title: 数学函数
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: e6c58d781d7138f8295f2d0a2f0db110ad4b1dd6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43560647"
---
# <a name="mathematical-functions"></a><span data-ttu-id="1552e-102">数学函数</span><span class="sxs-lookup"><span data-stu-id="1552e-102">Mathematical Functions</span></span>

<span data-ttu-id="1552e-103">SQL Server .NET Framework 数据提供程序 (SqlClient) 提供了各种数学函数，这些函数针对作为自变量提供的输入值执行计算并返回数值结果。</span><span class="sxs-lookup"><span data-stu-id="1552e-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="1552e-104">这些函数位于 SqlServer 命名空间中，该命名空间在您使用 SqlClient 时可用。</span><span class="sxs-lookup"><span data-stu-id="1552e-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="1552e-105">提供程序的命名空间属性使实体框架可以确定此提供程序对特定构造（如类型和函数）使用哪个前缀。下表描述 SqlClient 数学函数。</span><span class="sxs-lookup"><span data-stu-id="1552e-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="1552e-106">ABS(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-106">ABS(expression)</span></span>

<span data-ttu-id="1552e-107">执行绝对值函数。</span><span class="sxs-lookup"><span data-stu-id="1552e-107">Performs the absolute value function.</span></span>

<span data-ttu-id="1552e-108">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-108">**Arguments**</span></span>

<span data-ttu-id="1552e-109">`expression`：`Int32`、`Int64`、`Double` 或 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="1552e-109">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="1552e-110">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-110">**Return Value**</span></span>

<span data-ttu-id="1552e-111">指定表达式的绝对值。</span><span class="sxs-lookup"><span data-stu-id="1552e-111">The absolute value of the specified expression.</span></span>

<span data-ttu-id="1552e-112">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-112">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="1552e-113">ACOS(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-113">ACOS(expression)</span></span>

<span data-ttu-id="1552e-114">返回指定表达式的反余弦值。</span><span class="sxs-lookup"><span data-stu-id="1552e-114">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="1552e-115">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-115">**Arguments**</span></span>

<span data-ttu-id="1552e-116">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-116">`expression`: A `Double`.</span></span>

<span data-ttu-id="1552e-117">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-117">**Return Value**</span></span>

<span data-ttu-id="1552e-118">`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-118">A `Double`.</span></span>

<span data-ttu-id="1552e-119">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-119">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="1552e-120">ASIN(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-120">ASIN(expression)</span></span>

<span data-ttu-id="1552e-121">返回指定表达式的反正弦值。</span><span class="sxs-lookup"><span data-stu-id="1552e-121">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="1552e-122">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-122">**Arguments**</span></span>

<span data-ttu-id="1552e-123">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-123">`expression`: A `Double`.</span></span>

<span data-ttu-id="1552e-124">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-124">**Return Value**</span></span>

<span data-ttu-id="1552e-125">`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-125">A `Double`.</span></span>

<span data-ttu-id="1552e-126">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-126">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="1552e-127">ATAN(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-127">ATAN(expression)</span></span>

<span data-ttu-id="1552e-128">返回指定数值表达式的反正切值。</span><span class="sxs-lookup"><span data-stu-id="1552e-128">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="1552e-129">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-129">**Arguments**</span></span>

<span data-ttu-id="1552e-130">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-130">`expression`: A `Double`.</span></span>

<span data-ttu-id="1552e-131">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-131">**Return Value**</span></span>

<span data-ttu-id="1552e-132">`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-132">A `Double`.</span></span>

<span data-ttu-id="1552e-133">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-133">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="1552e-134">ATN2(expression, expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-134">ATN2(expression, expression)</span></span>

<span data-ttu-id="1552e-135">返回以弧度表示的角度，其正切介于两个指定的数值表达式之间。</span><span class="sxs-lookup"><span data-stu-id="1552e-135">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="1552e-136">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-136">**Arguments**</span></span>

<span data-ttu-id="1552e-137">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-137">`expression`: A `Double`.</span></span>

<span data-ttu-id="1552e-138">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-138">**Return Value**</span></span>

<span data-ttu-id="1552e-139">`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-139">A `Double`.</span></span>

<span data-ttu-id="1552e-140">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-140">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="1552e-141">CEILING(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-141">CEILING(expression)</span></span>

<span data-ttu-id="1552e-142">将指定表达式转换为大于或等于该表达式的最小整数。</span><span class="sxs-lookup"><span data-stu-id="1552e-142">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="1552e-143">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-143">**Arguments**</span></span>

<span data-ttu-id="1552e-144">`expression`：`Int32`、`Int64`、`Double` 或 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="1552e-144">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="1552e-145">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-145">**Return Value**</span></span>

<span data-ttu-id="1552e-146">`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="1552e-146">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="1552e-147">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-147">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="1552e-148">COS(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-148">COS(expression)</span></span>

<span data-ttu-id="1552e-149">计算以弧度表示的指定角度的三角余弦。</span><span class="sxs-lookup"><span data-stu-id="1552e-149">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="1552e-150">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-150">**Arguments**</span></span> 

<span data-ttu-id="1552e-151">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-151">`expression`: A `Double`.</span></span> 

<span data-ttu-id="1552e-152">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-152">**Return Value**</span></span> 

<span data-ttu-id="1552e-153">`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-153">A `Double`.</span></span> 

<span data-ttu-id="1552e-154">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-154">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="1552e-155">COT(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-155">COT(expression)</span></span>

<span data-ttu-id="1552e-156">计算以弧度表示的指定角度的三角余切。</span><span class="sxs-lookup"><span data-stu-id="1552e-156">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="1552e-157">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-157">**Arguments**</span></span> 

<span data-ttu-id="1552e-158">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-158">`expression`: A `Double`.</span></span> 

<span data-ttu-id="1552e-159">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-159">**Return Value**</span></span> 

<span data-ttu-id="1552e-160">`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-160">A `Double`.</span></span> 

<span data-ttu-id="1552e-161">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-161">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="1552e-162">DEGREES(radians)</span><span class="sxs-lookup"><span data-stu-id="1552e-162">DEGREES(radians)</span></span>

<span data-ttu-id="1552e-163">返回以度为单位的对应角度。</span><span class="sxs-lookup"><span data-stu-id="1552e-163">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="1552e-164">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-164">**Arguments**</span></span> 

<span data-ttu-id="1552e-165">`expression`：`Int32`、`Int64`、`Double` 或 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="1552e-165">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="1552e-166">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-166">**Return Value**</span></span> 

<span data-ttu-id="1552e-167">`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="1552e-167">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="1552e-168">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-168">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="1552e-169">EXP(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-169">EXP(expression)</span></span>

<span data-ttu-id="1552e-170">计算指定数值表达式的指数值。</span><span class="sxs-lookup"><span data-stu-id="1552e-170">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="1552e-171">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-171">**Arguments**</span></span> 

<span data-ttu-id="1552e-172">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-172">`expression`: A `Double`.</span></span> 

<span data-ttu-id="1552e-173">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-173">**Return Value**</span></span> 

<span data-ttu-id="1552e-174">`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-174">A `Double`.</span></span> 

<span data-ttu-id="1552e-175">**示例** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="1552e-175">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="1552e-176">FLOOR(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-176">FLOOR(expression)</span></span>

<span data-ttu-id="1552e-177">将指定表达式转换为小于或等于该表达式的最大整数。</span><span class="sxs-lookup"><span data-stu-id="1552e-177">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="1552e-178">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-178">**Arguments**</span></span> 

<span data-ttu-id="1552e-179">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-179">`expression`: A `Double`.</span></span> 

<span data-ttu-id="1552e-180">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-180">**Return Value**</span></span> 

<span data-ttu-id="1552e-181">`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-181">A `Double`.</span></span> 

<span data-ttu-id="1552e-182">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-182">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="1552e-183">LOG(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-183">LOG(expression)</span></span>

<span data-ttu-id="1552e-184">计算指定 `float` 表达式的自然对数。</span><span class="sxs-lookup"><span data-stu-id="1552e-184">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="1552e-185">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-185">**Arguments**</span></span> 

<span data-ttu-id="1552e-186">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-186">`expression`: A `Double`.</span></span> 

<span data-ttu-id="1552e-187">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-187">**Return Value**</span></span> 

<span data-ttu-id="1552e-188">`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-188">A `Double`.</span></span> 

<span data-ttu-id="1552e-189">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-189">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="1552e-190">LOG10(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-190">LOG10(expression)</span></span>

<span data-ttu-id="1552e-191">返回指定 `Double` 表达式的以 10 为底的对数。</span><span class="sxs-lookup"><span data-stu-id="1552e-191">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="1552e-192">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-192">**Arguments**</span></span> 

<span data-ttu-id="1552e-193">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-193">`expression`: A `Double`.</span></span> 

<span data-ttu-id="1552e-194">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-194">**Return Value**</span></span> 

<span data-ttu-id="1552e-195">`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-195">A `Double`.</span></span> 

<span data-ttu-id="1552e-196">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-196">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="1552e-197">PI （)</span><span class="sxs-lookup"><span data-stu-id="1552e-197">PI()</span></span>

<span data-ttu-id="1552e-198">以 `Double` 格式返回 pi 的常量值。</span><span class="sxs-lookup"><span data-stu-id="1552e-198">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="1552e-199">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-199">**Return Value**</span></span> 

<span data-ttu-id="1552e-200">`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-200">A `Double`.</span></span> 

<span data-ttu-id="1552e-201">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-201">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="1552e-202">POWER （numeric_expression，power_expression）</span><span class="sxs-lookup"><span data-stu-id="1552e-202">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="1552e-203">计算指定表达式的指定幂的值。</span><span class="sxs-lookup"><span data-stu-id="1552e-203">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="1552e-204">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-204">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="1552e-205">`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="1552e-205">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="1552e-206">`Double`，表示对 `numeric_expression` 进行幂运算的幂值。</span><span class="sxs-lookup"><span data-stu-id="1552e-206">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="1552e-207">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-207">**Return Value**</span></span> 

<span data-ttu-id="1552e-208">指定 `numeric_expression` 的指定 `power_expression` 次幂的值。</span><span class="sxs-lookup"><span data-stu-id="1552e-208">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="1552e-209">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-209">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="1552e-210">RADIANS(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-210">RADIANS(expression)</span></span>

<span data-ttu-id="1552e-211">将度数转换成弧度。</span><span class="sxs-lookup"><span data-stu-id="1552e-211">Converts degrees to radians.</span></span> 

<span data-ttu-id="1552e-212">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-212">**Arguments**</span></span> 

<span data-ttu-id="1552e-213">`expression`：`Int32`、`Int64`、`Double` 或 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="1552e-213">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="1552e-214">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-214">**Return Value**</span></span> 

<span data-ttu-id="1552e-215">`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="1552e-215">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="1552e-216">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-216">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="1552e-217">RAND([seed])</span><span class="sxs-lookup"><span data-stu-id="1552e-217">RAND([seed])</span></span>

<span data-ttu-id="1552e-218">返回介于 0 和 1 之间的随机值。</span><span class="sxs-lookup"><span data-stu-id="1552e-218">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="1552e-219">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-219">**Arguments**</span></span> 

<span data-ttu-id="1552e-220">作为种子值`Int32`。</span><span class="sxs-lookup"><span data-stu-id="1552e-220">The seed value as an `Int32`.</span></span> <span data-ttu-id="1552e-221">如果未指定种子，则 SQL Server 数据库引擎将随机分配种子值。</span><span class="sxs-lookup"><span data-stu-id="1552e-221">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="1552e-222">对于指定的种子值，返回的结果始终相同。</span><span class="sxs-lookup"><span data-stu-id="1552e-222">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="1552e-223">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-223">**Return Value**</span></span> 

<span data-ttu-id="1552e-224">介于 0 和 1 之间的随机 `Double` 值。</span><span class="sxs-lookup"><span data-stu-id="1552e-224">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="1552e-225">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-225">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="1552e-226">ROUND(numeric_expression, length[,function])</span><span class="sxs-lookup"><span data-stu-id="1552e-226">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="1552e-227">返回一个舍入到指定长度或精度的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="1552e-227">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="1552e-228">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-228">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="1552e-229">`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="1552e-229">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="1552e-230">表示 `Int32` 要舍入到的精度的 `numeric_expression`。</span><span class="sxs-lookup"><span data-stu-id="1552e-230">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="1552e-231">如果 `length` 为正数，则将 `numeric_expression` 舍入到 `length` 指定的小数位数。</span><span class="sxs-lookup"><span data-stu-id="1552e-231">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="1552e-232">如果 `length` 为负数，则将 `numeric_expression` 向小数点左边舍入 `length` 指定的长度。</span><span class="sxs-lookup"><span data-stu-id="1552e-232">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="1552e-233">可选。</span><span class="sxs-lookup"><span data-stu-id="1552e-233">Optional.</span></span> <span data-ttu-id="1552e-234">`Int32` ，表示要执行的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="1552e-234">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="1552e-235">当函数省略或其值为 0 （默认值），`numeric_expression`舍入。</span><span class="sxs-lookup"><span data-stu-id="1552e-235">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="1552e-236">如果指定了 0 以外的值，则将截断 `numeric_expression`。</span><span class="sxs-lookup"><span data-stu-id="1552e-236">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="1552e-237">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-237">**Return Value**</span></span> 

<span data-ttu-id="1552e-238">指定 `numeric_expression` 的指定 `power_expression` 次幂的值。</span><span class="sxs-lookup"><span data-stu-id="1552e-238">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="1552e-239">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-239">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="1552e-240">SIGN(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-240">SIGN(expression)</span></span> 

<span data-ttu-id="1552e-241">返回指定表达式的正号 (+1)、零 (0) 或负号 (-1)。</span><span class="sxs-lookup"><span data-stu-id="1552e-241">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="1552e-242">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-242">**Arguments**</span></span> 

<span data-ttu-id="1552e-243">`expression`：`Int32`、`Int64`、`Double` 或 `Decimal`</span><span class="sxs-lookup"><span data-stu-id="1552e-243">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="1552e-244">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-244">**Return Value**</span></span> 

<span data-ttu-id="1552e-245">`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="1552e-245">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="1552e-246">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-246">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="1552e-247">SIN(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-247">SIN(expression)</span></span>

<span data-ttu-id="1552e-248">计算以弧度表示的指定角度的三角正弦并返回 `Double` 表达式。</span><span class="sxs-lookup"><span data-stu-id="1552e-248">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="1552e-249">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-249">**Arguments**</span></span> 

<span data-ttu-id="1552e-250">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-250">`expression`: A `Double`.</span></span> 

<span data-ttu-id="1552e-251">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-251">**Return Value**</span></span> 

<span data-ttu-id="1552e-252">`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-252">A `Double`.</span></span> 

<span data-ttu-id="1552e-253">**示例** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="1552e-253">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="1552e-254">SQRT(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-254">SQRT(expression)</span></span>

<span data-ttu-id="1552e-255">返回指定表达式的平方根。</span><span class="sxs-lookup"><span data-stu-id="1552e-255">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="1552e-256">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-256">**Arguments**</span></span> 

<span data-ttu-id="1552e-257">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-257">`expression`: A `Double`.</span></span> 

<span data-ttu-id="1552e-258">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-258">**Return Value**</span></span> 

<span data-ttu-id="1552e-259">`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-259">A `Double`.</span></span> 

<span data-ttu-id="1552e-260">**示例** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="1552e-260">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="1552e-261">SQUARE(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-261">SQUARE(expression)</span></span>

<span data-ttu-id="1552e-262">返回指定表达式的平方。</span><span class="sxs-lookup"><span data-stu-id="1552e-262">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="1552e-263">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-263">**Arguments**</span></span> 

<span data-ttu-id="1552e-264">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-264">`expression`: A `Double`.</span></span> 

<span data-ttu-id="1552e-265">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-265">**Return Value**</span></span> 

<span data-ttu-id="1552e-266">`Double`。</span><span class="sxs-lookup"><span data-stu-id="1552e-266">A `Double`.</span></span> 

<span data-ttu-id="1552e-267">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-267">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="1552e-268">TAN(expression)</span><span class="sxs-lookup"><span data-stu-id="1552e-268">TAN(expression)</span></span>

<span data-ttu-id="1552e-269">计算指定表达式的正切。</span><span class="sxs-lookup"><span data-stu-id="1552e-269">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="1552e-270">**参数**</span><span class="sxs-lookup"><span data-stu-id="1552e-270">**Arguments**</span></span> 

<span data-ttu-id="1552e-271">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="1552e-271">`expression`: `Double`</span></span> 

<span data-ttu-id="1552e-272">**返回值**</span><span class="sxs-lookup"><span data-stu-id="1552e-272">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="1552e-273">**示例**</span><span class="sxs-lookup"><span data-stu-id="1552e-273">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="1552e-274">请参阅</span><span class="sxs-lookup"><span data-stu-id="1552e-274">See also</span></span>

<span data-ttu-id="1552e-275">有关 SqlClient 支持的数学函数的更多信息，请参见 SqlClient 提供程序清单中所指定的 SQL Server 版本的相应文档：</span><span class="sxs-lookup"><span data-stu-id="1552e-275">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  
  
<span data-ttu-id="1552e-276">**SQL Server 2005:** [数学函数 (Transact SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="1552e-276">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>  
<span data-ttu-id="1552e-277">**SQL Server 2008:** [数学函数 (Transact SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="1552e-277">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>  
<span data-ttu-id="1552e-278">**SQL Server 2012 和更高版本：** [数学函数 (Transact SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="1552e-278">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>   

 [<span data-ttu-id="1552e-279">用于实体框架函数的 SqlClient</span><span class="sxs-lookup"><span data-stu-id="1552e-279">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
