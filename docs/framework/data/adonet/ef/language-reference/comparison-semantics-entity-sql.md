---
title: "比较语义 (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2835d2064f1845b55dd3a33abb086c5af0fb9e6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="84b8a-102">比较语义 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="84b8a-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="84b8a-103">执行下列任一 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 运算符时都涉及类型实例的比较：</span><span class="sxs-lookup"><span data-stu-id="84b8a-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="84b8a-104">显式比较</span><span class="sxs-lookup"><span data-stu-id="84b8a-104">Explicit comparison</span></span>  
 <span data-ttu-id="84b8a-105">相等运算：</span><span class="sxs-lookup"><span data-stu-id="84b8a-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="84b8a-106">!=</span><span class="sxs-lookup"><span data-stu-id="84b8a-106">!=</span></span>  
  
 <span data-ttu-id="84b8a-107">排序运算：</span><span class="sxs-lookup"><span data-stu-id="84b8a-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   >  
  
-   \>=  
  
 <span data-ttu-id="84b8a-108">判断是否可为 Null 的运算：</span><span class="sxs-lookup"><span data-stu-id="84b8a-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="84b8a-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="84b8a-109">IS NULL</span></span>  
  
-   <span data-ttu-id="84b8a-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="84b8a-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="84b8a-111">显式区别</span><span class="sxs-lookup"><span data-stu-id="84b8a-111">Explicit distinction</span></span>  
 <span data-ttu-id="84b8a-112">相等区别：</span><span class="sxs-lookup"><span data-stu-id="84b8a-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="84b8a-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="84b8a-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="84b8a-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="84b8a-114">GROUP BY</span></span>  
  
 <span data-ttu-id="84b8a-115">排序区别：</span><span class="sxs-lookup"><span data-stu-id="84b8a-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="84b8a-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="84b8a-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="84b8a-117">隐式区别</span><span class="sxs-lookup"><span data-stu-id="84b8a-117">Implicit distinction</span></span>  
 <span data-ttu-id="84b8a-118">集运算和谓词（相等）：</span><span class="sxs-lookup"><span data-stu-id="84b8a-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="84b8a-119">UNION</span><span class="sxs-lookup"><span data-stu-id="84b8a-119">UNION</span></span>  
  
-   <span data-ttu-id="84b8a-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="84b8a-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="84b8a-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="84b8a-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="84b8a-122">SET</span><span class="sxs-lookup"><span data-stu-id="84b8a-122">SET</span></span>  
  
-   <span data-ttu-id="84b8a-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="84b8a-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="84b8a-124">项谓词（相等）：</span><span class="sxs-lookup"><span data-stu-id="84b8a-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="84b8a-125">IN</span><span class="sxs-lookup"><span data-stu-id="84b8a-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="84b8a-126">支持的组合</span><span class="sxs-lookup"><span data-stu-id="84b8a-126">Supported Combinations</span></span>  
 <span data-ttu-id="84b8a-127">下表说明了每种类型的比较运算符的所有受支持的组合：</span><span class="sxs-lookup"><span data-stu-id="84b8a-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="84b8a-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="84b8a-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="84b8a-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="84b8a-129">**!=**</span></span>|<span data-ttu-id="84b8a-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="84b8a-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="84b8a-131">**非重复**</span><span class="sxs-lookup"><span data-stu-id="84b8a-131">**DISTINCT**</span></span>|<span data-ttu-id="84b8a-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="84b8a-132">**UNION**</span></span><br /><br /> <span data-ttu-id="84b8a-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="84b8a-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="84b8a-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="84b8a-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="84b8a-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="84b8a-135">**SET**</span></span><br /><br /> <span data-ttu-id="84b8a-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="84b8a-136">**OVERLAPS**</span></span>|<span data-ttu-id="84b8a-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="84b8a-137">**IN**</span></span>|<span data-ttu-id="84b8a-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="84b8a-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="84b8a-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="84b8a-139">**>   >=**</span></span>|<span data-ttu-id="84b8a-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="84b8a-140">**ORDER BY**</span></span>|<span data-ttu-id="84b8a-141">**为 NULL**</span><span class="sxs-lookup"><span data-stu-id="84b8a-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="84b8a-142">**不为 NULL**</span><span class="sxs-lookup"><span data-stu-id="84b8a-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="84b8a-143">实体类型</span><span class="sxs-lookup"><span data-stu-id="84b8a-143">Entity type</span></span>|<span data-ttu-id="84b8a-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="84b8a-145">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="84b8a-146">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="84b8a-147">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="84b8a-148">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-149">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="84b8a-151">复杂类型</span><span class="sxs-lookup"><span data-stu-id="84b8a-151">Complex type</span></span>|<span data-ttu-id="84b8a-152">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-153">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-154">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-155">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-156">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-157">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-158">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="84b8a-159">行</span><span class="sxs-lookup"><span data-stu-id="84b8a-159">Row</span></span>|<span data-ttu-id="84b8a-160">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="84b8a-161">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="84b8a-162">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="84b8a-163">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-164">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-165">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="84b8a-166">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="84b8a-167">基元类型</span><span class="sxs-lookup"><span data-stu-id="84b8a-167">Primitive type</span></span>|<span data-ttu-id="84b8a-168">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="84b8a-168">Provider-specific</span></span>|<span data-ttu-id="84b8a-169">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="84b8a-169">Provider-specific</span></span>|<span data-ttu-id="84b8a-170">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="84b8a-170">Provider-specific</span></span>|<span data-ttu-id="84b8a-171">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="84b8a-171">Provider-specific</span></span>|<span data-ttu-id="84b8a-172">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="84b8a-172">Provider-specific</span></span>|<span data-ttu-id="84b8a-173">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="84b8a-173">Provider-specific</span></span>|<span data-ttu-id="84b8a-174">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="84b8a-174">Provider-specific</span></span>|  
|<span data-ttu-id="84b8a-175">多集</span><span class="sxs-lookup"><span data-stu-id="84b8a-175">Multiset</span></span>|<span data-ttu-id="84b8a-176">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-177">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-178">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-179">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-180">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-181">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-182">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="84b8a-183">引用</span><span class="sxs-lookup"><span data-stu-id="84b8a-183">Ref</span></span>|<span data-ttu-id="84b8a-184">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="84b8a-185">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="84b8a-186">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="84b8a-187">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="84b8a-188">引发</span><span class="sxs-lookup"><span data-stu-id="84b8a-188">Throw</span></span>|<span data-ttu-id="84b8a-189">引发</span><span class="sxs-lookup"><span data-stu-id="84b8a-189">Throw</span></span>|<span data-ttu-id="84b8a-190">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="84b8a-191">关联</span><span class="sxs-lookup"><span data-stu-id="84b8a-191">Association</span></span><br /><br /> <span data-ttu-id="84b8a-192">类型</span><span class="sxs-lookup"><span data-stu-id="84b8a-192">type</span></span>|<span data-ttu-id="84b8a-193">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-194">引发</span><span class="sxs-lookup"><span data-stu-id="84b8a-194">Throw</span></span>|<span data-ttu-id="84b8a-195">引发</span><span class="sxs-lookup"><span data-stu-id="84b8a-195">Throw</span></span>|<span data-ttu-id="84b8a-196">引发</span><span class="sxs-lookup"><span data-stu-id="84b8a-196">Throw</span></span>|<span data-ttu-id="84b8a-197">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-198">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="84b8a-199">引发<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="84b8a-200"><sup>1</sup>隐式比较给定的实体类型实例的引用，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="84b8a-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="84b8a-201">不能将实体实例与显式引用进行比较。</span><span class="sxs-lookup"><span data-stu-id="84b8a-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="84b8a-202">如果试图这么做，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="84b8a-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="84b8a-203">例如，以下查询将引发异常：</span><span class="sxs-lookup"><span data-stu-id="84b8a-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="84b8a-204"><sup>2</sup>复杂类型的属性被转换为扁平发送到应用商店中，因此它们变得可比较 （只要其所有属性都是可比较的） 之前。</span><span class="sxs-lookup"><span data-stu-id="84b8a-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="84b8a-205">另请参阅<sup>4。</sup></span><span class="sxs-lookup"><span data-stu-id="84b8a-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="84b8a-206"><sup>3</sup>实体框架运行时检测到不受支持的情况下，并在不牵扯提供程序/存储的情况下引发有意义的异常。</span><span class="sxs-lookup"><span data-stu-id="84b8a-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="84b8a-207"><sup>4</sup>尝试比较所有属性。</span><span class="sxs-lookup"><span data-stu-id="84b8a-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="84b8a-208">如果某个属性的类型不可比较，例如 text、ntext 或 image，则可能引发服务器异常。</span><span class="sxs-lookup"><span data-stu-id="84b8a-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="84b8a-209"><sup>5</sup>所有单个元素的引用进行比较 （包括实体集名称和实体类型的所有键属性）。</span><span class="sxs-lookup"><span data-stu-id="84b8a-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84b8a-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="84b8a-210">See Also</span></span>  
 [<span data-ttu-id="84b8a-211">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="84b8a-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
