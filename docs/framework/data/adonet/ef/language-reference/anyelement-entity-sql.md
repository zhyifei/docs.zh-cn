---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: c0f7686f7ff3f6458637b51e29ecafe0c0ccfbc4
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040322"
---
# <a name="anyelement-entity-sql"></a><span data-ttu-id="ac5b0-102">ANYELEMENT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ac5b0-102">ANYELEMENT (Entity SQL)</span></span>
<span data-ttu-id="ac5b0-103">从多值集合中提取元素。</span><span class="sxs-lookup"><span data-stu-id="ac5b0-103">Extracts an element from a multivalued collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac5b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="ac5b0-104">Syntax</span></span>  
  
```csharp
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="ac5b0-105">自变量</span><span class="sxs-lookup"><span data-stu-id="ac5b0-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ac5b0-106">返回要从中提取元素的集合的任何有效查询表达式。</span><span class="sxs-lookup"><span data-stu-id="ac5b0-106">Any valid query expression that returns a collection to extract an element from.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac5b0-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ac5b0-107">Return Value</span></span>  
 <span data-ttu-id="ac5b0-108">集合中的一个元素，或者任意元素（如果集合具有多个元素）；如果集合为空，则返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="ac5b0-108">A single element in the collection or an arbitrary element if the collection has more than one; if the collection is empty, returns `null`.</span></span> <span data-ttu-id="ac5b0-109">如果 `collection` 是 `Collection<T>`类型的集合，则 `ANYELEMENT(collection)` 为生成 `T`类型的实例的有效表达式。</span><span class="sxs-lookup"><span data-stu-id="ac5b0-109">If `collection` is a collection of type `Collection<T>`, then `ANYELEMENT(collection)` is a valid expression that yields an instance of type `T`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac5b0-110">备注</span><span class="sxs-lookup"><span data-stu-id="ac5b0-110">Remarks</span></span>  
 <span data-ttu-id="ac5b0-111">ANYELEMENT 从多值集合中提取任意元素。</span><span class="sxs-lookup"><span data-stu-id="ac5b0-111">ANYELEMENT extracts an arbitrary element from a multivalued collection.</span></span> <span data-ttu-id="ac5b0-112">例如，以下示例尝试从 `Customers`集中提取单一实例元素。</span><span class="sxs-lookup"><span data-stu-id="ac5b0-112">For example, the following example attempts to extract a singleton element from the set `Customers`.</span></span>  
  
```csharp
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a><span data-ttu-id="ac5b0-113">示例</span><span class="sxs-lookup"><span data-stu-id="ac5b0-113">Example</span></span>  
 <span data-ttu-id="ac5b0-114">以下 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询使用 ANYELEMENT 运算符以从多值集合中提取元素。</span><span class="sxs-lookup"><span data-stu-id="ac5b0-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ANYELEMENT operator to extract an element from a multivalued collection.</span></span> <span data-ttu-id="ac5b0-115">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="ac5b0-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ac5b0-116">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="ac5b0-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ac5b0-117">执行 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="ac5b0-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ac5b0-118">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="ac5b0-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a><span data-ttu-id="ac5b0-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac5b0-119">See also</span></span>

- [<span data-ttu-id="ac5b0-120">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="ac5b0-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="ac5b0-121">可以为 NULL 的结构化类型</span><span class="sxs-lookup"><span data-stu-id="ac5b0-121">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
