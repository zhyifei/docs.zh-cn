---
title: 变量 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 5be9c80c2fce877f179d79f6b2c22f11e31e65a0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248694"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="d7a68-102">变量 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d7a68-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="d7a68-103">变量</span><span class="sxs-lookup"><span data-stu-id="d7a68-103">Variable</span></span>  
 <span data-ttu-id="d7a68-104">变量表达式是对当前作用域中定义的命名表达式的引用。</span><span class="sxs-lookup"><span data-stu-id="d7a68-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="d7a68-105">变量引用必须是[标识符](identifiers-entity-sql.md)中定义[!INCLUDE[esql](../../../../../../includes/esql-md.md)]的有效标识符。</span><span class="sxs-lookup"><span data-stu-id="d7a68-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="d7a68-106">以下示例演示如何在表达式中使用变量。</span><span class="sxs-lookup"><span data-stu-id="d7a68-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="d7a68-107">FROM 子句中的 `c` 是变量定义。</span><span class="sxs-lookup"><span data-stu-id="d7a68-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="d7a68-108">在 SELECT 子句中使用的 `c` 表示变量引用。</span><span class="sxs-lookup"><span data-stu-id="d7a68-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7a68-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7a68-109">See also</span></span>

- [<span data-ttu-id="d7a68-110">标识符</span><span class="sxs-lookup"><span data-stu-id="d7a68-110">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="d7a68-111">Parameters</span><span class="sxs-lookup"><span data-stu-id="d7a68-111">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="d7a68-112">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="d7a68-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
