---
title: SQL 生成
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 9c5301d3f4d5bc2e0db4a138c6d8ceb06d3a7845
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854351"
---
# <a name="sql-generation"></a>SQL 生成
为实体框架编写提供程序时，必须将实体框架命令目录树转换为特定数据库可以理解的 SQL，如用于 SQL Server 的 Transact-sql 或用于 Oracle 的 PL/SQL。 在本部分中，你将学习如何为实体框架提供程序开发 SQL 生成组件（适用于选择查询）。 有关 insert、update 和 delete 查询的信息，请参阅[修改 SQL 生成](modification-sql-generation.md)。  
  
 若要理解此部分，应熟悉实体框架和 ADO.NET 提供程序模型。 您还应理解命令目录树和 <xref:System.Data.Common.CommandTrees.DbExpression>。  
  
## <a name="the-role-of-the-sql-generation-module"></a>SQL 生成模块的角色  
 实体框架提供程序的 SQL 生成模块将给定的查询命令目录树转换为针对 SQL：1999兼容数据库的单个 SQL SELECT 语句。 生成的 SQL 应具有尽可能少的嵌套查询。 SQL 生成模块不应简化输出查询命令目录树。 实体框架将执行此操作，例如，消除联接和折叠连续筛选器节点。  
  
 <xref:System.Data.Common.DbProviderServices> 类是用来访问 SQL 生成层以将命令目录树转换为 <xref:System.Data.Common.DbCommand> 的开始点。  
  
## <a name="in-this-section"></a>本节内容  
 [命令目录树的形状](the-shape-of-the-command-trees.md)  
  
 [从命令目录树生成 SQL - 最佳做法](generating-sql-from-command-trees-best-practices.md)  
  
 [示例提供程序中的 SQL 生成](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a>请参阅

- [编写实体框架数据提供程序](writing-an-ef-data-provider.md)
