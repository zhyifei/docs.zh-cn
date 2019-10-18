---
title: 变量 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bb8e6ebe81dacc7ec0f45fdde65b9c18cfd76789
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319190"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="0163a-102">变量 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0163a-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="0163a-103">变量</span><span class="sxs-lookup"><span data-stu-id="0163a-103">Variable</span></span>  
 <span data-ttu-id="0163a-104">变量表达式是对当前作用域中定义的命名表达式的引用。</span><span class="sxs-lookup"><span data-stu-id="0163a-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="0163a-105">变量引用必须是有效的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 标识符，如[标识符](identifiers-entity-sql.md)中所定义。</span><span class="sxs-lookup"><span data-stu-id="0163a-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="0163a-106">以下示例演示如何在表达式中使用变量。</span><span class="sxs-lookup"><span data-stu-id="0163a-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="0163a-107">FROM 子句中的 `c` 是变量定义。</span><span class="sxs-lookup"><span data-stu-id="0163a-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="0163a-108">在 SELECT 子句中使用的 `c` 表示变量引用。</span><span class="sxs-lookup"><span data-stu-id="0163a-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```sql  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="0163a-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="0163a-109">See also</span></span>

- [<span data-ttu-id="0163a-110">标识符</span><span class="sxs-lookup"><span data-stu-id="0163a-110">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="0163a-111">参数</span><span class="sxs-lookup"><span data-stu-id="0163a-111">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="0163a-112">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="0163a-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
