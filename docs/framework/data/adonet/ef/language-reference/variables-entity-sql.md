---
title: 变量 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 88ee41bc08711cf84b8b2e273c9ac0f4267d1d34
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149812"
---
# <a name="variables-entity-sql"></a>变量 (Entity SQL)
## <a name="variable"></a>变量  
 变量表达式是对当前作用域中定义的命名表达式的引用。 变量引用必须是有效的[!INCLUDE[esql](../../../../../../includes/esql-md.md)]标识符，如[标识符](identifiers-entity-sql.md)中定义的那样。  
  
 以下示例演示如何在表达式中使用变量。 FROM 子句中的 `c` 是变量定义。 在 SELECT 子句中使用的 `c` 表示变量引用。  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a>另请参阅

- [标识符](identifiers-entity-sql.md)
- [参数](parameters-entity-sql.md)
- [Entity SQL 概述](entity-sql-overview.md)
