---
title: 变量 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: a16c450401eee1021aeef885fba129c943a87fd7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742260"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="5eb4c-102">变量 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5eb4c-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="5eb4c-103">变量</span><span class="sxs-lookup"><span data-stu-id="5eb4c-103">Variable</span></span>  
 <span data-ttu-id="5eb4c-104">变量表达式是对当前作用域中定义的命名表达式的引用。</span><span class="sxs-lookup"><span data-stu-id="5eb4c-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="5eb4c-105">变量引用必须是有效[!INCLUDE[esql](../../../../../../includes/esql-md.md)]标识符，如中所定义[标识符](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="5eb4c-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="5eb4c-106">以下示例演示如何在表达式中使用变量。</span><span class="sxs-lookup"><span data-stu-id="5eb4c-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="5eb4c-107">FROM 子句中的 `c` 是变量定义。</span><span class="sxs-lookup"><span data-stu-id="5eb4c-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="5eb4c-108">在 SELECT 子句中使用的 `c` 表示变量引用。</span><span class="sxs-lookup"><span data-stu-id="5eb4c-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="5eb4c-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="5eb4c-109">See also</span></span>
- [<span data-ttu-id="5eb4c-110">标识符</span><span class="sxs-lookup"><span data-stu-id="5eb4c-110">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)
- [<span data-ttu-id="5eb4c-111">参数</span><span class="sxs-lookup"><span data-stu-id="5eb4c-111">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)
- [<span data-ttu-id="5eb4c-112">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="5eb4c-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
