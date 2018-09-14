---
title: OFTYPE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 6d259ca7-bbf0-40f8-a154-181d25c0d67e
ms.openlocfilehash: c90950e11cbfca7a49b505c1654d08be504990e1
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45596983"
---
# <a name="oftype-entity-sql"></a><span data-ttu-id="892a5-102">OFTYPE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="892a5-102">OFTYPE (Entity SQL)</span></span>
<span data-ttu-id="892a5-103">从查询表达式返回特定类型的对象集合。</span><span class="sxs-lookup"><span data-stu-id="892a5-103">Returns a collection of objects from a query expression that is of a specific type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="892a5-104">语法</span><span class="sxs-lookup"><span data-stu-id="892a5-104">Syntax</span></span>  
  
```  
OFTYPE ( expression, [ONLY] test_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="892a5-105">自变量</span><span class="sxs-lookup"><span data-stu-id="892a5-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="892a5-106">返回对象集合的任何有效的查询表达式。</span><span class="sxs-lookup"><span data-stu-id="892a5-106">Any valid query expression that returns a collection of objects.</span></span>  
  
 `test_type`  
 <span data-ttu-id="892a5-107">要对 `expression` 返回的每个对象进行测试的类型。</span><span class="sxs-lookup"><span data-stu-id="892a5-107">The type to test each object returned by `expression` against.</span></span> <span data-ttu-id="892a5-108">该类型必须由命名空间进行限定。</span><span class="sxs-lookup"><span data-stu-id="892a5-108">The type must be qualified by a namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="892a5-109">返回值</span><span class="sxs-lookup"><span data-stu-id="892a5-109">Return Value</span></span>  
 <span data-ttu-id="892a5-110">`test_type`类型或 `test_type`的基类型或派生类型的对象集合。</span><span class="sxs-lookup"><span data-stu-id="892a5-110">A collection of objects that are of type `test_type`, or a base type or derived type of `test_type`.</span></span> <span data-ttu-id="892a5-111">如果指定 ONLY，则仅返回 `test_type` 的实例或空集合。</span><span class="sxs-lookup"><span data-stu-id="892a5-111">If ONLY is specified, only instances of the `test_type` or an empty collection will be returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="892a5-112">备注</span><span class="sxs-lookup"><span data-stu-id="892a5-112">Remarks</span></span>  
 <span data-ttu-id="892a5-113">`OFTYPE` 表达式指定一个类型表达式，此表达式旨在针对集合的每个元素执行类型测试。</span><span class="sxs-lookup"><span data-stu-id="892a5-113">An `OFTYPE` expression specifies a type expression that is issued to perform a type test against each element of a collection.</span></span>  <span data-ttu-id="892a5-114">`OFTYPE` 表达式生成指定类型的新集合，其中仅包含等效于该类型或其子类型的元素。</span><span class="sxs-lookup"><span data-stu-id="892a5-114">The `OFTYPE` expression produces a new collection of the specified type containing only those elements that were either equivalent to that type or a sub-type of it.</span></span>  
  
 <span data-ttu-id="892a5-115">`OFTYPE` 表达式是下面的查询表达式的缩写形式：</span><span class="sxs-lookup"><span data-stu-id="892a5-115">An `OFTYPE` expression is an abbreviation of the following query expression:</span></span>  
  
```  
select value treat(t as T) from ts as t where t is of (T)  
```  
  
 <span data-ttu-id="892a5-116">如果 Manager 是 Employee 的子类型，则以下表达式将从员工集合生成仅包含经理的集合：</span><span class="sxs-lookup"><span data-stu-id="892a5-116">Given that a Manager is a subtype of Employee, the following expression produces a collection of only managers from a collection of employees:</span></span>  
  
```  
OfType(employees, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="892a5-117">还可以使用类型筛选器向上转换集合类型：</span><span class="sxs-lookup"><span data-stu-id="892a5-117">It is also possible to up cast a collection using the type filter:</span></span>  
  
```  
OfType(executives, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="892a5-118">因为所有执行官都是经理，所以结果集合仍然包含原来的所有执行官，但该集合现在的类型却是经理的集合。</span><span class="sxs-lookup"><span data-stu-id="892a5-118">Since all executives are managers, the resulting collection still contains all the original executives, though the collection is now typed as a collection of managers.</span></span>  
  
 <span data-ttu-id="892a5-119">下表显示了 `OFTYPE` 运算符对于某些模式的行为。</span><span class="sxs-lookup"><span data-stu-id="892a5-119">The following table shows the behavior of the `OFTYPE` operator over some patterns.</span></span> <span data-ttu-id="892a5-120">所有异常都在调用提供程序之前从客户端引发：</span><span class="sxs-lookup"><span data-stu-id="892a5-120">All exceptions are thrown from the client side before the provider is invoked:</span></span>  
  
|<span data-ttu-id="892a5-121">模式</span><span class="sxs-lookup"><span data-stu-id="892a5-121">Pattern</span></span>|<span data-ttu-id="892a5-122">行为</span><span class="sxs-lookup"><span data-stu-id="892a5-122">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="892a5-123">OFTYPE(Collection(EntityType), EntityType)</span><span class="sxs-lookup"><span data-stu-id="892a5-123">OFTYPE(Collection(EntityType), EntityType)</span></span>|<span data-ttu-id="892a5-124">Collection(EntityType)</span><span class="sxs-lookup"><span data-stu-id="892a5-124">Collection(EntityType)</span></span>|  
|<span data-ttu-id="892a5-125">OFTYPE(Collection(ComplexType), ComplexType)</span><span class="sxs-lookup"><span data-stu-id="892a5-125">OFTYPE(Collection(ComplexType), ComplexType)</span></span>|<span data-ttu-id="892a5-126">引发</span><span class="sxs-lookup"><span data-stu-id="892a5-126">Throws</span></span>|  
|<span data-ttu-id="892a5-127">OFTYPE(Collection(RowType), RowType)</span><span class="sxs-lookup"><span data-stu-id="892a5-127">OFTYPE(Collection(RowType), RowType)</span></span>|<span data-ttu-id="892a5-128">引发</span><span class="sxs-lookup"><span data-stu-id="892a5-128">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="892a5-129">示例</span><span class="sxs-lookup"><span data-stu-id="892a5-129">Example</span></span>  
 <span data-ttu-id="892a5-130">下面的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询使用 OFTYPE 运算符从 Course 对象集合返回 OnsiteCourse 对象集合。</span><span class="sxs-lookup"><span data-stu-id="892a5-130">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the OFTYPE operator to return a collection of OnsiteCourse objects from a collection of Course objects.</span></span> <span data-ttu-id="892a5-131">查询基于[School 模型](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac)。</span><span class="sxs-lookup"><span data-stu-id="892a5-131">The query is based on the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OFTYPE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#oftype)]  
  
## <a name="see-also"></a><span data-ttu-id="892a5-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="892a5-132">See Also</span></span>  
 [<span data-ttu-id="892a5-133">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="892a5-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
