---
title: "查询表达式 (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 46777cbe47e7d97fd3baaa1353787f33cff9f0aa
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="query-expressions-entity-sql"></a>查询表达式 (Entity SQL)
查询表达式将许多不同的查询运算符组合成单个语法。 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]提供了各种类型的表达式，包括以下：[文本](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md)，[参数](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)，[变量](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md)，运算符，[函数](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)、 集运算符，依次类推。 有关详细信息，请参阅[实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)。  
  
## <a name="clauses"></a>子句  
 查询表达式由一系列子句组成，这些子句将连续的操作应用于一个对象集合。 基于位于标准 SQL select 语句的相同子句：[选择](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)， [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md)，[其中](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md)， [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md)， [具有](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md)，和[ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)。  
  
## <a name="scope"></a>范围  
 在 FROM 子句中定义的名称以从左到右的出现顺序引入到 FROM 作用域。 在 JOIN 列表中，表达式可以引用以前在列表中定义的名称。 在 FROM 子句中标识的元素的公共属性不添加到 FROM 作用域：始终必须通过别名限定名称来引用这些属性。 通常，SELECT 表达式的所有部分都视作在 FROM 作用域内。  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
