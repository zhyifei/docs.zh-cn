---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: 1ba562ba6542e6ab0d62f1f8348434ae4f4c9b13
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59305177"
---
# <a name="deref-entity-sql"></a><span data-ttu-id="57195-102">DEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="57195-102">DEREF (Entity SQL)</span></span>
<span data-ttu-id="57195-103">取消引用一个引用值，并生成该取消引用的结果。</span><span class="sxs-lookup"><span data-stu-id="57195-103">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57195-104">语法</span><span class="sxs-lookup"><span data-stu-id="57195-104">Syntax</span></span>  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a><span data-ttu-id="57195-105">自变量</span><span class="sxs-lookup"><span data-stu-id="57195-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="57195-106">任何返回集合的有效查询表达式。</span><span class="sxs-lookup"><span data-stu-id="57195-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57195-107">返回值</span><span class="sxs-lookup"><span data-stu-id="57195-107">Return Value</span></span>  
 <span data-ttu-id="57195-108">引用的实体的值。</span><span class="sxs-lookup"><span data-stu-id="57195-108">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57195-109">备注</span><span class="sxs-lookup"><span data-stu-id="57195-109">Remarks</span></span>  
 <span data-ttu-id="57195-110">DEREF 运算符取消引用一个引用值，并生成该取消引用的结果。</span><span class="sxs-lookup"><span data-stu-id="57195-110">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="57195-111">例如，如果`r`为 ref 类型引用\<T >，`Deref(r)`类型的表达式`T`生成的引用的实体`r`。</span><span class="sxs-lookup"><span data-stu-id="57195-111">For example, if `r` is a reference of type ref\<T>, `Deref(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="57195-112">如果引用值为 Null，或无关联（即，引用的目标不存在），则 DEREF 运算符的结果为 Null。</span><span class="sxs-lookup"><span data-stu-id="57195-112">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57195-113">示例</span><span class="sxs-lookup"><span data-stu-id="57195-113">Example</span></span>  
 <span data-ttu-id="57195-114">下面的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询使用 DEREF 运算符取消引用一个引用值，并生成该取消引用的结果。</span><span class="sxs-lookup"><span data-stu-id="57195-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="57195-115">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="57195-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="57195-116">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="57195-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="57195-117">按照中的过程[如何：执行返回 PrimitiveType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="57195-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="57195-118">将以下查询作为参数传递给 ExecutePrimitiveTypeQuery 方法：</span><span class="sxs-lookup"><span data-stu-id="57195-118">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="57195-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="57195-119">See also</span></span>

- [<span data-ttu-id="57195-120">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="57195-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="57195-121">REF</span><span class="sxs-lookup"><span data-stu-id="57195-121">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
- [<span data-ttu-id="57195-122">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="57195-122">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)
- [<span data-ttu-id="57195-123">KEY</span><span class="sxs-lookup"><span data-stu-id="57195-123">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)
- [<span data-ttu-id="57195-124">可以为 NULL 的结构化类型</span><span class="sxs-lookup"><span data-stu-id="57195-124">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
