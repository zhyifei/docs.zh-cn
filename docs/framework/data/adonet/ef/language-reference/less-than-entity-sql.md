---
title: < （小于）（实体 SQL）
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: fb3f4a1c6bc0df6af3c27836f7b53b2701776366
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319685"
---
# <a name="-less-than-entity-sql"></a><span data-ttu-id="ec069-102">\<（小于）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ec069-102">\< (Less Than) (Entity SQL)</span></span>
<span data-ttu-id="ec069-103">比较两个表达式以确定左侧表达式的值是否小于右侧表达式的值。</span><span class="sxs-lookup"><span data-stu-id="ec069-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec069-104">语法</span><span class="sxs-lookup"><span data-stu-id="ec069-104">Syntax</span></span>  
  
```sql  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ec069-105">自变量</span><span class="sxs-lookup"><span data-stu-id="ec069-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ec069-106">任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="ec069-106">Any valid expression.</span></span> <span data-ttu-id="ec069-107">两个表达式都必须具有可隐式转换的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ec069-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ec069-108">结果类型</span><span class="sxs-lookup"><span data-stu-id="ec069-108">Result Types</span></span>  
 <span data-ttu-id="ec069-109">如果左侧表达式的值小于右侧表达式的值，则为`true` ；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="ec069-109">`true` if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec069-110">示例</span><span class="sxs-lookup"><span data-stu-id="ec069-110">Example</span></span>  
 <span data-ttu-id="ec069-111">下面的 Entity SQL 查询使用 < 比较运算符比较两个表达式，以确定左侧表达式的值是否小于右侧表达式的值。</span><span class="sxs-lookup"><span data-stu-id="ec069-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="ec069-112">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="ec069-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ec069-113">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="ec069-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ec069-114">执行 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="ec069-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ec069-115">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="ec069-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a><span data-ttu-id="ec069-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec069-116">See also</span></span>

- [<span data-ttu-id="ec069-117">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="ec069-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
