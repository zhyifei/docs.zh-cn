---
title: 比较语义 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 57d81d4b581df76a4382ad5e1d72fe8250b10d43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150449"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="57064-102">比较语义 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="57064-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="57064-103">执行下列任一 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 运算符时都涉及类型实例的比较：</span><span class="sxs-lookup"><span data-stu-id="57064-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="57064-104">显式比较</span><span class="sxs-lookup"><span data-stu-id="57064-104">Explicit comparison</span></span>  
 <span data-ttu-id="57064-105">相等运算：</span><span class="sxs-lookup"><span data-stu-id="57064-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="57064-106">!=</span><span class="sxs-lookup"><span data-stu-id="57064-106">!=</span></span>  
  
 <span data-ttu-id="57064-107">排序运算：</span><span class="sxs-lookup"><span data-stu-id="57064-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="57064-108">判断是否可为 Null 的运算：</span><span class="sxs-lookup"><span data-stu-id="57064-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="57064-109">为 NULL</span><span class="sxs-lookup"><span data-stu-id="57064-109">IS NULL</span></span>  
  
- <span data-ttu-id="57064-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="57064-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="57064-111">显式区别</span><span class="sxs-lookup"><span data-stu-id="57064-111">Explicit distinction</span></span>  
 <span data-ttu-id="57064-112">相等区别：</span><span class="sxs-lookup"><span data-stu-id="57064-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="57064-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="57064-113">DISTINCT</span></span>  
  
- <span data-ttu-id="57064-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="57064-114">GROUP BY</span></span>  
  
 <span data-ttu-id="57064-115">排序区别：</span><span class="sxs-lookup"><span data-stu-id="57064-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="57064-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="57064-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="57064-117">隐式区别</span><span class="sxs-lookup"><span data-stu-id="57064-117">Implicit distinction</span></span>  
 <span data-ttu-id="57064-118">集运算和谓词（相等）：</span><span class="sxs-lookup"><span data-stu-id="57064-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="57064-119">UNION</span><span class="sxs-lookup"><span data-stu-id="57064-119">UNION</span></span>  
  
- <span data-ttu-id="57064-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="57064-120">INTERSECT</span></span>  
  
- <span data-ttu-id="57064-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="57064-121">EXCEPT</span></span>  
  
- <span data-ttu-id="57064-122">SET</span><span class="sxs-lookup"><span data-stu-id="57064-122">SET</span></span>  
  
- <span data-ttu-id="57064-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="57064-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="57064-124">项谓词（相等）：</span><span class="sxs-lookup"><span data-stu-id="57064-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="57064-125">IN</span><span class="sxs-lookup"><span data-stu-id="57064-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="57064-126">支持的组合</span><span class="sxs-lookup"><span data-stu-id="57064-126">Supported Combinations</span></span>  
 <span data-ttu-id="57064-127">下表说明了每种类型的比较运算符的所有受支持的组合：</span><span class="sxs-lookup"><span data-stu-id="57064-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="57064-128">**类型**</span><span class="sxs-lookup"><span data-stu-id="57064-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="57064-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="57064-129">**!=**</span></span>|<span data-ttu-id="57064-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="57064-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="57064-131">**不同**</span><span class="sxs-lookup"><span data-stu-id="57064-131">**DISTINCT**</span></span>|<span data-ttu-id="57064-132">**联盟**</span><span class="sxs-lookup"><span data-stu-id="57064-132">**UNION**</span></span><br /><br /> <span data-ttu-id="57064-133">**相交**</span><span class="sxs-lookup"><span data-stu-id="57064-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="57064-134">**除了**</span><span class="sxs-lookup"><span data-stu-id="57064-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="57064-135">**设置**</span><span class="sxs-lookup"><span data-stu-id="57064-135">**SET**</span></span><br /><br /> <span data-ttu-id="57064-136">**重叠**</span><span class="sxs-lookup"><span data-stu-id="57064-136">**OVERLAPS**</span></span>|<span data-ttu-id="57064-137">**在**</span><span class="sxs-lookup"><span data-stu-id="57064-137">**IN**</span></span>|<span data-ttu-id="57064-138">**<<|**</span><span class="sxs-lookup"><span data-stu-id="57064-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="57064-139">**>>|**</span><span class="sxs-lookup"><span data-stu-id="57064-139">**>   >=**</span></span>|<span data-ttu-id="57064-140">**按**</span><span class="sxs-lookup"><span data-stu-id="57064-140">**ORDER BY**</span></span>|<span data-ttu-id="57064-141">**为空**</span><span class="sxs-lookup"><span data-stu-id="57064-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="57064-142">**不为空**</span><span class="sxs-lookup"><span data-stu-id="57064-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="57064-143">实体类型</span><span class="sxs-lookup"><span data-stu-id="57064-143">Entity type</span></span>|<span data-ttu-id="57064-144">参考<sup>文献 1</sup></span><span class="sxs-lookup"><span data-stu-id="57064-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="57064-145">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="57064-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="57064-146">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="57064-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="57064-147">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="57064-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="57064-148">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-149">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-150">参考<sup>文献 1</sup></span><span class="sxs-lookup"><span data-stu-id="57064-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="57064-151">复杂类型</span><span class="sxs-lookup"><span data-stu-id="57064-151">Complex type</span></span>|<span data-ttu-id="57064-152">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-153">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-154">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-155">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-156">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-157">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-158">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="57064-159">行</span><span class="sxs-lookup"><span data-stu-id="57064-159">Row</span></span>|<span data-ttu-id="57064-160">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="57064-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="57064-161">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="57064-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="57064-162">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="57064-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="57064-163">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-164">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-165">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="57064-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="57064-166">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="57064-167">基元类型</span><span class="sxs-lookup"><span data-stu-id="57064-167">Primitive type</span></span>|<span data-ttu-id="57064-168">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="57064-168">Provider-specific</span></span>|<span data-ttu-id="57064-169">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="57064-169">Provider-specific</span></span>|<span data-ttu-id="57064-170">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="57064-170">Provider-specific</span></span>|<span data-ttu-id="57064-171">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="57064-171">Provider-specific</span></span>|<span data-ttu-id="57064-172">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="57064-172">Provider-specific</span></span>|<span data-ttu-id="57064-173">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="57064-173">Provider-specific</span></span>|<span data-ttu-id="57064-174">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="57064-174">Provider-specific</span></span>|  
|<span data-ttu-id="57064-175">多集</span><span class="sxs-lookup"><span data-stu-id="57064-175">Multiset</span></span>|<span data-ttu-id="57064-176">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-177">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-178">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-179">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-180">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-181">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-182">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="57064-183">引用</span><span class="sxs-lookup"><span data-stu-id="57064-183">Ref</span></span>|<span data-ttu-id="57064-184">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="57064-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="57064-185">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="57064-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="57064-186">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="57064-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="57064-187">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="57064-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="57064-188">Throw</span><span class="sxs-lookup"><span data-stu-id="57064-188">Throw</span></span>|<span data-ttu-id="57064-189">Throw</span><span class="sxs-lookup"><span data-stu-id="57064-189">Throw</span></span>|<span data-ttu-id="57064-190">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="57064-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="57064-191">关联</span><span class="sxs-lookup"><span data-stu-id="57064-191">Association</span></span><br /><br /> <span data-ttu-id="57064-192">type</span><span class="sxs-lookup"><span data-stu-id="57064-192">type</span></span>|<span data-ttu-id="57064-193">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-194">Throw</span><span class="sxs-lookup"><span data-stu-id="57064-194">Throw</span></span>|<span data-ttu-id="57064-195">Throw</span><span class="sxs-lookup"><span data-stu-id="57064-195">Throw</span></span>|<span data-ttu-id="57064-196">Throw</span><span class="sxs-lookup"><span data-stu-id="57064-196">Throw</span></span>|<span data-ttu-id="57064-197">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-198">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="57064-199">投掷<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="57064-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="57064-200"><sup>1</sup>隐式比较给定实体类型实例的引用，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="57064-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="57064-201">不能将实体实例与显式引用进行比较。</span><span class="sxs-lookup"><span data-stu-id="57064-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="57064-202">如果试图这么做，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="57064-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="57064-203">例如，以下查询将引发异常：</span><span class="sxs-lookup"><span data-stu-id="57064-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="57064-204"><sup>2</sup>复杂类型的属性在发送到存储之前被拼合，因此它们变得可比较（只要它们的所有属性都是可比的）。</span><span class="sxs-lookup"><span data-stu-id="57064-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="57064-205">另请参阅<sup>4。</sup></span><span class="sxs-lookup"><span data-stu-id="57064-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="57064-206"><sup>3</sup>实体框架运行时检测不受支持的情况，并在不雇用提供程序/存储的情况下引发有意义的异常。</span><span class="sxs-lookup"><span data-stu-id="57064-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="57064-207"><sup>4</sup>尝试比较所有属性。</span><span class="sxs-lookup"><span data-stu-id="57064-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="57064-208">如果某个属性的类型不可比较，例如 text、ntext 或 image，则可能引发服务器异常。</span><span class="sxs-lookup"><span data-stu-id="57064-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="57064-209"><sup>5</sup>比较引用的所有单个元素（这包括实体集名称和实体类型的所有键属性）。</span><span class="sxs-lookup"><span data-stu-id="57064-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57064-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57064-210">See also</span></span>

- [<span data-ttu-id="57064-211">Entity SQL 概述</span><span class="sxs-lookup"><span data-stu-id="57064-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
