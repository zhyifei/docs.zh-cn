---
title: "变量 (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d035f8d5616f2eb4c5a4db31857da2be0cd3d930
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="variables-entity-sql"></a><span data-ttu-id="dff59-102">变量 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="dff59-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="dff59-103">变量</span><span class="sxs-lookup"><span data-stu-id="dff59-103">Variable</span></span>  
 <span data-ttu-id="dff59-104">变量表达式是对当前作用域中定义的命名表达式的引用。</span><span class="sxs-lookup"><span data-stu-id="dff59-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="dff59-105">变量的引用必须是有效[!INCLUDE[esql](../../../../../../includes/esql-md.md)]标识符中, 定义[标识符](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="dff59-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="dff59-106">以下示例演示如何在表达式中使用变量。</span><span class="sxs-lookup"><span data-stu-id="dff59-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="dff59-107">FROM 子句中的 `c` 是变量定义。</span><span class="sxs-lookup"><span data-stu-id="dff59-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="dff59-108">在 SELECT 子句中使用的 `c` 表示变量引用。</span><span class="sxs-lookup"><span data-stu-id="dff59-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="dff59-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="dff59-109">See Also</span></span>  
 [<span data-ttu-id="dff59-110">标识符</span><span class="sxs-lookup"><span data-stu-id="dff59-110">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
 [<span data-ttu-id="dff59-111">参数</span><span class="sxs-lookup"><span data-stu-id="dff59-111">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
 [<span data-ttu-id="dff59-112">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="dff59-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
