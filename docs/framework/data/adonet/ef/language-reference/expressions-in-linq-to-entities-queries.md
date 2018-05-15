---
title: LINQ to Entities 查询中的表达式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: f9230e9b5ac0c906652c03111b82df5147267143
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="6df67-102">LINQ to Entities 查询中的表达式</span><span class="sxs-lookup"><span data-stu-id="6df67-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="6df67-103">表达式是求值结果可以为单个值、对象、方法或命名空间的一段代码。</span><span class="sxs-lookup"><span data-stu-id="6df67-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="6df67-104">表达式可以包含文本值、方法调用、运算符及其操作数，或者简单名称。</span><span class="sxs-lookup"><span data-stu-id="6df67-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="6df67-105">简单名称可以是变量名、类型成员名、方法参数名、命名空间名或类型名。</span><span class="sxs-lookup"><span data-stu-id="6df67-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="6df67-106">表达式可以使用运算符（运算符又可使用其他表达式作为参数）或方法调用（方法调用的参数又可以是其他方法调用）。</span><span class="sxs-lookup"><span data-stu-id="6df67-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="6df67-107">因此，表达式可以非常简单，也可以极其复杂。</span><span class="sxs-lookup"><span data-stu-id="6df67-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="6df67-108">在 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 查询中，表达式可以包含 <xref:System.Linq.Expressions> 命名空间中的类型所允许的任何内容，包括 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="6df67-108">In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="6df67-109">可在 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 查询中使用的表达式是可用来查询 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] 的表达式的超集。</span><span class="sxs-lookup"><span data-stu-id="6df67-109">The expressions that can be used in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries are a superset of the expressions that can be used to query the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="6df67-110">对 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] 的查询中使用的表达式仅限于 `ObjectQuery<T>` 和基础数据源所支持的运算。</span><span class="sxs-lookup"><span data-stu-id="6df67-110">Expressions that are part of queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="6df67-111">在下面的示例中，`Where` 子句中的比较运算就是一个表达式：</span><span class="sxs-lookup"><span data-stu-id="6df67-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  <span data-ttu-id="6df67-112">特定的语言构造（如 C# `unchecked`）在 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 中没有意义。</span><span class="sxs-lookup"><span data-stu-id="6df67-112">Specific language constructs, such as C# `unchecked`, have no meaning in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6df67-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="6df67-113">In This Section</span></span>  
 [<span data-ttu-id="6df67-114">常量表达式</span><span class="sxs-lookup"><span data-stu-id="6df67-114">Constant Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [<span data-ttu-id="6df67-115">比较表达式</span><span class="sxs-lookup"><span data-stu-id="6df67-115">Comparison Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [<span data-ttu-id="6df67-116">NULL 比较</span><span class="sxs-lookup"><span data-stu-id="6df67-116">Null Comparisons</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [<span data-ttu-id="6df67-117">初始化表达式</span><span class="sxs-lookup"><span data-stu-id="6df67-117">Initialization Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [<span data-ttu-id="6df67-118">导航属性</span><span class="sxs-lookup"><span data-stu-id="6df67-118">Navigation Properties</span></span>](http://msdn.microsoft.com/library/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
  
## <a name="see-also"></a><span data-ttu-id="6df67-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="6df67-119">See Also</span></span>  
 [<span data-ttu-id="6df67-120">ADO.NET 实体框架</span><span class="sxs-lookup"><span data-stu-id="6df67-120">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
