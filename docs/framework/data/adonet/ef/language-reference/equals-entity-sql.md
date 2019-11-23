---
title: =（等于）(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: 5cdfd35450514a9699a39cf78f64c0fa6b7d5f39
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833850"
---
# <a name="-equals-entity-sql"></a>=（等于）(Entity SQL)
比较两个表达式是否相等。  
  
## <a name="syntax"></a>语法  
  
```sql  
expression = expression  
-- or   
expression == expression  
```  
  
## <a name="arguments"></a>参数  
 `expression`  
 任何有效表达式。 两个表达式都必须具有可隐式转换的数据类型。  
  
## <a name="result-types"></a>结果类型  
 如果左侧表达式等于右侧表达式，则为`true` ；否则为 `false`。  
  
## <a name="remarks"></a>备注  
 == 运算符等效于 =。  
  
## <a name="example"></a>示例  
 下面的 Entity SQL 查询使用 = 比较运算符比较两个表达式是否相等。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1. 执行 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2. 将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-sql[DP EntityServices Concepts#EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#equals)]  
  
## <a name="see-also"></a>另请参阅

- [实体 SQL 引用](entity-sql-reference.md)
