---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 40a5afd7eb99dba7cae8fe14ed0a45213fda94a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149942"
---
# <a name="ref-entity-sql"></a>REF (Entity SQL)
返回对实体实例的引用。  
  
## <a name="syntax"></a>语法  
  
```sql  
REF( expression )
```  
  
## <a name="arguments"></a>参数  
 `expression`  
 产生实体类型实例的任何有效表达式。  
  
## <a name="return-value"></a>返回值  
 对指定实体实例的引用。  
  
## <a name="remarks"></a>备注  
 实体引用由实体键和实体集名称组成。 不同的实体集可以基于相同的实体类型，因此一个特定实体键可以出现在多个实体集中。 但是，实体引用始终是唯一的。 如果输入表达式表示一个持久化实体，则会返回对此实体的引用。 如果输入表达式不是一个持久化实体，则会返回空引用。  
  
 如果使用属性提取运算符 (.) 访问实体的属性，则会自动取消引用。  
  
## <a name="example"></a>示例  
 下面的 Entity SQL 查询使用 REF 运算符返回输入实体参数的引用。 由于使用属性提取运算符 (.) 访问 Product 实体的属性，同一查询会取消引用。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1. 按照["如何执行"中的过程：执行返回基元类型结果的查询](../how-to-execute-a-query-that-returns-primitivetype-results.md)。  
  
2. 将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：  
  
 [!code-sql[DP EntityServices Concepts#REF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref)]  
  
## <a name="see-also"></a>另请参阅

- [DEREF](deref-entity-sql.md)
- [CREATEREF](createref-entity-sql.md)
- [关键](key-entity-sql.md)
- [实体 SQL 引用](entity-sql-reference.md)
- [类型定义](type-definitions-entity-sql.md)
