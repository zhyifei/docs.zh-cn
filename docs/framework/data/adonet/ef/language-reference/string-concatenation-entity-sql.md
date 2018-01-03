---
title: "+ （字符串串联）(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d780c4ceff6c44f375a21f976b09ad7987478e2a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="98232-102">+（字符串串联）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="98232-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="98232-103">串联两个字符串。</span><span class="sxs-lookup"><span data-stu-id="98232-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98232-104">语法</span><span class="sxs-lookup"><span data-stu-id="98232-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="98232-105">自变量</span><span class="sxs-lookup"><span data-stu-id="98232-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="98232-106">EDM.String 数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="98232-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="98232-107">这两个表达式都必须具有相同的数据类型，或者一个表达式必须能够隐式转换为另一表达式的数据类型。</span><span class="sxs-lookup"><span data-stu-id="98232-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="98232-108">结果类型</span><span class="sxs-lookup"><span data-stu-id="98232-108">Result Types</span></span>  
 <span data-ttu-id="98232-109">对这两个参数进行隐式类型提升而产生的数据类型。</span><span class="sxs-lookup"><span data-stu-id="98232-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="98232-110">有关隐式类型提升的详细信息，请参阅[类型系统](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="98232-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98232-111">示例</span><span class="sxs-lookup"><span data-stu-id="98232-111">Example</span></span>  
 <span data-ttu-id="98232-112">以下 Entity SQL 查询使用 + 运算符以串联两个字符串。</span><span class="sxs-lookup"><span data-stu-id="98232-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="98232-113">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="98232-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="98232-114">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="98232-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="98232-115">按照中的步骤[如何： 执行查询该返回 PrimitiveType 结果](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="98232-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="98232-116">将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="98232-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="98232-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="98232-117">See Also</span></span>  
 [<span data-ttu-id="98232-118">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="98232-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="98232-119">概念模型类型 (CSDL)</span><span class="sxs-lookup"><span data-stu-id="98232-119">Conceptual Model Types (CSDL)</span></span>](http://msdn.microsoft.com/en-us/987b995f-e429-4569-9559-b4146744def4)
