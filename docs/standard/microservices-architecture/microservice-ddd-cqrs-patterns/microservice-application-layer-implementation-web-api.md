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
# <a name="implementing-the-microservice-application-layer-using-the-web-api"></a><span data-ttu-id="3736a-104">实现微服务应用程序层使用 Web API</span><span class="sxs-lookup"><span data-stu-id="3736a-104">Implementing the microservice application layer using the Web API</span></span>

## <a name="using-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a><span data-ttu-id="3736a-105">使用依赖关系注入将基础结构对象注入到你的应用程序层</span><span class="sxs-lookup"><span data-stu-id="3736a-105">Using Dependency Injection to inject infrastructure objects into your application layer</span></span>

<span data-ttu-id="3736a-106">如前所述，可以作为构建的如在 Web API 项目或一个 MVC web 应用程序项目的项目的一部分实现的应用程序层。</span><span class="sxs-lookup"><span data-stu-id="3736a-106">As mentioned previously, the application layer can be implemented as part of the artifact you are building, such as within a Web API project or an MVC web app project.</span></span> <span data-ttu-id="3736a-107">对于使用 ASP.NET Core 构建 microservice，应用程序层通常将为你的 Web API 库。</span><span class="sxs-lookup"><span data-stu-id="3736a-107">In the case of a microservice built with ASP.NET Core, the application layer will usually be your Web API library.</span></span> <span data-ttu-id="3736a-108">如果你想要单独的自定义应用程序层代码中即将推出从 ASP.NET Core （其基础结构以及你的控制器），还可以将你的应用程序层放置在单独的类库，但这是可选。</span><span class="sxs-lookup"><span data-stu-id="3736a-108">If you want to separate what is coming from ASP.NET Core (its infrastructure plus your controllers) from your custom application layer code, you could also place your application layer in a separate class library, but that is optional.</span></span>

<span data-ttu-id="3736a-109">例如，作为的一部分直接实现排序微服务构成的应用程序层代码**Ordering.API**项目 （ASP.NET 核心 Web API 项目），作为中所示图 9-19。</span><span class="sxs-lookup"><span data-stu-id="3736a-109">For instance, the application layer code of the ordering microservice is directly implemented as part of the **Ordering.API** project (an ASP.NET Core Web API project), as shown in Figure 9-19.</span></span>

![](./media/image20.png)

<span data-ttu-id="3736a-110">**图 9-19**。</span><span class="sxs-lookup"><span data-stu-id="3736a-110">**Figure 9-19**.</span></span> <span data-ttu-id="3736a-111">Ordering.API ASP.NET 核心 Web API 项目中的应用程序层</span><span class="sxs-lookup"><span data-stu-id="3736a-111">The application layer in the Ordering.API ASP.NET Core Web API project</span></span>

<span data-ttu-id="3736a-112">ASP.NET 核心包括一个简单[内置 IoC 容器](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)（由 IServiceProvider 接口） 的支持构造函数注入默认情况下，ASP.NET 使某些服务可通过 DI。</span><span class="sxs-lookup"><span data-stu-id="3736a-112">ASP.NET Core includes a simple [built-in IoC container](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (represented by the IServiceProvider interface) that supports constructor injection by default, and ASP.NET makes certain services available through DI.</span></span> <span data-ttu-id="3736a-113">ASP.NET 核心使用术语*服务*有关的所有注册的类型，将通过 DI 注入。</span><span class="sxs-lookup"><span data-stu-id="3736a-113">ASP.NET Core uses the term *service* for any of the types you register that will be injected through DI.</span></span> <span data-ttu-id="3736a-114">应用程序的启动类中 ConfigureServices 方法中配置内置容器的服务。</span><span class="sxs-lookup"><span data-stu-id="3736a-114">You configure the built-in container's services in the ConfigureServices method in your application's Startup class.</span></span> <span data-ttu-id="3736a-115">依赖项的类型需要的服务在中实现。</span><span class="sxs-lookup"><span data-stu-id="3736a-115">Your dependencies are implemented in the services that a type needs.</span></span>

<span data-ttu-id="3736a-116">通常情况下，你想要将注入实现基础结构对象的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="3736a-116">Typically, you want to inject dependencies that implement infrastructure objects.</span></span> <span data-ttu-id="3736a-117">非常典型的依赖关系，以将注入是的存储库。</span><span class="sxs-lookup"><span data-stu-id="3736a-117">A very typical dependency to inject is a repository.</span></span> <span data-ttu-id="3736a-118">但你无法将注入可能具有任何其他基础结构依赖项。</span><span class="sxs-lookup"><span data-stu-id="3736a-118">But you could inject any other infrastructure dependency that you may have.</span></span> <span data-ttu-id="3736a-119">对于更简单的实现，你直接无法插入你的单元的工作模式对象 （EF DbContext 对象），因为 DBContext 也是你的基础结构持久性对象的实现。</span><span class="sxs-lookup"><span data-stu-id="3736a-119">For simpler implementations, you could directly inject your Unit of Work pattern object (the EF DbContext object), because the DBContext is also the implementation of your infrastructure persistence objects.</span></span>

<span data-ttu-id="3736a-120">在下面的示例中，你可以看到如何.NET 核心将注入通过构造函数的所需的存储库对象。</span><span class="sxs-lookup"><span data-stu-id="3736a-120">In the following example, you can see how .NET Core is injecting the required repository objects through the constructor.</span></span> <span data-ttu-id="3736a-121">此类是一个命令处理程序，我们将在下一部分中介绍。</span><span class="sxs-lookup"><span data-stu-id="3736a-121">The class is a command handler, which we will cover in the next section.</span></span>

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

<span data-ttu-id="3736a-122">类使用的插入的存储库来执行事务和保持的状态更改。</span><span class="sxs-lookup"><span data-stu-id="3736a-122">The class uses the injected repositories to execute the transaction and persist the state changes.</span></span> <span data-ttu-id="3736a-123">它并不重要该类是命令处理程序中，ASP.NET 核心 Web API 控制器方法，还是[DDD 应用程序服务](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/)。</span><span class="sxs-lookup"><span data-stu-id="3736a-123">It does not matter whether that class is a command handler, an ASP.NET Core Web API controller method, or a [DDD Application Service](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/).</span></span> <span data-ttu-id="3736a-124">最终的是简单的类，使用存储库、 域实体和其他应用程序协调方式类似于命令处理程序。</span><span class="sxs-lookup"><span data-stu-id="3736a-124">It is ultimately a simple class that uses repositories, domain entities, and other application coordination in a fashion similar to a command handler.</span></span> <span data-ttu-id="3736a-125">依赖关系注入工作原理相同的方式针对所有提到类，如使用 DI 示例所示根据构造函数。</span><span class="sxs-lookup"><span data-stu-id="3736a-125">Dependency Injection works the same way for all the mentioned classes, as in the example using DI based on the constructor.</span></span>

### <a name="registering-the-dependency-implementation-types-and-interfaces-or-abstractions"></a><span data-ttu-id="3736a-126">注册的依赖关系的实现类型和接口或抽象</span><span class="sxs-lookup"><span data-stu-id="3736a-126">Registering the dependency implementation types and interfaces or abstractions</span></span>

<span data-ttu-id="3736a-127">在使用通过构造函数将插入的对象之前，你需要知道从何处注册的接口和生成注入到通过 DI 你应用程序类的对象的类。</span><span class="sxs-lookup"><span data-stu-id="3736a-127">Before you use the objects injected through constructors, you need to know where to register the interfaces and classes that produce the objects injected into your application classes through DI.</span></span> <span data-ttu-id="3736a-128">（如 DI 根据构造函数中，如前面所示。）</span><span class="sxs-lookup"><span data-stu-id="3736a-128">(Like DI based on the constructor, as shown previously.)</span></span>

#### <a name="using-the-built-in-ioc-container-provided-by-aspnet-core"></a><span data-ttu-id="3736a-129">使用 ASP.NET Core 提供内置 IoC 容器</span><span class="sxs-lookup"><span data-stu-id="3736a-129">Using the built-in IoC container provided by ASP.NET Core</span></span>

<span data-ttu-id="3736a-130">当使用 ASP.NET Core 提供的内置 IoC 容器时，你注册你想要插入 Startup.cs 文件，如以下代码所示的 ConfigureServices 方法中的类型：</span><span class="sxs-lookup"><span data-stu-id="3736a-130">When you use the built-in IoC container provided by ASP.NET Core, you register the types you want to inject in the ConfigureServices method in the Startup.cs file, as in the following code:</span></span>

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

<span data-ttu-id="3736a-131">最常用的模式时注册 IoC 容器中的类型是注册的成对的类型-一个接口和其相关的实现类。</span><span class="sxs-lookup"><span data-stu-id="3736a-131">The most common pattern when registering types in an IoC container is to register a pair of types—an interface and its related implementation class.</span></span> <span data-ttu-id="3736a-132">然后从 IoC 容器可以通过任何构造函数请求一个对象，如果你将请求的接口的某些类型的对象。</span><span class="sxs-lookup"><span data-stu-id="3736a-132">Then when you request an object from the IoC container through any constructor, you request an object of a certain type of interface.</span></span> <span data-ttu-id="3736a-133">例如，在前面的示例中，最后一行说明当您的构造函数的任何依赖 IMyCustomRepository （接口或抽象） 上时，IoC 容器将插入 MyCustomSQLServerRepository 实现实例类。</span><span class="sxs-lookup"><span data-stu-id="3736a-133">For instance, in the previous example, the last line states that when any of your constructors have a dependency on IMyCustomRepository (interface or abstraction), the IoC container will inject an instance of the MyCustomSQLServerRepository implementation class.</span></span>

#### <a name="using-the-scrutor-library-for-automatic-types-registration"></a><span data-ttu-id="3736a-134">使用自动类型注册 Scrutor 库</span><span class="sxs-lookup"><span data-stu-id="3736a-134">Using the Scrutor library for automatic types registration</span></span>

<span data-ttu-id="3736a-135">在使用时 DI.NET 核心，你可能想要能够扫描程序集和自动注册其类型，按照约定。</span><span class="sxs-lookup"><span data-stu-id="3736a-135">When using DI in .NET Core, you might want to be able to scan an assembly and automatically register its types by convention.</span></span> <span data-ttu-id="3736a-136">此功能当前不可用 ASP.NET Core 中。</span><span class="sxs-lookup"><span data-stu-id="3736a-136">This feature is not currently available in ASP.NET Core.</span></span> <span data-ttu-id="3736a-137">但是，你可以使用[Scrutor](https://github.com/khellang/Scrutor)为此库。</span><span class="sxs-lookup"><span data-stu-id="3736a-137">However, you can use the [Scrutor](https://github.com/khellang/Scrutor) library for that.</span></span> <span data-ttu-id="3736a-138">当具有众多需要在 IoC 容器中注册的类型，此方法非常方便。</span><span class="sxs-lookup"><span data-stu-id="3736a-138">This approach is convenient when you have dozens of types that need to be registered in your IoC container.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="3736a-139">其他资源</span><span class="sxs-lookup"><span data-stu-id="3736a-139">Additional resources</span></span>

-   <span data-ttu-id="3736a-140">**Matthew 金。服务注册 Scrutor**
    [*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)</span><span class="sxs-lookup"><span data-stu-id="3736a-140">**Matthew King. Registering services with Scrutor**
[*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)</span></span>

<!-- -->

-   <span data-ttu-id="3736a-141">**Kristian Hellang。Scrutor。**</span><span class="sxs-lookup"><span data-stu-id="3736a-141">**Kristian Hellang. Scrutor.**</span></span> <span data-ttu-id="3736a-142">GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="3736a-142">GitHub repo.</span></span>
    [<span data-ttu-id="3736a-143">*https://github.com/khellang/Scrutor*</span><span class="sxs-lookup"><span data-stu-id="3736a-143">*https://github.com/khellang/Scrutor*</span></span>](https://github.com/khellang/Scrutor)

#### <a name="using-autofac-as-an-ioc-container"></a><span data-ttu-id="3736a-144">使用 Autofac 作为 IoC 容器</span><span class="sxs-lookup"><span data-stu-id="3736a-144">Using Autofac as an IoC container</span></span>

<span data-ttu-id="3736a-145">此外可以使用其他 IoC 容器，然后将其插入 ASP.NET Core 管道，如下所示在 eShopOnContainers，使用排序 microservice [Autofac](https://autofac.org/)。</span><span class="sxs-lookup"><span data-stu-id="3736a-145">You can also use additional IoC containers and plug them into the ASP.NET Core pipeline, as in the ordering microservice in eShopOnContainers, which uses [Autofac](https://autofac.org/).</span></span> <span data-ttu-id="3736a-146">使用 Autofac 时通常会注册通过模块，它可以通过拆分根据你的类型，就像您可以对分布在多个类库的应用程序类型的多个文件之间的注册类型的类型。</span><span class="sxs-lookup"><span data-stu-id="3736a-146">When using Autofac you typically register the types via modules, which allow you to split the registration types between multiple files depending on where your types are, just as you could have the application types distributed across multiple class libraries.</span></span>

<span data-ttu-id="3736a-147">例如，下面是[Autofac 应用程序模块](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs)为[Ordering.API Web API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API)与想要插入的类型的项目。</span><span class="sxs-lookup"><span data-stu-id="3736a-147">For example, the following is the [Autofac application module](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) for the [Ordering.API Web API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) project with the types you will want to inject.</span></span>

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

<span data-ttu-id="3736a-148">注册过程和概念非常类似于您可以使用内置的 ASP.NET Core iOS 容器，注册类型的方式，但使用 Autofac 时的语法是稍有不同。</span><span class="sxs-lookup"><span data-stu-id="3736a-148">The registration process and concepts are very similar to the way you can register types with the built-in ASP.NET Core iOS container, but the syntax when using Autofac is a bit different.</span></span>

<span data-ttu-id="3736a-149">在示例代码中，以及实现类 OrderRepository 注册 IOrderRepository 的抽象。</span><span class="sxs-lookup"><span data-stu-id="3736a-149">In the example code, the abstraction IOrderRepository is registered along with the implementation class OrderRepository.</span></span> <span data-ttu-id="3736a-150">这意味着一个构造函数为声明通过 IOrderRepository 抽象或接口的依赖项，每当 IoC 容器将插入 OrderRepository 类的实例。</span><span class="sxs-lookup"><span data-stu-id="3736a-150">This means that whenever a constructor is declaring a dependency through the IOrderRepository abstraction or interface, the IoC container will inject an instance of the OrderRepository class.</span></span>

<span data-ttu-id="3736a-151">实例作用域类型确定如何实例共享相同的服务或依赖项的请求之间。</span><span class="sxs-lookup"><span data-stu-id="3736a-151">The instance scope type determines how an instance is shared between requests for the same service or dependency.</span></span> <span data-ttu-id="3736a-152">发出请求后的某个依赖项，IoC 容器可以返回以下结果：</span><span class="sxs-lookup"><span data-stu-id="3736a-152">When a request is made for a dependency, the IoC container can return the following:</span></span>

-   <span data-ttu-id="3736a-153">每个生存期作用域的单个实例 (作为 ASP.NET 核心 IoC 容器中称为*范围*)。</span><span class="sxs-lookup"><span data-stu-id="3736a-153">A single instance per lifetime scope (referred to in the ASP.NET Core IoC container as *scoped*).</span></span>

-   <span data-ttu-id="3736a-154">每个依赖项的新实例 (作为 ASP.NET 核心 IoC 容器中称为*暂时性*)。</span><span class="sxs-lookup"><span data-stu-id="3736a-154">A new instance per dependency (referred to in the ASP.NET Core IoC container as *transient*).</span></span>

-   <span data-ttu-id="3736a-155">在使用 IoC 容器的所有对象之间共享的单一实例 (作为 ASP.NET 核心 IoC 容器中称为*singleton*)。</span><span class="sxs-lookup"><span data-stu-id="3736a-155">A single instance shared across all objects using the IoC container (referred to in the ASP.NET Core IoC container as *singleton*).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="3736a-156">其他资源</span><span class="sxs-lookup"><span data-stu-id="3736a-156">Additional resources</span></span>

-   <span data-ttu-id="3736a-157">**在 ASP.NET 核心中的依赖关系注入简介**
    [*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)</span><span class="sxs-lookup"><span data-stu-id="3736a-157">**Introduction to Dependency Injection in ASP.NET Core**
[*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)</span></span>

-   <span data-ttu-id="3736a-158">**Autofac。**</span><span class="sxs-lookup"><span data-stu-id="3736a-158">**Autofac.**</span></span> <span data-ttu-id="3736a-159">正式文档。</span><span class="sxs-lookup"><span data-stu-id="3736a-159">Official documentation.</span></span>
    [<span data-ttu-id="3736a-160">*http://docs.autofac.org/en/latest/*</span><span class="sxs-lookup"><span data-stu-id="3736a-160">*http://docs.autofac.org/en/latest/*</span></span>](http://docs.autofac.org/en/latest/)

-   <span data-ttu-id="3736a-161">**Cesar de la Torre。比较具有 Autofac IoC 容器实例作用域的 ASP.NET 核心 IoC 容器服务生命周期**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span><span class="sxs-lookup"><span data-stu-id="3736a-161">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span></span>

## <a name="implementing-the-command-and-command-handler-patterns"></a><span data-ttu-id="3736a-162">实现的命令和命令处理程序模式</span><span class="sxs-lookup"><span data-stu-id="3736a-162">Implementing the Command and Command Handler patterns</span></span>

<span data-ttu-id="3736a-163">在上一节中所示 DI 通过构造函数示例中，通过在类的构造函数的存储库已将注入 IoC 容器。</span><span class="sxs-lookup"><span data-stu-id="3736a-163">In the DI-through-constructor example shown in the previous section, the IoC container was injecting repositories through a constructor in a class.</span></span> <span data-ttu-id="3736a-164">但是，完全其中已它们注入？</span><span class="sxs-lookup"><span data-stu-id="3736a-164">But exactly where were they injected?</span></span> <span data-ttu-id="3736a-165">在简单 Web API (例如，在 eShopOnContainers 目录 microservice) 中，你将它们注入控制器构造函数中的 MVC 控制器级。</span><span class="sxs-lookup"><span data-stu-id="3736a-165">In a simple Web API (for example, the catalog microservice in eShopOnContainers), you inject them at the MVC controllers level, in a controller constructor.</span></span> <span data-ttu-id="3736a-166">但是，在本部分的初始代码 ( [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs)从中 eShopOnContainers Ordering.API 服务的类)，通过特定命令的构造函数完成的依赖关系注入处理程序。</span><span class="sxs-lookup"><span data-stu-id="3736a-166">However, in the initial code of this section (the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) class from the Ordering.API service in eShopOnContainers), the injection of dependencies is done through the constructor of a particular command handler.</span></span> <span data-ttu-id="3736a-167">让我们解释什么是命令处理程序是，为什么你想要使用它。</span><span class="sxs-lookup"><span data-stu-id="3736a-167">Let us explain what a command handler is and why you would want to use it.</span></span>

<span data-ttu-id="3736a-168">本指南中前面引入了 CQRS 模式本质上与相关命令模式。</span><span class="sxs-lookup"><span data-stu-id="3736a-168">The Command pattern is intrinsically related to the CQRS pattern that was introduced earlier in this guide.</span></span> <span data-ttu-id="3736a-169">CQRS 具有两条边。</span><span class="sxs-lookup"><span data-stu-id="3736a-169">CQRS has two sides.</span></span> <span data-ttu-id="3736a-170">第一个领域是使用简化的查询的查询[Dapper](https://github.com/StackExchange/dapper-dot-net)微型 ORM、 以前所述。</span><span class="sxs-lookup"><span data-stu-id="3736a-170">The first area is queries, using simplified queries with the [Dapper](https://github.com/StackExchange/dapper-dot-net) micro ORM, which was explained previously.</span></span> <span data-ttu-id="3736a-171">第二个区域是命令，为事务的起始点和从外部服务的输入的通道。</span><span class="sxs-lookup"><span data-stu-id="3736a-171">The second area is commands, which are the starting point for transactions, and the input channel from outside the service.</span></span>

<span data-ttu-id="3736a-172">如所示图 9-20，基于模式接受从客户端的命令处理，将其基于域模型规则，并最后将保存与事务的状态。</span><span class="sxs-lookup"><span data-stu-id="3736a-172">As shown in Figure 9-20, the pattern is based on accepting commands from the client side, processing them based on the domain model rules, and finally persisting the states with transactions.</span></span>

![](./media/image21.png)

<span data-ttu-id="3736a-173">**图 9-20**。</span><span class="sxs-lookup"><span data-stu-id="3736a-173">**Figure 9-20**.</span></span> <span data-ttu-id="3736a-174">命令或 CQRS 模式中的"事务端"的高级视图</span><span class="sxs-lookup"><span data-stu-id="3736a-174">High-level view of the commands or “transactional side” in a CQRS pattern</span></span>

### <a name="the-command-class"></a><span data-ttu-id="3736a-175">命令类</span><span class="sxs-lookup"><span data-stu-id="3736a-175">The command class</span></span>

<span data-ttu-id="3736a-176">命令是让系统执行更改系统的状态的操作的请求。</span><span class="sxs-lookup"><span data-stu-id="3736a-176">A command is a request for the system to perform an action that changes the state of the system.</span></span> <span data-ttu-id="3736a-177">命令是命令性，，应只需一次处理。</span><span class="sxs-lookup"><span data-stu-id="3736a-177">Commands are imperative, and should be processed just once.</span></span>

<span data-ttu-id="3736a-178">由于命令都是需求，它们通常命名为与在命令性语气 （例如，"创建"或"更新"），谓词，但可能包括的聚合类型，例如 CreateOrderCommand。</span><span class="sxs-lookup"><span data-stu-id="3736a-178">Since commands are imperatives, they are typically named with a verb in the imperative mood (for example, "create" or "update"), and they might include the aggregate type, such as CreateOrderCommand.</span></span> <span data-ttu-id="3736a-179">与某个事件，不同命令不是从过去; 事实它是仅一个请求，并因此可能被拒绝。</span><span class="sxs-lookup"><span data-stu-id="3736a-179">Unlike an event, a command is not a fact from the past; it is only a request, and thus may be refused.</span></span>

<span data-ttu-id="3736a-180">命令可能源自从启动请求，用户由于 UI 或从一个进程管理器时的进程管理器定向聚合执行操作。</span><span class="sxs-lookup"><span data-stu-id="3736a-180">Commands can originate from the UI as a result of a user initiating a request, or from a process manager when the process manager is directing an aggregate to perform an action.</span></span>

<span data-ttu-id="3736a-181">命令的重要特征是，它应处理只需一次通过单一接收方。</span><span class="sxs-lookup"><span data-stu-id="3736a-181">An important characteristic of a command is that it should be processed just once by a single receiver.</span></span> <span data-ttu-id="3736a-182">这是因为某命令是单个操作或你想要在应用程序中执行的事务。</span><span class="sxs-lookup"><span data-stu-id="3736a-182">This is because a command is a single action or transaction you want to perform in the application.</span></span> <span data-ttu-id="3736a-183">例如，应不超过一次处理相同的顺序创建命令。</span><span class="sxs-lookup"><span data-stu-id="3736a-183">For example, the same order creation command should not be processed more than once.</span></span> <span data-ttu-id="3736a-184">这是命令和事件之间的一项重大差异。</span><span class="sxs-lookup"><span data-stu-id="3736a-184">This is an important difference between commands and events.</span></span> <span data-ttu-id="3736a-185">事件可能会多次处理，因为许多系统或微服务可能感兴趣的事件。</span><span class="sxs-lookup"><span data-stu-id="3736a-185">Events may be processed multiple times, because many systems or microservices might be interested in the event.</span></span>

<span data-ttu-id="3736a-186">此外，很重要命令被处理仅一次，以防该命令不是幂等。</span><span class="sxs-lookup"><span data-stu-id="3736a-186">In addition, it is important that a command be processed only once in case the command is not idempotent.</span></span> <span data-ttu-id="3736a-187">如果可以执行它多次而无需更改的结果，该命令的性质，因此或由于系统处理命令的方法，某命令是幂等。</span><span class="sxs-lookup"><span data-stu-id="3736a-187">A command is idempotent if it can be executed multiple times without changing the result, either because of the nature of the command, or because of the way the system handles the command.</span></span>

<span data-ttu-id="3736a-188">它是一个好办法使命令和更新幂等，建立在你的域的业务规则条件和固定协定的意义上时。</span><span class="sxs-lookup"><span data-stu-id="3736a-188">It is a good practice to make your commands and updates idempotent when it makes sense under your domain’s business rules and invariants.</span></span> <span data-ttu-id="3736a-189">例如，若要使用相同的示例中，如果出于任何原因 （重试逻辑，发起的黑客攻击、 等） 相同的 CreateOrder 命令达到你的系统多次，你应能够标识它，确保你不会创建多个订单。</span><span class="sxs-lookup"><span data-stu-id="3736a-189">For instance, to use the same example, if for any reason (retry logic, hacking, etc.) the same CreateOrder command reaches your system multiple times, you should be able to identify it and ensure that you do not create multiple orders.</span></span> <span data-ttu-id="3736a-190">为此，你需要附加某种类型的操作中标识并确定是否已处理的命令或更新。</span><span class="sxs-lookup"><span data-stu-id="3736a-190">To do so, you need to attach some kind of identity in the operations and identify whether the command or update was already processed.</span></span>

<span data-ttu-id="3736a-191">将命令发送到一个接收方;不发布命令。</span><span class="sxs-lookup"><span data-stu-id="3736a-191">You send a command to a single receiver; you do not publish a command.</span></span> <span data-ttu-id="3736a-192">发布为该状态事实集成事件-出发生，可能感兴趣的事件接收器。</span><span class="sxs-lookup"><span data-stu-id="3736a-192">Publishing is for integration events that state a fact—that something has happened and might be interesting for event receivers.</span></span> <span data-ttu-id="3736a-193">对于事件，发布服务器有的无所顾忌哪些情况下，接收方收到事件或它们执行它。</span><span class="sxs-lookup"><span data-stu-id="3736a-193">In the case of events, the publisher has no concerns about which receivers get the event or what they do it.</span></span> <span data-ttu-id="3736a-194">但集成事件是前面部分中已引入另外一回事。</span><span class="sxs-lookup"><span data-stu-id="3736a-194">But integration events are a different story already introduced in previous sections.</span></span>

<span data-ttu-id="3736a-195">命令是使用包含数据字段或与执行该命令所需的所有信息的集合的类实施的。</span><span class="sxs-lookup"><span data-stu-id="3736a-195">A command is implemented with a class that contains data fields or collections with all the information that is needed in order to execute that command.</span></span> <span data-ttu-id="3736a-196">命令是一种特殊类型的数据传输对象 (DTO)，一个专门用于请求更改或事务。</span><span class="sxs-lookup"><span data-stu-id="3736a-196">A command is a special kind of Data Transfer Object (DTO), one that is specifically used to request changes or transactions.</span></span> <span data-ttu-id="3736a-197">命令本身基于完全处理命令，而不安装其他所需的信息。</span><span class="sxs-lookup"><span data-stu-id="3736a-197">The command itself is based on exactly the information that is needed for processing the command, and nothing more.</span></span>

<span data-ttu-id="3736a-198">下面的示例演示简化的 CreateOrderCommand 类。</span><span class="sxs-lookup"><span data-stu-id="3736a-198">The following example shows the simplified CreateOrderCommand class.</span></span> <span data-ttu-id="3736a-199">这是在中 eShopOnContainers 排序微服务中使用一个不可变命令。</span><span class="sxs-lookup"><span data-stu-id="3736a-199">This is an immutable command that is used in the ordering microservice in eShopOnContainers.</span></span>

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

<span data-ttu-id="3736a-200">基本上，命令类包含有关执行业务事务的使用的域模型对象所需的所有数据。</span><span class="sxs-lookup"><span data-stu-id="3736a-200">Basically, the command class contains all the data you need for performing a business transaction by using the domain model objects.</span></span> <span data-ttu-id="3736a-201">因此，命令是只需包含只读数据和任何行为的数据结构。</span><span class="sxs-lookup"><span data-stu-id="3736a-201">Thus, commands are simply data structures that contain read-only data, and no behavior.</span></span> <span data-ttu-id="3736a-202">命令的名称指示其用途。</span><span class="sxs-lookup"><span data-stu-id="3736a-202">The command’s name indicates its purpose.</span></span> <span data-ttu-id="3736a-203">在许多语言，如 C\#，命令表示为类，但它们不在实际的面向对象的意义上 true 类。</span><span class="sxs-lookup"><span data-stu-id="3736a-203">In many languages like C\#, commands are represented as classes, but they are not true classes in the real object-oriented sense.</span></span>

<span data-ttu-id="3736a-204">其他特征，命令将将不可变的因为预期使用情况是，它们直接通过域模型中处理。</span><span class="sxs-lookup"><span data-stu-id="3736a-204">As an additional characteristic, commands are immutable, because the expected usage is that they are processed directly by the domain model.</span></span> <span data-ttu-id="3736a-205">它们不需要在其计划的生存期内更改。</span><span class="sxs-lookup"><span data-stu-id="3736a-205">They do not need to change during their projected lifetime.</span></span> <span data-ttu-id="3736a-206">在 C 中\#类，可以通过不具有任何 setter 或更改内部状态的其他方法来实现不可变性。</span><span class="sxs-lookup"><span data-stu-id="3736a-206">In a C\# class, immutability can be achieved by not having any setters or other methods that change internal state.</span></span>

<span data-ttu-id="3736a-207">例如，命令类，用于创建顺序是在数据方面可能类似于你想要创建的顺序，但你可能不需要相同的属性。</span><span class="sxs-lookup"><span data-stu-id="3736a-207">For example, the command class for creating an order is probably similar in terms of data to the order you want to create, but you probably do not need the same attributes.</span></span> <span data-ttu-id="3736a-208">例如，CreateOrderCommand 没有一个订单 ID，因为尚未创建顺序。</span><span class="sxs-lookup"><span data-stu-id="3736a-208">For instance, CreateOrderCommand does not have an order ID, because the order has not been created yet.</span></span>

<span data-ttu-id="3736a-209">许多命令类可以是简单，需仅需要更改某些状态有关的几个字段。</span><span class="sxs-lookup"><span data-stu-id="3736a-209">Many command classes can be simple, requiring only a few fields about some state that needs to be changed.</span></span> <span data-ttu-id="3736a-210">为这种情况如果您只需更改订单的状态从"进程内"到"付费"或"交付"的使用如下命令：</span><span class="sxs-lookup"><span data-stu-id="3736a-210">That would be the case if you are just changing the status of an order from “in process” to “paid” or “shipped” by using a command similar to the following:</span></span>

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

<span data-ttu-id="3736a-211">一些开发人员使其 UI 请求对象独立于其命令 Dto，但这是只首选项。</span><span class="sxs-lookup"><span data-stu-id="3736a-211">Some developers make their UI request objects separate from their command DTOs, but that is just a matter of preference.</span></span> <span data-ttu-id="3736a-212">它是提供不会获得很附加的价值，乏味分离，并且对象几乎完全相同的形状。</span><span class="sxs-lookup"><span data-stu-id="3736a-212">It is a tedious separation with not much added value, and the objects are almost exactly the same shape.</span></span> <span data-ttu-id="3736a-213">例如，在 eShopOnContainers，命令直接来自客户端。</span><span class="sxs-lookup"><span data-stu-id="3736a-213">For instance, in eShopOnContainers, the commands come directly from the client side.</span></span>

### <a name="the-command-handler-class"></a><span data-ttu-id="3736a-214">命令处理程序类</span><span class="sxs-lookup"><span data-stu-id="3736a-214">The Command Handler class</span></span>

<span data-ttu-id="3736a-215">应实现每个命令的特定命令处理程序类。</span><span class="sxs-lookup"><span data-stu-id="3736a-215">You should implement a specific command handler class for each command.</span></span> <span data-ttu-id="3736a-216">这是模式的工作原理，并且你将在其中使用的命令对象、 域对象和基础结构存储库对象。</span><span class="sxs-lookup"><span data-stu-id="3736a-216">That is how the pattern works, and it is where you will use the command object, the domain objects, and the infrastructure repository objects.</span></span> <span data-ttu-id="3736a-217">命令处理程序中的事实是在 CQRS 和 DDD 方面的应用程序层的核心。</span><span class="sxs-lookup"><span data-stu-id="3736a-217">The command handler is in fact the heart of the application layer in terms of CQRS and DDD.</span></span> <span data-ttu-id="3736a-218">但是，所有域逻辑应都包含在域类-聚合根 （根实体） 中子实体或[域服务](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/)，但不是在命令处理程序，它是从应用程序的一个类层。</span><span class="sxs-lookup"><span data-stu-id="3736a-218">However, all the domain logic should be contained within the domain classes—within the aggregate roots (root entities), child entities, or [domain services](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), but not within the command handler, which is a class from the application layer.</span></span>

<span data-ttu-id="3736a-219">命令处理程序收到命令，并从使用聚合获取结果。</span><span class="sxs-lookup"><span data-stu-id="3736a-219">A command handler receives a command and obtains a result from the aggregate that is used.</span></span> <span data-ttu-id="3736a-220">结果应为此命令成功执行，或者异常。</span><span class="sxs-lookup"><span data-stu-id="3736a-220">The result should be either successful execution of the command, or an exception.</span></span> <span data-ttu-id="3736a-221">在出现异常，系统状态应保持不变。</span><span class="sxs-lookup"><span data-stu-id="3736a-221">In the case of an exception, the system state should be unchanged.</span></span>

<span data-ttu-id="3736a-222">命令处理程序通常将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3736a-222">The command handler usually takes the following steps:</span></span>

-   <span data-ttu-id="3736a-223">它接收命令对象，如 DTO (从[中介](https://en.wikipedia.org/wiki/Mediator_pattern)或其他基础结构对象)。</span><span class="sxs-lookup"><span data-stu-id="3736a-223">It receives the command object, like a DTO (from the [mediator](https://en.wikipedia.org/wiki/Mediator_pattern) or other infrastructure object).</span></span>

-   <span data-ttu-id="3736a-224">它会验证命令有效 （如果不能验证中介来实现）。</span><span class="sxs-lookup"><span data-stu-id="3736a-224">It validates that the command is valid (if not validated by the mediator).</span></span>

-   <span data-ttu-id="3736a-225">它实例化目标的当前命令的聚合根实例。</span><span class="sxs-lookup"><span data-stu-id="3736a-225">It instantiates the aggregate root instance that is the target of the current command.</span></span>

-   <span data-ttu-id="3736a-226">它在命令中获取所需的数据的聚合根实例上执行该方法。</span><span class="sxs-lookup"><span data-stu-id="3736a-226">It executes the method on the aggregate root instance, getting the required data from the command.</span></span>

-   <span data-ttu-id="3736a-227">它保存到其相关数据库聚合的新状态。</span><span class="sxs-lookup"><span data-stu-id="3736a-227">It persists the new state of the aggregate to its related database.</span></span> <span data-ttu-id="3736a-228">此最后一次操作是实际的事务。</span><span class="sxs-lookup"><span data-stu-id="3736a-228">This last operation is the actual transaction.</span></span>

<span data-ttu-id="3736a-229">通常情况下，命令处理程序处理单个聚合驱动由其聚合根 （根实体）。</span><span class="sxs-lookup"><span data-stu-id="3736a-229">Typically, a command handler deals with a single aggregate driven by its aggregate root (root entity).</span></span> <span data-ttu-id="3736a-230">如果多个聚合应受到接收的单个命令，你可以使用域事件通过多个聚合传播状态或操作</span><span class="sxs-lookup"><span data-stu-id="3736a-230">If multiple aggregates should be impacted by the reception of a single command, you could use domain events to propagate states or actions across multiple aggregates</span></span>

<span data-ttu-id="3736a-231">重要的一点是处理命令时，所有域逻辑应都为域模型中 （聚合），完全封装并准备好进行单元测试。</span><span class="sxs-lookup"><span data-stu-id="3736a-231">The important point here is that when a command is being processed, all the domain logic should be inside the domain model (the aggregates), fully encapsulated and ready for unit testing.</span></span> <span data-ttu-id="3736a-232">命令处理程序就可以充当作为一种方法从数据库中获取域模型和最后一步，以告知基础结构层 （存储库），以便在该模型更改时保留更改。</span><span class="sxs-lookup"><span data-stu-id="3736a-232">The command handler just acts as a way to get the domain model from the database, and as the final step, to tell the infrastructure layer (repositories) to persist the changes when the model is changed.</span></span> <span data-ttu-id="3736a-233">此方法的优点是可以在独立的、 完全封装的、 丰富的、 行为域模型中的域逻辑重构而无需更改应用程序或基础结构层，它们是联结级别 （命令处理程序，Web API 中的代码存储库、 等）。</span><span class="sxs-lookup"><span data-stu-id="3736a-233">The advantage of this approach is that you can refactor the domain logic in an isolated, fully encapsulated, rich, behavioral domain model without changing code in the application or infrastructure layers, which are the plumbing level (command handlers, Web API, repositories, etc.).</span></span>

<span data-ttu-id="3736a-234">当命令处理程序获得复杂，而且具有太多逻辑时，这可能是代码告知。</span><span class="sxs-lookup"><span data-stu-id="3736a-234">When command handlers get complex, with too much logic, that can be a code smell.</span></span> <span data-ttu-id="3736a-235">查看它们，并且如果你发现域逻辑，重构代码以将该域行为移动到的域对象 （聚合根和子实体） 的方法。</span><span class="sxs-lookup"><span data-stu-id="3736a-235">Review them, and if you find domain logic, refactor the code to move that domain behavior to the methods of the domain objects (the aggregate root and child entity).</span></span>

<span data-ttu-id="3736a-236">作为命令处理程序类的示例，下面的代码演示这一章开头你看到的同一个 CreateOrderCommandHandler 类。</span><span class="sxs-lookup"><span data-stu-id="3736a-236">As an example of a command handler class, the following code shows the same CreateOrderCommandHandler class that you saw at the beginning of this chapter.</span></span> <span data-ttu-id="3736a-237">在这种情况下我们具有突出显示的句柄方法和域模型对象/聚合操作。</span><span class="sxs-lookup"><span data-stu-id="3736a-237">In this case we have highlighted the Handle method and the operations with the domain model objects/aggregates.</span></span>

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

<span data-ttu-id="3736a-238">这些是命令处理程序应执行的附加步骤：</span><span class="sxs-lookup"><span data-stu-id="3736a-238">These are additional steps a command handler should take:</span></span>

-   <span data-ttu-id="3736a-239">使用命令的数据来操作时使用的聚合根方法和行为。</span><span class="sxs-lookup"><span data-stu-id="3736a-239">Use the command’s data to operate with the aggregate root’s methods and behavior.</span></span>

-   <span data-ttu-id="3736a-240">内部域对象中，在引发域事件时执行事务，但这是从命令处理程序的角度来看透明。</span><span class="sxs-lookup"><span data-stu-id="3736a-240">Internally within the domain objects, raise domain events while the transaction is executed, but that is transparent from a command handler point of view.</span></span>

-   <span data-ttu-id="3736a-241">如果聚合的操作结果是成功并且在完成事务后，引发集成事件命令处理程序。</span><span class="sxs-lookup"><span data-stu-id="3736a-241">If the aggregate’s operation result is successful and after the transaction is finished, raise integration events command handler.</span></span> <span data-ttu-id="3736a-242">（这些可能还会出现基础结构的类，如存储库。）</span><span class="sxs-lookup"><span data-stu-id="3736a-242">(These might also be raised by infrastructure classes like repositories.)</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="3736a-243">其他资源</span><span class="sxs-lookup"><span data-stu-id="3736a-243">Additional resources</span></span>

-   <span data-ttu-id="3736a-244">**标记 Seemann。在边界将应用程序是面向不对象的**
    [*http://blog.ploeh.dk/2011/05/31/AttheBoundaries，ApplicationsareNotObject 面向 /*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)</span><span class="sxs-lookup"><span data-stu-id="3736a-244">**Mark Seemann. At the Boundaries, Applications are Not Object-Oriented**
[*http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)</span></span>

-   <span data-ttu-id="3736a-245">**命令和事件**
    [*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)</span><span class="sxs-lookup"><span data-stu-id="3736a-245">**Commands and events**
[*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)</span></span>

-   <span data-ttu-id="3736a-246">**命令处理程序的作用是什么？** 
     [ *http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)</span><span class="sxs-lookup"><span data-stu-id="3736a-246">**What does a command handler do?**
[*http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)</span></span>

-   <span data-ttu-id="3736a-247">**Jimmy Bogard。域命令模式 – 处理程序**
    [*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)</span><span class="sxs-lookup"><span data-stu-id="3736a-247">**Jimmy Bogard. Domain Command Patterns – Handlers**
[*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)</span></span>

-   <span data-ttu-id="3736a-248">**Jimmy Bogard。域命令模式 – 验证**
    [*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)</span><span class="sxs-lookup"><span data-stu-id="3736a-248">**Jimmy Bogard. Domain Command Patterns – Validation**
[*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)</span></span>

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a><span data-ttu-id="3736a-249">命令处理管道： 如何在触发是命令处理程序</span><span class="sxs-lookup"><span data-stu-id="3736a-249">The Command process pipeline: how to trigger a command handler</span></span>

<span data-ttu-id="3736a-250">下一个问题是如何调用命令处理程序。</span><span class="sxs-lookup"><span data-stu-id="3736a-250">The next question is how to invoke a command handler.</span></span> <span data-ttu-id="3736a-251">你可以手动调用它从每个相关的 ASP.NET Core 控制器。</span><span class="sxs-lookup"><span data-stu-id="3736a-251">You could manually call it from each related ASP.NET Core controller.</span></span> <span data-ttu-id="3736a-252">但是，方法是将太结合并不理想。</span><span class="sxs-lookup"><span data-stu-id="3736a-252">However, that approach would be too coupled and is not ideal.</span></span>

<span data-ttu-id="3736a-253">其他两个主要选项，这些建议的选项有：</span><span class="sxs-lookup"><span data-stu-id="3736a-253">The other two main options, which are the recommended options, are:</span></span>

-   <span data-ttu-id="3736a-254">通过内存中中介模式项目。</span><span class="sxs-lookup"><span data-stu-id="3736a-254">Through an in-memory Mediator pattern artifact.</span></span>

-   <span data-ttu-id="3736a-255">使用控制器和处理程序之间的异步消息队列。</span><span class="sxs-lookup"><span data-stu-id="3736a-255">With an asynchronous message queue, in between controllers and handlers.</span></span>

### <a name="using-the-mediator-pattern-in-memory-in-the-command-pipeline"></a><span data-ttu-id="3736a-256">在命令管道中使用中介模式 （内存中）</span><span class="sxs-lookup"><span data-stu-id="3736a-256">Using the Mediator pattern (in-memory) in the command pipeline</span></span>

<span data-ttu-id="3736a-257">如所示图 9-21，CQRS 方法在情况下会使用智能中介，类似于内存中总线，这是足够智能，可将重定向到正确的命令处理程序基于命令或 DTO 正在接收的类型。</span><span class="sxs-lookup"><span data-stu-id="3736a-257">As shown in Figure 9-21, in a CQRS approach you use an intelligent mediator, similar to an in-memory bus, which is smart enough to redirect to the right command handler based on the type of the command or DTO being received.</span></span> <span data-ttu-id="3736a-258">组件之间的单个黑色箭头表示与他们相关之间的交互 （在许多情况下，通过 DI 插入） 的对象之间的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="3736a-258">The single black arrows between components represent the dependencies between objects (in many cases, injected through DI) with their related interactions.</span></span>

![](./media/image22.png)

<span data-ttu-id="3736a-259">**图 9-21**。</span><span class="sxs-lookup"><span data-stu-id="3736a-259">**Figure 9-21**.</span></span> <span data-ttu-id="3736a-260">在单个 CQRS 微服务中的过程中使用中介模式</span><span class="sxs-lookup"><span data-stu-id="3736a-260">Using the Mediator pattern in process in a single CQRS microservice</span></span>

<span data-ttu-id="3736a-261">使用中介模式有意义的原因是企业应用程序中处理请求可以变得很复杂。</span><span class="sxs-lookup"><span data-stu-id="3736a-261">The reason that using the Mediator pattern makes sense is that in enterprise applications, the processing requests can get complicated.</span></span> <span data-ttu-id="3736a-262">你想要能够添加打开如日志记录、 验证、 审核和安全的跨领域问题数。</span><span class="sxs-lookup"><span data-stu-id="3736a-262">You want to be able to add an open number of cross-cutting concerns like logging, validations, audit, and security.</span></span> <span data-ttu-id="3736a-263">在这些情况下，你可以依赖于中介管道 (请参阅[中介模式](https://en.wikipedia.org/wiki/Mediator_pattern)) 以提供一种为这些额外的行为或跨领域问题。</span><span class="sxs-lookup"><span data-stu-id="3736a-263">In these cases, you can rely on a mediator pipeline (see [Mediator pattern](https://en.wikipedia.org/wiki/Mediator_pattern)) to provide a means for these extra behaviors or cross-cutting concerns.</span></span>

<span data-ttu-id="3736a-264">中介是封装"如何"在此过程中的对象： 它协调基于状态的执行，则调用的方法是命令处理程序，或到处理程序提供的负载。</span><span class="sxs-lookup"><span data-stu-id="3736a-264">A mediator is an object that encapsulates the “how” of this process: it coordinates execution based on state, the way a command handler is invoked, or the payload you provide to the handler.</span></span> <span data-ttu-id="3736a-265">借助中介组件可以应用跨领域问题集中式和透明的方式通过应用修饰器 (或[管道行为](https://github.com/jbogard/MediatR/wiki/Behaviors)自中介 v3)。</span><span class="sxs-lookup"><span data-stu-id="3736a-265">With a mediator component you can apply cross-cutting concerns in a centralized and transparent way by applying decorators (or [pipeline behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) since Mediator v3).</span></span> <span data-ttu-id="3736a-266">(有关详细信息，请参阅[修饰器模式](https://en.wikipedia.org/wiki/Decorator_pattern)。)</span><span class="sxs-lookup"><span data-stu-id="3736a-266">(For more information, see the [Decorator pattern](https://en.wikipedia.org/wiki/Decorator_pattern).)</span></span>

<span data-ttu-id="3736a-267">修饰器以及行为都类似于[方面面向编程 (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming)，则只应用于由中介组件的特定进程管道。</span><span class="sxs-lookup"><span data-stu-id="3736a-267">Decorators and behaviors are similar to [Aspect Oriented Programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), only applied to a specific process pipeline managed by the mediator component.</span></span> <span data-ttu-id="3736a-268">根据应用 AOP 实现的跨领域问题的方面*方面 weavers*在编译时将插入的或基于对象调用截获。</span><span class="sxs-lookup"><span data-stu-id="3736a-268">Aspects in AOP that implement cross-cutting concerns are applied based on *aspect weavers* injected at compilation time or based on object call interception.</span></span> <span data-ttu-id="3736a-269">这两种典型的 AOP 方法有时称为"类似于"幻数，因为它不是轻松地了解如何 AOP 完成其工作。</span><span class="sxs-lookup"><span data-stu-id="3736a-269">Both typical AOP approaches are sometimes said to work "like magic," because it is not easy to see how AOP does its work.</span></span> <span data-ttu-id="3736a-270">在处理的严重问题或 bug，AOP 可能很难调试。</span><span class="sxs-lookup"><span data-stu-id="3736a-270">When dealing with serious issues or bugs, AOP can be difficult to debug.</span></span> <span data-ttu-id="3736a-271">另一方面，这些修饰符/行为是显式和应用仅在中介来实现，上下文中以便能够调试更可预测和轻松。</span><span class="sxs-lookup"><span data-stu-id="3736a-271">On the other hand, these decorators/behaviors are explicit and applied only in the context of the mediator, so debugging is much more predictable and easy.</span></span>

<span data-ttu-id="3736a-272">例如，在排序 microservice eShopOnContainers，我们实现两个示例修饰符， [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs)类和一个[ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs)类。</span><span class="sxs-lookup"><span data-stu-id="3736a-272">For example, in the eShopOnContainers ordering microservice, we implemented two sample decorators, a [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) class and a [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) class.</span></span> <span data-ttu-id="3736a-273">下一节介绍了修饰器的实现。</span><span class="sxs-lookup"><span data-stu-id="3736a-273">The decorator’s implementation is explained in the next section.</span></span> <span data-ttu-id="3736a-274">请注意，在将来版本中，eShopOnContainers 将迁移到[MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0)并转向[行为](https://github.com/jbogard/MediatR/wiki/Behaviors)而不是使用修饰器。</span><span class="sxs-lookup"><span data-stu-id="3736a-274">Note that in a future version, eShopOnContainers will migrate to [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) and move to [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) instead of using decorators.</span></span>

### <a name="using-message-queues-out-of-proc-in-the-commands-pipeline"></a><span data-ttu-id="3736a-275">在命令的管道中使用消息队列 （进程外）</span><span class="sxs-lookup"><span data-stu-id="3736a-275">Using message queues (out-of-proc) in the command’s pipeline</span></span>

<span data-ttu-id="3736a-276">另一个选项是使用基于代理或消息队列，如图 9-22 中所示的异步消息。</span><span class="sxs-lookup"><span data-stu-id="3736a-276">Another choice is to use asynchronous messages based on brokers or message queues, as shown in Figure 9-22.</span></span> <span data-ttu-id="3736a-277">此外可以使用该选项合并与中介组件之前的命令处理程序。</span><span class="sxs-lookup"><span data-stu-id="3736a-277">That option could also be combined with the mediator component right before the command handler.</span></span>

![](./media/image23.png)

<span data-ttu-id="3736a-278">**图 9-22**。</span><span class="sxs-lookup"><span data-stu-id="3736a-278">**Figure 9-22**.</span></span> <span data-ttu-id="3736a-279">通过 CQRS 命令中使用消息队列 （带进程和进程间通信）</span><span class="sxs-lookup"><span data-stu-id="3736a-279">Using message queues (out of process and inter-process communication) with CQRS commands</span></span>

<span data-ttu-id="3736a-280">使用消息队列接受命令可进一步使变得复杂命令的管道，因为你可能需要此管道拆分为两个进程通过外部消息队列连接。</span><span class="sxs-lookup"><span data-stu-id="3736a-280">Using message queues to accept the commands can further complicate your command’s pipeline, because you will probably need to split the pipeline into two processes connected through the external message queue.</span></span> <span data-ttu-id="3736a-281">但是，它应使用如果需要可伸缩性和基于异步消息传送的性能改进。</span><span class="sxs-lookup"><span data-stu-id="3736a-281">Still, it should be used if you need to have improved scalability and performance based on asynchronous messaging.</span></span> <span data-ttu-id="3736a-282">请考虑对于图 9-22，该控制器只需命令消息发送到队列，并且返回。</span><span class="sxs-lookup"><span data-stu-id="3736a-282">Consider that in the case of Figure 9-22, the controller just posts the command message into the queue and returns.</span></span> <span data-ttu-id="3736a-283">然后命令处理程序处理其自己的步调的消息。</span><span class="sxs-lookup"><span data-stu-id="3736a-283">Then the command handlers process the messages at their own pace.</span></span> <span data-ttu-id="3736a-284">它是非常有好处的队列-超可伸缩性是所需，例如对于 stocks 或与大量的传入数据的任何其他方案时，消息队列可充当用例中的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="3736a-284">That is a great benefit of queues—the message queue can act as a buffer in cases when hyper scalability is needed, such as for stocks or any other scenario with a high volume of ingress data.</span></span>

<span data-ttu-id="3736a-285">但是，消息队列的异步性质，因此你需要找出如何与客户端应用程序有关的成功或失败的命令的进程进行通信。</span><span class="sxs-lookup"><span data-stu-id="3736a-285">However, because of the asynchronous nature of message queues, you need to figure out how to communicate with the client application about the success or failure of the command’s process.</span></span> <span data-ttu-id="3736a-286">一般来说，你应永远不会使用"发后不理"命令。</span><span class="sxs-lookup"><span data-stu-id="3736a-286">As a rule, you should never use “fire and forget” commands.</span></span> <span data-ttu-id="3736a-287">每个业务应用程序需要知道是否命令已成功处理，或至少验证并且接受。</span><span class="sxs-lookup"><span data-stu-id="3736a-287">Every business application needs to know if a command was processed successfully, or at least validated and accepted.</span></span>

<span data-ttu-id="3736a-288">因此，能够响应客户端在验证已提交至异步队列的命令消息之后将增加你的系统，相比运行事务后返回操作的结果的进程内命令过程的复杂性。</span><span class="sxs-lookup"><span data-stu-id="3736a-288">Thus, being able to respond to the client after validating a command message that was submitted to an asynchronous queue adds complexity to your system, as compared to an in-process command process that returns the operation’s result after running the transaction.</span></span> <span data-ttu-id="3736a-289">使用队列时，你可能需要返回其他操作结果消息，将需要其他组件和自定义通信系统中通过命令过程的结果。</span><span class="sxs-lookup"><span data-stu-id="3736a-289">Using queues, you might need to return the result of the command process through other operation result messages, which will require additional components and custom communication in your system.</span></span>

<span data-ttu-id="3736a-290">此外，异步命令是单向的命令，这在许多情况下可能不需要如 Burtsev Alexey 和中的 Greg Young 之间的以下有趣交换中所述[联机会话](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span><span class="sxs-lookup"><span data-stu-id="3736a-290">Additionally, async commands are one-way commands, which in many cases might not be needed, as is explained in the following interesting exchange between Burtsev Alexey and Greg Young in an [online conversation](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span></span>

<span data-ttu-id="3736a-291">\[Burtsev Alexey\]发现的代码的许多人都使用异步命令处理或一种方法而无需任何原因需要这么做消息传递的命令 （它们未执行某些较长的操作，它们未在执行外部异步代码，它们甚至不跨应用程序边界要使用消息总线）。</span><span class="sxs-lookup"><span data-stu-id="3736a-291">\[Burtsev Alexey\] I find lots of code where people use async command handling or one way command messaging without any reason to do so (they are not doing some long operation, they are not executing external async code, they do not even cross application boundary to be using message bus).</span></span> <span data-ttu-id="3736a-292">它们为何引入此不必要的复杂性？</span><span class="sxs-lookup"><span data-stu-id="3736a-292">Why do they introduce this unnecessary complexity?</span></span> <span data-ttu-id="3736a-293">和实际上，我尚未看到 CQRS 代码示例与目前为止，阻塞命令处理程序，但它将在大多数情况下正常工作。</span><span class="sxs-lookup"><span data-stu-id="3736a-293">And actually, I haven't seen a CQRS code example with blocking command handlers so far, though it will work just fine in most cases.</span></span>

<span data-ttu-id="3736a-294">\[Greg Young\] \[...\]异步命令不存在; 它是实际另一个事件。</span><span class="sxs-lookup"><span data-stu-id="3736a-294">\[Greg Young\] \[...\] an asynchronous command doesn't exist; it's actually another event.</span></span> <span data-ttu-id="3736a-295">如果我必须接受你发送我并引发事件，如果我不同意，它不再你告诉我做些什么。</span><span class="sxs-lookup"><span data-stu-id="3736a-295">If I must accept what you send me and raise an event if I disagree, it's no longer you telling me to do something.</span></span> <span data-ttu-id="3736a-296">是你告诉我执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="3736a-296">It's you telling me something has been done.</span></span> <span data-ttu-id="3736a-297">这似乎存在细微的差异，首先，但它有许多含义。</span><span class="sxs-lookup"><span data-stu-id="3736a-297">This seems like a slight difference at first, but it has many implications.</span></span>

<span data-ttu-id="3736a-298">异步命令极大地增加系统的复杂性，因为没有简单方法以指示失败。</span><span class="sxs-lookup"><span data-stu-id="3736a-298">Asynchronous commands greatly increase the complexity of a system, because there is no simple way to indicate failures.</span></span> <span data-ttu-id="3736a-299">因此，异步命令时，建议不要以外的缩放要求需要时或在特殊情况下通信通过消息内部的微服务。</span><span class="sxs-lookup"><span data-stu-id="3736a-299">Therefore, asynchronous commands are not recommended other than when scaling requirements are needed or in special cases when communicating the internal microservices through messaging.</span></span> <span data-ttu-id="3736a-300">在这些情况下，则必须设计单独的报告和恢复系统故障。</span><span class="sxs-lookup"><span data-stu-id="3736a-300">In those cases, you must design a separate reporting and recovery system for failures.</span></span>

<span data-ttu-id="3736a-301">在 eShopOnContainers 的初始版本，我们决定使用同步命令处理，从 HTTP 请求启动，而且受中介模式。</span><span class="sxs-lookup"><span data-stu-id="3736a-301">In the initial version of eShopOnContainers, we decided to use synchronous command processing, started from HTTP requests and driven by the Mediator pattern.</span></span> <span data-ttu-id="3736a-302">轻松，你能够返回成功或失败的进程，如[CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs)实现。</span><span class="sxs-lookup"><span data-stu-id="3736a-302">That easily allows you to return the success or failure of the process, as in the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) implementation.</span></span>

<span data-ttu-id="3736a-303">在任何情况下，这应该是基于你的应用程序的或微服务构成的业务要求的决策。</span><span class="sxs-lookup"><span data-stu-id="3736a-303">In any case, this should be a decision based on your application’s or microservice’s business requirements.</span></span>

## <a name="implementing-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a><span data-ttu-id="3736a-304">实现命令过程管道具有中介模式 (MediatR)</span><span class="sxs-lookup"><span data-stu-id="3736a-304">Implementing the command process pipeline with a mediator pattern (MediatR)</span></span>

<span data-ttu-id="3736a-305">作为示例实现，本指南建议使用进程内管道基于驱动器命令引入到中介模式和路由，在内存中，到正确的命令处理程序。</span><span class="sxs-lookup"><span data-stu-id="3736a-305">As a sample implementation, this guide proposes using the in-process pipeline based on the Mediator pattern to drive command ingestion and routing them, in memory, to the right command handlers.</span></span> <span data-ttu-id="3736a-306">本指南还将建议应用修饰符或[行为](https://github.com/jbogard/MediatR/wiki/Behaviors)以便分隔跨领域问题。</span><span class="sxs-lookup"><span data-stu-id="3736a-306">The guide also proposes applying decorators or [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) in order to separate cross-cutting concerns.</span></span>

<span data-ttu-id="3736a-307">有关在.NET 核心的实现，有一些多个开放源代码库实现中介模式。</span><span class="sxs-lookup"><span data-stu-id="3736a-307">For implementation in .NET Core, there are multiple open-source libraries available that implement the Mediator pattern.</span></span> <span data-ttu-id="3736a-308">本指南中使用的库[MediatR](https://github.com/jbogard/MediatR)开放源代码库 （由 Jimmy Bogard 创建），但你可使用另一种方法。</span><span class="sxs-lookup"><span data-stu-id="3736a-308">The library used in this guide is the [MediatR](https://github.com/jbogard/MediatR) open-source library (created by Jimmy Bogard), but you could use another approach.</span></span> <span data-ttu-id="3736a-309">MediatR 是一个小型和简单的库，您可以像处理处理内存中消息命令，在应用修饰器或行为时。</span><span class="sxs-lookup"><span data-stu-id="3736a-309">MediatR is a small and simple library that allows you to process in-memory messages like a command, while applying decorators or behaviors.</span></span>

<span data-ttu-id="3736a-310">使用中介模式可帮助你减少耦合并隔离请求工作的情况下，同时自动连接到的处理程序执行该工作的问题 — 在这种情况下，到命令处理程序。</span><span class="sxs-lookup"><span data-stu-id="3736a-310">Using the Mediator pattern helps you to reduce coupling and to isolate the concerns of the requested work, while automatically connecting to the handler that performs that work—in this case, to command handlers.</span></span>

<span data-ttu-id="3736a-311">查看本指南时，使用中介模式的另一个好理由已解释的 Jimmy Bogard:</span><span class="sxs-lookup"><span data-stu-id="3736a-311">Another good reason to use the Mediator pattern was explained by Jimmy Bogard when reviewing this guide:</span></span>

<span data-ttu-id="3736a-312">我认为它可能值得一提的是测试此处 – 它提供的很好的一致窗口，你的系统行为。</span><span class="sxs-lookup"><span data-stu-id="3736a-312">I think it might be worth mentioning testing here – it provides a nice consistent window into the behavior of your system.</span></span> <span data-ttu-id="3736a-313">请求中，响应扩展。我们已找到该方面中一致的方式运行测试的生成非常有价值。</span><span class="sxs-lookup"><span data-stu-id="3736a-313">Request-in, response-out. We’ve found that aspect quite valuable in building consistently behaving tests.</span></span>

<span data-ttu-id="3736a-314">首先，让我们看一下到控制器代码在实际使用的中介对象。</span><span class="sxs-lookup"><span data-stu-id="3736a-314">First, let us take a look to the controller code where you actually would use the mediator object.</span></span> <span data-ttu-id="3736a-315">如果你未使用的中介对象，你需要插入的所有依赖项该控制器中，如记录器对象和其他人。</span><span class="sxs-lookup"><span data-stu-id="3736a-315">If you were not using the mediator object, you would need to inject all the dependencies for that controller, things like a logger object and others.</span></span> <span data-ttu-id="3736a-316">因此，构造函数可能十分复杂。</span><span class="sxs-lookup"><span data-stu-id="3736a-316">Therefore, the constructor would be quite complicated.</span></span> <span data-ttu-id="3736a-317">另一方面，如果你使用中介对象，你的构造函数可以是控制器的很简单，只需少量的依赖项，而不是控制器的你将会获得有一个每个横切操作，如以下示例所示的许多依赖关系：</span><span class="sxs-lookup"><span data-stu-id="3736a-317">On the other hand, if you use the mediator object, the constructor of your controller can be a lot simpler, with just a few dependencies instead of many dependencies that you would have if you had one per cross-cutting operation, as in the following example:</span></span>

```csharp
public class OrdersController : Controller
{
    public OrdersController(IMediator mediator,
        IOrderQueries orderQueries)
    // ...
```

<span data-ttu-id="3736a-318">你可以看到中介来实现提供的干净且精益 Web API 控制器构造函数。</span><span class="sxs-lookup"><span data-stu-id="3736a-318">You can see that the mediator provides a clean and lean Web API controller constructor.</span></span> <span data-ttu-id="3736a-319">此外，在控制器方法中，代码将命令发送到中介对象是几乎一个行：</span><span class="sxs-lookup"><span data-stu-id="3736a-319">In addition, within the controller methods, the code to send a command to the mediator object is almost one line:</span></span>

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

<span data-ttu-id="3736a-320">为了使 MediatR 需要注意的你的命令处理程序类，你需要在 IoC 容器中注册的中介类和命令处理程序类。</span><span class="sxs-lookup"><span data-stu-id="3736a-320">In order for MediatR to be aware of your command handler classes, you need to register the mediator classes and the command handler classes in your IoC container.</span></span> <span data-ttu-id="3736a-321">默认情况下 MediatR 使用 Autofac 作为 IoC 容器中，但你还可以使用内置的 ASP.NET 核心 IoC 容器或 MediatR 支持的任何其他容器。</span><span class="sxs-lookup"><span data-stu-id="3736a-321">By default, MediatR uses Autofac as the IoC container, but you can also use the built-in ASP.NET Core IoC container or any other container supported by MediatR.</span></span>

<span data-ttu-id="3736a-322">下面的代码演示如何使用 Autofac 模块时注册中介的类型和命令。</span><span class="sxs-lookup"><span data-stu-id="3736a-322">The following code shows how to register Mediator’s types and commands when using Autofac modules.</span></span>

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

<span data-ttu-id="3736a-323">因为每个命令处理程序实现具有泛型 IAsyncRequestHandler 接口&lt;T&gt; ，然后检查 RegisteredAssemblyTypes 对象，因为该处理程序能够与相关命令与其处理程序，每个命令，关系述 CommandHandler 类，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="3736a-323">Because each command handler implements the interface with generic IAsyncRequestHandler&lt;T&gt; and then inspects the RegisteredAssemblyTypes object, the handler is able to relate each command with its command handler, because that relationship is stated in the CommandHandler class, as in the following example:</span></span>

```csharp
public class CreateOrderCommandHandler
  : IAsyncRequestHandler<CreateOrderCommand, bool>
{
```

<span data-ttu-id="3736a-324">这是命令处理程序与关联命令的代码。</span><span class="sxs-lookup"><span data-stu-id="3736a-324">This is the code that correlates commands with command handlers.</span></span> <span data-ttu-id="3736a-325">该处理程序只需简单的类，但它将继承 RequestHandler&lt;T&gt;，和 MediatR 可确保使用正确的负载调用获取它。</span><span class="sxs-lookup"><span data-stu-id="3736a-325">The handler is just a simple class, but it inherits from RequestHandler&lt;T&gt;, and MediatR makes sure it gets invoked with the correct payload.</span></span>

## <a name="applying-cross-cutting-concerns-when-processing-commands-with-the-mediator-and-decorator-patterns"></a><span data-ttu-id="3736a-326">在处理具有的中介和修饰器模式命令时应用的跨领域问题</span><span class="sxs-lookup"><span data-stu-id="3736a-326">Applying cross-cutting concerns when processing commands with the Mediator and Decorator patterns</span></span>

<span data-ttu-id="3736a-327">没有一件事情： 无法应用于中介管道的跨领域问题。</span><span class="sxs-lookup"><span data-stu-id="3736a-327">There is one more thing: being able to apply cross-cutting concerns to the mediator pipeline.</span></span> <span data-ttu-id="3736a-328">你还可以看到 Autofac 注册模块代码的末尾，它如何注册修饰器，具体而言，键入自定义的 LogDecorator 类。</span><span class="sxs-lookup"><span data-stu-id="3736a-328">You can also see at the end of the Autofac registration module code how it is registering a decorator type, specifically, a custom LogDecorator class.</span></span>

<span data-ttu-id="3736a-329">此外，请注意，eShopOnContainers 的未来版本它将迁移到[MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0)并转向[行为](https://github.com/jbogard/MediatR/wiki/Behaviors)而不是使用修饰器。</span><span class="sxs-lookup"><span data-stu-id="3736a-329">Again, note that a future version of eShopOnContainers it will migrate to [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) and move to [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) instead of using decorators.</span></span>

<span data-ttu-id="3736a-330">[LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs)类可以将以下代码，以记录有关正在执行的命令处理程序以及它是否成功与否的信息作为实现。</span><span class="sxs-lookup"><span data-stu-id="3736a-330">That [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) class can be implemented as the following code, which logs information about the command handler being executed and whether it was successful or not.</span></span>

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

<span data-ttu-id="3736a-331">只需通过实现此修饰器类和的修饰与其管道，通过 MediatR 处理的所有命令将日志都记录执行有关的信息。</span><span class="sxs-lookup"><span data-stu-id="3736a-331">Just by implementing this decorator class and by decorating the pipeline with it, all the commands processed through MediatR will be logging information about the execution.</span></span>

<span data-ttu-id="3736a-332">排序 microservice 也适用的基本的验证，第二个修饰器 eShopOnContainers [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs)依赖于的类[FluentValidation](https://github.com/JeremySkinner/FluentValidation)库，如中所示以下代码：</span><span class="sxs-lookup"><span data-stu-id="3736a-332">The eShopOnContainers ordering microservice also applies a second decorator for basic validations, the [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) class that relies on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, as shown in the following code:</span></span>

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

<span data-ttu-id="3736a-333">然后，根据[FluentValidation](https://github.com/JeremySkinner/FluentValidation)库，我们将创建与 CreateOrderCommand，一起传递，如以下代码所示的数据验证：</span><span class="sxs-lookup"><span data-stu-id="3736a-333">Then, based on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, we created validation for the data passed with CreateOrderCommand, as in the following code:</span></span>

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

<span data-ttu-id="3736a-334">你可以创建其他验证。</span><span class="sxs-lookup"><span data-stu-id="3736a-334">You could create additional validations.</span></span> <span data-ttu-id="3736a-335">这是实现您命令验证一非常干净且简洁方法。</span><span class="sxs-lookup"><span data-stu-id="3736a-335">This is a very clean and elegant way to implement your command validations.</span></span>

<span data-ttu-id="3736a-336">以类似的方式，可以实现其他方面或你想要应用于命令时处理它们的跨领域问题的其他修饰符。</span><span class="sxs-lookup"><span data-stu-id="3736a-336">In a similar way, you could implement other decorators for additional aspects or cross-cutting concerns that you want to apply to commands when handling them.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="3736a-337">其他资源</span><span class="sxs-lookup"><span data-stu-id="3736a-337">Additional resources</span></span>

##### <a name="the-mediator-pattern"></a><span data-ttu-id="3736a-338">中介模式</span><span class="sxs-lookup"><span data-stu-id="3736a-338">The mediator pattern</span></span>

-   <span data-ttu-id="3736a-339">**中介模式**
    [*https://en.wikipedia.org/wiki/Mediator\_模式*](https://en.wikipedia.org/wiki/Mediator_pattern)</span><span class="sxs-lookup"><span data-stu-id="3736a-339">**Mediator pattern**
[*https://en.wikipedia.org/wiki/Mediator\_pattern*](https://en.wikipedia.org/wiki/Mediator_pattern)</span></span>

##### <a name="the-decorator-pattern"></a><span data-ttu-id="3736a-340">修饰器模式</span><span class="sxs-lookup"><span data-stu-id="3736a-340">The decorator pattern</span></span>

-   <span data-ttu-id="3736a-341">**修饰器模式**
    [*https://en.wikipedia.org/wiki/Decorator\_模式*](https://en.wikipedia.org/wiki/Decorator_pattern)</span><span class="sxs-lookup"><span data-stu-id="3736a-341">**Decorator pattern**
[*https://en.wikipedia.org/wiki/Decorator\_pattern*](https://en.wikipedia.org/wiki/Decorator_pattern)</span></span>

##### <a name="mediatr-jimmy-bogard"></a><span data-ttu-id="3736a-342">MediatR (Jimmy Bogard)</span><span class="sxs-lookup"><span data-stu-id="3736a-342">MediatR (Jimmy Bogard)</span></span>

-   <span data-ttu-id="3736a-343">**MediatR。**</span><span class="sxs-lookup"><span data-stu-id="3736a-343">**MediatR.**</span></span> <span data-ttu-id="3736a-344">GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="3736a-344">GitHub repo.</span></span>
    [<span data-ttu-id="3736a-345">*https://github.com/jbogard/MediatR*</span><span class="sxs-lookup"><span data-stu-id="3736a-345">*https://github.com/jbogard/MediatR*</span></span>](https://github.com/jbogard/MediatR)

-   <span data-ttu-id="3736a-346">**使用 MediatR 和 AutoMapper CQRS**
    [*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)</span><span class="sxs-lookup"><span data-stu-id="3736a-346">**CQRS with MediatR and AutoMapper**
[*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)</span></span>

-   <span data-ttu-id="3736a-347">**你的控制器置于饮食： 文章和命令。** 
     [ *https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)</span><span class="sxs-lookup"><span data-stu-id="3736a-347">**Put your controllers on a diet: POSTs and commands.**
[*https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)</span></span>

-   <span data-ttu-id="3736a-348">**有关与中介管道的跨领域问题**
    [*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)</span><span class="sxs-lookup"><span data-stu-id="3736a-348">**Tackling cross-cutting concerns with a mediator pipeline**
[*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)</span></span>

-   <span data-ttu-id="3736a-349">**CQRS 和 REST： 完全匹配**
    [*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)</span><span class="sxs-lookup"><span data-stu-id="3736a-349">**CQRS and REST: the perfect match**
[*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)</span></span>

-   <span data-ttu-id="3736a-350">**MediatR 管道示例**
    [*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)</span><span class="sxs-lookup"><span data-stu-id="3736a-350">**MediatR Pipeline Examples**
[*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)</span></span>

-   <span data-ttu-id="3736a-351">**垂直切片测试装置，用于 MediatR 和 ASP.NET Core**
    *<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>*</span><span class="sxs-lookup"><span data-stu-id="3736a-351">**Vertical Slice Test Fixtures for MediatR and ASP.NET Core**
*<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/> *</span></span>

-   <span data-ttu-id="3736a-352">**发布的 Microsoft 依赖关系注入 MediatR 扩展**
    [*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)</span><span class="sxs-lookup"><span data-stu-id="3736a-352">**MediatR Extensions for Microsoft Dependency Injection Released**
[*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)</span></span>

##### <a name="fluent-validation"></a><span data-ttu-id="3736a-353">Fluent 验证</span><span class="sxs-lookup"><span data-stu-id="3736a-353">Fluent validation</span></span>

-   <span data-ttu-id="3736a-354">**Jeremy Skinner。FluentValidation。**</span><span class="sxs-lookup"><span data-stu-id="3736a-354">**Jeremy Skinner. FluentValidation.**</span></span> <span data-ttu-id="3736a-355">GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="3736a-355">GitHub repo.</span></span>
    [<span data-ttu-id="3736a-356">*https://github.com/JeremySkinner/FluentValidation*</span><span class="sxs-lookup"><span data-stu-id="3736a-356">*https://github.com/JeremySkinner/FluentValidation*</span></span>](https://github.com/JeremySkinner/FluentValidation)

>[!div class="step-by-step"]
<span data-ttu-id="3736a-357">[以前](microservice-application-layer-web-api-design.md) [下一步] (.../implement-resilient-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="3736a-357">[Previous] (microservice-application-layer-web-api-design.md) [Next] (../implement-resilient-applications/index.md)</span></span>
