---
title: --（注释）(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: c10b17931c6024e2a9e947083747435d8aa54fa2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339510"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="daffe-102">--（注释）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="daffe-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="daffe-103">查询可以包含注释。</span><span class="sxs-lookup"><span data-stu-id="daffe-103">queries can contain comments.</span></span> <span data-ttu-id="daffe-104">注释行以两个短划线 (`--`) 开头。</span><span class="sxs-lookup"><span data-stu-id="daffe-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daffe-105">语法</span><span class="sxs-lookup"><span data-stu-id="daffe-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="daffe-106">自变量</span><span class="sxs-lookup"><span data-stu-id="daffe-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="daffe-107">包含注释文本的字符串。</span><span class="sxs-lookup"><span data-stu-id="daffe-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="daffe-108">示例</span><span class="sxs-lookup"><span data-stu-id="daffe-108">Example</span></span>  
 <span data-ttu-id="daffe-109">下面的 Entity SQL 查询演示如何使用注释。</span><span class="sxs-lookup"><span data-stu-id="daffe-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="daffe-110">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="daffe-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="daffe-111">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="daffe-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="daffe-112">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="daffe-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="daffe-113">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="daffe-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="daffe-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="daffe-114">See also</span></span>

- [<span data-ttu-id="daffe-115">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="daffe-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="daffe-116">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="daffe-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
