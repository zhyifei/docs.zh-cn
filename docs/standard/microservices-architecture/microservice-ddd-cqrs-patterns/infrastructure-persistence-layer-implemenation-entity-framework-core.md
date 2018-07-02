---
title: 使用 Entity Framework Core 实现基础结构持久性层
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 使用 Entity Framework Core 实现基础结构持久性层
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.openlocfilehash: 6003252d7e87428c7f954b57c3b67a041e3f3b15
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106471"
---
# <a name="implementing-the-infrastructure-persistence-layer-with-entity-framework-core"></a><span data-ttu-id="6bd53-103">使用 Entity Framework Core 实现基础结构持久性层</span><span class="sxs-lookup"><span data-stu-id="6bd53-103">Implementing the infrastructure persistence layer with Entity Framework Core</span></span>

<span data-ttu-id="6bd53-104">当使用 SQL Server、Oracle 或 PostgreSQL 等关系数据库时，推荐的方法是基于 Entity Framework (EF) 实现持久性层。</span><span class="sxs-lookup"><span data-stu-id="6bd53-104">When you use relational databases such as SQL Server, Oracle, or PostgreSQL, a recommended approach is to implement the persistence layer based on Entity Framework (EF).</span></span> <span data-ttu-id="6bd53-105">EF 支持 LINQ，并为模型提供强类型化的对象，且为数据库提供简化的持久性。</span><span class="sxs-lookup"><span data-stu-id="6bd53-105">EF supports LINQ and provides strongly typed objects for your model, as well as simplified persistence into your database.</span></span>

<span data-ttu-id="6bd53-106">Entity Framework 很长一段时期作为 .NET Framework 的一部分。</span><span class="sxs-lookup"><span data-stu-id="6bd53-106">Entity Framework has a long history as part of the .NET Framework.</span></span> <span data-ttu-id="6bd53-107">使用 .NET Core 时，还应使用 Entity Framework Core，它在 Windows 或 Linux 上的运行方式与在 .NET Core 上的相同。</span><span class="sxs-lookup"><span data-stu-id="6bd53-107">When you use .NET Core, you should also use Entity Framework Core, which runs on Windows or Linux in the same way as .NET Core.</span></span> <span data-ttu-id="6bd53-108">EF Core 完全重写了 Entity Framework，采用更小的占用空间来实现，且性能上具有重大改进。</span><span class="sxs-lookup"><span data-stu-id="6bd53-108">EF Core is a complete rewrite of Entity Framework, implemented with a much smaller footprint and important improvements in performance.</span></span>

## <a name="introduction-to-entity-framework-core"></a><span data-ttu-id="6bd53-109">Entity Framework Core 简介</span><span class="sxs-lookup"><span data-stu-id="6bd53-109">Introduction to Entity Framework Core</span></span>

<span data-ttu-id="6bd53-110">Entity Framework (EF) Core 是轻量化、可扩展和跨平台版的常用 Entity Framework 数据访问技术。</span><span class="sxs-lookup"><span data-stu-id="6bd53-110">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="6bd53-111">它随 .NET Core 于 2016 年年中引入。</span><span class="sxs-lookup"><span data-stu-id="6bd53-111">It was introduced with .NET Core in mid-2016.</span></span>

<span data-ttu-id="6bd53-112">EF 简介已提供于 Microsoft 文档中，因此这里我们只提供指向该信息的链接。</span><span class="sxs-lookup"><span data-stu-id="6bd53-112">Since an introduction to EF Core is already available in Microsoft documentation, here we simply provide links to that information.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="6bd53-113">其他资源</span><span class="sxs-lookup"><span data-stu-id="6bd53-113">Additional resources</span></span>

-   <span data-ttu-id="6bd53-114">**Entity Framework Core**
    [https://docs.microsoft.com/ef/core/](https://docs.microsoft.com/ef/core/)</span><span class="sxs-lookup"><span data-stu-id="6bd53-114">**Entity Framework Core**
[*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span></span>

-   <span data-ttu-id="6bd53-115">**借助 Visual Studio 使用 ASP.NET Core 和 Entity Framework Core 入门**
    [https://docs.microsoft.com/aspnet/core/data/ef-mvc/](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span><span class="sxs-lookup"><span data-stu-id="6bd53-115">**Getting started with ASP.NET Core and Entity Framework Core using Visual Studio**
[*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span></span>

-   <span data-ttu-id="6bd53-116">**DbContext 类**
    [https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span><span class="sxs-lookup"><span data-stu-id="6bd53-116">**DbContext Class**
[*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span></span>

-   <span data-ttu-id="6bd53-117">**比较 EF Core 和 EF6.x**
    [https://docs.microsoft.com/ef/efcore-and-ef6/index](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span><span class="sxs-lookup"><span data-stu-id="6bd53-117">**Compare EF Core & EF6.x**
[*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span></span>

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a><span data-ttu-id="6bd53-118">Entity Framework Core 中的基础结构（DDD 角度）</span><span class="sxs-lookup"><span data-stu-id="6bd53-118">Infrastructure in Entity Framework Core from a DDD perspective</span></span>

<span data-ttu-id="6bd53-119">从 DDD 的角度来看，EF 的一个重要功能是能够使用 POCO 域实体，在 EF 术语中也称为 POCO 代码优先实体。</span><span class="sxs-lookup"><span data-stu-id="6bd53-119">From a DDD point of view, an important capability of EF is the ability to use POCO domain entities, also known in EF terminology as POCO *code-first entities*.</span></span> <span data-ttu-id="6bd53-120">如果使用 POCO 域实体，根据[持久性无感知](http://deviq.com/persistence-ignorance/)和[基础结构无感知](https://ayende.com/blog/3137/infrastructure-ignorance)原则，域模型类对于持久性是无感知的。</span><span class="sxs-lookup"><span data-stu-id="6bd53-120">If you use POCO domain entities, your domain model classes are persistence-ignorant, following the [Persistence Ignorance](http://deviq.com/persistence-ignorance/) and the [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance) principles.</span></span>

<span data-ttu-id="6bd53-121">根据 DDD 模式，应在实体类自身内封装域行为和规则，以便在访问任何集合时，它可以控制不变量、验证和规则。</span><span class="sxs-lookup"><span data-stu-id="6bd53-121">Per DDD patterns, you should encapsulate domain behavior and rules within the entity class itself, so it can control invariants, validations, and rules when accessing any collection.</span></span> <span data-ttu-id="6bd53-122">因此，从 DDD 角度来看，允许公开访问子实体或值对象的集合不是一个好做法。</span><span class="sxs-lookup"><span data-stu-id="6bd53-122">Therefore, it is not a good practice in DDD to allow public access to collections of child entities or value objects.</span></span> <span data-ttu-id="6bd53-123">相反，建议公开用于控制如何及何时更新字段和属性集合的方法，以及这种情况下应发生什么行为和操作的方法。</span><span class="sxs-lookup"><span data-stu-id="6bd53-123">Instead, you want to expose methods that control how and when your fields and property collections can be updated, and what behavior and actions should occur when that happens.</span></span>

<span data-ttu-id="6bd53-124">自 EF Core 1.1 开始，若要满足这些 DDD 要求，可以在实体中包含纯字段，而非公共属性。</span><span class="sxs-lookup"><span data-stu-id="6bd53-124">Since EF Core 1.1, to satisfy those DDD requirements, you can have plain fields in your entities instead of public properties.</span></span> <span data-ttu-id="6bd53-125">如果不希望可从外部访问实体字段，创建特性或字段（而非属性）即可。</span><span class="sxs-lookup"><span data-stu-id="6bd53-125">If you do not want an entity field to be externally accessible, you can just create the attribute or field instead of a property.</span></span> <span data-ttu-id="6bd53-126">还可使用专用属性资源库。</span><span class="sxs-lookup"><span data-stu-id="6bd53-126">You can also use private property setters.</span></span>

<span data-ttu-id="6bd53-127">相同地，现可使用类型化为 `IReadOnlyCollection<T>`（受依赖 EF 实现持久性的实体中集合（如 `List<T>`）的专用字段成员的支持）的公共属性对集合进行只读访问。</span><span class="sxs-lookup"><span data-stu-id="6bd53-127">In a similar way, you can now have read-only access to collections by using a public property typed as  `IReadOnlyCollection<T>`, which is backed by a private field member for the collection (like a `List<T>`) in your entity that relies on EF for persistence.</span></span> <span data-ttu-id="6bd53-128">以前版本的 Entity Framework 需要集合属性来支持 `ICollection<T>`，这意味着任何使用父实体类的开发人员都无法通过其属性集合来添加或删除项。</span><span class="sxs-lookup"><span data-stu-id="6bd53-128">Previous versions of Entity Framework required collection properties to support `ICollection<T>`, which meant that any developer using the parent entity class could add or remove items through its property collections.</span></span> <span data-ttu-id="6bd53-129">这种可能性会违反 DDD 中的建议模式。</span><span class="sxs-lookup"><span data-stu-id="6bd53-129">That possibility would be against the recommended patterns in DDD.</span></span>

<span data-ttu-id="6bd53-130">公开只读 `IReadOnlyCollection<T>` 对象时可使用专用集合，如以下代码示例所示：</span><span class="sxs-lookup"><span data-stu-id="6bd53-130">You can use a private collection while exposing a read-only `IReadOnlyCollection<T>` object, as shown in the following code example:</span></span>

```csharp
public class Order : Entity
{
    // Using private fields, allowed since EF Core 1.1
    private DateTime _orderDate;
    // Other fields ...

    private readonly List<OrderItem> _orderItems; 
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        // Initializations ...
    }

    public void AddOrderItem(int productId, string productName,
                             decimal unitPrice, decimal discount,
                             string pictureUrl, int units = 1)
    {
        // Validation logic...

        var orderItem = new OrderItem(productId, productName, 
                                      unitPrice, discount,
                                      pictureUrl, units);
        _orderItems.Add(orderItem);
    }
}
```

<span data-ttu-id="6bd53-131">请注意，`OrderItems` 属性仅可通过 `IReadOnlyCollection<OrderItem>` 以只读形式进行访问。</span><span class="sxs-lookup"><span data-stu-id="6bd53-131">Note that the `OrderItems` property can only be accessed as read-only using `IReadOnlyCollection<OrderItem>`.</span></span> <span data-ttu-id="6bd53-132">此类型是只读的，因此它免受定期外部更新。</span><span class="sxs-lookup"><span data-stu-id="6bd53-132">This type is read-only so it is protected against regular external updates.</span></span> 

<span data-ttu-id="6bd53-133">EF Core 提供一种方法，可将域模型映射到物理数据库，而不会“污染”域模型。</span><span class="sxs-lookup"><span data-stu-id="6bd53-133">EF Core provides a way to map the domain model to the physical database without "contaminating" the domain model.</span></span> <span data-ttu-id="6bd53-134">这是纯 .NET POCO 代码，因为映射操作在持久性层中实现。</span><span class="sxs-lookup"><span data-stu-id="6bd53-134">It is pure .NET POCO code, because the mapping action is implemented in the persistence layer.</span></span> <span data-ttu-id="6bd53-135">在该映射操作中，需要配置“字段到数据库”映射。</span><span class="sxs-lookup"><span data-stu-id="6bd53-135">In that mapping action, you need to configure the fields-to-database mapping.</span></span> <span data-ttu-id="6bd53-136">在以下 OnModelCreating 方法示例中，突出显示的代码告知 EF Core 通过其字段访问 OrderItems 属性。</span><span class="sxs-lookup"><span data-stu-id="6bd53-136">In the following example of an OnModelCreating method, the highlighted code tells EF Core to access the OrderItems property through its field.</span></span>

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities’ configuration ...
}

// At OrderEntityTypeConfiguration.cs from eShopOnContainers
class OrderEntityTypeConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> orderConfiguration)
    {
        orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);
        // Other configuration

        var navigation = 
              orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));

        //EF access the OrderItem collection property through its backing field
        navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

        // Other configuration
    }
}
```

<span data-ttu-id="6bd53-137">使用字段而非属性时，OrderItem 实体得以持久保存，好似它有一个 List&lt;OrderItem&gt; 属性。</span><span class="sxs-lookup"><span data-stu-id="6bd53-137">When you use fields instead of properties, the OrderItem entity is persisted just as if it had a List&lt;OrderItem&gt; property.</span></span> <span data-ttu-id="6bd53-138">但是，它公开单个访问器 - 用于将新项添加到订单的 `AddOrderItem` 方法。</span><span class="sxs-lookup"><span data-stu-id="6bd53-138">However, it exposes a single accessor, the `AddOrderItem` method for adding new items to the order.</span></span> <span data-ttu-id="6bd53-139">因此，行为和数据绑定在一起，将在使用域模型的任何应用程序代码间保持一致。</span><span class="sxs-lookup"><span data-stu-id="6bd53-139">As a result, behavior and data are tied together and will be consistent throughout any application code that uses the domain model.</span></span>

## <a name="implementing-custom-repositories-with-entity-framework-core"></a><span data-ttu-id="6bd53-140">使用 Entity Framework Core 实现自定义存储库</span><span class="sxs-lookup"><span data-stu-id="6bd53-140">Implementing custom repositories with Entity Framework Core</span></span>

<span data-ttu-id="6bd53-141">在实现级别上，当执行更新时，存储库就是一个具有数据持久性代码的类，由工作单元（EF Core 中的 DBContext）进行协调，如下面的类所示：</span><span class="sxs-lookup"><span data-stu-id="6bd53-141">At the implementation level, a repository is simply a class with data persistence code coordinated by a unit of work (DBContext in EF Core) when performing updates, as shown in the following class:</span></span>

```csharp
// using statements...
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class BuyerRepository : IBuyerRepository
    {
        private readonly OrderingContext _context;
        public IUnitOfWork UnitOfWork
        {
            get
            {
                return _context;
            }
        }

        public BuyerRepository(OrderingContext context)
        {
            _context = context ?? throw new ArgumentNullException(nameof(context));
        }

        public Buyer Add(Buyer buyer)
        {
            return _context.Buyers.Add(buyer).Entity; 
        }

        public async Task<Buyer> FindAsync(string BuyerIdentityGuid)
        {
            var buyer = await _context.Buyers
                .Include(b => b.Payments)
                .Where(b => b.FullName == BuyerIdentityGuid)
                .SingleOrDefaultAsync();

            return buyer;
        }
    }
}
```

<span data-ttu-id="6bd53-142">请注意，IBuyerRepository 接口来自于域模型层（采用协定的形式）。</span><span class="sxs-lookup"><span data-stu-id="6bd53-142">Note that the IBuyerRepository interface comes from the domain model layer as a contract.</span></span> <span data-ttu-id="6bd53-143">但是，存储库在持久性和基础结构层上实现。</span><span class="sxs-lookup"><span data-stu-id="6bd53-143">However, the repository implementation is done at the persistence and infrastructure layer.</span></span>

<span data-ttu-id="6bd53-144">EF DbContext 经由依赖关系注入而通过构造函数。</span><span class="sxs-lookup"><span data-stu-id="6bd53-144">The EF DbContext comes through the constructor through Dependency Injection.</span></span> <span data-ttu-id="6bd53-145">它在同一 HTTP 请求范围内的多个存储库之间进行共享，这要感谢它在 IoC 容器（也可使用 services.AddDbContext&lt;&gt; 进行显式设置）中的默认生存期 (ServiceLifetime.Scoped)。</span><span class="sxs-lookup"><span data-stu-id="6bd53-145">It is shared between multiple repositories within the same HTTP request scope, thanks to its default lifetime (ServiceLifetime.Scoped) in the IoC container (which can also be explicitly set with services.AddDbContext&lt;&gt;).</span></span>

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a><span data-ttu-id="6bd53-146">存储库中的实现方法（更新或事务与查询）</span><span class="sxs-lookup"><span data-stu-id="6bd53-146">Methods to implement in a repository (updates or transactions versus queries)</span></span>

<span data-ttu-id="6bd53-147">每个存储库类中，都应放置持久性方法来更新受其相关聚合约束的实体状态。</span><span class="sxs-lookup"><span data-stu-id="6bd53-147">Within each repository class, you should put the persistence methods that update the state of entities contained by its related aggregate.</span></span> <span data-ttu-id="6bd53-148">请记住，聚合与其相关存储库之间存在一对一关系。</span><span class="sxs-lookup"><span data-stu-id="6bd53-148">Remember there is one-to-one relationship between an aggregate and its related repository.</span></span> <span data-ttu-id="6bd53-149">并考虑到，聚合根实体对象时可能已将其子实体嵌入 EF 图中。</span><span class="sxs-lookup"><span data-stu-id="6bd53-149">Take into account that an aggregate root entity object might have embedded child entities within its EF graph.</span></span> <span data-ttu-id="6bd53-150">例如，购买者可能有作为相关子实体的多个支付方法。</span><span class="sxs-lookup"><span data-stu-id="6bd53-150">For example, a buyer might have multiple payment methods as related child entities.</span></span>

<span data-ttu-id="6bd53-151">由于 eShopOnContainers 中订购微服务的方式也基于 CQS/CQRS，大多数查询不在自定义存储库中实现。</span><span class="sxs-lookup"><span data-stu-id="6bd53-151">Since the approach for the ordering microservice in eShopOnContainers is also based on CQS/CQRS, most of the queries are not implemented in custom repositories.</span></span> <span data-ttu-id="6bd53-152">一般而言，开发人员可以自由地为表示层创建所需查询和联接，而不受聚合、每个聚合的自定义存储库和 DDD 的限制。</span><span class="sxs-lookup"><span data-stu-id="6bd53-152">Developers have the freedom to create the queries and joins they need for the presentation layer without the restrictions imposed by aggregates, custom repositories per aggregate, and DDD in general.</span></span> <span data-ttu-id="6bd53-153">本指南建议的大多数自定义存储库具有多个更新或事务性方法，但只有查询方法需要更新数据。</span><span class="sxs-lookup"><span data-stu-id="6bd53-153">Most of the custom repositories suggested by this guide have several update or transactional methods but just the query methods needed to get data to be updated.</span></span> <span data-ttu-id="6bd53-154">例如，BuyerRepository 存储库实现 FindAsync 方法，因为应用程序需要知道创建订单相关的新买家之前是否存在特定买家。</span><span class="sxs-lookup"><span data-stu-id="6bd53-154">For example, the BuyerRepository repository implements a FindAsync method, because the application needs to know whether a particular buyer exists before creating a new buyer related to the order.</span></span>

<span data-ttu-id="6bd53-155">但是，正如所提及的，使数据发送至表示层或客户端应用的真正查询方法在使用 Dapper 基于灵活查询的 CQRS 查询中得以实现。</span><span class="sxs-lookup"><span data-stu-id="6bd53-155">However, the real query methods to get data to send to the presentation layer or client apps are implemented, as mentioned, in the CQRS queries based on flexible queries using Dapper.</span></span>

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a><span data-ttu-id="6bd53-156">使用自定义存储库与直接使用 EF DbContext</span><span class="sxs-lookup"><span data-stu-id="6bd53-156">Using a custom repository versus using EF DbContext directly</span></span>

<span data-ttu-id="6bd53-157">Entity Framework DbContext 类基于工作单元和存储库模式，且可直接通过代码（如 ASP.NET Core MVC 控制器）进行使用。</span><span class="sxs-lookup"><span data-stu-id="6bd53-157">The Entity Framework DbContext class is based on the Unit of Work and Repository patterns, and can be used directly from your code, such as from an ASP.NET Core MVC controller.</span></span> <span data-ttu-id="6bd53-158">这是可以创建最简单代码的途径，就像在 eShopOnContainers 的 CRUD 目录微服务中。</span><span class="sxs-lookup"><span data-stu-id="6bd53-158">That is the way you can create the simplest code, as in the CRUD catalog microservice in eShopOnContainers.</span></span> <span data-ttu-id="6bd53-159">如果需要尽可能简单的代码，建议直接使用 DbContext 类，就像许多开发人员操作的那样。</span><span class="sxs-lookup"><span data-stu-id="6bd53-159">In cases where you want the simplest code possible, you might want to directly use the DbContext class, as many developers do.</span></span>

<span data-ttu-id="6bd53-160">但是，实现更复杂的微服务或应用程序时，实现自定义存储库将提供以下几个优势。</span><span class="sxs-lookup"><span data-stu-id="6bd53-160">However, implementing custom repositories provides several benefits when implementing more complex microservices or applications.</span></span> <span data-ttu-id="6bd53-161">工作单元和存储库模式旨在封装基础结构持久性层，以便从应用程序和域模型层脱耦。</span><span class="sxs-lookup"><span data-stu-id="6bd53-161">The Unit of Work and Repository patterns are intended to encapsulate the infrastructure persistence layer so it is decoupled from the application and domain model layers.</span></span> <span data-ttu-id="6bd53-162">实现这些模式将促进用于模拟数据库访问的模拟数据库的使用。</span><span class="sxs-lookup"><span data-stu-id="6bd53-162">Implementing these patterns can facilitate the use of mock repositories simulating access to the database.</span></span>

<span data-ttu-id="6bd53-163">图 9-18 中可以看到不使用存储库（直接使用 EF DbContext）与使用存储库（便于模拟那些存储库）之间的差异。</span><span class="sxs-lookup"><span data-stu-id="6bd53-163">In Figure 9-18 you can see the differences between not using repositories (directly using the EF DbContext) versus using repositories which make it easier to mock those repositories.</span></span>

![](./media/image19.png)

<span data-ttu-id="6bd53-164">图 9-18。</span><span class="sxs-lookup"><span data-stu-id="6bd53-164">**Figure 9-18**.</span></span> <span data-ttu-id="6bd53-165">使用自定义存储库与纯 DbContext</span><span class="sxs-lookup"><span data-stu-id="6bd53-165">Using custom repositories versus a plain DbContext</span></span>

<span data-ttu-id="6bd53-166">模拟时有多个备选项。</span><span class="sxs-lookup"><span data-stu-id="6bd53-166">There are multiple alternatives when mocking.</span></span> <span data-ttu-id="6bd53-167">只模拟存储库或模拟整个工作单元。</span><span class="sxs-lookup"><span data-stu-id="6bd53-167">You could mock just repositories or you could mock a whole unit of work.</span></span> <span data-ttu-id="6bd53-168">通常情况下，只模拟存储库就足够了，不需要提取并模拟整个工作单元那般的复杂。</span><span class="sxs-lookup"><span data-stu-id="6bd53-168">Usually mocking just the repositories is enough, and the complexity to abstract and mock a whole unit of work is usually not needed.</span></span>

<span data-ttu-id="6bd53-169">稍后，当我们关注应用程序层时，将看到依赖关系注入在 ASP.NET Core 中的工作方式，以及使用存储库时的实现方式。</span><span class="sxs-lookup"><span data-stu-id="6bd53-169">Later, when we focus on the application layer, you will see how Dependency Injection works in ASP.NET Core and how it is implemented when using repositories.</span></span>

<span data-ttu-id="6bd53-170">简而言之，自定义存储库允许使用不受数据层状态影响的单元测试来更轻松地测试代码。</span><span class="sxs-lookup"><span data-stu-id="6bd53-170">In short, custom repositories allow you to test code more easily with unit tests that are not impacted by the data tier state.</span></span> <span data-ttu-id="6bd53-171">如果运行的测试还通过 Entity Framework 访问实际的数据库，它们不是单元测试而是更为缓慢的集成测试。</span><span class="sxs-lookup"><span data-stu-id="6bd53-171">If you run tests that also access the actual database through the Entity Framework, they are not unit tests but integration tests, which are a lot slower.</span></span>

<span data-ttu-id="6bd53-172">如果直接使用 DbContext，则你的唯一选择是通过单元测试的可预测数据使用内存中 SQL Server 来运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="6bd53-172">If you were using DbContext directly, the only choice you would have would be to run unit tests by using an in-memory SQL Server with predictable data for unit tests.</span></span> <span data-ttu-id="6bd53-173">将不能在存储库级别以相同的方式控制 mock 对象和模拟数据。</span><span class="sxs-lookup"><span data-stu-id="6bd53-173">You would not be able to control mock objects and fake data in the same way at the repository level.</span></span> <span data-ttu-id="6bd53-174">当然，可以始终测试 MVC 控制器。</span><span class="sxs-lookup"><span data-stu-id="6bd53-174">Of course, you could always test the MVC controllers.</span></span>

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="6bd53-175">IoC 容器中的 EF DbContext 和 IUnitOfWork 实例生存期</span><span class="sxs-lookup"><span data-stu-id="6bd53-175">EF DbContext and IUnitOfWork instance lifetime in your IoC container</span></span>

<span data-ttu-id="6bd53-176">DbContext 对象（公开为 IUnitOfWork 对象）可能需要在相同的 HTTP 请求范围内的多个存储库之间共享。</span><span class="sxs-lookup"><span data-stu-id="6bd53-176">The DbContext object (exposed as an IUnitOfWork object) might need to be shared among multiple repositories within the same HTTP request scope.</span></span> <span data-ttu-id="6bd53-177">例如，当正在执行的操作必须处理多个聚合时，或只是因为正在使用多个存储库实例时，就是这种情况。</span><span class="sxs-lookup"><span data-stu-id="6bd53-177">For example, this is true when the operation being executed must deal with multiple aggregates, or simply because you are using multiple repository instances.</span></span> <span data-ttu-id="6bd53-178">务必提到，IUnitOfWork 接口属于域层，而不是 EF Core 类型。</span><span class="sxs-lookup"><span data-stu-id="6bd53-178">It is also important to mention that the IUnitOfWork interface is part of your domain layer, not an EF Core type.</span></span>

<span data-ttu-id="6bd53-179">为此，DbContext 对象的示例须将其服务生存期设置为 ServiceLifetime.Scoped。</span><span class="sxs-lookup"><span data-stu-id="6bd53-179">In order to do that, the instance of the DbContext object has to have its service lifetime set to ServiceLifetime.Scoped.</span></span> <span data-ttu-id="6bd53-180">这是在 IoC 容器中通过 ASP.NET Core Web API 项目中 Startup.cs 文件的 ConfigureServices 方法向 services.AddDbContext 注册 DbContext 时的默认生存期。</span><span class="sxs-lookup"><span data-stu-id="6bd53-180">This is the default lifetime when registering a DbContext with services.AddDbContext in your IoC container from the ConfigureServices method of the Startup.cs file in your ASP.NET Core Web API project.</span></span> <span data-ttu-id="6bd53-181">下面的代码阐释这一点。</span><span class="sxs-lookup"><span data-stu-id="6bd53-181">The following code illustrates this.</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddMvc(options =>
    {
        options.Filters.Add(typeof(HttpGlobalExceptionFilter));
    }).AddControllersAsServices();

    services.AddEntityFrameworkSqlServer()
      .AddDbContext<OrderingContext>(options =>
      {
          options.UseSqlServer(Configuration["ConnectionString"],
                               sqlOptions => sqlOptions.MigrationsAssembly(typeof(Startup).GetTypeInfo().
                                                                                    Assembly.GetName().Name));
      },
      ServiceLifetime.Scoped // Note that Scoped is the default choice
                             // in AddDbContext. It is shown here only for
                             // pedagogic purposes.
      );
}
```

<span data-ttu-id="6bd53-182">不应将 DbContext 实例化模式配置为 ServiceLifetime.Transient 或 ServiceLifetime.Singleton。</span><span class="sxs-lookup"><span data-stu-id="6bd53-182">The DbContext instantiation mode should not be configured as ServiceLifetime.Transient or ServiceLifetime.Singleton.</span></span>

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="6bd53-183">IoC 容器中的存储库实例生存期</span><span class="sxs-lookup"><span data-stu-id="6bd53-183">The repository instance lifetime in your IoC container</span></span>

<span data-ttu-id="6bd53-184">同样地，通常应将存储库生存期设置为范围内（Autofac 中的 InstancePerLifetimeScope）。</span><span class="sxs-lookup"><span data-stu-id="6bd53-184">In a similar way, repository’s lifetime should usually be set as scoped (InstancePerLifetimeScope in Autofac).</span></span> <span data-ttu-id="6bd53-185">也可设置为短暂（Autofac 中的 InstancePerDependency），但使用范围内生存期时服务在内存方面会更有效率。</span><span class="sxs-lookup"><span data-stu-id="6bd53-185">It could also be transient (InstancePerDependency in Autofac), but your service will be more efficient in regards memory when using the scoped lifetime.</span></span>

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

<span data-ttu-id="6bd53-186">请注意，DbContext 设置为范围内 (InstancePerLifetimeScope) 生存期（DBContext 的默认生存期）时，为存储库使用的单一生存期可能导致严重的并发问题。</span><span class="sxs-lookup"><span data-stu-id="6bd53-186">Note that using the singleton lifetime for the repository could cause you serious concurrency problems when your DbContext is set to scoped (InstancePerLifetimeScope) lifetime (the default lifetimes for a DBContext).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="6bd53-187">其他资源</span><span class="sxs-lookup"><span data-stu-id="6bd53-187">Additional resources</span></span>

-   <span data-ttu-id="6bd53-188">**在 ASP.NET MVC 应用程序中实现存储库和工作单元模式**
    [https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span><span class="sxs-lookup"><span data-stu-id="6bd53-188">**Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application**
[*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span></span>

-   <span data-ttu-id="6bd53-189">**Jonathan Allen。Entity Framework、Dapper 和 Chain 中存储库模式的实现策略**
    [*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span><span class="sxs-lookup"><span data-stu-id="6bd53-189">**Jonathan Allen. Implementation Strategies for the Repository Pattern with Entity Framework, Dapper, and Chain**
[*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span></span>

-   <span data-ttu-id="6bd53-190">**Cesar de la Torre。比较 ASP.NET Core IoC 容器服务生存期和 Autofac IoC 容器实例范围**
    [https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span><span class="sxs-lookup"><span data-stu-id="6bd53-190">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span></span>

## <a name="table-mapping"></a><span data-ttu-id="6bd53-191">表映射</span><span class="sxs-lookup"><span data-stu-id="6bd53-191">Table mapping</span></span>

<span data-ttu-id="6bd53-192">表映射标识要从数据库查询并保存到数据库的表数据。</span><span class="sxs-lookup"><span data-stu-id="6bd53-192">Table mapping identifies the table data to be queried from and saved to the database.</span></span> <span data-ttu-id="6bd53-193">前面你已了解如何使用域实体（例如，产品或订单域）来生成相关的数据库架构。</span><span class="sxs-lookup"><span data-stu-id="6bd53-193">Previously you saw how domain entities (for example, a product or order domain) can be used to generate a related database schema.</span></span> <span data-ttu-id="6bd53-194">EF 特别围绕着约定的概念进行设计。</span><span class="sxs-lookup"><span data-stu-id="6bd53-194">EF is strongly designed around the concept of *conventions*.</span></span> <span data-ttu-id="6bd53-195">约定处理“表的名称是什么？”</span><span class="sxs-lookup"><span data-stu-id="6bd53-195">Conventions address questions like “What will the name of a table be?”</span></span> <span data-ttu-id="6bd53-196">或者“什么属性是主键？”这类问题。</span><span class="sxs-lookup"><span data-stu-id="6bd53-196">or “What property is the primary key?”</span></span> <span data-ttu-id="6bd53-197">约定通常基于约定俗成的名称，例如主键通常是一个以 Id 结尾的属性。</span><span class="sxs-lookup"><span data-stu-id="6bd53-197">Conventions are typically based on conventional names—for example, it is typical for the primary key to be a property that ends with Id.</span></span>

<span data-ttu-id="6bd53-198">按照约定，每个实体将设置为映射到具有与公开所派生上下文中实体的 DbSet&lt;TEntity&gt; 属性相同的名称的表中。</span><span class="sxs-lookup"><span data-stu-id="6bd53-198">By convention, each entity will be set up to map to a table with the same name as the DbSet&lt;TEntity&gt; property that exposes the entity on the derived context.</span></span> <span data-ttu-id="6bd53-199">如果给定实体未提供任何 DbSet&lt;TEntity&gt; 值，则使用类名称。</span><span class="sxs-lookup"><span data-stu-id="6bd53-199">If no DbSet&lt;TEntity&gt; value is provided for the given entity, the class name is used.</span></span>

### <a name="data-annotations-versus-fluent-api"></a><span data-ttu-id="6bd53-200">数据注释与 Fluent API</span><span class="sxs-lookup"><span data-stu-id="6bd53-200">Data Annotations versus Fluent API</span></span>

<span data-ttu-id="6bd53-201">存在许多其他 EF Core 约定，其中大多数可通过使用数据注释或 Fluent API 进行更改，并且在 OnModelCreating 方法内实现。</span><span class="sxs-lookup"><span data-stu-id="6bd53-201">There are many additional EF Core conventions, and most of them can be changed by using either data annotations or Fluent API, implemented within the OnModelCreating method.</span></span>

<span data-ttu-id="6bd53-202">数据注释必须在实体模型类自身上使用，从 DDD 观点来看实体模型类更具侵入性。</span><span class="sxs-lookup"><span data-stu-id="6bd53-202">Data annotations must be used on the entity model classes themselves, which is a more intrusive way from a DDD point of view.</span></span> <span data-ttu-id="6bd53-203">这是因为你会因与基础结构数据库相关的数据注释而污染模型。</span><span class="sxs-lookup"><span data-stu-id="6bd53-203">This is because you are contaminating your model with data annotations related to the infrastructure database.</span></span> <span data-ttu-id="6bd53-204">另一方面，Fluent API 可方便地更改数据持久性基础结构层中大部分的约定和映射，因此实体模型将保持整洁且从持久性基础结构分离。</span><span class="sxs-lookup"><span data-stu-id="6bd53-204">On the other hand, Fluent API is a convenient way to change most conventions and mappings within your data persistence infrastructure layer, so the entity model will be clean and decoupled from the persistence infrastructure.</span></span>

### <a name="fluent-api-and-the-onmodelcreating-method"></a><span data-ttu-id="6bd53-205">Fluent API 和 OnModelCreating 方法</span><span class="sxs-lookup"><span data-stu-id="6bd53-205">Fluent API and the OnModelCreating method</span></span>

<span data-ttu-id="6bd53-206">如前文所述，为了更改约定和映射，可以使用 DbContext 类中的 OnModelCreating 方法。</span><span class="sxs-lookup"><span data-stu-id="6bd53-206">As mentioned, in order to change conventions and mappings, you can use the OnModelCreating method in the DbContext class.</span></span> 

<span data-ttu-id="6bd53-207">eShopOnContainers 中的订购微服务根据需要实现显式映射和配置，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="6bd53-207">The ordering microservice in eShopOnContainers implements explicit mapping and configuration, when needed, as shown in the following code.</span></span>

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities’ configuration ...
}

// At OrderEntityTypeConfiguration.cs from eShopOnContainers
class OrderEntityTypeConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> orderConfiguration)
    {
            orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);

            orderConfiguration.HasKey(o => o.Id);

            orderConfiguration.Ignore(b => b.DomainEvents);

            orderConfiguration.Property(o => o.Id)
                .ForSqlServerUseSequenceHiLo("orderseq", OrderingContext.DEFAULT_SCHEMA);

            //Address Value Object persisted as owned entity type supported since EF Core 2.0
            orderConfiguration.OwnsOne(o => o.Address);

            orderConfiguration.Property<DateTime>("OrderDate").IsRequired();
            orderConfiguration.Property<int?>("BuyerId").IsRequired(false);
            orderConfiguration.Property<int>("OrderStatusId").IsRequired();
            orderConfiguration.Property<int?>("PaymentMethodId").IsRequired(false);
            orderConfiguration.Property<string>("Description").IsRequired(false);

            var navigation = orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));
            
            // DDD Patterns comment:
            //Set as field (New since EF 1.1) to access the OrderItem collection property through its field
            navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

            orderConfiguration.HasOne<PaymentMethod>()
                .WithMany()
                .HasForeignKey("PaymentMethodId")
                .IsRequired(false)
                .OnDelete(DeleteBehavior.Restrict);

            orderConfiguration.HasOne<Buyer>()
                .WithMany()
                .IsRequired(false)
                .HasForeignKey("BuyerId");

            orderConfiguration.HasOne(o => o.OrderStatus)
                .WithMany()
                .HasForeignKey("OrderStatusId");
    }
}
```

<span data-ttu-id="6bd53-208">可以设置同一 OnModelCreating 方法内的所有 Fluent API 映射，但最好是将该代码进行分区并得到多个配置类，每个实体一个，如示例中所示。</span><span class="sxs-lookup"><span data-stu-id="6bd53-208">You could set all the Fluent API mappings within the same OnModelCreating method, but it is advisable to partition that code and have multiple configuration classes, one per entity, as shown in the example.</span></span> <span data-ttu-id="6bd53-209">尤其是对于特别大的模型，最好有单独的配置类用于配置不同的实体类型。</span><span class="sxs-lookup"><span data-stu-id="6bd53-209">Especially for particularly large models, it is advisable to have separate configuration classes for configuring different entity types.</span></span>

<span data-ttu-id="6bd53-210">示例中的代码演示了几个显式声明和映射。</span><span class="sxs-lookup"><span data-stu-id="6bd53-210">The code in the example shows a few explicit declarations and mapping.</span></span> <span data-ttu-id="6bd53-211">但是，EF Core 约定自动执行这里的许多映射，因此示例中需要的实际代码可能较小。</span><span class="sxs-lookup"><span data-stu-id="6bd53-211">However, EF Core conventions do many of those mappings automatically, so the actual code you would need in your case might be smaller.</span></span>


### <a name="the-hilo-algorithm-in-ef-core"></a><span data-ttu-id="6bd53-212">EF Core 中的 Hi/Lo 算法</span><span class="sxs-lookup"><span data-stu-id="6bd53-212">The Hi/Lo algorithm in EF Core</span></span>

<span data-ttu-id="6bd53-213">前面示例中代码的一个有趣方面是，它使用 [Hi/Lo 算法](https://vladmihalcea.com/the-hilo-algorithm/)作为键生成策略。</span><span class="sxs-lookup"><span data-stu-id="6bd53-213">An interesting aspect of code in the preceding example is that it uses the [Hi/Lo algorithm](https://vladmihalcea.com/the-hilo-algorithm/) as the key generation strategy.</span></span>

<span data-ttu-id="6bd53-214">当需要唯一键时，Hi/Lo 算法很有用。</span><span class="sxs-lookup"><span data-stu-id="6bd53-214">The Hi/Lo algorithm is useful when you need unique keys.</span></span> <span data-ttu-id="6bd53-215">总之，Hi-Lo 算法将唯一标识符分配给表行，同时不依赖于立即将行存储于数据库中。</span><span class="sxs-lookup"><span data-stu-id="6bd53-215">As a summary, the Hi-Lo algorithm assigns unique identifiers to table rows while not depending on storing the row in the database immediately.</span></span> <span data-ttu-id="6bd53-216">这使你立即开始使用标识符，就像常规顺序数据库 ID 中的那般。</span><span class="sxs-lookup"><span data-stu-id="6bd53-216">This lets you start using the identifiers right away, as happens with regular sequential database IDs.</span></span>

<span data-ttu-id="6bd53-217">Hi/Lo 算法描述一种机制，用于生成客户端上而不是数据库中的安全 ID。</span><span class="sxs-lookup"><span data-stu-id="6bd53-217">The Hi/Lo algorithm describes a mechanism for generating safe IDs on the client side rather than in the database.</span></span> <span data-ttu-id="6bd53-218">这里所说的“安全”是指没有冲突。</span><span class="sxs-lookup"><span data-stu-id="6bd53-218">*Safe* in this context means without collisions.</span></span> <span data-ttu-id="6bd53-219">出于这些原因，此算法很有趣：</span><span class="sxs-lookup"><span data-stu-id="6bd53-219">This algorithm is interesting for these reasons:</span></span>

-   <span data-ttu-id="6bd53-220">它不中断工作单元模式。</span><span class="sxs-lookup"><span data-stu-id="6bd53-220">It does not break the Unit of Work pattern.</span></span>

-   <span data-ttu-id="6bd53-221">它不需要序列生成器在其他 DBMS 中执行操作的那种往返方式。</span><span class="sxs-lookup"><span data-stu-id="6bd53-221">It does not require round trips the way sequence generators do in other DBMSs.</span></span>

-   <span data-ttu-id="6bd53-222">它生成一个人工可读标识符，不同于使用 GUID 的技术。</span><span class="sxs-lookup"><span data-stu-id="6bd53-222">It generates a human readable identifier, unlike techniques that use GUIDs.</span></span>

<span data-ttu-id="6bd53-223">EF Core 支持使用 ForSqlServerUseSequenceHiLo 方法的 [HiLo](https://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm)，如前面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="6bd53-223">EF Core supports [HiLo](https://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) with the ForSqlServerUseSequenceHiLo method, as shown in the preceding example.</span></span>

### <a name="mapping-fields-instead-of-properties"></a><span data-ttu-id="6bd53-224">映射字段（而非属性）</span><span class="sxs-lookup"><span data-stu-id="6bd53-224">Mapping fields instead of properties</span></span>

<span data-ttu-id="6bd53-225">使用此功能（自 EF Core 1.1 之后可用），可以直接将列映射到字段。</span><span class="sxs-lookup"><span data-stu-id="6bd53-225">With this feature, available since EF Core 1.1, you can directly map columns to fields.</span></span> <span data-ttu-id="6bd53-226">可以不在实体类中使用属性，而只是将列从表格映射到字段。</span><span class="sxs-lookup"><span data-stu-id="6bd53-226">It is possible to not use properties in the entity class, and just to map columns from a table to fields.</span></span> <span data-ttu-id="6bd53-227">它的常见用法是那些无需从实体外进行访问的任意内部状态的专用字段。</span><span class="sxs-lookup"><span data-stu-id="6bd53-227">A common use for that would be private fields for any internal state that do not need to be accessed from outside the entity.</span></span> 

<span data-ttu-id="6bd53-228">可以使用单个字段或集合来执行此操作，如 `List<>` 字段。</span><span class="sxs-lookup"><span data-stu-id="6bd53-228">You can do this with single fields or also with collections, like a `List<>` field.</span></span> <span data-ttu-id="6bd53-229">我们前面讨论对域模型类进行建模时已提过这点，但此处你可以了解如何通过前述代码中强调的 `PropertyAccessMode.Field` 配置来执行该映射。</span><span class="sxs-lookup"><span data-stu-id="6bd53-229">This point was mentioned earlier when we discussed modeling the domain model classes, but here you can see how that mapping is performed with the `PropertyAccessMode.Field` configuration highlighted in the previous code.</span></span>

### <a name="using-shadow-properties-in-ef-core-hidden-at-the-infrastructure-level"></a><span data-ttu-id="6bd53-230">在 EF Core 中使用隐藏在基础结构级别的阴影属性</span><span class="sxs-lookup"><span data-stu-id="6bd53-230">Using shadow properties in EF Core, hidden at the infrastructure level</span></span>

<span data-ttu-id="6bd53-231">EF Core 中的阴影属性是不存于实体类模型中的属性。</span><span class="sxs-lookup"><span data-stu-id="6bd53-231">Shadow properties in EF Core are properties that do not exist in your entity class model.</span></span> <span data-ttu-id="6bd53-232">这些属性的值和状态完全在基础结构级别于 [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) 类中进行维护。</span><span class="sxs-lookup"><span data-stu-id="6bd53-232">The values and states of these properties are maintained purely in the [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) class at the infrastructure level.</span></span>


## <a name="implementing-the-specification-pattern"></a><span data-ttu-id="6bd53-233">实现规范模式</span><span class="sxs-lookup"><span data-stu-id="6bd53-233">Implementing the Specification pattern</span></span>

<span data-ttu-id="6bd53-234">如设计部分前面所介绍的，规范模式（其全名是查询规范模式）是域驱动设计模式，用作可放置含可选排序和分页逻辑的查询定义的位置。</span><span class="sxs-lookup"><span data-stu-id="6bd53-234">As introduced earlier in the design section, the Specification pattern (its full name would be Query-specification pattern) is a Domain-Driven Design pattern designed as the place where you can put the definition of a query with optional sorting and paging logic.</span></span> <span data-ttu-id="6bd53-235">规范模式定义对象中的查询。</span><span class="sxs-lookup"><span data-stu-id="6bd53-235">The Specification pattern defines a query in an object.</span></span> <span data-ttu-id="6bd53-236">例如，为了封装搜索某些产品的分页查询，可以创建采用必要输入参数（pageNumber、pageSize、filter 等）的 PagedProduct 规范。</span><span class="sxs-lookup"><span data-stu-id="6bd53-236">For example, in order to encapsulate a paged query that searches for some products you can create a PagedProduct specification that takes the necessary input parameters (pageNumber, pageSize, filter, etc.).</span></span> <span data-ttu-id="6bd53-237">继而，任何存储库的方法（通常为 List() 重载）将接受 ISpecification 并基于该规范运行预期的查询。</span><span class="sxs-lookup"><span data-stu-id="6bd53-237">Then, any Repository’s method (usually a List() overload) would accept an ISpecification and run the expected query based on that specification.</span></span>

<span data-ttu-id="6bd53-238">常规规范接口示例如下面的 [eShopOnweb](https://github.com/dotnet-architecture/eShopOnWeb) 的代码。</span><span class="sxs-lookup"><span data-stu-id="6bd53-238">An example of a generic Specification interface is the following code from [eShopOnweb](https://github.com/dotnet-architecture/eShopOnWeb).</span></span> 

```csharp
// GENERIC SPECIFICATION INTERFACE
// https://github.com/dotnet-architecture/eShopOnWeb 

public interface ISpecification<T>
{
    Expression<Func<T, bool>> Criteria { get; }
    List<Expression<Func<T, object>>> Includes { get; }
    List<string> IncludeStrings { get; }
}
```

<span data-ttu-id="6bd53-239">然后，常规规范基类的实现如下所示。</span><span class="sxs-lookup"><span data-stu-id="6bd53-239">Then, the implementation of a generic specification base class is the following.</span></span>

```csharp
// GENERIC SPECIFICATION IMPLEMENTATION (BASE CLASS)
// https://github.com/dotnet-architecture/eShopOnWeb
 
public abstract class BaseSpecification<T> : ISpecification<T>
{
    public BaseSpecification(Expression<Func<T, bool>> criteria)
    {
        Criteria = criteria;
    }
    public Expression<Func<T, bool>> Criteria { get; }

    public List<Expression<Func<T, object>>> Includes { get; } = 
                                           new List<Expression<Func<T, object>>>();

    public List<string> IncludeStrings { get; } = new List<string>();
 
    protected virtual void AddInclude(Expression<Func<T, object>> includeExpression)
    {
        Includes.Add(includeExpression);
    }
    
    // string-based includes allow for including children of children
    // e.g. Basket.Items.Product
    protected virtual void AddInclude(string includeString)
    {
        IncludeStrings.Add(includeString);
    }
}
```

<span data-ttu-id="6bd53-240">以下规范在给定购物篮 ID 或购物篮所属买家的 ID 情况下来加载单个购物篮实体。</span><span class="sxs-lookup"><span data-stu-id="6bd53-240">The following specification loads a single basket entity given either the basket’s ID or the ID of the buyer to whom the basket belongs.</span></span> <span data-ttu-id="6bd53-241">它将[立即加载](https://docs.microsoft.com/en-us/ef/core/querying/related-data)购物篮的项集合。</span><span class="sxs-lookup"><span data-stu-id="6bd53-241">It will [eager load](https://docs.microsoft.com/en-us/ef/core/querying/related-data) the basket’s Items collection.</span></span>

```csharp
// SAMPLE QUERY SPECIFICATION IMPLEMENTATION

public class BasketWithItemsSpecification : BaseSpecification<Basket>
{
    public BasketWithItemsSpecification(int basketId)
        : base(b => b.Id == basketId)
    {
        AddInclude(b => b.Items);
    }
    public BasketWithItemsSpecification(string buyerId)
        : base(b => b.BuyerId == buyerId)
    {
        AddInclude(b => b.Items);
    }
}
```

<span data-ttu-id="6bd53-242">最后，可以在下方看到常规 EF 存储库可以如何使用此类规范来筛选并立即加载与给定实体类型 T 相关的数据。</span><span class="sxs-lookup"><span data-stu-id="6bd53-242">And finally, you can see below how a generic EF Repository can use such a specification to filter and eager-load data related to a given entity type T.</span></span>

```csharp
// GENERIC EF REPOSITORY WITH SPECIFICATION
// https://github.com/dotnet-architecture/eShopOnWeb

public IEnumerable<T> List(ISpecification<T> spec)
{
    // fetch a Queryable that includes all expression-based includes
    var queryableResultWithIncludes = spec.Includes
        .Aggregate(_dbContext.Set<T>().AsQueryable(),
            (current, include) => current.Include(include));
 
    // modify the IQueryable to include any string-based include statements
    var secondaryResult = spec.IncludeStrings
        .Aggregate(queryableResultWithIncludes,
            (current, include) => current.Include(include));
 
    // return the result of the query using the specification's criteria expression
    return secondaryResult
                    .Where(spec.Criteria)
                    .AsEnumerable();
}
```
<span data-ttu-id="6bd53-243">除了封装筛选逻辑，该规范还可指定要返回的数据的形状，包括要填充的属性。</span><span class="sxs-lookup"><span data-stu-id="6bd53-243">In addition to encapsulating filtering logic, the specification can specify the shape of the data to be returned, including which properties to populate.</span></span> 

<span data-ttu-id="6bd53-244">尽管我们不建议从存储库返回 IQueryable，但可以在存储库中使用它们来建立一系列结果。</span><span class="sxs-lookup"><span data-stu-id="6bd53-244">Although we don't recommended to return IQueryable from a repository, it’s perfectly fine to use them within the repository to build up a set of results.</span></span> <span data-ttu-id="6bd53-245">可以看到此方法在以上 List 方法中使用，List 方法使用中间 IQueryable 表达式来生成查询的包含内容列表，然后再使用最后一行上的规范条件来执行查询。</span><span class="sxs-lookup"><span data-stu-id="6bd53-245">You can see this approach used in the List method above, which uses intermediate IQueryable expressions to build up the query’s list of includes before executing the query with the specification’s criteria on the last line.</span></span>


#### <a name="additional-resources"></a><span data-ttu-id="6bd53-246">其他资源</span><span class="sxs-lookup"><span data-stu-id="6bd53-246">Additional resources</span></span>

-   <span data-ttu-id="6bd53-247">**表映射**
    [https://docs.microsoft.com/ef/core/modeling/relational/tables](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span><span class="sxs-lookup"><span data-stu-id="6bd53-247">**Table Mapping**
[*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span></span>

-   <span data-ttu-id="6bd53-248">**使用 HiLo 通过 Entity Framework Core 生成关键值**
    [http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span><span class="sxs-lookup"><span data-stu-id="6bd53-248">**Use HiLo to generate keys with Entity Framework Core**
[*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span></span>

-   <span data-ttu-id="6bd53-249">**支持字段**
    [https://docs.microsoft.com/ef/core/modeling/backing-field](https://docs.microsoft.com/ef/core/modeling/backing-field)</span><span class="sxs-lookup"><span data-stu-id="6bd53-249">**Backing Fields**
[*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span></span>

-   <span data-ttu-id="6bd53-250">**Steve Smith.Entity Framework Core 中已封装的集合**
    [https://ardalis.com/encapsulated-collections-in-entity-framework-core](https://ardalis.com/encapsulated-collections-in-entity-framework-core)</span><span class="sxs-lookup"><span data-stu-id="6bd53-250">**Steve Smith. Encapsulated Collections in Entity Framework Core**
[*https://ardalis.com/encapsulated-collections-in-entity-framework-core*](https://ardalis.com/encapsulated-collections-in-entity-framework-core)</span></span>

-   <span data-ttu-id="6bd53-251">**阴影属性**
    [https://docs.microsoft.com/ef/core/modeling/shadow-properties](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="6bd53-251">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>

-   <span data-ttu-id="6bd53-252">**规范模式**
    [http://deviq.com/specification-pattern/](http://deviq.com/specification-pattern/)</span><span class="sxs-lookup"><span data-stu-id="6bd53-252">**The Specification pattern**
[*http://deviq.com/specification-pattern/*](http://deviq.com/specification-pattern/)</span></span>
    

>[!div class="step-by-step"]
<span data-ttu-id="6bd53-253">[上一页](infrastructure-persistence-layer-design.md)
[下一页](nosql-database-persistence-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="6bd53-253">[Previous](infrastructure-persistence-layer-design.md)
[Next](nosql-database-persistence-infrastructure.md)</span></span>
