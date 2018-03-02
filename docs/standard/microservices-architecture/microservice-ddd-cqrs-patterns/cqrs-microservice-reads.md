---
title: "在 CQRS 微服务中实现读取/查询"
description: "适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 在 CQRS 微服务中实现读取/查询"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/02/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ca9bcefb317d2b3c7c225b773918ca4a2484cb8f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a><span data-ttu-id="6d303-104">在 CQRS 微服务中实现读取/查询</span><span class="sxs-lookup"><span data-stu-id="6d303-104">Implementing reads/queries in a CQRS microservice</span></span>

<span data-ttu-id="6d303-105">对于读取/查询，来自 eShopOnContainers 引用应用程序的订购微服务独立于 DDD 模型和事务区域实现查询。</span><span class="sxs-lookup"><span data-stu-id="6d303-105">For reads/queries, the ordering microservice from the eShopOnContainers reference application implements the queries independently from the DDD model and transactional area.</span></span> <span data-ttu-id="6d303-106">这主要是因为查询的需要和事务的需要有很大不同。</span><span class="sxs-lookup"><span data-stu-id="6d303-106">This was done primarily because the demands for queries and for transactions are drastically different.</span></span> <span data-ttu-id="6d303-107">写入的执行事务必须符合域逻辑。</span><span class="sxs-lookup"><span data-stu-id="6d303-107">Writes execute transactions that must be compliant with the domain logic.</span></span> <span data-ttu-id="6d303-108">另一方面，查询是幂等的，可以与域规则分离。</span><span class="sxs-lookup"><span data-stu-id="6d303-108">Queries, on the other hand, are idempotent and can be segregated from the domain rules.</span></span>

<span data-ttu-id="6d303-109">如图 9-3 所示，这种方法很简单。</span><span class="sxs-lookup"><span data-stu-id="6d303-109">The approach is simple, as shown in Figure 9-3.</span></span> <span data-ttu-id="6d303-110">根据用户界面应用程序的要求，Web API 控制器使用任意基础结构（如 Dapper 等微观对象关系映射程序 (ORM)）并返回动态 ViewModel 就可实现 API 接口。</span><span class="sxs-lookup"><span data-stu-id="6d303-110">The API interface is implemented by the Web API controllers using any infrastructure, such as a micro Object Relational Mapper (ORM) like Dapper, and returning dynamic ViewModels depending on the needs of the UI applications.</span></span>

![](./media/image3.png)

<span data-ttu-id="6d303-111">**图 9-3**。</span><span class="sxs-lookup"><span data-stu-id="6d303-111">**Figure 9-3**.</span></span> <span data-ttu-id="6d303-112">CQRS 微服务中用于查询的最简单方法</span><span class="sxs-lookup"><span data-stu-id="6d303-112">The simplest approach for queries in a CQRS microservice</span></span>

<span data-ttu-id="6d303-113">这是用于查询的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="6d303-113">This is the simplest possible approach for queries.</span></span> <span data-ttu-id="6d303-114">查询定义查询数据库并返回为每个查询动态构建的动态 ViewModel。</span><span class="sxs-lookup"><span data-stu-id="6d303-114">The query definitions query the database and return a dynamic ViewModel built on the fly for each query.</span></span> <span data-ttu-id="6d303-115">因为查询是幂等的，所以无论查询运行多少次，数据都不会更改。</span><span class="sxs-lookup"><span data-stu-id="6d303-115">Since the queries are idempotent, they won't change the data no matter how many times you run a query.</span></span> <span data-ttu-id="6d303-116">因此，不会受到事务端所用 DDD 模式的限制（如聚合和其他模式），这也是查询与事务区域分离的原因。</span><span class="sxs-lookup"><span data-stu-id="6d303-116">Therefore, you don't need to be restricted by any DDD pattern used in the transactional side, like aggregates and other patterns, and that is why queries are separated from the transactional area.</span></span> <span data-ttu-id="6d303-117">只需查询数据库以获取 UI 需要的数据，并返回动态 ViewModel，除在 SQL 语句中外，动态 ViewModel 不需要在任何地方静态定义（ViewModel 没有类）。</span><span class="sxs-lookup"><span data-stu-id="6d303-117">You simply query the database for the data that the UI needs and return a dynamic ViewModel that does not need to be statically defined anywhere (no classes for the ViewModels) except in the SQL statements themselves.</span></span>

<span data-ttu-id="6d303-118">因为这种方法很简单，因此查询端所需的代码（例如使用 [Dapper](https://github.com/StackExchange/Dapper) 等微型 ORM 的代码）可[在同一 Web API 项目](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs)中实现。</span><span class="sxs-lookup"><span data-stu-id="6d303-118">Since this is a simple approach, the code required for the queries side (such as code using a micro ORM like [Dapper](https://github.com/StackExchange/Dapper)) can be implemented [within the same Web API project](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span></span> <span data-ttu-id="6d303-119">如图 9-4 所示。</span><span class="sxs-lookup"><span data-stu-id="6d303-119">Figure 9-4 shows this.</span></span> <span data-ttu-id="6d303-120">查询在 eShopOnContainers 解决方案的“Ordering.API”微服务项目中定义。</span><span class="sxs-lookup"><span data-stu-id="6d303-120">The queries are defined in the **Ordering.API** microservice project within the eShopOnContainers solution.</span></span>

![](./media/image4.png)

<span data-ttu-id="6d303-121">**图 9-4**。</span><span class="sxs-lookup"><span data-stu-id="6d303-121">**Figure 9-4**.</span></span> <span data-ttu-id="6d303-122">eShopOnContainers 的订购微服务中的查询</span><span class="sxs-lookup"><span data-stu-id="6d303-122">Queries in the Ordering microservice in eShopOnContainers</span></span>

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a><span data-ttu-id="6d303-123">使用专为客户端应用构建的 Viewmodel 不受域模型的约束</span><span class="sxs-lookup"><span data-stu-id="6d303-123">Using ViewModels specifically made for client apps, independent from domain model constraints</span></span>

<span data-ttu-id="6d303-124">由于执行查询是为获取客户端应用程序所需的数据，因此返回类型应根据查询所返回的数据专为客户端构建。</span><span class="sxs-lookup"><span data-stu-id="6d303-124">Since the queries are performed to obtain the data needed by the client applications, the returned type can be specifically made for the clients, based on the data returned by the queries.</span></span> <span data-ttu-id="6d303-125">这些模型或数据传输对象 (DTO) 称为 ViewModel。</span><span class="sxs-lookup"><span data-stu-id="6d303-125">These models, or Data Transfer Objects (DTOs), are called ViewModels.</span></span>

<span data-ttu-id="6d303-126">返回数据 (ViewModel) 可以是来自数据库中多个实体或表的联接数据结果，或者是事务区域域模型中定义的多个聚合中的联接数据结果。</span><span class="sxs-lookup"><span data-stu-id="6d303-126">The returned data (ViewModel) can be the result of joining data from multiple entities or tables in the database, or even across multiple aggregates defined in the domain model for the transactional area.</span></span> <span data-ttu-id="6d303-127">在这种情况下，因为正在创建独立于域模型的查询，所以完全忽略了聚合边界和约束，因此可随意查询可能需要的任何表和列。</span><span class="sxs-lookup"><span data-stu-id="6d303-127">In this case, because you are creating queries independent of the domain model, the aggregates boundaries and constraints are completely ignored and you're free to query any table and column you might need.</span></span> <span data-ttu-id="6d303-128">这种方法极大地提高了开发人员创建或更新查询的效率和灵活性。</span><span class="sxs-lookup"><span data-stu-id="6d303-128">This approach provides great flexibility and productivity for the developers creating or updating the queries.</span></span>

<span data-ttu-id="6d303-129">Viewmodel 可以是定义在类中的静态类型。</span><span class="sxs-lookup"><span data-stu-id="6d303-129">The ViewModels can be static types defined in classes.</span></span> <span data-ttu-id="6d303-130">或者可以根据执行的查询对其进行动态创建（如订单微服务中所实现的），开发人员可灵活处理。</span><span class="sxs-lookup"><span data-stu-id="6d303-130">Or they can be created dynamically based on the queries performed (as is implemented in the ordering microservice), which is very agile for developers.</span></span>

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a><span data-ttu-id="6d303-131">使用 Dapper 作为微型 ORM 以执行查询</span><span class="sxs-lookup"><span data-stu-id="6d303-131">Using Dapper as a micro ORM to perform queries</span></span>

<span data-ttu-id="6d303-132">可使用任何微型 ORM、Entity Framework Core 甚至普通的 ADO.NET 进行查询。</span><span class="sxs-lookup"><span data-stu-id="6d303-132">You can use any micro ORM, Entity Framework Core, or even plain ADO.NET for querying.</span></span> <span data-ttu-id="6d303-133">在示例应用程序中，选择 Dapper 用于 eShopOnContainers 中的订单微服务，这是常用微型 ORM 的一个良好示例。</span><span class="sxs-lookup"><span data-stu-id="6d303-133">In the sample application, Dapper was selected for the ordering microservice in eShopOnContainers as a good example of a popular micro ORM.</span></span> <span data-ttu-id="6d303-134">由于它是一个非常轻量化的框架，因此能够以极佳的性能运行普通 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="6d303-134">It can run plain SQL queries with great performance, because it's a very light framework.</span></span> <span data-ttu-id="6d303-135">使用 Dapper，可写入一个可访问和联接多个表的 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="6d303-135">Using Dapper, you can write a SQL query that can access and join multiple tables.</span></span>

<span data-ttu-id="6d303-136">Dapper 是开源项目（最初由 Sam Saffron 创建），也是在 [Stack Overflow](https://stackoverflow.com/) 中使用的构建基块的一部分。</span><span class="sxs-lookup"><span data-stu-id="6d303-136">Dapper is an open-source project (original created by Sam Saffron), and is part of the building blocks used in [Stack Overflow](https://stackoverflow.com/).</span></span> <span data-ttu-id="6d303-137">要使用 Dapper，只需通过 [Dapper NuGet 包](https://www.nuget.org/packages/Dapper)进行安装，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="6d303-137">To use Dapper, you just need to install it through the [Dapper NuGet package](https://www.nuget.org/packages/Dapper), as shown in the following figure:</span></span>

![](./media/image4.1.png)

<span data-ttu-id="6d303-138">还需要添加一个 using 语句，使代码具有 Dapper 扩展方法的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6d303-138">You also need to add a using statement so your code has access to the Dapper extension methods.</span></span>

<span data-ttu-id="6d303-139">在代码中使用 Dapper 时，可直接使用 <xref:System.Data.SqlClient> 命名空间中提供的 <xref:System.Data.SqlClient.SqlConnection> 类。</span><span class="sxs-lookup"><span data-stu-id="6d303-139">When you use Dapper in your code, you directly use the <xref:System.Data.SqlClient.SqlConnection> class available in the <xref:System.Data.SqlClient> namespace.</span></span> <span data-ttu-id="6d303-140">通过 QueryAsync 方法和扩展 <xref:System.Data.SqlClient.SqlConnection> 类的其他扩展方法，可以简单直观地运行查询。</span><span class="sxs-lookup"><span data-stu-id="6d303-140">Through the QueryAsync method and other extension methods that extend the <xref:System.Data.SqlClient.SqlConnection> class, you can simply run queries in a straightforward and performant way.</span></span>

## <a name="dynamic-versus-static-viewmodels"></a><span data-ttu-id="6d303-141">动态与静态 Viewmodel</span><span class="sxs-lookup"><span data-stu-id="6d303-141">Dynamic versus static ViewModels</span></span>

<span data-ttu-id="6d303-142">将 ViewModel 从服务器端返回到客户端应用时，可将这些 ViewModel 看作 DTO，这些 DOT 与实体模型的内部实体域不同，因为 ViewModel 以客户端应用所需的方式保存数据。</span><span class="sxs-lookup"><span data-stu-id="6d303-142">When returning ViewModels from the server-side to client apps, you can think about those ViewModels as DTOs that can be different to the internal domain entities of your entity model because the ViewModels hold the data the way the client app needs.</span></span> <span data-ttu-id="6d303-143">因此，在许多情况下，可以聚合来自多个域实体的数据，并根据客户端应用需要数据的方式精确地组合这些 ViewModel。</span><span class="sxs-lookup"><span data-stu-id="6d303-143">Therefore, in many cases, you can aggregate data coming from multiple domain entities and compose the ViewModels precisely according to how the client app needs that data.</span></span>

<span data-ttu-id="6d303-144">这些 ViewModel 或 DTO 可如稍后的代码片段中显示的 [OrderSummary](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Queries/OrderViewModel.cs) 类一样（作为数据持有者类）显式定义，或者，可以基于查询所返回的属性将动态 ViewModel 或动态 DTO 作为 `dynamic` 类型返回。</span><span class="sxs-lookup"><span data-stu-id="6d303-144">Those ViewModels or DTOs can be defined explicitly (as data holder classes) like the [OrderSummary](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Queries/OrderViewModel.cs) class shown in a later code snippet, or you could just return dynamic ViewModels or dynamic DTOs simply based on the attributes returned by your queries, as a `dynamic` type.</span></span>

### <a name="viewmodel-as-dynamic-type"></a><span data-ttu-id="6d303-145">ViewModel 作为动态类型</span><span class="sxs-lookup"><span data-stu-id="6d303-145">ViewModel as dynamic type</span></span>

<span data-ttu-id="6d303-146">如以下代码所示，通过返回一个内部基于查询所返回属性的动态类型，查询可直接返回 ViewModel。</span><span class="sxs-lookup"><span data-stu-id="6d303-146">As shown in the following code, a ViewModel can be directly returned by the queries by returning a dynamic type that internally is based on the attributes returned by a query.</span></span> <span data-ttu-id="6d303-147">这意味着要返回的属性的子集是基于查询本身的。</span><span class="sxs-lookup"><span data-stu-id="6d303-147">That means that the subset of attributes to be returned is based on the query itself.</span></span> <span data-ttu-id="6d303-148">因此，如果将新列添加到查询或联接，则该数据将动态添加到返回的 ViewModel 中。</span><span class="sxs-lookup"><span data-stu-id="6d303-148">Therefore, if you add a new column to the query or join, that data is dynamically added to the returned ViewModel.</span></span>

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

<span data-ttu-id="6d303-149">重点在于，通过使用动态类型，返回的数据集合将动态组装为 ViewModel。</span><span class="sxs-lookup"><span data-stu-id="6d303-149">The important point is that by using a dynamic type, the returned collection of data is dynamically assembled as the ViewModel.</span></span>

<span data-ttu-id="6d303-150">优点：无论何时更新查询的 SQL 语句，此方法都可降低修改静态 ViewModel 类的需要，这使得此设计方法在编码时非常灵活，并在未来更改时能快速改善。</span><span class="sxs-lookup"><span data-stu-id="6d303-150">*Pros:* This approach reduces the need to modify static ViewModel classes whenever you update the SQL sentence of a query, making this design approach pretty agile when coding, straightforward, and quick to evolve in regard to future changes.</span></span>

<span data-ttu-id="6d303-151">缺点：长远来看，动态类型可能会对清晰度造成不利影响，影响服务与客户端应用的兼容性。</span><span class="sxs-lookup"><span data-stu-id="6d303-151">*Cons:* In the long term, dynamic types can impact negatively the clarity and impact the compatibility of a service with client apps.</span></span> <span data-ttu-id="6d303-152">此外，如果使用动态类型，中间件软件（如 Swagger）无法为返回类型提供相同级别的文档。</span><span class="sxs-lookup"><span data-stu-id="6d303-152">In addition, middleware software like Swagger cannot provide the same level of documentation on returned types if using dynamic types.</span></span>

### <a name="viewmodel-as-predefined-dto-classes"></a><span data-ttu-id="6d303-153">ViewModel 作为预定义的 DTO 类</span><span class="sxs-lookup"><span data-stu-id="6d303-153">ViewModel as predefined DTO classes</span></span>

<span data-ttu-id="6d303-154">优点：具有静态预定义的 ViewModel 类（如基于显式 DTO 类的“协定”）毫无疑问有利于公共 API 和长期微服务，即使它们只用于同一应用程序。</span><span class="sxs-lookup"><span data-stu-id="6d303-154">*Pros:* Having static predefined ViewModel classes, like "contracts" based on explicit DTO classes, is definitely better for public APIs but also for long term microservices, even if they are only used by the same application.</span></span>

<span data-ttu-id="6d303-155">如果想要为 Swagger 指定响应类型，需要使用显式 DTO 类作为返回类型。</span><span class="sxs-lookup"><span data-stu-id="6d303-155">If you want to specify response types for swagger, you need to use explicit DTO classes as the return type.</span></span> <span data-ttu-id="6d303-156">因此，预定义的 DTO 类允许从 Swagger 提供更丰富的信息。</span><span class="sxs-lookup"><span data-stu-id="6d303-156">Therefore, predefined DTO classes allow you to offer richer information from Swagger.</span></span> <span data-ttu-id="6d303-157">它可在使用 API 时改善 API 文档和兼容性。</span><span class="sxs-lookup"><span data-stu-id="6d303-157">That improves the API documentation and compatibility when consuming an API.</span></span>

<span data-ttu-id="6d303-158">缺点：如前所述，更新代码时，更新 DTO 类需要花费更多步骤。</span><span class="sxs-lookup"><span data-stu-id="6d303-158">*Cons:* As mentioned earlier, when updating the code, it takes some more steps to update the DTO classes.</span></span>

<span data-ttu-id="6d303-159">经验之谈：在 eShopOnContainers 的订单微服务内实现的查询中，开始使用动态 ViewModel 开发，是因为它在早期开发阶段的直观性和灵活性。</span><span class="sxs-lookup"><span data-stu-id="6d303-159">*Tip based on our experience:* In the queries implemented at the Ordering microservice in eShopOnContainers, we started developing by using dynamic ViewModels as it was very straightforward and agile on the early development stages.</span></span> <span data-ttu-id="6d303-160">但是，一旦开发稳定后，我们将选择重构 API，并将静态或预定义的 DTO 用于 ViewModel，因为这样能使微服务的使用者更加清晰地了解用作“协定”的显式 DTO 类型。</span><span class="sxs-lookup"><span data-stu-id="6d303-160">But, once the development was stabilized, we chose to refactor the APIs and use static or pre-defined DTOs for the ViewModels, because it is clearer for the microservice’s consumers to know explicit DTO types, used as "contracts".</span></span>

<span data-ttu-id="6d303-161">在以下示例中，可以看到查询如何使用显式 ViewModel DTO 类返回数据：OrderSummary 类。</span><span class="sxs-lookup"><span data-stu-id="6d303-161">In the following example, you can see how the query is returning data by using an explicit ViewModel DTO class: the OrderSummary class.</span></span>

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
  public async Task<IEnumerable<OrderSummary>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            var result = await connection.QueryAsync<dynamic>(
                  @"SELECT o.[Id] as ordernumber, 
                  o.[OrderDate] as [date],os.[Name] as [status], 
                  SUM(oi.units*oi.unitprice) as total
                  FROM [ordering].[Orders] o
                  LEFT JOIN[ordering].[orderitems] oi ON  o.Id = oi.orderid 
                  LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
                  GROUP BY o.[Id], o.[OrderDate], os.[Name]
                  ORDER BY o.[Id]");
        }
    } 
}
```

#### <a name="describing-response-types-of-web-apis"></a><span data-ttu-id="6d303-162">介绍 Web API 的响应类型</span><span class="sxs-lookup"><span data-stu-id="6d303-162">Describing response types of Web APIs</span></span>

<span data-ttu-id="6d303-163">使用 Web API 和微服务的开发人员最关心的问题是返回的内容 - 具体的响应类型和错误代码（如果不标准）。</span><span class="sxs-lookup"><span data-stu-id="6d303-163">Developers consuming web APIs and microservices are most concerned with what is returned — specifically response types and error codes (if not standard).</span></span> <span data-ttu-id="6d303-164">这些问题在 XML 注释和数据批注中进行处理。</span><span class="sxs-lookup"><span data-stu-id="6d303-164">These are handled in the XML comments and data annotations.</span></span>

<span data-ttu-id="6d303-165">如果没有关于 Swagger UI 的合适文档，使用者无法了解返回的类型或可返回的 HTTP 代码。</span><span class="sxs-lookup"><span data-stu-id="6d303-165">Without proper documentation in the Swagger UI, the consumer lacks knowledge of what types are being returned or what HTTP codes can be returned.</span></span> <span data-ttu-id="6d303-166">该问题已通过添加 <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType> 解决，因此 Swagger 可以生成 API 返回模型和值的更加详细的信息，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="6d303-166">That problem is fixed by adding the <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType>, so Swagger can generate richer information about the API return model and values, as shown in the following code:</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class OrdersController : Controller
    {
       //Additional code...
       [Route("")]
       [HttpGet]
       [ProducesResponseType(typeof(IEnumerable<OrderSummary>),
                             (int)HttpStatusCode.OK)]
       public async Task<IActionResult> GetOrders()
       {
           var orderTask = _orderQueries.GetOrdersAsync();
           var orders = await orderTask;
           return Ok(orders);
        }
    }
}
```

<span data-ttu-id="6d303-167">但是，`ProducesResponseType` 属性无法使用动态类型，而需要使用显式类型，如 `OrderSummary` ViewModel DTO，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="6d303-167">However, the `ProducesResponseType` attribute cannot use dynamic as a type but requires to use explicit types, like the `OrderSummary` ViewModel DTO, shown in the following example:</span></span>

```csharp
public class OrderSummary
{
    public int ordernumber { get; set; }
    public DateTime date { get; set; }
    public string status { get; set; }
    public double total { get; set; }
}
```

<span data-ttu-id="6d303-168">这也是长期来看，显式返回类型比动态类型更好的另一原因。</span><span class="sxs-lookup"><span data-stu-id="6d303-168">This is another reason why explicit returned types are better than dynamic types, in the long term.</span></span>
<span data-ttu-id="6d303-169">使用 `ProducesResponseType` 属性时，还可以指定关于可能的 HTTP 错误/代码（如 200、400 等）的预期结果。</span><span class="sxs-lookup"><span data-stu-id="6d303-169">When using the `ProducesResponseType` attribute, you can also specify what is the expected outcome in regards possible HTTP errors/codes, like 200,400, etc.</span></span>

<span data-ttu-id="6d303-170">下图中，可以看到 Swagger UI 如何显示 ResponseType 信息。</span><span class="sxs-lookup"><span data-stu-id="6d303-170">In the following image, you can see how Swagger UI shows the ResponseType information.</span></span>

![](./media/image5.png)

<span data-ttu-id="6d303-171">**图 9-5**。</span><span class="sxs-lookup"><span data-stu-id="6d303-171">**Figure 9-5**.</span></span> <span data-ttu-id="6d303-172">显示来自 Web API 的响应类型和可能的 HTTP 状态代码的 Swagger UI</span><span class="sxs-lookup"><span data-stu-id="6d303-172">Swagger UI showing response types and possible HTTP status codes from a Web API</span></span>

<span data-ttu-id="6d303-173">可在上图中看到基于 ViewModel 类型的一些示例值，以及可能返回的 HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="6d303-173">You can see in the image above some example values based on the ViewModel types plus the possible HTTP status codes that can be returned.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6d303-174">其他资源</span><span class="sxs-lookup"><span data-stu-id="6d303-174">Additional resources</span></span>

-   <span data-ttu-id="6d303-175">**Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span><span class="sxs-lookup"><span data-stu-id="6d303-175">**Dapper**
[*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span></span>

-   <span data-ttu-id="6d303-176">**Julie Lerman.数据点 - Dapper、Entity Framework 和混合应用（MSDN Mag. 文章）**</span><span class="sxs-lookup"><span data-stu-id="6d303-176">**Julie Lerman. Data Points - Dapper, Entity Framework and Hybrid Apps (MSDN Mag. article)**</span></span>

    <span data-ttu-id="6d303-177">https://msdn.microsoft.com/magazine/mt703432.aspx</span><span class="sxs-lookup"><span data-stu-id="6d303-177">*https://msdn.microsoft.com/magazine/mt703432.aspx*</span></span>

-   <span data-ttu-id="6d303-178">**使用 Swagger 的 ASP.NET Core Web API 帮助页**</span><span class="sxs-lookup"><span data-stu-id="6d303-178">**ASP.NET Core Web API Help Pages using Swagger**</span></span>

    <span data-ttu-id="6d303-179">https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio</span><span class="sxs-lookup"><span data-stu-id="6d303-179">*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio*</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="6d303-180">[上一篇] (eshoponcontainers-cqrs-ddd-microservice.md) [下一篇] (ddd-oriented-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="6d303-180">[Previous] (eshoponcontainers-cqrs-ddd-microservice.md) [Next] (ddd-oriented-microservice.md)</span></span>
