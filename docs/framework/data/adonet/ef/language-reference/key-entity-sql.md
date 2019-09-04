---
title: KEY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 44ab5352c3b2a94cb210c3de775d2347d2df7fe7
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250486"
---
# <a name="key-entity-sql"></a><span data-ttu-id="c4d51-102">KEY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c4d51-102">KEY (Entity SQL)</span></span>
<span data-ttu-id="c4d51-103">提取引用或实体表达式的键。</span><span class="sxs-lookup"><span data-stu-id="c4d51-103">Extracts the key of a reference or of an entity expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4d51-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4d51-104">Syntax</span></span>  
  
```  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a><span data-ttu-id="c4d51-105">备注</span><span class="sxs-lookup"><span data-stu-id="c4d51-105">Remarks</span></span>  
 <span data-ttu-id="c4d51-106">实体键按指定实体或实体引用的正确顺序包含键值。</span><span class="sxs-lookup"><span data-stu-id="c4d51-106">An entity key contains the key values in the correct order of the specified entity or entity reference.</span></span> <span data-ttu-id="c4d51-107">因为多个实体集可以基于相同的类型，所以同一个键可能出现在每个实体集中。</span><span class="sxs-lookup"><span data-stu-id="c4d51-107">Because multiple entity sets can be based on the same type, the same key might appear in each entity set.</span></span> <span data-ttu-id="c4d51-108">若要获取唯一引用，请使用 `REF`。</span><span class="sxs-lookup"><span data-stu-id="c4d51-108">To get a unique reference, use `REF`.</span></span> <span data-ttu-id="c4d51-109">KEY 运算符的返回类型为行类型，该行类型按相同顺序为实体的每个键包含一个字段。</span><span class="sxs-lookup"><span data-stu-id="c4d51-109">The return type of the KEY operator is a row type that includes one field for each key of the entity, in the same order.</span></span>  
  
 <span data-ttu-id="c4d51-110">在下面的示例中，键运算符传递对 BadOrder 实体的引用，并返回该引用的键部分。</span><span class="sxs-lookup"><span data-stu-id="c4d51-110">In the following example, the key operator is passed a reference to the BadOrder entity, and returns the key portion of that reference.</span></span> <span data-ttu-id="c4d51-111">在此示例中，一个记录类型恰好包含对应于 `Id` 属性的一个字段。</span><span class="sxs-lookup"><span data-stu-id="c4d51-111">In this case, a record type with exactly one field corresponding to the `Id` property.</span></span>  
  
```  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )   
from LOB.Orders as o  
```  
  
## <a name="example"></a><span data-ttu-id="c4d51-112">示例</span><span class="sxs-lookup"><span data-stu-id="c4d51-112">Example</span></span>  
 <span data-ttu-id="c4d51-113">下面的 Entity SQL 查询使用 KEY 运算符提取具有类型引用的表达式的键部分。</span><span class="sxs-lookup"><span data-stu-id="c4d51-113">The following Entity SQL query uses the KEY operator to extract the key portion of an expression with type reference.</span></span> <span data-ttu-id="c4d51-114">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="c4d51-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c4d51-115">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="c4d51-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="c4d51-116">[按照如何：执行返回 StructuralType 结果](../how-to-execute-a-query-that-returns-structuraltype-results.md)的查询。</span><span class="sxs-lookup"><span data-stu-id="c4d51-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="c4d51-117">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="c4d51-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#KEY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#key)]  
  
## <a name="see-also"></a><span data-ttu-id="c4d51-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4d51-118">See also</span></span>

- [<span data-ttu-id="c4d51-119">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="c4d51-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="c4d51-120">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="c4d51-120">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="c4d51-121">REF</span><span class="sxs-lookup"><span data-stu-id="c4d51-121">REF</span></span>](ref-entity-sql.md)
- [<span data-ttu-id="c4d51-122">DEREF</span><span class="sxs-lookup"><span data-stu-id="c4d51-122">DEREF</span></span>](deref-entity-sql.md)
