---
title: Entity SQL 概述
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 880b81f2b6d4c4b893d28c919490f88dfb2a42e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150371"
---
# <a name="entity-sql-overview"></a><span data-ttu-id="619a3-102">Entity SQL 概述</span><span class="sxs-lookup"><span data-stu-id="619a3-102">Entity SQL Overview</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="619a3-103">是一种类似于 SQL 的语言，使您能够在实体框架中查询概念模型。</span><span class="sxs-lookup"><span data-stu-id="619a3-103">is a SQL-like language that enables you to query conceptual models in the Entity Framework.</span></span> <span data-ttu-id="619a3-104">概念模型将数据表示为实体和关系，[!INCLUDE[esql](../../../../../../includes/esql-md.md)]并允许您以使用 SQL 的实体和关系所熟悉的格式查询这些实体和关系。</span><span class="sxs-lookup"><span data-stu-id="619a3-104">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  

 <span data-ttu-id="619a3-105">实体框架与特定于存储的数据提供程序合作，将泛型[!INCLUDE[esql](../../../../../../includes/esql-md.md)]转换为特定于存储的查询。</span><span class="sxs-lookup"><span data-stu-id="619a3-105">The Entity Framework works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="619a3-106">EntityClient 提供程序提供一种方式，用于针对实体模型执行 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 命令并返回包括标量结果、结果集和对象图在内的丰富类型数据。</span><span class="sxs-lookup"><span data-stu-id="619a3-106">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="619a3-107">构造 <xref:System.Data.EntityClient.EntityCommand> 对象时，可以指定一个存储过程名称或者通过将 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询字符串分配该对象的 <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> 属性来指定查询文本。</span><span class="sxs-lookup"><span data-stu-id="619a3-107">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="619a3-108"><xref:System.Data.EntityClient.EntityDataReader> 公开对 EDM 执行 <xref:System.Data.EntityClient.EntityCommand> 的结果。</span><span class="sxs-lookup"><span data-stu-id="619a3-108">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="619a3-109">若要执行返回 <xref:System.Data.EntityClient.EntityDataReader> 的命令，请调用 <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>。</span><span class="sxs-lookup"><span data-stu-id="619a3-109">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="619a3-110">除了 EntityClient 提供程序之外，实体框架还允许您使用[!INCLUDE[esql](../../../../../../includes/esql-md.md)]执行针对概念模型的查询，并将数据作为实体类型的实例的强类型 CLR 对象返回数据。</span><span class="sxs-lookup"><span data-stu-id="619a3-110">In addition to the EntityClient provider, the Entity Framework enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly-typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="619a3-111">有关详细信息，请参阅[使用对象](../working-with-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="619a3-111">For more information, see [Working with Objects](../working-with-objects.md).</span></span>  
  
 <span data-ttu-id="619a3-112">本节提供 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 的概念信息。</span><span class="sxs-lookup"><span data-stu-id="619a3-112">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="619a3-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="619a3-113">In This Section</span></span>  
 [<span data-ttu-id="619a3-114">Entity SQL 与 Transact-SQL 有何不同</span><span class="sxs-lookup"><span data-stu-id="619a3-114">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="619a3-115">实体 SQL 快速参考</span><span class="sxs-lookup"><span data-stu-id="619a3-115">Entity SQL Quick Reference</span></span>](entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="619a3-116">类型系统</span><span class="sxs-lookup"><span data-stu-id="619a3-116">Type System</span></span>](type-system-entity-sql.md)  
  
 [<span data-ttu-id="619a3-117">类型定义</span><span class="sxs-lookup"><span data-stu-id="619a3-117">Type Definitions</span></span>](type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="619a3-118">构造类型</span><span class="sxs-lookup"><span data-stu-id="619a3-118">Constructing Types</span></span>](constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="619a3-119">查询计划缓存</span><span class="sxs-lookup"><span data-stu-id="619a3-119">Query Plan Caching</span></span>](query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="619a3-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="619a3-120">Namespaces</span></span>](namespaces-entity-sql.md)  
  
 [<span data-ttu-id="619a3-121">标识符</span><span class="sxs-lookup"><span data-stu-id="619a3-121">Identifiers</span></span>](identifiers-entity-sql.md)  
  
 [<span data-ttu-id="619a3-122">参数</span><span class="sxs-lookup"><span data-stu-id="619a3-122">Parameters</span></span>](parameters-entity-sql.md)  
  
 [<span data-ttu-id="619a3-123">变量</span><span class="sxs-lookup"><span data-stu-id="619a3-123">Variables</span></span>](variables-entity-sql.md)  
  
 [<span data-ttu-id="619a3-124">不支持的表达式</span><span class="sxs-lookup"><span data-stu-id="619a3-124">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="619a3-125">文字</span><span class="sxs-lookup"><span data-stu-id="619a3-125">Literals</span></span>](literals-entity-sql.md)  
  
 [<span data-ttu-id="619a3-126">NULL 文本和类型推理</span><span class="sxs-lookup"><span data-stu-id="619a3-126">Null Literals and Type Inference</span></span>](null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="619a3-127">输入字符集</span><span class="sxs-lookup"><span data-stu-id="619a3-127">Input Character Set</span></span>](input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="619a3-128">查询表达式</span><span class="sxs-lookup"><span data-stu-id="619a3-128">Query Expressions</span></span>](query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="619a3-129">函数</span><span class="sxs-lookup"><span data-stu-id="619a3-129">Functions</span></span>](functions-entity-sql.md)  
  
 [<span data-ttu-id="619a3-130">运算符优先级</span><span class="sxs-lookup"><span data-stu-id="619a3-130">Operator Precedence</span></span>](operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="619a3-131">分页</span><span class="sxs-lookup"><span data-stu-id="619a3-131">Paging</span></span>](paging-entity-sql.md)  
  
 [<span data-ttu-id="619a3-132">比较语义</span><span class="sxs-lookup"><span data-stu-id="619a3-132">Comparison Semantics</span></span>](comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="619a3-133">撰写嵌套的 Entity SQL 查询</span><span class="sxs-lookup"><span data-stu-id="619a3-133">Composing Nested Entity SQL Queries</span></span>](composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="619a3-134">可以为 NULL 的结构化类型</span><span class="sxs-lookup"><span data-stu-id="619a3-134">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="619a3-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="619a3-135">See also</span></span>

- [<span data-ttu-id="619a3-136">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="619a3-136">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="619a3-137">Entity SQL 语言</span><span class="sxs-lookup"><span data-stu-id="619a3-137">Entity SQL Language</span></span>](entity-sql-language.md)
- [<span data-ttu-id="619a3-138">CSDL、SSDL 和 MSL 规范</span><span class="sxs-lookup"><span data-stu-id="619a3-138">CSDL, SSDL, and MSL Specifications</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
