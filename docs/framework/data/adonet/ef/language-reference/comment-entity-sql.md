---
title: "--（注释）(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1961542e615bbbd99bbc517bdd7d649be3f3ef07
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="ff98a-102">--（注释）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ff98a-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="ff98a-103"> 查询可以包含注释。</span><span class="sxs-lookup"><span data-stu-id="ff98a-103"> queries can contain comments.</span></span> <span data-ttu-id="ff98a-104">注释行以两个短划线 (`--`) 开头。</span><span class="sxs-lookup"><span data-stu-id="ff98a-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff98a-105">语法</span><span class="sxs-lookup"><span data-stu-id="ff98a-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="ff98a-106">参数</span><span class="sxs-lookup"><span data-stu-id="ff98a-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="ff98a-107">包含注释文本的字符串。</span><span class="sxs-lookup"><span data-stu-id="ff98a-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff98a-108">示例</span><span class="sxs-lookup"><span data-stu-id="ff98a-108">Example</span></span>  
 <span data-ttu-id="ff98a-109">下面的 Entity SQL 查询演示如何使用注释。</span><span class="sxs-lookup"><span data-stu-id="ff98a-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="ff98a-110">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="ff98a-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ff98a-111">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="ff98a-111">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ff98a-112">执行 [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="ff98a-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ff98a-113">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="ff98a-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="ff98a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff98a-114">See Also</span></span>  
 [<span data-ttu-id="ff98a-115">Entity SQL 概述</span><span class="sxs-lookup"><span data-stu-id="ff98a-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="ff98a-116">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="ff98a-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
