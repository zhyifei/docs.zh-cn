---
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 20e18bf536f2b89eca9515b3c5dca7ca7fbd6fe5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250991"
---
# <a name="exists-entity-sql"></a>EXISTS (Entity SQL)
确定集合是否为空。  
  
## <a name="syntax"></a>语法  
  
```  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a>自变量  
 `expression`  
 返回集合的任何有效的表达式。  
  
 NOT  
 指定对 EXISTS 的结果取反。  
  
## <a name="return-value"></a>返回值  
 如果集合不为空，则为 `true`；否则为 `false`。  
  
## <a name="remarks"></a>备注  
 EXISTS 是 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符之一。 所有 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集运算符都是从左到右进行求值。 有关[!INCLUDE[esql](../../../../../../includes/esql-md.md)]集运算符的优先级信息，请参阅[EXCEPT](except-entity-sql.md)。  
  
## <a name="example"></a>示例  
 以下 Entity SQL 查询使用 EXISTS 运算符以确定集合是否为空。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1. [按照如何：执行返回 StructuralType 结果](../how-to-execute-a-query-that-returns-structuraltype-results.md)的查询。  
  
2. 将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## <a name="see-also"></a>请参阅

- [实体 SQL 引用](entity-sql-reference.md)
