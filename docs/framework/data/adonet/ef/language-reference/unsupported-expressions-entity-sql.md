---
title: "不支持的表达式 (Entity SQL)"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-ado
ms.topic: article
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
dev_langs:
- sql
ms.openlocfilehash: 075daf0e4f0477dda50231760fbb3d990a9f8468
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2018
---
# <a name="unsupported-expressions"></a><span data-ttu-id="f5a44-102">不支持的表达式</span><span class="sxs-lookup"><span data-stu-id="f5a44-102">Unsupported expressions</span></span>

<span data-ttu-id="f5a44-103">本主题介绍 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 中不支持的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 表达式。</span><span class="sxs-lookup"><span data-stu-id="f5a44-103">This topic describes [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="f5a44-104">有关详细信息，请参阅[如何实体 SQL 与 TRANSACT-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="f5a44-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="f5a44-105">限定的谓词</span><span class="sxs-lookup"><span data-stu-id="f5a44-105">Quantified predicates</span></span>

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] <span data-ttu-id="f5a44-106">允许以下形式的构造：</span><span class="sxs-lookup"><span data-stu-id="f5a44-106">allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="f5a44-107">但是，不支持此类构造。</span><span class="sxs-lookup"><span data-stu-id="f5a44-107">, however, does not support such constructs.</span></span> <span data-ttu-id="f5a44-108">在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中的等效表达式可以写为如下形式：</span><span class="sxs-lookup"><span data-stu-id="f5a44-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal > e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="f5a44-109">\* 运算符</span><span class="sxs-lookup"><span data-stu-id="f5a44-109">\* operator</span></span>

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] <span data-ttu-id="f5a44-110">支持使用 \* SELECT 子句中的运算符，以指示所有列应都提取出。在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中不支持使用此运算符。</span><span class="sxs-lookup"><span data-stu-id="f5a44-110">supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="f5a44-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5a44-111">See also</span></span>

[<span data-ttu-id="f5a44-112">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="f5a44-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
[<span data-ttu-id="f5a44-113">实体 SQL 与 Transact-SQL 的区别</span><span class="sxs-lookup"><span data-stu-id="f5a44-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)  
