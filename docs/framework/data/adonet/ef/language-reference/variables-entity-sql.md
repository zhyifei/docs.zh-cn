---
title: "变量 (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d035f8d5616f2eb4c5a4db31857da2be0cd3d930
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
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
