---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 40a5afd7eb99dba7cae8fe14ed0a45213fda94a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149942"
---
# <a name="ref-entity-sql"></a><span data-ttu-id="2d490-102">REF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2d490-102">REF (Entity SQL)</span></span>
<span data-ttu-id="2d490-103">返回对实体实例的引用。</span><span class="sxs-lookup"><span data-stu-id="2d490-103">Returns a reference to an entity instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d490-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d490-104">Syntax</span></span>  
  
```sql  
REF( expression )
```  
  
## <a name="arguments"></a><span data-ttu-id="2d490-105">参数</span><span class="sxs-lookup"><span data-stu-id="2d490-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2d490-106">产生实体类型实例的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="2d490-106">Any valid expression that yields an instance of an entity type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d490-107">返回值</span><span class="sxs-lookup"><span data-stu-id="2d490-107">Return Value</span></span>  
 <span data-ttu-id="2d490-108">对指定实体实例的引用。</span><span class="sxs-lookup"><span data-stu-id="2d490-108">A reference to the specified entity instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d490-109">备注</span><span class="sxs-lookup"><span data-stu-id="2d490-109">Remarks</span></span>  
 <span data-ttu-id="2d490-110">实体引用由实体键和实体集名称组成。</span><span class="sxs-lookup"><span data-stu-id="2d490-110">An entity reference consists of the entity key and an entity set name.</span></span> <span data-ttu-id="2d490-111">不同的实体集可以基于相同的实体类型，因此一个特定实体键可以出现在多个实体集中。</span><span class="sxs-lookup"><span data-stu-id="2d490-111">Because different entity sets can be based on the same entity type, a particular entity key can appear in multiple entity sets.</span></span> <span data-ttu-id="2d490-112">但是，实体引用始终是唯一的。</span><span class="sxs-lookup"><span data-stu-id="2d490-112">However, an entity reference is always unique.</span></span> <span data-ttu-id="2d490-113">如果输入表达式表示一个持久化实体，则会返回对此实体的引用。</span><span class="sxs-lookup"><span data-stu-id="2d490-113">If the input expression represents a persisted entity, a reference to this entity will be returned.</span></span> <span data-ttu-id="2d490-114">如果输入表达式不是一个持久化实体，则会返回空引用。</span><span class="sxs-lookup"><span data-stu-id="2d490-114">If the input expression is not a persisted entity, a null reference will be returned.</span></span>  
  
 <span data-ttu-id="2d490-115">如果使用属性提取运算符 (.) 访问实体的属性，则会自动取消引用。</span><span class="sxs-lookup"><span data-stu-id="2d490-115">If the property extraction operator (.) is used to access a property of an entity, the reference is automatically dereferenced.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d490-116">示例</span><span class="sxs-lookup"><span data-stu-id="2d490-116">Example</span></span>  
 <span data-ttu-id="2d490-117">下面的 Entity SQL 查询使用 REF 运算符返回输入实体参数的引用。</span><span class="sxs-lookup"><span data-stu-id="2d490-117">The following Entity SQL query uses the REF operator to return the reference for an input entity argument.</span></span> <span data-ttu-id="2d490-118">由于使用属性提取运算符 (.) 访问 Product 实体的属性，同一查询会取消引用。</span><span class="sxs-lookup"><span data-stu-id="2d490-118">The same query dereferences the reference because we are using a property extraction operation (.) to access a property of the Product entity.</span></span> <span data-ttu-id="2d490-119">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="2d490-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2d490-120">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="2d490-120">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2d490-121">按照["如何执行"中的过程：执行返回基元类型结果的查询](../how-to-execute-a-query-that-returns-primitivetype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="2d490-121">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="2d490-122">将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="2d490-122">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#REF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref)]  
  
## <a name="see-also"></a><span data-ttu-id="2d490-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d490-123">See also</span></span>

- [<span data-ttu-id="2d490-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="2d490-124">DEREF</span></span>](deref-entity-sql.md)
- [<span data-ttu-id="2d490-125">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="2d490-125">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="2d490-126">关键</span><span class="sxs-lookup"><span data-stu-id="2d490-126">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="2d490-127">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="2d490-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="2d490-128">类型定义</span><span class="sxs-lookup"><span data-stu-id="2d490-128">Type Definitions</span></span>](type-definitions-entity-sql.md)
