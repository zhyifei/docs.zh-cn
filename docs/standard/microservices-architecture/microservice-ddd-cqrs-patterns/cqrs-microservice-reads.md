---
title: "在 CQRS 微服务中实现读取/查询"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |在 CQRS 微服务中实现读取/查询"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e017aaaa701d8033110be8d6244d3e1120fc4fd9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a><span data-ttu-id="7c48b-104">在 CQRS 微服务中实现读取/查询</span><span class="sxs-lookup"><span data-stu-id="7c48b-104">Implementing reads/queries in a CQRS microservice</span></span>

<span data-ttu-id="7c48b-105">对于读取/查询，排序的微服务构成从 eShopOnContainers 引用应用程序实现独立于 DDD 模型和事务的区域的查询。</span><span class="sxs-lookup"><span data-stu-id="7c48b-105">For reads/queries, the ordering microservice from the eShopOnContainers reference application implements the queries independently from the DDD model and transactional area.</span></span> <span data-ttu-id="7c48b-106">这样做的主要原因和事务的查询的需求较大不相同。</span><span class="sxs-lookup"><span data-stu-id="7c48b-106">This was done primarily because the demands for queries and for transactions are drastically different.</span></span> <span data-ttu-id="7c48b-107">写入执行必须符合域逻辑的事务。</span><span class="sxs-lookup"><span data-stu-id="7c48b-107">Writes execute transactions that must be compliant with the domain logic.</span></span> <span data-ttu-id="7c48b-108">另一方面，查询是幂等的和可以分隔开来域规则。</span><span class="sxs-lookup"><span data-stu-id="7c48b-108">Queries, on the other hand, are idempotent and can be segregated from the domain rules.</span></span>

<span data-ttu-id="7c48b-109">这种方法很简单，如图 9-3 中所示。</span><span class="sxs-lookup"><span data-stu-id="7c48b-109">The approach is simple, as shown in Figure 9-3.</span></span> <span data-ttu-id="7c48b-110">API 接口实现的 Web API 控制器使用任何基础结构 （如微 ORM 如 Dapper） 并返回动态 Viewmodel 具体取决于 UI 应用程序的需求。</span><span class="sxs-lookup"><span data-stu-id="7c48b-110">The API interface is implemented by the Web API controllers using any infrastructure (such as a micro ORM like Dapper) and returning dynamic ViewModels depending on the needs of the UI applications.</span></span>

![](./media/image3.png)

<span data-ttu-id="7c48b-111">**图 9-3**。</span><span class="sxs-lookup"><span data-stu-id="7c48b-111">**Figure 9-3**.</span></span> <span data-ttu-id="7c48b-112">CQRS 微服务中查询的最简单的方法</span><span class="sxs-lookup"><span data-stu-id="7c48b-112">The simplest approach for queries in a CQRS microservice</span></span>

<span data-ttu-id="7c48b-113">这是最简单的可能的方法的查询。</span><span class="sxs-lookup"><span data-stu-id="7c48b-113">This is the simplest possible approach for queries.</span></span> <span data-ttu-id="7c48b-114">查询定义查询数据库，并返回每个查询动态生成动态视图模型。</span><span class="sxs-lookup"><span data-stu-id="7c48b-114">The query definitions query the database and return a dynamic ViewModel built on the fly for each query.</span></span> <span data-ttu-id="7c48b-115">由于查询是幂等的它们不会更改数据，而无论多少次运行查询。</span><span class="sxs-lookup"><span data-stu-id="7c48b-115">Since the queries are idempotent, they will not change the data no matter how many times you run a query.</span></span> <span data-ttu-id="7c48b-116">因此，不需要通过事务端，如聚合和其他模式中使用任何 DDD 模式进行限制，并且正因如此，从事务区域分隔查询。</span><span class="sxs-lookup"><span data-stu-id="7c48b-116">Therefore, you do not need to be restricted by any DDD pattern used in the transactional side, like aggregates and other patterns, and that is why queries are separated from the transactional area.</span></span> <span data-ttu-id="7c48b-117">你只需查询数据库中的用户界面需要的数据，并返回不需要被静态地动态 ViewModel 随处 （用于 Viewmodel 任何类） 除外中定义自己的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="7c48b-117">You simply query the database for the data that the UI needs and return a dynamic ViewModel that does not need to be statically defined anywhere (no classes for the ViewModels) except in the SQL statements themselves.</span></span>

<span data-ttu-id="7c48b-118">由于这是一种简单方法，代码所需的查询端 (如代码使用 ORM 喜欢 micro [Dapper](https://github.com/StackExchange/Dapper)) 可以实现[同一 Web API 项目中](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs)。</span><span class="sxs-lookup"><span data-stu-id="7c48b-118">Since this is a simple approach, the code required for the queries side (such as code using a micro ORM like [Dapper](https://github.com/StackExchange/Dapper)) can be implemented [within the same Web API project](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span></span> <span data-ttu-id="7c48b-119">图 9-4 演示了此过程。</span><span class="sxs-lookup"><span data-stu-id="7c48b-119">Figure 9-4 shows this.</span></span> <span data-ttu-id="7c48b-120">在中定义查询**Ordering.API** eShopOnContainers 解决方案中的微服务项目。</span><span class="sxs-lookup"><span data-stu-id="7c48b-120">The queries are defined in the **Ordering.API** microservice project within the eShopOnContainers solution.</span></span>

![](./media/image4.png)

<span data-ttu-id="7c48b-121">**图 9-4**。</span><span class="sxs-lookup"><span data-stu-id="7c48b-121">**Figure 9-4**.</span></span> <span data-ttu-id="7c48b-122">在 eShopOnContainers 排序微服务中的查询</span><span class="sxs-lookup"><span data-stu-id="7c48b-122">Queries in the Ordering microservice in eShopOnContainers</span></span>

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a><span data-ttu-id="7c48b-123">使用 Viewmodel 专门供客户端应用，独立于域模型约束</span><span class="sxs-lookup"><span data-stu-id="7c48b-123">Using ViewModels specifically made for client apps, independent from domain model constraints</span></span>

<span data-ttu-id="7c48b-124">由于执行查询以获取客户端应用程序所需的数据，则返回的类型可以专门进行对于客户端，在基于由查询返回的数据。</span><span class="sxs-lookup"><span data-stu-id="7c48b-124">Since the queries are performed to obtain the data needed by the client applications, the returned type can be specifically made for the clients, based on the data returned by the queries.</span></span> <span data-ttu-id="7c48b-125">这些模型或数据传输对象 (Dto)，称为 Viewmodel。</span><span class="sxs-lookup"><span data-stu-id="7c48b-125">These models, or Data Transfer Objects (DTOs), are called ViewModels.</span></span>

<span data-ttu-id="7c48b-126">返回的数据 (ViewModel) 可以联接来自多个实体或表的数据，在数据库中，或甚至可跨多个事务的区域的域模型中定义的聚合的结果。</span><span class="sxs-lookup"><span data-stu-id="7c48b-126">The returned data (ViewModel) can be the result of joining data from multiple entities or tables in the database, or even across multiple aggregates defined in the domain model for the transactional area.</span></span> <span data-ttu-id="7c48b-127">在这种情况下，由于你要创建查询独立的域模型，完全忽略聚合边界和约束，并且你是可用来查询任何表和列可能需要。</span><span class="sxs-lookup"><span data-stu-id="7c48b-127">In this case, because you are creating queries independent of the domain model, the aggregates boundaries and constraints are completely ignored and you are free to query any table and column you might need.</span></span> <span data-ttu-id="7c48b-128">此方法为开发人员创建或更新查询提供极大的灵活性和工作效率。</span><span class="sxs-lookup"><span data-stu-id="7c48b-128">This approach provides great flexibility and productivity for the developers creating or updating the queries.</span></span>

<span data-ttu-id="7c48b-129">Viewmodel 可以是在类中定义的静态类型。</span><span class="sxs-lookup"><span data-stu-id="7c48b-129">The ViewModels can be static types defined in classes.</span></span> <span data-ttu-id="7c48b-130">或者可以创建动态基于查询执行 （如在排序的微服务中实现），这是非常灵活的开发人员。</span><span class="sxs-lookup"><span data-stu-id="7c48b-130">Or they can be created dynamically based on the queries performed (as is implemented in the ordering microservice), which is very agile for developers.</span></span>

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a><span data-ttu-id="7c48b-131">使用 Dapper 作为微型 ORM 执行查询</span><span class="sxs-lookup"><span data-stu-id="7c48b-131">Using Dapper as a micro ORM to perform queries</span></span> 

<span data-ttu-id="7c48b-132">用于查询，可以使用任何微型 ORM、 实体框架核心或甚至纯 ADO.NET。</span><span class="sxs-lookup"><span data-stu-id="7c48b-132">You can use any micro ORM, Entity Framework Core, or even plain ADO.NET for querying.</span></span> <span data-ttu-id="7c48b-133">在示例应用程序，我们将选择 Dapper 中常用的微型 ORM 一个很好示例作为 eShopOnContainers 排序微服务构成的。</span><span class="sxs-lookup"><span data-stu-id="7c48b-133">In the sample application, we selected Dapper for the ordering microservice in eShopOnContainers as a good example of a popular micro ORM.</span></span> <span data-ttu-id="7c48b-134">它可以具有卓越性能，运行纯 SQL 查询，因为它是一个非常轻量的框架。</span><span class="sxs-lookup"><span data-stu-id="7c48b-134">It can run plain SQL queries with great performance, because it is a very light framework.</span></span> <span data-ttu-id="7c48b-135">使用 Dapper，你可以编写可访问和联接多个表的 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="7c48b-135">Using Dapper, you can write a SQL query that can access and join multiple tables.</span></span>

<span data-ttu-id="7c48b-136">Dapper 是开放源代码项目 （由 Sam Saffron 创建的原始），并且是在中使用的构建基块的一部分[堆栈溢出](https://stackoverflow.com/)。</span><span class="sxs-lookup"><span data-stu-id="7c48b-136">Dapper is an open source project (original created by Sam Saffron), and is part of the building blocks used in [Stack Overflow](https://stackoverflow.com/).</span></span> <span data-ttu-id="7c48b-137">若要使用 Dapper，只需将其通过安装[Dapper NuGet 包](https://www.nuget.org/packages/Dapper)下, 图中所示。</span><span class="sxs-lookup"><span data-stu-id="7c48b-137">To use Dapper, you just need to install it through the [Dapper NuGet package](https://www.nuget.org/packages/Dapper), as shown in the following figure.</span></span>

![](./media/image5.png)

<span data-ttu-id="7c48b-138">你还需要添加 using 语句，使你的代码有权访问 Dapper 扩展方法。</span><span class="sxs-lookup"><span data-stu-id="7c48b-138">You will also need to add a using statement so your code has access to the Dapper extension methods.</span></span>

<span data-ttu-id="7c48b-139">在代码中使用 Dapper 时，你将直接使用 SqlClient 类 System.Data.SqlClient 命名空间中提供。</span><span class="sxs-lookup"><span data-stu-id="7c48b-139">When you use Dapper in your code, you directly use the SqlClient class available in the System.Data.SqlClient namespace.</span></span> <span data-ttu-id="7c48b-140">通过 QueryAsync 方法和其他扩展方法，它 SqlClient 类进行扩展，你只需直观且高性能的方式运行查询。</span><span class="sxs-lookup"><span data-stu-id="7c48b-140">Through the QueryAsync method and other extension methods which extend the SqlClient class, you can simply run queries in a straightforward and performant way.</span></span>

## <a name="dynamic-and-static-viewmodels"></a><span data-ttu-id="7c48b-141">动态和静态 Viewmodel</span><span class="sxs-lookup"><span data-stu-id="7c48b-141">Dynamic and static ViewModels</span></span>

<span data-ttu-id="7c48b-142">大部分由查询返回 Viewmodel 排序微服务构成从下面的代码中所示，作为实现*动态*。</span><span class="sxs-lookup"><span data-stu-id="7c48b-142">As shown in the following code from the ordering microservice, most of the ViewModels returned by the queries are implemented as *dynamic*.</span></span> <span data-ttu-id="7c48b-143">这意味着要返回的属性的子集基于查询本身。</span><span class="sxs-lookup"><span data-stu-id="7c48b-143">That means that the subset of attributes to be returned is based on the query itself.</span></span> <span data-ttu-id="7c48b-144">如果你将新列添加到查询或联接时，该数据是动态添加到返回视图模型。</span><span class="sxs-lookup"><span data-stu-id="7c48b-144">If you add a new column to the query or join, that data is dynamically added to the returned ViewModel.</span></span> <span data-ttu-id="7c48b-145">此方法可以降低需要在更新部署到基础数据模型，更加灵活和容错的将来的更改进行此设计方法响应修改查询。</span><span class="sxs-lookup"><span data-stu-id="7c48b-145">This approach reduces the need to modify queries in response to updates to the underlying data model, making this design approach more flexible and tolerant of future changes.</span></span>

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
    public async Task<IEnumerable<dynamic>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            return await connection.QueryAsync<dynamic>(
@"SELECT o.[Id] as ordernumber,
o.[OrderDate] as [date],os.[Name] as [status],
SUM(oi.units*oi.unitprice) as total
FROM [ordering].[Orders] o
LEFT JOIN[ordering].[orderitems] oi ON o.Id = oi.orderid
LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
GROUP BY o.[Id], o.[OrderDate], os.[Name]");
        }
  }
}
```

<span data-ttu-id="7c48b-146">重要的一点是，通过使用动态类型，则返回的集合的数据将被动态组装为视图模型。</span><span class="sxs-lookup"><span data-stu-id="7c48b-146">The important point is that by using a dynamic type, the returned collection of data will be dynamically assembled as the ViewModel.</span></span>

<span data-ttu-id="7c48b-147">对于大多数查询，你不需要预定义 DTO 或 ViewModel 类，这使对其进行编码简单和高效。</span><span class="sxs-lookup"><span data-stu-id="7c48b-147">For most queries, you do not need to predefine a DTO or ViewModel class, which makes coding them straightforward and productive.</span></span> <span data-ttu-id="7c48b-148">但是，如果你想要作为协定的更受限制定义 Viewmodel 可以预定义 Viewmodel （如预定义 Dto)。</span><span class="sxs-lookup"><span data-stu-id="7c48b-148">However, you can predefine ViewModels (like predefined DTOs) if you want to have ViewModels with a more restricted definition as contracts.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="7c48b-149">其他资源</span><span class="sxs-lookup"><span data-stu-id="7c48b-149">Additional resources</span></span>

-   <span data-ttu-id="7c48b-150">**Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span><span class="sxs-lookup"><span data-stu-id="7c48b-150">**Dapper**
[*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span></span>

-   <span data-ttu-id="7c48b-151">**Julie Lerman。数据点-Dapper、 实体框架和混合应用程序 （MSDN Mag.文章）**</span><span class="sxs-lookup"><span data-stu-id="7c48b-151">**Julie Lerman. Data Points - Dapper, Entity Framework and Hybrid Apps (MSDN Mag. article)**</span></span>

    <span data-ttu-id="7c48b-152">*https://msdn.microsoft.com/en-us/magazine/mt703432.aspx*</span><span class="sxs-lookup"><span data-stu-id="7c48b-152">*https://msdn.microsoft.com/en-us/magazine/mt703432.aspx*</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="7c48b-153">[以前](eshoponcontainers-cqrs-ddd-microservice.md) [下一步] (ddd-面向-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="7c48b-153">[Previous] (eshoponcontainers-cqrs-ddd-microservice.md) [Next] (ddd-oriented-microservice.md)</span></span>
