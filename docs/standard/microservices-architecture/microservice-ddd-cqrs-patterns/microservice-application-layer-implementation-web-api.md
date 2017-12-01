---
title: "实现微服务应用程序层使用 Web API"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |实现微服务应用程序层使用 Web API"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: d505a2561ae9b8dee05e803fd639387b63b28b70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-microservice-application-layer-using-the-web-api"></a>实现微服务应用程序层使用 Web API

## <a name="using-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a>使用依赖关系注入将基础结构对象注入到你的应用程序层

如前所述，可以作为构建的如在 Web API 项目或一个 MVC web 应用程序项目的项目的一部分实现的应用程序层。 对于使用 ASP.NET Core 构建 microservice，应用程序层通常将为你的 Web API 库。 如果你想要单独的自定义应用程序层代码中即将推出从 ASP.NET Core （其基础结构以及你的控制器），还可以将你的应用程序层放置在单独的类库，但这是可选。

例如，作为的一部分直接实现排序微服务构成的应用程序层代码**Ordering.API**项目 （ASP.NET 核心 Web API 项目），作为中所示图 9-19。

![](./media/image20.png)

**图 9-19**。 Ordering.API ASP.NET 核心 Web API 项目中的应用程序层

ASP.NET 核心包括一个简单[内置 IoC 容器](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)（由 IServiceProvider 接口） 的支持构造函数注入默认情况下，ASP.NET 使某些服务可通过 DI。 ASP.NET 核心使用术语*服务*有关的所有注册的类型，将通过 DI 注入。 应用程序的启动类中 ConfigureServices 方法中配置内置容器的服务。 依赖项的类型需要的服务在中实现。

通常情况下，你想要将注入实现基础结构对象的依赖关系。 非常典型的依赖关系，以将注入是的存储库。 但你无法将注入可能具有任何其他基础结构依赖项。 对于更简单的实现，你直接无法插入你的单元的工作模式对象 （EF DbContext 对象），因为 DBContext 也是你的基础结构持久性对象的实现。

在下面的示例中，你可以看到如何.NET 核心将注入通过构造函数的所需的存储库对象。 此类是一个命令处理程序，我们将在下一部分中介绍。

```csharp
// Sample command handler
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;

    // Constructor where Dependencies are injected
    public CreateOrderCommandHandler(IOrderRepository orderRepository)
    {
        if (orderRepository == null)
        {
            throw new ArgumentNullException(nameof(orderRepository));
        }
        _orderRepository = orderRepository;
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        //
        // ... Additional code
        //
        // Create the Order AggregateRoot
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State,
            message.Country, message.ZipCode);
        var order = new Order(address, message.CardTypeId, message.CardNumber,
            message.CardSecurityNumber,
            message.CardHolderName,
            message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                item.Discount, item.PictureUrl, item.Units);
        }

        //Persist the Order through the Repository
        _orderRepository.Add(order);
        var result = await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
        return result > 0;
    }
}
```

类使用的插入的存储库来执行事务和保持的状态更改。 它并不重要该类是命令处理程序中，ASP.NET 核心 Web API 控制器方法，还是[DDD 应用程序服务](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/)。 最终的是简单的类，使用存储库、 域实体和其他应用程序协调方式类似于命令处理程序。 依赖关系注入工作原理相同的方式针对所有提到类，如使用 DI 示例所示根据构造函数。

### <a name="registering-the-dependency-implementation-types-and-interfaces-or-abstractions"></a>注册的依赖关系的实现类型和接口或抽象

在使用通过构造函数将插入的对象之前，你需要知道从何处注册的接口和生成注入到通过 DI 你应用程序类的对象的类。 （如 DI 根据构造函数中，如前面所示。）

#### <a name="using-the-built-in-ioc-container-provided-by-aspnet-core"></a>使用 ASP.NET Core 提供内置 IoC 容器

当使用 ASP.NET Core 提供的内置 IoC 容器时，你注册你想要插入 Startup.cs 文件，如以下代码所示的 ConfigureServices 方法中的类型：

```csharp
// Registration of types into ASP.NET Core built-in container
public void ConfigureServices(IServiceCollection services)
{
    // Register out-of-the-box framework services.
    services.AddDbContext<CatalogContext>(c =>
    {
        c.UseSqlServer(Configuration["ConnectionString"]);
    },
    ServiceLifetime.Scoped
    );
    services.AddMvc();
    // Register custom application dependencies.
    services.AddScoped<IMyCustomRepository, MyCustomSQLRepository>();
}
```

最常用的模式时注册 IoC 容器中的类型是注册的成对的类型-一个接口和其相关的实现类。 然后从 IoC 容器可以通过任何构造函数请求一个对象，如果你将请求的接口的某些类型的对象。 例如，在前面的示例中，最后一行说明当您的构造函数的任何依赖 IMyCustomRepository （接口或抽象） 上时，IoC 容器将插入 MyCustomSQLServerRepository 实现实例类。

#### <a name="using-the-scrutor-library-for-automatic-types-registration"></a>使用自动类型注册 Scrutor 库

在使用时 DI.NET 核心，你可能想要能够扫描程序集和自动注册其类型，按照约定。 此功能当前不可用 ASP.NET Core 中。 但是，你可以使用[Scrutor](https://github.com/khellang/Scrutor)为此库。 当具有众多需要在 IoC 容器中注册的类型，此方法非常方便。

#### <a name="additional-resources"></a>其他资源

-   **Matthew 金。服务注册 Scrutor**
    [*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)

<!-- -->

-   **Kristian Hellang。Scrutor。** GitHub 存储库。
    [*https://github.com/khellang/Scrutor*](https://github.com/khellang/Scrutor)

#### <a name="using-autofac-as-an-ioc-container"></a>使用 Autofac 作为 IoC 容器

此外可以使用其他 IoC 容器，然后将其插入 ASP.NET Core 管道，如下所示在 eShopOnContainers，使用排序 microservice [Autofac](https://autofac.org/)。 使用 Autofac 时通常会注册通过模块，它可以通过拆分根据你的类型，就像您可以对分布在多个类库的应用程序类型的多个文件之间的注册类型的类型。

例如，下面是[Autofac 应用程序模块](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs)为[Ordering.API Web API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API)与想要插入的类型的项目。

```csharp
public class ApplicationModule
    :Autofac.Module
{
    public string QueriesConnectionString { get; }
    public ApplicationModule(string qconstr)
    {
        QueriesConnectionString = qconstr;
    }

    protected override void Load(ContainerBuilder builder)
    {
        builder.Register(c => new OrderQueries(QueriesConnectionString))
            .As<IOrderQueries>()
            .InstancePerLifetimeScope();
        builder.RegisterType<BuyerRepository>()
            .As<IBuyerRepository>()
            .InstancePerLifetimeScope();
        builder.RegisterType<OrderRepository>()
            .As<IOrderRepository>()
            .InstancePerLifetimeScope();
        builder.RegisterType<RequestManager>()
            .As<IRequestManager>()
            .InstancePerLifetimeScope();
   }
}
```

注册过程和概念非常类似于您可以使用内置的 ASP.NET Core iOS 容器，注册类型的方式，但使用 Autofac 时的语法是稍有不同。

在示例代码中，以及实现类 OrderRepository 注册 IOrderRepository 的抽象。 这意味着一个构造函数为声明通过 IOrderRepository 抽象或接口的依赖项，每当 IoC 容器将插入 OrderRepository 类的实例。

实例作用域类型确定如何实例共享相同的服务或依赖项的请求之间。 发出请求后的某个依赖项，IoC 容器可以返回以下结果：

-   每个生存期作用域的单个实例 (作为 ASP.NET 核心 IoC 容器中称为*范围*)。

-   每个依赖项的新实例 (作为 ASP.NET 核心 IoC 容器中称为*暂时性*)。

-   在使用 IoC 容器的所有对象之间共享的单一实例 (作为 ASP.NET 核心 IoC 容器中称为*singleton*)。

#### <a name="additional-resources"></a>其他资源

-   **在 ASP.NET 核心中的依赖关系注入简介**
    [*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)

-   **Autofac。** 正式文档。
    [*http://docs.autofac.org/en/latest/*](http://docs.autofac.org/en/latest/)

-   **Cesar de la Torre。比较具有 Autofac IoC 容器实例作用域的 ASP.NET 核心 IoC 容器服务生命周期**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)

## <a name="implementing-the-command-and-command-handler-patterns"></a>实现的命令和命令处理程序模式

在上一节中所示 DI 通过构造函数示例中，通过在类的构造函数的存储库已将注入 IoC 容器。 但是，完全其中已它们注入？ 在简单 Web API (例如，在 eShopOnContainers 目录 microservice) 中，你将它们注入控制器构造函数中的 MVC 控制器级。 但是，在本部分的初始代码 ( [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs)从中 eShopOnContainers Ordering.API 服务的类)，通过特定命令的构造函数完成的依赖关系注入处理程序。 让我们解释什么是命令处理程序是，为什么你想要使用它。

本指南中前面引入了 CQRS 模式本质上与相关命令模式。 CQRS 具有两条边。 第一个领域是使用简化的查询的查询[Dapper](https://github.com/StackExchange/dapper-dot-net)微型 ORM、 以前所述。 第二个区域是命令，为事务的起始点和从外部服务的输入的通道。

如所示图 9-20，基于模式接受从客户端的命令处理，将其基于域模型规则，并最后将保存与事务的状态。

![](./media/image21.png)

**图 9-20**。 命令或 CQRS 模式中的"事务端"的高级视图

### <a name="the-command-class"></a>命令类

命令是让系统执行更改系统的状态的操作的请求。 命令是命令性，，应只需一次处理。

由于命令都是需求，它们通常命名为与在命令性语气 （例如，"创建"或"更新"），谓词，但可能包括的聚合类型，例如 CreateOrderCommand。 与某个事件，不同命令不是从过去; 事实它是仅一个请求，并因此可能被拒绝。

命令可能源自从启动请求，用户由于 UI 或从一个进程管理器时的进程管理器定向聚合执行操作。

命令的重要特征是，它应处理只需一次通过单一接收方。 这是因为某命令是单个操作或你想要在应用程序中执行的事务。 例如，应不超过一次处理相同的顺序创建命令。 这是命令和事件之间的一项重大差异。 事件可能会多次处理，因为许多系统或微服务可能感兴趣的事件。

此外，很重要命令被处理仅一次，以防该命令不是幂等。 如果可以执行它多次而无需更改的结果，该命令的性质，因此或由于系统处理命令的方法，某命令是幂等。

它是一个好办法使命令和更新幂等，建立在你的域的业务规则条件和固定协定的意义上时。 例如，若要使用相同的示例中，如果出于任何原因 （重试逻辑，发起的黑客攻击、 等） 相同的 CreateOrder 命令达到你的系统多次，你应能够标识它，确保你不会创建多个订单。 为此，你需要附加某种类型的操作中标识并确定是否已处理的命令或更新。

将命令发送到一个接收方;不发布命令。 发布为该状态事实集成事件-出发生，可能感兴趣的事件接收器。 对于事件，发布服务器有的无所顾忌哪些情况下，接收方收到事件或它们执行它。 但集成事件是前面部分中已引入另外一回事。

命令是使用包含数据字段或与执行该命令所需的所有信息的集合的类实施的。 命令是一种特殊类型的数据传输对象 (DTO)，一个专门用于请求更改或事务。 命令本身基于完全处理命令，而不安装其他所需的信息。

下面的示例演示简化的 CreateOrderCommand 类。 这是在中 eShopOnContainers 排序微服务中使用一个不可变命令。

```csharp
// DDD and CQRS patterns comment
// Note that it is recommended that yuo implement immutable commands
// In this case, immutability is achieved by having all the setters as private
// plus being able to update the data just once, when creating the object
// through the constructor.
// References on immutable commands:
// http://cqrs.nu/Faq
// https://docs.spine3.org/motivation/immutability.html
// http://blog.gauffin.org/2012/06/griffin-container-introducing-command-support/
// https://msdn.microsoft.com/en-us/library/bb383979.aspx
[DataContract]
public class CreateOrderCommand
    :IAsyncRequest<bool>
{
    [DataMember]
    private readonly List<OrderItemDTO> _orderItems;

    [DataMember]
    public string City { get; private set; }

    [DataMember]
    public string Street { get; private set; }

    [DataMember]
    public string State { get; private set; }

    [DataMember]
    public string Country { get; private set; }

    [DataMember]
    public string ZipCode { get; private set; }

    [DataMember]
    public string CardNumber { get; private set; }

    [DataMember]
    public string CardHolderName { get; private set; }

    [DataMember]
    public DateTime CardExpiration { get; private set; }

    [DataMember]
    public string CardSecurityNumber { get; private set; }

    [DataMember]
    public int CardTypeId { get; private set; }

    [DataMember]
    public IEnumerable<OrderItemDTO> OrderItems => _orderItems;

    public CreateOrderCommand()
    {
        _orderItems = new List<OrderItemDTO>();
    }

    public CreateOrderCommand(List<OrderItemDTO> orderItems, string city,
        string street,
        string state, string country, string zipcode,
        string cardNumber, string cardHolderName, DateTime cardExpiration,
        string cardSecurityNumber, int cardTypeId) : this()
    {
        _orderItems = orderItems;
        City = city;
        Street = street;
        State = state;
        Country = country;
        ZipCode = zipcode;
        CardNumber = cardNumber;
        CardHolderName = cardHolderName;
        CardSecurityNumber = cardSecurityNumber;
        CardTypeId = cardTypeId;
        CardExpiration = cardExpiration;
    }

    public class OrderItemDTO
    {
        public int ProductId { get; set; }
        public string ProductName { get; set; }
        public decimal UnitPrice { get; set; }
        public decimal Discount { get; set; }
        public int Units { get; set; }
        public string PictureUrl { get; set; }
    }
}
```

基本上，命令类包含有关执行业务事务的使用的域模型对象所需的所有数据。 因此，命令是只需包含只读数据和任何行为的数据结构。 命令的名称指示其用途。 在许多语言，如 C\#，命令表示为类，但它们不在实际的面向对象的意义上 true 类。

其他特征，命令将将不可变的因为预期使用情况是，它们直接通过域模型中处理。 它们不需要在其计划的生存期内更改。 在 C 中\#类，可以通过不具有任何 setter 或更改内部状态的其他方法来实现不可变性。

例如，命令类，用于创建顺序是在数据方面可能类似于你想要创建的顺序，但你可能不需要相同的属性。 例如，CreateOrderCommand 没有一个订单 ID，因为尚未创建顺序。

许多命令类可以是简单，需仅需要更改某些状态有关的几个字段。 为这种情况如果您只需更改订单的状态从"进程内"到"付费"或"交付"的使用如下命令：

```csharp
[DataContract]
public class UpdateOrderStatusCommand
    :IAsyncRequest<bool>
{
    [DataMember]
    public string Status { get; private set; }

    [DataMember]
    public string OrderId { get; private set; }

    [DataMember]
    public string BuyerIdentityGuid { get; private set; }
}
```

一些开发人员使其 UI 请求对象独立于其命令 Dto，但这是只首选项。 它是提供不会获得很附加的价值，乏味分离，并且对象几乎完全相同的形状。 例如，在 eShopOnContainers，命令直接来自客户端。

### <a name="the-command-handler-class"></a>命令处理程序类

应实现每个命令的特定命令处理程序类。 这是模式的工作原理，并且你将在其中使用的命令对象、 域对象和基础结构存储库对象。 命令处理程序中的事实是在 CQRS 和 DDD 方面的应用程序层的核心。 但是，所有域逻辑应都包含在域类-聚合根 （根实体） 中子实体或[域服务](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/)，但不是在命令处理程序，它是从应用程序的一个类层。

命令处理程序收到命令，并从使用聚合获取结果。 结果应为此命令成功执行，或者异常。 在出现异常，系统状态应保持不变。

命令处理程序通常将执行以下步骤：

-   它接收命令对象，如 DTO (从[中介](https://en.wikipedia.org/wiki/Mediator_pattern)或其他基础结构对象)。

-   它会验证命令有效 （如果不能验证中介来实现）。

-   它实例化目标的当前命令的聚合根实例。

-   它在命令中获取所需的数据的聚合根实例上执行该方法。

-   它保存到其相关数据库聚合的新状态。 此最后一次操作是实际的事务。

通常情况下，命令处理程序处理单个聚合驱动由其聚合根 （根实体）。 如果多个聚合应受到接收的单个命令，你可以使用域事件通过多个聚合传播状态或操作

重要的一点是处理命令时，所有域逻辑应都为域模型中 （聚合），完全封装并准备好进行单元测试。 命令处理程序就可以充当作为一种方法从数据库中获取域模型和最后一步，以告知基础结构层 （存储库），以便在该模型更改时保留更改。 此方法的优点是可以在独立的、 完全封装的、 丰富的、 行为域模型中的域逻辑重构而无需更改应用程序或基础结构层，它们是联结级别 （命令处理程序，Web API 中的代码存储库、 等）。

当命令处理程序获得复杂，而且具有太多逻辑时，这可能是代码告知。 查看它们，并且如果你发现域逻辑，重构代码以将该域行为移动到的域对象 （聚合根和子实体） 的方法。

作为命令处理程序类的示例，下面的代码演示这一章开头你看到的同一个 CreateOrderCommandHandler 类。 在这种情况下我们具有突出显示的句柄方法和域模型对象/聚合操作。

```csharp
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IBuyerRepository _buyerRepository;
    private readonly IOrderRepository _orderRepository;

    public CreateOrderCommandHandler(IBuyerRepository buyerRepository,
        IOrderRepository orderRepository)
    {
        if (buyerRepository == null)
        {
            throw new ArgumentNullException(nameof(buyerRepository));
        }
        if (orderRepository == null)
        {
            throw new ArgumentNullException(nameof(orderRepository));
        }

        _buyerRepository = buyerRepository;
        _orderRepository = orderRepository;
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        //
        // Additional code ...
        //
        // Create the Order aggregate root
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var order = new Order(buyer.Id, payment.Id,
            new Address(message.Street,
            message.City, message.State,
            message.Country, message.ZipCode));

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                item.Discount, item.PictureUrl, item.Units);
        }

        // Persist the Order through the aggregate's repository
        _orderRepository.Add(order);
        return await _orderRepository.UnitOfWork.SaveChangesAsync();
    }
}
```

这些是命令处理程序应执行的附加步骤：

-   使用命令的数据来操作时使用的聚合根方法和行为。

-   内部域对象中，在引发域事件时执行事务，但这是从命令处理程序的角度来看透明。

-   如果聚合的操作结果是成功并且在完成事务后，引发集成事件命令处理程序。 （这些可能还会出现基础结构的类，如存储库。）

#### <a name="additional-resources"></a>其他资源

-   **标记 Seemann。在边界将应用程序是面向不对象的**
    [*http://blog.ploeh.dk/2011/05/31/AttheBoundaries，ApplicationsareNotObject 面向 /*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)

-   **命令和事件**
    [*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)

-   **命令处理程序的作用是什么？** 
     [ *http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)

-   **Jimmy Bogard。域命令模式 – 处理程序**
    [*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)

-   **Jimmy Bogard。域命令模式 – 验证**
    [*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a>命令处理管道： 如何在触发是命令处理程序

下一个问题是如何调用命令处理程序。 你可以手动调用它从每个相关的 ASP.NET Core 控制器。 但是，方法是将太结合并不理想。

其他两个主要选项，这些建议的选项有：

-   通过内存中中介模式项目。

-   使用控制器和处理程序之间的异步消息队列。

### <a name="using-the-mediator-pattern-in-memory-in-the-command-pipeline"></a>在命令管道中使用中介模式 （内存中）

如所示图 9-21，CQRS 方法在情况下会使用智能中介，类似于内存中总线，这是足够智能，可将重定向到正确的命令处理程序基于命令或 DTO 正在接收的类型。 组件之间的单个黑色箭头表示与他们相关之间的交互 （在许多情况下，通过 DI 插入） 的对象之间的依赖关系。

![](./media/image22.png)

**图 9-21**。 在单个 CQRS 微服务中的过程中使用中介模式

使用中介模式有意义的原因是企业应用程序中处理请求可以变得很复杂。 你想要能够添加打开如日志记录、 验证、 审核和安全的跨领域问题数。 在这些情况下，你可以依赖于中介管道 (请参阅[中介模式](https://en.wikipedia.org/wiki/Mediator_pattern)) 以提供一种为这些额外的行为或跨领域问题。

中介是封装"如何"在此过程中的对象： 它协调基于状态的执行，则调用的方法是命令处理程序，或到处理程序提供的负载。 借助中介组件可以应用跨领域问题集中式和透明的方式通过应用修饰器 (或[管道行为](https://github.com/jbogard/MediatR/wiki/Behaviors)自中介 v3)。 (有关详细信息，请参阅[修饰器模式](https://en.wikipedia.org/wiki/Decorator_pattern)。)

修饰器以及行为都类似于[方面面向编程 (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming)，则只应用于由中介组件的特定进程管道。 根据应用 AOP 实现的跨领域问题的方面*方面 weavers*在编译时将插入的或基于对象调用截获。 这两种典型的 AOP 方法有时称为"类似于"幻数，因为它不是轻松地了解如何 AOP 完成其工作。 在处理的严重问题或 bug，AOP 可能很难调试。 另一方面，这些修饰符/行为是显式和应用仅在中介来实现，上下文中以便能够调试更可预测和轻松。

例如，在排序 microservice eShopOnContainers，我们实现两个示例修饰符， [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs)类和一个[ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs)类。 下一节介绍了修饰器的实现。 请注意，在将来版本中，eShopOnContainers 将迁移到[MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0)并转向[行为](https://github.com/jbogard/MediatR/wiki/Behaviors)而不是使用修饰器。

### <a name="using-message-queues-out-of-proc-in-the-commands-pipeline"></a>在命令的管道中使用消息队列 （进程外）

另一个选项是使用基于代理或消息队列，如图 9-22 中所示的异步消息。 此外可以使用该选项合并与中介组件之前的命令处理程序。

![](./media/image23.png)

**图 9-22**。 通过 CQRS 命令中使用消息队列 （带进程和进程间通信）

使用消息队列接受命令可进一步使变得复杂命令的管道，因为你可能需要此管道拆分为两个进程通过外部消息队列连接。 但是，它应使用如果需要可伸缩性和基于异步消息传送的性能改进。 请考虑对于图 9-22，该控制器只需命令消息发送到队列，并且返回。 然后命令处理程序处理其自己的步调的消息。 它是非常有好处的队列-超可伸缩性是所需，例如对于 stocks 或与大量的传入数据的任何其他方案时，消息队列可充当用例中的缓冲区。

但是，消息队列的异步性质，因此你需要找出如何与客户端应用程序有关的成功或失败的命令的进程进行通信。 一般来说，你应永远不会使用"发后不理"命令。 每个业务应用程序需要知道是否命令已成功处理，或至少验证并且接受。

因此，能够响应客户端在验证已提交至异步队列的命令消息之后将增加你的系统，相比运行事务后返回操作的结果的进程内命令过程的复杂性。 使用队列时，你可能需要返回其他操作结果消息，将需要其他组件和自定义通信系统中通过命令过程的结果。

此外，异步命令是单向的命令，这在许多情况下可能不需要如 Burtsev Alexey 和中的 Greg Young 之间的以下有趣交换中所述[联机会话](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):

\[Burtsev Alexey\]发现的代码的许多人都使用异步命令处理或一种方法而无需任何原因需要这么做消息传递的命令 （它们未执行某些较长的操作，它们未在执行外部异步代码，它们甚至不跨应用程序边界要使用消息总线）。 它们为何引入此不必要的复杂性？ 和实际上，我尚未看到 CQRS 代码示例与目前为止，阻塞命令处理程序，但它将在大多数情况下正常工作。

\[Greg Young\] \[...\]异步命令不存在; 它是实际另一个事件。 如果我必须接受你发送我并引发事件，如果我不同意，它不再你告诉我做些什么。 是你告诉我执行某些操作。 这似乎存在细微的差异，首先，但它有许多含义。

异步命令极大地增加系统的复杂性，因为没有简单方法以指示失败。 因此，异步命令时，建议不要以外的缩放要求需要时或在特殊情况下通信通过消息内部的微服务。 在这些情况下，则必须设计单独的报告和恢复系统故障。

在 eShopOnContainers 的初始版本，我们决定使用同步命令处理，从 HTTP 请求启动，而且受中介模式。 轻松，你能够返回成功或失败的进程，如[CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs)实现。

在任何情况下，这应该是基于你的应用程序的或微服务构成的业务要求的决策。

## <a name="implementing-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a>实现命令过程管道具有中介模式 (MediatR)

作为示例实现，本指南建议使用进程内管道基于驱动器命令引入到中介模式和路由，在内存中，到正确的命令处理程序。 本指南还将建议应用修饰符或[行为](https://github.com/jbogard/MediatR/wiki/Behaviors)以便分隔跨领域问题。

有关在.NET 核心的实现，有一些多个开放源代码库实现中介模式。 本指南中使用的库[MediatR](https://github.com/jbogard/MediatR)开放源代码库 （由 Jimmy Bogard 创建），但你可使用另一种方法。 MediatR 是一个小型和简单的库，您可以像处理处理内存中消息命令，在应用修饰器或行为时。

使用中介模式可帮助你减少耦合并隔离请求工作的情况下，同时自动连接到的处理程序执行该工作的问题 — 在这种情况下，到命令处理程序。

查看本指南时，使用中介模式的另一个好理由已解释的 Jimmy Bogard:

我认为它可能值得一提的是测试此处 – 它提供的很好的一致窗口，你的系统行为。 请求中，响应扩展。我们已找到该方面中一致的方式运行测试的生成非常有价值。

首先，让我们看一下到控制器代码在实际使用的中介对象。 如果你未使用的中介对象，你需要插入的所有依赖项该控制器中，如记录器对象和其他人。 因此，构造函数可能十分复杂。 另一方面，如果你使用中介对象，你的构造函数可以是控制器的很简单，只需少量的依赖项，而不是控制器的你将会获得有一个每个横切操作，如以下示例所示的许多依赖关系：

```csharp
public class OrdersController : Controller
{
    public OrdersController(IMediator mediator,
        IOrderQueries orderQueries)
    // ...
```

你可以看到中介来实现提供的干净且精益 Web API 控制器构造函数。 此外，在控制器方法中，代码将命令发送到中介对象是几乎一个行：

```csharp
[Route("new")]
[HttpPost]
public async Task<IActionResult> CreateOrder([FromBody]CreateOrderCommand
    createOrderCommand)
{
    var commandResult = await _mediator.SendAsync(createOrderCommand);
    return commandResult ? (IActionResult)Ok() : (IActionResult)BadRequest();
}
```

为了使 MediatR 需要注意的你的命令处理程序类，你需要在 IoC 容器中注册的中介类和命令处理程序类。 默认情况下 MediatR 使用 Autofac 作为 IoC 容器中，但你还可以使用内置的 ASP.NET 核心 IoC 容器或 MediatR 支持的任何其他容器。

下面的代码演示如何使用 Autofac 模块时注册中介的类型和命令。

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();
        builder.RegisterAssemblyTypes(typeof(CreateOrderCommand)
            .GetTypeInfo().Assembly)
            .As(o => o.GetInterfaces()
            .Where(i => i.IsClosedTypeOf(typeof(IAsyncRequestHandler<,>)))
            .Select(i => new KeyedService("IAsyncRequestHandler", i)));
        builder.RegisterGenericDecorator(typeof(LogDecorator<,>),
            typeof(IAsyncRequestHandler<,>), "IAsyncRequestHandler");

        // Other types registration
    }
}
```

因为每个命令处理程序实现具有泛型 IAsyncRequestHandler 接口&lt;T&gt; ，然后检查 RegisteredAssemblyTypes 对象，因为该处理程序能够与相关命令与其处理程序，每个命令，关系述 CommandHandler 类，如以下示例所示：

```csharp
public class CreateOrderCommandHandler
  : IAsyncRequestHandler<CreateOrderCommand, bool>
{
```

这是命令处理程序与关联命令的代码。 该处理程序只需简单的类，但它将继承 RequestHandler&lt;T&gt;，和 MediatR 可确保使用正确的负载调用获取它。

## <a name="applying-cross-cutting-concerns-when-processing-commands-with-the-mediator-and-decorator-patterns"></a>在处理具有的中介和修饰器模式命令时应用的跨领域问题

没有一件事情： 无法应用于中介管道的跨领域问题。 你还可以看到 Autofac 注册模块代码的末尾，它如何注册修饰器，具体而言，键入自定义的 LogDecorator 类。

此外，请注意，eShopOnContainers 的未来版本它将迁移到[MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0)并转向[行为](https://github.com/jbogard/MediatR/wiki/Behaviors)而不是使用修饰器。

[LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs)类可以将以下代码，以记录有关正在执行的命令处理程序以及它是否成功与否的信息作为实现。

```csharp
public class LogDecorator<TRequest, TResponse>
    : IAsyncRequestHandler<TRequest, TResponse>
    where TRequest : IAsyncRequest<TResponse>
{
    private readonly IAsyncRequestHandler<TRequest, TResponse> _inner;
    private readonly ILogger<LogDecorator<TRequest, TResponse>> _logger;

    public LogDecorator(
        IAsyncRequestHandler<TRequest, TResponse> inner,
        ILogger<LogDecorator<TRequest, TResponse>> logger)
    {
        _inner = inner;
        _logger = logger;
    }

    public async Task<TResponse> Handle(TRequest message)
    {
        _logger.LogInformation($"Executing command {_inner.GetType().FullName}");
        var response = await _inner.Handle(message);
        _logger.LogInformation($"Succeeded executed command{_inner.GetType().FullName}");
        return response;
    }
}
```

只需通过实现此修饰器类和的修饰与其管道，通过 MediatR 处理的所有命令将日志都记录执行有关的信息。

排序 microservice 也适用的基本的验证，第二个修饰器 eShopOnContainers [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs)依赖于的类[FluentValidation](https://github.com/JeremySkinner/FluentValidation)库，如中所示以下代码：

```csharp
public class ValidatorDecorator<TRequest, TResponse>
    : IAsyncRequestHandler<TRequest, TResponse>
    where TRequest : IAsyncRequest<TResponse>
{
    private readonly IAsyncRequestHandler<TRequest, TResponse> _inner;
    private readonly IValidator<TRequest>[] _validators;

    public ValidatorDecorator(
        IAsyncRequestHandler<TRequest, TResponse> inner,
        IValidator<TRequest>[] validators)
    {
        _inner = inner;
        _validators = validators;
    }

    public async Task<TResponse> Handle(TRequest message)
    {
        var failures = _validators
            .Select(v => v.Validate(message))
            .SelectMany(result => result.Errors)
            .Where(error => error != null)
            .ToList();
            if (failures.Any())
            {
                throw new OrderingDomainException(
                $"Command Validation Errors for type {typeof(TRequest).Name}",
                new ValidationException("Validation exception", failures));
            }
            var response = await _inner.Handle(message);
        return response;
    }
}
```

然后，根据[FluentValidation](https://github.com/JeremySkinner/FluentValidation)库，我们将创建与 CreateOrderCommand，一起传递，如以下代码所示的数据验证：

```csharp
public class CreateOrderCommandValidator : AbstractValidator<CreateOrderCommand>
{
    public CreateOrderCommandValidator()
    {
        RuleFor(command => command.City).NotEmpty();
        RuleFor(command => command.Street).NotEmpty();
        RuleFor(command => command.State).NotEmpty();
        RuleFor(command => command.Country).NotEmpty();
        RuleFor(command => command.ZipCode).NotEmpty();
        RuleFor(command => command.CardNumber).NotEmpty().Length(12, 19);
        RuleFor(command => command.CardHolderName).NotEmpty();
        RuleFor(command => command.CardExpiration).NotEmpty().Must(BeValidExpirationDate).
            WithMessage("Please specify a valid card expiration date");
        RuleFor(command => command.CardSecurityNumber).NotEmpty().Length(3);
        RuleFor(command => command.CardTypeId).NotEmpty();
        RuleFor(command => command.OrderItems).
            Must(ContainOrderItems).WithMessage("No order items found");
    }

    private bool BeValidExpirationDate(DateTime dateTime)
    {
        return dateTime >= DateTime.UtcNow;
    }

    private bool ContainOrderItems(IEnumerable<OrderItemDTO> orderItems)
    {
        return orderItems.Any();
    }
}
```

你可以创建其他验证。 这是实现您命令验证一非常干净且简洁方法。

以类似的方式，可以实现其他方面或你想要应用于命令时处理它们的跨领域问题的其他修饰符。

#### <a name="additional-resources"></a>其他资源

##### <a name="the-mediator-pattern"></a>中介模式

-   **中介模式**
    [*https://en.wikipedia.org/wiki/Mediator\_模式*](https://en.wikipedia.org/wiki/Mediator_pattern)

##### <a name="the-decorator-pattern"></a>修饰器模式

-   **修饰器模式**
    [*https://en.wikipedia.org/wiki/Decorator\_模式*](https://en.wikipedia.org/wiki/Decorator_pattern)

##### <a name="mediatr-jimmy-bogard"></a>MediatR (Jimmy Bogard)

-   **MediatR。** GitHub 存储库。
    [*https://github.com/jbogard/MediatR*](https://github.com/jbogard/MediatR)

-   **使用 MediatR 和 AutoMapper CQRS**
    [*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)

-   **你的控制器置于饮食： 文章和命令。** 
     [ *https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)

-   **有关与中介管道的跨领域问题**
    [*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)

-   **CQRS 和 REST： 完全匹配**
    [*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)

-   **MediatR 管道示例**
    [*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)

-   **垂直切片测试装置，用于 MediatR 和 ASP.NET Core**
    *<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>*

-   **发布的 Microsoft 依赖关系注入 MediatR 扩展**
    [*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)

##### <a name="fluent-validation"></a>Fluent 验证

-   **Jeremy Skinner。FluentValidation。** GitHub 存储库。
    [*https://github.com/JeremySkinner/FluentValidation*](https://github.com/JeremySkinner/FluentValidation)

>[!div class="step-by-step"]
[以前](microservice-application-layer-web-api-design.md) [下一步] (.../implement-resilient-applications/index.md)
