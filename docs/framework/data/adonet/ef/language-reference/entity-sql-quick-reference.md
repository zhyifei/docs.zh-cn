---
title: Entity SQL 快速参考
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: b4e3eaf8abd82b63fa2663b47f878ecfa9584897
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785250"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="6a7f2-102">Entity SQL 快速参考</span><span class="sxs-lookup"><span data-stu-id="6a7f2-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="6a7f2-103">本主题提供 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询的快速参考。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="6a7f2-104">本主题中的查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="6a7f2-105">文本</span><span class="sxs-lookup"><span data-stu-id="6a7f2-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="6a7f2-106">String</span><span class="sxs-lookup"><span data-stu-id="6a7f2-106">String</span></span>  
 <span data-ttu-id="6a7f2-107">字符串分为 Unicode 字符串和非 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="6a7f2-108">Unicode 字符串前面附有 n。例如， `N'hello'`。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="6a7f2-109">下面是非 Unicode 字符串的示例：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="6a7f2-110">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-110">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-111">“值”</span><span class="sxs-lookup"><span data-stu-id="6a7f2-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6a7f2-112">hello</span><span class="sxs-lookup"><span data-stu-id="6a7f2-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="6a7f2-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="6a7f2-113">DateTime</span></span>  
 <span data-ttu-id="6a7f2-114">在日期时间文本中，日期部分和时间部分是必须存在的。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="6a7f2-115">这里没有默认值。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-115">There are no default values.</span></span>  
  
 <span data-ttu-id="6a7f2-116">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-116">Example:</span></span>  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="6a7f2-117">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-117">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-118">“值”</span><span class="sxs-lookup"><span data-stu-id="6a7f2-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6a7f2-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="6a7f2-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="6a7f2-120">整数</span><span class="sxs-lookup"><span data-stu-id="6a7f2-120">Integer</span></span>  
 <span data-ttu-id="6a7f2-121">整数文本可以为 Int32 (123)、UInt32 (123U)、Int64 (123L) 和 UInt64 (123UL) 类型。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="6a7f2-122">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-122">Example:</span></span>  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="6a7f2-123">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-123">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-124">“值”</span><span class="sxs-lookup"><span data-stu-id="6a7f2-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6a7f2-125">1</span><span class="sxs-lookup"><span data-stu-id="6a7f2-125">1</span></span>|  
|<span data-ttu-id="6a7f2-126">2</span><span class="sxs-lookup"><span data-stu-id="6a7f2-126">2</span></span>|  
|<span data-ttu-id="6a7f2-127">3</span><span class="sxs-lookup"><span data-stu-id="6a7f2-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="6a7f2-128">其他</span><span class="sxs-lookup"><span data-stu-id="6a7f2-128">Other</span></span>  
 <span data-ttu-id="6a7f2-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 支持的其他文字为、Guid、二进制、浮点/双精度型、十进制和 `null`。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="6a7f2-130">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中的 null 文本视为与概念模型中的每一种其他类型兼容。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="6a7f2-131">类型构造函数</span><span class="sxs-lookup"><span data-stu-id="6a7f2-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="6a7f2-132">ROW</span><span class="sxs-lookup"><span data-stu-id="6a7f2-132">ROW</span></span>  
 <span data-ttu-id="6a7f2-133">[行](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md)构造一个匿名的结构化类型 （记录） 值作为： `ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="6a7f2-133">[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="6a7f2-134">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-134">Example:</span></span>  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 <span data-ttu-id="6a7f2-135">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-135">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="6a7f2-136">ProductID</span></span>|<span data-ttu-id="6a7f2-137">名称</span><span class="sxs-lookup"><span data-stu-id="6a7f2-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="6a7f2-138">1</span><span class="sxs-lookup"><span data-stu-id="6a7f2-138">1</span></span>|<span data-ttu-id="6a7f2-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6a7f2-139">Adjustable Race</span></span>|  
|<span data-ttu-id="6a7f2-140">879</span><span class="sxs-lookup"><span data-stu-id="6a7f2-140">879</span></span>|<span data-ttu-id="6a7f2-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6a7f2-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="6a7f2-142">712</span><span class="sxs-lookup"><span data-stu-id="6a7f2-142">712</span></span>|<span data-ttu-id="6a7f2-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6a7f2-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="6a7f2-144">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-144">...</span></span>|<span data-ttu-id="6a7f2-145">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="6a7f2-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="6a7f2-146">MULTISET</span></span>  
 <span data-ttu-id="6a7f2-147">[多重集](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md)构造集合，如：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="6a7f2-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="6a7f2-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="6a7f2-149">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-149">Example:</span></span>  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="6a7f2-150">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-150">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="6a7f2-151">ProductID</span></span>|<span data-ttu-id="6a7f2-152">名称</span><span class="sxs-lookup"><span data-stu-id="6a7f2-152">Name</span></span>|<span data-ttu-id="6a7f2-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="6a7f2-153">ProductNumber</span></span>|<span data-ttu-id="6a7f2-154">…</span><span class="sxs-lookup"><span data-stu-id="6a7f2-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="6a7f2-155">842</span><span class="sxs-lookup"><span data-stu-id="6a7f2-155">842</span></span>|<span data-ttu-id="6a7f2-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="6a7f2-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="6a7f2-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="6a7f2-157">PA-T100</span></span>|<span data-ttu-id="6a7f2-158">…</span><span class="sxs-lookup"><span data-stu-id="6a7f2-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="6a7f2-159">对象</span><span class="sxs-lookup"><span data-stu-id="6a7f2-159">Object</span></span>  
 <span data-ttu-id="6a7f2-160">[命名类型构造函数](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md)构造 （命名的） 用户定义的对象，如`person("abc", 12)`。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-160">[Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="6a7f2-161">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-161">Example:</span></span>  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="6a7f2-162">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-162">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="6a7f2-163">SalesOrderDetailID</span></span>|<span data-ttu-id="6a7f2-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="6a7f2-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="6a7f2-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="6a7f2-165">OrderQty</span></span>|<span data-ttu-id="6a7f2-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="6a7f2-166">ProductID</span></span>|<span data-ttu-id="6a7f2-167">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="6a7f2-168">1</span><span class="sxs-lookup"><span data-stu-id="6a7f2-168">1</span></span>|<span data-ttu-id="6a7f2-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="6a7f2-169">4911-403C-98</span></span>|<span data-ttu-id="6a7f2-170">1</span><span class="sxs-lookup"><span data-stu-id="6a7f2-170">1</span></span>|<span data-ttu-id="6a7f2-171">776</span><span class="sxs-lookup"><span data-stu-id="6a7f2-171">776</span></span>|<span data-ttu-id="6a7f2-172">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-172">...</span></span>|  
|<span data-ttu-id="6a7f2-173">2</span><span class="sxs-lookup"><span data-stu-id="6a7f2-173">2</span></span>|<span data-ttu-id="6a7f2-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="6a7f2-174">4911-403C-98</span></span>|<span data-ttu-id="6a7f2-175">3</span><span class="sxs-lookup"><span data-stu-id="6a7f2-175">3</span></span>|<span data-ttu-id="6a7f2-176">777</span><span class="sxs-lookup"><span data-stu-id="6a7f2-176">777</span></span>|<span data-ttu-id="6a7f2-177">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-177">...</span></span>|  
|<span data-ttu-id="6a7f2-178">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-178">...</span></span>|<span data-ttu-id="6a7f2-179">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-179">...</span></span>|<span data-ttu-id="6a7f2-180">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-180">...</span></span>|<span data-ttu-id="6a7f2-181">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-181">...</span></span>|<span data-ttu-id="6a7f2-182">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="6a7f2-183">参考资料</span><span class="sxs-lookup"><span data-stu-id="6a7f2-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="6a7f2-184">REF</span><span class="sxs-lookup"><span data-stu-id="6a7f2-184">REF</span></span>  
 <span data-ttu-id="6a7f2-185">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)创建对实体类型实例的引用。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-185">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="6a7f2-186">例如，下面的查询返回对 Orders 实体集中每一个 Order 实体的引用：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="6a7f2-187">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-187">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-188">“值”</span><span class="sxs-lookup"><span data-stu-id="6a7f2-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6a7f2-189">1</span><span class="sxs-lookup"><span data-stu-id="6a7f2-189">1</span></span>|  
|<span data-ttu-id="6a7f2-190">2</span><span class="sxs-lookup"><span data-stu-id="6a7f2-190">2</span></span>|  
|<span data-ttu-id="6a7f2-191">3</span><span class="sxs-lookup"><span data-stu-id="6a7f2-191">3</span></span>|  
|<span data-ttu-id="6a7f2-192">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-192">...</span></span>|  
  
 <span data-ttu-id="6a7f2-193">下面的示例使用属性提取运算符 (.) 访问实体的属性。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="6a7f2-194">在使用属性提取运算符时，引用将自动被反引用。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="6a7f2-195">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-195">Example:</span></span>  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="6a7f2-196">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-196">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-197">“值”</span><span class="sxs-lookup"><span data-stu-id="6a7f2-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6a7f2-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6a7f2-198">Adjustable Race</span></span>|  
|<span data-ttu-id="6a7f2-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6a7f2-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="6a7f2-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6a7f2-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="6a7f2-201">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="6a7f2-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="6a7f2-202">DEREF</span></span>  
 <span data-ttu-id="6a7f2-203">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)取消引用一个引用值并生成的结果。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-203">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="6a7f2-204">例如，下面的查询生成 Orders 实体集中每一个 Order 的 Order 实体：`SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="6a7f2-205">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-205">Example:</span></span>  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="6a7f2-206">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-206">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-207">“值”</span><span class="sxs-lookup"><span data-stu-id="6a7f2-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6a7f2-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6a7f2-208">Adjustable Race</span></span>|  
|<span data-ttu-id="6a7f2-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6a7f2-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="6a7f2-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6a7f2-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="6a7f2-211">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="6a7f2-212">CREATEREF 和 KEY</span><span class="sxs-lookup"><span data-stu-id="6a7f2-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="6a7f2-213">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)创建传递键的引用。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-213">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="6a7f2-214">[密钥](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)提取的密钥类型引用的表达式的一部分。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-214">[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="6a7f2-215">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-215">Example:</span></span>  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="6a7f2-216">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-216">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="6a7f2-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="6a7f2-218">980</span><span class="sxs-lookup"><span data-stu-id="6a7f2-218">980</span></span>|  
|<span data-ttu-id="6a7f2-219">365</span><span class="sxs-lookup"><span data-stu-id="6a7f2-219">365</span></span>|  
|<span data-ttu-id="6a7f2-220">771</span><span class="sxs-lookup"><span data-stu-id="6a7f2-220">771</span></span>|  
|<span data-ttu-id="6a7f2-221">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="6a7f2-222">函数</span><span class="sxs-lookup"><span data-stu-id="6a7f2-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="6a7f2-223">规范</span><span class="sxs-lookup"><span data-stu-id="6a7f2-223">Canonical</span></span>  
 <span data-ttu-id="6a7f2-224">命名空间[规范函数](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)是 Edm 中，如`Edm.Length("string")`。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-224">The namespace for [canonical functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="6a7f2-225">您无需指定命名空间，除非导入的另一个命名空间中包含与规范函数同名的函数。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="6a7f2-226">如果两个命名空间有相同的函数，用户应指定完整名称。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="6a7f2-227">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-227">Example:</span></span>  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="6a7f2-228">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-228">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="6a7f2-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="6a7f2-230">6</span><span class="sxs-lookup"><span data-stu-id="6a7f2-230">6</span></span>|  
|<span data-ttu-id="6a7f2-231">6</span><span class="sxs-lookup"><span data-stu-id="6a7f2-231">6</span></span>|  
|<span data-ttu-id="6a7f2-232">5</span><span class="sxs-lookup"><span data-stu-id="6a7f2-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="6a7f2-233">特定于 Microsoft 提供程序</span><span class="sxs-lookup"><span data-stu-id="6a7f2-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="6a7f2-234">[Microsoft 提供程序特定的函数](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)位于`SqlServer`命名空间。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-234">[Microsoft provider-specific functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="6a7f2-235">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-235">Example:</span></span>  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="6a7f2-236">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-236">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="6a7f2-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="6a7f2-238">27</span><span class="sxs-lookup"><span data-stu-id="6a7f2-238">27</span></span>|  
|<span data-ttu-id="6a7f2-239">27</span><span class="sxs-lookup"><span data-stu-id="6a7f2-239">27</span></span>|  
|<span data-ttu-id="6a7f2-240">26</span><span class="sxs-lookup"><span data-stu-id="6a7f2-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="6a7f2-241">命名空间</span><span class="sxs-lookup"><span data-stu-id="6a7f2-241">Namespaces</span></span>  
 <span data-ttu-id="6a7f2-242">[使用](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md)指定查询表达式中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-242">[USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="6a7f2-243">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-243">Example:</span></span>  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="6a7f2-244">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-244">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-245">“值”</span><span class="sxs-lookup"><span data-stu-id="6a7f2-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6a7f2-246">aa</span><span class="sxs-lookup"><span data-stu-id="6a7f2-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="6a7f2-247">分页</span><span class="sxs-lookup"><span data-stu-id="6a7f2-247">Paging</span></span>  
 <span data-ttu-id="6a7f2-248">可以通过声明表示分页[跳过](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)并[限制](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)于子子句[ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)子句。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-248">Paging can be expressed by declaring a [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses to the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="6a7f2-249">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-249">Example:</span></span>  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="6a7f2-250">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-250">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-251">Id</span><span class="sxs-lookup"><span data-stu-id="6a7f2-251">ID</span></span>|<span data-ttu-id="6a7f2-252">名称</span><span class="sxs-lookup"><span data-stu-id="6a7f2-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="6a7f2-253">10</span><span class="sxs-lookup"><span data-stu-id="6a7f2-253">10</span></span>|<span data-ttu-id="6a7f2-254">Adina</span><span class="sxs-lookup"><span data-stu-id="6a7f2-254">Adina</span></span>|  
|<span data-ttu-id="6a7f2-255">11</span><span class="sxs-lookup"><span data-stu-id="6a7f2-255">11</span></span>|<span data-ttu-id="6a7f2-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="6a7f2-256">Agcaoili</span></span>|  
|<span data-ttu-id="6a7f2-257">12</span><span class="sxs-lookup"><span data-stu-id="6a7f2-257">12</span></span>|<span data-ttu-id="6a7f2-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="6a7f2-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="6a7f2-259">分组</span><span class="sxs-lookup"><span data-stu-id="6a7f2-259">Grouping</span></span>  
 <span data-ttu-id="6a7f2-260">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md)组指定为查询返回的对象 ([选择](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) 表达式的放置。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-260">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="6a7f2-261">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-261">Example:</span></span>  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="6a7f2-262">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-262">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-263">name</span><span class="sxs-lookup"><span data-stu-id="6a7f2-263">name</span></span>|  
|----------|  
|<span data-ttu-id="6a7f2-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="6a7f2-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="6a7f2-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="6a7f2-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="6a7f2-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="6a7f2-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="6a7f2-267">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="6a7f2-268">导航</span><span class="sxs-lookup"><span data-stu-id="6a7f2-268">Navigation</span></span>  
 <span data-ttu-id="6a7f2-269">关系导航运算符用于导航从一个实体（起始端）到另一个实体（结束端）的关系。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="6a7f2-270">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)接受限定为关系类型\<命名空间 >。\<关系类型名称 >。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-270">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="6a7f2-271">导航返回 Ref\<T > 如果的基数为 1 结束。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="6a7f2-272">如果的基数为 n，集合结束 < Ref\<T >> 将返回。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="6a7f2-273">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-273">Example:</span></span>  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="6a7f2-274">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-274">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="6a7f2-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="6a7f2-276">1</span><span class="sxs-lookup"><span data-stu-id="6a7f2-276">1</span></span>|  
|<span data-ttu-id="6a7f2-277">2</span><span class="sxs-lookup"><span data-stu-id="6a7f2-277">2</span></span>|  
|<span data-ttu-id="6a7f2-278">3</span><span class="sxs-lookup"><span data-stu-id="6a7f2-278">3</span></span>|  
|<span data-ttu-id="6a7f2-279">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="6a7f2-280">SELECT VALUE 和 SELECT</span><span class="sxs-lookup"><span data-stu-id="6a7f2-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="6a7f2-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="6a7f2-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="6a7f2-282">提供了 SELECT VALUE 子句以跳过隐式行构造。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-282">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="6a7f2-283">SELECT VALUE 子句中只能指定一项。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="6a7f2-284">当使用这样的子句、 SELECT 子句中的项会构造没有行包装器和所需形状的集合可生成，例如： `SELECT VALUE a`。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="6a7f2-285">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-285">Example:</span></span>  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="6a7f2-286">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-286">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-287">名称</span><span class="sxs-lookup"><span data-stu-id="6a7f2-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="6a7f2-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6a7f2-288">Adjustable Race</span></span>|  
|<span data-ttu-id="6a7f2-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6a7f2-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="6a7f2-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6a7f2-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="6a7f2-291">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="6a7f2-292">选择</span><span class="sxs-lookup"><span data-stu-id="6a7f2-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="6a7f2-293">还提供了用于构造任意行的行构造函数。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-293">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="6a7f2-294">SELECT 接受投影中的一个或多个元素，并生成含有字段的数据记录，例如：`SELECT a, b, c`。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="6a7f2-295">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-295">Example:</span></span>  
  
 <span data-ttu-id="6a7f2-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="6a7f2-297">名称</span><span class="sxs-lookup"><span data-stu-id="6a7f2-297">Name</span></span>|<span data-ttu-id="6a7f2-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="6a7f2-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="6a7f2-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6a7f2-299">Adjustable Race</span></span>|<span data-ttu-id="6a7f2-300">1</span><span class="sxs-lookup"><span data-stu-id="6a7f2-300">1</span></span>|  
|<span data-ttu-id="6a7f2-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6a7f2-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="6a7f2-302">879</span><span class="sxs-lookup"><span data-stu-id="6a7f2-302">879</span></span>|  
|<span data-ttu-id="6a7f2-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6a7f2-303">AWC Logo Cap</span></span>|<span data-ttu-id="6a7f2-304">712</span><span class="sxs-lookup"><span data-stu-id="6a7f2-304">712</span></span>|  
|<span data-ttu-id="6a7f2-305">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-305">...</span></span>|<span data-ttu-id="6a7f2-306">...</span><span class="sxs-lookup"><span data-stu-id="6a7f2-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="6a7f2-307">CASE 表达式</span><span class="sxs-lookup"><span data-stu-id="6a7f2-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="6a7f2-308">[Case 表达式](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)计算一组布尔表达式，以确定结果。</span><span class="sxs-lookup"><span data-stu-id="6a7f2-308">The [case expression](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="6a7f2-309">示例:</span><span class="sxs-lookup"><span data-stu-id="6a7f2-309">Example:</span></span>  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="6a7f2-310">输出：</span><span class="sxs-lookup"><span data-stu-id="6a7f2-310">Output:</span></span>  
  
|<span data-ttu-id="6a7f2-311">“值”</span><span class="sxs-lookup"><span data-stu-id="6a7f2-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6a7f2-312">true</span><span class="sxs-lookup"><span data-stu-id="6a7f2-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a7f2-313">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a7f2-313">See also</span></span>

- [<span data-ttu-id="6a7f2-314">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="6a7f2-314">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="6a7f2-315">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="6a7f2-315">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
