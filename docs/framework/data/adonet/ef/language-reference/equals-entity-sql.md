---
title: =（等于）(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: ec87ec682e1773c001c225567a35b3cedc9c5aba
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251007"
---
# <a name="-equals-entity-sql"></a>=（等于）(Entity SQL)
比较两个表达式是否相等。  
  
## <a name="syntax"></a>语法  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a>自变量  
 `expression`  
 任何有效表达式。 两个表达式都必须具有可隐式转换的数据类型。  
  
## <a name="result-types"></a>结果类型  
 如果左侧表达式等于右侧表达式，则为`true` ；否则为 `false`。  
  
## <a name="remarks"></a>备注  
 == 运算符等效于 =。  
  
## <a name="example"></a>示例  
 下面的 Entity SQL 查询使用 = 比较运算符比较两个表达式是否相等。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1. [按照如何：执行返回 StructuralType 结果](../how-to-execute-a-query-that-returns-structuraltype-results.md)的查询。  
  
2. 将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a>请参阅

- [实体 SQL 引用](entity-sql-reference.md)
