---
title: Entity SQL 快速参考
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: b4e3eaf8abd82b63fa2663b47f878ecfa9584897
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207066"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="6821e-102">Entity SQL 快速参考</span><span class="sxs-lookup"><span data-stu-id="6821e-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="6821e-103">本主题提供 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询的快速参考。</span><span class="sxs-lookup"><span data-stu-id="6821e-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="6821e-104">本主题中的查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="6821e-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="6821e-105">文本</span><span class="sxs-lookup"><span data-stu-id="6821e-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="6821e-106">String</span><span class="sxs-lookup"><span data-stu-id="6821e-106">String</span></span>  
 <span data-ttu-id="6821e-107">字符串分为 Unicode 字符串和非 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="6821e-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="6821e-108">Unicode 字符串前面附有 n。例如， `N'hello'`。</span><span class="sxs-lookup"><span data-stu-id="6821e-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="6821e-109">下面是非 Unicode 字符串的示例：</span><span class="sxs-lookup"><span data-stu-id="6821e-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="6821e-110">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-110">Output:</span></span>  
  
|<span data-ttu-id="6821e-111">“值”</span><span class="sxs-lookup"><span data-stu-id="6821e-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6821e-112">hello</span><span class="sxs-lookup"><span data-stu-id="6821e-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="6821e-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="6821e-113">DateTime</span></span>  
 <span data-ttu-id="6821e-114">在日期时间文本中，日期部分和时间部分是必须存在的。</span><span class="sxs-lookup"><span data-stu-id="6821e-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="6821e-115">这里没有默认值。</span><span class="sxs-lookup"><span data-stu-id="6821e-115">There are no default values.</span></span>  
  
 <span data-ttu-id="6821e-116">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-116">Example:</span></span>  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="6821e-117">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-117">Output:</span></span>  
  
|<span data-ttu-id="6821e-118">“值”</span><span class="sxs-lookup"><span data-stu-id="6821e-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6821e-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="6821e-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="6821e-120">整数</span><span class="sxs-lookup"><span data-stu-id="6821e-120">Integer</span></span>  
 <span data-ttu-id="6821e-121">整数文本可以为 Int32 (123)、UInt32 (123U)、Int64 (123L) 和 UInt64 (123UL) 类型。</span><span class="sxs-lookup"><span data-stu-id="6821e-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="6821e-122">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-122">Example:</span></span>  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="6821e-123">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-123">Output:</span></span>  
  
|<span data-ttu-id="6821e-124">“值”</span><span class="sxs-lookup"><span data-stu-id="6821e-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6821e-125">1</span><span class="sxs-lookup"><span data-stu-id="6821e-125">1</span></span>|  
|<span data-ttu-id="6821e-126">2</span><span class="sxs-lookup"><span data-stu-id="6821e-126">2</span></span>|  
|<span data-ttu-id="6821e-127">3</span><span class="sxs-lookup"><span data-stu-id="6821e-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="6821e-128">其他</span><span class="sxs-lookup"><span data-stu-id="6821e-128">Other</span></span>  
 <span data-ttu-id="6821e-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 支持的其他文字为、Guid、二进制、浮点/双精度型、十进制和 `null`。</span><span class="sxs-lookup"><span data-stu-id="6821e-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="6821e-130">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中的 null 文本视为与概念模型中的每一种其他类型兼容。</span><span class="sxs-lookup"><span data-stu-id="6821e-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="6821e-131">类型构造函数</span><span class="sxs-lookup"><span data-stu-id="6821e-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="6821e-132">ROW</span><span class="sxs-lookup"><span data-stu-id="6821e-132">ROW</span></span>  
 <span data-ttu-id="6821e-133">[行](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md)构造一个匿名的结构化类型 （记录） 值作为：</span><span class="sxs-lookup"><span data-stu-id="6821e-133">[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in:</span></span> `ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 <span data-ttu-id="6821e-134">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-134">Example:</span></span>  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 <span data-ttu-id="6821e-135">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-135">Output:</span></span>  
  
|<span data-ttu-id="6821e-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="6821e-136">ProductID</span></span>|<span data-ttu-id="6821e-137">名称</span><span class="sxs-lookup"><span data-stu-id="6821e-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="6821e-138">1</span><span class="sxs-lookup"><span data-stu-id="6821e-138">1</span></span>|<span data-ttu-id="6821e-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6821e-139">Adjustable Race</span></span>|  
|<span data-ttu-id="6821e-140">879</span><span class="sxs-lookup"><span data-stu-id="6821e-140">879</span></span>|<span data-ttu-id="6821e-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6821e-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="6821e-142">712</span><span class="sxs-lookup"><span data-stu-id="6821e-142">712</span></span>|<span data-ttu-id="6821e-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6821e-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="6821e-144">...</span><span class="sxs-lookup"><span data-stu-id="6821e-144">...</span></span>|<span data-ttu-id="6821e-145">...</span><span class="sxs-lookup"><span data-stu-id="6821e-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="6821e-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="6821e-146">MULTISET</span></span>  
 <span data-ttu-id="6821e-147">[多重集](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md)构造集合，如：</span><span class="sxs-lookup"><span data-stu-id="6821e-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 `MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`  
  
 <span data-ttu-id="6821e-148">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-148">Example:</span></span>  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="6821e-149">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-149">Output:</span></span>  
  
|<span data-ttu-id="6821e-150">ProductID</span><span class="sxs-lookup"><span data-stu-id="6821e-150">ProductID</span></span>|<span data-ttu-id="6821e-151">名称</span><span class="sxs-lookup"><span data-stu-id="6821e-151">Name</span></span>|<span data-ttu-id="6821e-152">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="6821e-152">ProductNumber</span></span>|<span data-ttu-id="6821e-153">…</span><span class="sxs-lookup"><span data-stu-id="6821e-153">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="6821e-154">842</span><span class="sxs-lookup"><span data-stu-id="6821e-154">842</span></span>|<span data-ttu-id="6821e-155">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="6821e-155">Touring-Panniers, Large</span></span>|<span data-ttu-id="6821e-156">PA-T100</span><span class="sxs-lookup"><span data-stu-id="6821e-156">PA-T100</span></span>|<span data-ttu-id="6821e-157">…</span><span class="sxs-lookup"><span data-stu-id="6821e-157">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="6821e-158">对象</span><span class="sxs-lookup"><span data-stu-id="6821e-158">Object</span></span>  
 <span data-ttu-id="6821e-159">[命名类型构造函数](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md)构造 （命名的） 用户定义的对象，如`person("abc", 12)`。</span><span class="sxs-lookup"><span data-stu-id="6821e-159">[Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="6821e-160">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-160">Example:</span></span>  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="6821e-161">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-161">Output:</span></span>  
  
|<span data-ttu-id="6821e-162">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="6821e-162">SalesOrderDetailID</span></span>|<span data-ttu-id="6821e-163">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="6821e-163">CarrierTrackingNumber</span></span>|<span data-ttu-id="6821e-164">OrderQty</span><span class="sxs-lookup"><span data-stu-id="6821e-164">OrderQty</span></span>|<span data-ttu-id="6821e-165">ProductID</span><span class="sxs-lookup"><span data-stu-id="6821e-165">ProductID</span></span>|<span data-ttu-id="6821e-166">...</span><span class="sxs-lookup"><span data-stu-id="6821e-166">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="6821e-167">1</span><span class="sxs-lookup"><span data-stu-id="6821e-167">1</span></span>|<span data-ttu-id="6821e-168">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="6821e-168">4911-403C-98</span></span>|<span data-ttu-id="6821e-169">1</span><span class="sxs-lookup"><span data-stu-id="6821e-169">1</span></span>|<span data-ttu-id="6821e-170">776</span><span class="sxs-lookup"><span data-stu-id="6821e-170">776</span></span>|<span data-ttu-id="6821e-171">...</span><span class="sxs-lookup"><span data-stu-id="6821e-171">...</span></span>|  
|<span data-ttu-id="6821e-172">2</span><span class="sxs-lookup"><span data-stu-id="6821e-172">2</span></span>|<span data-ttu-id="6821e-173">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="6821e-173">4911-403C-98</span></span>|<span data-ttu-id="6821e-174">3</span><span class="sxs-lookup"><span data-stu-id="6821e-174">3</span></span>|<span data-ttu-id="6821e-175">777</span><span class="sxs-lookup"><span data-stu-id="6821e-175">777</span></span>|<span data-ttu-id="6821e-176">...</span><span class="sxs-lookup"><span data-stu-id="6821e-176">...</span></span>|  
|<span data-ttu-id="6821e-177">...</span><span class="sxs-lookup"><span data-stu-id="6821e-177">...</span></span>|<span data-ttu-id="6821e-178">...</span><span class="sxs-lookup"><span data-stu-id="6821e-178">...</span></span>|<span data-ttu-id="6821e-179">...</span><span class="sxs-lookup"><span data-stu-id="6821e-179">...</span></span>|<span data-ttu-id="6821e-180">...</span><span class="sxs-lookup"><span data-stu-id="6821e-180">...</span></span>|<span data-ttu-id="6821e-181">...</span><span class="sxs-lookup"><span data-stu-id="6821e-181">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="6821e-182">参考资料</span><span class="sxs-lookup"><span data-stu-id="6821e-182">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="6821e-183">REF</span><span class="sxs-lookup"><span data-stu-id="6821e-183">REF</span></span>  
 <span data-ttu-id="6821e-184">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)创建对实体类型实例的引用。</span><span class="sxs-lookup"><span data-stu-id="6821e-184">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="6821e-185">例如，下面的查询返回对 Orders 实体集中每一个 Order 实体的引用：</span><span class="sxs-lookup"><span data-stu-id="6821e-185">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="6821e-186">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-186">Output:</span></span>  
  
|<span data-ttu-id="6821e-187">“值”</span><span class="sxs-lookup"><span data-stu-id="6821e-187">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6821e-188">1</span><span class="sxs-lookup"><span data-stu-id="6821e-188">1</span></span>|  
|<span data-ttu-id="6821e-189">2</span><span class="sxs-lookup"><span data-stu-id="6821e-189">2</span></span>|  
|<span data-ttu-id="6821e-190">3</span><span class="sxs-lookup"><span data-stu-id="6821e-190">3</span></span>|  
|<span data-ttu-id="6821e-191">...</span><span class="sxs-lookup"><span data-stu-id="6821e-191">...</span></span>|  
  
 <span data-ttu-id="6821e-192">下面的示例使用属性提取运算符 (.) 访问实体的属性。</span><span class="sxs-lookup"><span data-stu-id="6821e-192">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="6821e-193">在使用属性提取运算符时，引用将自动被反引用。</span><span class="sxs-lookup"><span data-stu-id="6821e-193">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="6821e-194">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-194">Example:</span></span>  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="6821e-195">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-195">Output:</span></span>  
  
|<span data-ttu-id="6821e-196">“值”</span><span class="sxs-lookup"><span data-stu-id="6821e-196">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6821e-197">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6821e-197">Adjustable Race</span></span>|  
|<span data-ttu-id="6821e-198">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6821e-198">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="6821e-199">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6821e-199">AWC Logo Cap</span></span>|  
|<span data-ttu-id="6821e-200">...</span><span class="sxs-lookup"><span data-stu-id="6821e-200">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="6821e-201">DEREF</span><span class="sxs-lookup"><span data-stu-id="6821e-201">DEREF</span></span>  
 <span data-ttu-id="6821e-202">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)取消引用一个引用值并生成的结果。</span><span class="sxs-lookup"><span data-stu-id="6821e-202">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="6821e-203">例如，下面的查询生成 Orders 实体集中每一个 Order 的 Order 实体：`SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`。</span><span class="sxs-lookup"><span data-stu-id="6821e-203">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="6821e-204">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-204">Example:</span></span>  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="6821e-205">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-205">Output:</span></span>  
  
|<span data-ttu-id="6821e-206">“值”</span><span class="sxs-lookup"><span data-stu-id="6821e-206">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6821e-207">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6821e-207">Adjustable Race</span></span>|  
|<span data-ttu-id="6821e-208">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6821e-208">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="6821e-209">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6821e-209">AWC Logo Cap</span></span>|  
|<span data-ttu-id="6821e-210">...</span><span class="sxs-lookup"><span data-stu-id="6821e-210">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="6821e-211">CREATEREF 和 KEY</span><span class="sxs-lookup"><span data-stu-id="6821e-211">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="6821e-212">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)创建传递键的引用。</span><span class="sxs-lookup"><span data-stu-id="6821e-212">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="6821e-213">[密钥](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)提取的密钥类型引用的表达式的一部分。</span><span class="sxs-lookup"><span data-stu-id="6821e-213">[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="6821e-214">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-214">Example:</span></span>  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="6821e-215">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-215">Output:</span></span>  
  
|<span data-ttu-id="6821e-216">ProductID</span><span class="sxs-lookup"><span data-stu-id="6821e-216">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="6821e-217">980</span><span class="sxs-lookup"><span data-stu-id="6821e-217">980</span></span>|  
|<span data-ttu-id="6821e-218">365</span><span class="sxs-lookup"><span data-stu-id="6821e-218">365</span></span>|  
|<span data-ttu-id="6821e-219">771</span><span class="sxs-lookup"><span data-stu-id="6821e-219">771</span></span>|  
|<span data-ttu-id="6821e-220">...</span><span class="sxs-lookup"><span data-stu-id="6821e-220">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="6821e-221">函数</span><span class="sxs-lookup"><span data-stu-id="6821e-221">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="6821e-222">规范</span><span class="sxs-lookup"><span data-stu-id="6821e-222">Canonical</span></span>  
 <span data-ttu-id="6821e-223">命名空间[规范函数](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)是 Edm 中，如`Edm.Length("string")`。</span><span class="sxs-lookup"><span data-stu-id="6821e-223">The namespace for [canonical functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="6821e-224">您无需指定命名空间，除非导入的另一个命名空间中包含与规范函数同名的函数。</span><span class="sxs-lookup"><span data-stu-id="6821e-224">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="6821e-225">如果两个命名空间有相同的函数，用户应指定完整名称。</span><span class="sxs-lookup"><span data-stu-id="6821e-225">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="6821e-226">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-226">Example:</span></span>  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="6821e-227">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-227">Output:</span></span>  
  
|<span data-ttu-id="6821e-228">NameLen</span><span class="sxs-lookup"><span data-stu-id="6821e-228">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="6821e-229">6</span><span class="sxs-lookup"><span data-stu-id="6821e-229">6</span></span>|  
|<span data-ttu-id="6821e-230">6</span><span class="sxs-lookup"><span data-stu-id="6821e-230">6</span></span>|  
|<span data-ttu-id="6821e-231">5</span><span class="sxs-lookup"><span data-stu-id="6821e-231">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="6821e-232">特定于 Microsoft 提供程序</span><span class="sxs-lookup"><span data-stu-id="6821e-232">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="6821e-233">[Microsoft 提供程序特定的函数](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)位于`SqlServer`命名空间。</span><span class="sxs-lookup"><span data-stu-id="6821e-233">[Microsoft provider-specific functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="6821e-234">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-234">Example:</span></span>  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="6821e-235">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-235">Output:</span></span>  
  
|<span data-ttu-id="6821e-236">EmailLen</span><span class="sxs-lookup"><span data-stu-id="6821e-236">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="6821e-237">27</span><span class="sxs-lookup"><span data-stu-id="6821e-237">27</span></span>|  
|<span data-ttu-id="6821e-238">27</span><span class="sxs-lookup"><span data-stu-id="6821e-238">27</span></span>|  
|<span data-ttu-id="6821e-239">26</span><span class="sxs-lookup"><span data-stu-id="6821e-239">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="6821e-240">命名空间</span><span class="sxs-lookup"><span data-stu-id="6821e-240">Namespaces</span></span>  
 <span data-ttu-id="6821e-241">[使用](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md)指定查询表达式中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="6821e-241">[USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="6821e-242">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-242">Example:</span></span>  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="6821e-243">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-243">Output:</span></span>  
  
|<span data-ttu-id="6821e-244">“值”</span><span class="sxs-lookup"><span data-stu-id="6821e-244">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6821e-245">aa</span><span class="sxs-lookup"><span data-stu-id="6821e-245">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="6821e-246">分页</span><span class="sxs-lookup"><span data-stu-id="6821e-246">Paging</span></span>  
 <span data-ttu-id="6821e-247">可以通过声明表示分页[跳过](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)并[限制](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)于子子句[ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)子句。</span><span class="sxs-lookup"><span data-stu-id="6821e-247">Paging can be expressed by declaring a [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses to the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="6821e-248">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-248">Example:</span></span>  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="6821e-249">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-249">Output:</span></span>  
  
|<span data-ttu-id="6821e-250">Id</span><span class="sxs-lookup"><span data-stu-id="6821e-250">ID</span></span>|<span data-ttu-id="6821e-251">名称</span><span class="sxs-lookup"><span data-stu-id="6821e-251">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="6821e-252">10</span><span class="sxs-lookup"><span data-stu-id="6821e-252">10</span></span>|<span data-ttu-id="6821e-253">Adina</span><span class="sxs-lookup"><span data-stu-id="6821e-253">Adina</span></span>|  
|<span data-ttu-id="6821e-254">11</span><span class="sxs-lookup"><span data-stu-id="6821e-254">11</span></span>|<span data-ttu-id="6821e-255">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="6821e-255">Agcaoili</span></span>|  
|<span data-ttu-id="6821e-256">12</span><span class="sxs-lookup"><span data-stu-id="6821e-256">12</span></span>|<span data-ttu-id="6821e-257">Aguilar</span><span class="sxs-lookup"><span data-stu-id="6821e-257">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="6821e-258">分组</span><span class="sxs-lookup"><span data-stu-id="6821e-258">Grouping</span></span>  
 <span data-ttu-id="6821e-259">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md)组指定为查询返回的对象 ([选择](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) 表达式的放置。</span><span class="sxs-lookup"><span data-stu-id="6821e-259">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="6821e-260">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-260">Example:</span></span>  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="6821e-261">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-261">Output:</span></span>  
  
|<span data-ttu-id="6821e-262">name</span><span class="sxs-lookup"><span data-stu-id="6821e-262">name</span></span>|  
|----------|  
|<span data-ttu-id="6821e-263">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="6821e-263">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="6821e-264">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="6821e-264">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="6821e-265">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="6821e-265">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="6821e-266">...</span><span class="sxs-lookup"><span data-stu-id="6821e-266">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="6821e-267">导航</span><span class="sxs-lookup"><span data-stu-id="6821e-267">Navigation</span></span>  
 <span data-ttu-id="6821e-268">关系导航运算符用于导航从一个实体（起始端）到另一个实体（结束端）的关系。</span><span class="sxs-lookup"><span data-stu-id="6821e-268">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="6821e-269">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)接受限定为关系类型\<命名空间 >。\<关系类型名称 >。</span><span class="sxs-lookup"><span data-stu-id="6821e-269">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="6821e-270">导航返回 Ref\<T > 如果的基数为 1 结束。</span><span class="sxs-lookup"><span data-stu-id="6821e-270">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="6821e-271">如果的基数为 n，集合结束 < Ref\<T >> 将返回。</span><span class="sxs-lookup"><span data-stu-id="6821e-271">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="6821e-272">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-272">Example:</span></span>  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="6821e-273">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-273">Output:</span></span>  
  
|<span data-ttu-id="6821e-274">AddressID</span><span class="sxs-lookup"><span data-stu-id="6821e-274">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="6821e-275">1</span><span class="sxs-lookup"><span data-stu-id="6821e-275">1</span></span>|  
|<span data-ttu-id="6821e-276">2</span><span class="sxs-lookup"><span data-stu-id="6821e-276">2</span></span>|  
|<span data-ttu-id="6821e-277">3</span><span class="sxs-lookup"><span data-stu-id="6821e-277">3</span></span>|  
|<span data-ttu-id="6821e-278">...</span><span class="sxs-lookup"><span data-stu-id="6821e-278">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="6821e-279">SELECT VALUE 和 SELECT</span><span class="sxs-lookup"><span data-stu-id="6821e-279">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="6821e-280">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="6821e-280">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="6821e-281">提供了 SELECT VALUE 子句以跳过隐式行构建。</span><span class="sxs-lookup"><span data-stu-id="6821e-281">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="6821e-282">SELECT VALUE 子句中只能指定一项。</span><span class="sxs-lookup"><span data-stu-id="6821e-282">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="6821e-283">当使用这样的子句、 SELECT 子句中的项会构造没有行包装器和所需形状的集合可生成，例如： `SELECT VALUE a`。</span><span class="sxs-lookup"><span data-stu-id="6821e-283">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="6821e-284">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-284">Example:</span></span>  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="6821e-285">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-285">Output:</span></span>  
  
|<span data-ttu-id="6821e-286">名称</span><span class="sxs-lookup"><span data-stu-id="6821e-286">Name</span></span>|  
|----------|  
|<span data-ttu-id="6821e-287">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6821e-287">Adjustable Race</span></span>|  
|<span data-ttu-id="6821e-288">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6821e-288">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="6821e-289">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6821e-289">AWC Logo Cap</span></span>|  
|<span data-ttu-id="6821e-290">...</span><span class="sxs-lookup"><span data-stu-id="6821e-290">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="6821e-291">选择</span><span class="sxs-lookup"><span data-stu-id="6821e-291">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="6821e-292">此外提供了用于构造任意行的行构造函数。</span><span class="sxs-lookup"><span data-stu-id="6821e-292">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="6821e-293">SELECT 接受投影中的一个或多个元素，并生成含有字段的数据记录，例如：`SELECT a, b, c`。</span><span class="sxs-lookup"><span data-stu-id="6821e-293">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="6821e-294">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-294">Example:</span></span>  
  
 <span data-ttu-id="6821e-295">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="6821e-295">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="6821e-296">名称</span><span class="sxs-lookup"><span data-stu-id="6821e-296">Name</span></span>|<span data-ttu-id="6821e-297">ProductID</span><span class="sxs-lookup"><span data-stu-id="6821e-297">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="6821e-298">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="6821e-298">Adjustable Race</span></span>|<span data-ttu-id="6821e-299">1</span><span class="sxs-lookup"><span data-stu-id="6821e-299">1</span></span>|  
|<span data-ttu-id="6821e-300">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="6821e-300">All-Purpose Bike Stand</span></span>|<span data-ttu-id="6821e-301">879</span><span class="sxs-lookup"><span data-stu-id="6821e-301">879</span></span>|  
|<span data-ttu-id="6821e-302">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="6821e-302">AWC Logo Cap</span></span>|<span data-ttu-id="6821e-303">712</span><span class="sxs-lookup"><span data-stu-id="6821e-303">712</span></span>|  
|<span data-ttu-id="6821e-304">...</span><span class="sxs-lookup"><span data-stu-id="6821e-304">...</span></span>|<span data-ttu-id="6821e-305">...</span><span class="sxs-lookup"><span data-stu-id="6821e-305">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="6821e-306">CASE 表达式</span><span class="sxs-lookup"><span data-stu-id="6821e-306">CASE EXPRESSION</span></span>  
 <span data-ttu-id="6821e-307">[Case 表达式](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)计算一组布尔表达式，以确定结果。</span><span class="sxs-lookup"><span data-stu-id="6821e-307">The [case expression](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="6821e-308">示例:</span><span class="sxs-lookup"><span data-stu-id="6821e-308">Example:</span></span>  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="6821e-309">输出：</span><span class="sxs-lookup"><span data-stu-id="6821e-309">Output:</span></span>  
  
|<span data-ttu-id="6821e-310">“值”</span><span class="sxs-lookup"><span data-stu-id="6821e-310">Value</span></span>|  
|-----------|  
|<span data-ttu-id="6821e-311">true</span><span class="sxs-lookup"><span data-stu-id="6821e-311">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6821e-312">请参阅</span><span class="sxs-lookup"><span data-stu-id="6821e-312">See also</span></span>

- [<span data-ttu-id="6821e-313">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="6821e-313">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="6821e-314">Entity SQL 概述</span><span class="sxs-lookup"><span data-stu-id="6821e-314">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
