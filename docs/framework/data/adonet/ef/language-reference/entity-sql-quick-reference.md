---
title: Entity SQL 快速参考
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: 0617ce96acaf5a6eafb2658cfe218cc8f4135f6e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765849"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="c8d5c-102">Entity SQL 快速参考</span><span class="sxs-lookup"><span data-stu-id="c8d5c-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="c8d5c-103">本主题提供 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询的快速参考。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="c8d5c-104">本主题中的查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="c8d5c-105">文本</span><span class="sxs-lookup"><span data-stu-id="c8d5c-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="c8d5c-106">String</span><span class="sxs-lookup"><span data-stu-id="c8d5c-106">String</span></span>  
 <span data-ttu-id="c8d5c-107">字符串分为 Unicode 字符串和非 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="c8d5c-108">Unicode 字符串前面附有 n。例如， `N'hello'`。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="c8d5c-109">下面是非 Unicode 字符串的示例：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="c8d5c-110">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-110">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-111">值</span><span class="sxs-lookup"><span data-stu-id="c8d5c-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c8d5c-112">hello</span><span class="sxs-lookup"><span data-stu-id="c8d5c-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="c8d5c-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="c8d5c-113">DateTime</span></span>  
 <span data-ttu-id="c8d5c-114">在日期时间文本中，日期部分和时间部分是必须存在的。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="c8d5c-115">这里没有默认值。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-115">There are no default values.</span></span>  
  
 <span data-ttu-id="c8d5c-116">示例：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-116">Example:</span></span>  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="c8d5c-117">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-117">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-118">值</span><span class="sxs-lookup"><span data-stu-id="c8d5c-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c8d5c-119">25.12.06 01:01:00</span><span class="sxs-lookup"><span data-stu-id="c8d5c-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="c8d5c-120">Integer</span><span class="sxs-lookup"><span data-stu-id="c8d5c-120">Integer</span></span>  
 <span data-ttu-id="c8d5c-121">整数文本可以为 Int32 (123)、UInt32 (123U)、Int64 (123L) 和 UInt64 (123UL) 类型。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="c8d5c-122">示例：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-122">Example:</span></span>  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="c8d5c-123">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-123">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-124">值</span><span class="sxs-lookup"><span data-stu-id="c8d5c-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c8d5c-125">1</span><span class="sxs-lookup"><span data-stu-id="c8d5c-125">1</span></span>|  
|<span data-ttu-id="c8d5c-126">2</span><span class="sxs-lookup"><span data-stu-id="c8d5c-126">2</span></span>|  
|<span data-ttu-id="c8d5c-127">3</span><span class="sxs-lookup"><span data-stu-id="c8d5c-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="c8d5c-128">其他</span><span class="sxs-lookup"><span data-stu-id="c8d5c-128">Other</span></span>  
 <span data-ttu-id="c8d5c-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 支持的其他文字为、Guid、二进制、浮点/双精度型、十进制和 `null`。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="c8d5c-130">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中的 null 文本视为与概念模型中的每一种其他类型兼容。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="c8d5c-131">类型构造函数</span><span class="sxs-lookup"><span data-stu-id="c8d5c-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="c8d5c-132">ROW</span><span class="sxs-lookup"><span data-stu-id="c8d5c-132">ROW</span></span>  
 <span data-ttu-id="c8d5c-133">[行](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md)构造匿名结构上类型化 （记录） 中的值，作为： `ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="c8d5c-133">[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="c8d5c-134">示例:</span><span class="sxs-lookup"><span data-stu-id="c8d5c-134">Example:</span></span>  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 <span data-ttu-id="c8d5c-135">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-135">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="c8d5c-136">ProductID</span></span>|<span data-ttu-id="c8d5c-137">名称</span><span class="sxs-lookup"><span data-stu-id="c8d5c-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="c8d5c-138">1</span><span class="sxs-lookup"><span data-stu-id="c8d5c-138">1</span></span>|<span data-ttu-id="c8d5c-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="c8d5c-139">Adjustable Race</span></span>|  
|<span data-ttu-id="c8d5c-140">879</span><span class="sxs-lookup"><span data-stu-id="c8d5c-140">879</span></span>|<span data-ttu-id="c8d5c-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="c8d5c-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="c8d5c-142">712</span><span class="sxs-lookup"><span data-stu-id="c8d5c-142">712</span></span>|<span data-ttu-id="c8d5c-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="c8d5c-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="c8d5c-144">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-144">...</span></span>|<span data-ttu-id="c8d5c-145">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="c8d5c-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="c8d5c-146">MULTISET</span></span>  
 <span data-ttu-id="c8d5c-147">[多重集](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md)构造集合，如：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="c8d5c-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="c8d5c-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="c8d5c-149">示例:</span><span class="sxs-lookup"><span data-stu-id="c8d5c-149">Example:</span></span>  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="c8d5c-150">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-150">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="c8d5c-151">ProductID</span></span>|<span data-ttu-id="c8d5c-152">名称</span><span class="sxs-lookup"><span data-stu-id="c8d5c-152">Name</span></span>|<span data-ttu-id="c8d5c-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="c8d5c-153">ProductNumber</span></span>|<span data-ttu-id="c8d5c-154">…</span><span class="sxs-lookup"><span data-stu-id="c8d5c-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="c8d5c-155">842</span><span class="sxs-lookup"><span data-stu-id="c8d5c-155">842</span></span>|<span data-ttu-id="c8d5c-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="c8d5c-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="c8d5c-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="c8d5c-157">PA-T100</span></span>|<span data-ttu-id="c8d5c-158">…</span><span class="sxs-lookup"><span data-stu-id="c8d5c-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="c8d5c-159">对象</span><span class="sxs-lookup"><span data-stu-id="c8d5c-159">Object</span></span>  
 <span data-ttu-id="c8d5c-160">[命名类型构造函数](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md)构造 （已命名） 的用户定义的对象，如`person("abc", 12)`。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-160">[Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="c8d5c-161">示例:</span><span class="sxs-lookup"><span data-stu-id="c8d5c-161">Example:</span></span>  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="c8d5c-162">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-162">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="c8d5c-163">SalesOrderDetailID</span></span>|<span data-ttu-id="c8d5c-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="c8d5c-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="c8d5c-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="c8d5c-165">OrderQty</span></span>|<span data-ttu-id="c8d5c-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="c8d5c-166">ProductID</span></span>|<span data-ttu-id="c8d5c-167">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="c8d5c-168">1</span><span class="sxs-lookup"><span data-stu-id="c8d5c-168">1</span></span>|<span data-ttu-id="c8d5c-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="c8d5c-169">4911-403C-98</span></span>|<span data-ttu-id="c8d5c-170">1</span><span class="sxs-lookup"><span data-stu-id="c8d5c-170">1</span></span>|<span data-ttu-id="c8d5c-171">776</span><span class="sxs-lookup"><span data-stu-id="c8d5c-171">776</span></span>|<span data-ttu-id="c8d5c-172">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-172">...</span></span>|  
|<span data-ttu-id="c8d5c-173">2</span><span class="sxs-lookup"><span data-stu-id="c8d5c-173">2</span></span>|<span data-ttu-id="c8d5c-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="c8d5c-174">4911-403C-98</span></span>|<span data-ttu-id="c8d5c-175">3</span><span class="sxs-lookup"><span data-stu-id="c8d5c-175">3</span></span>|<span data-ttu-id="c8d5c-176">777</span><span class="sxs-lookup"><span data-stu-id="c8d5c-176">777</span></span>|<span data-ttu-id="c8d5c-177">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-177">...</span></span>|  
|<span data-ttu-id="c8d5c-178">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-178">...</span></span>|<span data-ttu-id="c8d5c-179">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-179">...</span></span>|<span data-ttu-id="c8d5c-180">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-180">...</span></span>|<span data-ttu-id="c8d5c-181">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-181">...</span></span>|<span data-ttu-id="c8d5c-182">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="c8d5c-183">参考资料</span><span class="sxs-lookup"><span data-stu-id="c8d5c-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="c8d5c-184">REF</span><span class="sxs-lookup"><span data-stu-id="c8d5c-184">REF</span></span>  
 <span data-ttu-id="c8d5c-185">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)创建对实体类型实例的引用。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-185">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="c8d5c-186">例如，下面的查询返回对 Orders 实体集中每一个 Order 实体的引用：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="c8d5c-187">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-187">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-188">值</span><span class="sxs-lookup"><span data-stu-id="c8d5c-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c8d5c-189">1</span><span class="sxs-lookup"><span data-stu-id="c8d5c-189">1</span></span>|  
|<span data-ttu-id="c8d5c-190">2</span><span class="sxs-lookup"><span data-stu-id="c8d5c-190">2</span></span>|  
|<span data-ttu-id="c8d5c-191">3</span><span class="sxs-lookup"><span data-stu-id="c8d5c-191">3</span></span>|  
|<span data-ttu-id="c8d5c-192">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-192">...</span></span>|  
  
 <span data-ttu-id="c8d5c-193">下面的示例使用属性提取运算符 (.) 访问实体的属性。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="c8d5c-194">在使用属性提取运算符时，引用将自动被反引用。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="c8d5c-195">示例：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-195">Example:</span></span>  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="c8d5c-196">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-196">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-197">值</span><span class="sxs-lookup"><span data-stu-id="c8d5c-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c8d5c-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="c8d5c-198">Adjustable Race</span></span>|  
|<span data-ttu-id="c8d5c-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="c8d5c-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="c8d5c-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="c8d5c-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="c8d5c-201">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="c8d5c-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="c8d5c-202">DEREF</span></span>  
 <span data-ttu-id="c8d5c-203">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)取消引用一个引用值并取消引用的结果的生成。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-203">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="c8d5c-204">例如，下面的查询生成 Orders 实体集中每一个 Order 的 Order 实体：`SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="c8d5c-205">示例：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-205">Example:</span></span>  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="c8d5c-206">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-206">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-207">值</span><span class="sxs-lookup"><span data-stu-id="c8d5c-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c8d5c-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="c8d5c-208">Adjustable Race</span></span>|  
|<span data-ttu-id="c8d5c-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="c8d5c-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="c8d5c-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="c8d5c-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="c8d5c-211">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="c8d5c-212">CREATEREF 和 KEY</span><span class="sxs-lookup"><span data-stu-id="c8d5c-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="c8d5c-213">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)创建传递键的引用。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-213">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="c8d5c-214">[密钥](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)提取具有类型引用的表达式的键部分。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-214">[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="c8d5c-215">示例:</span><span class="sxs-lookup"><span data-stu-id="c8d5c-215">Example:</span></span>  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="c8d5c-216">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-216">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="c8d5c-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="c8d5c-218">980</span><span class="sxs-lookup"><span data-stu-id="c8d5c-218">980</span></span>|  
|<span data-ttu-id="c8d5c-219">365</span><span class="sxs-lookup"><span data-stu-id="c8d5c-219">365</span></span>|  
|<span data-ttu-id="c8d5c-220">771</span><span class="sxs-lookup"><span data-stu-id="c8d5c-220">771</span></span>|  
|<span data-ttu-id="c8d5c-221">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="c8d5c-222">函数</span><span class="sxs-lookup"><span data-stu-id="c8d5c-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="c8d5c-223">规范</span><span class="sxs-lookup"><span data-stu-id="c8d5c-223">Canonical</span></span>  
 <span data-ttu-id="c8d5c-224">命名空间[规范函数](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)为 Edm，如`Edm.Length("string")`。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-224">The namespace for [canonical functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="c8d5c-225">您无需指定命名空间，除非导入的另一个命名空间中包含与规范函数同名的函数。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="c8d5c-226">如果两个命名空间有相同的函数，用户应指定完整名称。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="c8d5c-227">示例：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-227">Example:</span></span>  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="c8d5c-228">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-228">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="c8d5c-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="c8d5c-230">6</span><span class="sxs-lookup"><span data-stu-id="c8d5c-230">6</span></span>|  
|<span data-ttu-id="c8d5c-231">6</span><span class="sxs-lookup"><span data-stu-id="c8d5c-231">6</span></span>|  
|<span data-ttu-id="c8d5c-232">5</span><span class="sxs-lookup"><span data-stu-id="c8d5c-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="c8d5c-233">特定于 Microsoft 提供程序</span><span class="sxs-lookup"><span data-stu-id="c8d5c-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="c8d5c-234">[Microsoft 提供程序特定函数](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)中`SqlServer`命名空间。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-234">[Microsoft provider-specific functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="c8d5c-235">示例:</span><span class="sxs-lookup"><span data-stu-id="c8d5c-235">Example:</span></span>  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="c8d5c-236">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-236">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="c8d5c-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="c8d5c-238">27</span><span class="sxs-lookup"><span data-stu-id="c8d5c-238">27</span></span>|  
|<span data-ttu-id="c8d5c-239">27</span><span class="sxs-lookup"><span data-stu-id="c8d5c-239">27</span></span>|  
|<span data-ttu-id="c8d5c-240">26</span><span class="sxs-lookup"><span data-stu-id="c8d5c-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="c8d5c-241">命名空间</span><span class="sxs-lookup"><span data-stu-id="c8d5c-241">Namespaces</span></span>  
 <span data-ttu-id="c8d5c-242">[使用](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md)指定查询表达式中使用命名空间。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-242">[USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="c8d5c-243">示例:</span><span class="sxs-lookup"><span data-stu-id="c8d5c-243">Example:</span></span>  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="c8d5c-244">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-244">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-245">值</span><span class="sxs-lookup"><span data-stu-id="c8d5c-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c8d5c-246">aa</span><span class="sxs-lookup"><span data-stu-id="c8d5c-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="c8d5c-247">分页</span><span class="sxs-lookup"><span data-stu-id="c8d5c-247">Paging</span></span>  
 <span data-ttu-id="c8d5c-248">可以通过声明表示分页[跳过](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)和[限制](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)于子子句[ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)子句。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-248">Paging can be expressed by declaring a [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses to the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="c8d5c-249">示例:</span><span class="sxs-lookup"><span data-stu-id="c8d5c-249">Example:</span></span>  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="c8d5c-250">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-250">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-251">ID</span><span class="sxs-lookup"><span data-stu-id="c8d5c-251">ID</span></span>|<span data-ttu-id="c8d5c-252">名称</span><span class="sxs-lookup"><span data-stu-id="c8d5c-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="c8d5c-253">10</span><span class="sxs-lookup"><span data-stu-id="c8d5c-253">10</span></span>|<span data-ttu-id="c8d5c-254">Adina</span><span class="sxs-lookup"><span data-stu-id="c8d5c-254">Adina</span></span>|  
|<span data-ttu-id="c8d5c-255">11</span><span class="sxs-lookup"><span data-stu-id="c8d5c-255">11</span></span>|<span data-ttu-id="c8d5c-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="c8d5c-256">Agcaoili</span></span>|  
|<span data-ttu-id="c8d5c-257">12</span><span class="sxs-lookup"><span data-stu-id="c8d5c-257">12</span></span>|<span data-ttu-id="c8d5c-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="c8d5c-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="c8d5c-259">分组</span><span class="sxs-lookup"><span data-stu-id="c8d5c-259">Grouping</span></span>  
 <span data-ttu-id="c8d5c-260">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md)指定为查询返回的对象的组 ([选择](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) 表达式的放置。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-260">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="c8d5c-261">示例:</span><span class="sxs-lookup"><span data-stu-id="c8d5c-261">Example:</span></span>  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="c8d5c-262">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-262">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-263">name</span><span class="sxs-lookup"><span data-stu-id="c8d5c-263">name</span></span>|  
|----------|  
|<span data-ttu-id="c8d5c-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="c8d5c-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="c8d5c-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="c8d5c-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="c8d5c-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="c8d5c-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="c8d5c-267">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="c8d5c-268">导航</span><span class="sxs-lookup"><span data-stu-id="c8d5c-268">Navigation</span></span>  
 <span data-ttu-id="c8d5c-269">关系导航运算符用于导航从一个实体（起始端）到另一个实体（结束端）的关系。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="c8d5c-270">[导航](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)采用关系类型限定为\<命名空间 >。\<关系类型名称 >。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-270">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="c8d5c-271">导航返回 Ref\<T > 如果的基数结束为 1。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="c8d5c-272">如果的基数为 n，集合结束 < Ref\<T >> 将返回。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="c8d5c-273">示例:</span><span class="sxs-lookup"><span data-stu-id="c8d5c-273">Example:</span></span>  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="c8d5c-274">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-274">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="c8d5c-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="c8d5c-276">1</span><span class="sxs-lookup"><span data-stu-id="c8d5c-276">1</span></span>|  
|<span data-ttu-id="c8d5c-277">2</span><span class="sxs-lookup"><span data-stu-id="c8d5c-277">2</span></span>|  
|<span data-ttu-id="c8d5c-278">3</span><span class="sxs-lookup"><span data-stu-id="c8d5c-278">3</span></span>|  
|<span data-ttu-id="c8d5c-279">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="c8d5c-280">SELECT VALUE 和 SELECT</span><span class="sxs-lookup"><span data-stu-id="c8d5c-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="c8d5c-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="c8d5c-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="c8d5c-282"> 提供了 SELECT VALUE 子句以跳过隐式行构造。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-282"> provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="c8d5c-283">SELECT VALUE 子句中只能指定一项。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="c8d5c-284">当使用这样的子句、 SELECT 子句中中的项会构造没有行包装器和所需形状的集合可以生成，例如： `SELECT VALUE a`。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="c8d5c-285">示例:</span><span class="sxs-lookup"><span data-stu-id="c8d5c-285">Example:</span></span>  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="c8d5c-286">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-286">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-287">名称</span><span class="sxs-lookup"><span data-stu-id="c8d5c-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="c8d5c-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="c8d5c-288">Adjustable Race</span></span>|  
|<span data-ttu-id="c8d5c-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="c8d5c-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="c8d5c-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="c8d5c-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="c8d5c-291">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="c8d5c-292">选择</span><span class="sxs-lookup"><span data-stu-id="c8d5c-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="c8d5c-293"> 还提供了用于构造任意行的行构造函数。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-293"> also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="c8d5c-294">SELECT 接受投影中的一个或多个元素，并生成含有字段的数据记录，例如：`SELECT a, b, c`。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="c8d5c-295">示例：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-295">Example:</span></span>  
  
 <span data-ttu-id="c8d5c-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="c8d5c-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="c8d5c-297">名称</span><span class="sxs-lookup"><span data-stu-id="c8d5c-297">Name</span></span>|<span data-ttu-id="c8d5c-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="c8d5c-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="c8d5c-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="c8d5c-299">Adjustable Race</span></span>|<span data-ttu-id="c8d5c-300">1</span><span class="sxs-lookup"><span data-stu-id="c8d5c-300">1</span></span>|  
|<span data-ttu-id="c8d5c-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="c8d5c-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="c8d5c-302">879</span><span class="sxs-lookup"><span data-stu-id="c8d5c-302">879</span></span>|  
|<span data-ttu-id="c8d5c-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="c8d5c-303">AWC Logo Cap</span></span>|<span data-ttu-id="c8d5c-304">712</span><span class="sxs-lookup"><span data-stu-id="c8d5c-304">712</span></span>|  
|<span data-ttu-id="c8d5c-305">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-305">...</span></span>|<span data-ttu-id="c8d5c-306">...</span><span class="sxs-lookup"><span data-stu-id="c8d5c-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="c8d5c-307">CASE 表达式</span><span class="sxs-lookup"><span data-stu-id="c8d5c-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="c8d5c-308">[Case 表达式](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)求出一组布尔表达式的值以确定结果。</span><span class="sxs-lookup"><span data-stu-id="c8d5c-308">The [case expression](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="c8d5c-309">示例:</span><span class="sxs-lookup"><span data-stu-id="c8d5c-309">Example:</span></span>  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="c8d5c-310">输出：</span><span class="sxs-lookup"><span data-stu-id="c8d5c-310">Output:</span></span>  
  
|<span data-ttu-id="c8d5c-311">值</span><span class="sxs-lookup"><span data-stu-id="c8d5c-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="c8d5c-312">true</span><span class="sxs-lookup"><span data-stu-id="c8d5c-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8d5c-313">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8d5c-313">See Also</span></span>  
 [<span data-ttu-id="c8d5c-314">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="c8d5c-314">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="c8d5c-315">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="c8d5c-315">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
