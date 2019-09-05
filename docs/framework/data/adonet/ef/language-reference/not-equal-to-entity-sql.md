---
title: '!=（不等于）(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: c2ccadaa5801cac9c10241108f02ade223a8697f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249841"
---
# <a name="-not-equal-to-entity-sql"></a>!=（不等于）(Entity SQL)
比较两个表达式以确定左侧表达式是否不等于右侧表达式。 !=（不等于）运算符在功能上等效于 <> 运算符。  
  
## <a name="syntax"></a>语法  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a>自变量  
 `expression`  
 任何有效表达式。 两个表达式都必须具有可隐式转换的数据类型。  
  
## <a name="result-types"></a>结果类型  
 如果左侧表达式不等于右侧表达式，则为`true` ；否则为 `false`。  
  
## <a name="example"></a>示例  
 下面的 Entity SQL 查询使用 != 运算符比较两个表达式，以确定左侧表达式是否不等于右侧表达式。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1. [按照如何：执行返回 StructuralType 结果](../how-to-execute-a-query-that-returns-structuraltype-results.md)的查询。  
  
2. 将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a>请参阅

- [实体 SQL 引用](entity-sql-reference.md)
