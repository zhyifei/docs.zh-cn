---
title: "用于实体框架的 EntityClient 提供程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c5db787-78e6-4a34-8dc1-188bca0aca5e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: eb6d8d4db676502b8c363a7d45407384333b3f22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="entityclient-provider-for-the-entity-framework"></a>用于实体框架的 EntityClient 提供程序
EntityClient 提供程序是一种数据提供程序，实体框架应用程序使用该提供程序访问在概念模型中描述的数据。 有关概念模型的信息，请参阅[建模和映射](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)。 EntityClient 使用其他 .NET Framework 数据提供程序访问数据源。 例如，EntityClient 在访问 SQL Server 数据库时使用 SQL Server .NET Framework 数据提供程序 (SqlClient)。 有关 SqlClient 提供程序的信息，请参阅[用于实体框架的 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)。 EntityClient 提供程序是在 <xref:System.Data.EntityClient> 命名空间中实现的。  
  
## <a name="managing-connections"></a>管理连接  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 通过提供到基础数据提供程序和关系数据库的 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]，建立在特定于存储的 <xref:System.Data.EntityClient.EntityConnection> 数据提供程序的基础之上。 若要构造<xref:System.Data.EntityClient.EntityConnection>对象，你必须引用一组包含所需模型和映射，以及特定于存储的数据提供程序名称和连接字符串的元数据。 后<xref:System.Data.EntityClient.EntityConnection>是到位，实体可以访问通过从概念模型生成的类。  
  
 可以在 app.config 文件中指定连接字符串。  
  
 <xref:System.Data.EntityClient> 还包含 <xref:System.Data.EntityClient.EntityConnectionStringBuilder> 类。 通过使用此类的属性和方法，开发人员可以使用此类以编程方式创建语法正确的连接字符串，并可以分析和重新生成现有的连接字符串。 有关详细信息，请参阅[如何： 生成 EntityConnection 连接字符串](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)。  
  
## <a name="creating-queries"></a>创建查询  
 [!INCLUDE[esql](../../../../../includes/esql-md.md)]语言与存储无关的直接使用概念实体架构并支持诸如继承和关系等实体数据模型概念的 SQL 方言。 <xref:System.Data.EntityClient.EntityCommand> 类用于对实体模型执行 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 命令。 构造 <xref:System.Data.EntityClient.EntityCommand> 对象时，可以指定一个存储过程名称或查询文本。 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 使用存储特定的数据提供程序，将一般 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 转换为存储特定的查询。 有关编写[!INCLUDE[esql](../../../../../includes/esql-md.md)]查询，请参阅[Entity SQL 语言](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)。  
  
 下面的示例创建<xref:System.Data.EntityClient.EntityCommand>对象，并将分配[!INCLUDE[esql](../../../../../includes/esql-md.md)]查询文本到其<xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>属性。 这[!INCLUDE[esql](../../../../../includes/esql-md.md)]查询请求按定价从概念模型已订购产品。 下面的代码完全不识别存储模型。  
  
 `EntityCommand cmd = conn.CreateCommand();`  
  
 `cmd.CommandText = @"` `SELECT VALUE p`  
  
 `FROM AdventureWorksEntities.Product AS p`  
  
 `ORDER BY p.ListPrice ";`  
  
## <a name="executing-queries"></a>执行查询  
 执行查询时，查询将经过解析并转换为规范命令目录树。 所有后续处理都在该命令目录树上执行。 该命令目录树是 <xref:System.Data.EntityClient> 与基础 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 数据提供程序（如 <xref:System.Data.SqlClient>）之间的通信途径。  
  
 <xref:System.Data.EntityClient.EntityDataReader> 公开对概念模型执行 <xref:System.Data.EntityClient.EntityCommand> 的结果。 若要执行返回 <xref:System.Data.EntityClient.EntityDataReader> 的命令，请调用 <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>。 <xref:System.Data.EntityClient.EntityDataReader> 实现 <xref:System.Data.IExtendedDataRecord> 以描述丰富结构化的结果。  
  
## <a name="managing-transactions"></a>管理事务  
 在实体框架中，有两种使用事务的方法：自动和显式。 自动事务使用 <xref:System.Transactions> 命名空间，而显式事务使用 <xref:System.Data.EntityClient.EntityTransaction> 类。  
  
 若要更新概念模型中; 通过公开的数据请参阅[如何： 在实体框架中管理事务](http://msdn.microsoft.com/en-us/4a55eb7f-f826-4a48-9df1-aebe2352ebef)。  
  
## <a name="in-this-section"></a>本节内容  
 [如何： 生成 EntityConnection 连接字符串](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [如何： 执行返回 PrimitiveType 结果的查询](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [如何： 执行返回 StructuralType 结果的查询](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [如何： 执行返回 RefType 结果的查询](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [如何： 执行返回复杂类型的查询](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [如何： 执行返回嵌套的集合的查询](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [如何： 执行参数化的 Entity SQL 查询使用 EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [如何： 执行参数化存储的过程使用 EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [如何： 执行多态查询](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [如何： 导航与关系导航运算符](../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="see-also"></a>另请参阅  
 [管理连接和事务](http://msdn.microsoft.com/en-us/b6659d2a-9a45-4e98-acaa-d7a8029e5b99)  
 [ADO.NET 实体框架](../../../../../docs/framework/data/adonet/ef/index.md)  
 [语言参考](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
