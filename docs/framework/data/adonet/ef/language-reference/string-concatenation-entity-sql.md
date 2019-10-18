---
title: + （字符串串联）（实体 SQL）
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 9c078e193eeecd4d331c5e3c04c66dee2c4a1daa
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319312"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="6e125-102">+（字符串串联）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6e125-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="6e125-103">串联两个字符串。</span><span class="sxs-lookup"><span data-stu-id="6e125-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e125-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e125-104">Syntax</span></span>  
  
```sql  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="6e125-105">自变量</span><span class="sxs-lookup"><span data-stu-id="6e125-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="6e125-106">EDM.String 数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="6e125-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="6e125-107">这两个表达式都必须具有相同的数据类型，或者一个表达式必须能够隐式转换为另一表达式的数据类型。</span><span class="sxs-lookup"><span data-stu-id="6e125-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6e125-108">结果类型</span><span class="sxs-lookup"><span data-stu-id="6e125-108">Result Types</span></span>  
 <span data-ttu-id="6e125-109">对这两个参数进行隐式类型提升而产生的数据类型。</span><span class="sxs-lookup"><span data-stu-id="6e125-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="6e125-110">有关隐式类型升级的详细信息，请参阅[类型系统](type-system-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="6e125-110">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e125-111">示例</span><span class="sxs-lookup"><span data-stu-id="6e125-111">Example</span></span>  
 <span data-ttu-id="6e125-112">以下 Entity SQL 查询使用 + 运算符以串联两个字符串。</span><span class="sxs-lookup"><span data-stu-id="6e125-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="6e125-113">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="6e125-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6e125-114">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="6e125-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6e125-115">按照[如何：执行返回 PrimitiveType 结果的查询](../how-to-execute-a-query-that-returns-primitivetype-results.md)中的过程进行操作。</span><span class="sxs-lookup"><span data-stu-id="6e125-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="6e125-116">将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="6e125-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CONCAT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="6e125-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e125-117">See also</span></span>

- [<span data-ttu-id="6e125-118">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="6e125-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="6e125-119">概念模型类型 (CSDL)</span><span class="sxs-lookup"><span data-stu-id="6e125-119">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
