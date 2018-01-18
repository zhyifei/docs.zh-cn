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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a7dde3d88b5b21df99be64cedc92d6aa06b00d3b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="unsupported-expressions-entity-sql"></a>不支持的表达式 (Entity SQL)
本主题介绍 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 中不支持的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 表达式。 有关详细信息，请参阅[如何实体 SQL 与 TRANSACT-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)。  
  
## <a name="quantified-predicates"></a>限定谓词  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 允许以下形式的构造：  
  
```  
sal > all (select salary from employees)  
sal > any (select salary from employees)  
```  
  
 但 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 不支持此这样的构造。 在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中的等效表达式可以写为如下形式：  
  
```  
not exists(select 0 from employees as e where sal > e.salary)  
exists(select 0 from employees as e where sal > e.salary)  
```  
  
## <a name="-operator"></a>* 运算符  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 支持在 SELECT 子句中使用 * 运算符来表示应提取出所有列。在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 中不支持使用此运算符。  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 概述](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [实体 SQL 与 Transact-SQL 的区别](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
