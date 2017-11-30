---
title: "实现与实体框架核心基础结构持久性层"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |实现与实体框架核心基础结构持久性层"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 508d60d73eb7c0f0cc2cc909613cc4f8712b4aba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-infrastructure-persistence-layer-with-entity-framework-core"></a><span data-ttu-id="5d8b7-104">实现与实体框架核心基础结构持久性层</span><span class="sxs-lookup"><span data-stu-id="5d8b7-104">Implementing the infrastructure persistence layer with Entity Framework Core</span></span>

<span data-ttu-id="5d8b7-105">当使用 SQL Server、 Oracle 或 PostgreSQL 如关系数据库时，推荐的方法是实现基于 Entity Framework (EF) 上的持久性层。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-105">When you use relational databases such as SQL Server, Oracle, or PostgreSQL, a recommended approach is to implement the persistence layer based on Entity Framework (EF).</span></span> <span data-ttu-id="5d8b7-106">EF 支持 LINQ，并为您的模型，并插入您的数据库简化的持久性提供强类型化的对象。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-106">EF supports LINQ and provides strongly typed objects for your model, as well as simplified persistence into your database.</span></span>

<span data-ttu-id="5d8b7-107">实体框架已有多年历史作为.NET Framework 的一部分。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-107">Entity Framework has a long history as part of the .NET Framework.</span></span> <span data-ttu-id="5d8b7-108">当你使用.NET 核心时，你还应使用实体框架核心，在 Windows 或 Linux 运行.NET 核心的方式相同。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-108">When you use .NET Core, you should also use Entity Framework Core, which runs on Windows or Linux in the same way as .NET Core.</span></span> <span data-ttu-id="5d8b7-109">EF 核心是实体框架中，使用小得多的占用量和性能的重要改进实施的完全重写。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-109">EF Core is a complete rewrite of Entity Framework, implemented with a much smaller footprint and important improvements in performance.</span></span>

## <a name="introduction-to-entity-framework-core"></a><span data-ttu-id="5d8b7-110">实体框架核心简介</span><span class="sxs-lookup"><span data-stu-id="5d8b7-110">Introduction to Entity Framework Core</span></span>

<span data-ttu-id="5d8b7-111">实体框架 (EF) 核心是一种轻型，可扩展的并跨平台版本的受欢迎的实体框架数据访问技术。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-111">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="5d8b7-112">它引入了.NET 核心中旬 2016年中。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-112">It was introduced with .NET Core in mid-2016.</span></span>

<span data-ttu-id="5d8b7-113">由于已在 Microsoft 文档中可用的简介 EF 核心，此处我们只需提供该信息的链接。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-113">Since an introduction to EF Core is already available in Microsoft documentation, here we simply provide links to that information.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="5d8b7-114">其他资源</span><span class="sxs-lookup"><span data-stu-id="5d8b7-114">Additional resources</span></span>

-   <span data-ttu-id="5d8b7-115">**实体框架核心**
    [*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span><span class="sxs-lookup"><span data-stu-id="5d8b7-115">**Entity Framework Core**
[*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span></span>

-   <span data-ttu-id="5d8b7-116">**开始使用 ASP.NET Core 和使用 Visual Studio 的实体框架核心**
    [*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span><span class="sxs-lookup"><span data-stu-id="5d8b7-116">**Getting started with ASP.NET Core and Entity Framework Core using Visual Studio**
[*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span></span>

-   <span data-ttu-id="5d8b7-117">**DbContext 类**
    [*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span><span class="sxs-lookup"><span data-stu-id="5d8b7-117">**DbContext Class**
[*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span></span>

-   <span data-ttu-id="5d8b7-118">**比较 EF 核心和 EF6.x**
    [*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span><span class="sxs-lookup"><span data-stu-id="5d8b7-118">**Compare EF Core & EF6.x**
[*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span></span>

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a><span data-ttu-id="5d8b7-119">在实体框架核心中从 DDD 角度来看的基础结构</span><span class="sxs-lookup"><span data-stu-id="5d8b7-119">Infrastructure in Entity Framework Core from a DDD perspective</span></span>

<span data-ttu-id="5d8b7-120">从 DDD 的角度来看，EF 的一个重要功能是能够使用 POCO 域实体，也称为在 EF 术语中作为 POCO*代码的第一个实体*。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-120">From a DDD point of view, an important capability of EF is the ability to use POCO domain entities, also known in EF terminology as POCO *code-first entities*.</span></span> <span data-ttu-id="5d8b7-121">如果使用域的 POCO 实体，你的域模型类将持久性未知，以下[持久性无感知](http://deviq.com/persistence-ignorance/)和[基础结构无知](https://ayende.com/blog/3137/infrastructure-ignorance)原则。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-121">If you use POCO domain entities, your domain model classes are persistence-ignorant, following the [Persistence Ignorance](http://deviq.com/persistence-ignorance/) and the [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance) principles.</span></span>

<span data-ttu-id="5d8b7-122">DDD 模式每应封装域行为和规则的实体类本身，以便访问任何集合时，它可以控制固定协定、 验证和规则。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-122">Per DDD patterns, you should encapsulate domain behavior and rules within the entity class itself, so it can control invariants, validations, and rules when accessing any collection.</span></span> <span data-ttu-id="5d8b7-123">因此，它不是子的很好的做法，DDD，以允许到集合的公共访问实体或值对象中。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-123">Therefore, it is not a good practice in DDD to allow public access to collections of child entities or value objects.</span></span> <span data-ttu-id="5d8b7-124">相反，你想要公开方法，用于控制如何及何时可以更新字段和属性集合，以及行为和操作应发生在这种情况。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-124">Instead, you want to expose methods that control how and when your fields and property collections can be updated, and what behavior and actions should occur when that happens.</span></span>

<span data-ttu-id="5d8b7-125">在 EF 核心 1.1，以满足这些 DDD 要求你可以有纯字段实体而不是使用公钥和私钥 setter 的属性中。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-125">In EF Core 1.1, to satisfy those DDD requirements you can have plain fields in your entities instead of properties with public and private setters.</span></span> <span data-ttu-id="5d8b7-126">如果您不希望实体字段是从外部访问，你仅可以创建的属性或字段而不是一个属性。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-126">If you do not want an entity field to be externally accessible, you can just create the attribute or field instead of a property.</span></span> <span data-ttu-id="5d8b7-127">没有无需使用私有 setter，如果你愿意此简洁方法。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-127">There is no need to use private setters if you prefer this cleaner approach.</span></span>

<span data-ttu-id="5d8b7-128">以类似的方式，你现在可以对集合的只读访问通过使用类型为 IEnumerable 的公共属性&lt;T&gt;，进行备份找不到的私有字段成员 (如列表&lt;&gt;) 在你依赖于 EF 提供持久性的实体。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-128">In a similar way, you can now have read-only access to collections by using a public property typed as IEnumerable&lt;T&gt;, which is backed by a private field member for the collection (like a List&lt;&gt;) in your entity that relies on EF for persistence.</span></span> <span data-ttu-id="5d8b7-129">以前版本的实体框架所需的集合属性，以支持 ICollection&lt;T&gt;，这意味着任何开发人员使用父实体类无法添加或删除其属性集合中的项。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-129">Previous versions of Entity Framework required collection properties to support ICollection&lt;T&gt;, which meant that any developer using the parent entity class could add or remove items from its property collections.</span></span> <span data-ttu-id="5d8b7-130">这种可能性将会违反 DDD 中的建议模式。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-130">That possibility would be against the recommended patterns in DDD.</span></span>

<span data-ttu-id="5d8b7-131">可以使用专用的集合，同时公开只读 IEnumerable 对象，如下面的代码示例中所示：</span><span class="sxs-lookup"><span data-stu-id="5d8b7-131">You can use a private collection while exposing a read-only IEnumerable object, as shown in the following code example:</span></span>

```csharp
public class Order : Entity
{
    // Using private fields, allowed since EF Core 1.1
    private DateTime _orderDate;
    // Other fields ...
    private readonly List<OrderItem> _orderItems;

    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();

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
        var orderItem = new OrderItem(productId, productName, unitPrice, discount,
            pictureUrl, units);
        _orderItems.Add(orderItem);
    }
}
```

<span data-ttu-id="5d8b7-132">请注意以只读方式使用列表仅可访问 OrderItems 属性&lt;&gt;。AsReadOnly()。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-132">Note that the OrderItems property can only be accessed as read-only using List&lt;&gt;.AsReadOnly().</span></span> <span data-ttu-id="5d8b7-133">此方法创建专用的列表的只读包装，以便它不会受到外部更新。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-133">This method creates a read-only wrapper around the private list so that it is protected against external updates.</span></span> <span data-ttu-id="5d8b7-134">这是比使用 ToList 方法中，更廉价的因为它没有要复制新的集合; 中的所有项相反，它执行包装实例的只是一个堆分配操作。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-134">It is much cheaper than using the ToList method, because it does not have to copy all the items in a new collection; instead, it performs just one heap alloc operation for the wrapper instance.</span></span>

<span data-ttu-id="5d8b7-135">EF 核心使您能够将域模型映射到物理数据库，而不出现影响域模型。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-135">EF Core provides a way to map the domain model to the physical database without contaminating the domain model.</span></span> <span data-ttu-id="5d8b7-136">这是纯 POCO.NET 代码，因为在持久性层中实现的映射操作。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-136">It is pure .NET POCO code, because the mapping action is implemented in the persistence layer.</span></span> <span data-ttu-id="5d8b7-137">在该映射操作，你需要配置到数据库字段映射。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-137">In that mapping action, you need to configure the fields-to-database mapping.</span></span> <span data-ttu-id="5d8b7-138">在 OnModelCreating 方法的以下示例中，突出显示的代码指示 EF 核心以通过其字段访问 OrderItems 属性。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-138">In the following example of an OnModelCreating method, the highlighted code tells EF Core to access the OrderItems property through its field.</span></span>

```csharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    // ...
    modelBuilder.Entity<Order>(ConfigureOrder);
    // Other entities ...
}

void ConfigureOrder(EntityTypeBuilder<Order> orderConfiguration)
{
    // Other configuration ...
    var navigation = orderConfiguration.Metadata.
    FindNavigation(nameof(Order.OrderItems));
    navigation.SetPropertyAccessMode(PropertyAccessMode.Field);
    // Other configuration ...
}
```

<span data-ttu-id="5d8b7-139">就像它具有一个列表，当你使用字段而不是属性时，保留 OrderItem 实体&lt;OrderItem&gt;属性。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-139">When you use fields instead of properties, the OrderItem entity is persisted just as if it had a List&lt;OrderItem&gt; property.</span></span> <span data-ttu-id="5d8b7-140">但是，它公开单个访问器 （AddOrderItem 方法） 以便将新项添加到订单。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-140">However, it exposes a single accessor (the AddOrderItem method) for adding new items to the order.</span></span> <span data-ttu-id="5d8b7-141">因此，行为和数据绑定在一起，将在使用域模型中的任何应用程序代码保持一致。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-141">As a result, behavior and data are tied together and will be consistent throughout any application code that uses the domain model.</span></span>

## <a name="implementing-custom-repositories-with-entity-framework-core"></a><span data-ttu-id="5d8b7-142">实现与实体框架核心的自定义存储库</span><span class="sxs-lookup"><span data-stu-id="5d8b7-142">Implementing custom repositories with Entity Framework Core</span></span>

<span data-ttu-id="5d8b7-143">在实现级别中，存储库是只需具有协调工作 (DBContext 在 EF 核心中) 的工作单元的数据持久性代码的类时执行更新，如下面的类中所示：</span><span class="sxs-lookup"><span data-stu-id="5d8b7-143">At the implementation level, a repository is simply a class with data persistence code coordinated by a unit of work (DBContext in EF Core) when performing updates, as shown in the following class:</span></span>

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
    }

    public BuyerRepository(OrderingContext context)
    {
        if (context == null)
        {
            throw new ArgumentNullException(
                nameof(context));
        }
        _context = context;
    }

    public Buyer Add(Buyer buyer)
    {
        return _context.Buyers.Add(buyer).Entity;
    }

    public async Task<Buyer> FindAsync(string BuyerIdentityGuid)
    {
        var buyer = await _context.Buyers.Include(b => b.Payments)
            .Where(b => b.FullName == BuyerIdentityGuid)
            .SingleOrDefaultAsync();
        return buyer;
    }
}
```

<span data-ttu-id="5d8b7-144">请注意 IBuyerRepository 接口来自域模型层。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-144">Note that the IBuyerRepository interface comes from the domain model layer.</span></span> <span data-ttu-id="5d8b7-145">但是，存储库实现可在持久性和基础结构层。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-145">However, the repository implementation is done at the persistence and infrastructure layer.</span></span>

<span data-ttu-id="5d8b7-146">EF DbContext 来自通过依赖关系注入通过构造函数。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-146">The EF DbContext comes through the constructor through Dependency Injection.</span></span> <span data-ttu-id="5d8b7-147">在相同 HTTP 请求范围内，感谢 IoC 容器 （这也可以显式设置与服务在其默认生存时间 (ServiceLifetime.Scoped) 多个存储库之间共享。AddDbContext&lt;&gt;)。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-147">It is shared between multiple repositories within the same HTTP request scope, thanks to its default lifetime (ServiceLifetime.Scoped) in the IoC container (which can also be explicitly set with services.AddDbContext&lt;&gt;).</span></span>

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a><span data-ttu-id="5d8b7-148">方法来实现在存储库 （更新或与查询的事务）</span><span class="sxs-lookup"><span data-stu-id="5d8b7-148">Methods to implement in a repository (updates or transactions versus queries)</span></span>

<span data-ttu-id="5d8b7-149">在每个存储库类，则应将更新其相关聚合所包含的实体的状态的持久性方法。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-149">Within each repository class, you should put the persistence methods that update the state of entities contained by its related aggregate.</span></span> <span data-ttu-id="5d8b7-150">请记住聚合和其相关的存储库之间的一对一关系。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-150">Remember there is one-to-one relationship between an aggregate and its related repository.</span></span> <span data-ttu-id="5d8b7-151">考虑到的聚合根实体对象时可能会嵌入了其 EF 图中的子实体。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-151">Take into account that an aggregate root entity object might have embedded child entities within its EF graph.</span></span> <span data-ttu-id="5d8b7-152">例如，购买者可能会有多个支付方法相关的子实体。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-152">For example, a buyer might have multiple payment methods as related child entities.</span></span>

<span data-ttu-id="5d8b7-153">由于在 eShopOnContainers 排序微服务构成的方法还基于 CQS/CQRS，自定义存储库中未实现的大多数查询。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-153">Since the approach for the ordering microservice in eShopOnContainers is also based on CQS/CQRS, most of the queries are not implemented in custom repositories.</span></span> <span data-ttu-id="5d8b7-154">开发人员也可以自由创建查询和联接而一般情况下施加聚合，每个聚合和 DDD 的自定义存储库的限制不需要的表示层。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-154">Developers have the freedom to create the queries and joins they need for the presentation layer without the restrictions imposed by aggregates, custom repositories per aggregate, and DDD in general.</span></span> <span data-ttu-id="5d8b7-155">本指南建议的自定义存储库的大多数都有多个更新或事务的方法，但只需查询方法需要以获取要更新的数据。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-155">Most of the custom repositories suggested by this guide have several update or transactional methods but just the query methods needed to get data to be updated.</span></span> <span data-ttu-id="5d8b7-156">例如，BuyerRepository 存储库实现 FindAsync 方法，因为应用程序需要知道在创建新的购买者订单相关之前是否存在特定购买者。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-156">For example, the BuyerRepository repository implements a FindAsync method, because the application needs to know whether a particular buyer exists before creating a new buyer related to the order.</span></span>

<span data-ttu-id="5d8b7-157">但是，若要获取要发送到演示文稿层或客户端应用程序数据实际查询方法来实现时中, 所述，使用 Dapper 的灵活查询所基于的 CQRS 查询。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-157">However, the real query methods to get data to send to the presentation layer or client apps are implemented, as mentioned, in the CQRS queries based on flexible queries using Dapper.</span></span>

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a><span data-ttu-id="5d8b7-158">使用与直接使用 EF DbContext 的自定义存储库</span><span class="sxs-lookup"><span data-stu-id="5d8b7-158">Using a custom repository versus using EF DbContext directly</span></span>

<span data-ttu-id="5d8b7-159">实体框架 DbContext 类基于单元的工作和存储库模式中，并可以是直接在代码中使用，如从 ASP.NET 核心 MVC 控制器。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-159">The Entity Framework DbContext class is based on the Unit of Work and Repository patterns, and can be used directly from your code, such as from an ASP.NET Core MVC controller.</span></span> <span data-ttu-id="5d8b7-160">它是方法可以创建的最简单的代码，如下所示在 eShopOnContainers CRUD 目录微服务。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-160">That is the way you can create the simplest code, as in the CRUD catalog microservice in eShopOnContainers.</span></span> <span data-ttu-id="5d8b7-161">在其中所需的最简单的代码可能的情况下，你可能想要直接使用 DbContext 类中，许多开发人员一样。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-161">In cases where you want the simplest code possible, you might want to directly use the DbContext class, as many developers do.</span></span>

<span data-ttu-id="5d8b7-162">但是，实现自定义存储库提供以下几个好处时实现更复杂的微服务或应用程序。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-162">However, implementing custom repositories provides several benefits when implementing more complex microservices or applications.</span></span> <span data-ttu-id="5d8b7-163">工作单元和存储库模式旨在封装基础结构持久性层，以便从应用程序和域模型层相互脱耦。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-163">The Unit of Work and Repository patterns are intended to encapsulate the infrastructure persistence layer so it is decoupled from the application and domain model layers.</span></span> <span data-ttu-id="5d8b7-164">实现这些模式可以方便使用模拟的存储库模拟对数据库的访问。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-164">Implementing these patterns can facilitate the use of mock repositories simulating access to the database.</span></span>

<span data-ttu-id="5d8b7-165">图 9-18 中可以看到不使用存储库 （直接使用 EF DbContext） 之间的差异，而不是使用更加轻松地模拟这些存储库存储库。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-165">In Figure 9-18 you can see the differences between not using repositories (directly using the EF DbContext) versus using repositories which make it easier to mock those repositories.</span></span>

![](./media/image19.png)

<span data-ttu-id="5d8b7-166">**图 9-18**。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-166">**Figure 9-18**.</span></span> <span data-ttu-id="5d8b7-167">使用与纯 DbContext 的自定义存储库</span><span class="sxs-lookup"><span data-stu-id="5d8b7-167">Using custom repositories versus a plain DbContext</span></span>

<span data-ttu-id="5d8b7-168">有多个备选模拟。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-168">There are multiple alternatives when mocking.</span></span> <span data-ttu-id="5d8b7-169">无法模拟只是存储库或无法模拟整个工作单元。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-169">You could mock just repositories or you could mock a whole unit of work.</span></span> <span data-ttu-id="5d8b7-170">通常模拟只需的存储库就足够了，并将复杂性抽象的模拟整个工作单元通常不需要。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-170">Usually mocking just the repositories is enough, and the complexity to abstract and mock a whole unit of work is usually not needed.</span></span>

<span data-ttu-id="5d8b7-171">更高版本，当我们重点放在应用程序层，你将看到在 ASP.NET 核心依赖关系注入工作原理以及如何实现使用存储库时。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-171">Later, when we focus on the application layer, you will see how Dependency Injection works in ASP.NET Core and how it is implemented when using repositories.</span></span>

<span data-ttu-id="5d8b7-172">简单地说，自定义存储库，可以具有不受影响的数据层状态的单元测试更轻松地测试代码。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-172">In short, custom repositories allow you to test code more easily with unit tests that are not impacted by the data tier state.</span></span> <span data-ttu-id="5d8b7-173">如果在运行测试，还通过实体框架访问实际的数据库，它们不是单元测试而很多慢的集成测试。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-173">If you run tests that also access the actual database through the Entity Framework, they are not unit tests but integration tests, which are a lot slower.</span></span>

<span data-ttu-id="5d8b7-174">如果中直接使用 DbContext，你必须是唯一选择是通过使用 SQL Server 的内存中具有可预测的数据单元测试运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-174">If you were using DbContext directly, the only choice you would have would be to run unit tests by using an in-memory SQL Server with predictable data for unit tests.</span></span> <span data-ttu-id="5d8b7-175">你将不能在存储库级别相同的方式控制 mock 对象和假数据。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-175">You would not be able to control mock objects and fake data in the same way at the repository level.</span></span> <span data-ttu-id="5d8b7-176">当然，你无法始终测试 MVC 控制器。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-176">Of course, you could always test the MVC controllers.</span></span>

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="5d8b7-177">EF DbContext 和 IUnitOfWork IoC 容器中的实例生存期</span><span class="sxs-lookup"><span data-stu-id="5d8b7-177">EF DbContext and IUnitOfWork instance lifetime in your IoC container</span></span>

<span data-ttu-id="5d8b7-178">（公开为 IUnitOfWork 对象） 的 DbContext 对象可能需要在相同的 HTTP 请求范围内的多个存储库之间共享。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-178">The DbContext object (exposed as an IUnitOfWork object) might need to be shared among multiple repositories within the same HTTP request scope.</span></span> <span data-ttu-id="5d8b7-179">例如，这是 true，当正在执行该操作必须处理与多个聚合，或只是因为您正在使用多个存储库实例。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-179">For example, this is true when the operation being executed must deal with multiple aggregates, or simply because you are using multiple repository instances.</span></span> <span data-ttu-id="5d8b7-180">务必还需要提到 IUnitOfWork 接口属于域，不 EF 类型。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-180">It is also important to mention that the IUnitOfWork interface is part of the domain, not an EF type.</span></span>

<span data-ttu-id="5d8b7-181">为此，必须拥有服务生存期设置为 ServiceLifetime.Scoped DbContext 对象的实例。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-181">In order to do that, the instance of the DbContext object has to have its service lifetime set to ServiceLifetime.Scoped.</span></span> <span data-ttu-id="5d8b7-182">这是注册使用的 DbContext 服务时的默认生存时间。从 ASP.NET 核心 Web API 项目中的 Startup.cs 文件 ConfigureServices 方法 IoC 容器中的 AddDbContext。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-182">This is the default lifetime when registering a DbContext with services.AddDbContext in your IoC container from the ConfigureServices method of the Startup.cs file in your ASP.NET Core Web API project.</span></span> <span data-ttu-id="5d8b7-183">下面的代码阐释这一点。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-183">The following code illustrates this.</span></span>

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
        sqlop => sqlop.MigrationsAssembly(typeof(Startup).GetTypeInfo().
        Assembly.GetName().Name));
    },
    ServiceLifetime.Scoped // Note that Scoped is the default choice
    // in AddDbContext. It is shown here only for
    // pedagogic purposes.
    );
}
```

<span data-ttu-id="5d8b7-184">不应为 ServiceLifetime.Transient 或 ServiceLifetime.Singleton 配置 DbContext 实例化模式。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-184">The DbContext instantiation mode should not be configured as ServiceLifetime.Transient or ServiceLifetime.Singleton.</span></span>

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="5d8b7-185">IoC 容器中存储库实例生存期</span><span class="sxs-lookup"><span data-stu-id="5d8b7-185">The repository instance lifetime in your IoC container</span></span>

<span data-ttu-id="5d8b7-186">类似地，在存储库的生存期通常应设置为指定了作用域 (InstancePerLifetimeScope Autofac 中)。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-186">In a similar way, repository’s lifetime should usually be set as scoped (InstancePerLifetimeScope in Autofac).</span></span> <span data-ttu-id="5d8b7-187">这也可能是暂时性 (InstancePerDependency Autofac 中)，但你的服务将会更高效方面内存中，使用指定了作用域的生存期时。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-187">It could also be transient (InstancePerDependency in Autofac), but your service will be more efficient in regards memory when using the scoped lifetime.</span></span>

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

<span data-ttu-id="5d8b7-188">请注意，为存储库使用的单一实例生存期可能导致严重的并发问题时你 DbContext 设置为作用域 (InstancePerLifetimeScope) 生存期 （创建的 DBContext 的默认生存期）。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-188">Note that using the singleton lifetime for the repository could cause you serious concurrency problems when your DbContext is set to scoped (InstancePerLifetimeScope) lifetime (the default lifetimes for a DBContext).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="5d8b7-189">其他资源</span><span class="sxs-lookup"><span data-stu-id="5d8b7-189">Additional resources</span></span>

-   <span data-ttu-id="5d8b7-190">**在 ASP.NET MVC 应用程序中实现的存储库和单元的工作模式**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span><span class="sxs-lookup"><span data-stu-id="5d8b7-190">**Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application**
[*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span></span>

-   <span data-ttu-id="5d8b7-191">**Jonathan Allen。存储库中的实现策略模式使用实体框架，Dapper，并且链接**
    [*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span><span class="sxs-lookup"><span data-stu-id="5d8b7-191">**Jonathan Allen. Implementation Strategies for the Repository Pattern with Entity Framework, Dapper, and Chain**
[*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span></span>

-   <span data-ttu-id="5d8b7-192">**Cesar de la Torre。比较具有 Autofac IoC 容器实例作用域的 ASP.NET 核心 IoC 容器服务生命周期**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span><span class="sxs-lookup"><span data-stu-id="5d8b7-192">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span></span>

## <a name="table-mapping"></a><span data-ttu-id="5d8b7-193">表映射</span><span class="sxs-lookup"><span data-stu-id="5d8b7-193">Table mapping</span></span>

<span data-ttu-id="5d8b7-194">表映射标识要从查询的表数据，并保存到数据库。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-194">Table mapping identifies the table data to be queried from and saved to the database.</span></span> <span data-ttu-id="5d8b7-195">前面你已了解如何使用域实体 （例如，产品或顺序域） 来生成相关的数据库架构。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-195">Previously you saw how domain entities (for example, a product or order domain) can be used to generate a related database schema.</span></span> <span data-ttu-id="5d8b7-196">EF 强设计的设计思路*约定*。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-196">EF is strongly designed around the concept of *conventions*.</span></span> <span data-ttu-id="5d8b7-197">此类约定地址问题:"表的名称是什么？"</span><span class="sxs-lookup"><span data-stu-id="5d8b7-197">Conventions address questions like “What will the name of a table be?”</span></span> <span data-ttu-id="5d8b7-198">或者"哪些属性是 primary key？"</span><span class="sxs-lookup"><span data-stu-id="5d8b7-198">or “What property is the primary key?”</span></span> <span data-ttu-id="5d8b7-199">约定通常基于传统名称-例如，它是典型的主键是一个属性，结尾 id。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-199">Conventions are typically based on conventional names—for example, it is typical for the primary key to be a property that ends with Id.</span></span>

<span data-ttu-id="5d8b7-200">按照约定，每个实体将设置为将映射到与 DbSet 同名表&lt;TEntity&gt;公开派生上下文上的该实体的属性。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-200">By convention, each entity will be set up to map to a table with the same name as the DbSet&lt;TEntity&gt; property that exposes the entity on the derived context.</span></span> <span data-ttu-id="5d8b7-201">如果没有 DbSet&lt;TEntity&gt;值是提供对于给定的实体中，使用的类名称。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-201">If no DbSet&lt;TEntity&gt; value is provided for the given entity, the class name is used.</span></span>

### <a name="data-annotations-versus-fluent-api"></a><span data-ttu-id="5d8b7-202">与 Fluent API 的数据批注</span><span class="sxs-lookup"><span data-stu-id="5d8b7-202">Data Annotations versus Fluent API</span></span>

<span data-ttu-id="5d8b7-203">有许多其他 EF 核心约定，并且可以使用数据注释或 Fluent API，在 OnModelCreating 方法内实现更改其中的大多数。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-203">There are many additional EF Core conventions, and most of them can be changed by using either data annotations or Fluent API, implemented within the OnModelCreating method.</span></span>

<span data-ttu-id="5d8b7-204">数据注释必须使用在的实体模型类本身，它是从 DDD 角度来看更具有侵入性方式。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-204">Data annotations must be used on the entity model classes themselves, which is a more intrusive way from a DDD point of view.</span></span> <span data-ttu-id="5d8b7-205">这是因为会出现你的模型影响使用数据注释与基础结构数据库相关。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-205">This is because you are contaminating your model with data annotations related to the infrastructure database.</span></span> <span data-ttu-id="5d8b7-206">另一方面，Fluent API 是一种简便方式更改大多数约定和你的数据持久性基础结构层中映射以实体模型将清理并分离从持久性基础结构。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-206">On the other hand, Fluent API is a convenient way to change most conventions and mappings within your data persistence infrastructure layer, so the entity model will be clean and decoupled from the persistence infrastructure.</span></span>

### <a name="fluent-api-and-the-onmodelcreating-method"></a><span data-ttu-id="5d8b7-207">Fluent API 和 OnModelCreating 方法</span><span class="sxs-lookup"><span data-stu-id="5d8b7-207">Fluent API and the OnModelCreating method</span></span>

<span data-ttu-id="5d8b7-208">如前文所述，为了更改约定和映射，你可以使用 OnModelCreating 方法 DbContext 类中。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-208">As mentioned, in order to change conventions and mappings, you can use the OnModelCreating method in the DbContext class.</span></span> <span data-ttu-id="5d8b7-209">下面的示例演示如何执行此操作中 eShopOnContainers 排序微服务中。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-209">The following example shows how we do this in the ordering microservice in eShopOnContainers.</span></span>

```csharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    //Other entities
    modelBuilder.Entity<OrderStatus>(ConfigureOrderStatus);
    //Other entities
}

void ConfigureOrder(EntityTypeBuilder<Order> orderConfiguration)
{
    orderConfiguration.ToTable("orders", DEFAULT_SCHEMA);
    orderConfiguration.HasKey(o => o.Id);
    orderConfiguration.Property(o => o.Id).ForSqlServerUseSequenceHiLo("orderseq", DEFAULT_SCHEMA);
    orderConfiguration.Property<DateTime>("OrderDate").IsRequired();
    orderConfiguration.Property<string>("Street").IsRequired();
    orderConfiguration.Property<string>("State").IsRequired();
    orderConfiguration.Property<string>("City").IsRequired();
    orderConfiguration.Property<string>("ZipCode").IsRequired();
    orderConfiguration.Property<string>("Country").IsRequired();
    orderConfiguration.Property<int>("BuyerId").IsRequired();
    orderConfiguration.Property<int>("OrderStatusId").IsRequired();
    orderConfiguration.Property<int>("PaymentMethodId").IsRequired();

    var navigation =
    orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));
    // DDD Patterns comment:
    // Set as Field (new since EF 1.1) to access
    // the OrderItem collection property as a field
    navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

    orderConfiguration.HasOne(o => o.PaymentMethod)
        .WithMany()
        .HasForeignKey("PaymentMethodId")
        .OnDelete(DeleteBehavior.Restrict);
        orderConfiguration.HasOne(o => o.Buyer)
        .WithMany()
        .HasForeignKey("BuyerId");
        orderConfiguration.HasOne(o => o.OrderStatus)
        .WithMany()
        .HasForeignKey("OrderStatusId");
}
```

<span data-ttu-id="5d8b7-210">你可以设置的相同的 OnModelCreating 方法内的所有 Fluent API 映射，但最好是分区该代码并且具有多个 submethods，每个实体，一个示例中所示。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-210">You could set all the Fluent API mappings within the same OnModelCreating method, but it is advisable to partition that code and have multiple submethods, one per entity, as shown in the example.</span></span> <span data-ttu-id="5d8b7-211">对于特别大的模型，它甚至可以最好拥有用于配置不同的实体类型单独的源文件 （静态类）。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-211">For particularly large models, it can even be advisable to have separate source files (static classes) for configuring different entity types.</span></span>

<span data-ttu-id="5d8b7-212">示例中的代码是显式的。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-212">The code in the example is explicit.</span></span> <span data-ttu-id="5d8b7-213">但是，EF 核心约定执行大多数的此自动，因此你需要编写实现同一目标的实际代码会是小得多。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-213">However, EF Core conventions do most of this automatically, so the actual code you would need to write to achieve the same thing would be much smaller.</span></span>

### <a name="the-hilo-algorithm-in-ef-core"></a><span data-ttu-id="5d8b7-214">EF 核心中的 Hi/Lo 算法</span><span class="sxs-lookup"><span data-stu-id="5d8b7-214">The Hi/Lo algorithm in EF Core</span></span>

<span data-ttu-id="5d8b7-215">在前面的示例代码的一个有趣方面是它使用[Hi/Lo 算法](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/)作为密钥生成策略。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-215">An interesting aspect of code in the preceding example is that it uses the [Hi/Lo algorithm](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) as the key generation strategy.</span></span>

<span data-ttu-id="5d8b7-216">当你需要唯一键时，Hi/Lo 算法很有用。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-216">The Hi/Lo algorithm is useful when you need unique keys.</span></span> <span data-ttu-id="5d8b7-217">作为摘要，Hi-Lo 算法将唯一标识符时不具体取决于立即存储在数据库中的行分配给表行。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-217">As a summary, the Hi-Lo algorithm assigns unique identifiers to table rows while not depending on storing the row in the database immediately.</span></span> <span data-ttu-id="5d8b7-218">这使你立即开始使用标识符，就像使用常规顺序数据库 Id。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-218">This lets you start using the identifiers right away, as happens with regular sequential database IDs.</span></span>

<span data-ttu-id="5d8b7-219">Hi/Lo 算法描述一种机制，用于生成客户端上而不是数据库中的安全 Id。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-219">The Hi/Lo algorithm describes a mechanism for generating safe IDs on the client side rather than in the database.</span></span> <span data-ttu-id="5d8b7-220">*安全*在此上下文中，意味着不冲突的情况下。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-220">*Safe* in this context means without collisions.</span></span> <span data-ttu-id="5d8b7-221">出于这些原因，此算法很有趣:</span><span class="sxs-lookup"><span data-stu-id="5d8b7-221">This algorithm is interesting for these reasons:</span></span>

-   <span data-ttu-id="5d8b7-222">它不会中断的单元的工作模式。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-222">It does not break the Unit of Work pattern.</span></span>

-   <span data-ttu-id="5d8b7-223">它不需要在其他 Dbms 中执行操作之间的往返方式序列生成器。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-223">It does not require round trips the way sequence generators do in other DBMSs.</span></span>

-   <span data-ttu-id="5d8b7-224">它会生成一个人工可读标识符，与使用的 Guid 的技术。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-224">It generates a human readable identifier, unlike techniques that use GUIDs.</span></span>

<span data-ttu-id="5d8b7-225">EF 核心支持[HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm)使用 ForSqlServerUseSequenceHiLo 方法，如前面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-225">EF Core supports [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) with the ForSqlServerUseSequenceHiLo method, as shown in the preceding example.</span></span>

### <a name="mapping-fields-instead-of-properties"></a><span data-ttu-id="5d8b7-226">而不是属性的映射字段</span><span class="sxs-lookup"><span data-stu-id="5d8b7-226">Mapping fields instead of properties</span></span>

<span data-ttu-id="5d8b7-227">通过将列映射到字段的 EF 核心 1.1 的功能，则可能不在实体类中，使用任何属性，并只是为了映射到字段表中的列。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-227">With the feature of EF Core 1.1 that maps columns to fields, it is possible to not use any properties in the entity class, and just to map columns from a table to fields.</span></span> <span data-ttu-id="5d8b7-228">常见的用于将无需从外部实体进行访问的私有字段的任何内部状态。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-228">A common use for that would be private fields for any internal state that do not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="5d8b7-229">EF 1.1 支持一种方法没有相关的属性的字段映射到数据库中的列。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-229">EF 1.1 supports a way to map a field without a related property to a column in the database.</span></span> <span data-ttu-id="5d8b7-230">你可以执行此操作还与单个字段或集合，如列表&lt;&gt;字段。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-230">You can do this with single fields or also with collections, like a List&lt;&gt; field.</span></span> <span data-ttu-id="5d8b7-231">此点已前面提到，在我们讨论建模的域模型类，但你可以看到如何使用在前面的代码中突出显示 PropertyAccessMode.Field 配置执行该映射。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-231">This point was mentioned earlier when we discussed modeling the domain model classes, but here you can see how that mapping is performed with the PropertyAccessMode.Field configuration highlighted in the previous code.</span></span>

### <a name="using-shadow-properties-in-value-objects-for-hidden-ids-at-the-infrastructure-level"></a><span data-ttu-id="5d8b7-232">使用卷影属性值对象中的隐藏在基础结构级别 Id</span><span class="sxs-lookup"><span data-stu-id="5d8b7-232">Using shadow properties in value objects for hidden IDs at the infrastructure level</span></span>

<span data-ttu-id="5d8b7-233">在 EF 核心中的隐藏属性是实体类模型中不存在的属性。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-233">Shadow properties in EF Core are properties that do not exist in your entity class model.</span></span> <span data-ttu-id="5d8b7-234">值和这些属性的状态进行维护纯粹在[ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker)类在基础结构级别。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-234">The values and states of these properties are maintained purely in the [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) class at the infrastructure level.</span></span>

<span data-ttu-id="5d8b7-235">从 DDD 的角度来看，隐藏属性是一种简便方式实现通过隐藏卷影属性为主键的 ID 值对象。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-235">From a DDD point of view, shadow properties are a convenient way to implement value objects by hiding the ID as a shadow property primary key.</span></span> <span data-ttu-id="5d8b7-236">这很重要，因为值对象不应具有标识 （至少，你不应包含 ID 域模型层中时调整值对象）。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-236">This is important, because a value object should not have identity (at least, you should not have the ID in the domain model layer when shaping value objects).</span></span> <span data-ttu-id="5d8b7-237">这里的要点是，截至 EF 核心最新版本，EF 核心不一定实现值的对象作为一方法[复杂类型](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx)，EF 中尽可能 6.x。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-237">The point here is that as of the current version of EF Core, EF Core does not have a way to implement value objects as [complex types](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), as is possible in EF 6.x.</span></span> <span data-ttu-id="5d8b7-238">正因为如此你当前需要实现将值对象作为具有一个隐藏的 ID （主键） 将设置为卷影属性的实体。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-238">That is why you currently need to implement a value object as an entity with a hidden ID (primary key) set as a shadow property.</span></span>

<span data-ttu-id="5d8b7-239">在中可以看到[地址值对象](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)eShopOnContainers，在地址模型中看不见 ID:</span><span class="sxs-lookup"><span data-stu-id="5d8b7-239">As you can see in the [Address value object](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) in eShopOnContainers, in the Address model you do not see an ID:</span></span>

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }
    //Constructor initializing, etc
}
```

<span data-ttu-id="5d8b7-240">但事实上，我们需要提供一个 ID，以便 EF 核心都能保留此数据库表中的数据。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-240">But under the covers, we need to provide an ID so that EF Core is able to persist this data in the database tables.</span></span> <span data-ttu-id="5d8b7-241">我们执行此操作的 ConfigureAddress 方法中[OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs)类在基础结构级别，因此我们不会污染域模型中的与 EF 基础结构代码。</span><span class="sxs-lookup"><span data-stu-id="5d8b7-241">We do that in the ConfigureAddress method of the [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) class at the infrastructure level, so we do not pollute the domain model with EF infrastructure code.</span></span>

```csharp
void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);
    // DDD pattern comment:
    // Implementing the Address ID as a shadow property, because the
    // address is a value object and an identity is not required for a
    // value object
    // EF Core just needs the ID so it can store it in a database table
    // See: https://docs.microsoft.com/ef/core/modeling/shadow-properties
    addressConfiguration.Property<int>("Id").IsRequired();
    addressConfiguration.HasKey("Id");
}
```

#### <a name="additional-resources"></a><span data-ttu-id="5d8b7-242">其他资源</span><span class="sxs-lookup"><span data-stu-id="5d8b7-242">Additional resources</span></span>

-   <span data-ttu-id="5d8b7-243">**表映射**
    [*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span><span class="sxs-lookup"><span data-stu-id="5d8b7-243">**Table Mapping**
[*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span></span>

-   <span data-ttu-id="5d8b7-244">**HiLo 用于生成密钥与实体框架核心**
    [*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span><span class="sxs-lookup"><span data-stu-id="5d8b7-244">**Use HiLo to generate keys with Entity Framework Core**
[*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span></span>

-   <span data-ttu-id="5d8b7-245">**支持字段**
    [*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span><span class="sxs-lookup"><span data-stu-id="5d8b7-245">**Backing Fields**
[*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span></span>

-   <span data-ttu-id="5d8b7-246">**Steve Smith。封装在实体框架核心集合**
    [*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)</span><span class="sxs-lookup"><span data-stu-id="5d8b7-246">**Steve Smith. Encapsulated Collections in Entity Framework Core**
[*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)</span></span>

-   <span data-ttu-id="5d8b7-247">**隐藏属性**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="5d8b7-247">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="5d8b7-248">[以前](基础结构的持久性-层-design.md) [下一步] (nosql-数据库-持久性-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="5d8b7-248">[Previous] (infrastructure-persistence-layer-design.md) [Next] (nosql-database-persistence-infrastructure.md)</span></span>
