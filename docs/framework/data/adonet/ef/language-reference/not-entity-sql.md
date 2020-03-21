---
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 0b69d4cb64adc1f9232631d50ec42af0d1ba47e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150124"
---
# <a name="-not-entity-sql"></a>! (NOT) (Entity SQL)
对 `Boolean` 表达式求反。  
  
## <a name="syntax"></a>语法  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
```
  
## <a name="arguments"></a>参数  
 `boolean_expression`  
 返回 Boolean 的任何有效表达式。  
  
## <a name="remarks"></a>备注  
 惊叹号 (!) 与 NOT 运算符具有相同的功能。  
  
## <a name="example"></a>示例  
 以下 Entity SQL 查询使用 NOT 运算符以对 `Boolean` 表达式求反。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1. 执行 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2. 将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a>另请参阅

- [实体 SQL 引用](entity-sql-reference.md)
