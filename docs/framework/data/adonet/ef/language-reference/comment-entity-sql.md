---
title: --（注释）(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: c10b17931c6024e2a9e947083747435d8aa54fa2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339510"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="c1a21-102">--（注释）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c1a21-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="c1a21-103">查询可以包含注释。</span><span class="sxs-lookup"><span data-stu-id="c1a21-103">queries can contain comments.</span></span> <span data-ttu-id="c1a21-104">注释行以两个短划线 (`--`) 开头。</span><span class="sxs-lookup"><span data-stu-id="c1a21-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1a21-105">语法</span><span class="sxs-lookup"><span data-stu-id="c1a21-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="c1a21-106">自变量</span><span class="sxs-lookup"><span data-stu-id="c1a21-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="c1a21-107">包含注释文本的字符串。</span><span class="sxs-lookup"><span data-stu-id="c1a21-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1a21-108">示例</span><span class="sxs-lookup"><span data-stu-id="c1a21-108">Example</span></span>  
 <span data-ttu-id="c1a21-109">下面的 Entity SQL 查询演示如何使用注释。</span><span class="sxs-lookup"><span data-stu-id="c1a21-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="c1a21-110">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="c1a21-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c1a21-111">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="c1a21-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="c1a21-112">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="c1a21-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="c1a21-113">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="c1a21-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="c1a21-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1a21-114">See also</span></span>

- [<span data-ttu-id="c1a21-115">Entity SQL 概述</span><span class="sxs-lookup"><span data-stu-id="c1a21-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="c1a21-116">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="c1a21-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
