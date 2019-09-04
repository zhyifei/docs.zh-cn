---
title: + （字符串串联）（实体 SQL）
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: ef482a1206dea98cfb5a0ba5071acc130ef0cd18
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249031"
---
# <a name="-string-concatenation-entity-sql"></a>+（字符串串联）(Entity SQL)
串联两个字符串。  
  
## <a name="syntax"></a>语法  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a>自变量  
 `expression`  
 EDM.String 数据类型的任何有效表达式。 这两个表达式都必须具有相同的数据类型，或者一个表达式必须能够隐式转换为另一表达式的数据类型。  
  
## <a name="result-types"></a>结果类型  
 对这两个参数进行隐式类型提升而产生的数据类型。 有关隐式类型升级的详细信息，请参阅[类型系统](type-system-entity-sql.md)。  
  
## <a name="example"></a>示例  
 以下 Entity SQL 查询使用 + 运算符以串联两个字符串。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1. [按照如何：执行返回 PrimitiveType 结果](../how-to-execute-a-query-that-returns-primitivetype-results.md)的查询。  
  
2. 将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a>请参阅

- [实体 SQL 引用](entity-sql-reference.md)
- [概念模型类型 (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
