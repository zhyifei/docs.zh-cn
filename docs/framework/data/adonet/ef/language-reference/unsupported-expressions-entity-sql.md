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
# <a name="unsupported-expressions"></a>不支持的表达式

本主题介绍中不支持的 TRANSACT-SQL 表达式[!INCLUDE[esql](../../../../../../includes/esql-md.md)]。 有关详细信息，请参阅[如何实体 SQL 与 TRANSACT-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)。

## <a name="quantified-predicates"></a>限定的谓词

TRANSACT-SQL 允许以下形式的构造：

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

但 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不支持此这样的构造。 在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中的等效表达式可以写为如下形式：

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a>* 运算符

Transact SQL 支持使用 * 运算符在 SELECT 子句中的，以指示所有列应都提取出。在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中不支持使用此运算符。

## <a name="see-also"></a>请参阅

- [实体 SQL 概述](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [实体 SQL 与 Transact-SQL 的区别](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
