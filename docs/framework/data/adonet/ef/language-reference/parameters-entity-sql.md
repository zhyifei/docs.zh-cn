---
title: 参数 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 47a1514933904daa623adc151d50525f011e07a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187664"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="c4f52-102">参数 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c4f52-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="c4f52-103">参数是在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 之外（通常通过由主机语言使用的绑定 API）定义的变量。</span><span class="sxs-lookup"><span data-stu-id="c4f52-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="c4f52-104">每个参数都具有名称和类型。</span><span class="sxs-lookup"><span data-stu-id="c4f52-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="c4f52-105">参数名称在查询表达式中定义，并以 (@) 符号作为前缀。</span><span class="sxs-lookup"><span data-stu-id="c4f52-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="c4f52-106">这可以将它们与属性的名称或在查询中定义的其他名称区分开来。</span><span class="sxs-lookup"><span data-stu-id="c4f52-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="c4f52-107">主机语言绑定 API 提供用于绑定参数的 API。</span><span class="sxs-lookup"><span data-stu-id="c4f52-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4f52-108">示例</span><span class="sxs-lookup"><span data-stu-id="c4f52-108">Example</span></span>  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4f52-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4f52-109">See also</span></span>

- [<span data-ttu-id="c4f52-110">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="c4f52-110">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="c4f52-111">Entity SQL 概述</span><span class="sxs-lookup"><span data-stu-id="c4f52-111">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
