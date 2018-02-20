---
title: "比较语义 (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: e20d47e0ae97067d2dcafcf929f717598d4e3e80
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="eaee9-102">比较语义 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="eaee9-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="eaee9-103">执行下列任一 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 运算符时都涉及类型实例的比较：</span><span class="sxs-lookup"><span data-stu-id="eaee9-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="eaee9-104">显式比较</span><span class="sxs-lookup"><span data-stu-id="eaee9-104">Explicit comparison</span></span>  
 <span data-ttu-id="eaee9-105">相等运算：</span><span class="sxs-lookup"><span data-stu-id="eaee9-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="eaee9-106">!=</span><span class="sxs-lookup"><span data-stu-id="eaee9-106">!=</span></span>  
  
 <span data-ttu-id="eaee9-107">排序运算：</span><span class="sxs-lookup"><span data-stu-id="eaee9-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="eaee9-108">判断是否可为 Null 的运算：</span><span class="sxs-lookup"><span data-stu-id="eaee9-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="eaee9-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="eaee9-109">IS NULL</span></span>  
  
-   <span data-ttu-id="eaee9-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="eaee9-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="eaee9-111">显式区别</span><span class="sxs-lookup"><span data-stu-id="eaee9-111">Explicit distinction</span></span>  
 <span data-ttu-id="eaee9-112">相等区别：</span><span class="sxs-lookup"><span data-stu-id="eaee9-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="eaee9-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="eaee9-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="eaee9-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="eaee9-114">GROUP BY</span></span>  
  
 <span data-ttu-id="eaee9-115">排序区别：</span><span class="sxs-lookup"><span data-stu-id="eaee9-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="eaee9-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="eaee9-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="eaee9-117">隐式区别</span><span class="sxs-lookup"><span data-stu-id="eaee9-117">Implicit distinction</span></span>  
 <span data-ttu-id="eaee9-118">集运算和谓词（相等）：</span><span class="sxs-lookup"><span data-stu-id="eaee9-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="eaee9-119">UNION</span><span class="sxs-lookup"><span data-stu-id="eaee9-119">UNION</span></span>  
  
-   <span data-ttu-id="eaee9-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="eaee9-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="eaee9-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="eaee9-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="eaee9-122">SET</span><span class="sxs-lookup"><span data-stu-id="eaee9-122">SET</span></span>  
  
-   <span data-ttu-id="eaee9-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="eaee9-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="eaee9-124">项谓词（相等）：</span><span class="sxs-lookup"><span data-stu-id="eaee9-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="eaee9-125">IN</span><span class="sxs-lookup"><span data-stu-id="eaee9-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="eaee9-126">支持的组合</span><span class="sxs-lookup"><span data-stu-id="eaee9-126">Supported Combinations</span></span>  
 <span data-ttu-id="eaee9-127">下表说明了每种类型的比较运算符的所有受支持的组合：</span><span class="sxs-lookup"><span data-stu-id="eaee9-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="eaee9-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="eaee9-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="eaee9-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="eaee9-129">**!=**</span></span>|<span data-ttu-id="eaee9-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="eaee9-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="eaee9-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="eaee9-131">**DISTINCT**</span></span>|<span data-ttu-id="eaee9-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="eaee9-132">**UNION**</span></span><br /><br /> <span data-ttu-id="eaee9-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="eaee9-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="eaee9-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="eaee9-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="eaee9-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="eaee9-135">**SET**</span></span><br /><br /> <span data-ttu-id="eaee9-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="eaee9-136">**OVERLAPS**</span></span>|<span data-ttu-id="eaee9-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="eaee9-137">**IN**</span></span>|<span data-ttu-id="eaee9-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="eaee9-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="eaee9-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="eaee9-139">**>   >=**</span></span>|<span data-ttu-id="eaee9-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="eaee9-140">**ORDER BY**</span></span>|<span data-ttu-id="eaee9-141">**为 NULL**</span><span class="sxs-lookup"><span data-stu-id="eaee9-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="eaee9-142">**不为 NULL**</span><span class="sxs-lookup"><span data-stu-id="eaee9-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="eaee9-143">实体类型</span><span class="sxs-lookup"><span data-stu-id="eaee9-143">Entity type</span></span>|<span data-ttu-id="eaee9-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="eaee9-145">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="eaee9-146">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="eaee9-147">所有属性<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="eaee9-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="eaee9-151">复杂类型</span><span class="sxs-lookup"><span data-stu-id="eaee9-151">Complex type</span></span>|<span data-ttu-id="eaee9-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="eaee9-159">行</span><span class="sxs-lookup"><span data-stu-id="eaee9-159">Row</span></span>|<span data-ttu-id="eaee9-160">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="eaee9-161">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="eaee9-162">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="eaee9-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-165">所有属性<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="eaee9-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="eaee9-167">基元类型</span><span class="sxs-lookup"><span data-stu-id="eaee9-167">Primitive type</span></span>|<span data-ttu-id="eaee9-168">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="eaee9-168">Provider-specific</span></span>|<span data-ttu-id="eaee9-169">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="eaee9-169">Provider-specific</span></span>|<span data-ttu-id="eaee9-170">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="eaee9-170">Provider-specific</span></span>|<span data-ttu-id="eaee9-171">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="eaee9-171">Provider-specific</span></span>|<span data-ttu-id="eaee9-172">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="eaee9-172">Provider-specific</span></span>|<span data-ttu-id="eaee9-173">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="eaee9-173">Provider-specific</span></span>|<span data-ttu-id="eaee9-174">特定于提供程序</span><span class="sxs-lookup"><span data-stu-id="eaee9-174">Provider-specific</span></span>|  
|<span data-ttu-id="eaee9-175">多集</span><span class="sxs-lookup"><span data-stu-id="eaee9-175">Multiset</span></span>|<span data-ttu-id="eaee9-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="eaee9-183">引用</span><span class="sxs-lookup"><span data-stu-id="eaee9-183">Ref</span></span>|<span data-ttu-id="eaee9-184">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="eaee9-185">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="eaee9-186">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="eaee9-187">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="eaee9-188">引发</span><span class="sxs-lookup"><span data-stu-id="eaee9-188">Throw</span></span>|<span data-ttu-id="eaee9-189">引发</span><span class="sxs-lookup"><span data-stu-id="eaee9-189">Throw</span></span>|<span data-ttu-id="eaee9-190">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="eaee9-191">关联</span><span class="sxs-lookup"><span data-stu-id="eaee9-191">Association</span></span><br /><br /> <span data-ttu-id="eaee9-192">类型</span><span class="sxs-lookup"><span data-stu-id="eaee9-192">type</span></span>|<span data-ttu-id="eaee9-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-194">引发</span><span class="sxs-lookup"><span data-stu-id="eaee9-194">Throw</span></span>|<span data-ttu-id="eaee9-195">引发</span><span class="sxs-lookup"><span data-stu-id="eaee9-195">Throw</span></span>|<span data-ttu-id="eaee9-196">引发</span><span class="sxs-lookup"><span data-stu-id="eaee9-196">Throw</span></span>|<span data-ttu-id="eaee9-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="eaee9-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="eaee9-200"><sup>1</sup>隐式比较给定的实体类型实例的引用，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="eaee9-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="eaee9-201">不能将实体实例与显式引用进行比较。</span><span class="sxs-lookup"><span data-stu-id="eaee9-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="eaee9-202">如果试图这么做，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="eaee9-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="eaee9-203">例如，以下查询将引发异常：</span><span class="sxs-lookup"><span data-stu-id="eaee9-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="eaee9-204"><sup>2</sup>复杂类型的属性被转换为扁平发送到应用商店中，因此它们变得可比较 （只要其所有属性都是可比较的） 之前。</span><span class="sxs-lookup"><span data-stu-id="eaee9-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="eaee9-205">另请参阅<sup>4。</sup></span><span class="sxs-lookup"><span data-stu-id="eaee9-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="eaee9-206"><sup>3</sup>实体框架运行时检测到不受支持的情况下，并在不牵扯提供程序/存储的情况下引发有意义的异常。</span><span class="sxs-lookup"><span data-stu-id="eaee9-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="eaee9-207"><sup>4</sup>尝试比较所有属性。</span><span class="sxs-lookup"><span data-stu-id="eaee9-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="eaee9-208">如果某个属性的类型不可比较，例如 text、ntext 或 image，则可能引发服务器异常。</span><span class="sxs-lookup"><span data-stu-id="eaee9-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="eaee9-209"><sup>5</sup>所有单个元素的引用进行比较 （包括实体集名称和实体类型的所有键属性）。</span><span class="sxs-lookup"><span data-stu-id="eaee9-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaee9-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="eaee9-210">See Also</span></span>  
 [<span data-ttu-id="eaee9-211">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="eaee9-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
