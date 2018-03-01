---
title: "设计基础结构持久性层"
description: "适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 设计基础结构持久性层"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 76db5388c75d4eb3b5cc23c1e57cc391a15f2934
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="designing-the-infrastructure-persistence-layer"></a><span data-ttu-id="f392e-104">设计基础结构持久性层</span><span class="sxs-lookup"><span data-stu-id="f392e-104">Designing the infrastructure persistence layer</span></span>

<span data-ttu-id="f392e-105">数据持久性组件提供对微服务边界（即微服务的数据库）内托管的数据的访问。</span><span class="sxs-lookup"><span data-stu-id="f392e-105">Data persistence components provide access to the data hosted within the boundaries of a microservice (that is, a microservice’s database).</span></span> <span data-ttu-id="f392e-106">它们包含组件（例如存储库和[工作单元](http://martinfowler.com/eaaCatalog/unitOfWork.html)类）的实际实现，例如自定义 EF DBContexts。</span><span class="sxs-lookup"><span data-stu-id="f392e-106">They contain the actual implementation of components such as repositories and [Unit of Work](http://martinfowler.com/eaaCatalog/unitOfWork.html) classes, like custom EF DBContexts.</span></span>

## <a name="the-repository-pattern"></a><span data-ttu-id="f392e-107">存储库模式</span><span class="sxs-lookup"><span data-stu-id="f392e-107">The Repository pattern</span></span>

<span data-ttu-id="f392e-108">存储库是封装访问数据源所需逻辑的类或组件。</span><span class="sxs-lookup"><span data-stu-id="f392e-108">Repositories are classes or components that encapsulate the logic required to access data sources.</span></span> <span data-ttu-id="f392e-109">它们集中提供常见的数据访问功能，从而提供更好的可维护性，并将用于访问数据库的基础结构或技术与域模型层分离。</span><span class="sxs-lookup"><span data-stu-id="f392e-109">They centralize common data access functionality, providing better maintainability and decoupling the infrastructure or technology used to access databases from the domain model layer.</span></span> <span data-ttu-id="f392e-110">如果使用像 Entity Framework 这样的 ORM，则可通过 LINQ 和强类型化来简化必须实现的代码。</span><span class="sxs-lookup"><span data-stu-id="f392e-110">If you use an ORM like Entity Framework, the code that must be implemented is simplified, thanks to LINQ and strong typing.</span></span> <span data-ttu-id="f392e-111">这样你就可以专注于数据持久性逻辑而不是数据访问管道。</span><span class="sxs-lookup"><span data-stu-id="f392e-111">This lets you focus on the data persistence logic rather than on data access plumbing.</span></span>

<span data-ttu-id="f392e-112">存储库模式是一种使用数据源的详细记录方式。</span><span class="sxs-lookup"><span data-stu-id="f392e-112">The Repository pattern is a well-documented way of working with a data source.</span></span> <span data-ttu-id="f392e-113">在 [Patterns of Enterprise Application Architecture](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/)（企业应用程序体系结构模式）一书中，Martin Fowler 是这样描述存储库的：</span><span class="sxs-lookup"><span data-stu-id="f392e-113">In the book [Patterns of Enterprise Application Architecture](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/), Martin Fowler describes a repository as follows:</span></span>

<span data-ttu-id="f392e-114">存储库执行域模型层与数据映射之间的中介者的任务，以类似于内存中一组域对象的方式工作。</span><span class="sxs-lookup"><span data-stu-id="f392e-114">A repository performs the tasks of an intermediary between the domain model layers and data mapping, acting in a similar way to a set of domain objects in memory.</span></span> <span data-ttu-id="f392e-115">客户端对象以声明方式生成查询，并将它们发送到存储库以获取答案。</span><span class="sxs-lookup"><span data-stu-id="f392e-115">Client objects declaratively build queries and send them to the repositories for answers.</span></span> <span data-ttu-id="f392e-116">从概念上讲，存储库封装了存储在数据库中的一组对象以及可对其执行的操作，从而提供一种更接近持久性层的方式。</span><span class="sxs-lookup"><span data-stu-id="f392e-116">Conceptually, a repository encapsulates a set of objects stored in the database and operations that can be performed on them, providing a way that is closer to the persistence layer.</span></span> <span data-ttu-id="f392e-117">存储库还明确支持在一个方向上分离工作域与数据分配或映射之间的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="f392e-117">Repositories, also, support the purpose of separating, clearly and in one direction, the dependency between the work domain and the data allocation or mapping.</span></span>

### <a name="define-one-repository-per-aggregate"></a><span data-ttu-id="f392e-118">为每个聚合定义一个存储库</span><span class="sxs-lookup"><span data-stu-id="f392e-118">Define one repository per aggregate</span></span>

<span data-ttu-id="f392e-119">对于每个聚合或聚合根，应创建一个存储库类。</span><span class="sxs-lookup"><span data-stu-id="f392e-119">For each aggregate or aggregate root, you should create one repository class.</span></span> <span data-ttu-id="f392e-120">在基于域驱动设计模式的微服务中，可用来更新数据库的唯一渠道应该是存储库。</span><span class="sxs-lookup"><span data-stu-id="f392e-120">In a microservice based on domain-driven design patterns, the only channel you should use to update the database should be the repositories.</span></span> <span data-ttu-id="f392e-121">这是因为它们与聚合根具有一对一的关系，聚合根控制着聚合的不变量和事务一致性。</span><span class="sxs-lookup"><span data-stu-id="f392e-121">This is because they have a one-to-one relationship with the aggregate root, which controls the aggregate’s invariants and transactional consistency.</span></span> <span data-ttu-id="f392e-122">可以通过其他渠道查询数据库（就像使用 CQRS 方法时一样），因为查询不会更改数据库的状态。</span><span class="sxs-lookup"><span data-stu-id="f392e-122">It is okay to query the database through other channels (as you can do following a CQRS approach), because queries do not change the state of the database.</span></span> <span data-ttu-id="f392e-123">但是，事务区域（更新）必须始终由存储库和聚合根控制。</span><span class="sxs-lookup"><span data-stu-id="f392e-123">However, the transactional area—the updates—must always be controlled by the repositories and the aggregate roots.</span></span>

<span data-ttu-id="f392e-124">从本质上讲，存储库允许以域实体的形式填充内存中来自数据库的数据。</span><span class="sxs-lookup"><span data-stu-id="f392e-124">Basically, a repository allows you to populate data in memory that comes from the database in the form of the domain entities.</span></span> <span data-ttu-id="f392e-125">一旦实体在内存中，就可以对它们进行更改，然后通过事务存回数据库中。</span><span class="sxs-lookup"><span data-stu-id="f392e-125">Once the entities are in memory, they can be changed and then persisted back to the database through transactions.</span></span>

<span data-ttu-id="f392e-126">如前所述，如果使用 CQS/CQRS 体系结构模式，则将由简单的 SQL 语句使用 Dapper 在域模型外并行执行初始查询。</span><span class="sxs-lookup"><span data-stu-id="f392e-126">As noted earlier, if you are using the CQS/CQRS architectural pattern, the initial queries will be performed by side queries out of the domain model, performed by simple SQL statements using Dapper.</span></span> <span data-ttu-id="f392e-127">这种方法比存储库更加灵活，因为你可以查询和联接所需的任何表，并且这些查询不受聚合中的规则的限制。</span><span class="sxs-lookup"><span data-stu-id="f392e-127">This approach is much more flexible than repositories because you can query and join any tables you need, and these queries are not restricted by rules from the aggregates.</span></span> <span data-ttu-id="f392e-128">该数据将发送到表示层或客户端应用。</span><span class="sxs-lookup"><span data-stu-id="f392e-128">That data will go to the presentation layer or client app.</span></span>

<span data-ttu-id="f392e-129">如果用户进行更改，要更新的数据将从客户端应用或表示层发送到应用层（例如 Web API 服务）。</span><span class="sxs-lookup"><span data-stu-id="f392e-129">If the user makes changes, the data to be updated will come from the client app or presentation layer to the application layer (such as a Web API service).</span></span> <span data-ttu-id="f392e-130">当在命令处理程序中收到命令（包含数据）时，可以使用存储库获取要从数据库更新的数据。</span><span class="sxs-lookup"><span data-stu-id="f392e-130">When you receive a command (with data) in a command handler, you use repositories to get the data you want to update from the database.</span></span> <span data-ttu-id="f392e-131">可使用通过命令传递的信息在内存中更新数据，然后通过事务在数据库中添加或更新数据（域实体）。</span><span class="sxs-lookup"><span data-stu-id="f392e-131">You update it in memory with the information passed with the commands, and you then add or update the data (domain entities) in the database through a transaction.</span></span>

<span data-ttu-id="f392e-132">请注意，只能为每个聚合根定义一个存储库，如图 9-17 所示。</span><span class="sxs-lookup"><span data-stu-id="f392e-132">Remember that only one repository should be defined for each aggregate root, as shown in Figure 9-17.</span></span> <span data-ttu-id="f392e-133">若要实现聚合根的目标，即维持聚合中所有对象之间的事务一致性，就决不能为数据库中的每个表创建一个存储库。</span><span class="sxs-lookup"><span data-stu-id="f392e-133">To achieve the goal of the aggregate root to maintain transactional consistency between all the objects within the aggregate, you should never create a repository for each table in the database.</span></span>

![](./media/image18.png)

<span data-ttu-id="f392e-134">**图 9-17**.</span><span class="sxs-lookup"><span data-stu-id="f392e-134">**Figure 9-17**.</span></span> <span data-ttu-id="f392e-135">存储库、聚合和数据库表之间的关系</span><span class="sxs-lookup"><span data-stu-id="f392e-135">The relationship between repositories, aggregates, and database tables</span></span>

### <a name="enforcing-one-aggregate-root-per-repository"></a><span data-ttu-id="f392e-136">强制每个存储库一个聚合根</span><span class="sxs-lookup"><span data-stu-id="f392e-136">Enforcing one aggregate root per repository</span></span>

<span data-ttu-id="f392e-137">以这样一种方式实现存储库设计可能很有价值，即实施仅聚合根具有存储库的规则。</span><span class="sxs-lookup"><span data-stu-id="f392e-137">It can be valuable to implement your repository design in such a way that it enforces the rule that only aggregate roots should have repositories.</span></span> <span data-ttu-id="f392e-138">你可以创建一个泛型或基本存储库类型，以限制其使用的实体类型，确保这些实体具有 IAggregateRoot 标记接口。</span><span class="sxs-lookup"><span data-stu-id="f392e-138">You can create a generic or base repository type that constrains the type of entities it works with to ensure they have the IAggregateRoot marker interface.</span></span>

<span data-ttu-id="f392e-139">这样，在基础结构层实现的每个存储库类都会实现自己的协定或接口，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="f392e-139">Thus, each repository class implemented at the infrastructure layer implements its own contract or interface, as shown in the following code:</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class OrderRepository : IOrderRepository
    {
```

<span data-ttu-id="f392e-140">每个特定的存储库接口都实现 IRepository 泛型接口：</span><span class="sxs-lookup"><span data-stu-id="f392e-140">Each specific repository interface implements the generic IRepository interface:</span></span>

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
    // ...
}
```

<span data-ttu-id="f392e-141">不过，若要让代码执行每个存储库都应与单个聚合关联的约定，一种更好的方式是实现泛型存储库类型，这样就可以明确看出你在使用存储库定位特定聚合。</span><span class="sxs-lookup"><span data-stu-id="f392e-141">However, a better way to have the code enforce the convention that each repository should be related to a single aggregate would be to implement a generic repository type so it is explicit that you are using a repository to target a specific aggregate.</span></span> <span data-ttu-id="f392e-142">这可以通过在 IRepository 基接口中实现该泛型来轻松完成，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="f392e-142">That can be easily done by implementing that generic in the IRepository base interface, as in the following code:</span></span>

```csharp
  public interface IRepository<T> where T : IAggregateRoot
```

### <a name="the-repository-pattern-makes-it-easier-to-test-your-application-logic"></a><span data-ttu-id="f392e-143">存储库模式使应用程序逻辑测试更轻松</span><span class="sxs-lookup"><span data-stu-id="f392e-143">The Repository pattern makes it easier to test your application logic</span></span>

<span data-ttu-id="f392e-144">存储库模式允许使用单元测试轻松测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="f392e-144">The Repository pattern allows you to easily test your application with unit tests.</span></span> <span data-ttu-id="f392e-145">请记住，单元测试只测试代码，不测试基础结构，所以存储库抽象使得它更容易实现这个目标。</span><span class="sxs-lookup"><span data-stu-id="f392e-145">Remember that unit tests only test your code, not infrastructure, so the repository abstractions make it easier to achieve that goal.</span></span>

<span data-ttu-id="f392e-146">如前面部分所述，建议在域模型层中定义并放置存储库接口，这样，应用层（例如，Web API 微服务）就不会直接依赖于已实现实际存储库类的基础结构层。</span><span class="sxs-lookup"><span data-stu-id="f392e-146">As noted in an earlier section, it is recommended that you define and place the repository interfaces in the domain model layer so the application layer (for instance, your Web API microservice) does not depend directly on the infrastructure layer where you have implemented the actual repository classes.</span></span> <span data-ttu-id="f392e-147">通过执行此操作并在 Web API 的控制器中使用依赖项注入，可以实现模拟存储库来返回假数据，而不是数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="f392e-147">By doing this and using Dependency Injection in the controllers of your Web API, you can implement mock repositories that return fake data instead of data from the database.</span></span> <span data-ttu-id="f392e-148">这种分离方法可用于创建和运行单元测试，这些单元测试可以只测试应用程序的逻辑，而无需连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="f392e-148">That decoupled approach allows you to create and run unit tests that can test just the logic of your application without requiring connectivity to the database.</span></span>

<span data-ttu-id="f392e-149">与数据库的连接可能会失败，更重要的是，针对数据库运行数百个测试的做法并不可取，原因有两个。</span><span class="sxs-lookup"><span data-stu-id="f392e-149">Connections to databases can fail and, more importantly, running hundreds of tests against a database is bad for two reasons.</span></span> <span data-ttu-id="f392e-150">首先，由于有大量测试，运行起来可能很费时。</span><span class="sxs-lookup"><span data-stu-id="f392e-150">First, it can take a lot of time because of the large number of tests.</span></span> <span data-ttu-id="f392e-151">其次，数据库记录可能会更改并影响测试结果，因此它们可能不一致。</span><span class="sxs-lookup"><span data-stu-id="f392e-151">Second, the database records might change and impact the results of your tests, so that they might not be consistent.</span></span> <span data-ttu-id="f392e-152">针对数据库进行的测试不是单元测试，而是集成测试。</span><span class="sxs-lookup"><span data-stu-id="f392e-152">Testing against the database is not a unit tests but an integration test.</span></span> <span data-ttu-id="f392e-153">你应该有许多快速运行的单元测试，较少针对数据库的集成测试。</span><span class="sxs-lookup"><span data-stu-id="f392e-153">You should have many unit tests running fast, but fewer integration tests against the databases.</span></span>

<span data-ttu-id="f392e-154">根据单元测试的关注点分离原则，你的逻辑应作用于内存中的域实体。</span><span class="sxs-lookup"><span data-stu-id="f392e-154">In terms of separation of concerns for unit tests, your logic operates on domain entities in memory.</span></span> <span data-ttu-id="f392e-155">它假定存储库类已经提供这些实体。</span><span class="sxs-lookup"><span data-stu-id="f392e-155">It assumes the repository class has delivered those.</span></span> <span data-ttu-id="f392e-156">一旦你的逻辑修改了域实体，它就会假定存储库类将正确存储它们。</span><span class="sxs-lookup"><span data-stu-id="f392e-156">Once your logic modifies the domain entities, it assumes the repository class will store them correctly.</span></span> <span data-ttu-id="f392e-157">这里的重点在于针对域模型及其域逻辑创建单元测试。</span><span class="sxs-lookup"><span data-stu-id="f392e-157">The important point here is to create unit tests against your domain model and its domain logic.</span></span> <span data-ttu-id="f392e-158">聚合根是 DDD 中的主要一致性边界。</span><span class="sxs-lookup"><span data-stu-id="f392e-158">Aggregate roots are the main consistency boundaries in DDD.</span></span>

### <a name="the-difference-between-the-repository-pattern-and-the-legacy-data-access-class-dal-class-pattern"></a><span data-ttu-id="f392e-159">存储库模式与传统数据访问类（DAL 类）模式之间的区别</span><span class="sxs-lookup"><span data-stu-id="f392e-159">The difference between the Repository pattern and the legacy Data Access class (DAL class) pattern</span></span>

<span data-ttu-id="f392e-160">数据访问对象直接对存储执行数据访问和持久性操作。</span><span class="sxs-lookup"><span data-stu-id="f392e-160">A data access object directly performs data access and persistence operations against storage.</span></span> <span data-ttu-id="f392e-161">存储库则使用要在工作单元对象的内存中执行的操作对数据进行标记（正如在 EF 中使用 DbContext 时一样），但不立即执行这些更新。</span><span class="sxs-lookup"><span data-stu-id="f392e-161">A repository marks the data with the operations you want to perform in the memory of a unit of work object (as in EF when using the DbContext), but these updates aren't performed immediately.</span></span>

<span data-ttu-id="f392e-162">工作单元亦称单个事务，涉及多个插入、更新或删除操作。</span><span class="sxs-lookup"><span data-stu-id="f392e-162">A unit of work is referred to as a single transaction that involves multiple insert, update, or delete operations.</span></span> <span data-ttu-id="f392e-163">简而言之，这意味着对于特定的用户操作（例如，网站注册），所有插入、更新和删除事务都在单个事务中处理。</span><span class="sxs-lookup"><span data-stu-id="f392e-163">In simple terms, it means that for a specific user action (for example, registration on a website), all the insert, update, and delete transactions are handled in a single transaction.</span></span> <span data-ttu-id="f392e-164">这比以更繁琐的方式处理多个数据库事务更有效。</span><span class="sxs-lookup"><span data-stu-id="f392e-164">This is more efficient than handling multiple database transactions in a chattier way.</span></span>

<span data-ttu-id="f392e-165">这几个持久性操作稍后会在应用层中的代码发出命令时，在单个操作中执行。</span><span class="sxs-lookup"><span data-stu-id="f392e-165">These multiple persistence operations are performed later in a single action when your code from the application layer commands it.</span></span> <span data-ttu-id="f392e-166">关于将内存中更改应用于实际数据库存储的决策通常基于[工作单元模式](http://martinfowler.com/eaaCatalog/unitOfWork.html)。</span><span class="sxs-lookup"><span data-stu-id="f392e-166">The decision about applying the in-memory changes to the actual database storage is typically based on the [Unit of Work pattern](http://martinfowler.com/eaaCatalog/unitOfWork.html).</span></span> <span data-ttu-id="f392e-167">在 EF 中，工作单元模式作为 DBContext 实现。</span><span class="sxs-lookup"><span data-stu-id="f392e-167">In EF, the Unit of Work pattern is implemented as the DBContext.</span></span>

<span data-ttu-id="f392e-168">在许多情况下，这种对存储应用操作的模式或方式可以提高应用程序性能并减少出现不一致的可能性。</span><span class="sxs-lookup"><span data-stu-id="f392e-168">In many cases, this pattern or way of applying operations against the storage can increase application performance and reduce the possibility of inconsistencies.</span></span> <span data-ttu-id="f392e-169">此外，它还能减少数据库表中的事务阻塞，因为所有预期操作都作为一个事务的一部分进行提交。</span><span class="sxs-lookup"><span data-stu-id="f392e-169">Also, it reduces transaction blocking in the database tables, because all the intended operations are committed as part of one transaction.</span></span> <span data-ttu-id="f392e-170">与对数据库执行许多独立操作相比，这样做效率更高。</span><span class="sxs-lookup"><span data-stu-id="f392e-170">This is more efficient in comparison to executing many isolated operations against the database.</span></span> <span data-ttu-id="f392e-171">因此，选定的 ORM 能够通过在同一个事务中对几个更新操作进行分组来优化对数据库的执行，而不是使用许多单独的小型事务执行。</span><span class="sxs-lookup"><span data-stu-id="f392e-171">Therefore, the selected ORM is able to optimize the execution against the database by grouping several update actions within the same transaction, as opposed to many small and separate transaction executions.</span></span>

### <a name="repositories-should-not-be-mandatory"></a><span data-ttu-id="f392e-172">存储库不应该是强制性的</span><span class="sxs-lookup"><span data-stu-id="f392e-172">Repositories should not be mandatory</span></span>

<span data-ttu-id="f392e-173">自定义存储库适用于前面提到的原因，这也是 eShopOnContainers 中的订购微服务所采用的方法。</span><span class="sxs-lookup"><span data-stu-id="f392e-173">Custom repositories are useful for the reasons cited earlier, and that is the approach for the ordering microservice in eShopOnContainers.</span></span> <span data-ttu-id="f392e-174">但是，它不是一种必须在 DDD 设计中甚至在 .NET 的一般开发中实现的模式。</span><span class="sxs-lookup"><span data-stu-id="f392e-174">However, it is not an essential pattern to implement in a DDD design or even in general development in .NET.</span></span>

<span data-ttu-id="f392e-175">例如，Jimmy Bogard 在为本指南提供直接反馈时表示：</span><span class="sxs-lookup"><span data-stu-id="f392e-175">For instance, Jimmy Bogard, when providing direct feedback for this guide, said the following:</span></span>

<span data-ttu-id="f392e-176">这可能是我最重要的一次反馈。</span><span class="sxs-lookup"><span data-stu-id="f392e-176">This’ll probably be my biggest feedback.</span></span> <span data-ttu-id="f392e-177">我真的不喜欢存储库，主要是因为它们隐藏了底层持久性机制的重要细节。</span><span class="sxs-lookup"><span data-stu-id="f392e-177">I’m really not a fan of repositories, mainly because they hide the important details of the underlying persistence mechanism.</span></span> <span data-ttu-id="f392e-178">这也是我选择 MediatR 命令的原因。</span><span class="sxs-lookup"><span data-stu-id="f392e-178">It’s why I go for MediatR for commands, too.</span></span> <span data-ttu-id="f392e-179">我可以利用持久性层的完整功能，将所有域行为推送到我的聚合根中。</span><span class="sxs-lookup"><span data-stu-id="f392e-179">I can use the full power of the persistence layer, and push all that domain behavior into my aggregate roots.</span></span> <span data-ttu-id="f392e-180">我通常不想模拟存储库 — 我仍然需要对真实存在的东西执行集成测试。</span><span class="sxs-lookup"><span data-stu-id="f392e-180">I don’t usually want to mock my repositories – I still need to have that integration test with the real thing.</span></span> <span data-ttu-id="f392e-181">使用 CQRS 意味着我们不再需要存储库。</span><span class="sxs-lookup"><span data-stu-id="f392e-181">Going CQRS meant that we didn’t really have a need for repositories any more.</span></span>

<span data-ttu-id="f392e-182">我们发现存储库很有用，但我们承认它们对你的 DDD 并不重要，这一点与聚合模式和丰富域模型不同。</span><span class="sxs-lookup"><span data-stu-id="f392e-182">We find repositories useful, but we acknowledge that they are not critical for your DDD, in the way that the Aggregate pattern and rich domain model are.</span></span> <span data-ttu-id="f392e-183">因此，你可以根据需要使用或不使用存储库模式。</span><span class="sxs-lookup"><span data-stu-id="f392e-183">Therefore, use the Repository pattern or not, as you see fit.</span></span>

## <a name="the-specification-pattern"></a><span data-ttu-id="f392e-184">规范模式</span><span class="sxs-lookup"><span data-stu-id="f392e-184">The Specification pattern</span></span>

<span data-ttu-id="f392e-185">规范模式（全名为查询规范模式）是一种域驱动设计模式，用作可放置含可选排序和分页逻辑的查询定义的位置。</span><span class="sxs-lookup"><span data-stu-id="f392e-185">The Specification pattern (its full name would be Query-specification pattern) is a Domain-Driven Design pattern designed as the place where you can put the definition of a query with optional sorting and paging logic.</span></span>

<span data-ttu-id="f392e-186">规范模式定义对象中的查询。</span><span class="sxs-lookup"><span data-stu-id="f392e-186">The Specification pattern defines a query in an object.</span></span> <span data-ttu-id="f392e-187">例如，为了封装搜索某些产品的分页查询，可以创建采用必要输入参数（pageNumber、pageSize、filter 等）的 PagedProduct 规范。</span><span class="sxs-lookup"><span data-stu-id="f392e-187">For example, in order to encapsulate a paged query that searches for some products, you can create a PagedProduct specification that takes the necessary input parameters (pageNumber, pageSize, filter, etc.).</span></span> <span data-ttu-id="f392e-188">然后，在任何存储库方法（通常为 List() 重载）内，它会接受 ISpecification 并基于该规范运行预期的查询。</span><span class="sxs-lookup"><span data-stu-id="f392e-188">Then, within any Repository method (usually a List() overload) it would accept an ISpecification and run the expected query based on that specification.</span></span>

<span data-ttu-id="f392e-189">这种方法有几个好处：</span><span class="sxs-lookup"><span data-stu-id="f392e-189">There are several benefits to this approach:</span></span>

* <span data-ttu-id="f392e-190">规范具有名称（而不只是一堆 LINQ 表达式），你可以对其进行讨论。</span><span class="sxs-lookup"><span data-stu-id="f392e-190">The specification has a name (as opposed to just a bunch of LINQ expressions) that you can discuss about.</span></span>

* <span data-ttu-id="f392e-191">可以对规范单独进行单元测试，以确保它是正确的。</span><span class="sxs-lookup"><span data-stu-id="f392e-191">The specification can be unit tested in isolation to ensure it is right.</span></span> <span data-ttu-id="f392e-192">如果你需要相似的行为，也可以轻松地重复使用规范。</span><span class="sxs-lookup"><span data-stu-id="f392e-192">It can also easily be reused if you need similar behavior.</span></span> <span data-ttu-id="f392e-193">例如，在 MVC 视图操作和 Web API 操作上，以及各种服务中。</span><span class="sxs-lookup"><span data-stu-id="f392e-193">For example, on an MVC View action and a Web API action, as well as in various services.</span></span>

* <span data-ttu-id="f392e-194">规范还可用于描述要返回的数据的形状，以便查询仅返回所需的数据。</span><span class="sxs-lookup"><span data-stu-id="f392e-194">A specification can also be used to describe the shape of the data to be returned, so that queries can return just the data they required.</span></span> <span data-ttu-id="f392e-195">这样就不必在 Web 应用程序中进行延迟加载（这通常不是什么好主意），并且有助于使存储库实现免受这些细节的干扰。</span><span class="sxs-lookup"><span data-stu-id="f392e-195">This eliminates the need for lazy loading in web applications (which is usually not a good idea) and helps keep repository implementations from becoming cluttered with these details.</span></span>

<span data-ttu-id="f392e-196">常规规范接口示例如下面的 [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb ) 的代码。</span><span class="sxs-lookup"><span data-stu-id="f392e-196">An example of a generic Specification interface is the following code from [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb ).</span></span>

```csharp
// https://github.com/dotnet-architecture/eShopOnWeb 
public interface ISpecification<T>
{
    Expression<Func<T, bool>> Criteria { get; }
    List<Expression<Func<T, object>>> Includes { get; }
    List<string> IncludeStrings { get; }
}
```

<span data-ttu-id="f392e-197">接下来的部分解释了如何使用 Entity Framework Core 2.0 实现规范模式，以及如何从任何存储库类中使用它。</span><span class="sxs-lookup"><span data-stu-id="f392e-197">In the upcoming sections, it is explained how to implement the Specification pattern with Entity Framework Core 2.0 and how to use it from any Repository class.</span></span>

<span data-ttu-id="f392e-198">**重要说明：**规范模式是一种旧模式，可通过多种方式实现，如下面的其他资源中所示。</span><span class="sxs-lookup"><span data-stu-id="f392e-198">**Important note:** The specification pattern is an old pattern that can be implemented in many different ways, as in the following additional resources.</span></span> <span data-ttu-id="f392e-199">作为一种模式/概念，旧方法容易理解，但要留心那些未利用现代语言功能（如 Linq 和表达式）的旧实现。</span><span class="sxs-lookup"><span data-stu-id="f392e-199">As a pattern/idea, older approaches are good to know, but beware of older implementations that are not taking advantage of modern language capabilities like Linq and expressions.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f392e-200">其他资源</span><span class="sxs-lookup"><span data-stu-id="f392e-200">Additional resources</span></span>

### <a name="the-repository-pattern"></a><span data-ttu-id="f392e-201">存储库模式</span><span class="sxs-lookup"><span data-stu-id="f392e-201">The Repository pattern</span></span>

-   <span data-ttu-id="f392e-202">**Edward Hieatt 和 Rob Mee.Repository pattern.**（存储库模式。）
    [*http://martinfowler.com/eaaCatalog/repository.html*](http://martinfowler.com/eaaCatalog/repository.html)</span><span class="sxs-lookup"><span data-stu-id="f392e-202">**Edward Hieatt and Rob Mee. Repository pattern.**
[*http://martinfowler.com/eaaCatalog/repository.html*](http://martinfowler.com/eaaCatalog/repository.html)</span></span>

-   <span data-ttu-id="f392e-203">**存储库模式**
    [https://msdn.microsoft.com/library/ff649690.aspx](https://msdn.microsoft.com/library/ff649690.aspx)</span><span class="sxs-lookup"><span data-stu-id="f392e-203">**The Repository pattern**
[*https://msdn.microsoft.com/library/ff649690.aspx*](https://msdn.microsoft.com/library/ff649690.aspx)</span></span>

-   <span data-ttu-id="f392e-204">**Repository Pattern: A data persistence abstraction**（存储库模式：数据持久性抽象）
    [*http://deviq.com/repository-pattern/*](http://deviq.com/repository-pattern/)</span><span class="sxs-lookup"><span data-stu-id="f392e-204">**Repository Pattern: A data persistence abstraction**
[*http://deviq.com/repository-pattern/*](http://deviq.com/repository-pattern/)</span></span>

-   <span data-ttu-id="f392e-205">**Eric Evans。Domain-Driven Design: Tackling Complexity in the Heart of Software.**（域驱动设计：软件核心复杂性应对之道。）</span><span class="sxs-lookup"><span data-stu-id="f392e-205">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="f392e-206">（书中讨论了存储库模式）[https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="f392e-206">(Book; includes a discussion of the Repository pattern) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

### <a name="unit-of-work-pattern"></a><span data-ttu-id="f392e-207">工作单元模式</span><span class="sxs-lookup"><span data-stu-id="f392e-207">Unit of Work pattern</span></span>

-   <span data-ttu-id="f392e-208">**Martin Fowler。Unit of Work pattern.**（工作单元模式。）
    [*http://martinfowler.com/eaaCatalog/unitOfWork.html*](http://martinfowler.com/eaaCatalog/unitOfWork.html)</span><span class="sxs-lookup"><span data-stu-id="f392e-208">**Martin Fowler. Unit of Work pattern.**
[*http://martinfowler.com/eaaCatalog/unitOfWork.html*](http://martinfowler.com/eaaCatalog/unitOfWork.html)</span></span>

<!-- -->

-   <span data-ttu-id="f392e-209">**Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application**（在 ASP.NET MVC 应用程序中实现存储库和单元工作模式）
    [https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span><span class="sxs-lookup"><span data-stu-id="f392e-209">**Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application**
[*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span></span>

### <a name="the-specification-pattern"></a><span data-ttu-id="f392e-210">规范模式</span><span class="sxs-lookup"><span data-stu-id="f392e-210">The Specification pattern</span></span>

-   <span data-ttu-id="f392e-211">**The Specification pattern.**（规范模式。）
    [*http://deviq.com/specification-pattern/*](http://deviq.com/specification-pattern/)</span><span class="sxs-lookup"><span data-stu-id="f392e-211">**The Specification pattern.**
[*http://deviq.com/specification-pattern/*](http://deviq.com/specification-pattern/)</span></span>

-   <span data-ttu-id="f392e-212">**Eric Evans (2004)。域驱动设计。Addison-Wesley. p. 224。**</span><span class="sxs-lookup"><span data-stu-id="f392e-212">**Evans, Eric (2004). Domain Driven Design. Addison-Wesley. p. 224.**</span></span>

-   <span data-ttu-id="f392e-213">**规范。Martin Fowler**
    [https://www.martinfowler.com/apsupp/spec.pdf/](https://www.martinfowler.com/apsupp/spec.pdf)</span><span class="sxs-lookup"><span data-stu-id="f392e-213">**Specifications. Martin Fowler**
[*https://www.martinfowler.com/apsupp/spec.pdf/*](https://www.martinfowler.com/apsupp/spec.pdf)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="f392e-214">[上一篇] (domain-events-design-implementation.md) [下一篇] (infrastructure-persistence-layer-implemenation-entity-framework-core.md)</span><span class="sxs-lookup"><span data-stu-id="f392e-214">[Previous] (domain-events-design-implementation.md) [Next] (infrastructure-persistence-layer-implemenation-entity-framework-core.md)</span></span>
