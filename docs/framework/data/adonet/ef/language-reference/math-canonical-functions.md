---
title: 数学规范函数
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: f575785bb198251ef50ba3563e736946253c9526
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228765"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="a19b0-102">数学规范函数</span><span class="sxs-lookup"><span data-stu-id="a19b0-102">Math Canonical Functions</span></span>

<span data-ttu-id="a19b0-103">实体 SQL 包括以下数学规范函数：</span><span class="sxs-lookup"><span data-stu-id="a19b0-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="a19b0-104">Abs(value)</span><span class="sxs-lookup"><span data-stu-id="a19b0-104">Abs(value)</span></span>

<span data-ttu-id="a19b0-105">返回 `value` 的绝对值。</span><span class="sxs-lookup"><span data-stu-id="a19b0-105">Returns the absolute value of `value`.</span></span>

**<span data-ttu-id="a19b0-106">自变量</span><span class="sxs-lookup"><span data-stu-id="a19b0-106">Arguments</span></span>**

<span data-ttu-id="a19b0-107">`Int16`， `Int32`， `Int64`， `Byte`， `Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="a19b0-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

**<span data-ttu-id="a19b0-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a19b0-108">Return Value</span></span>**

<span data-ttu-id="a19b0-109">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="a19b0-109">The type of `value`.</span></span>

**<span data-ttu-id="a19b0-110">示例</span><span class="sxs-lookup"><span data-stu-id="a19b0-110">Example</span></span>**

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="a19b0-111">Ceiling(value)</span><span class="sxs-lookup"><span data-stu-id="a19b0-111">Ceiling(value)</span></span>

<span data-ttu-id="a19b0-112">返回不小于 `value` 的最小整数。</span><span class="sxs-lookup"><span data-stu-id="a19b0-112">Returns the smallest integer that is not less than `value`.</span></span>

**<span data-ttu-id="a19b0-113">自变量</span><span class="sxs-lookup"><span data-stu-id="a19b0-113">Arguments</span></span>**

<span data-ttu-id="a19b0-114">一个`Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="a19b0-114">A `Single`, `Double`, and `Decimal`.</span></span>

**<span data-ttu-id="a19b0-115">返回值</span><span class="sxs-lookup"><span data-stu-id="a19b0-115">Return Value</span></span>**

<span data-ttu-id="a19b0-116">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="a19b0-116">The type of `value`.</span></span>

**<span data-ttu-id="a19b0-117">示例</span><span class="sxs-lookup"><span data-stu-id="a19b0-117">Example</span></span>**

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="a19b0-118">Floor(value)</span><span class="sxs-lookup"><span data-stu-id="a19b0-118">Floor(value)</span></span>

<span data-ttu-id="a19b0-119">返回不大于 `value` 的最大整数。</span><span class="sxs-lookup"><span data-stu-id="a19b0-119">Returns the largest integer that is not greater than `value`.</span></span>

**<span data-ttu-id="a19b0-120">自变量</span><span class="sxs-lookup"><span data-stu-id="a19b0-120">Arguments</span></span>**

<span data-ttu-id="a19b0-121">一个`Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="a19b0-121">A `Single`, `Double`, and `Decimal`.</span></span>

**<span data-ttu-id="a19b0-122">返回值</span><span class="sxs-lookup"><span data-stu-id="a19b0-122">Return Value</span></span>**

<span data-ttu-id="a19b0-123">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="a19b0-123">The type of `value`.</span></span>

**<span data-ttu-id="a19b0-124">示例</span><span class="sxs-lookup"><span data-stu-id="a19b0-124">Example</span></span>**

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="a19b0-125">Power(值, 指数)</span><span class="sxs-lookup"><span data-stu-id="a19b0-125">Power(value, exponent)</span></span>

<span data-ttu-id="a19b0-126">返回对指定的 `value` 求指定的 `exponent` 幂次所得的结果。</span><span class="sxs-lookup"><span data-stu-id="a19b0-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

**<span data-ttu-id="a19b0-127">自变量</span><span class="sxs-lookup"><span data-stu-id="a19b0-127">Arguments</span></span>**

|  |  |
|--|--|
|`value` | <span data-ttu-id="a19b0-128">`Int32, Int64, Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="a19b0-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="a19b0-129">`Int64`， `Double`，或`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="a19b0-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

**<span data-ttu-id="a19b0-130">返回值</span><span class="sxs-lookup"><span data-stu-id="a19b0-130">Return Value</span></span>**

<span data-ttu-id="a19b0-131">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="a19b0-131">The type of `value`.</span></span>

**<span data-ttu-id="a19b0-132">示例</span><span class="sxs-lookup"><span data-stu-id="a19b0-132">Example</span></span>**

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="a19b0-133">Round(value)</span><span class="sxs-lookup"><span data-stu-id="a19b0-133">Round(value)</span></span>

<span data-ttu-id="a19b0-134">返回 `value` 的整数部分，舍入到最近的整数。</span><span class="sxs-lookup"><span data-stu-id="a19b0-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

**<span data-ttu-id="a19b0-135">自变量</span><span class="sxs-lookup"><span data-stu-id="a19b0-135">Arguments</span></span>**

<span data-ttu-id="a19b0-136">一个`Single`， `Double`，和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="a19b0-136">A `Single`, `Double`, and `Decimal`.</span></span>

**<span data-ttu-id="a19b0-137">返回值</span><span class="sxs-lookup"><span data-stu-id="a19b0-137">Return Value</span></span>**

<span data-ttu-id="a19b0-138">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="a19b0-138">The type of `value`.</span></span>

**<span data-ttu-id="a19b0-139">示例</span><span class="sxs-lookup"><span data-stu-id="a19b0-139">Example</span></span>**

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="a19b0-140">Round(值, 位数)</span><span class="sxs-lookup"><span data-stu-id="a19b0-140">Round(value, digits)</span></span>

<span data-ttu-id="a19b0-141">返回 `value`，舍入到最近的指定 `digits`。</span><span class="sxs-lookup"><span data-stu-id="a19b0-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

**<span data-ttu-id="a19b0-142">自变量</span><span class="sxs-lookup"><span data-stu-id="a19b0-142">Arguments</span></span>**

|  |  |
|--|--|
|`value`|`Double` <span data-ttu-id="a19b0-143">或 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="a19b0-143">or `Decimal`.</span></span>|
|`digits`|`Int16` <span data-ttu-id="a19b0-144">或 `Int32`。</span><span class="sxs-lookup"><span data-stu-id="a19b0-144">or `Int32`.</span></span>|

**<span data-ttu-id="a19b0-145">返回值</span><span class="sxs-lookup"><span data-stu-id="a19b0-145">Return Value</span></span>**

<span data-ttu-id="a19b0-146">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="a19b0-146">The type of `value`.</span></span>

**<span data-ttu-id="a19b0-147">示例</span><span class="sxs-lookup"><span data-stu-id="a19b0-147">Example</span></span>**

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="a19b0-148">Truncate(值, 位数)</span><span class="sxs-lookup"><span data-stu-id="a19b0-148">Truncate(value, digits)</span></span>

<span data-ttu-id="a19b0-149">返回 `value`，截断至最近的指定 `digits`。</span><span class="sxs-lookup"><span data-stu-id="a19b0-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

**<span data-ttu-id="a19b0-150">自变量</span><span class="sxs-lookup"><span data-stu-id="a19b0-150">Arguments</span></span>**

|  |  |
|--|--|
|`value`|`Double` <span data-ttu-id="a19b0-151">或 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="a19b0-151">or `Decimal`.</span></span>|
|`digits`|`Int16` <span data-ttu-id="a19b0-152">或 `Int32`。</span><span class="sxs-lookup"><span data-stu-id="a19b0-152">or `Int32`.</span></span>|

**<span data-ttu-id="a19b0-153">返回值</span><span class="sxs-lookup"><span data-stu-id="a19b0-153">Return Value</span></span>**

<span data-ttu-id="a19b0-154">`value` 的类型。</span><span class="sxs-lookup"><span data-stu-id="a19b0-154">The type of `value`.</span></span>

**<span data-ttu-id="a19b0-155">示例</span><span class="sxs-lookup"><span data-stu-id="a19b0-155">Example</span></span>**

`Truncate(748.58,1)`  
  
 <span data-ttu-id="a19b0-156">如果提供 `null` 输入，则这些函数返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="a19b0-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="a19b0-157">Microsoft SQL 客户端托管提供程序中提供了等效功能。</span><span class="sxs-lookup"><span data-stu-id="a19b0-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="a19b0-158">有关详细信息，请参阅[用于实体框架函数的 SqlClient](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="a19b0-158">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a19b0-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="a19b0-159">See also</span></span>

- [<span data-ttu-id="a19b0-160">规范函数</span><span class="sxs-lookup"><span data-stu-id="a19b0-160">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
