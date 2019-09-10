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
# <a name="sql-generation"></a><span data-ttu-id="fedc9-102">SQL 生成</span><span class="sxs-lookup"><span data-stu-id="fedc9-102">SQL Generation</span></span>
<span data-ttu-id="fedc9-103">为实体框架编写提供程序时，必须将实体框架命令目录树转换为特定数据库可以理解的 SQL，如用于 SQL Server 的 Transact-sql 或用于 Oracle 的 PL/SQL。</span><span class="sxs-lookup"><span data-stu-id="fedc9-103">When you write a provider for the Entity Framework, you must translate Entity Framework command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="fedc9-104">在本部分中，你将学习如何为实体框架提供程序开发 SQL 生成组件（适用于选择查询）。</span><span class="sxs-lookup"><span data-stu-id="fedc9-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an Entity Framework provider.</span></span> <span data-ttu-id="fedc9-105">有关 insert、update 和 delete 查询的信息，请参阅[修改 SQL 生成](modification-sql-generation.md)。</span><span class="sxs-lookup"><span data-stu-id="fedc9-105">For information about insert, update, and delete queries, see [Modification SQL Generation](modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="fedc9-106">若要理解此部分，应熟悉实体框架和 ADO.NET 提供程序模型。</span><span class="sxs-lookup"><span data-stu-id="fedc9-106">To understand this section, you should be familiar with the Entity Framework and the ADO.NET Provider Model.</span></span> <span data-ttu-id="fedc9-107">您还应理解命令目录树和 <xref:System.Data.Common.CommandTrees.DbExpression>。</span><span class="sxs-lookup"><span data-stu-id="fedc9-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="fedc9-108">SQL 生成模块的角色</span><span class="sxs-lookup"><span data-stu-id="fedc9-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="fedc9-109">实体框架提供程序的 SQL 生成模块将给定的查询命令目录树转换为针对 SQL：1999兼容数据库的单个 SQL SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="fedc9-109">The SQL generation module of an Entity Framework provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="fedc9-110">生成的 SQL 应具有尽可能少的嵌套查询。</span><span class="sxs-lookup"><span data-stu-id="fedc9-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="fedc9-111">SQL 生成模块不应简化输出查询命令目录树。</span><span class="sxs-lookup"><span data-stu-id="fedc9-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="fedc9-112">实体框架将执行此操作，例如，消除联接和折叠连续筛选器节点。</span><span class="sxs-lookup"><span data-stu-id="fedc9-112">The Entity Framework will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="fedc9-113"><xref:System.Data.Common.DbProviderServices> 类是用来访问 SQL 生成层以将命令目录树转换为 <xref:System.Data.Common.DbCommand> 的开始点。</span><span class="sxs-lookup"><span data-stu-id="fedc9-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fedc9-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="fedc9-114">In This Section</span></span>  
 [<span data-ttu-id="fedc9-115">命令目录树的形状</span><span class="sxs-lookup"><span data-stu-id="fedc9-115">The Shape of the Command Trees</span></span>](the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="fedc9-116">从命令目录树生成 SQL - 最佳做法</span><span class="sxs-lookup"><span data-stu-id="fedc9-116">Generating SQL from Command Trees - Best Practices</span></span>](generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="fedc9-117">示例提供程序中的 SQL 生成</span><span class="sxs-lookup"><span data-stu-id="fedc9-117">SQL Generation in the Sample Provider</span></span>](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="fedc9-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="fedc9-118">See also</span></span>

- [<span data-ttu-id="fedc9-119">编写实体框架数据提供程序</span><span class="sxs-lookup"><span data-stu-id="fedc9-119">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
