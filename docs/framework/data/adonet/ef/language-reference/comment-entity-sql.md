---
title: --（注释）(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 4b3c801999d520a775c1a7026c945c027145b59d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="52eb9-102">--（注释）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="52eb9-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="52eb9-103"> 查询可以包含注释。</span><span class="sxs-lookup"><span data-stu-id="52eb9-103"> queries can contain comments.</span></span> <span data-ttu-id="52eb9-104">注释行以两个短划线 (`--`) 开头。</span><span class="sxs-lookup"><span data-stu-id="52eb9-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52eb9-105">语法</span><span class="sxs-lookup"><span data-stu-id="52eb9-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="52eb9-106">自变量</span><span class="sxs-lookup"><span data-stu-id="52eb9-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="52eb9-107">包含注释文本的字符串。</span><span class="sxs-lookup"><span data-stu-id="52eb9-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52eb9-108">示例</span><span class="sxs-lookup"><span data-stu-id="52eb9-108">Example</span></span>  
 <span data-ttu-id="52eb9-109">下面的 Entity SQL 查询演示如何使用注释。</span><span class="sxs-lookup"><span data-stu-id="52eb9-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="52eb9-110">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="52eb9-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="52eb9-111">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="52eb9-111">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="52eb9-112">执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="52eb9-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="52eb9-113">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="52eb9-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="52eb9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="52eb9-114">See Also</span></span>  
 [<span data-ttu-id="52eb9-115">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="52eb9-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="52eb9-116">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="52eb9-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
