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
# <a name="develop-aspnet-core-mvc-apps"></a>开发 ASP.NET Core MVC 应用程序

> "它并不重要若要获取其右第一次。 它是非常重要，以使其正确最后一次。"  
> _-Andrew Hunt 和 David Thomas_

## <a name="summary"></a>摘要

ASP.NET 核心是一个跨平台的开放源代码框架，用于生成现代的云优化 web 应用程序。 ASP.NET Core 应用程序是轻量和模块化，具有依赖关系注入，在更高的可测试性和可维护性中启用的内置支持。 ASP.NET 核心结合 MVC，支持构建除了基于视图的应用的现代 web Api，是用于生成 web 应用程序的企业功能强大的框架。

## <a name="mapping-requests-to-responses"></a>将请求映射到响应

其核心 ASP.NET Core 应用将传入请求映射到传出的响应。 在低级别，这使用中间件，完成和简单的 ASP.NET Core 应用程序和微服务可能包含单独的自定义的中间件。 在使用时 ASP.NET 核心 MVC，可在某种程度上更高级别中，考虑按照*路由*，*控制器*，和*操作*。 每个传入请求与应用程序的路由表进行比较，如果找到匹配的路由，则调用 （属于一个控制器） 关联的操作方法来处理该请求。 如果找到匹配的路由，则调用错误处理程序 （在此情况下，返回 NotFound 结果）。

ASP.NET 核心 MVC 应用程序可以使用传统的路由、 属性的路由，或两者。 在代码中，指定路由定义常规路由*约定*在下面的示例中使用类似的语法：

```csharp
app.UseMvc(routes =>;
{
    routes.MapRoute("default","{controller=Home}/{action=Index}/{id?}");
});
```

在此示例中，名为"default"的路由具有已添加到路由表。 它定义带有占位符的路由模板*控制器*，*操作*，和*id*。控制器和操作占位符具有指定的默认值 ("主页"和"索引"，分别)，和是可选的 id 占位符 (借助于"？"应用于它)。 约定定义此处请求的第一部分应对应的状态为控制器上，与操作的第二个部分的名称，然后如有必要第三部分将表示一个 id 参数。 传统路由通常在一个位置对于应用程序，如中定义的启动类中的配置方法。

属性的路由将直接应用到控制器和操作而不是全局范围内指定。 这具有的优势是使它们更容易可见时要查看特定的方法，但意思路由的信息将不会在应用程序中的一个位置。 使用属性的路由，你可以轻松地指定为某个给定操作的多个路由，以及组合控制器和操作之间的路由。 例如: 

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
```

可以在 [HttpGet] 上指定路由和单独的类似属性，无需添加 [路由\]属性。 属性的路由还可以使用令牌来减少需要重复控制器或操作名称，如下所示：

```csharp
[Route("[controller\]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index()
}
```

一旦在找到给定的请求匹配到某个路由，但操作之前调用方法，将执行 ASP.NET 核心 MVC[模型绑定](https://docs.microsoft.com/aspnet/core/mvc/models/model-binding)和[模型验证](https://docs.microsoft.com/aspnet/core/mvc/models/validation)针对此请求。 模型绑定负责将传入的 HTTP 数据转换为.NET 类型指定为参数的操作方法的调用。 例如，如果操作方法预期 int id 参数，模型绑定将尝试提供从值作为请求的一部分提供此参数。 为此，请模型绑定查找已发布的窗体中的值、 本身，路由中的值和查询字符串值。 假设找到 id 值，它将转换为整数之前正传入到操作方法。

绑定模型之后但在调用的操作方法之前，将执行模型验证。 模型验证模型的类型，使用可选属性，并且可以帮助确保提供的模型对象符合某些数据要求。 某些值可以指定为必需的也限制为特定长度或数值范围，等等。如果指定的验证属性但模型不符合其要求，该属性 ModelState.IsValid 将为 false，并将可用于将发送到客户端发出请求的失败的验证规则集。

如果你使用的模型验证，你应确保始终检查模型在执行任何状态更改的命令，就以确保数据未损坏你的应用程序之前有效。 你可以使用[筛选器](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters)以避免需要添加此代码，在每个操作。 ASP.NET 核心 MVC 筛选器提供一种截获的请求，组的过程，以便可以在目标的基础上应用常见策略和跨领域问题。 与单个操作，整个控制器或全局应用程序，可以应用筛选器。

对于 web Api，ASP.NET 核心 MVC 支持[*内容协商*](https://docs.microsoft.com/aspnet/core/mvc/models/formatting)，允许以指定应如何格式化响应的请求。 根据请求中提供的标头，操作返回的数据将格式化 XML、 JSON 或另一个受支持的格式中的响应。 此功能可以提供相同的 API，由具有不同的数据格式要求的多个客户端使用。

> ### <a name="references--mapping-requests-to-responses"></a>引用 – 将请求映射到响应
> - **路由到控制器操作**
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing>
> - **模型绑定**https://docs.microsoft.com/aspnet/core/mvc/models/model-binding
> - **模型验证**
> <https://docs.microsoft.com/aspnet/core/mvc/models/validation>
> - **筛选器**https://docs.microsoft.com/aspnet/core/mvc/controllers/filters

## <a name="working-with-dependencies"></a>使用依赖关系

ASP.NET 核心内置支持和内部使用的一种技术称为[依赖关系注入](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)。 依赖关系注入是一种技术，启用应用程序的不同部分之间的松散耦合。 松散耦合是需要的因为这样可以更轻松地隔离的应用程序，允许进行测试或替换部分。 它还使可能性变小，应用程序的一部分中的更改会产生意外的影响应用程序中的其他位置。 依赖关系注入的依赖项反向原则，为基础，通常是实现打开/关闭原则关键。 当评估你的应用程序如何使用其依赖项，请注意[静态粘贴](http://deviq.com/static-cling/)代码告知，并记住 aphorism"[新是粘附](http://ardalis.com/new-is-glue)。"

当你的类对静态方法进行调用或访问静态属性，其基础结构上具有副作用或依赖关系，静态粘贴时发生。 例如，如果你的一个方法调用静态方法，后者反过来将写入数据库，你的方法是紧密耦合到数据库。 将中断该数据库调用的任何内容将中断你的方法。 测试此类方法是训练非常困难，因为此类测试需要商业模拟库来模拟静态调用，或仅使用一个测试数据库就地进行测试。 没有任何依赖于基础结构，尤其是那些完全无状态的的静态调用是合适调用，并让不影响耦合或 （超出耦合到静态调用本身的代码） 的可测试性的。

许多开发人员了解静态粘贴和全局状态的风险，但将仍紧密耦合到通过直接实例化的特定实现其代码。 "新 is 粘附"要作为此耦合，提醒和不使用新的关键字常规 condemnation。 就像使用静态方法调用，通常具有没有外部依赖项的类型的新实例不要不紧密耦合代码到实现详细信息或使测试更加困难。 但是，类实例化，每次需要花费只是一小段时间考虑是否它有意义硬编码到该特定实例中的特定位置，或如果它可能会更好的设计，以请求为依赖项的该实例。

### <a name="declare-your-dependencies"></a>声明依赖项

ASP.NET 核心围绕具有方法和类声明依赖项，以及请求这些作为自变量。 ASP.NET 应用程序通常在一个 Startup 类中, 进行设置其自身配置为支持在多个点的依赖关系注入。 如果你的启动类具有构造函数，它可以请求通过构造函数的依赖关系如下所示：

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

Startup 类的有趣，在于它没有显式类型要求。 它不会从的特殊启动基类继承，也不实现任何特定的接口。 你可以在您或不是，为其提供一个构造函数，并可以指定任意多个构造函数参数。 当 web 主机已配置为用于你的应用程序启动时，它将调用您告诉它要使用，Startup 类，并且将使用依赖关系注入来填充 Startup 类需要任何依赖关系。 当然，如果请求未配置 ASP.NET Core 所用的服务容器中的参数，你将收到异常，但只要坚持依赖项容器知道，你可以请求所需的任何内容。

在创建启动实例时，依赖关系注入已内置到从一开始，就你 ASP.NET Core 应用。 它不会阻止为 Startup 类的存在。 你还可以请求中的配置方法的依赖关系：

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

ConfigureServices 方法是此行为; 的例外它必须采用一个参数的类型 IServiceCollection。 它实际上不需要以支持依赖关系注入，因为一方面它负责将对象添加到服务容器中，并且在其他它有权访问通过 IServiceCollection 参数的所有当前配置服务。 因此，你可以使用 ASP.NET 核心服务集合中的 Startup 类，通过请求所需的服务作为参数或通过使用在 ConfigureServices IServiceCollection 每个部分中定义的依赖关系。

> [!NOTE]
> 如果你需要确保某些服务可供你 Startup 类，则可以配置这些使用 WebHostBuilder 和其 ConfigureServices 方法。

Startup 类是用于您如何构建 ASP.NET Core 应用程序，从控制器到你自己的服务筛选器的中间件的其他部分的模型。 在每种情况下，你应遵循[显式依赖关系原则](http://deviq.com/explicit-dependencies-principle/)、 请求依赖项而不是直接创建它们，并利用在整个应用程序的依赖关系注入。 请注意的位置和方式直接实例化实现中，尤其是服务和使用基础结构或产生负面影响的对象。 更喜欢使用在将应用程序核心中定义并在作为自变量传递到对特定的实现类型的硬编码引用的抽象。

## <a name="structuring-the-application"></a>构建应用程序

整体应用程序通常具有单一入口点。 对于 ASP.NET Core 的 web 应用程序，将 ASP.NET 核心 web 项目的入口点。 但是，这并不意味着解决方案应包含单个项目。 它可用于分解到不同的层应用程序，以便按照关注点分离。 分解成层后，超出文件夹到单独的项目，可帮助实现更好地封装很有帮助。 最好的方法来实现这些目标与 ASP.NET Core 应用程序是干净的体系结构中第 5 章所述的变体。 此方法时，以下应用程序的解决方案将包含单独的库 UI、 基础结构和 ApplicationCore。

除了这些项目，单独的测试项目也包含 （第 9 章讨论测试）。

应用程序的对象模型和接口应该放置 ApplicationCore 项目中。 此项目将尽可能情况下，具有尽可能少的依赖项和其他项目解决方案中的将引用它。 需要保留的业务实体定义在 ApplicationCore 项目中，是不直接依赖于基础结构的服务。

实现详细信息，例如如何执行持久性或可能如何将通知发送给用户，将保留在基础结构项目。 此项目将引用特定于实现的包，例如实体框架核心，但不是应公开有关这些实现在项目外的详细信息。 基础结构服务和存储库，应实现 ApplicationCore 项目中定义的接口，并且其持久性实现负责检索并将存储在 ApplicationCore 中定义的实体。

ASP.NET 核心项目本身负责任何 UI 级别问题，但不是应包含业务逻辑或基础结构的详细信息。 实际上，理想情况下它不应即使有依赖于基础结构项目，这将有助于确保将两个项目之间没有依赖关系引入意外。 可以使用 StructureMap，允许你在注册表中的每个项目的类中定义 DI 规则等第三方 DI 容器实现此操作。

分离中实现的详细信息的应用程序的另一种方法是让应用程序调用微服务，可能是部署在单个 Docker 容器中。 这提供的问题和分离比 DI 利用两个项目之间的更多分离，但具有附加的复杂性。

### <a name="feature-organization"></a>功能组织

默认情况下，ASP.NET Core 应用程序会将其文件夹结构，以包含控制器和视图，并经常 Viewmodel。 客户端代码，以支持这些服务器端结构通常的 wwwroot 文件夹中单独存储。 但是，由于通常处理任何给定的功能要求这些文件夹之间跳转大型应用程序可能会遇到与此组织的问题。 这将得到的文件和子文件夹中每个文件夹数增大时，导致了极大的解决方案资源管理器在滚动越来越困难。 此问题的一种解决方案是将应用程序代码通过组织*功能*而不是按文件类型。 此组织样式通常简称为功能文件夹或功能切片 (另请参阅：[垂直切片](http://deviq.com/vertical-slices/))。

ASP.NET 核心 MVC 支持区域为此目的。 使用区域，可以创建单独的控制器和视图文件夹 （以及任何关联的模型） 中每个区域文件夹集。 图 7-1 显示了使用区域的示例文件夹结构。

![](./media/image7-1.png)

图 7-1 示例区域组织

在使用区域，你必须使用属性修饰将控制器与它们所属的区域的名称：

```csharp
[Area("Catalog")]
public class HomeController
{}
```

你还需要将区域支持添加到路由：

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

除了区域的内置支持，还可以使用自己的文件夹结构和约定来代替特性和自定义路由。 这将使你能够功能文件夹未包含单独的文件夹的视图和控制器等，保留层次结构更简单，并使其更轻松地查看所有相关的每个功能在单个位置的文件。

ASP.NET 核心使用内置的约定类型来控制其行为。 你可以修改或替换这些约定。 例如，你可以创建会自动收到基于其命名空间 （通常对应于控制器所在的文件夹） 的给定控制器的功能名称的约定：

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

你然后此约定作为一个选项时指定支持 MVC 的添加 ConfigureServices 中的应用程序：

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

ASP.NET 核心 MVC 还使用约定来找到视图。 你可以重写它使用自定义约定，以便视图将位于功能文件夹 （使用 FeatureConvention，上面提供的功能名称）。 你可以了解有关这种方法的详细信息和 MSDN 文章中，从下载的工作示例[ASP.NET 核心 MVC 的功能切片](https://msdn.microsoft.com/magazine/mt763233.aspx)。

### <a name="cross-cutting-concerns"></a>跨领域问题

随着应用程序的增长，则它变得越来越重要抽取跨领域问题，以消除重复和保持一致性。 在 ASP.NET Core 应用程序中的跨领域问题的一些示例，身份验证、 模型验证规则、 输出缓存，日期和错误处理，但是有许多其他。 ASP.NET 核心 MVC[筛选器](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters)让你运行代码之前或之后在请求处理管道中的某些步骤。 例如，筛选器可以运行之前和之后模型绑定之前, 和之后的操作，或之前和之后的操作的结果。 授权筛选器还可用于控制对管道的其余部分的访问。 图 7-2 显示如何执行流传递筛选器，如果请求配置。

![通过授权筛选器、 资源筛选器、 模型绑定，操作筛选器、 操作执行和操作结果转换、 异常筛选器，结果筛选器和结果执行处理该请求。 在路上，请求仅由处理结果筛选器和资源筛选器才会发送到客户端的响应。](./media/image7-2.png)

图 7-2 请求通过筛选器和请求管道的执行。

筛选器通常会作为属性实现，因此你可以将它们应用控制器或操作。 当以这种方式，指定在操作级别覆盖或指定的控制器级别筛选器后的生成筛选器添加自身重写全局筛选器。 例如，\[路由\]属性可用来生成控制器和操作之间的路由。 同样，可以控制器级别配置授权和将其替换原来的各项操作，如下面的示例所示：

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous]
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

第一种方法，登录名，使用 AllowAnonymous 筛选器 （属性） 重写在控制器级别设置的 Authorize 筛选器。 ForgotPassword 操作 （和不具有 AllowAnonymous 特性类中的任何其他操作） 将需要身份验证的请求。

可以使用筛选器，以消除重复的常见错误 Api 处理策略窗体中。 例如，典型的 API 策略是返回 NotFound 响应引用不存在的密钥的请求和错误的请求响应，如果模型验证失败。 下面的示例演示在操作中的这两种策略：

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

不允许使用条件如下的代码变得杂乱你操作方法。 相反，请求到可以基于根据需要应用的筛选器的策略。 在此示例中，模型验证检查，这应发生的随时命令发送到 API，可替换的以下属性：

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

同样，可以使用筛选器以检查是否存在一条记录，并返回 404 之前执行的操作，不再需要的操作中执行这些检查。 一旦拉出常见约定并组织你的解决方案基础结构代码和业务逻辑分开从你的 UI，你的 MVC 操作方法应非常精简：

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

你可以阅读更多有关实现筛选器和 MSDN 文章中，从下载的工作示例[真实世界 ASP.NET 核心 MVC 筛选器](https://msdn.microsoft.com/magazine/mt767699.aspx)。

> ### <a name="references--structuring-applications"></a>引用 – 构建应用程序
> - **区域**  
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/areas>
> - **MSDN – ASP.NET Core MVC 的功能切片**
>  <https://msdn.microsoft.com/magazine/mt763233.aspx>
> - **筛选器**  
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/filters>
> - **MSDN – 现实世界 ASP.NET Core MVC 筛选器**  
> <https://msdn.microsoft.com/magazine/mt767699.aspx>

## <a name="security"></a>安全性

保护 web 应用程序是具有许多注意事项的大型主题。 在其最基本级别，涉及到安全确保你知道谁，给定的请求的来源，然后确保该请求仅有权访问它应的资源。 身份验证是比较对的请求中的受信任的数据存储区中，若要查看是否请求应被视为来自已知实体提供凭据的过程。 授权是限制对基于用户标识的某些资源的访问的过程。 第三个安全问题保护请求以防止窃听由第三方，为其至少应[确保你的应用程序使用 SSL](https://docs.microsoft.com/aspnet/core/security/enforcing-ssl)。

### <a name="authentication"></a>身份验证

ASP.NET 核心标识是可用于支持你的应用程序的登录功能的成员身份系统。 它还具有对本地用户帐户的支持以及等 Microsoft 帐户、 Twitter、 Facebook、 Google、 和的详细信息的提供程序的外部登录提供程序支持。 除了 ASP.NET 核心标识你的应用程序可以使用 windows 身份验证，或第三方标识提供程序，例如[标识服务器](https://github.com/IdentityServer/IdentityServer4)。

ASP.NET 核心标识包含新的项目模板中，如果选择单个用户帐户选项。 此模板包括注册、 登录名、 外部登录名、 忘记了的密码和其他功能的支持。

![](./media/image7-3.png)

图 7-3 选择单个用户帐户具有预先配置的标识。

在启动时，在 ConfigureServices 和配置中配置身份验证支持：

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

很重要 UseIdentity 出现在 UseMvc 之前，在配置方法。 在配置中 ConfigureServices 时标识，你会注意到 AddDefaultTokenProviders 调用。 这与令牌可用于保护 web 之间的通信，但改为引用创建可以发送到通过短信或电子邮件以使其以确认其身份的用户的提示的提供程序无关。

你可以详细了解[配置双因素身份验证](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)和[启用外部登录提供程序](https://docs.microsoft.com/aspnet/core/security/authentication/social/)从官方 ASP.NET 核心文档。

### <a name="authorization"></a>授权

授权的最简单形式涉及限制匿名用户访问。 这可以通过只需应用来实现\[Authorize\]属性设为特定控制器或操作。 如果正在使用角色，该属性可以进一步扩展以限制对属于特定角色，用户的访问，如所示：

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

在这种情况下，属于是 HRManager 或财务角色 （或两者） 的用户将有权访问 SalaryController。 要求用户属于多个角色 （而不仅仅是一个多个），你可以将该属性多次，指定每次的所需的角色。

指定一组特定的角色，因为在许多不同的控制器和操作的字符串将导致不希望重复。 你可以配置授权策略，可封装授权规则，，然后应用时指定的策略而不是单个角色\[Authorize\]属性：

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

以这种方式使用策略，可以分隔的各种操作的特定角色或将应用于它的规则受到限制。 更高版本，如果你创建一个新角色，需要具有对特定资源的访问权限，你可以仅更新策略，而不是更新角色的每个列表上每个\[Authorize\]属性。

#### <a name="claims"></a>声明

声明是用户的表示经过身份验证的属性的名称值对。 例如，你可能会以声明方式存储用户的员工数。 声明随后可作为授权策略的一部分。 你可以创建名为"EmployeeOnly"的策略，则需要存在的声明称为"EmployeeNumber"，在此示例中所示：

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

此策略无法随后可用于\[Authorize\]属性以保护任何控制器和/或操作，如上面所述。

#### <a name="securing-web-apis"></a>保护 Web Api

大多数 web Api 应实现的基于令牌的身份验证系统。 令牌身份验证是无状态和设计可缩放性。 在基于令牌的身份验证系统中，客户端必须首先进行身份验证的身份验证提供程序。 如果成功，客户端颁发一个令牌，只需是加密有意义的字符字符串。 然后，客户端需要向 API 发出请求，它会添加此令牌作为请求标头。 服务器然后验证完成请求之前在请求标头中找到的令牌。 图 7-4 演示了此过程。

![TokenAuth](./media/image7-4.png)

**图 7-4。** 基于令牌的身份验证的 Web Api。

> ### <a name="references--security"></a>引用 – 安全
> - **安全文档概述**  
> https://docs.microsoft.com/aspnet/core/security/
> - **强制在 ASP.NET Core 应用程序的 SSL**  
> <https://docs.microsoft.com/aspnet/core/security/enforcing-ssl>
> - **标识简介**  
> <https://docs.microsoft.com/aspnet/core/security/authentication/identity>
> - **授权简介**  
> <https://docs.microsoft.com/aspnet/core/security/authorization/introduction>
> - **身份验证和授权，而 Azure App Service 中的 API 应用**  
> <https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication>

## <a name="client-communication"></a>客户端通信

除了页，并且对通过 web Api 的数据的请求的响应，ASP.NET Core 应用可直接与连接的客户端进行通信。 此出站通信可以使用各种传输技术，最常见的是 Websocket。 ASP.NET 核心 SignalR 是一个库，即可轻松访问类到你的应用程序的实时服务器到客户端通信功能。 SignalR 支持多种传输技术，包括 Websocket，和提取远多的开发人员的实现详细信息。

ASP.NET 核心 SignalR 我们正在开发，并将在 ASP.NET Core 的下一个版本中可用。 但是，其他[开放源代码 Websocket 库](https://github.com/radu-matei/websocket-manager)当前可用。

实时客户端通信，是否使用 Websocket 直接或其他技术，可在多个应用程序方案。 一些示例包括：

-   实时聊天室应用程序

-   监视应用程序

-   作业进度更新

-   通知

-   交互式窗体应用程序

在生成到应用程序的客户端通信时，通常有两个组件：

-   服务器端连接管理器 （SignalR Hub，WebSocketManager WebSocketHandler）

-   客户端库

客户端并不局限于浏览器 – 移动应用程序、 控制台应用和其他的本机应用还可以使用 SignalR/Websocket 通信。 下面的简单程序回显发送到的聊天应用程序到控制台，WebSocketManager 示例应用程序的一部分的所有内容：

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

请考虑的方式你的应用程序直接与客户端应用程序进行通信，然后考虑实时通信是否可以提高应用程序的用户体验。

> ### <a name="references--client-communication"></a>引用 – 客户端通信
> - **ASP.NET 核心 SignalR**  
> <https://github.com/aspnet/SignalR>
> - **WebSocket 管理器**  
> https://github.com/radu-matei/websocket-manager

## <a name="domain-driven-design--should-you-apply-it"></a>域驱动的设计 – 应将其应用？

域驱动设计 (DDD) 是一种构建强调的将精力集中的软件的敏捷方法*业务领域*。 它强调大量通信以及与业务域 expert(s) 可以与开发人员实际系统的工作原理的交互。 例如，如果你正在生成处理股票交易的系统，则域专家可能有经验的常用 broker。 DDD 旨在解决大型、 复杂的业务问题，并且不通常适用于较小、 更简单的应用程序，了解和建模域中的投资是不值得。

在生成软件以下 DDD 方法时，团队 （包括非技术利益干系人和 contributors （参与者）） 应开发*无处不在语言*问题空间。 即，相同的术语应用于所模拟的实际概念、 软件同等和以保留概念 （例如，数据库表） 可能存在的任何结构。 因此，无处不在的语言中所述的概念应构成的基础你*域模型*。

您的域模型组成之间来表示系统的行为进行交互的对象。 这些对象可能分为以下类别：

-   [实体](http://deviq.com/entity/)，分别表示与线程的标识的对象。 使用密钥依据可以以后检索这些实体通常存储在持久性。

-   [聚合](http://deviq.com/aggregate-pattern/)，分别表示应保持作为一个单元的对象组。

-   [值对象](http://deviq.com/value-object/)，这表示可以比较基于其属性值的总和的概念。 例如，DateRange 包含开始和结束日期。

-   [域事件](https://martinfowler.com/eaaDev/DomainEvent.html)，分别表示系统内发生的事，感兴趣的系统的其他部分。

请注意 DDD 域模型应封装复杂模型中的行为。 实体，特别是，不应仅为属性的集合。 当域模型中缺少行为，并且只是表示系统的状态时，它称为[贫乏模型](http://deviq.com/anemic-model/)，即在 DDD 不可取。

除了这些模型类型，DDD 通常采用多种模式：

-   [存储库](http://deviq.com/repository-pattern/)，提取持久性详细信息。

-   [工厂](https://en.wikipedia.org/wiki/Factory_method_pattern)，用于封装复杂的对象创建。

-   域事件，为分离依赖从触发行为的行为。

-   [服务](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/)、 封装复杂的行为和/或基础结构实现详细信息。

-   [命令](https://en.wikipedia.org/wiki/Command_pattern)、 为分离发出命令和执行命令本身。

-   [规范](http://deviq.com/specification-pattern/)，用于封装查询详细信息。

DDD 还建议讨论过，干净体系结构的使用可以进行更松散耦合，封装和可以轻松地验证使用单元测试的代码。

### <a name="when-should-you-apply-ddd"></a>当你应将 DDD

DDD 非常适合于具有 （而不仅是技术） 的重要业务复杂性的大型应用程序。 应用程序应需要了解的域专业人员。 域模型本身，表示业务规则和交互超出只需存储和从数据存储检索的各种记录的当前状态应为重要行为。

### <a name="when-shouldnt-you-apply-ddd"></a>当你不应将 DDD

DDD 涉及建模、 体系结构和可能不合理的较小的应用程序或应用程序是实质上是只需 CRUD （创建/读取/更新/删除） 的通信中的投资。 如果你选择接近你的应用程序后 DDD，但是发现你的域具有与任何行为贫乏模型，你可能需要重新考虑您的方法。 你的应用程序可能不需要 DDD，或者你可能需要帮助重构你的应用程序能够在域模型中，而不是数据库或用户界面中的业务逻辑进行封装。

混合方法将仅使用 DDD，适用于事务性的也更复杂的区域的应用程序，但不是能为更简单 CRUD 或应用程序的只读部分。 例如，如果你要查询以显示报表或仪表板的数据可视化的数据不需要有聚合的约束。 它是完全可以接受具有此类要求的单独的、 更简单的读取的模型。

> ### <a name="references--domain-driven-design"></a>引用 – 域驱动的设计
> - **用英文 （StackOverflow 答案） DDD**  
> <https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488>

## <a name="deployment"></a>部署

有几个步骤涉及在过程中部署 ASP.NET Core 应用程序，而不考虑它的托管位置。 第一步是发布应用程序，这可以实现使用 dotnet 发布 CLI 命令。 这将编译该应用程序，并将所有到指定文件夹中运行应用程序所需的文件。 当从 Visual Studio 进行部署时，此步骤为你自动执行。 发布文件夹包含.exe 和.dll 文件以及该应用程序及其依赖项。 自包含的应用程序还将包括.NET 运行时的版本。 配置文件、 静态的客户端资产和 MVC 视图，还将包括 ASP.NET Core 应用程序。

ASP.NET 核心应用程序是控制台应用程序时在服务器启动和重新启动，如果应用程序 （一个或多个） 崩溃必须启动。 一个进程管理器可以用于自动执行此过程。 有关 ASP.NET 核心最常见的进程管理器是 Nginx 和 Apache 在 Linux 和 IIS 上的或在 Windows 上的 Windows 服务。

一个进程管理器中，除了 Kestrel web 服务器中托管的 ASP.NET Core 应用程序必须使用反向代理服务器。 从 internet 接收 HTTP 请求和一些初步处理后将其转发给 Kestrel 的反向代理服务器。 反向代理服务器对应用程序提供的安全层和边缘部署 （从 Internet 的流量到公开） 所需。 Kestrel 来说相对较新，不尚未提供对某些攻击防御能力。 Kestrel 也不支持托管的相同端口上的多个应用程序，因此技术主机标头不能与使用它来启用承载上的相同的端口和 IP 地址的多个应用程序。

![到 Internet 的 kestrel](./media/image7-5.png)

图 7-5 反向代理服务器后面 Kestrel 中托管的 ASP.NET

反向代理可在其中很有帮助的另一种情况是安全使用 SSL/HTTPS 的多个应用程序。 在这种情况下，仅反向代理需要已配置 SSL。 反向代理服务器和 Kestrel 之间的通信无法接管位置 HTTP，如图 7-6 中所示。

![](./media/image7-6.png)

图 7-6 HTTPS 保护反向代理服务器后面托管的 ASP.NET

日益盛行的方法是承载在 Docker 容器，然后可以本地托管或部署到 Azure 的基于云的承载 ASP.NET Core 应用程序。 Docker 容器可包含在 Kestrel 上, 运行的应用程序代码，并如上所示将后面的反向代理服务器，部署。

如果你要托管在 Azure 上的应用程序，你可以将 Microsoft Azure 应用程序网关用作专用的虚拟设备提供多个服务。 除了充当的单个应用程序的反向代理时，应用程序网关也可以提供以下功能：

-   HTTP 负载平衡

-   SSL 卸载 (仅到 Internet 的 SSL)

-   端到端 SSL

-   多站点路由 （合并在单个应用程序网关上的最多 20 个站点）

-   Web 应用程序防火墙

-   Websocket 支持

-   高级诊断功能

*了解有关章 10 中的 Azure 部署选项的详细信息。*

> ### <a name="references--deployment"></a>引用 – 部署
> - **承载和部署概述**  
> <https://docs.microsoft.com/aspnet/core/publishing/>
> - **何时使用反向代理使用 Kestrel**  
> <https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy>
> - **在 Docker 中承载 ASP.NET Core 应用程序**  
> <https://docs.microsoft.com/aspnet/core/publishing/docker>
> - **引入 Azure 应用程序网关**  
> <https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction>

>[!div class="step-by-step"]
[以前](常用的客户端-端-web-technologies.md) [下一步] (work-with-data-in-asp-net-core-apps.md)
