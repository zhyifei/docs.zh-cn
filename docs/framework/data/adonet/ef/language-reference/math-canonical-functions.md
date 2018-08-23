---
title: 数学规范函数
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 0fc9f4942c3f76f139ab7e4400005f0bfe80204e
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754608"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="3c6d3-102">数学规范函数</span><span class="sxs-lookup"><span data-stu-id="3c6d3-102">Math Canonical Functions</span></span>

<span data-ttu-id="3c6d3-103">实体 SQL 包括以下数学规范函数：</span><span class="sxs-lookup"><span data-stu-id="3c6d3-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="3c6d3-104">Abs(value)</span><span class="sxs-lookup"><span data-stu-id="3c6d3-104">Abs(value)</span></span>

<span data-ttu-id="3c6d3-105">返回 `value` 的绝对值。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-105">Returns the absolute value of `value`.</span></span>

<span data-ttu-id="3c6d3-106">**参数**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-106">**Arguments**</span></span>

<span data-ttu-id="3c6d3-107">`Int16`， `Int32`， `Int64`， `Byte`， `Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="3c6d3-108">**返回值**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-108">**Return Value**</span></span>

<span data-ttu-id="3c6d3-109">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-109">The type of `value`.</span></span>

<span data-ttu-id="3c6d3-110">**示例**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-110">**Example**</span></span>

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="3c6d3-111">Ceiling(value)</span><span class="sxs-lookup"><span data-stu-id="3c6d3-111">Ceiling(value)</span></span>

<span data-ttu-id="3c6d3-112">返回不小于 `value` 的最小整数。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-112">Returns the smallest integer that is not less than `value`.</span></span>

<span data-ttu-id="3c6d3-113">**参数**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-113">**Arguments**</span></span>

<span data-ttu-id="3c6d3-114">一个`Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-114">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="3c6d3-115">**返回值**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-115">**Return Value**</span></span>

<span data-ttu-id="3c6d3-116">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-116">The type of `value`.</span></span>

<span data-ttu-id="3c6d3-117">**示例**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-117">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="3c6d3-118">Floor(value)</span><span class="sxs-lookup"><span data-stu-id="3c6d3-118">Floor(value)</span></span>

<span data-ttu-id="3c6d3-119">返回不大于 `value` 的最大整数。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-119">Returns the largest integer that is not greater than `value`.</span></span>

<span data-ttu-id="3c6d3-120">**参数**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-120">**Arguments**</span></span>

<span data-ttu-id="3c6d3-121">一个`Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-121">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="3c6d3-122">**返回值**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-122">**Return Value**</span></span>

<span data-ttu-id="3c6d3-123">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-123">The type of `value`.</span></span>

<span data-ttu-id="3c6d3-124">**示例**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-124">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="3c6d3-125">Power(值, 指数)</span><span class="sxs-lookup"><span data-stu-id="3c6d3-125">Power(value, exponent)</span></span>

<span data-ttu-id="3c6d3-126">返回对指定的 `value` 求指定的 `exponent` 幂次所得的结果。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

<span data-ttu-id="3c6d3-127">**参数**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-127">**Arguments**</span></span>

|  |  |
|--|--|
|`value` | <span data-ttu-id="3c6d3-128">`Int32, Int64, Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="3c6d3-129">`Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

<span data-ttu-id="3c6d3-130">**返回值**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-130">**Return Value**</span></span>

<span data-ttu-id="3c6d3-131">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-131">The type of `value`.</span></span>

<span data-ttu-id="3c6d3-132">**示例**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-132">**Example**</span></span>

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="3c6d3-133">Round(value)</span><span class="sxs-lookup"><span data-stu-id="3c6d3-133">Round(value)</span></span>

<span data-ttu-id="3c6d3-134">返回 `value` 的整数部分，舍入到最近的整数。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

<span data-ttu-id="3c6d3-135">**参数**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-135">**Arguments**</span></span>

<span data-ttu-id="3c6d3-136">一个`Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-136">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="3c6d3-137">**返回值**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-137">**Return Value**</span></span>

<span data-ttu-id="3c6d3-138">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-138">The type of `value`.</span></span>

<span data-ttu-id="3c6d3-139">**示例**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-139">**Example**</span></span>

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="3c6d3-140">Round(值, 位数)</span><span class="sxs-lookup"><span data-stu-id="3c6d3-140">Round(value, digits)</span></span>

<span data-ttu-id="3c6d3-141">返回 `value`，舍入到最近的指定 `digits`。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

<span data-ttu-id="3c6d3-142">**参数**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-142">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="3c6d3-143">`Double` 或 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-143">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="3c6d3-144">`Int16` 或 `Int32`。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-144">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="3c6d3-145">**返回值**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-145">**Return Value**</span></span>

<span data-ttu-id="3c6d3-146">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-146">The type of `value`.</span></span>

<span data-ttu-id="3c6d3-147">**示例**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-147">**Example**</span></span>

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="3c6d3-148">Truncate(值, 位数)</span><span class="sxs-lookup"><span data-stu-id="3c6d3-148">Truncate(value, digits)</span></span>

<span data-ttu-id="3c6d3-149">返回 `value`，截断至最近的指定 `digits`。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

<span data-ttu-id="3c6d3-150">**参数**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-150">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="3c6d3-151">`Double` 或 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-151">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="3c6d3-152">`Int16` 或 `Int32`。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-152">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="3c6d3-153">**返回值**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-153">**Return Value**</span></span>

<span data-ttu-id="3c6d3-154">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-154">The type of `value`.</span></span>

<span data-ttu-id="3c6d3-155">**示例**</span><span class="sxs-lookup"><span data-stu-id="3c6d3-155">**Example**</span></span>

`Truncate(748.58,1)`  
  
 <span data-ttu-id="3c6d3-156">如果提供 `null` 输入，则这些函数返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="3c6d3-157">Microsoft SQL 客户端托管提供程序中提供了等效功能。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="3c6d3-158">有关详细信息，请参阅[用于实体框架函数的 SqlClient](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="3c6d3-158">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c6d3-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c6d3-159">See Also</span></span>  
 [<span data-ttu-id="3c6d3-160">规范函数</span><span class="sxs-lookup"><span data-stu-id="3c6d3-160">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
