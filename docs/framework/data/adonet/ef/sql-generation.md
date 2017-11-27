---
title: "SQL 生成"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 727aa0ca3e1673a5bbd29884077ed5aa65d792f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="sql-generation"></a>SQL 生成
在编写[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]的提供程序时，必须将[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]命令目录树转换为特定数据库可理解的 SQL，如 Transact-SQL for SQL Server 或 PL/SQL for Oracle。 在本节中，您将了解如何针对[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]提供程序开发 SQL 生成组件（用于 SELECT 查询）。 有关插入的内容，更新和删除查询，请参阅[修改 SQL 生成](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)。  
  
 若要理解本节内容，您应熟悉[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]和 ADO.NET 提供程序模型。 您还应理解命令目录树和 <xref:System.Data.Common.CommandTrees.DbExpression>。  
  
## <a name="the-role-of-the-sql-generation-module"></a>SQL 生成模块的角色  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]提供程序的 SQL 生成模块可将给定的查询命令目录树转换为面向符合 SQL:1999 的数据库的单个 SQL SELECT 语句。 生成的 SQL 应具有尽可能少的嵌套查询。 SQL 生成模块不应简化输出查询命令目录树。 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]将执行此操作，例如，它将通过消除联接并折叠连续的筛选器节点来做到这一点。  
  
 <!--zz<xref:System.Data.Common.DBProviderServices> --> `System.Data.Common.DBProviderServices`类是用于访问 SQL 生成层以将命令目录树到转换的起始点<!--zz<xref:System.Data.Common.DbCommands>--> `System.Data.Common.DbCommands`。  
  
## <a name="in-this-section"></a>本节内容  
 [命令目录树的形状](../../../../../docs/framework/data/adonet/ef/the-shape-of-the-command-trees.md)  
  
 [从命令目录树的最佳实践生成 SQL](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md)  
  
 [该示例提供程序中的 SQL 生成](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a>另请参阅  
 [编写实体框架数据提供程序](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
