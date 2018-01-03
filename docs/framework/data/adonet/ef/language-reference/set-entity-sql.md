---
title: SET (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 12ce6c47db89fe91fd11a94aa10a47b57b45d736
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="set-entity-sql"></a>SET (Entity SQL)
SET 表达式用于通过生成一个新集合（其中移除了所有重复元素）将对象集合转换为一个集。  
  
## <a name="syntax"></a>语法  
  
```  
SET ( expression )  
```  
  
## <a name="arguments"></a>自变量  
 `expression`  
 任何返回集合的有效查询表达式。  
  
## <a name="remarks"></a>备注  
 SET 表达式 `SET(c)` 在逻辑上等效于以下 select 语句：  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` 是 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符之一。 所有 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符都是从左到右进行求值。 请参阅[EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)有关优先级信息[!INCLUDE[esql](../../../../../../includes/esql-md.md)]集运算符。  
  
## <a name="example"></a>示例  
 以下 Entity SQL 查询使用 SET 表达式将一个对象集合转换为一个集。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  按照中的步骤[如何： 执行查询该返回 PrimitiveType 结果](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。  
  
2.  将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
