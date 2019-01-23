---
title: 规范函数
ms.date: 03/30/2017
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
ms.openlocfilehash: 4657fd2b68008e4194fc39982dc2ac5b34a644ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513875"
---
# <a name="canonical-functions"></a><span data-ttu-id="7dc7a-102">规范函数</span><span class="sxs-lookup"><span data-stu-id="7dc7a-102">Canonical Functions</span></span>
<span data-ttu-id="7dc7a-103">本节讨论所有数据提供程序支持的并可由所有查询技术使用的规范函数。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-103">This section discusses canonical functions that are supported by all data providers, and can be used by all querying technologies.</span></span> <span data-ttu-id="7dc7a-104">规范函数不能由提供程序扩展。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-104">Canonical functions cannot be extended by a provider.</span></span>  
  
 <span data-ttu-id="7dc7a-105">这些规范函数将转换为提供程序的相应数据源功能。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-105">These canonical functions will be translated to the corresponding data source functionality for the provider.</span></span> <span data-ttu-id="7dc7a-106">这样，就可以用一种在不同数据源间通用的形式表示函数调用。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-106">This allows for function invocations expressed in a common form across data sources.</span></span>  
  
 <span data-ttu-id="7dc7a-107">因为这些规范函数独立于数据源，所以会按概念模型中的类型来定义规范函数的参数和返回类型。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-107">Because these canonical functions are independent of data sources, argument and return types of canonical functions are defined in terms of types in the conceptual model.</span></span> <span data-ttu-id="7dc7a-108">但某些数据源可能不支持概念模型中的所有类型。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-108">However, some data sources might not support all types in the conceptual model.</span></span>  
  
 <span data-ttu-id="7dc7a-109">当在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询中使用规范函数时，将在数据源中调用适当的函数。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-109">When canonical functions are used in an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query, the appropriate function will be called at the data source.</span></span>  
  
 <span data-ttu-id="7dc7a-110">所有规范函数都同时显式指定 null 输入行为和错误条件。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-110">All canonical functions have both null-input behavior and error conditions explicitly specified.</span></span> <span data-ttu-id="7dc7a-111">存储提供程序应遵循此行为，但 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] 不强制执行此行为。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-111">Store providers should comply with that behavior, but [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] does not enforce this behavior.</span></span>  
  
 <span data-ttu-id="7dc7a-112">对于 LINQ 方案，对 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] 所执行的查询涉及将 CLR 方法映射到基础数据源中的方法。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-112">For LINQ scenarios, queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] involve mapping CLR methods to methods in the underlying data source.</span></span> <span data-ttu-id="7dc7a-113">CLR 方法映射到规范函数，这样，无论数据源如何，特定的方法集都会正确映射。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-113">The CLR methods map to canonical functions, so that a specific set of methods will correctly map, regardless of the data source.</span></span>  
  
## <a name="canonical-functions-namespace"></a><span data-ttu-id="7dc7a-114">规范函数命名空间</span><span class="sxs-lookup"><span data-stu-id="7dc7a-114">Canonical Functions Namespace</span></span>  
 <span data-ttu-id="7dc7a-115">规范函数的命名空间是 <xref:System.Data.Metadata.Edm>。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-115">The namespace for canonical function is <xref:System.Data.Metadata.Edm>.</span></span> <span data-ttu-id="7dc7a-116"><xref:System.Data.Metadata.Edm> 命名空间自动包含在所有查询中。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-116">The <xref:System.Data.Metadata.Edm> namespace is automatically included in all queries.</span></span> <span data-ttu-id="7dc7a-117">但如果导入的另一个命名空间包含与规范函数（在 <xref:System.Data.Metadata.Edm> 命名空间中）同名的函数，则必须指定命名空间。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-117">However, if another namespace is imported that contains a function with the same name as a canonical function (in the <xref:System.Data.Metadata.Edm> namespace), you must specify the namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7dc7a-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="7dc7a-118">In This Section</span></span>  
 [<span data-ttu-id="7dc7a-119">聚合 Canonical 函数</span><span class="sxs-lookup"><span data-stu-id="7dc7a-119">Aggregate Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)  
 <span data-ttu-id="7dc7a-120">讨论 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 聚合规范函数。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-120">Discusses aggregate [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="7dc7a-121">数学 Canonical 函数</span><span class="sxs-lookup"><span data-stu-id="7dc7a-121">Math Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)  
 <span data-ttu-id="7dc7a-122">讨论 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 数学规范函数。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-122">Discusses math [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="7dc7a-123">字符串 Canonical 函数</span><span class="sxs-lookup"><span data-stu-id="7dc7a-123">String Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)  
 <span data-ttu-id="7dc7a-124">讨论 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 字符串规范函数。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-124">Discusses string [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="7dc7a-125">日期和事件 Canonical 函数</span><span class="sxs-lookup"><span data-stu-id="7dc7a-125">Date and Time Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)  
 <span data-ttu-id="7dc7a-126">讨论 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 日期和时间规范函数。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-126">Discusses date and time [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="7dc7a-127">按位 Canonical 函数</span><span class="sxs-lookup"><span data-stu-id="7dc7a-127">Bitwise Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)  
 <span data-ttu-id="7dc7a-128">讨论 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 按位规范函数。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-128">Discusses bitwise [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="7dc7a-129">空间函数</span><span class="sxs-lookup"><span data-stu-id="7dc7a-129">Spatial Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/spatial-functions.md)  
 <span data-ttu-id="7dc7a-130">讨论空间 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 规范函数。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-130">Discusses Spatial [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="7dc7a-131">其他 Canonical 函数</span><span class="sxs-lookup"><span data-stu-id="7dc7a-131">Other Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/other-canonical-functions.md)  
 <span data-ttu-id="7dc7a-132">讨论未分类为按位、日期/时间、字符串、数字或聚合函数的函数。</span><span class="sxs-lookup"><span data-stu-id="7dc7a-132">Discusses functions not classified as bitwise, date/time, string, math, or aggregate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dc7a-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="7dc7a-133">See also</span></span>
- [<span data-ttu-id="7dc7a-134">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="7dc7a-134">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="7dc7a-135">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="7dc7a-135">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="7dc7a-136">SQL Server 函数映射的规范化概念模型</span><span class="sxs-lookup"><span data-stu-id="7dc7a-136">Conceptual Model Canonical to SQL Server Functions Mapping</span></span>](../../../../../../docs/framework/data/adonet/ef/conceptual-model-canonical-to-sql-server-functions-mapping.md)
- [<span data-ttu-id="7dc7a-137">用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="7dc7a-137">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)
