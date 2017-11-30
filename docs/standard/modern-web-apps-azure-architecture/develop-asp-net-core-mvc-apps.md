---
title: "开发 ASP.NET Core MVC 应用"
description: "设计使用 ASP.NET Core 和 Azure 的现代 Web 应用程序 |开发 ASP.NET 核心 MVC 应用程序"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 54e7ed6fff9ac709e411d0ac1e345c63fd753201
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2017
---
# <a name="develop-aspnet-core-mvc-apps"></a><span data-ttu-id="b2ea6-103">开发 ASP.NET Core MVC 应用程序</span><span class="sxs-lookup"><span data-stu-id="b2ea6-103">Develop ASP.NET Core MVC Apps</span></span>

> <span data-ttu-id="b2ea6-104">"它并不重要若要获取其右第一次。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-104">"It's not important to get it right the first time.</span></span> <span data-ttu-id="b2ea6-105">它是非常重要，以使其正确最后一次。"</span><span class="sxs-lookup"><span data-stu-id="b2ea6-105">It's vitally important to get it right the last time."</span></span>  
> <span data-ttu-id="b2ea6-106">_-Andrew Hunt 和 David Thomas_</span><span class="sxs-lookup"><span data-stu-id="b2ea6-106">_- Andrew Hunt and David Thomas_</span></span>

## <a name="summary"></a><span data-ttu-id="b2ea6-107">摘要</span><span class="sxs-lookup"><span data-stu-id="b2ea6-107">Summary</span></span>

<span data-ttu-id="b2ea6-108">ASP.NET 核心是一个跨平台的开放源代码框架，用于生成现代的云优化 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-108">ASP.NET Core is a cross-platform, open-source framework for building modern cloud-optimized web applications.</span></span> <span data-ttu-id="b2ea6-109">ASP.NET Core 应用程序是轻量和模块化，具有依赖关系注入，在更高的可测试性和可维护性中启用的内置支持。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-109">ASP.NET Core apps are lightweight and modular, with built-in support for dependency injection, enabling in greater testability and maintainability.</span></span> <span data-ttu-id="b2ea6-110">ASP.NET 核心结合 MVC，支持构建除了基于视图的应用的现代 web Api，是用于生成 web 应用程序的企业功能强大的框架。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-110">Combined with MVC, which supports building modern web APIs in addition to view-based apps, ASP.NET Core is a powerful framework with which to build enterprise web applications.</span></span>

## <a name="mapping-requests-to-responses"></a><span data-ttu-id="b2ea6-111">将请求映射到响应</span><span class="sxs-lookup"><span data-stu-id="b2ea6-111">Mapping Requests to Responses</span></span>

<span data-ttu-id="b2ea6-112">其核心 ASP.NET Core 应用将传入请求映射到传出的响应。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-112">At its heart, ASP.NET Core apps map incoming requests to outgoing responses.</span></span> <span data-ttu-id="b2ea6-113">在低级别，这使用中间件，完成和简单的 ASP.NET Core 应用程序和微服务可能包含单独的自定义的中间件。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-113">At a low level, this is done with middleware, and simple ASP.NET Core apps and microservices may be comprised solely of custom middleware.</span></span> <span data-ttu-id="b2ea6-114">在使用时 ASP.NET 核心 MVC，可在某种程度上更高级别中，考虑按照*路由*，*控制器*，和*操作*。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-114">When using ASP.NET Core MVC, you can work at a somewhat higher level, thinking in terms of *routes*, *controllers*, and *actions*.</span></span> <span data-ttu-id="b2ea6-115">每个传入请求与应用程序的路由表进行比较，如果找到匹配的路由，则调用 （属于一个控制器） 关联的操作方法来处理该请求。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-115">Each incoming request is compared with the application's routing table, and if a matching route is found, the associated action method (belonging to a controller) is called to handle the request.</span></span> <span data-ttu-id="b2ea6-116">如果找到匹配的路由，则调用错误处理程序 （在此情况下，返回 NotFound 结果）。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-116">If no matching route is found, an error handler (in this case, returning a NotFound result) is called.</span></span>

<span data-ttu-id="b2ea6-117">ASP.NET 核心 MVC 应用程序可以使用传统的路由、 属性的路由，或两者。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-117">ASP.NET Core MVC apps can use conventional routes, attribute routes, or both.</span></span> <span data-ttu-id="b2ea6-118">在代码中，指定路由定义常规路由*约定*在下面的示例中使用类似的语法：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-118">Conventional routes are defined in code, specifying routing *conventions* using syntax like in the example below:</span></span>

```csharp
app.UseMvc(routes =>;
{
    routes.MapRoute("default","{controller=Home}/{action=Index}/{id?}");
});
```

<span data-ttu-id="b2ea6-119">在此示例中，名为"default"的路由具有已添加到路由表。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-119">In this example, a route named "default" has been added to the routing table.</span></span> <span data-ttu-id="b2ea6-120">它定义带有占位符的路由模板*控制器*，*操作*，和*id*。控制器和操作占位符具有指定的默认值 ("主页"和"索引"，分别)，和是可选的 id 占位符 (借助于"？"应用于它)。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-120">It defines a route template with placeholders for *controller*, *action*, and *id*. The controller and action placeholders have default specified ("Home" and "Index", respectively), and the id placeholder is optional (by virtue of a "?" applied to it).</span></span> <span data-ttu-id="b2ea6-121">约定定义此处请求的第一部分应对应的状态为控制器上，与操作的第二个部分的名称，然后如有必要第三部分将表示一个 id 参数。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-121">The convention defined here states that the first part of a request should correspond to the name of the controller, the second part to the action, and then if necessary a third part will represent an id parameter.</span></span> <span data-ttu-id="b2ea6-122">传统路由通常在一个位置对于应用程序，如中定义的启动类中的配置方法。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-122">Conventional routes are typically defined in one place for the application, such as in the Configure method in the Startup class.</span></span>

<span data-ttu-id="b2ea6-123">属性的路由将直接应用到控制器和操作而不是全局范围内指定。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-123">Attribute routes are applied to controllers and actions directly, rather than specified globally.</span></span> <span data-ttu-id="b2ea6-124">这具有的优势是使它们更容易可见时要查看特定的方法，但意思路由的信息将不会在应用程序中的一个位置。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-124">This has the advantage of making them much more discoverable when you're looking at a particular method, but does mean that routing information is not kept in one place in the application.</span></span> <span data-ttu-id="b2ea6-125">使用属性的路由，你可以轻松地指定为某个给定操作的多个路由，以及组合控制器和操作之间的路由。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-125">With attribute routes, you can easily specify multiple routes for a given action, as well as combine routes between controllers and actions.</span></span> <span data-ttu-id="b2ea6-126">例如: </span><span class="sxs-lookup"><span data-stu-id="b2ea6-126">For example:</span></span>

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
```

<span data-ttu-id="b2ea6-127">可以在 [HttpGet] 上指定路由和单独的类似属性，无需添加 [路由\]属性。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-127">Routes can be specified on [HttpGet] and similar attributes, avoiding the need to add separate [Route\] attributes.</span></span> <span data-ttu-id="b2ea6-128">属性的路由还可以使用令牌来减少需要重复控制器或操作名称，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-128">Attribute routes can also use tokens to reduce the need to repeat controller or action names, as shown below:</span></span>

```csharp
[Route("[controller\]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index()
}
```

<span data-ttu-id="b2ea6-129">一旦在找到给定的请求匹配到某个路由，但操作之前调用方法，将执行 ASP.NET 核心 MVC[模型绑定](https://docs.microsoft.com/aspnet/core/mvc/models/model-binding)和[模型验证](https://docs.microsoft.com/aspnet/core/mvc/models/validation)针对此请求。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-129">Once a given request has been matched to a route, but before the action method is called, ASP.NET Core MVC will perform [model binding](https://docs.microsoft.com/aspnet/core/mvc/models/model-binding) and [model validation](https://docs.microsoft.com/aspnet/core/mvc/models/validation) on the request.</span></span> <span data-ttu-id="b2ea6-130">模型绑定负责将传入的 HTTP 数据转换为.NET 类型指定为参数的操作方法的调用。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-130">Model binding is responsible for converting incoming HTTP data into the .NET types specified as parameters of the action method to be called.</span></span> <span data-ttu-id="b2ea6-131">例如，如果操作方法预期 int id 参数，模型绑定将尝试提供从值作为请求的一部分提供此参数。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-131">For example, if the action method expects an int id parameter, model binding will attempt to provide this parameter from a value provided as part of the request.</span></span> <span data-ttu-id="b2ea6-132">为此，请模型绑定查找已发布的窗体中的值、 本身，路由中的值和查询字符串值。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-132">To do so, model binding looks for values in a posted form, values in the route itself, and query string values.</span></span> <span data-ttu-id="b2ea6-133">假设找到 id 值，它将转换为整数之前正传入到操作方法。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-133">Assuming an id value is found, it will be converted to an integer before being passed into the action method.</span></span>

<span data-ttu-id="b2ea6-134">绑定模型之后但在调用的操作方法之前，将执行模型验证。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-134">After binding the model but before calling the action method, model validation occurs.</span></span> <span data-ttu-id="b2ea6-135">模型验证模型的类型，使用可选属性，并且可以帮助确保提供的模型对象符合某些数据要求。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-135">Model validation uses optional attributes on the model type, and can help ensure that the provided model object conforms to certain data requirements.</span></span> <span data-ttu-id="b2ea6-136">某些值可以指定为必需的也限制为特定长度或数值范围，等等。如果指定的验证属性但模型不符合其要求，该属性 ModelState.IsValid 将为 false，并将可用于将发送到客户端发出请求的失败的验证规则集。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-136">Certain values may be specified as required, or limited to a certain length or numeric range, etc. If validation attributes are specified but the model does not conform to their requirements, the property ModelState.IsValid will be false, and the set of failing validation rules will be available to send to the client making the request.</span></span>

<span data-ttu-id="b2ea6-137">如果你使用的模型验证，你应确保始终检查模型在执行任何状态更改的命令，就以确保数据未损坏你的应用程序之前有效。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-137">If you are using model validation, you should be sure to always check that the model is valid before performing any state-altering commands, to ensure your app is not corrupted by invalid data.</span></span> <span data-ttu-id="b2ea6-138">你可以使用[筛选器](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters)以避免需要添加此代码，在每个操作。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-138">You can use a [filter](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) to avoid the need to add code for this in every action.</span></span> <span data-ttu-id="b2ea6-139">ASP.NET 核心 MVC 筛选器提供一种截获的请求，组的过程，以便可以在目标的基础上应用常见策略和跨领域问题。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-139">ASP.NET Core MVC filters offer a way of intercepting groups of requests, so that common policies and cross-cutting concerns can be applied on a targeted basis.</span></span> <span data-ttu-id="b2ea6-140">与单个操作，整个控制器或全局应用程序，可以应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-140">Filters can be applied to individual actions, whole controllers, or globally for an application.</span></span>

<span data-ttu-id="b2ea6-141">对于 web Api，ASP.NET 核心 MVC 支持[*内容协商*](https://docs.microsoft.com/aspnet/core/mvc/models/formatting)，允许以指定应如何格式化响应的请求。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-141">For web APIs, ASP.NET Core MVC supports [*content negotiation*](https://docs.microsoft.com/aspnet/core/mvc/models/formatting), allowing requests to specify how responses should be formatted.</span></span> <span data-ttu-id="b2ea6-142">根据请求中提供的标头，操作返回的数据将格式化 XML、 JSON 或另一个受支持的格式中的响应。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-142">Based on headers provided in the request, actions returning data will format the response in XML, JSON, or another supported format.</span></span> <span data-ttu-id="b2ea6-143">此功能可以提供相同的 API，由具有不同的数据格式要求的多个客户端使用。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-143">This feature enables the same API to be used by multiple clients with different data format requirements.</span></span>

> ### <a name="references--mapping-requests-to-responses"></a><span data-ttu-id="b2ea6-144">引用 – 将请求映射到响应</span><span class="sxs-lookup"><span data-stu-id="b2ea6-144">References – Mapping Requests to Responses</span></span>
> - <span data-ttu-id="b2ea6-145">**路由到控制器操作**
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing></span><span class="sxs-lookup"><span data-stu-id="b2ea6-145">**Routing to Controller Actions**
<https://docs.microsoft.com/aspnet/core/mvc/controllers/routing></span></span>
> - <span data-ttu-id="b2ea6-146">**模型绑定**https://docs.microsoft.com/aspnet/core/mvc/models/model-binding</span><span class="sxs-lookup"><span data-stu-id="b2ea6-146">**Model Binding** https://docs.microsoft.com/aspnet/core/mvc/models/model-binding</span></span>
> - <span data-ttu-id="b2ea6-147">**模型验证**
> <https://docs.microsoft.com/aspnet/core/mvc/models/validation></span><span class="sxs-lookup"><span data-stu-id="b2ea6-147">**Model Validation**
<https://docs.microsoft.com/aspnet/core/mvc/models/validation></span></span>
> - <span data-ttu-id="b2ea6-148">**筛选器**https://docs.microsoft.com/aspnet/core/mvc/controllers/filters</span><span class="sxs-lookup"><span data-stu-id="b2ea6-148">**Filters** https://docs.microsoft.com/aspnet/core/mvc/controllers/filters</span></span>

## <a name="working-with-dependencies"></a><span data-ttu-id="b2ea6-149">使用依赖关系</span><span class="sxs-lookup"><span data-stu-id="b2ea6-149">Working with Dependencies</span></span>

<span data-ttu-id="b2ea6-150">ASP.NET 核心内置支持和内部使用的一种技术称为[依赖关系注入](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-150">ASP.NET Core has built-in support for and internally makes use of a technique known as [dependency injection](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection).</span></span> <span data-ttu-id="b2ea6-151">依赖关系注入是一种技术，启用应用程序的不同部分之间的松散耦合。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-151">Dependency injection is a technique that enabled loose coupling between different parts of an application.</span></span> <span data-ttu-id="b2ea6-152">松散耦合是需要的因为这样可以更轻松地隔离的应用程序，允许进行测试或替换部分。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-152">Looser coupling is desirable because it makes it easier to isolate parts of the application, allowing for testing or replacement.</span></span> <span data-ttu-id="b2ea6-153">它还使可能性变小，应用程序的一部分中的更改会产生意外的影响应用程序中的其他位置。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-153">It also makes it less likely that a change in one part of the application will have an unexpected impact somewhere else in the application.</span></span> <span data-ttu-id="b2ea6-154">依赖关系注入的依赖项反向原则，为基础，通常是实现打开/关闭原则关键。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-154">Dependency injection is based on the dependency inversion principle, and is often key to achieving the open/closed principle.</span></span> <span data-ttu-id="b2ea6-155">当评估你的应用程序如何使用其依赖项，请注意[静态粘贴](http://deviq.com/static-cling/)代码告知，并记住 aphorism"[新是粘附](http://ardalis.com/new-is-glue)。"</span><span class="sxs-lookup"><span data-stu-id="b2ea6-155">When evaluating how your application works with its dependencies, beware of the [static cling](http://deviq.com/static-cling/) code smell, and remember the aphorism "[new is glue](http://ardalis.com/new-is-glue)."</span></span>

<span data-ttu-id="b2ea6-156">当你的类对静态方法进行调用或访问静态属性，其基础结构上具有副作用或依赖关系，静态粘贴时发生。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-156">Static cling occurs when your classes make calls to static methods, or access static properties, which have side effects or dependencies on infrastructure.</span></span> <span data-ttu-id="b2ea6-157">例如，如果你的一个方法调用静态方法，后者反过来将写入数据库，你的方法是紧密耦合到数据库。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-157">For example, if you have a method that calls a static method, which in turn writes to a database, your method is tightly coupled to the database.</span></span> <span data-ttu-id="b2ea6-158">将中断该数据库调用的任何内容将中断你的方法。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-158">Anything that breaks that database call will break your method.</span></span> <span data-ttu-id="b2ea6-159">测试此类方法是训练非常困难，因为此类测试需要商业模拟库来模拟静态调用，或仅使用一个测试数据库就地进行测试。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-159">Testing such methods is notoriously difficult, since such tests either require commercial mocking libraries to mock the static calls, or can only be tested with a test database in place.</span></span> <span data-ttu-id="b2ea6-160">没有任何依赖于基础结构，尤其是那些完全无状态的的静态调用是合适调用，并让不影响耦合或 （超出耦合到静态调用本身的代码） 的可测试性的。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-160">Static calls that don't have any dependence on infrastructure, especially those that are completely stateless, are fine to call and have no impact on coupling or testability (beyond coupling code to the static call itself).</span></span>

<span data-ttu-id="b2ea6-161">许多开发人员了解静态粘贴和全局状态的风险，但将仍紧密耦合到通过直接实例化的特定实现其代码。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-161">Many developers understand the risks of static cling and global state, but will still tightly couple their code to specific implementations through direct instantiation.</span></span> <span data-ttu-id="b2ea6-162">"新 is 粘附"要作为此耦合，提醒和不使用新的关键字常规 condemnation。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-162">"New is glue" is meant to be a reminder of this coupling, and not a general condemnation of the use of the new keyword.</span></span> <span data-ttu-id="b2ea6-163">就像使用静态方法调用，通常具有没有外部依赖项的类型的新实例不要不紧密耦合代码到实现详细信息或使测试更加困难。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-163">Just as with static method calls, new instances of types that have no external dependencies typically do not tightly couple code to implementation details or make testing more difficult.</span></span> <span data-ttu-id="b2ea6-164">但是，类实例化，每次需要花费只是一小段时间考虑是否它有意义硬编码到该特定实例中的特定位置，或如果它可能会更好的设计，以请求为依赖项的该实例。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-164">But each time a class is instantiated, take just a brief moment to consider whether it makes sense to hard-code that specific instance in that particular location, or if it would be a better design to request that instance as a dependency.</span></span>

### <a name="declare-your-dependencies"></a><span data-ttu-id="b2ea6-165">声明依赖项</span><span class="sxs-lookup"><span data-stu-id="b2ea6-165">Declare Your Dependencies</span></span>

<span data-ttu-id="b2ea6-166">ASP.NET 核心围绕具有方法和类声明依赖项，以及请求这些作为自变量。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-166">ASP.NET Core is built around having methods and classes declare their dependencies, requesting them as arguments.</span></span> <span data-ttu-id="b2ea6-167">ASP.NET 应用程序通常在一个 Startup 类中, 进行设置其自身配置为支持在多个点的依赖关系注入。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-167">ASP.NET applications are typically set up in a Startup class, which itself is configured to support dependency injection at several points.</span></span> <span data-ttu-id="b2ea6-168">如果你的启动类具有构造函数，它可以请求通过构造函数的依赖关系如下所示：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-168">If your Startup class has a constructor, it can request dependencies through the constructor, like so:</span></span>

```csharp
public class Startup
{
    public Startup(IHostingEnvironment env)
    {
        var builder = new ConfigurationBuilder()
        .SetBasePath(env.ContentRootPath)
        .AddJsonFile("appsettings.json", optional: false, reloadOnChange: true)
        .AddJsonFile(\$"appsettings.{env.EnvironmentName}.json", optional: true);
    }
}
```

<span data-ttu-id="b2ea6-169">Startup 类的有趣，在于它没有显式类型要求。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-169">The Startup class is interesting in that there are no explicit type requirements for it.</span></span> <span data-ttu-id="b2ea6-170">它不会从的特殊启动基类继承，也不实现任何特定的接口。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-170">It doesn't inherit from a special Startup base class, nor does it implement any particular interface.</span></span> <span data-ttu-id="b2ea6-171">你可以在您或不是，为其提供一个构造函数，并可以指定任意多个构造函数参数。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-171">You can give it a constructor, or not, and you can specify as many parameters on the constructor as you want.</span></span> <span data-ttu-id="b2ea6-172">当 web 主机已配置为用于你的应用程序启动时，它将调用您告诉它要使用，Startup 类，并且将使用依赖关系注入来填充 Startup 类需要任何依赖关系。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-172">When the web host you've configured for your application starts, it will call the Startup class you've told it to use, and will use dependency injection to populate any dependencies the Startup class requires.</span></span> <span data-ttu-id="b2ea6-173">当然，如果请求未配置 ASP.NET Core 所用的服务容器中的参数，你将收到异常，但只要坚持依赖项容器知道，你可以请求所需的任何内容。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-173">Of course, if you request parameters that aren't configured in the services container used by ASP.NET Core, you'll get an exception, but as long as you stick to dependencies the container knows about, you can request anything you want.</span></span>

<span data-ttu-id="b2ea6-174">在创建启动实例时，依赖关系注入已内置到从一开始，就你 ASP.NET Core 应用。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-174">Dependency injection is built into your ASP.NET Core apps right from the start, when you create the Startup instance.</span></span> <span data-ttu-id="b2ea6-175">它不会阻止为 Startup 类的存在。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-175">It doesn't stop there for the Startup class.</span></span> <span data-ttu-id="b2ea6-176">你还可以请求中的配置方法的依赖关系：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-176">You can also request dependencies in the Configure method:</span></span>

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

<span data-ttu-id="b2ea6-177">ConfigureServices 方法是此行为; 的例外它必须采用一个参数的类型 IServiceCollection。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-177">The ConfigureServices method is the exception to this behavior; it must take just one parameter of type IServiceCollection.</span></span> <span data-ttu-id="b2ea6-178">它实际上不需要以支持依赖关系注入，因为一方面它负责将对象添加到服务容器中，并且在其他它有权访问通过 IServiceCollection 参数的所有当前配置服务。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-178">It doesn't really need to support dependency injection, since on the one hand it is responsible for adding objects to the services container, and on the other it has access to all currently configured services via the IServiceCollection parameter.</span></span> <span data-ttu-id="b2ea6-179">因此，你可以使用 ASP.NET 核心服务集合中的 Startup 类，通过请求所需的服务作为参数或通过使用在 ConfigureServices IServiceCollection 每个部分中定义的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-179">Thus, you can work with dependencies defined in the ASP.NET Core services collection in every part of the Startup class, either by requesting the needed service as a parameter or by working with the IServiceCollection in ConfigureServices.</span></span>

> [!NOTE]
> <span data-ttu-id="b2ea6-180">如果你需要确保某些服务可供你 Startup 类，则可以配置这些使用 WebHostBuilder 和其 ConfigureServices 方法。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-180">If you need to ensure certain services are available to your Startup class, you can configure them using WebHostBuilder and its ConfigureServices method.</span></span>

<span data-ttu-id="b2ea6-181">Startup 类是用于您如何构建 ASP.NET Core 应用程序，从控制器到你自己的服务筛选器的中间件的其他部分的模型。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-181">The Startup class is a model for how you should structure other parts of your ASP.NET Core application, from Controllers to Middleware to Filters to your own Services.</span></span> <span data-ttu-id="b2ea6-182">在每种情况下，你应遵循[显式依赖关系原则](http://deviq.com/explicit-dependencies-principle/)、 请求依赖项而不是直接创建它们，并利用在整个应用程序的依赖关系注入。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-182">In each case, you should follow the [Explicit Dependencies Principle](http://deviq.com/explicit-dependencies-principle/), requesting your dependencies rather than directly creating them, and leveraging dependency injection throughout your application.</span></span> <span data-ttu-id="b2ea6-183">请注意的位置和方式直接实例化实现中，尤其是服务和使用基础结构或产生负面影响的对象。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-183">Be careful of where and how you directly instantiate implementations, especially services and objects that work with infrastructure or have side effects.</span></span> <span data-ttu-id="b2ea6-184">更喜欢使用在将应用程序核心中定义并在作为自变量传递到对特定的实现类型的硬编码引用的抽象。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-184">Prefer working with abstractions defined in your application core and passed in as arguments to hardcoding references to specific implementation types.</span></span>

## <a name="structuring-the-application"></a><span data-ttu-id="b2ea6-185">构建应用程序</span><span class="sxs-lookup"><span data-stu-id="b2ea6-185">Structuring the Application</span></span>

<span data-ttu-id="b2ea6-186">整体应用程序通常具有单一入口点。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-186">Monolithic applications typically have a single entry point.</span></span> <span data-ttu-id="b2ea6-187">对于 ASP.NET Core 的 web 应用程序，将 ASP.NET 核心 web 项目的入口点。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-187">In the case of an ASP.NET Core web application, the entry point will be the ASP.NET Core web project.</span></span> <span data-ttu-id="b2ea6-188">但是，这并不意味着解决方案应包含单个项目。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-188">However, that doesn't mean the solution should consist of just a single project.</span></span> <span data-ttu-id="b2ea6-189">它可用于分解到不同的层应用程序，以便按照关注点分离。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-189">It's useful to break up the application into different layers in order to follow separation of concerns.</span></span> <span data-ttu-id="b2ea6-190">分解成层后，超出文件夹到单独的项目，可帮助实现更好地封装很有帮助。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-190">Once broken up into layers, it's helpful to go beyond folders to separate projects, which can help achieve better encapsulation.</span></span> <span data-ttu-id="b2ea6-191">最好的方法来实现这些目标与 ASP.NET Core 应用程序是干净的体系结构中第 5 章所述的变体。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-191">The best approach to achieve these goals with an ASP.NET Core application is a variation of the Clean Architecture discussed in chapter 5.</span></span> <span data-ttu-id="b2ea6-192">此方法时，以下应用程序的解决方案将包含单独的库 UI、 基础结构和 ApplicationCore。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-192">Following this approach, the application's solution will be comprised of separate libraries for the UI, Infrastructure, and ApplicationCore.</span></span>

<span data-ttu-id="b2ea6-193">除了这些项目，单独的测试项目也包含 （第 9 章讨论测试）。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-193">In addition to these projects, separate test projects are included as well (Testing is discussed in Chapter 9).</span></span>

<span data-ttu-id="b2ea6-194">应用程序的对象模型和接口应该放置 ApplicationCore 项目中。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-194">The application's object model and interfaces should be placed in the ApplicationCore project.</span></span> <span data-ttu-id="b2ea6-195">此项目将尽可能情况下，具有尽可能少的依赖项和其他项目解决方案中的将引用它。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-195">This project will have as few dependencies as possible, and the other projects in the solution will reference it.</span></span> <span data-ttu-id="b2ea6-196">需要保留的业务实体定义在 ApplicationCore 项目中，是不直接依赖于基础结构的服务。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-196">Business entities that need to be persisted are defined in the ApplicationCore project, as are services that do not directly depend on infrastructure.</span></span>

<span data-ttu-id="b2ea6-197">实现详细信息，例如如何执行持久性或可能如何将通知发送给用户，将保留在基础结构项目。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-197">Implementation details, such as how persistence is performed or how notifications might be sent to a user, are kept in the Infrastructure project.</span></span> <span data-ttu-id="b2ea6-198">此项目将引用特定于实现的包，例如实体框架核心，但不是应公开有关这些实现在项目外的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-198">This project will reference implementation-specific packages such as Entity Framework Core, but should not expose details about these implementations outside of the project.</span></span> <span data-ttu-id="b2ea6-199">基础结构服务和存储库，应实现 ApplicationCore 项目中定义的接口，并且其持久性实现负责检索并将存储在 ApplicationCore 中定义的实体。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-199">Infrastructure services and repositories should implement interfaces that are defined in the ApplicationCore project, and its persistence implementations are responsible for retrieving and storing entities defined in ApplicationCore.</span></span>

<span data-ttu-id="b2ea6-200">ASP.NET 核心项目本身负责任何 UI 级别问题，但不是应包含业务逻辑或基础结构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-200">The ASP.NET Core project itself is responsible for any UI level concerns, but should not include business logic or infrastructure details.</span></span> <span data-ttu-id="b2ea6-201">实际上，理想情况下它不应即使有依赖于基础结构项目，这将有助于确保将两个项目之间没有依赖关系引入意外。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-201">In fact, ideally it shouldn't even have a dependency on the Infrastructure project, which will help ensure no dependency between the two projects is introduced accidentally.</span></span> <span data-ttu-id="b2ea6-202">可以使用 StructureMap，允许你在注册表中的每个项目的类中定义 DI 规则等第三方 DI 容器实现此操作。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-202">This can be achieved using a third-party DI container like StructureMap, which allows you to define DI rules in Registry classes in each project.</span></span>

<span data-ttu-id="b2ea6-203">分离中实现的详细信息的应用程序的另一种方法是让应用程序调用微服务，可能是部署在单个 Docker 容器中。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-203">Another approach to decoupling the application from implementation details is to have the application call microservices, perhaps deployed in individual Docker containers.</span></span> <span data-ttu-id="b2ea6-204">这提供的问题和分离比 DI 利用两个项目之间的更多分离，但具有附加的复杂性。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-204">This provides even greater separation of concerns and decoupling than leveraging DI between two projects, but has additional complexity.</span></span>

### <a name="feature-organization"></a><span data-ttu-id="b2ea6-205">功能组织</span><span class="sxs-lookup"><span data-stu-id="b2ea6-205">Feature Organization</span></span>

<span data-ttu-id="b2ea6-206">默认情况下，ASP.NET Core 应用程序会将其文件夹结构，以包含控制器和视图，并经常 Viewmodel。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-206">By default, ASP.NET Core applications organize their folder structure to include Controllers and Views, and frequently ViewModels.</span></span> <span data-ttu-id="b2ea6-207">客户端代码，以支持这些服务器端结构通常的 wwwroot 文件夹中单独存储。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-207">Client-side code to support these server-side structures is typically stored separately in the wwwroot folder.</span></span> <span data-ttu-id="b2ea6-208">但是，由于通常处理任何给定的功能要求这些文件夹之间跳转大型应用程序可能会遇到与此组织的问题。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-208">However, large applications may encounter problems with this organization, since working on any given feature often requires jumping between these folders.</span></span> <span data-ttu-id="b2ea6-209">这将得到的文件和子文件夹中每个文件夹数增大时，导致了极大的解决方案资源管理器在滚动越来越困难。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-209">This gets more and more difficult as the number of files and subfolders in each folder grows, resulting in a great deal of scrolling through Solution Explorer.</span></span> <span data-ttu-id="b2ea6-210">此问题的一种解决方案是将应用程序代码通过组织*功能*而不是按文件类型。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-210">One solution to this problem is to organize application code by *feature* instead of by file type.</span></span> <span data-ttu-id="b2ea6-211">此组织样式通常简称为功能文件夹或功能切片 (另请参阅：[垂直切片](http://deviq.com/vertical-slices/))。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-211">This organizational style is typically referred to as feature folders or feature slices (see also: [Vertical Slices](http://deviq.com/vertical-slices/)).</span></span>

<span data-ttu-id="b2ea6-212">ASP.NET 核心 MVC 支持区域为此目的。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-212">ASP.NET Core MVC supports Areas for this purpose.</span></span> <span data-ttu-id="b2ea6-213">使用区域，可以创建单独的控制器和视图文件夹 （以及任何关联的模型） 中每个区域文件夹集。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-213">Using areas, you can create separate sets of Controllers and Views folders (as well as any associated models) in each Area folder.</span></span> <span data-ttu-id="b2ea6-214">图 7-1 显示了使用区域的示例文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-214">Figure 7-1 shows an example folder structure, using Areas.</span></span>

![](./media/image7-1.png)

<span data-ttu-id="b2ea6-215">图 7-1 示例区域组织</span><span class="sxs-lookup"><span data-stu-id="b2ea6-215">Figure 7-1 Sample Area Organization</span></span>

<span data-ttu-id="b2ea6-216">在使用区域，你必须使用属性修饰将控制器与它们所属的区域的名称：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-216">When using Areas, you must use attributes to decorate your controllers with the name of the area to which they belong:</span></span>

```csharp
[Area("Catalog")]
public class HomeController
{}
```

<span data-ttu-id="b2ea6-217">你还需要将区域支持添加到路由：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-217">You also need to add area support to your routes:</span></span>

```csharp
app.UseMvc(routes =>
{
    // Areas support
    routes.MapRoute(
    name: "areaRoute",
    template: "{area:exists}/{controller=Home}/{action=Index}/{id?}");
    routes.MapRoute(
    name: "default",
    template: "{controller=Home}/{action=Index}/{id?}");
});
```

<span data-ttu-id="b2ea6-218">除了区域的内置支持，还可以使用自己的文件夹结构和约定来代替特性和自定义路由。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-218">In addition to the built-in support for Areas, you can also use your own folder structure, and conventions in place of attributes and custom routes.</span></span> <span data-ttu-id="b2ea6-219">这将使你能够功能文件夹未包含单独的文件夹的视图和控制器等，保留层次结构更简单，并使其更轻松地查看所有相关的每个功能在单个位置的文件。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-219">This would allow you to have feature folders that didn't include separate folders for Views, Controllers, etc., keeping the hierarchy flatter and making it easier to see all related files in a single place for each feature.</span></span>

<span data-ttu-id="b2ea6-220">ASP.NET 核心使用内置的约定类型来控制其行为。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-220">ASP.NET Core uses built-in convention types to control its behavior.</span></span> <span data-ttu-id="b2ea6-221">你可以修改或替换这些约定。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-221">You can modify or replace these conventions.</span></span> <span data-ttu-id="b2ea6-222">例如，你可以创建会自动收到基于其命名空间 （通常对应于控制器所在的文件夹） 的给定控制器的功能名称的约定：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-222">For example, you can create a convention that will automatically get the feature name for a given controller based on its namespace (which typically correlates to the folder in which the controller is located):</span></span>

```csharp
FeatureConvention : IControllerModelConvention
{
    public void Apply(ControllerModel controller)
    {
        controller.Properties.Add("feature",
        GetFeatureName(controller.ControllerType));
    }

    private string GetFeatureName(TypeInfo controllerType)
    {
        string[] tokens = controllerType.FullName.Split('.');
        if (!tokens.Any(t => t == "Features")) return "";
        string featureName = tokens
        .SkipWhile(t => !t.Equals("features",
        StringComparison.CurrentCultureIgnoreCase))
        .Skip(1)
        .Take(1)
        .FirstOrDefault();
        return featureName;
    }
}
```

<span data-ttu-id="b2ea6-223">你然后此约定作为一个选项时指定支持 MVC 的添加 ConfigureServices 中的应用程序：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-223">You then specify this convention as an option when you add support for MVC to your application in ConfigureServices:</span></span>

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

<span data-ttu-id="b2ea6-224">ASP.NET 核心 MVC 还使用约定来找到视图。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-224">ASP.NET Core MVC also uses a convention to locate views.</span></span> <span data-ttu-id="b2ea6-225">你可以重写它使用自定义约定，以便视图将位于功能文件夹 （使用 FeatureConvention，上面提供的功能名称）。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-225">You can override it with a custom convention so that views will be located in your feature folders (using the feature name provided by the FeatureConvention, above).</span></span> <span data-ttu-id="b2ea6-226">你可以了解有关这种方法的详细信息和 MSDN 文章中，从下载的工作示例[ASP.NET 核心 MVC 的功能切片](https://msdn.microsoft.com/magazine/mt763233.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-226">You can learn more about this approach and download a working sample from the MSDN article, [Feature Slices for ASP.NET Core MVC](https://msdn.microsoft.com/magazine/mt763233.aspx).</span></span>

### <a name="cross-cutting-concerns"></a><span data-ttu-id="b2ea6-227">跨领域问题</span><span class="sxs-lookup"><span data-stu-id="b2ea6-227">Cross-Cutting Concerns</span></span>

<span data-ttu-id="b2ea6-228">随着应用程序的增长，则它变得越来越重要抽取跨领域问题，以消除重复和保持一致性。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-228">As applications grow, it becomes increasingly important to factor out cross-cutting concerns to eliminate duplication and maintain consistency.</span></span> <span data-ttu-id="b2ea6-229">在 ASP.NET Core 应用程序中的跨领域问题的一些示例，身份验证、 模型验证规则、 输出缓存，日期和错误处理，但是有许多其他。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-229">Some examples of cross-cutting concerns in ASP.NET Core applications are authentication, model validation rules, output caching, and error handling, though there are many others.</span></span> <span data-ttu-id="b2ea6-230">ASP.NET 核心 MVC[筛选器](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters)让你运行代码之前或之后在请求处理管道中的某些步骤。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-230">ASP.NET Core MVC [filters](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) allow you to run code before or after certain steps in the request processing pipeline.</span></span> <span data-ttu-id="b2ea6-231">例如，筛选器可以运行之前和之后模型绑定之前, 和之后的操作，或之前和之后的操作的结果。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-231">For instance, a filter can run before and after model binding, before and after an action, or before and after an action's result.</span></span> <span data-ttu-id="b2ea6-232">授权筛选器还可用于控制对管道的其余部分的访问。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-232">You can also use an authorization filter to control access to the rest of the pipeline.</span></span> <span data-ttu-id="b2ea6-233">图 7-2 显示如何执行流传递筛选器，如果请求配置。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-233">Figures 7-2 shows how request execution flows through filters, if configured.</span></span>

![通过授权筛选器、 资源筛选器、 模型绑定，操作筛选器、 操作执行和操作结果转换、 异常筛选器，结果筛选器和结果执行处理该请求。](./media/image7-2.png)

<span data-ttu-id="b2ea6-236">图 7-2 请求通过筛选器和请求管道的执行。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-236">Figure 7-2 Request execution through filters and request pipeline.</span></span>

<span data-ttu-id="b2ea6-237">筛选器通常会作为属性实现，因此你可以将它们应用控制器或操作。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-237">Filters are usually implemented as attributes, so you can apply them controllers or actions.</span></span> <span data-ttu-id="b2ea6-238">当以这种方式，指定在操作级别覆盖或指定的控制器级别筛选器后的生成筛选器添加自身重写全局筛选器。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-238">When added in this fashion, filters specified at the action level override or build upon filters specified at the controller level, which themselves override global filters.</span></span> <span data-ttu-id="b2ea6-239">例如，\[路由\]属性可用来生成控制器和操作之间的路由。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-239">For example, the \[Route\] attribute can be used to build up routes between controllers and actions.</span></span> <span data-ttu-id="b2ea6-240">同样，可以控制器级别配置授权和将其替换原来的各项操作，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-240">Likewise, authorization can be configured at the controller level, and then overridden by individual actions, as the following sample demonstrates:</span></span>

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous]
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

<span data-ttu-id="b2ea6-241">第一种方法，登录名，使用 AllowAnonymous 筛选器 （属性） 重写在控制器级别设置的 Authorize 筛选器。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-241">The first method, Login, uses the AllowAnonymous filter (attribute) to override the Authorize filter set at the controller level.</span></span> <span data-ttu-id="b2ea6-242">ForgotPassword 操作 （和不具有 AllowAnonymous 特性类中的任何其他操作） 将需要身份验证的请求。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-242">The ForgotPassword action (and any other action in the class that doesn't have an AllowAnonymous attribute) will require an authenticated request.</span></span>

<span data-ttu-id="b2ea6-243">可以使用筛选器，以消除重复的常见错误 Api 处理策略窗体中。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-243">Filters can be used to eliminate duplication in the form of common error handling policies for APIs.</span></span> <span data-ttu-id="b2ea6-244">例如，典型的 API 策略是返回 NotFound 响应引用不存在的密钥的请求和错误的请求响应，如果模型验证失败。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-244">For example, a typical API policy is to return a NotFound response to requests referencing keys that do not exist, and a BadRequest response if model validation fails.</span></span> <span data-ttu-id="b2ea6-245">下面的示例演示在操作中的这两种策略：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-245">The following example demonstrates these two policies in action:</span></span>

```csharp
[HttpPut("{id}")]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    if ((await _authorRepository.ListAsync()).All(a => a.Id != id))
    {
        return NotFound(id);
    }
    if (!ModelState.IsValid)
    {
        return BadRequest(ModelState);
    }
    author.Id = id;
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

<span data-ttu-id="b2ea6-246">不允许使用条件如下的代码变得杂乱你操作方法。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-246">Don't allow your action methods to become cluttered with conditional code like this.</span></span> <span data-ttu-id="b2ea6-247">相反，请求到可以基于根据需要应用的筛选器的策略。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-247">Instead, pull the policies into filters that can be applied on an as-needed basis.</span></span> <span data-ttu-id="b2ea6-248">在此示例中，模型验证检查，这应发生的随时命令发送到 API，可替换的以下属性：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-248">In this example, the model validation check, which should occur any time a command is sent to the API, can be replaced by the following attribute:</span></span>

```csharp
public class ValidateModelAttribute : ActionFilterAttribute
{
    public override void OnActionExecuting(ActionExecutingContext context)
    {
        if (!context.ModelState.IsValid)
        {
            context.Result = new BadRequestObjectResult(context.ModelState);
        }
    }
}
```

<span data-ttu-id="b2ea6-249">同样，可以使用筛选器以检查是否存在一条记录，并返回 404 之前执行的操作，不再需要的操作中执行这些检查。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-249">Likewise, a filter can be used to check if a record exists and return a 404 before the action is executed, eliminating the need to perform these checks in the action.</span></span> <span data-ttu-id="b2ea6-250">一旦拉出常见约定并组织你的解决方案基础结构代码和业务逻辑分开从你的 UI，你的 MVC 操作方法应非常精简：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-250">Once you've pulled out common conventions and organized your solution to separate infrastructure code and business logic from your UI, your MVC action methods should be extremely thin:</span></span>

```csharp
// PUT api/authors/2/5
[HttpPut("{id}")]
[ValidateAuthorExists]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

<span data-ttu-id="b2ea6-251">你可以阅读更多有关实现筛选器和 MSDN 文章中，从下载的工作示例[真实世界 ASP.NET 核心 MVC 筛选器](https://msdn.microsoft.com/magazine/mt767699.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-251">You can read more about implementing filters and download a working sample from the MSDN article, [Real World ASP.NET Core MVC Filters](https://msdn.microsoft.com/magazine/mt767699.aspx).</span></span>

> ### <a name="references--structuring-applications"></a><span data-ttu-id="b2ea6-252">引用 – 构建应用程序</span><span class="sxs-lookup"><span data-stu-id="b2ea6-252">References – Structuring Applications</span></span>
> - <span data-ttu-id="b2ea6-253">**区域**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-253">**Areas**</span></span>  
> <span data-ttu-id="b2ea6-254"><https://docs.microsoft.com/aspnet/core/mvc/controllers/areas></span><span class="sxs-lookup"><span data-stu-id="b2ea6-254"><https://docs.microsoft.com/aspnet/core/mvc/controllers/areas></span></span>
> - <span data-ttu-id="b2ea6-255">**MSDN – ASP.NET Core MVC 的功能切片**
>  <https://msdn.microsoft.com/magazine/mt763233.aspx></span><span class="sxs-lookup"><span data-stu-id="b2ea6-255">**MSDN – Feature Slices for ASP.NET Core MVC**
<https://msdn.microsoft.com/magazine/mt763233.aspx></span></span>
> - <span data-ttu-id="b2ea6-256">**筛选器**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-256">**Filters**</span></span>  
> <span data-ttu-id="b2ea6-257"><https://docs.microsoft.com/aspnet/core/mvc/controllers/filters></span><span class="sxs-lookup"><span data-stu-id="b2ea6-257"><https://docs.microsoft.com/aspnet/core/mvc/controllers/filters></span></span>
> - <span data-ttu-id="b2ea6-258">**MSDN – 现实世界 ASP.NET Core MVC 筛选器**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-258">**MSDN – Real World ASP.NET Core MVC Filters**</span></span>  
> <span data-ttu-id="b2ea6-259"><https://msdn.microsoft.com/magazine/mt767699.aspx></span><span class="sxs-lookup"><span data-stu-id="b2ea6-259"><https://msdn.microsoft.com/magazine/mt767699.aspx></span></span>

## <a name="security"></a><span data-ttu-id="b2ea6-260">安全性</span><span class="sxs-lookup"><span data-stu-id="b2ea6-260">Security</span></span>

<span data-ttu-id="b2ea6-261">保护 web 应用程序是具有许多注意事项的大型主题。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-261">Securing web applications is a large topic, with many considerations.</span></span> <span data-ttu-id="b2ea6-262">在其最基本级别，涉及到安全确保你知道谁，给定的请求的来源，然后确保该请求仅有权访问它应的资源。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-262">At its most basic level, security involves ensuring you know who a given request is coming from, and then ensuring that that request only has access to resources it should.</span></span> <span data-ttu-id="b2ea6-263">身份验证是比较对的请求中的受信任的数据存储区中，若要查看是否请求应被视为来自已知实体提供凭据的过程。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-263">Authentication is the process of comparing credentials provided with a request to those in a trusted data store, to see if the request should be treated as coming from a known entity.</span></span> <span data-ttu-id="b2ea6-264">授权是限制对基于用户标识的某些资源的访问的过程。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-264">Authorization is the process of restricting access to certain resources based on user identity.</span></span> <span data-ttu-id="b2ea6-265">第三个安全问题保护请求以防止窃听由第三方，为其至少应[确保你的应用程序使用 SSL](https://docs.microsoft.com/aspnet/core/security/enforcing-ssl)。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-265">A third security concern is protecting requests from eavesdropping by third parties, for which you should at least [ensure that SSL is used by your application](https://docs.microsoft.com/aspnet/core/security/enforcing-ssl).</span></span>

### <a name="authentication"></a><span data-ttu-id="b2ea6-266">身份验证</span><span class="sxs-lookup"><span data-stu-id="b2ea6-266">Authentication</span></span>

<span data-ttu-id="b2ea6-267">ASP.NET 核心标识是可用于支持你的应用程序的登录功能的成员身份系统。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-267">ASP.NET Core Identity is a membership system you can use to support login functionality for your application.</span></span> <span data-ttu-id="b2ea6-268">它还具有对本地用户帐户的支持以及等 Microsoft 帐户、 Twitter、 Facebook、 Google、 和的详细信息的提供程序的外部登录提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-268">It has support for local user accounts as well as external login provider support from providers like Microsoft Account, Twitter, Facebook, Google, and more.</span></span> <span data-ttu-id="b2ea6-269">除了 ASP.NET 核心标识你的应用程序可以使用 windows 身份验证，或第三方标识提供程序，例如[标识服务器](https://github.com/IdentityServer/IdentityServer4)。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-269">In addition to ASP.NET Core Identity, your application can use windows authentication, or a third-party identity provider like [Identity Server](https://github.com/IdentityServer/IdentityServer4).</span></span>

<span data-ttu-id="b2ea6-270">ASP.NET 核心标识包含新的项目模板中，如果选择单个用户帐户选项。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-270">ASP.NET Core Identity is included in new project templates if the Individual User Accounts option is selected.</span></span> <span data-ttu-id="b2ea6-271">此模板包括注册、 登录名、 外部登录名、 忘记了的密码和其他功能的支持。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-271">This template includes support for registration, login, external logins, forgotten passwords, and additional functionality.</span></span>

![](./media/image7-3.png)

<span data-ttu-id="b2ea6-272">图 7-3 选择单个用户帐户具有预先配置的标识。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-272">Figure 7-3 Select Individual User Accounts to have Identity preconfigured.</span></span>

<span data-ttu-id="b2ea6-273">在启动时，在 ConfigureServices 和配置中配置身份验证支持：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-273">Identity support is configured in Startup, both in ConfigureServices and Configure:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
    .AddEntityFrameworkStores<ApplicationDbContext>()
    .AddDefaultTokenProviders();
    services.AddMvc();
}

public void Configure(IApplicationBuilder app)
{
    app.UseStaticFiles();
    app.UseIdentity();
    app.UseMvc(routes =>
    {
        routes.MapRoute(
        name: "default",
        template: "{controller=Home}/{action=Index}/{id?}");
    });
}
```

<span data-ttu-id="b2ea6-274">很重要 UseIdentity 出现在 UseMvc 之前，在配置方法。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-274">It's important that UseIdentity appear before UseMvc in the Configure method.</span></span> <span data-ttu-id="b2ea6-275">在配置中 ConfigureServices 时标识，你会注意到 AddDefaultTokenProviders 调用。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-275">When configuring Identity in ConfigureServices, you'll notice a call to AddDefaultTokenProviders.</span></span> <span data-ttu-id="b2ea6-276">这与令牌可用于保护 web 之间的通信，但改为引用创建可以发送到通过短信或电子邮件以使其以确认其身份的用户的提示的提供程序无关。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-276">This has nothing to do with tokens that may be used to secure web communications, but instead refers to providers that create prompts that can be sent to users via SMS or email in order for them to confirm their identity.</span></span>

<span data-ttu-id="b2ea6-277">你可以详细了解[配置双因素身份验证](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)和[启用外部登录提供程序](https://docs.microsoft.com/aspnet/core/security/authentication/social/)从官方 ASP.NET 核心文档。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-277">You can learn more about [configuring two-factor authentication](https://docs.microsoft.com/aspnet/core/security/authentication/2fa) and [enabling external login providers](https://docs.microsoft.com/aspnet/core/security/authentication/social/) from the official ASP.NET Core docs.</span></span>

### <a name="authorization"></a><span data-ttu-id="b2ea6-278">授权</span><span class="sxs-lookup"><span data-stu-id="b2ea6-278">Authorization</span></span>

<span data-ttu-id="b2ea6-279">授权的最简单形式涉及限制匿名用户访问。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-279">The simplest form of authorization involves restricting access to anonymous users.</span></span> <span data-ttu-id="b2ea6-280">这可以通过只需应用来实现\[Authorize\]属性设为特定控制器或操作。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-280">This can be achieved by simply applying the \[Authorize\] attribute to certain controllers or actions.</span></span> <span data-ttu-id="b2ea6-281">如果正在使用角色，该属性可以进一步扩展以限制对属于特定角色，用户的访问，如所示：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-281">If roles are being used, the attribute can be further extended to restrict access to users who belong to certain roles, as shown:</span></span>

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

<span data-ttu-id="b2ea6-282">在这种情况下，属于是 HRManager 或财务角色 （或两者） 的用户将有权访问 SalaryController。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-282">In this case, users belonging to either the HRManager or Finance roles (or both) would have access to the SalaryController.</span></span> <span data-ttu-id="b2ea6-283">要求用户属于多个角色 （而不仅仅是一个多个），你可以将该属性多次，指定每次的所需的角色。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-283">To require that a user belong to multiple roles (not just one of several), you can apply the attribute multiple times, specifying a required role each time.</span></span>

<span data-ttu-id="b2ea6-284">指定一组特定的角色，因为在许多不同的控制器和操作的字符串将导致不希望重复。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-284">Specifying certain sets of roles as strings in many different controllers and actions can lead to undesirable repetition.</span></span> <span data-ttu-id="b2ea6-285">你可以配置授权策略，可封装授权规则，，然后应用时指定的策略而不是单个角色\[Authorize\]属性：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-285">You can configure authorization policies, which encapsulate authorization rules, and then specify the policy instead of individual roles when applying the \[Authorize\] attribute:</span></span>

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

<span data-ttu-id="b2ea6-286">以这种方式使用策略，可以分隔的各种操作的特定角色或将应用于它的规则受到限制。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-286">Using policies in this way, you can separate the kinds of actions being restricted from the specific roles or rules that apply to it.</span></span> <span data-ttu-id="b2ea6-287">更高版本，如果你创建一个新角色，需要具有对特定资源的访问权限，你可以仅更新策略，而不是更新角色的每个列表上每个\[Authorize\]属性。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-287">Later, if you create a new role that needs to have access to certain resources, you can just update a policy, rather than updating every list of roles on every \[Authorize\] attribute.</span></span>

#### <a name="claims"></a><span data-ttu-id="b2ea6-288">声明</span><span class="sxs-lookup"><span data-stu-id="b2ea6-288">Claims</span></span>

<span data-ttu-id="b2ea6-289">声明是用户的表示经过身份验证的属性的名称值对。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-289">Claims are name value pairs that represent properties of an authenticated user.</span></span> <span data-ttu-id="b2ea6-290">例如，你可能会以声明方式存储用户的员工数。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-290">For example, you might store users' employee number as a claim.</span></span> <span data-ttu-id="b2ea6-291">声明随后可作为授权策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-291">Claims can then be used as part of authorization policies.</span></span> <span data-ttu-id="b2ea6-292">你可以创建名为"EmployeeOnly"的策略，则需要存在的声明称为"EmployeeNumber"，在此示例中所示：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-292">You could create a policy called "EmployeeOnly" that requires the existence of a claim called "EmployeeNumber", as shown in this example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
    services.AddAuthorization(options =>
    {
        options.AddPolicy("EmployeeOnly", policy => policy.RequireClaim("EmployeeNumber"));
    });
}
```

<span data-ttu-id="b2ea6-293">此策略无法随后可用于\[Authorize\]属性以保护任何控制器和/或操作，如上面所述。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-293">This policy could then be used with the \[Authorize\] attribute to protect any controller and/or action, as described above.</span></span>

#### <a name="securing-web-apis"></a><span data-ttu-id="b2ea6-294">保护 Web Api</span><span class="sxs-lookup"><span data-stu-id="b2ea6-294">Securing Web APIs</span></span>

<span data-ttu-id="b2ea6-295">大多数 web Api 应实现的基于令牌的身份验证系统。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-295">Most web APIs should implement a token-based authentication system.</span></span> <span data-ttu-id="b2ea6-296">令牌身份验证是无状态和设计可缩放性。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-296">Token authentication is stateless and designed to be scalable.</span></span> <span data-ttu-id="b2ea6-297">在基于令牌的身份验证系统中，客户端必须首先进行身份验证的身份验证提供程序。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-297">In a token-based authentication system, the client must first authenticate with the authentication provider.</span></span> <span data-ttu-id="b2ea6-298">如果成功，客户端颁发一个令牌，只需是加密有意义的字符字符串。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-298">If successful, the client is issued a token, which is simply a cryptographically meaningful string of characters.</span></span> <span data-ttu-id="b2ea6-299">然后，客户端需要向 API 发出请求，它会添加此令牌作为请求标头。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-299">When the client then needs to issue a request to an API, it adds this token as a header on the request.</span></span> <span data-ttu-id="b2ea6-300">服务器然后验证完成请求之前在请求标头中找到的令牌。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-300">The server then validates the token found in the request header before completing the request.</span></span> <span data-ttu-id="b2ea6-301">图 7-4 演示了此过程。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-301">Figure 7-4 demonstrates this process.</span></span>

![TokenAuth](./media/image7-4.png)

<span data-ttu-id="b2ea6-303">**图 7-4。**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-303">**Figure 7-4.**</span></span> <span data-ttu-id="b2ea6-304">基于令牌的身份验证的 Web Api。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-304">Token-based authentication for Web APIs.</span></span>

> ### <a name="references--security"></a><span data-ttu-id="b2ea6-305">引用 – 安全</span><span class="sxs-lookup"><span data-stu-id="b2ea6-305">References – Security</span></span>
> - <span data-ttu-id="b2ea6-306">**安全文档概述**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-306">**Security Docs Overview**</span></span>  
> <span data-ttu-id="b2ea6-307">https://docs.microsoft.com/aspnet/core/security/</span><span class="sxs-lookup"><span data-stu-id="b2ea6-307">https://docs.microsoft.com/aspnet/core/security/</span></span>
> - <span data-ttu-id="b2ea6-308">**强制在 ASP.NET Core 应用程序的 SSL**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-308">**Enforcing SSL in an ASP.NET Core App**</span></span>  
> <span data-ttu-id="b2ea6-309"><https://docs.microsoft.com/aspnet/core/security/enforcing-ssl></span><span class="sxs-lookup"><span data-stu-id="b2ea6-309"><https://docs.microsoft.com/aspnet/core/security/enforcing-ssl></span></span>
> - <span data-ttu-id="b2ea6-310">**标识简介**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-310">**Introduction to Identity**</span></span>  
> <span data-ttu-id="b2ea6-311"><https://docs.microsoft.com/aspnet/core/security/authentication/identity></span><span class="sxs-lookup"><span data-stu-id="b2ea6-311"><https://docs.microsoft.com/aspnet/core/security/authentication/identity></span></span>
> - <span data-ttu-id="b2ea6-312">**授权简介**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-312">**Introduction to Authorization**</span></span>  
> <span data-ttu-id="b2ea6-313"><https://docs.microsoft.com/aspnet/core/security/authorization/introduction></span><span class="sxs-lookup"><span data-stu-id="b2ea6-313"><https://docs.microsoft.com/aspnet/core/security/authorization/introduction></span></span>
> - <span data-ttu-id="b2ea6-314">**身份验证和授权，而 Azure App Service 中的 API 应用**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-314">**Authentication and Authorization for API Apps in Azure App Service**</span></span>  
> <span data-ttu-id="b2ea6-315"><https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication></span><span class="sxs-lookup"><span data-stu-id="b2ea6-315"><https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication></span></span>

## <a name="client-communication"></a><span data-ttu-id="b2ea6-316">客户端通信</span><span class="sxs-lookup"><span data-stu-id="b2ea6-316">Client Communication</span></span>

<span data-ttu-id="b2ea6-317">除了页，并且对通过 web Api 的数据的请求的响应，ASP.NET Core 应用可直接与连接的客户端进行通信。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-317">In addition to serving pages and responding to requests for data via web APIs, ASP.NET Core apps can communicate directly with connected clients.</span></span> <span data-ttu-id="b2ea6-318">此出站通信可以使用各种传输技术，最常见的是 Websocket。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-318">This outbound communication can use a variety of transport technologies, the most common being WebSockets.</span></span> <span data-ttu-id="b2ea6-319">ASP.NET 核心 SignalR 是一个库，即可轻松访问类到你的应用程序的实时服务器到客户端通信功能。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-319">ASP.NET Core SignalR is a library that makes it simple to kind of real-time server-to-client communication functionality to your applications.</span></span> <span data-ttu-id="b2ea6-320">SignalR 支持多种传输技术，包括 Websocket，和提取远多的开发人员的实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-320">SignalR supports a variety of transport technologies, including WebSockets, and abstracts away many of the implementation details from the developer.</span></span>

<span data-ttu-id="b2ea6-321">ASP.NET 核心 SignalR 我们正在开发，并将在 ASP.NET Core 的下一个版本中可用。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-321">ASP.NET Core SignalR is currently under development, and will be available in the next release of ASP.NET Core.</span></span> <span data-ttu-id="b2ea6-322">但是，其他[开放源代码 Websocket 库](https://github.com/radu-matei/websocket-manager)当前可用。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-322">However, other [open source WebSockets libraries](https://github.com/radu-matei/websocket-manager) are currently available.</span></span>

<span data-ttu-id="b2ea6-323">实时客户端通信，是否使用 Websocket 直接或其他技术，可在多个应用程序方案。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-323">Real-time client communication, whether using WebSockets directly or other techniques, are useful in a variety of application scenarios.</span></span> <span data-ttu-id="b2ea6-324">一些示例包括：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-324">Some examples include:</span></span>

-   <span data-ttu-id="b2ea6-325">实时聊天室应用程序</span><span class="sxs-lookup"><span data-stu-id="b2ea6-325">Live chat room applications</span></span>

-   <span data-ttu-id="b2ea6-326">监视应用程序</span><span class="sxs-lookup"><span data-stu-id="b2ea6-326">Monitoring applications</span></span>

-   <span data-ttu-id="b2ea6-327">作业进度更新</span><span class="sxs-lookup"><span data-stu-id="b2ea6-327">Job progress updates</span></span>

-   <span data-ttu-id="b2ea6-328">通知</span><span class="sxs-lookup"><span data-stu-id="b2ea6-328">Notifications</span></span>

-   <span data-ttu-id="b2ea6-329">交互式窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="b2ea6-329">Interactive forms applications</span></span>

<span data-ttu-id="b2ea6-330">在生成到应用程序的客户端通信时，通常有两个组件：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-330">When building client communication into your applications, there are typically two components:</span></span>

-   <span data-ttu-id="b2ea6-331">服务器端连接管理器 （SignalR Hub，WebSocketManager WebSocketHandler）</span><span class="sxs-lookup"><span data-stu-id="b2ea6-331">Server-side connection manager (SignalR Hub, WebSocketManager WebSocketHandler)</span></span>

-   <span data-ttu-id="b2ea6-332">客户端库</span><span class="sxs-lookup"><span data-stu-id="b2ea6-332">Client-side library</span></span>

<span data-ttu-id="b2ea6-333">客户端并不局限于浏览器 – 移动应用程序、 控制台应用和其他的本机应用还可以使用 SignalR/Websocket 通信。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-333">Clients are not limited to browsers – mobile apps, console apps, and other native apps can also communicate using SignalR/WebSockets.</span></span> <span data-ttu-id="b2ea6-334">下面的简单程序回显发送到的聊天应用程序到控制台，WebSocketManager 示例应用程序的一部分的所有内容：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-334">The following simple program echoes all content sent to a chat application to the console, as part of a WebSocketManager sample application:</span></span>

```csharp
public class Program
{
    private static Connection _connection;
    public static void Main(string[] args)
    {
        StartConnectionAsync();
        _connection.On("receiveMessage", (arguments) =>;
        {
            Console.WriteLine(\$"{arguments\[0\]} said: {arguments\[1\]}");
        });
        Console.ReadLine();
        StopConnectionAsync();
    }
    
    public static async Task StartConnectionAsync()
    {
        _connection = new Connection();
        await _connection.StartConnectionAsync("ws://localhost:65110/chat");
    }
    
    public static async Task StopConnectionAsync()
    {
        await _connection.StopConnectionAsync();
    }
```

<span data-ttu-id="b2ea6-335">请考虑的方式你的应用程序直接与客户端应用程序进行通信，然后考虑实时通信是否可以提高应用程序的用户体验。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-335">Consider ways in which your applications communicate directly with client applications, and consider whether real-time communication would improve your app's user experience.</span></span>

> ### <a name="references--client-communication"></a><span data-ttu-id="b2ea6-336">引用 – 客户端通信</span><span class="sxs-lookup"><span data-stu-id="b2ea6-336">References – Client Communication</span></span>
> - <span data-ttu-id="b2ea6-337">**ASP.NET 核心 SignalR**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-337">**ASP.NET Core SignalR**</span></span>  
> <span data-ttu-id="b2ea6-338"><https://github.com/aspnet/SignalR></span><span class="sxs-lookup"><span data-stu-id="b2ea6-338"><https://github.com/aspnet/SignalR></span></span>
> - <span data-ttu-id="b2ea6-339">**WebSocket 管理器**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-339">**WebSocket Manager**</span></span>  
> <span data-ttu-id="b2ea6-340">https://github.com/radu-matei/websocket-manager</span><span class="sxs-lookup"><span data-stu-id="b2ea6-340">https://github.com/radu-matei/websocket-manager</span></span>

## <a name="domain-driven-design--should-you-apply-it"></a><span data-ttu-id="b2ea6-341">域驱动的设计 – 应将其应用？</span><span class="sxs-lookup"><span data-stu-id="b2ea6-341">Domain-Driven Design – Should You Apply It?</span></span>

<span data-ttu-id="b2ea6-342">域驱动设计 (DDD) 是一种构建强调的将精力集中的软件的敏捷方法*业务领域*。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-342">Domain-Driven Design (DDD) is an agile approach to building software that emphasizes focusing on the *business domain*.</span></span> <span data-ttu-id="b2ea6-343">它强调大量通信以及与业务域 expert(s) 可以与开发人员实际系统的工作原理的交互。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-343">It places a heavy emphasis on communication and interaction with business domain expert(s) who can relate to the developers how the real-world system works.</span></span> <span data-ttu-id="b2ea6-344">例如，如果你正在生成处理股票交易的系统，则域专家可能有经验的常用 broker。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-344">For example, if you're building a system that handles stock trades, your domain expert might be an experienced stock broker.</span></span> <span data-ttu-id="b2ea6-345">DDD 旨在解决大型、 复杂的业务问题，并且不通常适用于较小、 更简单的应用程序，了解和建模域中的投资是不值得。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-345">DDD is designed to address large, complex business problems, and is often not appropriate for smaller, simpler applications, as the investment in understanding and modeling the domain is not worth it.</span></span>

<span data-ttu-id="b2ea6-346">在生成软件以下 DDD 方法时，团队 （包括非技术利益干系人和 contributors （参与者）） 应开发*无处不在语言*问题空间。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-346">When building software following a DDD approach, your team (including non-technical stakeholders and contributors) should develop a *ubiquitous language* for the problem space.</span></span> <span data-ttu-id="b2ea6-347">即，相同的术语应用于所模拟的实际概念、 软件同等和以保留概念 （例如，数据库表） 可能存在的任何结构。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-347">That is, the same terminology should be used for the real-world concept being modeled, the software equivalent, and any structures that might exist to persist the concept (for example, database tables).</span></span> <span data-ttu-id="b2ea6-348">因此，无处不在的语言中所述的概念应构成的基础你*域模型*。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-348">Thus, the concepts described in the ubiquitous language should form the basis for your *domain model*.</span></span>

<span data-ttu-id="b2ea6-349">您的域模型组成之间来表示系统的行为进行交互的对象。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-349">Your domain model is comprised of objects that interact with one another to represent the behavior of the system.</span></span> <span data-ttu-id="b2ea6-350">这些对象可能分为以下类别：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-350">These objects may fall into the following categories:</span></span>

-   <span data-ttu-id="b2ea6-351">[实体](http://deviq.com/entity/)，分别表示与线程的标识的对象。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-351">[Entities](http://deviq.com/entity/), which represent objects with a thread of identity.</span></span> <span data-ttu-id="b2ea6-352">使用密钥依据可以以后检索这些实体通常存储在持久性。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-352">Entities are typically stored in persistence with a key by which they can later be retrieved.</span></span>

-   <span data-ttu-id="b2ea6-353">[聚合](http://deviq.com/aggregate-pattern/)，分别表示应保持作为一个单元的对象组。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-353">[Aggregates](http://deviq.com/aggregate-pattern/), which represent groups of objects that should be persisted as a unit.</span></span>

-   <span data-ttu-id="b2ea6-354">[值对象](http://deviq.com/value-object/)，这表示可以比较基于其属性值的总和的概念。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-354">[Value objects](http://deviq.com/value-object/), which represent concepts that can be compared on the basis of the sum of their property values.</span></span> <span data-ttu-id="b2ea6-355">例如，DateRange 包含开始和结束日期。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-355">For example, DateRange consisting of a start and end date.</span></span>

-   <span data-ttu-id="b2ea6-356">[域事件](https://martinfowler.com/eaaDev/DomainEvent.html)，分别表示系统内发生的事，感兴趣的系统的其他部分。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-356">[Domain events](https://martinfowler.com/eaaDev/DomainEvent.html), which represent things happening within the system that are of interest to other parts of the system.</span></span>

<span data-ttu-id="b2ea6-357">请注意 DDD 域模型应封装复杂模型中的行为。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-357">Note that a DDD domain model should encapsulate complex behavior within the model.</span></span> <span data-ttu-id="b2ea6-358">实体，特别是，不应仅为属性的集合。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-358">Entities, in particular, should not merely be collections of properties.</span></span> <span data-ttu-id="b2ea6-359">当域模型中缺少行为，并且只是表示系统的状态时，它称为[贫乏模型](http://deviq.com/anemic-model/)，即在 DDD 不可取。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-359">When the domain model lacks behavior and merely represents the state of the system, it is said to be an [anemic model](http://deviq.com/anemic-model/), which is undesirable in DDD.</span></span>

<span data-ttu-id="b2ea6-360">除了这些模型类型，DDD 通常采用多种模式：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-360">In addition to these model types, DDD typically employs a variety of patterns:</span></span>

-   <span data-ttu-id="b2ea6-361">[存储库](http://deviq.com/repository-pattern/)，提取持久性详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-361">[Repository](http://deviq.com/repository-pattern/), for abstracting persistence details.</span></span>

-   <span data-ttu-id="b2ea6-362">[工厂](https://en.wikipedia.org/wiki/Factory_method_pattern)，用于封装复杂的对象创建。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-362">[Factory](https://en.wikipedia.org/wiki/Factory_method_pattern), for encapsulating complex object creation.</span></span>

-   <span data-ttu-id="b2ea6-363">域事件，为分离依赖从触发行为的行为。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-363">Domain events, for decoupling dependent behavior from triggering behavior.</span></span>

-   <span data-ttu-id="b2ea6-364">[服务](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/)、 封装复杂的行为和/或基础结构实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-364">[Services](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/), for encapsulating complex behavior and/or infrastructure implementation details.</span></span>

-   <span data-ttu-id="b2ea6-365">[命令](https://en.wikipedia.org/wiki/Command_pattern)、 为分离发出命令和执行命令本身。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-365">[Command](https://en.wikipedia.org/wiki/Command_pattern), for decoupling issuing commands and executing the command itself.</span></span>

-   <span data-ttu-id="b2ea6-366">[规范](http://deviq.com/specification-pattern/)，用于封装查询详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-366">[Specification](http://deviq.com/specification-pattern/), for encapsulating query details.</span></span>

<span data-ttu-id="b2ea6-367">DDD 还建议讨论过，干净体系结构的使用可以进行更松散耦合，封装和可以轻松地验证使用单元测试的代码。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-367">DDD also recommends the use of the Clean Architecture discussed previously, allowing for loose coupling, encapsulation, and code that can easily be verified using unit tests.</span></span>

### <a name="when-should-you-apply-ddd"></a><span data-ttu-id="b2ea6-368">当你应将 DDD</span><span class="sxs-lookup"><span data-stu-id="b2ea6-368">When Should You Apply DDD</span></span>

<span data-ttu-id="b2ea6-369">DDD 非常适合于具有 （而不仅是技术） 的重要业务复杂性的大型应用程序。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-369">DDD is well-suited to large applications with significant business (not just technical) complexity.</span></span> <span data-ttu-id="b2ea6-370">应用程序应需要了解的域专业人员。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-370">The application should require the knowledge of domain experts.</span></span> <span data-ttu-id="b2ea6-371">域模型本身，表示业务规则和交互超出只需存储和从数据存储检索的各种记录的当前状态应为重要行为。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-371">There should be significant behavior in the domain model itself, representing business rules and interactions beyond simply storing and retrieving the current state of various records from data stores.</span></span>

### <a name="when-shouldnt-you-apply-ddd"></a><span data-ttu-id="b2ea6-372">当你不应将 DDD</span><span class="sxs-lookup"><span data-stu-id="b2ea6-372">When Shouldn't You Apply DDD</span></span>

<span data-ttu-id="b2ea6-373">DDD 涉及建模、 体系结构和可能不合理的较小的应用程序或应用程序是实质上是只需 CRUD （创建/读取/更新/删除） 的通信中的投资。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-373">DDD involves investments in modeling, architecture, and communication that may not be warranted for smaller applications or applications that are essentially just CRUD (create/read/update/delete).</span></span> <span data-ttu-id="b2ea6-374">如果你选择接近你的应用程序后 DDD，但是发现你的域具有与任何行为贫乏模型，你可能需要重新考虑您的方法。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-374">If you choose to approach your application following DDD, but find that your domain has an anemic model with no behavior, you may need to rethink your approach.</span></span> <span data-ttu-id="b2ea6-375">你的应用程序可能不需要 DDD，或者你可能需要帮助重构你的应用程序能够在域模型中，而不是数据库或用户界面中的业务逻辑进行封装。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-375">Either your application may not need DDD, or you may need assistance refactoring your application to encapsulate business logic in the domain model, rather than in your database or user interface.</span></span>

<span data-ttu-id="b2ea6-376">混合方法将仅使用 DDD，适用于事务性的也更复杂的区域的应用程序，但不是能为更简单 CRUD 或应用程序的只读部分。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-376">A hybrid approach would be to only use DDD for the transactional or more complex areas of the application, but not for simpler CRUD or read-only portions of the application.</span></span> <span data-ttu-id="b2ea6-377">例如，如果你要查询以显示报表或仪表板的数据可视化的数据不需要有聚合的约束。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-377">For instance, you needn't have the constraints of an Aggregate if you're querying data to display a report or to visualize data for a dashboard.</span></span> <span data-ttu-id="b2ea6-378">它是完全可以接受具有此类要求的单独的、 更简单的读取的模型。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-378">It's perfectly acceptable to have a separate, simpler read model for such requirements.</span></span>

> ### <a name="references--domain-driven-design"></a><span data-ttu-id="b2ea6-379">引用 – 域驱动的设计</span><span class="sxs-lookup"><span data-stu-id="b2ea6-379">References – Domain-Driven Design</span></span>
> - <span data-ttu-id="b2ea6-380">**用英文 （StackOverflow 答案） DDD**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-380">**DDD in Plain English (StackOverflow Answer)**</span></span>  
> <span data-ttu-id="b2ea6-381"><https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488></span><span class="sxs-lookup"><span data-stu-id="b2ea6-381"><https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488></span></span>

## <a name="deployment"></a><span data-ttu-id="b2ea6-382">部署</span><span class="sxs-lookup"><span data-stu-id="b2ea6-382">Deployment</span></span>

<span data-ttu-id="b2ea6-383">有几个步骤涉及在过程中部署 ASP.NET Core 应用程序，而不考虑它的托管位置。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-383">There are a few steps involved in the process of deploying your ASP.NET Core application, regardless of where it will be hosted.</span></span> <span data-ttu-id="b2ea6-384">第一步是发布应用程序，这可以实现使用 dotnet 发布 CLI 命令。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-384">The first step is to publish the application, which can be done using the dotnet publish CLI command.</span></span> <span data-ttu-id="b2ea6-385">这将编译该应用程序，并将所有到指定文件夹中运行应用程序所需的文件。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-385">This will compile the application and place all of the files needed to run the application into a designated folder.</span></span> <span data-ttu-id="b2ea6-386">当从 Visual Studio 进行部署时，此步骤为你自动执行。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-386">When you deploy from Visual Studio, this step is performed for you automatically.</span></span> <span data-ttu-id="b2ea6-387">发布文件夹包含.exe 和.dll 文件以及该应用程序及其依赖项。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-387">The publish folder contains .exe and .dll files for the application and its dependencies.</span></span> <span data-ttu-id="b2ea6-388">自包含的应用程序还将包括.NET 运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-388">A self-contained application will also include a version of the .NET runtime.</span></span> <span data-ttu-id="b2ea6-389">配置文件、 静态的客户端资产和 MVC 视图，还将包括 ASP.NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-389">ASP.NET Core applications will also include configuration files, static client assets, and MVC views.</span></span>

<span data-ttu-id="b2ea6-390">ASP.NET 核心应用程序是控制台应用程序时在服务器启动和重新启动，如果应用程序 （一个或多个） 崩溃必须启动。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-390">ASP.NET Core applications are console applications that must be started when the server boots and restarted if the application (or server) crashes.</span></span> <span data-ttu-id="b2ea6-391">一个进程管理器可以用于自动执行此过程。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-391">A process manager can be used to automate this process.</span></span> <span data-ttu-id="b2ea6-392">有关 ASP.NET 核心最常见的进程管理器是 Nginx 和 Apache 在 Linux 和 IIS 上的或在 Windows 上的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-392">The most common process managers for ASP.NET Core are Nginx and Apache on Linux and IIS or Windows Service on Windows.</span></span>

<span data-ttu-id="b2ea6-393">一个进程管理器中，除了 Kestrel web 服务器中托管的 ASP.NET Core 应用程序必须使用反向代理服务器。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-393">In addition to a process manager, ASP.NET Core applications hosted in the Kestrel web server must use a reverse proxy server.</span></span> <span data-ttu-id="b2ea6-394">从 internet 接收 HTTP 请求和一些初步处理后将其转发给 Kestrel 的反向代理服务器。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-394">A reverse proxy server receives HTTP requests from the internet and forwards them to Kestrel after some preliminary handling.</span></span> <span data-ttu-id="b2ea6-395">反向代理服务器对应用程序提供的安全层和边缘部署 （从 Internet 的流量到公开） 所需。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-395">Reverse proxy servers provide a layer of security for the application, and are required for edge deployments (exposed to traffic from the Internet).</span></span> <span data-ttu-id="b2ea6-396">Kestrel 来说相对较新，不尚未提供对某些攻击防御能力。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-396">Kestrel is relatively new and does not yet offer defenses against certain attacks.</span></span> <span data-ttu-id="b2ea6-397">Kestrel 也不支持托管的相同端口上的多个应用程序，因此技术主机标头不能与使用它来启用承载上的相同的端口和 IP 地址的多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-397">Kestrel also doesn't support hosting multiple applications on the same port, so techniques like host headers cannot be used with it to enable hosting multiple applications on the same port and IP address.</span></span>

![到 Internet 的 kestrel](./media/image7-5.png)

<span data-ttu-id="b2ea6-399">图 7-5 反向代理服务器后面 Kestrel 中托管的 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b2ea6-399">Figure 7-5 ASP.NET hosted in Kestrel behind a reverse proxy server</span></span>

<span data-ttu-id="b2ea6-400">反向代理可在其中很有帮助的另一种情况是安全使用 SSL/HTTPS 的多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-400">Another scenario in which a reverse proxy can be helpful is to secure multiple applications using SSL/HTTPS.</span></span> <span data-ttu-id="b2ea6-401">在这种情况下，仅反向代理需要已配置 SSL。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-401">In this case, only the reverse proxy would need to have SSL configured.</span></span> <span data-ttu-id="b2ea6-402">反向代理服务器和 Kestrel 之间的通信无法接管位置 HTTP，如图 7-6 中所示。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-402">Communication between the reverse proxy server and Kestrel could take place over HTTP, as shown in Figure 7-6.</span></span>

![](./media/image7-6.png)

<span data-ttu-id="b2ea6-403">图 7-6 HTTPS 保护反向代理服务器后面托管的 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b2ea6-403">Figure 7-6 ASP.NET hosted behind an HTTPS-secured reverse proxy server</span></span>

<span data-ttu-id="b2ea6-404">日益盛行的方法是承载在 Docker 容器，然后可以本地托管或部署到 Azure 的基于云的承载 ASP.NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-404">An increasingly popular approach is to host your ASP.NET Core application in a Docker container, which then can be hosted locally or deployed to Azure for cloud-based hosting.</span></span> <span data-ttu-id="b2ea6-405">Docker 容器可包含在 Kestrel 上, 运行的应用程序代码，并如上所示将后面的反向代理服务器，部署。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-405">The Docker container could contain your application code, running on Kestrel, and would be deployed behind a reverse proxy server, as shown above.</span></span>

<span data-ttu-id="b2ea6-406">如果你要托管在 Azure 上的应用程序，你可以将 Microsoft Azure 应用程序网关用作专用的虚拟设备提供多个服务。</span><span class="sxs-lookup"><span data-stu-id="b2ea6-406">If you're hosting your application on Azure, you can use Microsoft Azure Application Gateway as a dedicated virtual appliance to provide several services.</span></span> <span data-ttu-id="b2ea6-407">除了充当的单个应用程序的反向代理时，应用程序网关也可以提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="b2ea6-407">In addition to acting as a reverse proxy for individual applications, Application Gateway can also offer the following features:</span></span>

-   <span data-ttu-id="b2ea6-408">HTTP 负载平衡</span><span class="sxs-lookup"><span data-stu-id="b2ea6-408">HTTP load balancing</span></span>

-   <span data-ttu-id="b2ea6-409">SSL 卸载 (仅到 Internet 的 SSL)</span><span class="sxs-lookup"><span data-stu-id="b2ea6-409">SSL offload (SSL only to Internet)</span></span>

-   <span data-ttu-id="b2ea6-410">端到端 SSL</span><span class="sxs-lookup"><span data-stu-id="b2ea6-410">End to End SSL</span></span>

-   <span data-ttu-id="b2ea6-411">多站点路由 （合并在单个应用程序网关上的最多 20 个站点）</span><span class="sxs-lookup"><span data-stu-id="b2ea6-411">Multi-site routing (consolidate up to 20 sites on a single Application Gateway)</span></span>

-   <span data-ttu-id="b2ea6-412">Web 应用程序防火墙</span><span class="sxs-lookup"><span data-stu-id="b2ea6-412">Web application firewall</span></span>

-   <span data-ttu-id="b2ea6-413">Websocket 支持</span><span class="sxs-lookup"><span data-stu-id="b2ea6-413">Websocket support</span></span>

-   <span data-ttu-id="b2ea6-414">高级诊断功能</span><span class="sxs-lookup"><span data-stu-id="b2ea6-414">Advanced diagnostics</span></span>

<span data-ttu-id="b2ea6-415">*了解有关章 10 中的 Azure 部署选项的详细信息。*</span><span class="sxs-lookup"><span data-stu-id="b2ea6-415">*Learn more about Azure deployment options in Chapter 10.*</span></span>

> ### <a name="references--deployment"></a><span data-ttu-id="b2ea6-416">引用 – 部署</span><span class="sxs-lookup"><span data-stu-id="b2ea6-416">References – Deployment</span></span>
> - <span data-ttu-id="b2ea6-417">**承载和部署概述**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-417">**Hosting and Deployment Overview**</span></span>  
> <span data-ttu-id="b2ea6-418"><https://docs.microsoft.com/aspnet/core/publishing/></span><span class="sxs-lookup"><span data-stu-id="b2ea6-418"><https://docs.microsoft.com/aspnet/core/publishing/></span></span>
> - <span data-ttu-id="b2ea6-419">**何时使用反向代理使用 Kestrel**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-419">**When to use Kestrel with a reverse proxy**</span></span>  
> <span data-ttu-id="b2ea6-420"><https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy></span><span class="sxs-lookup"><span data-stu-id="b2ea6-420"><https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy></span></span>
> - <span data-ttu-id="b2ea6-421">**在 Docker 中承载 ASP.NET Core 应用程序**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-421">**Host ASP.NET Core apps in Docker**</span></span>  
> <span data-ttu-id="b2ea6-422"><https://docs.microsoft.com/aspnet/core/publishing/docker></span><span class="sxs-lookup"><span data-stu-id="b2ea6-422"><https://docs.microsoft.com/aspnet/core/publishing/docker></span></span>
> - <span data-ttu-id="b2ea6-423">**引入 Azure 应用程序网关**</span><span class="sxs-lookup"><span data-stu-id="b2ea6-423">**Introducing Azure Application Gateway**</span></span>  
> <span data-ttu-id="b2ea6-424"><https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction></span><span class="sxs-lookup"><span data-stu-id="b2ea6-424"><https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="b2ea6-425">[以前](常用的客户端-端-web-technologies.md) [下一步] (work-with-data-in-asp-net-core-apps.md)</span><span class="sxs-lookup"><span data-stu-id="b2ea6-425">[Previous] (common-client-side-web-technologies.md) [Next] (work-with-data-in-asp-net-core-apps.md)</span></span>
