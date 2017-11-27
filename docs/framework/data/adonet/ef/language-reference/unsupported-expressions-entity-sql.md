---
title: "不支持的表达式 (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c18c726a962d9a29a3dace1ebd5c2073637bb4aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="unsupported-expressions-entity-sql"></a><span data-ttu-id="5af7a-102">不支持的表达式 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5af7a-102">Unsupported Expressions (Entity SQL)</span></span>
<span data-ttu-id="5af7a-103">本主题介绍 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 中不支持的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 表达式。</span><span class="sxs-lookup"><span data-stu-id="5af7a-103">This topic describes [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="5af7a-104">有关详细信息，请参阅[如何实体 SQL 与 TRANSACT-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="5af7a-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>  
  
## <a name="quantified-predicates"></a><span data-ttu-id="5af7a-105">限定谓词</span><span class="sxs-lookup"><span data-stu-id="5af7a-105">Quantified Predicates</span></span>  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="5af7a-106"> 允许以下形式的构造：</span><span class="sxs-lookup"><span data-stu-id="5af7a-106"> allows constructs of the following form:</span></span>  
  
```  
sal > all (select salary from employees)  
sal > any (select salary from employees)  
```  
  
 <span data-ttu-id="5af7a-107">但 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不支持此这样的构造。</span><span class="sxs-lookup"><span data-stu-id="5af7a-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="5af7a-108">在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中的等效表达式可以写为如下形式：</span><span class="sxs-lookup"><span data-stu-id="5af7a-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>  
  
```  
not exists(select 0 from employees as e where sal > e.salary)  
exists(select 0 from employees as e where sal > e.salary)  
```  
  
## <a name="-operator"></a><span data-ttu-id="5af7a-109">* 运算符</span><span class="sxs-lookup"><span data-stu-id="5af7a-109">* Operator</span></span>  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="5af7a-110"> 支持在 SELECT 子句中使用 * 运算符来表示应提取出所有列。在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中不支持使用此运算符。</span><span class="sxs-lookup"><span data-stu-id="5af7a-110"> supports the use of the * operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af7a-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5af7a-111">See Also</span></span>  
 [<span data-ttu-id="5af7a-112">Entity SQL 概述</span><span class="sxs-lookup"><span data-stu-id="5af7a-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="5af7a-113">Entity SQL 与 TRANSACT-SQL 的区别</span><span class="sxs-lookup"><span data-stu-id="5af7a-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
