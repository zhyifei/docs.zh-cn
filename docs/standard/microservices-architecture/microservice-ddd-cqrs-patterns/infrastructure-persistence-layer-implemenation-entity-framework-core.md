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
# <a name="implementing-the-infrastructure-persistence-layer-with-entity-framework-core"></a>实现与实体框架核心基础结构持久性层

当使用 SQL Server、 Oracle 或 PostgreSQL 如关系数据库时，推荐的方法是实现基于 Entity Framework (EF) 上的持久性层。 EF 支持 LINQ，并为您的模型，并插入您的数据库简化的持久性提供强类型化的对象。

实体框架已有多年历史作为.NET Framework 的一部分。 当你使用.NET 核心时，你还应使用实体框架核心，在 Windows 或 Linux 运行.NET 核心的方式相同。 EF 核心是实体框架中，使用小得多的占用量和性能的重要改进实施的完全重写。

## <a name="introduction-to-entity-framework-core"></a>实体框架核心简介

实体框架 (EF) 核心是一种轻型，可扩展的并跨平台版本的受欢迎的实体框架数据访问技术。 它引入了.NET 核心中旬 2016年中。

由于已在 Microsoft 文档中可用的简介 EF 核心，此处我们只需提供该信息的链接。

#### <a name="additional-resources"></a>其他资源

-   **实体框架核心**
    [*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)

-   **开始使用 ASP.NET Core 和使用 Visual Studio 的实体框架核心**
    [*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)

-   **DbContext 类**
    [*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)

-   **比较 EF 核心和 EF6.x**
    [*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a>在实体框架核心中从 DDD 角度来看的基础结构

从 DDD 的角度来看，EF 的一个重要功能是能够使用 POCO 域实体，也称为在 EF 术语中作为 POCO*代码的第一个实体*。 如果使用域的 POCO 实体，你的域模型类将持久性未知，以下[持久性无感知](http://deviq.com/persistence-ignorance/)和[基础结构无知](https://ayende.com/blog/3137/infrastructure-ignorance)原则。

DDD 模式每应封装域行为和规则的实体类本身，以便访问任何集合时，它可以控制固定协定、 验证和规则。 因此，它不是子的很好的做法，DDD，以允许到集合的公共访问实体或值对象中。 相反，你想要公开方法，用于控制如何及何时可以更新字段和属性集合，以及行为和操作应发生在这种情况。

在 EF 核心 1.1，以满足这些 DDD 要求你可以有纯字段实体而不是使用公钥和私钥 setter 的属性中。 如果您不希望实体字段是从外部访问，你仅可以创建的属性或字段而不是一个属性。 没有无需使用私有 setter，如果你愿意此简洁方法。

以类似的方式，你现在可以对集合的只读访问通过使用类型为 IEnumerable 的公共属性&lt;T&gt;，进行备份找不到的私有字段成员 (如列表&lt;&gt;) 在你依赖于 EF 提供持久性的实体。 以前版本的实体框架所需的集合属性，以支持 ICollection&lt;T&gt;，这意味着任何开发人员使用父实体类无法添加或删除其属性集合中的项。 这种可能性将会违反 DDD 中的建议模式。

可以使用专用的集合，同时公开只读 IEnumerable 对象，如下面的代码示例中所示：

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

请注意以只读方式使用列表仅可访问 OrderItems 属性&lt;&gt;。AsReadOnly()。 此方法创建专用的列表的只读包装，以便它不会受到外部更新。 这是比使用 ToList 方法中，更廉价的因为它没有要复制新的集合; 中的所有项相反，它执行包装实例的只是一个堆分配操作。

EF 核心使您能够将域模型映射到物理数据库，而不出现影响域模型。 这是纯 POCO.NET 代码，因为在持久性层中实现的映射操作。 在该映射操作，你需要配置到数据库字段映射。 在 OnModelCreating 方法的以下示例中，突出显示的代码指示 EF 核心以通过其字段访问 OrderItems 属性。

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

就像它具有一个列表，当你使用字段而不是属性时，保留 OrderItem 实体&lt;OrderItem&gt;属性。 但是，它公开单个访问器 （AddOrderItem 方法） 以便将新项添加到订单。 因此，行为和数据绑定在一起，将在使用域模型中的任何应用程序代码保持一致。

## <a name="implementing-custom-repositories-with-entity-framework-core"></a>实现与实体框架核心的自定义存储库

在实现级别中，存储库是只需具有协调工作 (DBContext 在 EF 核心中) 的工作单元的数据持久性代码的类时执行更新，如下面的类中所示：

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

请注意 IBuyerRepository 接口来自域模型层。 但是，存储库实现可在持久性和基础结构层。

EF DbContext 来自通过依赖关系注入通过构造函数。 在相同 HTTP 请求范围内，感谢 IoC 容器 （这也可以显式设置与服务在其默认生存时间 (ServiceLifetime.Scoped) 多个存储库之间共享。AddDbContext&lt;&gt;)。

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a>方法来实现在存储库 （更新或与查询的事务）

在每个存储库类，则应将更新其相关聚合所包含的实体的状态的持久性方法。 请记住聚合和其相关的存储库之间的一对一关系。 考虑到的聚合根实体对象时可能会嵌入了其 EF 图中的子实体。 例如，购买者可能会有多个支付方法相关的子实体。

由于在 eShopOnContainers 排序微服务构成的方法还基于 CQS/CQRS，自定义存储库中未实现的大多数查询。 开发人员也可以自由创建查询和联接而一般情况下施加聚合，每个聚合和 DDD 的自定义存储库的限制不需要的表示层。 本指南建议的自定义存储库的大多数都有多个更新或事务的方法，但只需查询方法需要以获取要更新的数据。 例如，BuyerRepository 存储库实现 FindAsync 方法，因为应用程序需要知道在创建新的购买者订单相关之前是否存在特定购买者。

但是，若要获取要发送到演示文稿层或客户端应用程序数据实际查询方法来实现时中, 所述，使用 Dapper 的灵活查询所基于的 CQRS 查询。

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a>使用与直接使用 EF DbContext 的自定义存储库

实体框架 DbContext 类基于单元的工作和存储库模式中，并可以是直接在代码中使用，如从 ASP.NET 核心 MVC 控制器。 它是方法可以创建的最简单的代码，如下所示在 eShopOnContainers CRUD 目录微服务。 在其中所需的最简单的代码可能的情况下，你可能想要直接使用 DbContext 类中，许多开发人员一样。

但是，实现自定义存储库提供以下几个好处时实现更复杂的微服务或应用程序。 工作单元和存储库模式旨在封装基础结构持久性层，以便从应用程序和域模型层相互脱耦。 实现这些模式可以方便使用模拟的存储库模拟对数据库的访问。

图 9-18 中可以看到不使用存储库 （直接使用 EF DbContext） 之间的差异，而不是使用更加轻松地模拟这些存储库存储库。

![](./media/image19.png)

**图 9-18**。 使用与纯 DbContext 的自定义存储库

有多个备选模拟。 无法模拟只是存储库或无法模拟整个工作单元。 通常模拟只需的存储库就足够了，并将复杂性抽象的模拟整个工作单元通常不需要。

更高版本，当我们重点放在应用程序层，你将看到在 ASP.NET 核心依赖关系注入工作原理以及如何实现使用存储库时。

简单地说，自定义存储库，可以具有不受影响的数据层状态的单元测试更轻松地测试代码。 如果在运行测试，还通过实体框架访问实际的数据库，它们不是单元测试而很多慢的集成测试。

如果中直接使用 DbContext，你必须是唯一选择是通过使用 SQL Server 的内存中具有可预测的数据单元测试运行单元测试。 你将不能在存储库级别相同的方式控制 mock 对象和假数据。 当然，你无法始终测试 MVC 控制器。

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a>EF DbContext 和 IUnitOfWork IoC 容器中的实例生存期

（公开为 IUnitOfWork 对象） 的 DbContext 对象可能需要在相同的 HTTP 请求范围内的多个存储库之间共享。 例如，这是 true，当正在执行该操作必须处理与多个聚合，或只是因为您正在使用多个存储库实例。 务必还需要提到 IUnitOfWork 接口属于域，不 EF 类型。

为此，必须拥有服务生存期设置为 ServiceLifetime.Scoped DbContext 对象的实例。 这是注册使用的 DbContext 服务时的默认生存时间。从 ASP.NET 核心 Web API 项目中的 Startup.cs 文件 ConfigureServices 方法 IoC 容器中的 AddDbContext。 下面的代码阐释这一点。

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

不应为 ServiceLifetime.Transient 或 ServiceLifetime.Singleton 配置 DbContext 实例化模式。

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a>IoC 容器中存储库实例生存期

类似地，在存储库的生存期通常应设置为指定了作用域 (InstancePerLifetimeScope Autofac 中)。 这也可能是暂时性 (InstancePerDependency Autofac 中)，但你的服务将会更高效方面内存中，使用指定了作用域的生存期时。

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

请注意，为存储库使用的单一实例生存期可能导致严重的并发问题时你 DbContext 设置为作用域 (InstancePerLifetimeScope) 生存期 （创建的 DBContext 的默认生存期）。

#### <a name="additional-resources"></a>其他资源

-   **在 ASP.NET MVC 应用程序中实现的存储库和单元的工作模式**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)

-   **Jonathan Allen。存储库中的实现策略模式使用实体框架，Dapper，并且链接**
    [*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)

-   **Cesar de la Torre。比较具有 Autofac IoC 容器实例作用域的 ASP.NET 核心 IoC 容器服务生命周期**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)

## <a name="table-mapping"></a>表映射

表映射标识要从查询的表数据，并保存到数据库。 前面你已了解如何使用域实体 （例如，产品或顺序域） 来生成相关的数据库架构。 EF 强设计的设计思路*约定*。 此类约定地址问题:"表的名称是什么？" 或者"哪些属性是 primary key？" 约定通常基于传统名称-例如，它是典型的主键是一个属性，结尾 id。

按照约定，每个实体将设置为将映射到与 DbSet 同名表&lt;TEntity&gt;公开派生上下文上的该实体的属性。 如果没有 DbSet&lt;TEntity&gt;值是提供对于给定的实体中，使用的类名称。

### <a name="data-annotations-versus-fluent-api"></a>与 Fluent API 的数据批注

有许多其他 EF 核心约定，并且可以使用数据注释或 Fluent API，在 OnModelCreating 方法内实现更改其中的大多数。

数据注释必须使用在的实体模型类本身，它是从 DDD 角度来看更具有侵入性方式。 这是因为会出现你的模型影响使用数据注释与基础结构数据库相关。 另一方面，Fluent API 是一种简便方式更改大多数约定和你的数据持久性基础结构层中映射以实体模型将清理并分离从持久性基础结构。

### <a name="fluent-api-and-the-onmodelcreating-method"></a>Fluent API 和 OnModelCreating 方法

如前文所述，为了更改约定和映射，你可以使用 OnModelCreating 方法 DbContext 类中。 下面的示例演示如何执行此操作中 eShopOnContainers 排序微服务中。

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

你可以设置的相同的 OnModelCreating 方法内的所有 Fluent API 映射，但最好是分区该代码并且具有多个 submethods，每个实体，一个示例中所示。 对于特别大的模型，它甚至可以最好拥有用于配置不同的实体类型单独的源文件 （静态类）。

示例中的代码是显式的。 但是，EF 核心约定执行大多数的此自动，因此你需要编写实现同一目标的实际代码会是小得多。

### <a name="the-hilo-algorithm-in-ef-core"></a>EF 核心中的 Hi/Lo 算法

在前面的示例代码的一个有趣方面是它使用[Hi/Lo 算法](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/)作为密钥生成策略。

当你需要唯一键时，Hi/Lo 算法很有用。 作为摘要，Hi-Lo 算法将唯一标识符时不具体取决于立即存储在数据库中的行分配给表行。 这使你立即开始使用标识符，就像使用常规顺序数据库 Id。

Hi/Lo 算法描述一种机制，用于生成客户端上而不是数据库中的安全 Id。 *安全*在此上下文中，意味着不冲突的情况下。 出于这些原因，此算法很有趣:

-   它不会中断的单元的工作模式。

-   它不需要在其他 Dbms 中执行操作之间的往返方式序列生成器。

-   它会生成一个人工可读标识符，与使用的 Guid 的技术。

EF 核心支持[HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm)使用 ForSqlServerUseSequenceHiLo 方法，如前面的示例中所示。

### <a name="mapping-fields-instead-of-properties"></a>而不是属性的映射字段

通过将列映射到字段的 EF 核心 1.1 的功能，则可能不在实体类中，使用任何属性，并只是为了映射到字段表中的列。 常见的用于将无需从外部实体进行访问的私有字段的任何内部状态。

EF 1.1 支持一种方法没有相关的属性的字段映射到数据库中的列。 你可以执行此操作还与单个字段或集合，如列表&lt;&gt;字段。 此点已前面提到，在我们讨论建模的域模型类，但你可以看到如何使用在前面的代码中突出显示 PropertyAccessMode.Field 配置执行该映射。

### <a name="using-shadow-properties-in-value-objects-for-hidden-ids-at-the-infrastructure-level"></a>使用卷影属性值对象中的隐藏在基础结构级别 Id

在 EF 核心中的隐藏属性是实体类模型中不存在的属性。 值和这些属性的状态进行维护纯粹在[ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker)类在基础结构级别。

从 DDD 的角度来看，隐藏属性是一种简便方式实现通过隐藏卷影属性为主键的 ID 值对象。 这很重要，因为值对象不应具有标识 （至少，你不应包含 ID 域模型层中时调整值对象）。 这里的要点是，截至 EF 核心最新版本，EF 核心不一定实现值的对象作为一方法[复杂类型](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx)，EF 中尽可能 6.x。 正因为如此你当前需要实现将值对象作为具有一个隐藏的 ID （主键） 将设置为卷影属性的实体。

在中可以看到[地址值对象](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)eShopOnContainers，在地址模型中看不见 ID:

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

但事实上，我们需要提供一个 ID，以便 EF 核心都能保留此数据库表中的数据。 我们执行此操作的 ConfigureAddress 方法中[OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs)类在基础结构级别，因此我们不会污染域模型中的与 EF 基础结构代码。

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

#### <a name="additional-resources"></a>其他资源

-   **表映射**
    [*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)

-   **HiLo 用于生成密钥与实体框架核心**
    [*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)

-   **支持字段**
    [*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)

-   **Steve Smith。封装在实体框架核心集合**
    [*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)

-   **隐藏属性**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)


>[!div class="step-by-step"]
[以前](基础结构的持久性-层-design.md) [下一步] (nosql-数据库-持久性-infrastructure.md)
