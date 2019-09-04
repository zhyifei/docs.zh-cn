---
title: Entity SQL 概述
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 4d7db9c6a7aaeef900132663a5b0aa7420afe668
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251068"
---
# <a name="entity-sql-overview"></a>Entity SQL 概述
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 是一种类似于 SQL 的语言，用于在[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]中查询概念模型。 概念模型将数据表示为实体和关系， [!INCLUDE[esql](../../../../../../includes/esql-md.md)]并使你能够以熟悉使用 SQL 的用户所熟悉的格式查询这些实体和关系。  
  
 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] 使用存储特定的数据提供程序，将一般 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 转换为存储特定的查询。 EntityClient 提供程序提供一种方式，用于针对实体模型执行 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 命令并返回包括标量结果、结果集和对象图在内的丰富类型数据。 构造 <xref:System.Data.EntityClient.EntityCommand> 对象时，可以指定一个存储过程名称或者通过将 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询字符串分配该对象的 <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> 属性来指定查询文本。 <xref:System.Data.EntityClient.EntityDataReader> 公开对 EDM 执行 <xref:System.Data.EntityClient.EntityCommand> 的结果。 若要执行返回 <xref:System.Data.EntityClient.EntityDataReader> 的命令，请调用 <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>。  
  
 除了 EntityClient 提供程序之外，[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]还允许您使用 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 对概念模型执行查询，并以强类型 CLR 对象的形式返回数据，这些对象是实体类型的实例。 有关详细信息，请参阅使用[对象](../working-with-objects.md)。  
  
 本节提供 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 的概念信息。  
  
## <a name="in-this-section"></a>本节内容  
 [实体 SQL 与 Transact-SQL 的区别](how-entity-sql-differs-from-transact-sql.md)  
  
 [实体 SQL 快速参考](entity-sql-quick-reference.md)  
  
 [类型系统](type-system-entity-sql.md)  
  
 [类型定义](type-definitions-entity-sql.md)  
  
 [构造类型](constructing-types-entity-sql.md)  
  
 [查询计划缓存](query-plan-caching-entity-sql.md)  
  
 [命名空间](namespaces-entity-sql.md)  
  
 [标识符](identifiers-entity-sql.md)  
  
 [Parameters](parameters-entity-sql.md)  
  
 [变量](variables-entity-sql.md)  
  
 [不支持的表达式](unsupported-expressions-entity-sql.md)  
  
 [文本](literals-entity-sql.md)  
  
 [NULL 文本和类型推理](null-literals-and-type-inference-entity-sql.md)  
  
 [输入字符集](input-character-set-entity-sql.md)  
  
 [查询表达式](query-expressions-entity-sql.md)  
  
 [函数](functions-entity-sql.md)  
  
 [运算符优先级](operator-precedence-entity-sql.md)  
  
 [分页](paging-entity-sql.md)  
  
 [比较语义](comparison-semantics-entity-sql.md)  
  
 [撰写嵌套的实体 SQL 查询](composing-nested-entity-sql-queries.md)  
  
 [可以为 NULL 的结构化类型](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a>请参阅

- [实体 SQL 引用](entity-sql-reference.md)
- [实体 SQL 语言](entity-sql-language.md)
- [CSDL、SSDL 和 MSL 规范](csdl-ssdl-and-msl-specifications.md)
