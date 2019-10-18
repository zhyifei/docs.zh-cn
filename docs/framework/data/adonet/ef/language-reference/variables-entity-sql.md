---
title: 变量 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bb8e6ebe81dacc7ec0f45fdde65b9c18cfd76789
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319190"
---
# <a name="variables-entity-sql"></a>变量 (Entity SQL)
## <a name="variable"></a>变量  
 变量表达式是对当前作用域中定义的命名表达式的引用。 变量引用必须是有效的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 标识符，如[标识符](identifiers-entity-sql.md)中所定义。  
  
 以下示例演示如何在表达式中使用变量。 FROM 子句中的 `c` 是变量定义。 在 SELECT 子句中使用的 `c` 表示变量引用。  
  
```sql  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a>请参阅

- [标识符](identifiers-entity-sql.md)
- [参数](parameters-entity-sql.md)
- [实体 SQL 概述](entity-sql-overview.md)
