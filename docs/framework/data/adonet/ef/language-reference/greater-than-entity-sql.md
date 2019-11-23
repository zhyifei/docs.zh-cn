---
title: '> （大于）（实体 SQL）'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: f2d3a0ed81cf75b7e567dbd07e119629ea47ac69
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833772"
---
# <a name="-greater-than-entity-sql"></a>> （大于）（实体 SQL）
比较两个表达式以确定左侧表达式的值是否大于右侧表达式的值。  
  
## <a name="syntax"></a>语法  
  
```sql  
expression > expression  
```  
  
## <a name="arguments"></a>参数  
 `expression`  
 任何有效表达式。 两个表达式都必须具有可隐式转换的数据类型。  
  
## <a name="result-types"></a>结果类型  
 如果左侧表达式的值大于右侧表达式的值，则为`true` ；否则为 `false`。  
  
## <a name="example"></a>示例  
 下面的 Entity SQL 查询使用 > 比较运算符比较两个表达式，以确定左侧表达式的值是否大于右侧表达式的值。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1. 执行 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2. 将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-sql[DP EntityServices Concepts#GREATER](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#greater)]  
  
## <a name="see-also"></a>另请参阅

- [实体 SQL 引用](entity-sql-reference.md)
