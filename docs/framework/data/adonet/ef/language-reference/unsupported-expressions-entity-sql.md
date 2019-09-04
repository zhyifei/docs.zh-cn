---
title: 不支持的表达式 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: 956fe117eb0c59392c3999046bc70deaed268ac6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248784"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="189b4-102">不支持的表达式</span><span class="sxs-lookup"><span data-stu-id="189b4-102">Unsupported expressions</span></span>

<span data-ttu-id="189b4-103">本主题介绍中[!INCLUDE[esql](../../../../../../includes/esql-md.md)]不支持的 transact-sql 表达式。</span><span class="sxs-lookup"><span data-stu-id="189b4-103">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="189b4-104">有关详细信息，请参阅[实体 SQL 与 transact-sql 的不同之处](how-entity-sql-differs-from-transact-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="189b4-104">For more information, see [How Entity SQL Differs from Transact-SQL](how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="189b4-105">量化谓词</span><span class="sxs-lookup"><span data-stu-id="189b4-105">Quantified predicates</span></span>

<span data-ttu-id="189b4-106">Transact-sql 允许构造以下形式：</span><span class="sxs-lookup"><span data-stu-id="189b4-106">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

<span data-ttu-id="189b4-107">但 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不支持此这样的构造。</span><span class="sxs-lookup"><span data-stu-id="189b4-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="189b4-108">在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中的等效表达式可以写为如下形式：</span><span class="sxs-lookup"><span data-stu-id="189b4-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="189b4-109">\* 运算符</span><span class="sxs-lookup"><span data-stu-id="189b4-109">\* operator</span></span>

<span data-ttu-id="189b4-110">Transact-sql 支持在 SELECT 子句中使用 \* 运算符，以指示应提取所有列。在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中不支持使用此运算符。</span><span class="sxs-lookup"><span data-stu-id="189b4-110">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="189b4-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="189b4-111">See also</span></span>

- [<span data-ttu-id="189b4-112">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="189b4-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="189b4-113">实体 SQL 与 Transact-SQL 的区别</span><span class="sxs-lookup"><span data-stu-id="189b4-113">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)
