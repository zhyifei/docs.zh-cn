---
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 44f128a292b013fd3a3a80efdd2d10a63e3cfb07
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833839"
---
# <a name="exists-entity-sql"></a>EXISTS (Entity SQL)
确定集合是否为空。  
  
## <a name="syntax"></a>语法  
  
```sql  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a>参数  
 `expression`  
 返回集合的任何有效的表达式。  
  
 NOT  
 指定对 EXISTS 的结果取反。  
  
## <a name="return-value"></a>返回值  
 如果集合不为空，则为 `true`;否则，`false`。  
  
## <a name="remarks"></a>备注  
 EXISTS 是 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符之一。 所有 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符都是从左到右进行求值。 有关 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符的优先级信息，请参阅[EXCEPT](except-entity-sql.md)。  
  
## <a name="example"></a>示例  
 以下 Entity SQL 查询使用 EXISTS 运算符以确定集合是否为空。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1. 执行 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2. 将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-sql[DP EntityServices Concepts#EXISTS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#exists)]  
  
## <a name="see-also"></a>另请参阅

- [实体 SQL 引用](entity-sql-reference.md)
