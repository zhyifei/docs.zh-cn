---
title: 开发 ASP.NET Core MVC 应用
description: 使用 ASP.NET Core 和 Azure 构建新式 Web 应用程序 | 开发 ASP.NET Core MVC 应用
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c10bf66dd37f0d99c038db7f95999d84986152fa
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="develop-aspnet-core-mvc-apps"></a>开发 ASP.NET Core MVC 应用

> “第一次是否正确完成并不重要。 最后一次正确完成才至关重要。”  
> — Andrew Hunt 和 David Thomas

## <a name="summary"></a>总结

ASP.NET Core 是一个跨平台的开源框架，用于构建新式云优化 Web 应用程序。 ASP.NET Core 具有轻量级和模块化的特点，并且内置了对依赖关系注入的支持，因此具有更好的可测试性和可维护性。 而 MVC 支持构建新式 Web API 和基于视图的应用，ASP.NET Core 与之结合后将成为一个功能强大的框架，用于构建企业 Web 应用程序。

## <a name="mapping-requests-to-responses"></a>将请求映射到响应

ASP.NET Core 应用的核心在于将传入请求映射到传出响应。 较低级别的实现方式是使用中间件，简单的 ASP.NET Core 应用和微服务可能只包含自定义中间件。 在某种程度上，使用 ASP.NET Core MVC 可以实现更高级别的操作，需要考虑路由、控制器和操作。 每个传入请求都会和应用程序的路由表进行对比，如果找到匹配的路由，则调用关联的操作方法（属于控制器）来处理该请求。 如果未找到匹配的路由，则调用错误处理程序（此时返回 NotFound 结果）。

ASP.NET Core MVC 应用可以使用传统路由或属性路由，或二者同时使用。 传统路由在代码中定义，使用类似以下示例中的语法指定路由约定：

```csharp
app.UseMvc(routes =>;
{
    routes.MapRoute("default","{controller=Home}/{action=Index}/{id?}");
});
```

此示例向路由表添加了一个名为“default”的路由。 它定义了一个具有 controller、action 和 id 占位符的路由模板。controller 和 action 占位符具有指定的默认值（分别为“Home”和“Index”），id 占位符则为可选项（通过应用“?”来实现）。 此处定义的约定规定，请求的第一部分应与控制器的名称对应，第二部分与操作对应，第三部分（如有）表示 id 参数。 通常在同一个位置定义应用程序的传统路由，例如在 Startup 类的 Configure 方法中。

属性路由直接应用到控制器和操作，而不是在全局范围内指定。 其优势在于，查看特定方法时，属性路由更容易发现，但也意味着路由信息不会保存在应用程序中的同一个地方。 通过属性路由可以为给定操作轻松指定多个路由，并将控制器和操作之间的路由合并在一起。 例如:

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
```

可以在 [HttpGet] 和类似属性上指定路由，而无需添加单独的 [Route\] 属性。 属性路由还可以通过使用令牌来减少重复控制器或操作名称的次数，如下所示：

```csharp
[Route("[controller\]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index()
}
```

给定请求与路由匹配之后，ASP.NET Core MVC 会对该请求执行[模型绑定](https://docs.microsoft.com/aspnet/core/mvc/models/model-binding)和[模型验证](https://docs.microsoft.com/aspnet/core/mvc/models/validation)，然后才调用操作方法。 模型绑定负责将传入到指定 .NET 类型的 HTTP 数据转换为要调用的操作方法的参数。 例如，如果操作方法需要一个 int id 参数，模型绑定将尝试根据请求中提供的值来提供此参数。 为此，模型绑定会查找已发布表单中的值、路由中的值和查询字符串值。 假设找到了 id 值，该值会被转换为整数，然后传入操作方法。

模型验证发生在绑定模型之后，调用操作方法之前。 模型验证对模型类型使用可选属性，且有助于确保提供的模型对象符合特定数据要求。 可以将某些值指定为必需项，将其限制为特定长度，或将其限制在一定数值范围内，等等。如果指定了验证特性，但该模型不符合其要求，则属性 ModelState.IsValid 将为 false，并且失败的验证规则集将可被发送到发出请求的客户端。

使用模型验证时，执行任何状态更改命令之前，务必确保模型有效，以防无效数据损坏应用。 使用[筛选器](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters)可避免在每个操作中都为此添加代码的需要。 ASP.NET Core MVC 筛选器具有截获多组请求的功能，因此可以有针对性地应用通用策略和横切关注点。 筛选器可应用于单个操作、整个控制器或应用程序全局。

对于 Web API，ASP.NET Core MVC 支持[*内容协商*](https://docs.microsoft.com/aspnet/core/mvc/models/formatting)，允许对指定如何设置响应格式进行请求。 根据请求中提供的标头，操作返回的数据将采用 XML、JSON 或其他支持格式作为响应的格式。 借助此功能，同一个 API 可供数据格式要求不同的多个客户端使用。

> ### <a name="references--mapping-requests-to-responses"></a>参考 - 将请求映射到响应
> - **路由到控制器操作**
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing>
> - **模型绑定** https://docs.microsoft.com/aspnet/core/mvc/models/model-binding
> - **模型验证**
> <https://docs.microsoft.com/aspnet/core/mvc/models/validation>
> - **筛选器** https://docs.microsoft.com/aspnet/core/mvc/controllers/filters

## <a name="working-with-dependencies"></a>处理依赖关系

ASP.NET Core 内置了对[依赖关系注入](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)技术的支持，并且在内部使用这一技术。 依赖关系注入技术可以在应用程序的不同部分之间实现松散耦合。 比较松散的耦合更符合需要，因为它可以更轻松地将应用程序的某些部分隔离开，然后进行测试或替换。 它还可以降低对应用程序某个部分进行更改会对应用程序中的其他位置产生意外影响的可能性。 依赖关系注入的基础是依赖关系反转原则，并且通常是实现开放/闭合原则的关键。 评估应用程序对其依赖关系的处理方式时，请注意 [static cling](http://deviq.com/static-cling/)（静态粘附）这一代码味，并请记住这句格言：[新增即粘附](http://ardalis.com/new-is-glue)。

类调用静态方法或访问静态属性时，会对基础结构造成负面影响或产生依赖关系，此时会发生静态粘附。 例如，如果一个方法调用静态方法，静态方法反过来又写入数据库，则该方法与该数据库紧密耦合。 破坏该数据库调用的任何内容都会破坏该方法。 测试此类方法非常困难，因为此类测试要么需要使用商业模拟库来模拟静态调用，要么只能使用已有测试数据库进行测试。 不依赖于任何基础结构的静态调用，尤其是完全无状态的静态调用可以进行正常调用，并且对耦合或可测试性没有任何影响（超越了将代码耦合到静态调用本身）。

许多开发人员知道静态粘附和全局状态的风险，但仍会通过直接实例化将其代码与具体实现紧密耦合。 “新增即粘附”旨在提醒注意这种耦合，并非一律谴责使用新关键词。 和静态方法调用一样，没有外部依赖关系的类型的新实例通常不会将代码紧密耦合到实现详细信息，或增加测试的难度。 但每次将类实例化时，花一小点时间思考对该特定位置的该特定实例进行硬编码是否有意义，或者说如果将该实例作为依赖项进行请求会不会更好。

### <a name="declare-your-dependencies"></a>声明依赖关系

ASP.NET Core 的构建原理是让方法和类声明依赖关系，并将其作为参数进行请求。 ASP.NET 应用程序通常在 Startup 类中进行设置，而该类本身就配置为在多处支持依赖关系注入。 如果 Startup 类具有构造函数，则可以通过构造函数请求依赖关系，如下所示：

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

Startup 类很有意思，因为它没有显式的类型要求。 它不继承特殊的 Startup 基类，也不实现任何特定的接口。 可为其提供构造函数，也可不提供，并且可以为构造函数指定任意所需数量的参数。 为应用程序配置的 Web 主机启动时，该主机将调用你命令其使用的 Startup 类，并将使用依赖关系注入来填充 Startup 类请求的任何依赖关系。 当然，如果 ASP.NET Core 使用的服务容器中未配置请求的参数，则会引发异常，但只要是粘附到容器知晓的依赖项，则可以请求任何所需内容。

依赖关系注入从一开始创建 Startup 实例时就内置在 ASP.NET Core 应用中。 它不会为 Startup 类在此停留。 也可以在 Configure 方法中请求依赖关系：

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

ConfigureServices 方法是此行为的例外情况，它必须使用 IServiceCollection 类型的一个参数。 实际上它并不需要支持依赖关系注入，因为一方面它负责向服务容器添加对象，另一方面它有权通过 IServiceCollection 参数访问所有当前已配置的服务。 因此在 Startup 类的每个部分均可使用 ASP.NET Core 服务集合中定义的依赖关系，方法是以参数形式请求所需服务，也可通过在 ConfigureServices 中使用 IServiceCollection。

> [!NOTE]
> 如果需确保某些服务可供 Startup 类使用，可以使用 WebHostBuilder 及其 ConfigureServices 方法对其进行配置。

Startup 类是一个范例，应照此构建 ASP.NET Core 应用程序的其他部分，从控制器到中间件到筛选器再到自己的服务。 在任何情况下都应遵守[显式依赖关系原则](http://deviq.com/explicit-dependencies-principle/)，请求依赖关系，而不要直接创建依赖关系，在整个应用程序中充分利用依赖关系注入。 注意对实现进行直接实例化的位置和方式，特别是使用基础结构或会产生负面影响的服务和对象。 相较于对特定实现类型的引用进行硬编码，最好是使用在应用程序核心中定义并作为参数传递的抽象元素。

## <a name="structuring-the-application"></a>构建应用程序

整体式应用程序通常只有一个入口点。 对 ASP.NET Core Web 应用程序而言，入口点是 ASP.NET Core Web 项目。 但是，这并不意味着解决方案只应包含一个项目。 按照分离关注点的原则，将应用程序分解到不同层中非常有用。 分解到不同层后，超越文件夹来分离项目很有好处，可帮助实现更好的封装。 通过 ASP.NET Core 应用程序实现这些目标的最佳方法是第 5 章中所述的干净体系结构的变体。 按照此方法，应用程序的解决方案将包含 UI、基础结构和 ApplicationCore 各自单独的库。

除这些项目之外，还包含一个单独的测试项目（第 9 章中对测试进行介绍）。

应用程序的对象模型和接口应放在 ApplicationCore 项目中。 此项目应具有尽可能少的依赖关系，可供解决方案中的其他项目引用。 需要保留的业务实体以及不直接依赖基础结构的服务在 ApplicationCore 项目中进行定义。

实现的详细信息（例如如何执行保留或如何将通知发送给用户）保存在 Infrastructure 项目中。 此项目将引用特定于实现的包，例如 Entity Framework Core，但不应在此项目之外泄露这些实现的详细信息。 基础结构服务和存储库应实现在 ApplicationCore 项目中定义的接口，其持久性实现负责检索和存储在 ApplicationCore 中定义的实体。

ASP.NET Core 项目本身负责任何 UI 级别的问题，但不应包含业务逻辑或基础结构详细信息。 实际上，最理想的情况是它甚至没有对 Infrastructure 项目的依赖关系，这样可确保不意外引入两个项目之间的依赖关系。 第三方 DI 容器（例如 StructureMap）可用于定于每个项目中 Registry 类中的 DI 规则，从而帮助实现这一目的。

将应用程序与实现详细信息分离开的另一种方法是让应用程序调用微服务，微服务可能部署在各 Docker 容器中。 相较于在两个项目之间利用 DI，这种方法更好地分离关注点，且解耦效果更好，但也更复杂一些。

### <a name="feature-organization"></a>功能整理

默认情况下，ASP.NET Core 应用程序将其文件夹结构整理为包含 Controllers 和 Views，还经常包含 ViewModels。 支持这些服务器端结构的客户端代码通常单独存放在 wwwroot 文件夹中。 但是对于大型应用程序而言，这种整理方式可能会出现问题，因为处理任何给定功能通常会要求在这些文件夹之间跳转。 每个文件夹中的文件和子文件夹数量越多，通过解决方案资源管理器的滚动就越多，这种整理方式实现起来也就越难。 解决此问题的其中一种办法是按功能，而不要按文件类型来整理应用程序代码。 这种整理方式通常被称为功能文件夹或功能切片（另请参阅：[垂直切片](http://deviq.com/vertical-slices/)）。

ASP.NET Core MVC 支持使用 Areas 实现此目的。 使用区域可以在每个 Area 文件夹中创建单独的 Controllers 和 Views 文件夹集（以及任何关联的模型）。 图 7-1 显示了一个使用 Areas 的示例文件夹结构。

![](./media/image7-1.png)

图 7-1 示例 Area 整理

使用 Areas 时，必须使用属性通过控制器所属的区域名称来修饰控制器：

```csharp
[Area("Catalog")]
public class HomeController
{}
```

还需要向路由添加区域支持：

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

除了对 Areas 的内置支持，还可以使用你自己的文件夹结构和约定来代替属性和自定义路由。 这样可以让功能文件夹中不包含单独的 Views 和 Controllers 等文件夹，让层次结构更简单，并且可以更轻松地在一个地方查看每个功能的所有相关文件。

ASP.NET Core 使用内置的约定类型来控制其行为。 可以修改或替换这些约定。 例如，可以创建一个约定，自动基于给定控制器的命名空间获取其功能名称（通常对应于控制器所在的文件夹）：

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

然后在 ConfigureServices 中向应用程序添加 MVC 支持时将此约定指定为一个选项：

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

ASP.NET Core MVC 还使用约定来确定视图的位置。 可以使用自定义约定取而代之，使视图位于功能文件夹中（使用上述 FeatureConvention 提供的功能名称）。 可在 MSDN 文章 [ASP.NET Core MVC 的功能切片](https://msdn.microsoft.com/magazine/mt763233.aspx)中详细了解此方法并下载工作示例。

### <a name="cross-cutting-concerns"></a>横切关注点

随着应用程序的发展，将横切关注点分解出来，以消除重复和保持一致性变得越来越重要。 ASP.NET Core 应用程序中的横切关注点非常多，例如身份验证、模型验证规则、输出缓存和错误处理等等。 ASP.NET Core MVC [筛选器](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters)允许在请求处理管道中的特定步骤之前或之后运行代码。 例如，可以在模型绑定之前/之后、某个操作之前/之后或某个操作结果之前/之后运行筛选器。 还可以使用授权筛选器来控制对管道其余部分的访问权限。 图 7-2 显示了请求执行如何流经筛选器（如果配置）。

![请求通过授权筛选器、资源筛选器、模型绑定、操作筛选器、操作执行和操作结果转换、异常筛选器、结果筛选器和结果执行进行处理。 返回时，请求仅由结果筛选器和资源筛选器进行处理，变成发送到客户端的响应。](./media/image7-2.png)

图 7-2 请求执行通过各筛选器和请求管道。

筛选器通常作为属性实现，因此可应用于控制器或操作。 以这种方式添加时，在操作级别指定的筛选器会覆盖在控制器级别指定的筛选器（会覆盖全局筛选器）或在其基础之上生成。 例如，\[Route\] 属性可用来生成控制器和操作之间的路由。 同样，可以在控制器级别配置授权，然后被各操作覆盖，如下所示：

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous]
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

第一个方法 Login 使用 AllowAnonymous 筛选器（属性）来覆盖在控制器级别设置的 Authorize 筛选器。 ForgotPassword 操作（以及类中没有 AllowAnonymous 属性的任何其他操作）需要经过身份验证的请求。

筛选器可作为 API 的常见错误处理策略，用于消除重复。 例如，如果请求引用的关键字不存在，典型的 API 策略会返回 NotFound 响应，如果模型验证失败，则返回 BadRequest 响应。 下面的示例通过操作演示了这两种策略：

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

切勿让操作方法因为类似于此的条件代码变得杂乱。 而应该将策略放在可按需应用的筛选器中。 此示例中，无论何时只要向 API 发送命令就会进行模型验证检查，可使用以下属性替换模型验证检查：

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

同样，可以使用筛选器来检查某条记录是否存在，并在执行操作前返回 404，而无需在操作中执行这些检查。 将常见约定提取出来，并在整理解决方案时将基础结构代码和业务逻辑与 UI 分离开，这样 MVC 操作方法会变得极其精简：

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

可在 MSDN 文章[实际的 ASP.NET Core MVC 筛选器](https://msdn.microsoft.com/magazine/mt767699.aspx)中了解有关实现筛选器的详细信息并下载工作示例。

> ### <a name="references--structuring-applications"></a>参考 - 构建应用程序
> - **区域**  
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/areas>
> - **MSDN - ASP.NET Core MVC 的功能切片**
>  <https://msdn.microsoft.com/magazine/mt763233.aspx>
> - **筛选器**  
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/filters>
> - **MSDN - 实际的 ASP.NET Core MVC 筛选器**  
> <https://msdn.microsoft.com/magazine/mt767699.aspx>

## <a name="security"></a>安全性

保护 Web 应用程序是一个非常大的主题，涉及到许多问题。 安全性涉及的最基本问题是，确保你知道是谁发出的给定请求，然后确保该请求只对它应访问的资源具有访问权限。 身份验证是将请求提供的凭据与受信任数据存储中的凭据进行对比的过程，目的在于确定该请求是否应被视为来源于已知实体。 授权是根据用户标识限制对某些资源的访问权限的过程。 第三个安全问题是保护请求免遭第三方窃听，对于此问题至少应[确保 SSL 由你的应用程序使用](https://docs.microsoft.com/aspnet/core/security/enforcing-ssl)。

### <a name="authentication"></a>身份验证

ASP.NET Core 标识是一个成员身份系统，可用于支持应用程序的登录功能。 它支持本地用户帐户，也支持来自 Microsoft Account、Twitter、Facebook 和 Google 等提供者的外部登录。 除 ASP.NET Core 标识之外，应用程序还可以使用 Windows 身份验证或 [Identity Server](https://github.com/IdentityServer/IdentityServer4) 等第三方标识提供者。

如果选择了“个人用户帐户”选项，ASP.NET Core 标识将包含在新的项目模板中。 此模板包括对注册、登录名、外部登录名、忘记的密码和其他功能的支持。

![](./media/image7-3.png)

图 7-3 选择“个人用户帐户”以预配标识。

在 ConfigureServices 和 Configure 中，标识支持都在 Startup 中配置：

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

在 Configure 方法中，UseIdentity 应出现在 UseMvc 之前，这一点很重要。 在 ConfigureServices 中配置标识时，请注意对 AddDefaultTokenProviders 的调用。 这与用于保护 Web 通信的令牌无关，它引用的是创建提示的提供者，该提示会通过短信或电子邮件发送给用户让其确认身份。

可从官方 ASP.NET Core 文档详细了解有关[配置双重身份验证](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)和[启用外部登录提供者](https://docs.microsoft.com/aspnet/core/security/authentication/social/)的信息。

### <a name="authorization"></a>授权

最简单的授权方式包括限制匿名用户的访问权限。 只需对某些控制器和操作应用 \[Authorize\] 属性即可实现此目的。 如果正在使用角色，可进一步扩展该属性，用于限制属于特定角色的用户的访问权限，如下所示：

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

此示例中，属于 HRManager 或 Finance 角色（或同时属于这两个角色）的用户将有权访问 SalaryController。 如需要求用户属于多个角色，而不是属于多个角色中的某一个角色，可多次应用该属性，每次指定一个所需角色。

在许多不同的控制器和操作中以字符串形式指定特定角色集可能会导致不必要的重复。 可配置封装授权规则的授权策略，然后在应用 \[Authorize\] 属性时指定该策略，而不是各个角色：

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

以这种方式使用策略可将受限制的操作与适用于该操作的特定角色或规则区分开。 之后创建需访问特定资源的新角色时，只需更新策略即可，而无需更新每个 \[Authorize\] 属性上的每个角色列表。

#### <a name="claims"></a>声明

声明是名称值对，代表已通过身份验证的用户的属性。 例如，可以将用户的员工编号存储为声明。 该声明随后可用作授权策略的一部分。 可以创建一个名为“EmployeeOnly”的策略，该策略要求存在名为“EmployeeNumber”的声明，如下所示：

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

此策略随后可与 \[Authorize\] 属性一起用于保护任何控制器和/或操作，如上所述。

#### <a name="securing-web-apis"></a>保护 Web API

大多数 Web API 应实现基于令牌的身份验证系统。 令牌身份验证无状态，且可缩放。 在基于令牌的身份验证系统中，客户端必须首先使用身份验证提供程序进行身份验证。 如果成功，则向该客户端颁发一个令牌，该令牌即是字符经过加密的有意义的字符串。 然后当客户端需要向 API 发出请求时，会将此令牌添加为请求的标题。 继而，服务器会在完成请求之前验证请求标头中的令牌。 图 7-4 展示了此过程。

![TokenAuth](./media/image7-4.png)

**图 7-4.** Web API 基于令牌的身份验证。

> ### <a name="references--security"></a>参考 - 安全
> - **安全性文档概述**  
> https://docs.microsoft.com/aspnet/core/security/
> - **在 ASP.NET Core 应用中强制实施 SSL**  
> <https://docs.microsoft.com/aspnet/core/security/enforcing-ssl>
> - **标识简介**  
> <https://docs.microsoft.com/aspnet/core/security/authentication/identity>
> - **授权简介**  
> <https://docs.microsoft.com/aspnet/core/security/authorization/introduction>
> - **Azure 应用服务中 API 应用的身份验证和授权**  
> <https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication>

## <a name="client-communication"></a>客户端通信

除了通过 Web API 提供页面和响应数据请求之外，ASP.NET Core 应用还能与已连接的客户端直接通信。 这种出站通信可以使用多种传输技术，其中最常见的是 WebSocket。 ASP.NET Core SignalR 是一个库，它简化了应用程序的某种实时服务器到客户端通信功能。 SignalR 支持多种传输技术，包括 WebSocket，并从开发人员处抽象出许多实现细节。

ASP.NET Core SignalR 目前正在开发中，将在下一版本的 ASP.NET Core 中提供。 但是，目前已有其他一些[开源 WebSocket 库](https://github.com/radu-matei/websocket-manager)可供使用。

无论是直接使用 WebSocket 还是使用其他技术，实时客户端通信在许多应用程序方案中都很有用。 一些示例包括：

-   实时聊天室应用程序

-   监视应用程序

-   作业进度更新

-   通知

-   交互式窗体应用程序

在应用程序中构建客户端通信时，通常有两个组件：

-   服务器端连接管理器（SignalR Hub、WebSocketManager WebSocketHandler）

-   客户端库

客户端不限于浏览器 - 移动应用、控制台应用和其他本地应用也可以使用 SignalR/WebSocket 进行通信。 下面的简单程序是 WebSocketManager 示例应用程序的一部分，它向控制台回显发送给聊天应用程序的所有内容：

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

请思考应用程序可通过哪些方式与客户端应用程序直接通信，以及实时通信是否会改善应用的用户体验。

> ### <a name="references--client-communication"></a>参考 - 客户端通信
> - **ASP.NET Core SignalR**  
> <https://github.com/aspnet/SignalR>
> - **WebSocket 管理器**  
> https://github.com/radu-matei/websocket-manager

## <a name="domain-driven-design--should-you-apply-it"></a>域驱动的设计 - 是否该使用？

域驱动设计 (DDD) 是一种敏捷方法，用于构建强调注重企业域的软件。 它非常注重与企业领域专家的沟通和互动，这些专家可以告知开发人员实际系统如何工作。 例如，如果你在构建处理股票交易的系统，那么域专家可能是一位经验丰富的股票经纪人。 DDD 旨在解决大型复杂的企业问题，通常不适合较小型较简单的应用程序，因为在理解域和为域建模上的投入并不值得。

采用 DDD 方法构建软件时，团队（包括非技术型利益干系人和参与者）应为问题空间开发一种通用语言。 即，要进行建模的实际概念、软件同义词以及可能存在以维持该概念的任何结构（例如数据库表）应使用相同的术语。 因此，通用语言中所述的概念应该形成域模型的基础。

组成域模型的对象彼此交互，以表现系统行为。 这些对象可分为以下几类：

-   [实体](http://deviq.com/entity/)，表示具有一系列标识的对象。 实体通常使用键永久存储，并且之后可使用该键进行检索。

-   [聚合](http://deviq.com/aggregate-pattern/)，表示应作为单元保留的一组对象。

-   [值对象](http://deviq.com/value-object/)，表示可以根据其属性值的总和进行比较的概念。 例如，包含开始日期和结束日期的 DateRange。

-   [域事件](https://martinfowler.com/eaaDev/DomainEvent.html)，表示系统中发生的与系统其他部分相关的事件。

请注意，DDD 域模型应封装模型中的复杂行为。 尤其是实体，它不应该仅仅是属性的集合。 域模型缺少行为，并且仅表示系统状态时，就是所谓的[贫乏性模型](http://deviq.com/anemic-model/)，DDD 中应避免此类模型。

除这些模型类型之外，DDD 通常还采用多种模式：

-   [存储库](http://deviq.com/repository-pattern/)，用于提取持久保留详细信息。

-   [工厂](https://en.wikipedia.org/wiki/Factory_method_pattern)，用于封装复杂对象创建。

-   域事件，用于从触发行为中分离依赖性行为。

-   [服务](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/)，用于封装复杂行为和/或基础结构实现详细信息。

-   [命令](https://en.wikipedia.org/wiki/Command_pattern)，用于分离发出的命令并执行命令本身。

-   [规范](http://deviq.com/specification-pattern/)，用于封装查询详细信息。

DDD 还建议使用之前介绍过的干净体系结构，以实现松散耦合、封装和使用单元测试即可轻松验证的代码。

### <a name="when-should-you-apply-ddd"></a>该何时使用 DDD

DDD 非常适合业务（不仅仅是技术）非常复杂的大型应用程序。 这种应用程序需要域专家的知识。 域模型本身应包括有某种意义的行为，表示业务规则和交互，而不仅仅是存储和检索数据存储中各种记录的当前状态。

### <a name="when-shouldnt-you-apply-ddd"></a>何时不该使用 DDD

DDD 需要在建模、体系结构和通信方面进行投资，这对于较小型的应用程序或本质只是 CRUD（创建/读取/更新/删除）的应用程序来说可能并不值得。 如果选择采用 DDD 处理应用程序，但发现域中有一个没有任何行为的贫乏性模型，则可能需要重新考虑处理方法。 可能是该应用程序不需要 DDD，也可能是你需要别人帮助你重构应用程序，将业务逻辑封装在域模型中，而不是数据库或用户界面中。

可以使用混合方法，只对应用程序中的事务性区域或比较复杂的区域使用 DDD，而不对应用程序中比较简单的 CRUD 或只读部分使用 DDD。 例如，如果是为显示报表或将仪表板数据可视化而查询数据，则无需具有聚合约束。 使用单独的、更简单的读取模型处理这类要求是完全可以接受的。

> ### <a name="references--domain-driven-design"></a>参考 - 域驱动设计
> - **简明 DDD（StackOverflow 答案）**  
> <https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488>

## <a name="deployment"></a>部署

无论在哪里托管 ASP.NET Core 应用，部署过程都包含以下几个步骤。 第一步，发布应用程序，可以使用 dotnet 发布 CLI 命令来完成。 此操作将编译应用程序，并将运行应用程序所需的所有文件放到指定的文件夹中。 从 Visual Studio 部署时，系统将自动执行此步骤。 发布文件夹中包含应用程序的 .exe 和 .dll 文件及其依赖项。 自包含应用程序中还包含一个 .NET 运行时版本。 ASP.NET Core 应用程序还将包含配置文件、静态客户端资产和 MVC 视图。

ASP.NET Core 应用程序是控制台应用程序，服务器启动时必须启动，应用程序（或服务器）崩溃时必须重新启动。 可以使用流程管理器自动执行此过程。 适用于 ASP.NET Core 的最常见的进程管理器是 Linux 上的 Nginx 和 Apache，以及 Windows 上的 IIS 或 Windows Service。

除流程管理器之外，Kestrel Web 服务器中托管的 ASP.NET Core 应用程序还必须使用反向代理服务器。 反向代理服务器接收到来自 Internet 的 HTTP 请求，并在进行一些初步处理后将这些请求转发到 Kestrel。 反向代理服务器为应用程序提供一个安全层，并且是边缘部署的必需条件（向来自 Internet 的流量公开）。 Kestrel 相对较新，尚未提供对某些攻击的抵御功能。 Kestrel 也不支持在同一端口上承载多个应用程序，因此不能将其用于主机头之类的技术以实现在同一端口和 IP 地址上承载多个应用程序。

![Kestrel 到 Internet](./media/image7-5.png)

图 7-5 反向代理服务器背后托管在 Kestrel 中的 ASP.NET

反向代理发挥作用的其他情况包括使用 SSL/HTTPS 保护多个应用程序。 在这种情况下，只需要为反向代理服务器配置 SSL。 反向代理服务器和 Kestrel 之间的通信可以通过 HTTP 进行，如图 7-6 所示。

![](./media/image7-6.png)

图 7-6 HTTPS 保护的反向代理服务器后托管的 ASP.NET

可以将 ASP.NET Core 应用程序托管在 Docker 容器中，然后该应用程序即可本地托管或部署到 Azure 进行基于云的托管，这种方法正日益普及。 Docker 容器可以包含应用程序代码（在 Kestrel 上运行），并部署在反向代理服务器后，如上所述。

如果在 Azure 上托管应用程序，则可以使用 Microsoft Azure 应用程序网关作为专用虚拟设备来提供多项服务。 除了充当单个应用程序的反向代理之外，应用程序网关还可以提供以下功能：

-   HTTP 负载均衡

-   SSL 卸载（仅到 Internet 的 SSL）

-   端到端 SSL

-   多站点路由（在单个应用程序网关上整合最多 20 个站点）

-   Web 应用程序防火墙

-   Websocket 支持

-   高级诊断

请在第 10 章中了解有关 Azure 部署选项的详细信息。

> ### <a name="references--deployment"></a>参考 - 部署
> - **托管和部署概述**  
> <https://docs.microsoft.com/aspnet/core/publishing/>
> - **何时结合使用 Kestrel 和反向代理**  
> <https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy>
> - **在 Docker 容器中托管 ASP.NET Core 应用**  
> <https://docs.microsoft.com/aspnet/core/publishing/docker>
> - **应用程序网关简介**  
> <https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction>

>[!div class="step-by-step"]
[上一篇] (common-client-side-web-technologies.md) [下一篇] (work-with-data-in-asp-net-core-apps.md)
