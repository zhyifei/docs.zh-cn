---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: 27fc23a2be47ea00eff20aa8d2f559af5ae90387
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833896"
---
# <a name="deref-entity-sql"></a><span data-ttu-id="f3af3-102">DEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f3af3-102">DEREF (Entity SQL)</span></span>
<span data-ttu-id="f3af3-103">取消引用一个引用值，并生成该取消引用的结果。</span><span class="sxs-lookup"><span data-stu-id="f3af3-103">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3af3-104">语法</span><span class="sxs-lookup"><span data-stu-id="f3af3-104">Syntax</span></span>  
  
```sql  
SELECT DEREF ( o.expression ) FROM Table AS o;
```  
  
## <a name="arguments"></a><span data-ttu-id="f3af3-105">参数</span><span class="sxs-lookup"><span data-stu-id="f3af3-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="f3af3-106">任何返回集合的有效查询表达式。</span><span class="sxs-lookup"><span data-stu-id="f3af3-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3af3-107">返回值</span><span class="sxs-lookup"><span data-stu-id="f3af3-107">Return Value</span></span>  
 <span data-ttu-id="f3af3-108">引用的实体的值。</span><span class="sxs-lookup"><span data-stu-id="f3af3-108">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3af3-109">备注</span><span class="sxs-lookup"><span data-stu-id="f3af3-109">Remarks</span></span>  
 <span data-ttu-id="f3af3-110">DEREF 运算符取消引用一个引用值，并生成该取消引用的结果。</span><span class="sxs-lookup"><span data-stu-id="f3af3-110">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="f3af3-111">例如，如果 `r` 是引用类型引用\<T >，则 `Deref(r)` 是 `T` 类型的表达式，该表达式生成由 `r`引用的实体。</span><span class="sxs-lookup"><span data-stu-id="f3af3-111">For example, if `r` is a reference of type ref\<T>, `Deref(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="f3af3-112">如果引用值为 Null，或无关联（即，引用的目标不存在），则 DEREF 运算符的结果为 Null。</span><span class="sxs-lookup"><span data-stu-id="f3af3-112">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3af3-113">示例</span><span class="sxs-lookup"><span data-stu-id="f3af3-113">Example</span></span>  
 <span data-ttu-id="f3af3-114">下面的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询使用 DEREF 运算符取消引用一个引用值，并生成该取消引用的结果。</span><span class="sxs-lookup"><span data-stu-id="f3af3-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="f3af3-115">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="f3af3-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f3af3-116">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="f3af3-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f3af3-117">按照[如何：执行返回 PrimitiveType 结果的查询](../how-to-execute-a-query-that-returns-primitivetype-results.md)中的过程进行操作。</span><span class="sxs-lookup"><span data-stu-id="f3af3-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="f3af3-118">将以下查询作为参数传递给 ExecutePrimitiveTypeQuery 方法：</span><span class="sxs-lookup"><span data-stu-id="f3af3-118">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#DEREF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="f3af3-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3af3-119">See also</span></span>

- [<span data-ttu-id="f3af3-120">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="f3af3-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="f3af3-121">REF</span><span class="sxs-lookup"><span data-stu-id="f3af3-121">REF</span></span>](ref-entity-sql.md)
- [<span data-ttu-id="f3af3-122">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="f3af3-122">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="f3af3-123">KEY</span><span class="sxs-lookup"><span data-stu-id="f3af3-123">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="f3af3-124">可以为 NULL 的结构化类型</span><span class="sxs-lookup"><span data-stu-id="f3af3-124">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
