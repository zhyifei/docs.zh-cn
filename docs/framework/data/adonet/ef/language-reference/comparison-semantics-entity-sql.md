---
title: 比较语义 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: da7b8f662d10376abd649e674701b43b7b740a6f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251183"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="ead11-102">比较语义 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ead11-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="ead11-103">执行下列任一 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 运算符时都涉及类型实例的比较：</span><span class="sxs-lookup"><span data-stu-id="ead11-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="ead11-104">显式比较</span><span class="sxs-lookup"><span data-stu-id="ead11-104">Explicit comparison</span></span>  
 <span data-ttu-id="ead11-105">相等运算：</span><span class="sxs-lookup"><span data-stu-id="ead11-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="ead11-106">!=</span><span class="sxs-lookup"><span data-stu-id="ead11-106">!=</span></span>  
  
 <span data-ttu-id="ead11-107">排序运算：</span><span class="sxs-lookup"><span data-stu-id="ead11-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="ead11-108">判断是否可为 Null 的运算：</span><span class="sxs-lookup"><span data-stu-id="ead11-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="ead11-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="ead11-109">IS NULL</span></span>  
  
- <span data-ttu-id="ead11-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="ead11-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="ead11-111">显式区别</span><span class="sxs-lookup"><span data-stu-id="ead11-111">Explicit distinction</span></span>  
 <span data-ttu-id="ead11-112">相等区别：</span><span class="sxs-lookup"><span data-stu-id="ead11-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="ead11-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="ead11-113">DISTINCT</span></span>  
  
- <span data-ttu-id="ead11-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="ead11-114">GROUP BY</span></span>  
  
 <span data-ttu-id="ead11-115">排序区别：</span><span class="sxs-lookup"><span data-stu-id="ead11-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="ead11-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="ead11-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="ead11-117">隐式区别</span><span class="sxs-lookup"><span data-stu-id="ead11-117">Implicit distinction</span></span>  
 <span data-ttu-id="ead11-118">集运算和谓词（相等）：</span><span class="sxs-lookup"><span data-stu-id="ead11-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="ead11-119">UNION</span><span class="sxs-lookup"><span data-stu-id="ead11-119">UNION</span></span>  
  
- <span data-ttu-id="ead11-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="ead11-120">INTERSECT</span></span>  
  
- <span data-ttu-id="ead11-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="ead11-121">EXCEPT</span></span>  
  
- <span data-ttu-id="ead11-122">SET</span><span class="sxs-lookup"><span data-stu-id="ead11-122">SET</span></span>  
  
- <span data-ttu-id="ead11-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="ead11-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="ead11-124">项谓词（相等）：</span><span class="sxs-lookup"><span data-stu-id="ead11-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="ead11-125">IN</span><span class="sxs-lookup"><span data-stu-id="ead11-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="ead11-126">支持的组合</span><span class="sxs-lookup"><span data-stu-id="ead11-126">Supported Combinations</span></span>  
 <span data-ttu-id="ead11-127">下表说明了每种类型的比较运算符的所有受支持的组合：</span><span class="sxs-lookup"><span data-stu-id="ead11-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="ead11-128">类型</span><span class="sxs-lookup"><span data-stu-id="ead11-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="ead11-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="ead11-129">**!=**</span></span>|<span data-ttu-id="ead11-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="ead11-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="ead11-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="ead11-131">**DISTINCT**</span></span>|<span data-ttu-id="ead11-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="ead11-132">**UNION**</span></span><br /><br /> <span data-ttu-id="ead11-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="ead11-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="ead11-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="ead11-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="ead11-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="ead11-135">**SET**</span></span><br /><br /> <span data-ttu-id="ead11-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="ead11-136">**OVERLAPS**</span></span>|<span data-ttu-id="ead11-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="ead11-137">**IN**</span></span>|<span data-ttu-id="ead11-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="ead11-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="ead11-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="ead11-139">**>   >=**</span></span>|<span data-ttu-id="ead11-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="ead11-140">**ORDER BY**</span></span>|<span data-ttu-id="ead11-141">**为 NULL**</span><span class="sxs-lookup"><span data-stu-id="ead11-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="ead11-142">**不为 NULL**</span><span class="sxs-lookup"><span data-stu-id="ead11-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="ead11-143">实体类型</span><span class="sxs-lookup"><span data-stu-id="ead11-143">Entity type</span></span>|<span data-ttu-id="ead11-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="ead11-145">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="ead11-146">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="ead11-147">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="ead11-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="ead11-151">复杂类型</span><span class="sxs-lookup"><span data-stu-id="ead11-151">Complex type</span></span>|<span data-ttu-id="ead11-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="ead11-159">行</span><span class="sxs-lookup"><span data-stu-id="ead11-159">Row</span></span>|<span data-ttu-id="ead11-160">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="ead11-161">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="ead11-162">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="ead11-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-165">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="ead11-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="ead11-167">基元类型</span><span class="sxs-lookup"><span data-stu-id="ead11-167">Primitive type</span></span>|<span data-ttu-id="ead11-168">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="ead11-168">Provider-specific</span></span>|<span data-ttu-id="ead11-169">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="ead11-169">Provider-specific</span></span>|<span data-ttu-id="ead11-170">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="ead11-170">Provider-specific</span></span>|<span data-ttu-id="ead11-171">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="ead11-171">Provider-specific</span></span>|<span data-ttu-id="ead11-172">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="ead11-172">Provider-specific</span></span>|<span data-ttu-id="ead11-173">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="ead11-173">Provider-specific</span></span>|<span data-ttu-id="ead11-174">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="ead11-174">Provider-specific</span></span>|  
|<span data-ttu-id="ead11-175">多集</span><span class="sxs-lookup"><span data-stu-id="ead11-175">Multiset</span></span>|<span data-ttu-id="ead11-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="ead11-183">引用</span><span class="sxs-lookup"><span data-stu-id="ead11-183">Ref</span></span>|<span data-ttu-id="ead11-184">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="ead11-185">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="ead11-186">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="ead11-187">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="ead11-188">引发</span><span class="sxs-lookup"><span data-stu-id="ead11-188">Throw</span></span>|<span data-ttu-id="ead11-189">引发</span><span class="sxs-lookup"><span data-stu-id="ead11-189">Throw</span></span>|<span data-ttu-id="ead11-190">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="ead11-191">关联</span><span class="sxs-lookup"><span data-stu-id="ead11-191">Association</span></span><br /><br /> <span data-ttu-id="ead11-192">type</span><span class="sxs-lookup"><span data-stu-id="ead11-192">type</span></span>|<span data-ttu-id="ead11-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-194">引发</span><span class="sxs-lookup"><span data-stu-id="ead11-194">Throw</span></span>|<span data-ttu-id="ead11-195">引发</span><span class="sxs-lookup"><span data-stu-id="ead11-195">Throw</span></span>|<span data-ttu-id="ead11-196">引发</span><span class="sxs-lookup"><span data-stu-id="ead11-196">Throw</span></span>|<span data-ttu-id="ead11-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="ead11-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="ead11-200"><sup>1</sup>给定实体类型实例的引用将被隐式比较，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="ead11-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="ead11-201">不能将实体实例与显式引用进行比较。</span><span class="sxs-lookup"><span data-stu-id="ead11-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="ead11-202">如果试图这么做，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="ead11-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="ead11-203">例如，以下查询将引发异常：</span><span class="sxs-lookup"><span data-stu-id="ead11-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="ead11-204"><sup>2</sup>复杂类型的属性将在发送到存储区之前平展，因此它们可以比较（只要它们的所有属性都是可比较的）。</span><span class="sxs-lookup"><span data-stu-id="ead11-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="ead11-205">另请参阅<sup>4。</sup></span><span class="sxs-lookup"><span data-stu-id="ead11-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="ead11-206"><sup>3</sup>实体框架运行时检测不受支持的情况，并引发有意义的异常，而不参与提供程序/存储。</span><span class="sxs-lookup"><span data-stu-id="ead11-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="ead11-207"><sup>4</sup>尝试比较所有属性。</span><span class="sxs-lookup"><span data-stu-id="ead11-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="ead11-208">如果某个属性的类型不可比较，例如 text、ntext 或 image，则可能引发服务器异常。</span><span class="sxs-lookup"><span data-stu-id="ead11-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="ead11-209"><sup>5</sup>对引用的所有单个元素进行比较（这包括实体集名称和实体类型的所有键属性）。</span><span class="sxs-lookup"><span data-stu-id="ead11-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ead11-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="ead11-210">See also</span></span>

- [<span data-ttu-id="ead11-211">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="ead11-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
