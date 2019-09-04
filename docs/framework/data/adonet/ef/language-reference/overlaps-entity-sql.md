---
title: OVERLAPS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: fef90beebf1c2723c767eaf5155542ad40d5fcb8
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249724"
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="4486b-102">OVERLAPS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4486b-102">OVERLAPS (Entity SQL)</span></span>
<span data-ttu-id="4486b-103">确定两个集合是否具有公共元素。</span><span class="sxs-lookup"><span data-stu-id="4486b-103">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4486b-104">语法</span><span class="sxs-lookup"><span data-stu-id="4486b-104">Syntax</span></span>  
  
```  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="4486b-105">自变量</span><span class="sxs-lookup"><span data-stu-id="4486b-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="4486b-106">返回一个集合以与从其他查询表达式返回的集合进行比较的任何有效查询表达式。</span><span class="sxs-lookup"><span data-stu-id="4486b-106">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="4486b-107">所有表达式都必须与 `expression`一样属于同一类型或属于公共基类型或派生类型。</span><span class="sxs-lookup"><span data-stu-id="4486b-107">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4486b-108">返回值</span><span class="sxs-lookup"><span data-stu-id="4486b-108">Return Value</span></span>  
 <span data-ttu-id="4486b-109">如果两个集合具有公共元素，则为`true` ；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="4486b-109">`true` if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4486b-110">备注</span><span class="sxs-lookup"><span data-stu-id="4486b-110">Remarks</span></span>  
 <span data-ttu-id="4486b-111">重叠提供的功能等效于以下形式：</span><span class="sxs-lookup"><span data-stu-id="4486b-111">OVERLAPS provides functionally equivalent to the following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="4486b-112">OVERLAPS 是 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符之一。</span><span class="sxs-lookup"><span data-stu-id="4486b-112">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="4486b-113">所有 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符都是从左到右进行求值。</span><span class="sxs-lookup"><span data-stu-id="4486b-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="4486b-114">有关[!INCLUDE[esql](../../../../../../includes/esql-md.md)]集运算符的优先级信息，请参阅[EXCEPT](except-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="4486b-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4486b-115">示例</span><span class="sxs-lookup"><span data-stu-id="4486b-115">Example</span></span>  
 <span data-ttu-id="4486b-116">以下 Entity SQL 查询使用 OVERLAPS 运算符以确定两个集合是否具有公共值。</span><span class="sxs-lookup"><span data-stu-id="4486b-116">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="4486b-117">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="4486b-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4486b-118">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="4486b-118">To compile and run this, follow these steps:</span></span>  
  
1. <span data-ttu-id="4486b-119">[按照如何：执行返回 StructuralType 结果](../how-to-execute-a-query-that-returns-structuraltype-results.md)的查询。</span><span class="sxs-lookup"><span data-stu-id="4486b-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="4486b-120">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="4486b-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="4486b-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="4486b-121">See also</span></span>

- [<span data-ttu-id="4486b-122">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="4486b-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
