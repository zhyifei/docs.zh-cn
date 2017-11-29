---
title: "- （除）(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0f215e12f9f86ee08679bdb2e2638c0c8df35ea4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="-divide-entity-sql"></a>/（除）(Entity SQL)
一个数字除另一个数字。  
  
## <a name="syntax"></a>语法  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a>参数  
 `dividend`  
 被除数的数值表达式。 `dividend` 为任何一种数值数据类型的任何有效表达式。  
  
 `divisor`  
 除数的数值表达式。 `divisor` 为任何一种数值数据类型的任何有效表达式。  
  
## <a name="result-types"></a>结果类型  
 对这两个参数进行隐式类型提升而产生的数据类型。 有关隐式类型提升的详细信息，请参阅[类型系统](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)。  
  
## <a name="example"></a>示例  
 以下 Entity SQL 查询使用 / 算术运算符将两个数值相除。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  执行 [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2.  将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a>另请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
