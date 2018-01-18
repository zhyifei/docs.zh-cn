---
title: WHERE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 11687b1218c61acde7a68bb8fc112e287e5e1c38
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="where-entity-sql"></a>WHERE (Entity SQL)
WHERE 子句应用直接后[FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md)子句。  
  
## <a name="syntax"></a>语法  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a>自变量  
 `expression`  
 Boolean 类型。  
  
## <a name="remarks"></a>备注  
 WHERE 子句的语义与针对 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 所述的语义相同。 它将源集合的元素限定为传递条件的元素，以此限制查询表达式所生成的对象。  
  
```  
select c from cs as c where e  
```  
  
 表达式 `e` 必须为 Boolean 类型。  
  
 WHERE 子句直接应用在 FROM 子句之后，任何分组、排序或投影操作之前。 FROM 子句中定义的所有元素名称对 WHERE 子句的表达式都是可见的。  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [查询表达式](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
