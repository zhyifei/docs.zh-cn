---
title: 比较语义 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 2184f86ee43f88b0c4cfc1b96e42e2486c17fe5f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="ef430-102">比较语义 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ef430-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="ef430-103">执行下列任一 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 运算符时都涉及类型实例的比较：</span><span class="sxs-lookup"><span data-stu-id="ef430-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="ef430-104">显式比较</span><span class="sxs-lookup"><span data-stu-id="ef430-104">Explicit comparison</span></span>  
 <span data-ttu-id="ef430-105">相等运算：</span><span class="sxs-lookup"><span data-stu-id="ef430-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="ef430-106">!=</span><span class="sxs-lookup"><span data-stu-id="ef430-106">!=</span></span>  
  
 <span data-ttu-id="ef430-107">排序运算：</span><span class="sxs-lookup"><span data-stu-id="ef430-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="ef430-108">判断是否可为 Null 的运算：</span><span class="sxs-lookup"><span data-stu-id="ef430-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="ef430-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="ef430-109">IS NULL</span></span>  
  
-   <span data-ttu-id="ef430-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="ef430-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="ef430-111">显式区别</span><span class="sxs-lookup"><span data-stu-id="ef430-111">Explicit distinction</span></span>  
 <span data-ttu-id="ef430-112">相等区别：</span><span class="sxs-lookup"><span data-stu-id="ef430-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="ef430-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="ef430-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="ef430-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="ef430-114">GROUP BY</span></span>  
  
 <span data-ttu-id="ef430-115">排序区别：</span><span class="sxs-lookup"><span data-stu-id="ef430-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="ef430-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="ef430-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="ef430-117">隐式区别</span><span class="sxs-lookup"><span data-stu-id="ef430-117">Implicit distinction</span></span>  
 <span data-ttu-id="ef430-118">集运算和谓词（相等）：</span><span class="sxs-lookup"><span data-stu-id="ef430-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="ef430-119">UNION</span><span class="sxs-lookup"><span data-stu-id="ef430-119">UNION</span></span>  
  
-   <span data-ttu-id="ef430-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="ef430-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="ef430-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="ef430-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="ef430-122">SET</span><span class="sxs-lookup"><span data-stu-id="ef430-122">SET</span></span>  
  
-   <span data-ttu-id="ef430-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="ef430-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="ef430-124">项谓词（相等）：</span><span class="sxs-lookup"><span data-stu-id="ef430-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="ef430-125">IN</span><span class="sxs-lookup"><span data-stu-id="ef430-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="ef430-126">支持的组合</span><span class="sxs-lookup"><span data-stu-id="ef430-126">Supported Combinations</span></span>  
 <span data-ttu-id="ef430-127">下表说明了每种类型的比较运算符的所有受支持的组合：</span><span class="sxs-lookup"><span data-stu-id="ef430-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="ef430-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="ef430-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="ef430-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="ef430-129">**!=**</span></span>|<span data-ttu-id="ef430-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="ef430-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="ef430-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="ef430-131">**DISTINCT**</span></span>|<span data-ttu-id="ef430-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="ef430-132">**UNION**</span></span><br /><br /> <span data-ttu-id="ef430-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="ef430-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="ef430-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="ef430-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="ef430-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="ef430-135">**SET**</span></span><br /><br /> <span data-ttu-id="ef430-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="ef430-136">**OVERLAPS**</span></span>|<span data-ttu-id="ef430-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="ef430-137">**IN**</span></span>|<span data-ttu-id="ef430-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="ef430-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="ef430-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="ef430-139">**>   >=**</span></span>|<span data-ttu-id="ef430-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="ef430-140">**ORDER BY**</span></span>|<span data-ttu-id="ef430-141">**为 NULL**</span><span class="sxs-lookup"><span data-stu-id="ef430-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="ef430-142">**不为 NULL**</span><span class="sxs-lookup"><span data-stu-id="ef430-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="ef430-143">实体类型</span><span class="sxs-lookup"><span data-stu-id="ef430-143">Entity type</span></span>|<span data-ttu-id="ef430-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="ef430-145">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="ef430-146">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="ef430-147">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="ef430-148">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-149">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="ef430-151">复杂类型</span><span class="sxs-lookup"><span data-stu-id="ef430-151">Complex type</span></span>|<span data-ttu-id="ef430-152">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-153">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-154">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-155">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-156">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-157">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-158">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="ef430-159">行</span><span class="sxs-lookup"><span data-stu-id="ef430-159">Row</span></span>|<span data-ttu-id="ef430-160">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="ef430-161">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="ef430-162">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="ef430-163">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-164">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-165">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="ef430-166">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="ef430-167">基元类型</span><span class="sxs-lookup"><span data-stu-id="ef430-167">Primitive type</span></span>|<span data-ttu-id="ef430-168">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="ef430-168">Provider-specific</span></span>|<span data-ttu-id="ef430-169">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="ef430-169">Provider-specific</span></span>|<span data-ttu-id="ef430-170">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="ef430-170">Provider-specific</span></span>|<span data-ttu-id="ef430-171">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="ef430-171">Provider-specific</span></span>|<span data-ttu-id="ef430-172">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="ef430-172">Provider-specific</span></span>|<span data-ttu-id="ef430-173">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="ef430-173">Provider-specific</span></span>|<span data-ttu-id="ef430-174">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="ef430-174">Provider-specific</span></span>|  
|<span data-ttu-id="ef430-175">多集</span><span class="sxs-lookup"><span data-stu-id="ef430-175">Multiset</span></span>|<span data-ttu-id="ef430-176">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-177">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-178">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-179">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-180">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-181">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-182">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="ef430-183">引用</span><span class="sxs-lookup"><span data-stu-id="ef430-183">Ref</span></span>|<span data-ttu-id="ef430-184">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="ef430-185">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="ef430-186">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="ef430-187">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="ef430-188">引发</span><span class="sxs-lookup"><span data-stu-id="ef430-188">Throw</span></span>|<span data-ttu-id="ef430-189">引发</span><span class="sxs-lookup"><span data-stu-id="ef430-189">Throw</span></span>|<span data-ttu-id="ef430-190">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="ef430-191">关联</span><span class="sxs-lookup"><span data-stu-id="ef430-191">Association</span></span><br /><br /> <span data-ttu-id="ef430-192">类型</span><span class="sxs-lookup"><span data-stu-id="ef430-192">type</span></span>|<span data-ttu-id="ef430-193">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-194">引发</span><span class="sxs-lookup"><span data-stu-id="ef430-194">Throw</span></span>|<span data-ttu-id="ef430-195">引发</span><span class="sxs-lookup"><span data-stu-id="ef430-195">Throw</span></span>|<span data-ttu-id="ef430-196">引发</span><span class="sxs-lookup"><span data-stu-id="ef430-196">Throw</span></span>|<span data-ttu-id="ef430-197">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-198">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="ef430-199">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="ef430-200"><sup>1</sup>隐式比较给定的实体类型实例的引用，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="ef430-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="ef430-201">不能将实体实例与显式引用进行比较。</span><span class="sxs-lookup"><span data-stu-id="ef430-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="ef430-202">如果试图这么做，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="ef430-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="ef430-203">例如，以下查询将引发异常：</span><span class="sxs-lookup"><span data-stu-id="ef430-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="ef430-204"><sup>2</sup>复杂类型的属性被转换为扁平发送到应用商店中，因此它们变得可比较 （只要其所有属性都是可比较的） 之前。</span><span class="sxs-lookup"><span data-stu-id="ef430-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="ef430-205">另请参阅<sup>4。</sup></span><span class="sxs-lookup"><span data-stu-id="ef430-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="ef430-206"><sup>3</sup>实体框架运行时检测到不受支持的情况下，并在不牵扯提供程序/存储的情况下引发有意义的异常。</span><span class="sxs-lookup"><span data-stu-id="ef430-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="ef430-207"><sup>4</sup>尝试比较所有属性。</span><span class="sxs-lookup"><span data-stu-id="ef430-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="ef430-208">如果某个属性的类型不可比较，例如 text、ntext 或 image，则可能引发服务器异常。</span><span class="sxs-lookup"><span data-stu-id="ef430-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="ef430-209"><sup>5</sup>所有单个元素的引用进行比较 （包括实体集名称和实体类型的所有键属性）。</span><span class="sxs-lookup"><span data-stu-id="ef430-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef430-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef430-210">See Also</span></span>  
 [<span data-ttu-id="ef430-211">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="ef430-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
