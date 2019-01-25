---
title: 数学函数
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: d8d766cb1416a9a07476175364fe568d81fd9b25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652262"
---
# <a name="mathematical-functions"></a><span data-ttu-id="90c75-102">数学函数</span><span class="sxs-lookup"><span data-stu-id="90c75-102">Mathematical Functions</span></span>

<span data-ttu-id="90c75-103">SQL Server .NET Framework 数据提供程序 (SqlClient) 提供了各种数学函数，这些函数针对作为自变量提供的输入值执行计算并返回数值结果。</span><span class="sxs-lookup"><span data-stu-id="90c75-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="90c75-104">这些函数位于 SqlServer 命名空间中，该命名空间在您使用 SqlClient 时可用。</span><span class="sxs-lookup"><span data-stu-id="90c75-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="90c75-105">提供程序的命名空间属性使实体框架可以确定此提供程序对特定构造（如类型和函数）使用哪个前缀。</span><span class="sxs-lookup"><span data-stu-id="90c75-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="90c75-106">下表描述 SqlClient 数学函数。</span><span class="sxs-lookup"><span data-stu-id="90c75-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="90c75-107">ABS(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-107">ABS(expression)</span></span>

<span data-ttu-id="90c75-108">执行绝对值函数。</span><span class="sxs-lookup"><span data-stu-id="90c75-108">Performs the absolute value function.</span></span>

<span data-ttu-id="90c75-109">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-109">**Arguments**</span></span>

<span data-ttu-id="90c75-110">`expression`：`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="90c75-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="90c75-111">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-111">**Return Value**</span></span>

<span data-ttu-id="90c75-112">指定表达式的绝对值。</span><span class="sxs-lookup"><span data-stu-id="90c75-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="90c75-113">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="90c75-114">ACOS(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-114">ACOS(expression)</span></span>

<span data-ttu-id="90c75-115">返回指定表达式的反余弦值。</span><span class="sxs-lookup"><span data-stu-id="90c75-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="90c75-116">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-116">**Arguments**</span></span>

<span data-ttu-id="90c75-117">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="90c75-118">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-118">**Return Value**</span></span>

<span data-ttu-id="90c75-119">`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-119">A `Double`.</span></span>

<span data-ttu-id="90c75-120">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="90c75-121">ASIN(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-121">ASIN(expression)</span></span>

<span data-ttu-id="90c75-122">返回指定表达式的反正弦值。</span><span class="sxs-lookup"><span data-stu-id="90c75-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="90c75-123">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-123">**Arguments**</span></span>

<span data-ttu-id="90c75-124">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="90c75-125">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-125">**Return Value**</span></span>

<span data-ttu-id="90c75-126">`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-126">A `Double`.</span></span>

<span data-ttu-id="90c75-127">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="90c75-128">ATAN(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-128">ATAN(expression)</span></span>

<span data-ttu-id="90c75-129">返回指定数值表达式的反正切值。</span><span class="sxs-lookup"><span data-stu-id="90c75-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="90c75-130">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-130">**Arguments**</span></span>

<span data-ttu-id="90c75-131">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="90c75-132">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-132">**Return Value**</span></span>

<span data-ttu-id="90c75-133">`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-133">A `Double`.</span></span>

<span data-ttu-id="90c75-134">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="90c75-135">ATN2(expression, expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="90c75-136">返回以弧度表示的角度，其正切介于两个指定的数值表达式之间。</span><span class="sxs-lookup"><span data-stu-id="90c75-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="90c75-137">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-137">**Arguments**</span></span>

<span data-ttu-id="90c75-138">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="90c75-139">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-139">**Return Value**</span></span>

<span data-ttu-id="90c75-140">`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-140">A `Double`.</span></span>

<span data-ttu-id="90c75-141">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a><span data-ttu-id="90c75-142">CEILING(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-142">CEILING(expression)</span></span>

<span data-ttu-id="90c75-143">将指定表达式转换为大于或等于该表达式的最小整数。</span><span class="sxs-lookup"><span data-stu-id="90c75-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="90c75-144">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-144">**Arguments**</span></span>

<span data-ttu-id="90c75-145">`expression`：`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="90c75-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="90c75-146">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-146">**Return Value**</span></span>

<span data-ttu-id="90c75-147">`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="90c75-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="90c75-148">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-148">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="90c75-149">COS(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-149">COS(expression)</span></span>

<span data-ttu-id="90c75-150">计算以弧度表示的指定角度的三角余弦。</span><span class="sxs-lookup"><span data-stu-id="90c75-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span> 

<span data-ttu-id="90c75-151">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-151">**Arguments**</span></span> 

<span data-ttu-id="90c75-152">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-152">`expression`: A `Double`.</span></span> 

<span data-ttu-id="90c75-153">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-153">**Return Value**</span></span> 

<span data-ttu-id="90c75-154">`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-154">A `Double`.</span></span> 

<span data-ttu-id="90c75-155">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-155">**Example**</span></span> 

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="90c75-156">COT(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-156">COT(expression)</span></span>

<span data-ttu-id="90c75-157">计算以弧度表示的指定角度的三角余切。</span><span class="sxs-lookup"><span data-stu-id="90c75-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span> 

<span data-ttu-id="90c75-158">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-158">**Arguments**</span></span> 

<span data-ttu-id="90c75-159">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-159">`expression`: A `Double`.</span></span> 

<span data-ttu-id="90c75-160">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-160">**Return Value**</span></span> 

<span data-ttu-id="90c75-161">`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-161">A `Double`.</span></span> 

<span data-ttu-id="90c75-162">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-162">**Example**</span></span> 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="90c75-163">DEGREES(radians)</span><span class="sxs-lookup"><span data-stu-id="90c75-163">DEGREES(radians)</span></span>

<span data-ttu-id="90c75-164">返回以度为单位的对应角度。</span><span class="sxs-lookup"><span data-stu-id="90c75-164">Returns the corresponding angle in degrees.</span></span> 

<span data-ttu-id="90c75-165">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-165">**Arguments**</span></span> 

<span data-ttu-id="90c75-166">`expression`：`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="90c75-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="90c75-167">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-167">**Return Value**</span></span> 

<span data-ttu-id="90c75-168">`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="90c75-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="90c75-169">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-169">**Example**</span></span> 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="90c75-170">EXP(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-170">EXP(expression)</span></span>

<span data-ttu-id="90c75-171">计算指定数值表达式的指数值。</span><span class="sxs-lookup"><span data-stu-id="90c75-171">Calculates the exponential value of a specified numeric expression.</span></span> 

<span data-ttu-id="90c75-172">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-172">**Arguments**</span></span> 

<span data-ttu-id="90c75-173">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-173">`expression`: A `Double`.</span></span> 

<span data-ttu-id="90c75-174">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-174">**Return Value**</span></span> 

<span data-ttu-id="90c75-175">`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-175">A `Double`.</span></span> 

<span data-ttu-id="90c75-176">**示例** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="90c75-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="90c75-177">FLOOR(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-177">FLOOR(expression)</span></span>

<span data-ttu-id="90c75-178">将指定表达式转换为小于或等于该表达式的最大整数。</span><span class="sxs-lookup"><span data-stu-id="90c75-178">Converts the specified expression to the largest integer less than or equal to it.</span></span> 

<span data-ttu-id="90c75-179">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-179">**Arguments**</span></span> 

<span data-ttu-id="90c75-180">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-180">`expression`: A `Double`.</span></span> 

<span data-ttu-id="90c75-181">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-181">**Return Value**</span></span> 

<span data-ttu-id="90c75-182">`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-182">A `Double`.</span></span> 

<span data-ttu-id="90c75-183">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-183">**Example**</span></span> 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="90c75-184">LOG(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-184">LOG(expression)</span></span>

<span data-ttu-id="90c75-185">计算指定 `float` 表达式的自然对数。</span><span class="sxs-lookup"><span data-stu-id="90c75-185">Calculates the natural logarithm of the specified `float` expression.</span></span> 

<span data-ttu-id="90c75-186">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-186">**Arguments**</span></span> 

<span data-ttu-id="90c75-187">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-187">`expression`: A `Double`.</span></span> 

<span data-ttu-id="90c75-188">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-188">**Return Value**</span></span> 

<span data-ttu-id="90c75-189">`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-189">A `Double`.</span></span> 

<span data-ttu-id="90c75-190">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-190">**Example**</span></span> 

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="90c75-191">LOG10(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-191">LOG10(expression)</span></span>

<span data-ttu-id="90c75-192">返回指定 `Double` 表达式的以 10 为底的对数。</span><span class="sxs-lookup"><span data-stu-id="90c75-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span> 

<span data-ttu-id="90c75-193">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-193">**Arguments**</span></span> 

<span data-ttu-id="90c75-194">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-194">`expression`: A `Double`.</span></span> 

<span data-ttu-id="90c75-195">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-195">**Return Value**</span></span> 

<span data-ttu-id="90c75-196">`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-196">A `Double`.</span></span> 

<span data-ttu-id="90c75-197">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-197">**Example**</span></span> 

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="90c75-198">PI()</span><span class="sxs-lookup"><span data-stu-id="90c75-198">PI()</span></span>

<span data-ttu-id="90c75-199">以 `Double` 格式返回 pi 的常量值。</span><span class="sxs-lookup"><span data-stu-id="90c75-199">Returns the constant value of pi as a `Double`.</span></span> 

<span data-ttu-id="90c75-200">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-200">**Return Value**</span></span> 

<span data-ttu-id="90c75-201">`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-201">A `Double`.</span></span> 

<span data-ttu-id="90c75-202">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-202">**Example**</span></span> 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a><span data-ttu-id="90c75-203">POWER(numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="90c75-204">计算指定表达式的指定幂的值。</span><span class="sxs-lookup"><span data-stu-id="90c75-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="90c75-205">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-205">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="90c75-206">`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="90c75-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="90c75-207">`Double`，表示对 `numeric_expression` 进行幂运算的幂值。</span><span class="sxs-lookup"><span data-stu-id="90c75-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>| 

<span data-ttu-id="90c75-208">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-208">**Return Value**</span></span> 

<span data-ttu-id="90c75-209">指定 `numeric_expression` 的指定 `power_expression` 次幂的值。</span><span class="sxs-lookup"><span data-stu-id="90c75-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span> 

<span data-ttu-id="90c75-210">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-210">**Example**</span></span> 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="90c75-211">RADIANS(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-211">RADIANS(expression)</span></span>

<span data-ttu-id="90c75-212">将度数转换成弧度。</span><span class="sxs-lookup"><span data-stu-id="90c75-212">Converts degrees to radians.</span></span> 

<span data-ttu-id="90c75-213">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-213">**Arguments**</span></span> 

<span data-ttu-id="90c75-214">`expression`：`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="90c75-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="90c75-215">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-215">**Return Value**</span></span> 

<span data-ttu-id="90c75-216">`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="90c75-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="90c75-217">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-217">**Example**</span></span> 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="90c75-218">RAND([seed])</span><span class="sxs-lookup"><span data-stu-id="90c75-218">RAND([seed])</span></span>

<span data-ttu-id="90c75-219">返回介于 0 和 1 之间的随机值。</span><span class="sxs-lookup"><span data-stu-id="90c75-219">Returns a random value from 0 through 1.</span></span> 

<span data-ttu-id="90c75-220">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-220">**Arguments**</span></span> 

<span data-ttu-id="90c75-221">作为种子值`Int32`。</span><span class="sxs-lookup"><span data-stu-id="90c75-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="90c75-222">如果未指定种子，则 SQL Server 数据库引擎将随机分配种子值。</span><span class="sxs-lookup"><span data-stu-id="90c75-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="90c75-223">对于指定的种子值，返回的结果始终相同。</span><span class="sxs-lookup"><span data-stu-id="90c75-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="90c75-224">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-224">**Return Value**</span></span> 

<span data-ttu-id="90c75-225">介于 0 和 1 之间的随机 `Double` 值。</span><span class="sxs-lookup"><span data-stu-id="90c75-225">A random `Double` value from 0 through 1.</span></span> 

<span data-ttu-id="90c75-226">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-226">**Example**</span></span> 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a><span data-ttu-id="90c75-227">ROUND(numeric_expression, length[,function])</span><span class="sxs-lookup"><span data-stu-id="90c75-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="90c75-228">返回一个舍入到指定长度或精度的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="90c75-228">Returns a numeric expression, rounded to the specified length or precision.</span></span> 

<span data-ttu-id="90c75-229">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-229">**Arguments**</span></span> 

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="90c75-230">`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="90c75-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 
|`length`| <span data-ttu-id="90c75-231">表示 `Int32` 要舍入到的精度的 `numeric_expression`。</span><span class="sxs-lookup"><span data-stu-id="90c75-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="90c75-232">如果 `length` 为正数，则将 `numeric_expression` 舍入到 `length` 指定的小数位数。</span><span class="sxs-lookup"><span data-stu-id="90c75-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="90c75-233">如果 `length` 为负数，则将 `numeric_expression` 向小数点左边舍入 `length` 指定的长度。</span><span class="sxs-lookup"><span data-stu-id="90c75-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="90c75-234">可选。</span><span class="sxs-lookup"><span data-stu-id="90c75-234">Optional.</span></span> <span data-ttu-id="90c75-235">`Int32` ，表示要执行的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="90c75-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="90c75-236">当函数省略或其值为 0 （默认值），`numeric_expression`舍入。</span><span class="sxs-lookup"><span data-stu-id="90c75-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="90c75-237">如果指定了 0 以外的值，则将截断 `numeric_expression`。</span><span class="sxs-lookup"><span data-stu-id="90c75-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="90c75-238">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-238">**Return Value**</span></span> 

<span data-ttu-id="90c75-239">指定 `numeric_expression` 的指定 `power_expression` 次幂的值。</span><span class="sxs-lookup"><span data-stu-id="90c75-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="90c75-240">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-240">**Example**</span></span> 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="90c75-241">SIGN(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-241">SIGN(expression)</span></span> 

<span data-ttu-id="90c75-242">返回指定表达式的正号 (+1)、零 (0) 或负号 (-1)。</span><span class="sxs-lookup"><span data-stu-id="90c75-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span> 

<span data-ttu-id="90c75-243">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-243">**Arguments**</span></span> 

<span data-ttu-id="90c75-244">`expression`：`Int32`、`Int64`、`Double` 或 `Decimal`</span><span class="sxs-lookup"><span data-stu-id="90c75-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span> 

<span data-ttu-id="90c75-245">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-245">**Return Value**</span></span> 

<span data-ttu-id="90c75-246">`Int32`， `Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="90c75-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span> 

<span data-ttu-id="90c75-247">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-247">**Example**</span></span> 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="90c75-248">SIN(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-248">SIN(expression)</span></span>

<span data-ttu-id="90c75-249">计算以弧度表示的指定角度的三角正弦并返回 `Double` 表达式。</span><span class="sxs-lookup"><span data-stu-id="90c75-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span> 

<span data-ttu-id="90c75-250">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-250">**Arguments**</span></span> 

<span data-ttu-id="90c75-251">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-251">`expression`: A `Double`.</span></span> 

<span data-ttu-id="90c75-252">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-252">**Return Value**</span></span> 

<span data-ttu-id="90c75-253">`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-253">A `Double`.</span></span> 

<span data-ttu-id="90c75-254">**示例** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="90c75-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="90c75-255">SQRT(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-255">SQRT(expression)</span></span>

<span data-ttu-id="90c75-256">返回指定表达式的平方根。</span><span class="sxs-lookup"><span data-stu-id="90c75-256">Returns the square root of the specified expression.</span></span> 

<span data-ttu-id="90c75-257">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-257">**Arguments**</span></span> 

<span data-ttu-id="90c75-258">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-258">`expression`: A `Double`.</span></span> 

<span data-ttu-id="90c75-259">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-259">**Return Value**</span></span> 

<span data-ttu-id="90c75-260">`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-260">A `Double`.</span></span> 

<span data-ttu-id="90c75-261">**示例** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="90c75-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="90c75-262">SQUARE(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-262">SQUARE(expression)</span></span>

<span data-ttu-id="90c75-263">返回指定表达式的平方。</span><span class="sxs-lookup"><span data-stu-id="90c75-263">Returns the square of the specified expression.</span></span> 

<span data-ttu-id="90c75-264">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-264">**Arguments**</span></span> 

<span data-ttu-id="90c75-265">`expression`：`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-265">`expression`: A `Double`.</span></span> 

<span data-ttu-id="90c75-266">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-266">**Return Value**</span></span> 

<span data-ttu-id="90c75-267">`Double`。</span><span class="sxs-lookup"><span data-stu-id="90c75-267">A `Double`.</span></span> 

<span data-ttu-id="90c75-268">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-268">**Example**</span></span> 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="90c75-269">TAN(expression)</span><span class="sxs-lookup"><span data-stu-id="90c75-269">TAN(expression)</span></span>

<span data-ttu-id="90c75-270">计算指定表达式的正切。</span><span class="sxs-lookup"><span data-stu-id="90c75-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="90c75-271">**参数**</span><span class="sxs-lookup"><span data-stu-id="90c75-271">**Arguments**</span></span> 

<span data-ttu-id="90c75-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="90c75-272">`expression`: `Double`</span></span> 

<span data-ttu-id="90c75-273">**返回值**</span><span class="sxs-lookup"><span data-stu-id="90c75-273">**Return Value**</span></span> 

`Double` 

<span data-ttu-id="90c75-274">**示例**</span><span class="sxs-lookup"><span data-stu-id="90c75-274">**Example**</span></span> 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="90c75-275">请参阅</span><span class="sxs-lookup"><span data-stu-id="90c75-275">See also</span></span>

<span data-ttu-id="90c75-276">有关 SqlClient 支持的数学函数的更多信息，请参见 SqlClient 提供程序清单中所指定的 SQL Server 版本的相应文档：</span><span class="sxs-lookup"><span data-stu-id="90c75-276">For more information about the mathematical functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>  

<span data-ttu-id="90c75-277">**SQL Server 2005:**[数学函数 (Transact SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="90c75-277">**SQL Server 2005:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))</span></span>  
<span data-ttu-id="90c75-278">**SQL Server 2008:**[数学函数 (Transact SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="90c75-278">**SQL Server 2008:** [Mathematical Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))</span></span>  
<span data-ttu-id="90c75-279">**SQL Server 2012 和更高版本：**[数学函数 (Transact SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="90c75-279">**SQL Server 2012 and later:** [Mathematical Functions (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)</span></span>   

- [<span data-ttu-id="90c75-280">用于实体框架函数的 SqlClient</span><span class="sxs-lookup"><span data-stu-id="90c75-280">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
