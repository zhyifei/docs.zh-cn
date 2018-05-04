---
title: Entity SQL 语言
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: dbc44189634f4548b97647d19465e28ee343635d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="entity-sql-language"></a>Entity SQL 语言
Entity SQL 是类似于 SQL 的与存储无关的查询语言。 通过 Entity SQL，可以将实体数据作为对象或以表格形式进行查询。 在以下情况下，应考虑使用 Entity SQL：  
  
-   当查询必须在运行时动态构造时。 在这种情况下，还应考虑使用 <xref:System.Data.Objects.ObjectQuery%601> 的查询生成器方法，而不是在运行时构造 Entity SQL 查询字符串。  
  
-   当您要将查询定义为模型定义的一部分时。 在数据模型中只支持 Entity SQL。 有关详细信息，请参阅[QueryView 元素 (MSL)](http://msdn.microsoft.com/library/f0426b34-45cb-4fd7-9777-e0570c5e0e80)  
  
-   当使用 EntityClient，通过 <xref:System.Data.EntityClient.EntityDataReader> 将只读实体数据返回为行集时。 有关详细信息，请参阅[用于实体框架的 EntityClient 提供程序](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)。  
  
-   如果您已经是基于 SQL 的查询语言的专家，Entity SQL 可能对您而言是最简单不过了。  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>将 Entity SQL 与 EntityClient 提供程序结合使用  
 如果您要将 Entity SQL 与 EntityClient 提供程序结合使用，有关更多信息请参见下列主题：  
  
 [用于实体框架的 EntityClient 提供程序](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [如何：生成 EntityConnection 连接字符串](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [如何：执行返回 PrimitiveType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [如何：执行返回 RefType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [如何：执行返回复杂类型的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [如何：执行返回嵌套集合的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [如何：使用 EntityCommand 执行参数化 Entity SQL 查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [如何：使用 EntityCommand 执行参数化存储过程](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [如何：执行多态查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [如何：使用导航运算符导航关系](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>将 Entity SQL 与对象查询结合使用  
 如果您要将 Entity SQL 与对象查询结合使用，有关更多信息请参见下列主题：  
  
 [如何： 执行返回实体类型对象的查询](http://msdn.microsoft.com/library/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [如何： 执行参数化的查询](http://msdn.microsoft.com/library/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [如何： 导航关系使用导航属性](http://msdn.microsoft.com/library/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [如何： 调用用户定义函数](http://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [如何： 筛选数据](http://msdn.microsoft.com/library/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [如何： 对数据进行排序](http://msdn.microsoft.com/library/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [如何： 对数据进行分组](http://msdn.microsoft.com/library/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [如何： 聚合数据](http://msdn.microsoft.com/library/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [如何： 执行返回匿名类型的对象的查询](http://msdn.microsoft.com/library/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [如何： 执行返回基元类型的集合的查询](http://msdn.microsoft.com/library/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [如何： 查询 EntityCollection 中的相关的对象](http://msdn.microsoft.com/library/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [如何： 排序的两个查询联合](http://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313)  
  
 [如何： 查询结果分页](http://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## <a name="in-this-section"></a>本节内容  
 [实体 SQL 概述](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a>请参阅  
 [ADO.NET 实体框架](../../../../../../docs/framework/data/adonet/ef/index.md)  
 [语言参考](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
