---
title: Entity SQL 概述
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 54a3832cffbf3376e6b3ab0826b280b676ccc1a0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534639"
---
# <a name="entity-sql-overview"></a><span data-ttu-id="225e1-102">Entity SQL 概述</span><span class="sxs-lookup"><span data-stu-id="225e1-102">Entity SQL Overview</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="225e1-103">是一种类似于 SQL 的语言，用于在[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]中查询概念模型。</span><span class="sxs-lookup"><span data-stu-id="225e1-103">is a SQL-like language that enables you to query conceptual models in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="225e1-104">概念模型表示为实体和关系数据和[!INCLUDE[esql](../../../../../../includes/esql-md.md)]可以查询这些实体和关系所熟悉的用户使用过 SQL 的格式。</span><span class="sxs-lookup"><span data-stu-id="225e1-104">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  
  
 <span data-ttu-id="225e1-105">[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] 使用存储特定的数据提供程序，将一般 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 转换为存储特定的查询。</span><span class="sxs-lookup"><span data-stu-id="225e1-105">The [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="225e1-106">EntityClient 提供程序提供一种方式，用于针对实体模型执行 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 命令并返回包括标量结果、结果集和对象图在内的丰富类型数据。</span><span class="sxs-lookup"><span data-stu-id="225e1-106">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="225e1-107">构造 <xref:System.Data.EntityClient.EntityCommand> 对象时，可以指定一个存储过程名称或者通过将 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询字符串分配该对象的 <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> 属性来指定查询文本。</span><span class="sxs-lookup"><span data-stu-id="225e1-107">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="225e1-108"><xref:System.Data.EntityClient.EntityDataReader> 公开对 EDM 执行 <xref:System.Data.EntityClient.EntityCommand> 的结果。</span><span class="sxs-lookup"><span data-stu-id="225e1-108">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="225e1-109">若要执行返回 <xref:System.Data.EntityClient.EntityDataReader> 的命令，请调用 <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>。</span><span class="sxs-lookup"><span data-stu-id="225e1-109">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="225e1-110">除了 EntityClient 提供程序之外，[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]还允许您使用 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 对概念模型执行查询，并以强类型 CLR 对象的形式返回数据，这些对象是实体类型的实例。</span><span class="sxs-lookup"><span data-stu-id="225e1-110">In addition to the EntityClient provider, the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly-typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="225e1-111">有关详细信息，请参阅[使用对象](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="225e1-111">For more information, see [Working with Objects](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span></span>  
  
 <span data-ttu-id="225e1-112">本节提供 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 的概念信息。</span><span class="sxs-lookup"><span data-stu-id="225e1-112">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="225e1-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="225e1-113">In This Section</span></span>  
 [<span data-ttu-id="225e1-114">实体 SQL 与 Transact-SQL 的区别</span><span class="sxs-lookup"><span data-stu-id="225e1-114">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="225e1-115">实体 SQL 快速参考</span><span class="sxs-lookup"><span data-stu-id="225e1-115">Entity SQL Quick Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="225e1-116">类型系统</span><span class="sxs-lookup"><span data-stu-id="225e1-116">Type System</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)  
  
 [<span data-ttu-id="225e1-117">类型定义</span><span class="sxs-lookup"><span data-stu-id="225e1-117">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="225e1-118">构造类型</span><span class="sxs-lookup"><span data-stu-id="225e1-118">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="225e1-119">查询计划缓存</span><span class="sxs-lookup"><span data-stu-id="225e1-119">Query Plan Caching</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="225e1-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="225e1-120">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
  
 [<span data-ttu-id="225e1-121">标识符</span><span class="sxs-lookup"><span data-stu-id="225e1-121">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
  
 [<span data-ttu-id="225e1-122">参数</span><span class="sxs-lookup"><span data-stu-id="225e1-122">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
  
 [<span data-ttu-id="225e1-123">变量</span><span class="sxs-lookup"><span data-stu-id="225e1-123">Variables</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md)  
  
 [<span data-ttu-id="225e1-124">不支持的表达式</span><span class="sxs-lookup"><span data-stu-id="225e1-124">Unsupported Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="225e1-125">文本</span><span class="sxs-lookup"><span data-stu-id="225e1-125">Literals</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md)  
  
 [<span data-ttu-id="225e1-126">NULL 文本和类型推理</span><span class="sxs-lookup"><span data-stu-id="225e1-126">Null Literals and Type Inference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="225e1-127">输入字符集</span><span class="sxs-lookup"><span data-stu-id="225e1-127">Input Character Set</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="225e1-128">查询表达式</span><span class="sxs-lookup"><span data-stu-id="225e1-128">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="225e1-129">函数</span><span class="sxs-lookup"><span data-stu-id="225e1-129">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)  
  
 [<span data-ttu-id="225e1-130">运算符优先级</span><span class="sxs-lookup"><span data-stu-id="225e1-130">Operator Precedence</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="225e1-131">分页</span><span class="sxs-lookup"><span data-stu-id="225e1-131">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
  
 [<span data-ttu-id="225e1-132">比较语义</span><span class="sxs-lookup"><span data-stu-id="225e1-132">Comparison Semantics</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="225e1-133">撰写嵌套的实体 SQL 查询</span><span class="sxs-lookup"><span data-stu-id="225e1-133">Composing Nested Entity SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="225e1-134">可以为 NULL 的结构化类型</span><span class="sxs-lookup"><span data-stu-id="225e1-134">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="225e1-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="225e1-135">See also</span></span>
- [<span data-ttu-id="225e1-136">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="225e1-136">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="225e1-137">实体 SQL 语言</span><span class="sxs-lookup"><span data-stu-id="225e1-137">Entity SQL Language</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [<span data-ttu-id="225e1-138">CSDL、SSDL 和 MSL 规范</span><span class="sxs-lookup"><span data-stu-id="225e1-138">CSDL, SSDL, and MSL Specifications</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
