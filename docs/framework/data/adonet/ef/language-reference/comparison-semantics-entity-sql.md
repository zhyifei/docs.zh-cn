---
title: 比较语义 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 8d7868b0166f0a18824ec25e6cdf639deec665ac
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833933"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="50d21-102">比较语义 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="50d21-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="50d21-103">执行下列任一 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 运算符时都涉及类型实例的比较：</span><span class="sxs-lookup"><span data-stu-id="50d21-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="50d21-104">显式比较</span><span class="sxs-lookup"><span data-stu-id="50d21-104">Explicit comparison</span></span>  
 <span data-ttu-id="50d21-105">相等运算：</span><span class="sxs-lookup"><span data-stu-id="50d21-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="50d21-106">!=</span><span class="sxs-lookup"><span data-stu-id="50d21-106">!=</span></span>  
  
 <span data-ttu-id="50d21-107">排序运算：</span><span class="sxs-lookup"><span data-stu-id="50d21-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="50d21-108">判断是否可为 Null 的运算：</span><span class="sxs-lookup"><span data-stu-id="50d21-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="50d21-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="50d21-109">IS NULL</span></span>  
  
- <span data-ttu-id="50d21-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="50d21-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="50d21-111">显式区别</span><span class="sxs-lookup"><span data-stu-id="50d21-111">Explicit distinction</span></span>  
 <span data-ttu-id="50d21-112">相等区别：</span><span class="sxs-lookup"><span data-stu-id="50d21-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="50d21-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="50d21-113">DISTINCT</span></span>  
  
- <span data-ttu-id="50d21-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="50d21-114">GROUP BY</span></span>  
  
 <span data-ttu-id="50d21-115">排序区别：</span><span class="sxs-lookup"><span data-stu-id="50d21-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="50d21-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="50d21-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="50d21-117">隐式区别</span><span class="sxs-lookup"><span data-stu-id="50d21-117">Implicit distinction</span></span>  
 <span data-ttu-id="50d21-118">集运算和谓词（相等）：</span><span class="sxs-lookup"><span data-stu-id="50d21-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="50d21-119">UNION</span><span class="sxs-lookup"><span data-stu-id="50d21-119">UNION</span></span>  
  
- <span data-ttu-id="50d21-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="50d21-120">INTERSECT</span></span>  
  
- <span data-ttu-id="50d21-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="50d21-121">EXCEPT</span></span>  
  
- <span data-ttu-id="50d21-122">SET</span><span class="sxs-lookup"><span data-stu-id="50d21-122">SET</span></span>  
  
- <span data-ttu-id="50d21-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="50d21-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="50d21-124">项谓词（相等）：</span><span class="sxs-lookup"><span data-stu-id="50d21-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="50d21-125">IN</span><span class="sxs-lookup"><span data-stu-id="50d21-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="50d21-126">支持的组合</span><span class="sxs-lookup"><span data-stu-id="50d21-126">Supported Combinations</span></span>  
 <span data-ttu-id="50d21-127">下表说明了每种类型的比较运算符的所有受支持的组合：</span><span class="sxs-lookup"><span data-stu-id="50d21-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="50d21-128">类型</span><span class="sxs-lookup"><span data-stu-id="50d21-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="50d21-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="50d21-129">**!=**</span></span>|<span data-ttu-id="50d21-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="50d21-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="50d21-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="50d21-131">**DISTINCT**</span></span>|<span data-ttu-id="50d21-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="50d21-132">**UNION**</span></span><br /><br /> <span data-ttu-id="50d21-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="50d21-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="50d21-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="50d21-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="50d21-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="50d21-135">**SET**</span></span><br /><br /> <span data-ttu-id="50d21-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="50d21-136">**OVERLAPS**</span></span>|<span data-ttu-id="50d21-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="50d21-137">**IN**</span></span>|<span data-ttu-id="50d21-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="50d21-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="50d21-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="50d21-139">**>   >=**</span></span>|<span data-ttu-id="50d21-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="50d21-140">**ORDER BY**</span></span>|<span data-ttu-id="50d21-141">**为 NULL**</span><span class="sxs-lookup"><span data-stu-id="50d21-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="50d21-142">**不为 NULL**</span><span class="sxs-lookup"><span data-stu-id="50d21-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="50d21-143">实体类型</span><span class="sxs-lookup"><span data-stu-id="50d21-143">Entity type</span></span>|<span data-ttu-id="50d21-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="50d21-145">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="50d21-146">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="50d21-147">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="50d21-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="50d21-151">复杂类型</span><span class="sxs-lookup"><span data-stu-id="50d21-151">Complex type</span></span>|<span data-ttu-id="50d21-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="50d21-159">行</span><span class="sxs-lookup"><span data-stu-id="50d21-159">Row</span></span>|<span data-ttu-id="50d21-160">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="50d21-161">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="50d21-162">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="50d21-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-165">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="50d21-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="50d21-167">基元类型</span><span class="sxs-lookup"><span data-stu-id="50d21-167">Primitive type</span></span>|<span data-ttu-id="50d21-168">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="50d21-168">Provider-specific</span></span>|<span data-ttu-id="50d21-169">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="50d21-169">Provider-specific</span></span>|<span data-ttu-id="50d21-170">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="50d21-170">Provider-specific</span></span>|<span data-ttu-id="50d21-171">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="50d21-171">Provider-specific</span></span>|<span data-ttu-id="50d21-172">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="50d21-172">Provider-specific</span></span>|<span data-ttu-id="50d21-173">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="50d21-173">Provider-specific</span></span>|<span data-ttu-id="50d21-174">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="50d21-174">Provider-specific</span></span>|  
|<span data-ttu-id="50d21-175">多集</span><span class="sxs-lookup"><span data-stu-id="50d21-175">Multiset</span></span>|<span data-ttu-id="50d21-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="50d21-183">引用</span><span class="sxs-lookup"><span data-stu-id="50d21-183">Ref</span></span>|<span data-ttu-id="50d21-184">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="50d21-185">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="50d21-186">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="50d21-187">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="50d21-188">引发</span><span class="sxs-lookup"><span data-stu-id="50d21-188">Throw</span></span>|<span data-ttu-id="50d21-189">引发</span><span class="sxs-lookup"><span data-stu-id="50d21-189">Throw</span></span>|<span data-ttu-id="50d21-190">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="50d21-191">关联</span><span class="sxs-lookup"><span data-stu-id="50d21-191">Association</span></span><br /><br /> <span data-ttu-id="50d21-192">type</span><span class="sxs-lookup"><span data-stu-id="50d21-192">type</span></span>|<span data-ttu-id="50d21-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-194">引发</span><span class="sxs-lookup"><span data-stu-id="50d21-194">Throw</span></span>|<span data-ttu-id="50d21-195">引发</span><span class="sxs-lookup"><span data-stu-id="50d21-195">Throw</span></span>|<span data-ttu-id="50d21-196">引发</span><span class="sxs-lookup"><span data-stu-id="50d21-196">Throw</span></span>|<span data-ttu-id="50d21-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="50d21-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="50d21-200"><sup>1</sup>给定实体类型实例的引用将被隐式比较，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="50d21-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="50d21-201">不能将实体实例与显式引用进行比较。</span><span class="sxs-lookup"><span data-stu-id="50d21-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="50d21-202">如果试图这么做，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="50d21-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="50d21-203">例如，以下查询将引发异常：</span><span class="sxs-lookup"><span data-stu-id="50d21-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="50d21-204"><sup>2</sup>复杂类型的属性将在发送到存储区之前平展，因此它们可以比较（只要它们的所有属性都是可比较的）。</span><span class="sxs-lookup"><span data-stu-id="50d21-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="50d21-205">另请参阅<sup>4。</sup></span><span class="sxs-lookup"><span data-stu-id="50d21-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="50d21-206"><sup>3</sup>实体框架运行时检测不受支持的情况，并引发有意义的异常，而不参与提供程序/存储。</span><span class="sxs-lookup"><span data-stu-id="50d21-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="50d21-207"><sup>4</sup>尝试比较所有属性。</span><span class="sxs-lookup"><span data-stu-id="50d21-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="50d21-208">如果某个属性的类型不可比较，例如 text、ntext 或 image，则可能引发服务器异常。</span><span class="sxs-lookup"><span data-stu-id="50d21-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="50d21-209"><sup>5</sup>对引用的所有单个元素进行比较（这包括实体集名称和实体类型的所有键属性）。</span><span class="sxs-lookup"><span data-stu-id="50d21-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50d21-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="50d21-210">See also</span></span>

- [<span data-ttu-id="50d21-211">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="50d21-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
