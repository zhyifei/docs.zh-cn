---
title: KEY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 68ee7d512e0a3b5d912dc12c55be6f0135129225
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509193"
---
# <a name="key-entity-sql"></a><span data-ttu-id="9471a-102">KEY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9471a-102">KEY (Entity SQL)</span></span>
<span data-ttu-id="9471a-103">提取引用或实体表达式的键。</span><span class="sxs-lookup"><span data-stu-id="9471a-103">Extracts the key of a reference or of an entity expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9471a-104">语法</span><span class="sxs-lookup"><span data-stu-id="9471a-104">Syntax</span></span>  
  
```  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a><span data-ttu-id="9471a-105">备注</span><span class="sxs-lookup"><span data-stu-id="9471a-105">Remarks</span></span>  
 <span data-ttu-id="9471a-106">实体键按指定实体或实体引用的正确顺序包含键值。</span><span class="sxs-lookup"><span data-stu-id="9471a-106">An entity key contains the key values in the correct order of the specified entity or entity reference.</span></span> <span data-ttu-id="9471a-107">因为多个实体集可以基于相同的类型，所以同一个键可能出现在每个实体集中。</span><span class="sxs-lookup"><span data-stu-id="9471a-107">Because multiple entity sets can be based on the same type, the same key might appear in each entity set.</span></span> <span data-ttu-id="9471a-108">若要获取唯一引用，请使用 `REF`。</span><span class="sxs-lookup"><span data-stu-id="9471a-108">To get a unique reference, use `REF`.</span></span> <span data-ttu-id="9471a-109">KEY 运算符的返回类型为行类型，该行类型按相同顺序为实体的每个键包含一个字段。</span><span class="sxs-lookup"><span data-stu-id="9471a-109">The return type of the KEY operator is a row type that includes one field for each key of the entity, in the same order.</span></span>  
  
 <span data-ttu-id="9471a-110">在下面的示例中，键运算符传递对 BadOrder 实体的引用，并返回该引用的键部分。</span><span class="sxs-lookup"><span data-stu-id="9471a-110">In the following example, the key operator is passed a reference to the BadOrder entity, and returns the key portion of that reference.</span></span> <span data-ttu-id="9471a-111">在此示例中，一个记录类型恰好包含对应于 `Id` 属性的一个字段。</span><span class="sxs-lookup"><span data-stu-id="9471a-111">In this case, a record type with exactly one field corresponding to the `Id` property.</span></span>  
  
```  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )   
from LOB.Orders as o  
```  
  
## <a name="example"></a><span data-ttu-id="9471a-112">示例</span><span class="sxs-lookup"><span data-stu-id="9471a-112">Example</span></span>  
 <span data-ttu-id="9471a-113">下面的 Entity SQL 查询使用 KEY 运算符提取具有类型引用的表达式的键部分。</span><span class="sxs-lookup"><span data-stu-id="9471a-113">The following Entity SQL query uses the KEY operator to extract the key portion of an expression with type reference.</span></span> <span data-ttu-id="9471a-114">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="9471a-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9471a-115">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="9471a-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="9471a-116">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="9471a-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="9471a-117">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="9471a-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#KEY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#key)]  
  
## <a name="see-also"></a><span data-ttu-id="9471a-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9471a-118">See also</span></span>
- [<span data-ttu-id="9471a-119">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="9471a-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="9471a-120">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="9471a-120">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)
- [<span data-ttu-id="9471a-121">REF</span><span class="sxs-lookup"><span data-stu-id="9471a-121">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
- [<span data-ttu-id="9471a-122">DEREF</span><span class="sxs-lookup"><span data-stu-id="9471a-122">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)
