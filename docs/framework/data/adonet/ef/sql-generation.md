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
ms.openlocfilehash: 39f31e27f1e62d889df5a40a9ecb554c2547db8f
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="sql-generation"></a><span data-ttu-id="b55c5-102">SQL 生成</span><span class="sxs-lookup"><span data-stu-id="b55c5-102">SQL Generation</span></span>
<span data-ttu-id="b55c5-103">在编写[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]的提供程序时，必须将[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]命令目录树转换为特定数据库可理解的 SQL，如 Transact-SQL for SQL Server 或 PL/SQL for Oracle。</span><span class="sxs-lookup"><span data-stu-id="b55c5-103">When you write a provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you must translate [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="b55c5-104">在本节中，您将了解如何针对[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]提供程序开发 SQL 生成组件（用于 SELECT 查询）。</span><span class="sxs-lookup"><span data-stu-id="b55c5-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider.</span></span> <span data-ttu-id="b55c5-105">有关插入的内容，更新和删除查询，请参阅[修改 SQL 生成](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)。</span><span class="sxs-lookup"><span data-stu-id="b55c5-105">For information about insert, update, and delete queries, see [Modification SQL Generation](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="b55c5-106">若要理解本节内容，您应熟悉[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]和 ADO.NET 提供程序模型。</span><span class="sxs-lookup"><span data-stu-id="b55c5-106">To understand this section, you should be familiar with the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and the ADO.NET Provider Model.</span></span> <span data-ttu-id="b55c5-107">您还应理解命令目录树和 <xref:System.Data.Common.CommandTrees.DbExpression>。</span><span class="sxs-lookup"><span data-stu-id="b55c5-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="b55c5-108">SQL 生成模块的角色</span><span class="sxs-lookup"><span data-stu-id="b55c5-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="b55c5-109">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]提供程序的 SQL 生成模块可将给定的查询命令目录树转换为面向符合 SQL:1999 的数据库的单个 SQL SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="b55c5-109">The SQL generation module of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="b55c5-110">生成的 SQL 应具有尽可能少的嵌套查询。</span><span class="sxs-lookup"><span data-stu-id="b55c5-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="b55c5-111">SQL 生成模块不应简化输出查询命令目录树。</span><span class="sxs-lookup"><span data-stu-id="b55c5-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="b55c5-112">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]将执行此操作，例如，它将通过消除联接并折叠连续的筛选器节点来做到这一点。</span><span class="sxs-lookup"><span data-stu-id="b55c5-112">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="b55c5-113"><xref:System.Data.Common.DbProviderServices> 类是用来访问 SQL 生成层以将命令目录树转换为 <xref:System.Data.Common.DbCommand> 的开始点。</span><span class="sxs-lookup"><span data-stu-id="b55c5-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b55c5-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="b55c5-114">In This Section</span></span>  
 [<span data-ttu-id="b55c5-115">命令目录树的形状</span><span class="sxs-lookup"><span data-stu-id="b55c5-115">The Shape of the Command Trees</span></span>](../../../../../docs/framework/data/adonet/ef/the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="b55c5-116">从命令目录树的最佳实践生成 SQL</span><span class="sxs-lookup"><span data-stu-id="b55c5-116">Generating SQL from Command Trees - Best Practices</span></span>](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="b55c5-117">该示例提供程序中的 SQL 生成</span><span class="sxs-lookup"><span data-stu-id="b55c5-117">SQL Generation in the Sample Provider</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="b55c5-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b55c5-118">See Also</span></span>  
 [<span data-ttu-id="b55c5-119">编写实体框架数据提供程序</span><span class="sxs-lookup"><span data-stu-id="b55c5-119">Writing an Entity Framework Data Provider</span></span>](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
