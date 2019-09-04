---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: 5a07ee79d5452da4341d391fae7c997c33b603a2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250659"
---
# <a name="in-entity-sql"></a>IN (Entity SQL)
确定某个值是否与某个集合中的任何值匹配。  
  
## <a name="syntax"></a>语法  
  
```  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a>自变量  
 `value`  
 返回匹配值的任何有效表达式。  
  
 [ NOT ]  
 指定对 IN 的 `Boolean` 结果取反。  
  
 `expression`  
 返回集合以测试是否具有匹配的任何有效表达式。 所有表达式都必须与 `value`一样属于同一类型或属于公共基类型或派生类型。  
  
## <a name="return-value"></a>返回值  
 如果在集合中找到此值，则为 `true`；如果值为空或集合为空，则为空；否则为 `false`。 使用 NOT IN 可对 IN 的结果取反。  
  
## <a name="example"></a>示例  
 以下 Entity SQL 查询使用 IN 运算符以确定某个值是否与集合中的任何值匹配。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1. [按照如何：执行返回 StructuralType 结果](../how-to-execute-a-query-that-returns-structuraltype-results.md)的查询。  
  
2. 将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## <a name="see-also"></a>请参阅

- [实体 SQL 引用](entity-sql-reference.md)
