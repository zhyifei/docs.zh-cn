---
title: 参数 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: c8bdb54e52b4c0d189f3bff72bdb24785c1a9c27
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765069"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="69a6d-102">参数 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="69a6d-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="69a6d-103">参数是在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 之外（通常通过由主机语言使用的绑定 API）定义的变量。</span><span class="sxs-lookup"><span data-stu-id="69a6d-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="69a6d-104">每个参数都具有名称和类型。</span><span class="sxs-lookup"><span data-stu-id="69a6d-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="69a6d-105">参数名称在查询表达式中定义，并以 (@) 符号作为前缀。</span><span class="sxs-lookup"><span data-stu-id="69a6d-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="69a6d-106">这可以将它们与属性的名称或在查询中定义的其他名称区分开来。</span><span class="sxs-lookup"><span data-stu-id="69a6d-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="69a6d-107">主机语言绑定 API 提供用于绑定参数的 API。</span><span class="sxs-lookup"><span data-stu-id="69a6d-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69a6d-108">示例</span><span class="sxs-lookup"><span data-stu-id="69a6d-108">Example</span></span>  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="69a6d-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="69a6d-109">See Also</span></span>  
 [<span data-ttu-id="69a6d-110">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="69a6d-110">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="69a6d-111">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="69a6d-111">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
