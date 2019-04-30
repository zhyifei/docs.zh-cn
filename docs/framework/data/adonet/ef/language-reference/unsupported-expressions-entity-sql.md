---
title: 不支持的表达式 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: a47ff46ca99a84500bc5dfecc19bb31652e9b4b6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034068"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="8b979-102">不支持的表达式</span><span class="sxs-lookup"><span data-stu-id="8b979-102">Unsupported expressions</span></span>

<span data-ttu-id="8b979-103">本主题介绍 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 中不支持的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 表达式。</span><span class="sxs-lookup"><span data-stu-id="8b979-103">This topic describes [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="8b979-104">有关详细信息，请参阅[如何实体 SQL 与 TRANSACT-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="8b979-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="8b979-105">限定的谓词</span><span class="sxs-lookup"><span data-stu-id="8b979-105">Quantified predicates</span></span>

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] <span data-ttu-id="8b979-106">允许以下形式的构造：</span><span class="sxs-lookup"><span data-stu-id="8b979-106">allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

<span data-ttu-id="8b979-107">但 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不支持此这样的构造。</span><span class="sxs-lookup"><span data-stu-id="8b979-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="8b979-108">在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中的等效表达式可以写为如下形式：</span><span class="sxs-lookup"><span data-stu-id="8b979-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="8b979-109">\* 运算符</span><span class="sxs-lookup"><span data-stu-id="8b979-109">\* operator</span></span>

[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] <span data-ttu-id="8b979-110">支持在 SELECT 子句中使用 \* 运算符来表示应提取出所有列。在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中不支持使用此运算符。</span><span class="sxs-lookup"><span data-stu-id="8b979-110">supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="8b979-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b979-111">See also</span></span>

- [<span data-ttu-id="8b979-112">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="8b979-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="8b979-113">实体 SQL 与 Transact-SQL 的区别</span><span class="sxs-lookup"><span data-stu-id="8b979-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
