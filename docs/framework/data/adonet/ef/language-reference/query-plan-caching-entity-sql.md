---
title: 查询计划缓存 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 90b0c685-5ef2-461b-98b4-c3c0a2b253c7
ms.openlocfilehash: 9f042d46d9a601c1091e36f8d81ce8f933140b20
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178173"
---
# <a name="query-plan-caching-entity-sql"></a><span data-ttu-id="d01cb-102">查询计划缓存 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d01cb-102">Query Plan Caching (Entity SQL)</span></span>
<span data-ttu-id="d01cb-103">每当试图执行查询时，查询管道都会查找它的查询计划缓存，以便了解该查询是否已经编译且可用。</span><span class="sxs-lookup"><span data-stu-id="d01cb-103">Whenever an attempt to execute a query is made, the query pipeline looks up its query plan cache to see whether the exact query is already compiled and available.</span></span> <span data-ttu-id="d01cb-104">如果答案是肯定的，它将重用缓存的计划而不是生成新的计划。</span><span class="sxs-lookup"><span data-stu-id="d01cb-104">If so, it reuses the cached plan rather than building a new one.</span></span> <span data-ttu-id="d01cb-105">如果未在查询计划缓存中找到匹配的计划，则会编译和缓存该查询。</span><span class="sxs-lookup"><span data-stu-id="d01cb-105">If a match is not found in the query plan cache, the query is compiled and cached.</span></span> <span data-ttu-id="d01cb-106">查询由其 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 文本和参数集合（名称和类型）标识。</span><span class="sxs-lookup"><span data-stu-id="d01cb-106">A query is identified by its [!INCLUDE[esql](../../../../../../includes/esql-md.md)] text and parameter collection (names and types).</span></span> <span data-ttu-id="d01cb-107">所有文本比较都区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d01cb-107">All text comparisons are case-sensitive.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d01cb-108">配置</span><span class="sxs-lookup"><span data-stu-id="d01cb-108">Configuration</span></span>  
 <span data-ttu-id="d01cb-109">可以通过 <xref:System.Data.EntityClient.EntityCommand> 配置查询计划缓存。</span><span class="sxs-lookup"><span data-stu-id="d01cb-109">Query plan caching is configurable through the <xref:System.Data.EntityClient.EntityCommand>.</span></span>  
  
 <span data-ttu-id="d01cb-110">若要通过 <xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=nameWithType> 启用或禁用查询计划缓存，请将此属性设置为 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="d01cb-110">To enable or disable query plan caching through <xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=nameWithType>, set this property to `true` or `false`.</span></span> <span data-ttu-id="d01cb-111">为单个不太可能使用一次以上的动态查询禁用计划缓存可以改进性能。</span><span class="sxs-lookup"><span data-stu-id="d01cb-111">Disabling plan caching for individual dynamic queries that are unlikely to be used more then once improves performance.</span></span>  
  
 <span data-ttu-id="d01cb-112">可以通过 <xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A> 启用查询计划缓存。</span><span class="sxs-lookup"><span data-stu-id="d01cb-112">You can enable query plan caching through <xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A>.</span></span>  
  
## <a name="recommended-practice"></a><span data-ttu-id="d01cb-113">推荐的做法</span><span class="sxs-lookup"><span data-stu-id="d01cb-113">Recommended Practice</span></span>  
 <span data-ttu-id="d01cb-114">一般来说，应该避免使用动态查询。</span><span class="sxs-lookup"><span data-stu-id="d01cb-114">Dynamic queries should be avoided, in general.</span></span> <span data-ttu-id="d01cb-115">下面的动态查询示例容易受到 SQL 注入式攻击，因为该示例在不进行任何验证的情况下直接获取用户输入。</span><span class="sxs-lookup"><span data-stu-id="d01cb-115">The following dynamic query example is vulnerable to SQL injection attacks, because it takes user input directly without any validation.</span></span>  
  
 `"SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp WHERE sp.EmployeeID = " + employeeTextBox.Text;`  
  
 <span data-ttu-id="d01cb-116">如果您确实要使用动态生成的查询，请考虑禁用查询计划缓存，从而避免不必要地将内存用于不太可能重复使用的缓存项。</span><span class="sxs-lookup"><span data-stu-id="d01cb-116">If you do use dynamically generated queries, consider disabling query plan caching to avoid unnecessary memory consumption for cache entries that are unlikely to be reused.</span></span>  
  
 <span data-ttu-id="d01cb-117">静态查询和参数化查询的查询计划缓存可以提供性能方面的好处。</span><span class="sxs-lookup"><span data-stu-id="d01cb-117">Query plan caching on static queries and parameterized queries can provide performance benefits.</span></span> <span data-ttu-id="d01cb-118">下面是一个静态查询示例：</span><span class="sxs-lookup"><span data-stu-id="d01cb-118">The following is an example of a static query:</span></span>  
  
```  
"SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp";  
```  
  
 <span data-ttu-id="d01cb-119">为了通过查询计划缓存正确匹配查询，查询应该遵守以下要求：</span><span class="sxs-lookup"><span data-stu-id="d01cb-119">For queries to be matched properly by the query plan cache, they should comply with the following requirements:</span></span>  
  
-   <span data-ttu-id="d01cb-120">查询文本应该具有常量模式，最好是常量字符串或资源。</span><span class="sxs-lookup"><span data-stu-id="d01cb-120">Query text should be a constant pattern, preferably a constant string or a resource.</span></span>  
  
-   <xref:System.Data.EntityClient.EntityParameter> <span data-ttu-id="d01cb-121">或<xref:System.Data.Objects.ObjectParameter>只要必须传递一个用户提供的值应使用。</span><span class="sxs-lookup"><span data-stu-id="d01cb-121">or <xref:System.Data.Objects.ObjectParameter> should be used wherever a user-supplied value must be passed.</span></span>  
  
 <span data-ttu-id="d01cb-122">应该避免以下查询模式，这种模式不必要地消耗查询计划缓存中的存储槽：</span><span class="sxs-lookup"><span data-stu-id="d01cb-122">You should avoid the following query patterns, which unnecessarily consume slots in the query plan cache:</span></span>  
  
-   <span data-ttu-id="d01cb-123">对文本中字母大小写的更改。</span><span class="sxs-lookup"><span data-stu-id="d01cb-123">Changes to letter case in the text.</span></span>  
  
-   <span data-ttu-id="d01cb-124">对空格的更改。</span><span class="sxs-lookup"><span data-stu-id="d01cb-124">Changes to white space.</span></span>  
  
-   <span data-ttu-id="d01cb-125">对字面值的更改。</span><span class="sxs-lookup"><span data-stu-id="d01cb-125">Changes to literal values.</span></span>  
  
-   <span data-ttu-id="d01cb-126">对注释内部文本的更改。</span><span class="sxs-lookup"><span data-stu-id="d01cb-126">Changes to text inside comments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d01cb-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="d01cb-127">See also</span></span>

- [<span data-ttu-id="d01cb-128">Entity SQL 概述</span><span class="sxs-lookup"><span data-stu-id="d01cb-128">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
