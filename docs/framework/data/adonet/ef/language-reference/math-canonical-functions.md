---
title: 数学规范函数
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 0fc9f4942c3f76f139ab7e4400005f0bfe80204e
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "45969699"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="5c442-102">数学规范函数</span><span class="sxs-lookup"><span data-stu-id="5c442-102">Math Canonical Functions</span></span>

<span data-ttu-id="5c442-103">实体 SQL 包括以下数学规范函数：</span><span class="sxs-lookup"><span data-stu-id="5c442-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="5c442-104">Abs(value)</span><span class="sxs-lookup"><span data-stu-id="5c442-104">Abs(value)</span></span>

<span data-ttu-id="5c442-105">返回 `value` 的绝对值。</span><span class="sxs-lookup"><span data-stu-id="5c442-105">Returns the absolute value of `value`.</span></span>

<span data-ttu-id="5c442-106">**参数**</span><span class="sxs-lookup"><span data-stu-id="5c442-106">**Arguments**</span></span>

<span data-ttu-id="5c442-107">`Int16`， `Int32`， `Int64`， `Byte`， `Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="5c442-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="5c442-108">**返回值**</span><span class="sxs-lookup"><span data-stu-id="5c442-108">**Return Value**</span></span>

<span data-ttu-id="5c442-109">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="5c442-109">The type of `value`.</span></span>

<span data-ttu-id="5c442-110">**示例**</span><span class="sxs-lookup"><span data-stu-id="5c442-110">**Example**</span></span>

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="5c442-111">Ceiling(value)</span><span class="sxs-lookup"><span data-stu-id="5c442-111">Ceiling(value)</span></span>

<span data-ttu-id="5c442-112">返回不小于 `value` 的最小整数。</span><span class="sxs-lookup"><span data-stu-id="5c442-112">Returns the smallest integer that is not less than `value`.</span></span>

<span data-ttu-id="5c442-113">**参数**</span><span class="sxs-lookup"><span data-stu-id="5c442-113">**Arguments**</span></span>

<span data-ttu-id="5c442-114">一个`Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="5c442-114">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="5c442-115">**返回值**</span><span class="sxs-lookup"><span data-stu-id="5c442-115">**Return Value**</span></span>

<span data-ttu-id="5c442-116">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="5c442-116">The type of `value`.</span></span>

<span data-ttu-id="5c442-117">**示例**</span><span class="sxs-lookup"><span data-stu-id="5c442-117">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="5c442-118">Floor(value)</span><span class="sxs-lookup"><span data-stu-id="5c442-118">Floor(value)</span></span>

<span data-ttu-id="5c442-119">返回不大于 `value` 的最大整数。</span><span class="sxs-lookup"><span data-stu-id="5c442-119">Returns the largest integer that is not greater than `value`.</span></span>

<span data-ttu-id="5c442-120">**参数**</span><span class="sxs-lookup"><span data-stu-id="5c442-120">**Arguments**</span></span>

<span data-ttu-id="5c442-121">一个`Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="5c442-121">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="5c442-122">**返回值**</span><span class="sxs-lookup"><span data-stu-id="5c442-122">**Return Value**</span></span>

<span data-ttu-id="5c442-123">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="5c442-123">The type of `value`.</span></span>

<span data-ttu-id="5c442-124">**示例**</span><span class="sxs-lookup"><span data-stu-id="5c442-124">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="5c442-125">Power(值, 指数)</span><span class="sxs-lookup"><span data-stu-id="5c442-125">Power(value, exponent)</span></span>

<span data-ttu-id="5c442-126">返回对指定的 `value` 求指定的 `exponent` 幂次所得的结果。</span><span class="sxs-lookup"><span data-stu-id="5c442-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

<span data-ttu-id="5c442-127">**参数**</span><span class="sxs-lookup"><span data-stu-id="5c442-127">**Arguments**</span></span>

|  |  |
|--|--|
|`value` | <span data-ttu-id="5c442-128">`Int32, Int64, Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="5c442-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="5c442-129">`Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="5c442-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

<span data-ttu-id="5c442-130">**返回值**</span><span class="sxs-lookup"><span data-stu-id="5c442-130">**Return Value**</span></span>

<span data-ttu-id="5c442-131">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="5c442-131">The type of `value`.</span></span>

<span data-ttu-id="5c442-132">**示例**</span><span class="sxs-lookup"><span data-stu-id="5c442-132">**Example**</span></span>

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="5c442-133">Round(value)</span><span class="sxs-lookup"><span data-stu-id="5c442-133">Round(value)</span></span>

<span data-ttu-id="5c442-134">返回 `value` 的整数部分，舍入到最近的整数。</span><span class="sxs-lookup"><span data-stu-id="5c442-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

<span data-ttu-id="5c442-135">**参数**</span><span class="sxs-lookup"><span data-stu-id="5c442-135">**Arguments**</span></span>

<span data-ttu-id="5c442-136">一个`Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="5c442-136">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="5c442-137">**返回值**</span><span class="sxs-lookup"><span data-stu-id="5c442-137">**Return Value**</span></span>

<span data-ttu-id="5c442-138">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="5c442-138">The type of `value`.</span></span>

<span data-ttu-id="5c442-139">**示例**</span><span class="sxs-lookup"><span data-stu-id="5c442-139">**Example**</span></span>

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="5c442-140">Round(值, 位数)</span><span class="sxs-lookup"><span data-stu-id="5c442-140">Round(value, digits)</span></span>

<span data-ttu-id="5c442-141">返回 `value`，舍入到最近的指定 `digits`。</span><span class="sxs-lookup"><span data-stu-id="5c442-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

<span data-ttu-id="5c442-142">**参数**</span><span class="sxs-lookup"><span data-stu-id="5c442-142">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="5c442-143">`Double` 或 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="5c442-143">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="5c442-144">`Int16` 或 `Int32`。</span><span class="sxs-lookup"><span data-stu-id="5c442-144">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="5c442-145">**返回值**</span><span class="sxs-lookup"><span data-stu-id="5c442-145">**Return Value**</span></span>

<span data-ttu-id="5c442-146">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="5c442-146">The type of `value`.</span></span>

<span data-ttu-id="5c442-147">**示例**</span><span class="sxs-lookup"><span data-stu-id="5c442-147">**Example**</span></span>

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="5c442-148">Truncate(值, 位数)</span><span class="sxs-lookup"><span data-stu-id="5c442-148">Truncate(value, digits)</span></span>

<span data-ttu-id="5c442-149">返回 `value`，截断至最近的指定 `digits`。</span><span class="sxs-lookup"><span data-stu-id="5c442-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

<span data-ttu-id="5c442-150">**参数**</span><span class="sxs-lookup"><span data-stu-id="5c442-150">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="5c442-151">`Double` 或 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="5c442-151">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="5c442-152">`Int16` 或 `Int32`。</span><span class="sxs-lookup"><span data-stu-id="5c442-152">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="5c442-153">**返回值**</span><span class="sxs-lookup"><span data-stu-id="5c442-153">**Return Value**</span></span>

<span data-ttu-id="5c442-154">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="5c442-154">The type of `value`.</span></span>

<span data-ttu-id="5c442-155">**示例**</span><span class="sxs-lookup"><span data-stu-id="5c442-155">**Example**</span></span>

`Truncate(748.58,1)`  
  
 <span data-ttu-id="5c442-156">如果提供 `null` 输入，则这些函数返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="5c442-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="5c442-157">Microsoft SQL 客户端托管提供程序中提供了等效功能。</span><span class="sxs-lookup"><span data-stu-id="5c442-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="5c442-158">有关详细信息，请参阅[用于实体框架函数的 SqlClient](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="5c442-158">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c442-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c442-159">See Also</span></span>  
 [<span data-ttu-id="5c442-160">规范函数</span><span class="sxs-lookup"><span data-stu-id="5c442-160">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
