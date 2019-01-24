---
title: + （字符串串联）(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: e53bd0a2607deb67d45edc44e51cf4ad283b21c6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54633909"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="83102-102">+（字符串串联）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="83102-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="83102-103">串联两个字符串。</span><span class="sxs-lookup"><span data-stu-id="83102-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83102-104">语法</span><span class="sxs-lookup"><span data-stu-id="83102-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="83102-105">自变量</span><span class="sxs-lookup"><span data-stu-id="83102-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="83102-106">EDM.String 数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="83102-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="83102-107">这两个表达式都必须具有相同的数据类型，或者一个表达式必须能够隐式转换为另一表达式的数据类型。</span><span class="sxs-lookup"><span data-stu-id="83102-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="83102-108">结果类型</span><span class="sxs-lookup"><span data-stu-id="83102-108">Result Types</span></span>  
 <span data-ttu-id="83102-109">对这两个参数进行隐式类型提升而产生的数据类型。</span><span class="sxs-lookup"><span data-stu-id="83102-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="83102-110">有关隐式类型提升的详细信息，请参阅[类型系统](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="83102-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="83102-111">示例</span><span class="sxs-lookup"><span data-stu-id="83102-111">Example</span></span>  
 <span data-ttu-id="83102-112">以下 Entity SQL 查询使用 + 运算符以串联两个字符串。</span><span class="sxs-lookup"><span data-stu-id="83102-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="83102-113">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="83102-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="83102-114">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="83102-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="83102-115">按照中的过程[如何：执行返回 PrimitiveType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="83102-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="83102-116">将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="83102-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="83102-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="83102-117">See also</span></span>
- [<span data-ttu-id="83102-118">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="83102-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="83102-119">概念模型类型 (CSDL)</span><span class="sxs-lookup"><span data-stu-id="83102-119">Conceptual Model Types (CSDL)</span></span>](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
