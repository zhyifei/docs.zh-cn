---
title: 变量 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: f271ffc31875e7d94a27f4752b71bfe508fcb620
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="variables-entity-sql"></a>变量 (Entity SQL)
## <a name="variable"></a>变量  
 变量表达式是对当前作用域中定义的命名表达式的引用。 变量的引用必须是有效[!INCLUDE[esql](../../../../../../includes/esql-md.md)]标识符中, 定义[标识符](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)。  
  
 以下示例演示如何在表达式中使用变量。 FROM 子句中的 `c` 是变量定义。 在 SELECT 子句中使用的 `c` 表示变量引用。  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a>请参阅  
 [标识符](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
 [参数](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
 [实体 SQL 概述](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
