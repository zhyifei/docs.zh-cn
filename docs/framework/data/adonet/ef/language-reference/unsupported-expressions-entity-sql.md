---
title: 不支持的表达式 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: af0e00f470584883b6a65b63f2650c1c359b404c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489868"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="0be68-102">不支持的表达式</span><span class="sxs-lookup"><span data-stu-id="0be68-102">Unsupported expressions</span></span>

<span data-ttu-id="0be68-103">本主题介绍中不支持的 TRANSACT-SQL 表达式[!INCLUDE[esql](../../../../../../includes/esql-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0be68-103">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="0be68-104">有关详细信息，请参阅[如何实体 SQL 与 TRANSACT-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="0be68-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="0be68-105">限定的谓词</span><span class="sxs-lookup"><span data-stu-id="0be68-105">Quantified predicates</span></span>

<span data-ttu-id="0be68-106">TRANSACT-SQL 允许以下形式的构造：</span><span class="sxs-lookup"><span data-stu-id="0be68-106">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

<span data-ttu-id="0be68-107">但 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不支持此这样的构造。</span><span class="sxs-lookup"><span data-stu-id="0be68-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="0be68-108">在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中的等效表达式可以写为如下形式：</span><span class="sxs-lookup"><span data-stu-id="0be68-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="0be68-109">\* 运算符</span><span class="sxs-lookup"><span data-stu-id="0be68-109">\* operator</span></span>

<span data-ttu-id="0be68-110">Transact SQL 支持使用 \* 运算符在 SELECT 子句中的，以指示所有列应都提取出。在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中不支持使用此运算符。</span><span class="sxs-lookup"><span data-stu-id="0be68-110">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="0be68-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="0be68-111">See also</span></span>

- [<span data-ttu-id="0be68-112">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="0be68-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="0be68-113">实体 SQL 与 Transact-SQL 的区别</span><span class="sxs-lookup"><span data-stu-id="0be68-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
