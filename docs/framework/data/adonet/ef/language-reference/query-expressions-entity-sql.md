---
title: 查询表达式 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: 4428286890f41573a02daf31a4593d0c8f9ad34b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249279"
---
# <a name="query-expressions-entity-sql"></a>查询表达式 (Entity SQL)
查询表达式将许多不同的查询运算符组合成单个语法。 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]提供各种类型的表达式，包括：[文本](literals-entity-sql.md)、[参数](parameters-entity-sql.md)、[变量](variables-entity-sql.md)、运算符、[函数](functions-entity-sql.md)、集运算符等等。 有关详细信息，请参阅[实体 SQL 引用](entity-sql-reference.md)。  
  
## <a name="clauses"></a>子句  
 查询表达式由一系列子句组成，这些子句将连续的操作应用于一个对象集合。 查询表达式基于标准 SQL SELECT 语句中存在的相同子句：[SELECT](select-entity-sql.md)、 [FROM](from-entity-sql.md)、 [WHERE](where-entity-sql.md)、 [GROUP BY](group-by-entity-sql.md)、 [HAVING](having-entity-sql.md)和[ORDER by](order-by-entity-sql.md)。  
  
## <a name="scope"></a>范围  
 在 FROM 子句中定义的名称以从左到右的出现顺序引入到 FROM 作用域。 在 JOIN 列表中，表达式可以引用以前在列表中定义的名称。 在 FROM 子句中标识的元素的公共属性不会添加到 FROM 作用域：必须总是通过别名限定名称来引用这些属性。 通常，SELECT 表达式的所有部分都视作在 FROM 作用域内。  
  
## <a name="see-also"></a>请参阅

- [实体 SQL 引用](entity-sql-reference.md)
