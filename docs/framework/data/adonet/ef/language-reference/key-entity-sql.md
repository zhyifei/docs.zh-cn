---
title: KEY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 14c0b5d273b26c71c9c63e8bbbcef863ac95a5f3
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319702"
---
# <a name="key-entity-sql"></a><span data-ttu-id="ba79e-102">KEY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ba79e-102">KEY (Entity SQL)</span></span>
<span data-ttu-id="ba79e-103">提取引用或实体表达式的键。</span><span class="sxs-lookup"><span data-stu-id="ba79e-103">Extracts the key of a reference or of an entity expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba79e-104">语法</span><span class="sxs-lookup"><span data-stu-id="ba79e-104">Syntax</span></span>  
  
```sql  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a><span data-ttu-id="ba79e-105">备注</span><span class="sxs-lookup"><span data-stu-id="ba79e-105">Remarks</span></span>  
 <span data-ttu-id="ba79e-106">实体键按指定实体或实体引用的正确顺序包含键值。</span><span class="sxs-lookup"><span data-stu-id="ba79e-106">An entity key contains the key values in the correct order of the specified entity or entity reference.</span></span> <span data-ttu-id="ba79e-107">因为多个实体集可以基于相同的类型，所以同一个键可能出现在每个实体集中。</span><span class="sxs-lookup"><span data-stu-id="ba79e-107">Because multiple entity sets can be based on the same type, the same key might appear in each entity set.</span></span> <span data-ttu-id="ba79e-108">若要获取唯一引用，请使用 `REF`。</span><span class="sxs-lookup"><span data-stu-id="ba79e-108">To get a unique reference, use `REF`.</span></span> <span data-ttu-id="ba79e-109">KEY 运算符的返回类型为行类型，该行类型按相同顺序为实体的每个键包含一个字段。</span><span class="sxs-lookup"><span data-stu-id="ba79e-109">The return type of the KEY operator is a row type that includes one field for each key of the entity, in the same order.</span></span>  
  
 <span data-ttu-id="ba79e-110">在下面的示例中，键运算符传递对 BadOrder 实体的引用，并返回该引用的键部分。</span><span class="sxs-lookup"><span data-stu-id="ba79e-110">In the following example, the key operator is passed a reference to the BadOrder entity, and returns the key portion of that reference.</span></span> <span data-ttu-id="ba79e-111">在此示例中，一个记录类型恰好包含对应于 `Id` 属性的一个字段。</span><span class="sxs-lookup"><span data-stu-id="ba79e-111">In this case, a record type with exactly one field corresponding to the `Id` property.</span></span>  
  
```sql  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )   
from LOB.Orders as o  
```  
  
## <a name="example"></a><span data-ttu-id="ba79e-112">示例</span><span class="sxs-lookup"><span data-stu-id="ba79e-112">Example</span></span>  
 <span data-ttu-id="ba79e-113">下面的 Entity SQL 查询使用 KEY 运算符提取具有类型引用的表达式的键部分。</span><span class="sxs-lookup"><span data-stu-id="ba79e-113">The following Entity SQL query uses the KEY operator to extract the key portion of an expression with type reference.</span></span> <span data-ttu-id="ba79e-114">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="ba79e-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ba79e-115">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="ba79e-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ba79e-116">执行 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="ba79e-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ba79e-117">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="ba79e-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#KEY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#key)]  
  
## <a name="see-also"></a><span data-ttu-id="ba79e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba79e-118">See also</span></span>

- [<span data-ttu-id="ba79e-119">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="ba79e-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="ba79e-120">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="ba79e-120">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="ba79e-121">REF</span><span class="sxs-lookup"><span data-stu-id="ba79e-121">REF</span></span>](ref-entity-sql.md)
- [<span data-ttu-id="ba79e-122">DEREF</span><span class="sxs-lookup"><span data-stu-id="ba79e-122">DEREF</span></span>](deref-entity-sql.md)
