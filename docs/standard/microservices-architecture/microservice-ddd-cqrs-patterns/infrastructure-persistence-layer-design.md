---
title: "设计基础结构持久性层"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |设计基础结构持久性层"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ce0f1d608eed909a7707f3c580afc5253f3eef06
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-infrastructure-persistence-layer"></a><span data-ttu-id="c021e-104">设计基础结构持久性层</span><span class="sxs-lookup"><span data-stu-id="c021e-104">Designing the infrastructure persistence layer</span></span>

<span data-ttu-id="c021e-105">数据持久性组件提供对托管微服务 （即，微服务构成的数据库） 的边界内的数据访问。</span><span class="sxs-lookup"><span data-stu-id="c021e-105">Data persistence components provide access to the data hosted within the boundaries of a microservice (that is, a microservice’s database).</span></span> <span data-ttu-id="c021e-106">它们包含的组件，如存储库的实际实现和[工作单元](http://martinfowler.com/eaaCatalog/unitOfWork.html)类，如自定义 EF Dbcontext。</span><span class="sxs-lookup"><span data-stu-id="c021e-106">They contain the actual implementation of components such as repositories and [Unit of Work](http://martinfowler.com/eaaCatalog/unitOfWork.html) classes, like custom EF DBContexts.</span></span>

## <a name="the-repository-pattern"></a><span data-ttu-id="c021e-107">存储库模式</span><span class="sxs-lookup"><span data-stu-id="c021e-107">The Repository pattern</span></span>

<span data-ttu-id="c021e-108">存储库类或组件，用于封装各种访问数据源所需的逻辑。</span><span class="sxs-lookup"><span data-stu-id="c021e-108">Repositories are classes or components that encapsulate the logic required to access data sources.</span></span> <span data-ttu-id="c021e-109">它们集中处理通用数据访问功能，提供更好的可维护性和分离的基础结构或用来从域模型层访问数据库技术。</span><span class="sxs-lookup"><span data-stu-id="c021e-109">They centralize common data access functionality, providing better maintainability and decoupling the infrastructure or technology used to access databases from the domain model layer.</span></span> <span data-ttu-id="c021e-110">如果你使用如实体框架 ORM，则必须实现的代码被简化，感谢 LINQ 和强类型化。</span><span class="sxs-lookup"><span data-stu-id="c021e-110">If you use an ORM like Entity Framework, the code that must be implemented is simplified, thanks to LINQ and strong typing.</span></span> <span data-ttu-id="c021e-111">这允许您将精力集中在数据持久性逻辑上，而不是在数据访问管道。</span><span class="sxs-lookup"><span data-stu-id="c021e-111">This lets you focus on the data persistence logic rather than on data access plumbing.</span></span>

<span data-ttu-id="c021e-112">存储库模式是使用与数据源的完备的方法。</span><span class="sxs-lookup"><span data-stu-id="c021e-112">The Repository pattern is a well-documented way of working with a data source.</span></span> <span data-ttu-id="c021e-113">书中[模式的企业应用程序体系结构](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/)，Martin Fowler 描述存储库，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c021e-113">In the book [Patterns of Enterprise Application Architecture](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/), Martin Fowler describes a repository as follows:</span></span>

<span data-ttu-id="c021e-114">存储库执行的任务之间的域模型层和数据映射到内存中的域对象的一组类似的方式中起作用的媒介。</span><span class="sxs-lookup"><span data-stu-id="c021e-114">A repository performs the tasks of an intermediary between the domain model layers and data mapping, acting in a similar way to a set of domain objects in memory.</span></span> <span data-ttu-id="c021e-115">客户端对象以声明方式生成查询，并将其发送给答案的存储库。</span><span class="sxs-lookup"><span data-stu-id="c021e-115">Client objects declaratively build queries and send them to the repositories for answers.</span></span> <span data-ttu-id="c021e-116">从概念上讲，一个存储库中封装一组对象存储在数据库中，可以对它们，执行提供更接近于持久性层一种方法的操作。</span><span class="sxs-lookup"><span data-stu-id="c021e-116">Conceptually, a repository encapsulates a set of objects stored in the database and operations that can be performed on them, providing a way that is closer to the persistence layer.</span></span> <span data-ttu-id="c021e-117">存储库，此外，支持将分离开来，明确并按一个方向工作域和数据分配之间的依赖关系或映射的用途。</span><span class="sxs-lookup"><span data-stu-id="c021e-117">Repositories, also, support the purpose of separating, clearly and in one direction, the dependency between the work domain and the data allocation or mapping.</span></span>

### <a name="define-one-repository-per-aggregate"></a><span data-ttu-id="c021e-118">定义每个聚合的一个存储库</span><span class="sxs-lookup"><span data-stu-id="c021e-118">Define one repository per aggregate</span></span>

<span data-ttu-id="c021e-119">对于每个聚合或聚合的根，您应该创建一个存储库类。</span><span class="sxs-lookup"><span data-stu-id="c021e-119">For each aggregate or aggregate root, you should create one repository class.</span></span> <span data-ttu-id="c021e-120">在基于域驱动的设计模式微服务，应使用以更新数据库的唯一通道应存储库。</span><span class="sxs-lookup"><span data-stu-id="c021e-120">In a microservice based on domain-driven design patterns, the only channel you should use to update the database should be the repositories.</span></span> <span data-ttu-id="c021e-121">这是因为它们具有与聚合根域，它控制聚合的固定条件及事务一致性一对一的关系。</span><span class="sxs-lookup"><span data-stu-id="c021e-121">This is because they have a one-to-one relationship with the aggregate root, which controls the aggregate’s invariants and transactional consistency.</span></span> <span data-ttu-id="c021e-122">可以通过其他数据库中查询通道 （如你可以执行以下 CQRS 方法），因为查询不会更改数据库的状态。</span><span class="sxs-lookup"><span data-stu-id="c021e-122">It is okay to query the database through other channels (as you can do following a CQRS approach), because queries do not change the state of the database.</span></span> <span data-ttu-id="c021e-123">但是，事务区域-更新-必须始终控制存储库和聚合根。</span><span class="sxs-lookup"><span data-stu-id="c021e-123">However, the transactional area—the updates—must always be controlled by the repositories and the aggregate roots.</span></span>

<span data-ttu-id="c021e-124">基本上，一个存储库，可填充来自的域实体的窗体中的数据库的内存中的数据。</span><span class="sxs-lookup"><span data-stu-id="c021e-124">Basically, a repository allows you to populate data in memory that comes from the database in the form of the domain entities.</span></span> <span data-ttu-id="c021e-125">在内存中的实体后，可以更改以及然后将其保存回通过事务的数据库。</span><span class="sxs-lookup"><span data-stu-id="c021e-125">Once the entities are in memory, they can be changed and then persisted back to the database through transactions.</span></span>

<span data-ttu-id="c021e-126">如前所述，如果你使用 CQS/CQRS 体系结构模式，将由域模型中，执行简单的 SQL 语句，使用 Dapper 外侧查询执行的初始查询。</span><span class="sxs-lookup"><span data-stu-id="c021e-126">As noted earlier, if you are using the CQS/CQRS architectural pattern, the initial queries will be performed by side queries out of the domain model, performed by simple SQL statements using Dapper.</span></span> <span data-ttu-id="c021e-127">这种方法是更多，你需要比存储库灵活因为您可以查询和联接任何表，并且这些查询不会限制由规则聚合。</span><span class="sxs-lookup"><span data-stu-id="c021e-127">This approach is much more flexible than repositories because you can query and join any tables you need, and these queries are not restricted by rules from the aggregates.</span></span> <span data-ttu-id="c021e-128">该数据将转到演示文稿层或客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="c021e-128">That data will go to the presentation layer or client app.</span></span>

<span data-ttu-id="c021e-129">如果用户进行更改，要更新的数据将来自客户端应用程序或演示文稿层到应用程序层 （如 Web API 服务）。</span><span class="sxs-lookup"><span data-stu-id="c021e-129">If the user makes changes, the data to be updated will come from the client app or presentation layer to the application layer (such as a Web API service).</span></span> <span data-ttu-id="c021e-130">当命令处理程序中收到 （具有数据） 的命令时，请使用存储库来获取你想要从数据库进行更新的数据。</span><span class="sxs-lookup"><span data-stu-id="c021e-130">When you receive a command (with data) in a command handler, you use repositories to get the data you want to update from the database.</span></span> <span data-ttu-id="c021e-131">你在内存中与使用命令，传递的信息进行更新，然后添加或更新事务通过数据库中的数据 （域实体）。</span><span class="sxs-lookup"><span data-stu-id="c021e-131">You update it in memory with the information passed with the commands, and you then add or update the data (domain entities) in the database through a transaction.</span></span>

<span data-ttu-id="c021e-132">我们必须强调再次的是，应为每个聚合根定义仅一个存储库，在图 9-17 中所示。</span><span class="sxs-lookup"><span data-stu-id="c021e-132">We must emphasize again that only one repository should be defined for each aggregate root, as shown in Figure 9-17.</span></span> <span data-ttu-id="c021e-133">若要实现的聚合根的目标为维护聚合内的所有对象之间的事务一致性，应永远不会在数据库中创建的每个表的存储库。</span><span class="sxs-lookup"><span data-stu-id="c021e-133">To achieve the goal of the aggregate root to maintain transactional consistency between all the objects within the aggregate, you should never create a repository for each table in the database.</span></span>

![](./media/image18.png)

<span data-ttu-id="c021e-134">**图 9-17**。</span><span class="sxs-lookup"><span data-stu-id="c021e-134">**Figure 9-17**.</span></span> <span data-ttu-id="c021e-135">存储库、 聚合和数据库表之间的关系</span><span class="sxs-lookup"><span data-stu-id="c021e-135">The relationship between repositories, aggregates, and database tables</span></span>

### <a name="enforcing-one-aggregate-root-per-repository"></a><span data-ttu-id="c021e-136">强制实施每个存储库的一个聚合根</span><span class="sxs-lookup"><span data-stu-id="c021e-136">Enforcing one aggregate root per repository</span></span>

<span data-ttu-id="c021e-137">可以是很有价值实现存储库设计的方式，它会强制实施仅聚合根应具有存储库的规则。</span><span class="sxs-lookup"><span data-stu-id="c021e-137">It can be valuable to implement your repository design in such a way that it enforces the rule that only aggregate roots should have repositories.</span></span> <span data-ttu-id="c021e-138">你可以创建泛型数据或基数据存储库类型约束与配合工作以确保其具有 IAggregateRoot 标记接口的实体的类型。</span><span class="sxs-lookup"><span data-stu-id="c021e-138">You can create a generic or base repository type that constrains the type of entities it works with to ensure they have the IAggregateRoot marker interface.</span></span>

<span data-ttu-id="c021e-139">因此，在基础结构层实现每个存储库类实现其自己的协定或接口，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="c021e-139">Thus, each repository class implemented at the infrastructure layer implements its own contract or interface, as shown in the following code:</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class OrderRepository : IOrderRepository
    {
```

<span data-ttu-id="c021e-140">每个特定的存储库接口实现的泛型 IRepository 接口：</span><span class="sxs-lookup"><span data-stu-id="c021e-140">Each specific repository interface implements the generic IRepository interface:</span></span>

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
    // ...
}
```

<span data-ttu-id="c021e-141">但是，更好的方法让代码强制实施约定每个存储库应与单个聚合可以实现泛型存储库类型，因此很显式使用的存储库的目的面向特定的聚合。</span><span class="sxs-lookup"><span data-stu-id="c021e-141">However, a better way to have the code enforce the convention that each repository should be related to a single aggregate would be to implement a generic repository type so it is explicit that you are using a repository to target a specific aggregate.</span></span> <span data-ttu-id="c021e-142">可以通过实现该泛型 IRepository 基接口，如以下代码所示中轻松地完成：</span><span class="sxs-lookup"><span data-stu-id="c021e-142">That can be easily done by implementing that generic in the IRepository base interface, as in the following code:</span></span>

```csharp
  public interface IRepository<T> where T : IAggregateRoot
```

### <a name="the-repository-pattern-makes-it-easier-to-test-your-application-logic"></a><span data-ttu-id="c021e-143">存储库模式，更便于测试应用程序逻辑</span><span class="sxs-lookup"><span data-stu-id="c021e-143">The Repository pattern makes it easier to test your application logic</span></span>

<span data-ttu-id="c021e-144">存储库模式，你可以轻松地具有单元测试中测试你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c021e-144">The Repository pattern allows you to easily test your application with unit tests.</span></span> <span data-ttu-id="c021e-145">请记住，单元测试仅测试你的代码、 非基础结构，因此存储库抽象更加轻松地实现该目标。</span><span class="sxs-lookup"><span data-stu-id="c021e-145">Remember that unit tests only test your code, not infrastructure, so the repository abstractions make it easier to achieve that goal.</span></span>

<span data-ttu-id="c021e-146">如前面部分所述，建议你定义，并放置的存储库接口在域模型层中以便应用程序层 (例如，Web API microservice) 不直接依赖基础结构层中必须使用实现的实际存储库类。</span><span class="sxs-lookup"><span data-stu-id="c021e-146">As noted in an earlier section, it is recommended that you define and place the repository interfaces in the domain model layer so the application layer (for instance, your Web API microservice) does not depend directly on the infrastructure layer where you have implemented the actual repository classes.</span></span> <span data-ttu-id="c021e-147">通过执行此操作，并在你的 Web api 控制器中使用依赖关系注入，你可以实现模拟从数据库返回假数据而不是数据的存储库。</span><span class="sxs-lookup"><span data-stu-id="c021e-147">By doing this and using Dependency Injection in the controllers of your Web API, you can implement mock repositories that return fake data instead of data from the database.</span></span> <span data-ttu-id="c021e-148">去耦的方法允许你创建和运行的单元测试，可以测试只是你的应用程序的逻辑，而无需连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="c021e-148">That decoupled approach allows you to create and run unit tests that can test just the logic of your application without requiring connectivity to the database.</span></span>

<span data-ttu-id="c021e-149">连接到数据库可能会失败，并更重要的是，针对数据库运行数百个测试是错误的两个原因。</span><span class="sxs-lookup"><span data-stu-id="c021e-149">Connections to databases can fail and, more importantly, running hundreds of tests against a database is bad for two reasons.</span></span> <span data-ttu-id="c021e-150">首先，因为大量测试可能需要大量时间。</span><span class="sxs-lookup"><span data-stu-id="c021e-150">First, it can take a lot of time because of the large number of tests.</span></span> <span data-ttu-id="c021e-151">其次，数据库记录可能会更改，并影响你测试的结果，以便它们可能不一致。</span><span class="sxs-lookup"><span data-stu-id="c021e-151">Second, the database records might change and impact the results of your tests, so that they might not be consistent.</span></span> <span data-ttu-id="c021e-152">针对数据库的测试不是单元测试集成测试。</span><span class="sxs-lookup"><span data-stu-id="c021e-152">Testing against the database is not a unit tests but an integration test.</span></span> <span data-ttu-id="c021e-153">你应多个单元测试运行速度快，而较少的集成测试对数据库。</span><span class="sxs-lookup"><span data-stu-id="c021e-153">You should have many unit tests running fast, but fewer integration tests against the databases.</span></span>

<span data-ttu-id="c021e-154">方面的单元测试的关注点分离，你的逻辑在内存中的域实体进行操作。</span><span class="sxs-lookup"><span data-stu-id="c021e-154">In terms of separation of concerns for unit tests, your logic operates on domain entities in memory.</span></span> <span data-ttu-id="c021e-155">它假定存储库类传递那些。</span><span class="sxs-lookup"><span data-stu-id="c021e-155">It assumes the repository class has delivered those.</span></span> <span data-ttu-id="c021e-156">一旦你的逻辑修改域实体，该示例假定存储库类将正确存储它们。</span><span class="sxs-lookup"><span data-stu-id="c021e-156">Once your logic modifies the domain entities, it assumes the repository class will store them correctly.</span></span> <span data-ttu-id="c021e-157">重要的一点是创建针对您的域模型和其域逻辑单元测试。</span><span class="sxs-lookup"><span data-stu-id="c021e-157">The important point here is to create unit tests against your domain model and its domain logic.</span></span> <span data-ttu-id="c021e-158">聚合根是 DDD 中的主要一致性边界。</span><span class="sxs-lookup"><span data-stu-id="c021e-158">Aggregate roots are the main consistency boundaries in DDD.</span></span>

### <a name="the-difference-between-the-repository-pattern-and-the-legacy-data-access-class-dal-class-pattern"></a><span data-ttu-id="c021e-159">存储库模式和旧的数据访问类 （DAL 类） 模式之间的差异</span><span class="sxs-lookup"><span data-stu-id="c021e-159">The difference between the Repository pattern and the legacy Data Access class (DAL class) pattern</span></span>

<span data-ttu-id="c021e-160">数据访问对象直接执行了针对存储的数据访问和持久性操作。</span><span class="sxs-lookup"><span data-stu-id="c021e-160">A data access object directly performs data access and persistence operations against storage.</span></span> <span data-ttu-id="c021e-161">将不会立即执行与你想要在单元的工作对象 （如所示 EF 使用 DbContext 时)，但这些更新内存中执行的操作数据存储库标记。</span><span class="sxs-lookup"><span data-stu-id="c021e-161">A repository marks the data with the operations you want to perform in the memory of a unit of work object (as in EF when using the DbContext), but these updates will not be performed immediately.</span></span>

<span data-ttu-id="c021e-162">工作单元被称之为作为单个事务涉及多个插入、 更新或删除操作。</span><span class="sxs-lookup"><span data-stu-id="c021e-162">A unit of work is referred to as a single transaction that involves multiple insert, update, or delete operations.</span></span> <span data-ttu-id="c021e-163">简单地说，这意味着，对于特定的用户操作 （例如，在网站上的注册），所有插入、 更新和删除事务在都处理单个事务中。</span><span class="sxs-lookup"><span data-stu-id="c021e-163">In simple terms, it means that for a specific user action (for example, registration on a website), all the insert, update, and delete transactions are handled in a single transaction.</span></span> <span data-ttu-id="c021e-164">这是比 chattier 方式处理多个数据库事务更高效。</span><span class="sxs-lookup"><span data-stu-id="c021e-164">This is more efficient than handling multiple database transactions in a chattier way.</span></span>

<span data-ttu-id="c021e-165">应用程序层中的代码命令它时，将更高版本在单个操作中执行这些多个持久性操作。</span><span class="sxs-lookup"><span data-stu-id="c021e-165">These multiple persistence operations will be performed later in a single action when your code from the application layer commands it.</span></span> <span data-ttu-id="c021e-166">将内存中更改应用于实际的数据库存储的决定通常基于[单元的工作模式](http://martinfowler.com/eaaCatalog/unitOfWork.html)。</span><span class="sxs-lookup"><span data-stu-id="c021e-166">The decision about applying the in-memory changes to the actual database storage is typically based on the [Unit of Work pattern](http://martinfowler.com/eaaCatalog/unitOfWork.html).</span></span> <span data-ttu-id="c021e-167">在 EF，作为 DBContext 实现单元的工作模式。</span><span class="sxs-lookup"><span data-stu-id="c021e-167">In EF, the Unit of Work pattern is implemented as the DBContext.</span></span>

<span data-ttu-id="c021e-168">在许多情况下，此模式或将应用对存储操作的方式可以提高应用程序性能并降低出现不一致的可能性。</span><span class="sxs-lookup"><span data-stu-id="c021e-168">In many cases, this pattern or way of applying operations against the storage can increase application performance and reduce the possibility of inconsistencies.</span></span> <span data-ttu-id="c021e-169">此外，它减少了事务阻止在数据库表中，因为所有预期的操作是作为一个事务的一部分提交。</span><span class="sxs-lookup"><span data-stu-id="c021e-169">Also, it reduces transaction blocking in the database tables, because all the intended operations are committed as part of one transaction.</span></span> <span data-ttu-id="c021e-170">这是与执行对数据库的多个独立的操作相比更高效。</span><span class="sxs-lookup"><span data-stu-id="c021e-170">This is more efficient in comparison to executing many isolated operations against the database.</span></span> <span data-ttu-id="c021e-171">因此，所选的 ORM 将能够通过对同一事务，而不是许多小型和单独的事务执行中的多个更新操作进行分组来优化对数据库执行。</span><span class="sxs-lookup"><span data-stu-id="c021e-171">Therefore, the selected ORM will be able to optimize the execution against the database by grouping several update actions within the same transaction, as opposed to many small and separate transaction executions.</span></span>

### <a name="repositories-should-not-be-mandatory"></a><span data-ttu-id="c021e-172">存储库不应为必填</span><span class="sxs-lookup"><span data-stu-id="c021e-172">Repositories should not be mandatory</span></span>

<span data-ttu-id="c021e-173">自定义存储库可用于更早版本，提到的原因，这是在 eShopOnContainers 排序微服务构成的方法。</span><span class="sxs-lookup"><span data-stu-id="c021e-173">Custom repositories are useful for the reasons cited earlier, and that is the approach for the ordering microservice in eShopOnContainers.</span></span> <span data-ttu-id="c021e-174">但是，它不是在 DDD 设计中实现，甚至在一般情况下开发.NET 中的基本模式。</span><span class="sxs-lookup"><span data-stu-id="c021e-174">However, it is not an essential pattern to implement in a DDD design or even in general development in .NET.</span></span>

<span data-ttu-id="c021e-175">例如，Jimmy Bogard，本指南提供直接反馈时称以下：</span><span class="sxs-lookup"><span data-stu-id="c021e-175">For instance, Jimmy Bogard, when providing direct feedback for this guide, said the following:</span></span>

<span data-ttu-id="c021e-176">这可能会我最大的反馈。</span><span class="sxs-lookup"><span data-stu-id="c021e-176">This’ll probably be my biggest feedback.</span></span> <span data-ttu-id="c021e-177">我实际上不风扇的存储库，主要是因为它们会隐藏基础持久性机制的重要详细信息。</span><span class="sxs-lookup"><span data-stu-id="c021e-177">I’m really not a fan of repositories, mainly because they hide the important details of the underlying persistence mechanism.</span></span> <span data-ttu-id="c021e-178">它的为什么我转 MediatR 命令，请过。</span><span class="sxs-lookup"><span data-stu-id="c021e-178">It’s why I go for MediatR for commands, too.</span></span> <span data-ttu-id="c021e-179">我可以使用持久性层的完整功能，并将所有该域行为推送到我的聚合根。</span><span class="sxs-lookup"><span data-stu-id="c021e-179">I can use the full power of the persistence layer, and push all that domain behavior into my aggregate roots.</span></span> <span data-ttu-id="c021e-180">我通常不想模拟我的存储库 – 我仍需要该集成测试与真实存在。</span><span class="sxs-lookup"><span data-stu-id="c021e-180">I don’t usually want to mock my repositories – I still need to have that integration test with the real thing.</span></span> <span data-ttu-id="c021e-181">转 CQRS 意味着，我们实际上没有存储库需要更。</span><span class="sxs-lookup"><span data-stu-id="c021e-181">Going CQRS meant that we didn’t really have a need for repositories any more.</span></span>

<span data-ttu-id="c021e-182">我们发现存储库有用，但我们确认它们并不是你 DDD 中的聚合模式和丰富的域模型的方式。</span><span class="sxs-lookup"><span data-stu-id="c021e-182">We find repositories useful, but we acknowledge that they are not critical for your DDD, in the way that the Aggregate pattern and rich domain model are.</span></span> <span data-ttu-id="c021e-183">因此，或不使用的存储库模式，如上所示符合。</span><span class="sxs-lookup"><span data-stu-id="c021e-183">Therefore, use the Repository pattern or not, as you see fit.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="c021e-184">其他资源</span><span class="sxs-lookup"><span data-stu-id="c021e-184">Additional resources</span></span>

##### <a name="the-repository-pattern"></a><span data-ttu-id="c021e-185">存储库模式</span><span class="sxs-lookup"><span data-stu-id="c021e-185">The Repository pattern</span></span>

-   <span data-ttu-id="c021e-186">**Edward Hieatt 和 Rob me。存储库模式。** 
     [ *http://martinfowler.com/eaaCatalog/repository.html*](http://martinfowler.com/eaaCatalog/repository.html)</span><span class="sxs-lookup"><span data-stu-id="c021e-186">**Edward Hieatt and Rob Mee. Repository pattern.**
[*http://martinfowler.com/eaaCatalog/repository.html*](http://martinfowler.com/eaaCatalog/repository.html)</span></span>

-   <span data-ttu-id="c021e-187">**存储库模式**
    [*https://msdn.microsoft.com/en-us/library/ff649690.aspx*](https://msdn.microsoft.com/en-us/library/ff649690.aspx)</span><span class="sxs-lookup"><span data-stu-id="c021e-187">**The Repository pattern**
[*https://msdn.microsoft.com/en-us/library/ff649690.aspx*](https://msdn.microsoft.com/en-us/library/ff649690.aspx)</span></span>

-   <span data-ttu-id="c021e-188">**存储库模式： 数据持久性抽象**
    [*http://deviq.com/repository-pattern/*](http://deviq.com/repository-pattern/)</span><span class="sxs-lookup"><span data-stu-id="c021e-188">**Repository Pattern: A data persistence abstraction**
[*http://deviq.com/repository-pattern/*](http://deviq.com/repository-pattern/)</span></span>

-   <span data-ttu-id="c021e-189">**Eric Evans。域驱动的设计： 解决软件核心的复杂性。**</span><span class="sxs-lookup"><span data-stu-id="c021e-189">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="c021e-190">（本书; 包括的存储库模式的讨论）[ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="c021e-190">(Book; includes a discussion of the Repository pattern) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

##### <a name="unit-of-work-pattern"></a><span data-ttu-id="c021e-191">单元的工作模式</span><span class="sxs-lookup"><span data-stu-id="c021e-191">Unit of Work pattern</span></span>

-   <span data-ttu-id="c021e-192">**Martin Fowler。单元的工作模式。** 
     [ *http://martinfowler.com/eaaCatalog/unitOfWork.html*](http://martinfowler.com/eaaCatalog/unitOfWork.html)</span><span class="sxs-lookup"><span data-stu-id="c021e-192">**Martin Fowler. Unit of Work pattern.**
[*http://martinfowler.com/eaaCatalog/unitOfWork.html*](http://martinfowler.com/eaaCatalog/unitOfWork.html)</span></span>

<!-- -->

-   <span data-ttu-id="c021e-193">**在 ASP.NET MVC 应用程序中实现的存储库和单元的工作模式**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span><span class="sxs-lookup"><span data-stu-id="c021e-193">**Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application**
[*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="c021e-194">[以前](域的事件的设计-implementation.md) [下一步] (infrastructure-persistence-layer-implemenation-entity-framework-core.md)</span><span class="sxs-lookup"><span data-stu-id="c021e-194">[Previous] (domain-events-design-implementation.md) [Next] (infrastructure-persistence-layer-implemenation-entity-framework-core.md)</span></span>
