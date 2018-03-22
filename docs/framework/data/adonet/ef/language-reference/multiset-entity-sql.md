---
title: MULTISET (Entity SQL)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 6389051ae1244a2a38699704c67217d9807fe7e4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="multiset-entity-sql"></a><span data-ttu-id="a1cba-102">MULTISET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a1cba-102">MULTISET (Entity SQL)</span></span>
<span data-ttu-id="a1cba-103">根据值列表创建多集的实例。</span><span class="sxs-lookup"><span data-stu-id="a1cba-103">Creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="a1cba-104">MULTISET 构造函数中的所有值都必须具有兼容类型 `T`。</span><span class="sxs-lookup"><span data-stu-id="a1cba-104">All the values in the MULTISET constructor must be of a compatible type `T`.</span></span> <span data-ttu-id="a1cba-105">不允许使用空的多集构造函数。</span><span class="sxs-lookup"><span data-stu-id="a1cba-105">Empty multiset constructors are not allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1cba-106">语法</span><span class="sxs-lookup"><span data-stu-id="a1cba-106">Syntax</span></span>  
  
```  
MULTISET ( expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a><span data-ttu-id="a1cba-107">自变量</span><span class="sxs-lookup"><span data-stu-id="a1cba-107">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="a1cba-108">任何有效的值列表。</span><span class="sxs-lookup"><span data-stu-id="a1cba-108">Any valid list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1cba-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a1cba-109">Return Value</span></span>  
 <span data-ttu-id="a1cba-110">类型多重集的集合\<T >。</span><span class="sxs-lookup"><span data-stu-id="a1cba-110">A collection of type MULTISET\<T>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1cba-111">备注</span><span class="sxs-lookup"><span data-stu-id="a1cba-111">Remarks</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="a1cba-112"> 提供了三种构造函数：行构造函数、对象构造函数和多集（或集合）构造函数。</span><span class="sxs-lookup"><span data-stu-id="a1cba-112"> provides three kinds of constructors: row constructors, object constructors, and multiset (or collection) constructors.</span></span> <span data-ttu-id="a1cba-113">有关详细信息，请参阅[构造类型](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="a1cba-113">For more information, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
 <span data-ttu-id="a1cba-114">多集构造函数根据值列表创建多集的实例。</span><span class="sxs-lookup"><span data-stu-id="a1cba-114">The multiset constructor creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="a1cba-115">该构造函数中的所有值都必须具有兼容类型。</span><span class="sxs-lookup"><span data-stu-id="a1cba-115">All the values in the constructor must be of a compatible type.</span></span>  
  
 <span data-ttu-id="a1cba-116">例如，下面的表达式创建整数的多集。</span><span class="sxs-lookup"><span data-stu-id="a1cba-116">For example, the following expression creates a multiset of integers.</span></span>  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
>  <span data-ttu-id="a1cba-117">仅当包装多集只有一个多集元素时才支持嵌套多集文本；例如 `{{1, 2, 3}}`。</span><span class="sxs-lookup"><span data-stu-id="a1cba-117">Nested multiset literals are only supported when a wrapping mutiset has a single multiset element; for example, `{{1, 2, 3}}`.</span></span> <span data-ttu-id="a1cba-118">当包装多集具有多个多集元素（如 `{{1, 2}, {3, 4}}`）时，不支持嵌套多集文本。</span><span class="sxs-lookup"><span data-stu-id="a1cba-118">When the wrapping multiset has multiple multiset elements (for example, `{{1, 2}, {3, 4}}`), nested multiset literals are not supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1cba-119">示例</span><span class="sxs-lookup"><span data-stu-id="a1cba-119">Example</span></span>  
 <span data-ttu-id="a1cba-120">下面的 Entity SQL 查询使用 MULTISET 运算符根据值列表创建多集的实例。</span><span class="sxs-lookup"><span data-stu-id="a1cba-120">The following Entity SQL query uses the MULTISET operator to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="a1cba-121">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="a1cba-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a1cba-122">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="a1cba-122">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a1cba-123">执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="a1cba-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="a1cba-124">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="a1cba-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a><span data-ttu-id="a1cba-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1cba-125">See Also</span></span>  
 [<span data-ttu-id="a1cba-126">构造类型</span><span class="sxs-lookup"><span data-stu-id="a1cba-126">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [<span data-ttu-id="a1cba-127">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="a1cba-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
