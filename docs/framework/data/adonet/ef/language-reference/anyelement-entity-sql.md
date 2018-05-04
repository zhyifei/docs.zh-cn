---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: 11d1dd4b09ff07519f3435d313de72c5b9a3edf4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="anyelement-entity-sql"></a>ANYELEMENT (Entity SQL)
从多值集合中提取元素。  
  
## <a name="syntax"></a>语法  
  
```  
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a>自变量  
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
  
1.  执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2.  将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [可以为 NULL 的结构化类型](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
