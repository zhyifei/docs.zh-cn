---
title: SKIP (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 28f774b8d8bb232512fb975d292df4423f56a6d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="skip-entity-sql"></a>SKIP (Entity SQL)
在 ORDER BY 子句中使用 SKIP 子子句可执行物理分页。 SKIP 不能脱离 ORDER BY 子句单独使用。  
  
## <a name="syntax"></a>语法  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a>自变量  
 `n`  
 要跳过的项数。  
  
## <a name="remarks"></a>备注  
 如果 ORDER BY 子句中存在 SKIP 表达式子子句，则将根据排序规范对结果排序，结果集将包含从紧接着 SKIP 表达式之后的下一行开始的行。 例如，SKIP 5 将跳过前五行，并返回第六行以及后续行。  
  
> [!NOTE]
>  如果 TOP 修饰符和 SKIP 子子句同时出现在同一个查询表达式中， [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询将无效。 应重写查询，将 TOP 表达式更改为 LIMIT 表达式。  
  
> [!NOTE]
>  在 [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]中，对非键列同时使用 SKIP 和 ORDER BY 可能返回不正确的结果。 如果非键列中有重复数据，那么跳过的行数可能多于指定的行数。 这是由于 [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]对 SKIP 的解释方式造成的。 例如，在下面的代码中，如果 `E.NonKeyColumn` 有重复值，则跳过的行可能超过 5 行：  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 本 [示例中的](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) 查询使用 ORDER BY 运算符与 SKIP 来指定 SELECT 语句中返回的对象所使用的排序顺序。  
  
## <a name="see-also"></a>请参阅  
 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [如何： 查询结果分页](http://msdn.microsoft.com/en-us/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [分页](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
