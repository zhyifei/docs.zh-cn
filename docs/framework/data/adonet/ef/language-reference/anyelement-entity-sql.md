---
title: ANYELEMENT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 518ac4bc1ba6842a4b5e5f3b1f0771495752859c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="anyelement-entity-sql"></a>ANYELEMENT (Entity SQL)
从多值集合中提取元素。  
  
## <a name="syntax"></a>语法  
  
```  
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a>参数  
 `expression`  
 返回要从中提取元素的集合的任何有效查询表达式。  
  
## <a name="return-value"></a>返回值  
 集合中的一个元素，或者任意元素（如果集合具有多个元素）；如果集合为空，则返回 `null`。 如果`collection`是类型的集合`Collection<T>`，然后`ANYELEMENT(collection)`是一个产生类型的实例的有效表达式`T`。  
  
## <a name="remarks"></a>备注  
 ANYELEMENT 从多值集合中提取任意元素。 例如，以下示例尝试从 `Customers`集中提取单一实例元素。  
  
```  
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a>示例  
 以下 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询使用 ANYELEMENT 运算符以从多值集合中提取元素。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  执行 [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2.  将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a>另请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [可以为 null 的结构化的类型](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
