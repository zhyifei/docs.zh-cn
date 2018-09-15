---
title: 数学规范函数
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 0fc9f4942c3f76f139ab7e4400005f0bfe80204e
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2018
ms.locfileid: "45653182"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="b4bc1-102">数学规范函数</span><span class="sxs-lookup"><span data-stu-id="b4bc1-102">Math Canonical Functions</span></span>

<span data-ttu-id="b4bc1-103">实体 SQL 包括以下数学规范函数：</span><span class="sxs-lookup"><span data-stu-id="b4bc1-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="b4bc1-104">Abs(value)</span><span class="sxs-lookup"><span data-stu-id="b4bc1-104">Abs(value)</span></span>

<span data-ttu-id="b4bc1-105">返回 `value` 的绝对值。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-105">Returns the absolute value of `value`.</span></span>

<span data-ttu-id="b4bc1-106">**参数**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-106">**Arguments**</span></span>

<span data-ttu-id="b4bc1-107">`Int16`， `Int32`， `Int64`， `Byte`， `Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="b4bc1-108">**返回值**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-108">**Return Value**</span></span>

<span data-ttu-id="b4bc1-109">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-109">The type of `value`.</span></span>

<span data-ttu-id="b4bc1-110">**示例**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-110">**Example**</span></span>

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="b4bc1-111">Ceiling(value)</span><span class="sxs-lookup"><span data-stu-id="b4bc1-111">Ceiling(value)</span></span>

<span data-ttu-id="b4bc1-112">返回不小于 `value` 的最小整数。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-112">Returns the smallest integer that is not less than `value`.</span></span>

<span data-ttu-id="b4bc1-113">**参数**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-113">**Arguments**</span></span>

<span data-ttu-id="b4bc1-114">一个`Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-114">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="b4bc1-115">**返回值**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-115">**Return Value**</span></span>

<span data-ttu-id="b4bc1-116">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-116">The type of `value`.</span></span>

<span data-ttu-id="b4bc1-117">**示例**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-117">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="b4bc1-118">Floor(value)</span><span class="sxs-lookup"><span data-stu-id="b4bc1-118">Floor(value)</span></span>

<span data-ttu-id="b4bc1-119">返回不大于 `value` 的最大整数。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-119">Returns the largest integer that is not greater than `value`.</span></span>

<span data-ttu-id="b4bc1-120">**参数**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-120">**Arguments**</span></span>

<span data-ttu-id="b4bc1-121">一个`Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-121">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="b4bc1-122">**返回值**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-122">**Return Value**</span></span>

<span data-ttu-id="b4bc1-123">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-123">The type of `value`.</span></span>

<span data-ttu-id="b4bc1-124">**示例**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-124">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="b4bc1-125">Power(值, 指数)</span><span class="sxs-lookup"><span data-stu-id="b4bc1-125">Power(value, exponent)</span></span>

<span data-ttu-id="b4bc1-126">返回对指定的 `value` 求指定的 `exponent` 幂次所得的结果。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

<span data-ttu-id="b4bc1-127">**参数**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-127">**Arguments**</span></span>

|  |  |
|--|--|
|`value` | <span data-ttu-id="b4bc1-128">`Int32, Int64, Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="b4bc1-129">`Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

<span data-ttu-id="b4bc1-130">**返回值**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-130">**Return Value**</span></span>

<span data-ttu-id="b4bc1-131">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-131">The type of `value`.</span></span>

<span data-ttu-id="b4bc1-132">**示例**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-132">**Example**</span></span>

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="b4bc1-133">Round(value)</span><span class="sxs-lookup"><span data-stu-id="b4bc1-133">Round(value)</span></span>

<span data-ttu-id="b4bc1-134">返回 `value` 的整数部分，舍入到最近的整数。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

<span data-ttu-id="b4bc1-135">**参数**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-135">**Arguments**</span></span>

<span data-ttu-id="b4bc1-136">一个`Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-136">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="b4bc1-137">**返回值**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-137">**Return Value**</span></span>

<span data-ttu-id="b4bc1-138">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-138">The type of `value`.</span></span>

<span data-ttu-id="b4bc1-139">**示例**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-139">**Example**</span></span>

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="b4bc1-140">Round(值, 位数)</span><span class="sxs-lookup"><span data-stu-id="b4bc1-140">Round(value, digits)</span></span>

<span data-ttu-id="b4bc1-141">返回 `value`，舍入到最近的指定 `digits`。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

<span data-ttu-id="b4bc1-142">**参数**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-142">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="b4bc1-143">`Double` 或 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-143">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="b4bc1-144">`Int16` 或 `Int32`。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-144">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="b4bc1-145">**返回值**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-145">**Return Value**</span></span>

<span data-ttu-id="b4bc1-146">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-146">The type of `value`.</span></span>

<span data-ttu-id="b4bc1-147">**示例**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-147">**Example**</span></span>

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="b4bc1-148">Truncate(值, 位数)</span><span class="sxs-lookup"><span data-stu-id="b4bc1-148">Truncate(value, digits)</span></span>

<span data-ttu-id="b4bc1-149">返回 `value`，截断至最近的指定 `digits`。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

<span data-ttu-id="b4bc1-150">**参数**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-150">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="b4bc1-151">`Double` 或 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-151">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="b4bc1-152">`Int16` 或 `Int32`。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-152">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="b4bc1-153">**返回值**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-153">**Return Value**</span></span>

<span data-ttu-id="b4bc1-154">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-154">The type of `value`.</span></span>

<span data-ttu-id="b4bc1-155">**示例**</span><span class="sxs-lookup"><span data-stu-id="b4bc1-155">**Example**</span></span>

`Truncate(748.58,1)`  
  
 <span data-ttu-id="b4bc1-156">如果提供 `null` 输入，则这些函数返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="b4bc1-157">Microsoft SQL 客户端托管提供程序中提供了等效功能。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="b4bc1-158">有关详细信息，请参阅[用于实体框架函数的 SqlClient](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="b4bc1-158">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4bc1-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4bc1-159">See Also</span></span>  
 [<span data-ttu-id="b4bc1-160">规范函数</span><span class="sxs-lookup"><span data-stu-id="b4bc1-160">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
