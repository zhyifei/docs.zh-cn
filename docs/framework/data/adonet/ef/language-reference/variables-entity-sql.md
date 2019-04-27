---
title: 变量 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bf6fa95e38d1eb5817fd67165b6993cbb0755fd1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879770"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="e73bd-102">变量 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e73bd-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="e73bd-103">变量</span><span class="sxs-lookup"><span data-stu-id="e73bd-103">Variable</span></span>  
 <span data-ttu-id="e73bd-104">变量表达式是对当前作用域中定义的命名表达式的引用。</span><span class="sxs-lookup"><span data-stu-id="e73bd-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="e73bd-105">变量引用必须是有效[!INCLUDE[esql](../../../../../../includes/esql-md.md)]标识符，如中所定义[标识符](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="e73bd-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="e73bd-106">以下示例演示如何在表达式中使用变量。</span><span class="sxs-lookup"><span data-stu-id="e73bd-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="e73bd-107">FROM 子句中的 `c` 是变量定义。</span><span class="sxs-lookup"><span data-stu-id="e73bd-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="e73bd-108">在 SELECT 子句中使用的 `c` 表示变量引用。</span><span class="sxs-lookup"><span data-stu-id="e73bd-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="e73bd-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="e73bd-109">See also</span></span>

- [<span data-ttu-id="e73bd-110">标识符</span><span class="sxs-lookup"><span data-stu-id="e73bd-110">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)
- [<span data-ttu-id="e73bd-111">参数</span><span class="sxs-lookup"><span data-stu-id="e73bd-111">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)
- [<span data-ttu-id="e73bd-112">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="e73bd-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
