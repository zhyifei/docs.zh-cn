---
title: REF (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 226a14daa706f6cf0481b752fa03dc95db3eff81
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="ref-entity-sql"></a><span data-ttu-id="ec6e3-102">REF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ec6e3-102">REF (Entity SQL)</span></span>
<span data-ttu-id="ec6e3-103">返回对实体实例的引用。</span><span class="sxs-lookup"><span data-stu-id="ec6e3-103">Returns a reference to an entity instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec6e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="ec6e3-104">Syntax</span></span>  
  
```  
REF( expression )   
```  
  
## <a name="arguments"></a><span data-ttu-id="ec6e3-105">自变量</span><span class="sxs-lookup"><span data-stu-id="ec6e3-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ec6e3-106">产生实体类型实例的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="ec6e3-106">Any valid expression that yields an instance of an entity type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec6e3-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ec6e3-107">Return Value</span></span>  
 <span data-ttu-id="ec6e3-108">对指定实体实例的引用。</span><span class="sxs-lookup"><span data-stu-id="ec6e3-108">A reference to the specified entity instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec6e3-109">备注</span><span class="sxs-lookup"><span data-stu-id="ec6e3-109">Remarks</span></span>  
 <span data-ttu-id="ec6e3-110">实体引用由实体键和实体集名称组成。</span><span class="sxs-lookup"><span data-stu-id="ec6e3-110">An entity reference consists of the entity key and an entity set name.</span></span> <span data-ttu-id="ec6e3-111">不同的实体集可以基于相同的实体类型，因此一个特定实体键可以出现在多个实体集中。</span><span class="sxs-lookup"><span data-stu-id="ec6e3-111">Because different entity sets can be based on the same entity type, a particular entity key can appear in multiple entity sets.</span></span> <span data-ttu-id="ec6e3-112">但是，实体引用始终是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ec6e3-112">However, an entity reference is always unique.</span></span> <span data-ttu-id="ec6e3-113">如果输入表达式表示一个持久化实体，则会返回对此实体的引用。</span><span class="sxs-lookup"><span data-stu-id="ec6e3-113">If the input expression represents a persisted entity, a reference to this entity will be returned.</span></span> <span data-ttu-id="ec6e3-114">如果输入表达式不是一个持久化实体，则会返回空引用。</span><span class="sxs-lookup"><span data-stu-id="ec6e3-114">If the input expression is not a persisted entity, a null reference will be returned.</span></span>  
  
 <span data-ttu-id="ec6e3-115">如果使用属性提取运算符 (.) 访问实体的属性，则会自动取消引用。</span><span class="sxs-lookup"><span data-stu-id="ec6e3-115">If the property extraction operator (.) is used to access a property of an entity, the reference is automatically dereferenced.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec6e3-116">示例</span><span class="sxs-lookup"><span data-stu-id="ec6e3-116">Example</span></span>  
 <span data-ttu-id="ec6e3-117">下面的 Entity SQL 查询使用 REF 运算符返回输入实体参数的引用。</span><span class="sxs-lookup"><span data-stu-id="ec6e3-117">The following Entity SQL query uses the REF operator to return the reference for an input entity argument.</span></span> <span data-ttu-id="ec6e3-118">由于使用属性提取运算符 (.) 访问 Product 实体的属性，同一查询会取消引用。</span><span class="sxs-lookup"><span data-stu-id="ec6e3-118">The same query dereferences the reference because we are using a property extraction operation (.) to access a property of the Product entity.</span></span> <span data-ttu-id="ec6e3-119">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="ec6e3-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ec6e3-120">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="ec6e3-120">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ec6e3-121">按照中的步骤[如何： 执行查询该返回 PrimitiveType 结果](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="ec6e3-121">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="ec6e3-122">将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="ec6e3-122">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## <a name="see-also"></a><span data-ttu-id="ec6e3-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec6e3-123">See Also</span></span>  
 [<span data-ttu-id="ec6e3-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="ec6e3-124">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [<span data-ttu-id="ec6e3-125">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="ec6e3-125">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [<span data-ttu-id="ec6e3-126">KEY</span><span class="sxs-lookup"><span data-stu-id="ec6e3-126">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="ec6e3-127">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="ec6e3-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="ec6e3-128">类型定义</span><span class="sxs-lookup"><span data-stu-id="ec6e3-128">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
