---
title: ROW (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 58f954d2a03e6cf1c3117ebe440513014149f819
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="row-entity-sql"></a><span data-ttu-id="89149-102">ROW (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="89149-102">ROW (Entity SQL)</span></span>
<span data-ttu-id="89149-103">从一个或多个值构造结构上类型化的匿名记录。</span><span class="sxs-lookup"><span data-stu-id="89149-103">Constructs anonymous, structurally typed records from one or more values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89149-104">语法</span><span class="sxs-lookup"><span data-stu-id="89149-104">Syntax</span></span>  
  
```  
ROW ( expression [ AS alias ] [,...] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="89149-105">自变量</span><span class="sxs-lookup"><span data-stu-id="89149-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="89149-106">任何有效的查询表达式，该表达式返回要在行类型中构造的值。</span><span class="sxs-lookup"><span data-stu-id="89149-106">Any valid query expression that returns a value to construct in a row type.</span></span>  
  
 `alias`  
 <span data-ttu-id="89149-107">为在行类型中指定的值指定别名。</span><span class="sxs-lookup"><span data-stu-id="89149-107">Specifies an alias for the value specified in a row type.</span></span> <span data-ttu-id="89149-108">如果未提供别名，则 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 会尝试基于 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 别名生成规则来生成别名。</span><span class="sxs-lookup"><span data-stu-id="89149-108">If an alias is not provided, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to generate an alias based on the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alias generation rules.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89149-109">返回值</span><span class="sxs-lookup"><span data-stu-id="89149-109">Return Value</span></span>  
 <span data-ttu-id="89149-110">一个行类型。</span><span class="sxs-lookup"><span data-stu-id="89149-110">A row type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89149-111">备注</span><span class="sxs-lookup"><span data-stu-id="89149-111">Remarks</span></span>  
 <span data-ttu-id="89149-112">使用 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中的行构造函数可以从一个或多个值构造结构上类型化的匿名记录。</span><span class="sxs-lookup"><span data-stu-id="89149-112">You use row constructors in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="89149-113">行构造函数的结果类型为行类型，其字段类型对应于用于构造该行的值的类型。</span><span class="sxs-lookup"><span data-stu-id="89149-113">The result type of a row constructor is a row type whose field types correspond to the types of the values that were used to construct the row.</span></span> <span data-ttu-id="89149-114">例如，下面的表达式构造一个类型为 `Record(a int, b string, c int)`的值。</span><span class="sxs-lookup"><span data-stu-id="89149-114">For example, the following expression constructs a value of type `Record(a int, b string, c int)`.</span></span>  
  
```  
ROW(1 AS a, "abc" AS b, a+34 AS c)  
```  
  
 <span data-ttu-id="89149-115">如果没有为行构造函数中的表达式提供别名，则实体框架会尝试生成一个别名。</span><span class="sxs-lookup"><span data-stu-id="89149-115">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="89149-116">有关更多信息，请参见 [标识符](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md) 主题中的“别名规则”一节。</span><span class="sxs-lookup"><span data-stu-id="89149-116">For more information, see the "Aliasing Rules" section of the [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md) topic.</span></span>  
  
 <span data-ttu-id="89149-117">以下规则适用于在行构造函数中指定表达式别名：</span><span class="sxs-lookup"><span data-stu-id="89149-117">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
-   <span data-ttu-id="89149-118">行构造函数中的表达式不能引用同一构造函数中的其他别名。</span><span class="sxs-lookup"><span data-stu-id="89149-118">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
-   <span data-ttu-id="89149-119">同一行构造函数中的两个表达式不能具有相同别名。</span><span class="sxs-lookup"><span data-stu-id="89149-119">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="89149-120">有关查询构造函数的详细信息，请参阅[构造类型](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="89149-120">For more information about query constructors, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89149-121">示例</span><span class="sxs-lookup"><span data-stu-id="89149-121">Example</span></span>  
 <span data-ttu-id="89149-122">下面的 Entity SQL 查询使用 ROW 运算符构造结构上类型化的匿名记录。</span><span class="sxs-lookup"><span data-stu-id="89149-122">The following Entity SQL query uses the ROW operator to construct anonymous, structurally typed records.</span></span> <span data-ttu-id="89149-123">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="89149-123">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="89149-124">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="89149-124">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="89149-125">执行 [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="89149-125">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="89149-126">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="89149-126">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ROW](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#row)]  
  
## <a name="see-also"></a><span data-ttu-id="89149-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="89149-127">See Also</span></span>  
 [<span data-ttu-id="89149-128">构造类型</span><span class="sxs-lookup"><span data-stu-id="89149-128">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [<span data-ttu-id="89149-129">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="89149-129">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="89149-130">类型定义</span><span class="sxs-lookup"><span data-stu-id="89149-130">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
