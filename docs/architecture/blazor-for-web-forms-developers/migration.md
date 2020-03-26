---
title: 从ASP.NET Web 窗体迁移到布拉佐尔
description: 了解如何处理将现有ASP.NET Web 窗体应用迁移到 Blazor 的方法。
author: twsouthwick
ms.author: tasou
ms.date: 09/19/2019
ms.openlocfilehash: 0a10a9a3d5ab32e16cb59a68da57116e20c53e49
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134092"
---
# <a name="migrate-from-aspnet-web-forms-to-blazor"></a><span data-ttu-id="fcde8-103">从ASP.NET Web 窗体迁移到布拉佐尔</span><span class="sxs-lookup"><span data-stu-id="fcde8-103">Migrate from ASP.NET Web Forms to Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="fcde8-104">将代码库从ASP.NET Web 窗体迁移到 Blazor 是一项耗时的任务，需要规划。</span><span class="sxs-lookup"><span data-stu-id="fcde8-104">Migrating a code base from ASP.NET Web Forms to Blazor is a time-consuming task that requires planning.</span></span> <span data-ttu-id="fcde8-105">本章概述了该过程。</span><span class="sxs-lookup"><span data-stu-id="fcde8-105">This chapter outlines the process.</span></span> <span data-ttu-id="fcde8-106">可以简化转换的是确保应用遵循*N 层*体系结构，其中应用模型（在本例中为 Web 窗体）与业务逻辑分开。</span><span class="sxs-lookup"><span data-stu-id="fcde8-106">Something that can ease the transition is to ensure the app adheres to an *N-tier* architecture, wherein the app model (in this case, Web Forms) is separate from the business logic.</span></span> <span data-ttu-id="fcde8-107">这种层的逻辑分离可以清楚地说明需要迁移到 .NET Core 和 Blazor 的内容。</span><span class="sxs-lookup"><span data-stu-id="fcde8-107">This logical separation of layers makes it clear what needs to move to .NET Core and Blazor.</span></span>

<span data-ttu-id="fcde8-108">在此示例中，使用[GitHub](https://github.com/dotnet-architecture/eShopOnBlazor)上可用的 eShop 应用。</span><span class="sxs-lookup"><span data-stu-id="fcde8-108">For this example, the eShop app available on [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) is used.</span></span> <span data-ttu-id="fcde8-109">eShop 是一种目录服务，通过表单输入和验证提供 CRUD 功能。</span><span class="sxs-lookup"><span data-stu-id="fcde8-109">eShop is a catalog service that provides CRUD capabilities via form entry and validation.</span></span>

<span data-ttu-id="fcde8-110">为什么工作应用应迁移到 Blazor？</span><span class="sxs-lookup"><span data-stu-id="fcde8-110">Why should a working app be migrated to Blazor?</span></span> <span data-ttu-id="fcde8-111">很多时候，没有必要。</span><span class="sxs-lookup"><span data-stu-id="fcde8-111">Many times, there's no need.</span></span> <span data-ttu-id="fcde8-112">ASP.NET Web 表单将继续支持多年。</span><span class="sxs-lookup"><span data-stu-id="fcde8-112">ASP.NET Web Forms will continue to be supported for many years.</span></span> <span data-ttu-id="fcde8-113">但是，Blazor 提供的许多功能仅在迁移的应用上受支持。</span><span class="sxs-lookup"><span data-stu-id="fcde8-113">However, many of the features that Blazor provides are only supported on a migrated app.</span></span> <span data-ttu-id="fcde8-114">这些功能包括：</span><span class="sxs-lookup"><span data-stu-id="fcde8-114">Such features include:</span></span>

- <span data-ttu-id="fcde8-115">框架中的性能改进，例如`Span<T>`</span><span class="sxs-lookup"><span data-stu-id="fcde8-115">Performance improvements in the framework such as `Span<T>`</span></span>
- <span data-ttu-id="fcde8-116">能够以 Web 程序集身份运行</span><span class="sxs-lookup"><span data-stu-id="fcde8-116">Ability to run as WebAssembly</span></span>
- <span data-ttu-id="fcde8-117">对 Linux 和 macOS 的跨平台支持</span><span class="sxs-lookup"><span data-stu-id="fcde8-117">Cross-platform support for Linux and macOS</span></span>
- <span data-ttu-id="fcde8-118">应用本地部署或共享框架部署，不影响其他应用</span><span class="sxs-lookup"><span data-stu-id="fcde8-118">App-local deployment or shared framework deployment without impacting other apps</span></span>

<span data-ttu-id="fcde8-119">如果这些或其他新功能足够吸引人，则迁移应用可能具有价值。</span><span class="sxs-lookup"><span data-stu-id="fcde8-119">If these or other new features are compelling enough, there may be value in migrating the app.</span></span> <span data-ttu-id="fcde8-120">迁移可以采用不同的形状;它可以是整个应用，也可以只是需要更改的某些终结点。</span><span class="sxs-lookup"><span data-stu-id="fcde8-120">The migration can take different shapes; it can be the entire app, or only certain endpoints that require the changes.</span></span> <span data-ttu-id="fcde8-121">迁移的决定最终基于开发人员要解决的业务问题。</span><span class="sxs-lookup"><span data-stu-id="fcde8-121">The decision to migrate is ultimately based on the business problems to be solved by the developer.</span></span>

## <a name="server-side-versus-client-side-hosting"></a><span data-ttu-id="fcde8-122">服务器端与客户端托管</span><span class="sxs-lookup"><span data-stu-id="fcde8-122">Server-side versus client-side hosting</span></span>

<span data-ttu-id="fcde8-123">如[托管模型](hosting-models.md)章节所述，Blazor 应用可以通过两种不同的方式托管：服务器端和客户端。</span><span class="sxs-lookup"><span data-stu-id="fcde8-123">As described in the [hosting models](hosting-models.md) chapter, a Blazor app can be hosted in two different ways: server-side and client-side.</span></span> <span data-ttu-id="fcde8-124">服务器端模型使用ASP.NET核心信号R连接来管理 DOM 更新，同时在服务器上运行任何实际代码。</span><span class="sxs-lookup"><span data-stu-id="fcde8-124">The server-side model uses ASP.NET Core SignalR connections to manage the DOM updates while running any actual code on the server.</span></span> <span data-ttu-id="fcde8-125">客户端模型在浏览器中作为 WebAssembly 运行，不需要服务器连接。</span><span class="sxs-lookup"><span data-stu-id="fcde8-125">The client-side model runs as WebAssembly within a browser and requires no server connections.</span></span> <span data-ttu-id="fcde8-126">有许多差异可能会影响特定应用：</span><span class="sxs-lookup"><span data-stu-id="fcde8-126">There are a number of differences that may affect which is best for a specific app:</span></span>

- <span data-ttu-id="fcde8-127">以 WebAssembly 身份运行仍处于开发阶段，当前可能不支持所有功能（如线程处理）</span><span class="sxs-lookup"><span data-stu-id="fcde8-127">Running as WebAssembly is still in development and may not support all features (such as threading) at the current time</span></span>
- <span data-ttu-id="fcde8-128">客户端和服务器之间的聊天通信可能会导致服务器端模式下的延迟问题</span><span class="sxs-lookup"><span data-stu-id="fcde8-128">Chatty communication between the client and server may cause latency issues in server-side mode</span></span>
- <span data-ttu-id="fcde8-129">访问数据库和内部或受保护服务需要使用客户端托管提供单独的服务</span><span class="sxs-lookup"><span data-stu-id="fcde8-129">Access to databases and internal or protected services require a separate service with client-side hosting</span></span>

<span data-ttu-id="fcde8-130">在编写本文时，服务器端模型更像 Web 窗体。</span><span class="sxs-lookup"><span data-stu-id="fcde8-130">At the time of writing, the server-side model more closely resembles Web Forms.</span></span> <span data-ttu-id="fcde8-131">本章的大部分重点介绍服务器端托管模型，因为它已做好生产准备。</span><span class="sxs-lookup"><span data-stu-id="fcde8-131">Most of this chapter focuses on the server-side hosting model, as it's production-ready.</span></span>

## <a name="create-a-new-project"></a><span data-ttu-id="fcde8-132">创建新项目</span><span class="sxs-lookup"><span data-stu-id="fcde8-132">Create a new project</span></span>

<span data-ttu-id="fcde8-133">此初始迁移步骤是创建新项目。</span><span class="sxs-lookup"><span data-stu-id="fcde8-133">This initial migration step is to create a new project.</span></span> <span data-ttu-id="fcde8-134">此项目类型基于 .NET Core 的 SDK 样式项目，并简化了以前项目格式中使用的许多样板。</span><span class="sxs-lookup"><span data-stu-id="fcde8-134">This project type is based on the SDK style projects of .NET Core and simplifies much of the boilerplate that was used in previous project formats.</span></span> <span data-ttu-id="fcde8-135">有关详细信息，请参阅有关[项目结构](project-structure.md)的章节。</span><span class="sxs-lookup"><span data-stu-id="fcde8-135">For more detail, please see the chapter on [Project Structure](project-structure.md).</span></span>

<span data-ttu-id="fcde8-136">创建项目后，安装上一个项目中使用的库。</span><span class="sxs-lookup"><span data-stu-id="fcde8-136">Once the project has been created, install the libraries that were used in the previous project.</span></span> <span data-ttu-id="fcde8-137">在较旧的 Web 窗体项目中，您可能已使用*包.config*文件列出所需的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="fcde8-137">In older Web Forms projects, you may have used the *packages.config* file to list the required NuGet packages.</span></span> <span data-ttu-id="fcde8-138">在新的 SDK 样式项目中，*包.config*已替换为`<PackageReference>`项目文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="fcde8-138">In the new SDK-style project, *packages.config* has been replaced with `<PackageReference>` elements in the project file.</span></span> <span data-ttu-id="fcde8-139">此方法的一个好处是，所有依赖项都是以过渡方式安装的。</span><span class="sxs-lookup"><span data-stu-id="fcde8-139">A benefit to this approach is that all dependencies are installed transitively.</span></span> <span data-ttu-id="fcde8-140">您只列出您关心的顶级依赖项。</span><span class="sxs-lookup"><span data-stu-id="fcde8-140">You only list the top-level dependencies you care about.</span></span>

<span data-ttu-id="fcde8-141">您正在使用的许多依赖项可用于 .NET Core，包括实体框架 6 和 log4net。</span><span class="sxs-lookup"><span data-stu-id="fcde8-141">Many of the dependencies you're using are available for .NET Core, including Entity Framework 6 and log4net.</span></span> <span data-ttu-id="fcde8-142">如果没有可用的 .NET Core 或 .NET 标准版本，则经常使用 .NET 框架版本。</span><span class="sxs-lookup"><span data-stu-id="fcde8-142">If there's no .NET Core or .NET Standard version available, the .NET Framework version can often be used.</span></span> <span data-ttu-id="fcde8-143">您的里程可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="fcde8-143">Your mileage may vary.</span></span> <span data-ttu-id="fcde8-144">.NET Core 中不可用的任何 API 都会导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="fcde8-144">Any API used that isn't available in .NET Core causes a runtime error.</span></span> <span data-ttu-id="fcde8-145">Visual Studio 会通知您此类套餐。</span><span class="sxs-lookup"><span data-stu-id="fcde8-145">Visual Studio notifies you of such packages.</span></span> <span data-ttu-id="fcde8-146">在**解决方案资源管理器**中的项目的**参考节点**上会出现一个黄色图标。</span><span class="sxs-lookup"><span data-stu-id="fcde8-146">A yellow icon appears on the project's **References** node in **Solution Explorer**.</span></span>

<span data-ttu-id="fcde8-147">在基于 Blazor 的 eShop 项目中，您可以看到已安装的软件包。</span><span class="sxs-lookup"><span data-stu-id="fcde8-147">In the Blazor-based eShop project, you can see the packages that are installed.</span></span> <span data-ttu-id="fcde8-148">以前 *，package.config*文件列出了项目中使用的每个包，导致文件近 50 行长。</span><span class="sxs-lookup"><span data-stu-id="fcde8-148">Previously, the *packages.config* file listed every package used in the project, resulting in a file almost 50 lines long.</span></span> <span data-ttu-id="fcde8-149">*包段. 配置*是：</span><span class="sxs-lookup"><span data-stu-id="fcde8-149">A snippet of *packages.config* is:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<packages>
  ...
  <package id="Microsoft.ApplicationInsights.Agent.Intercept" version="2.4.0" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.DependencyCollector" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.PerfCounterCollector" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.Web" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.WindowsServer" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.WindowsServer.TelemetryChannel" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.AspNet.FriendlyUrls" version="1.0.2" targetFramework="net472" />
  <package id="Microsoft.AspNet.FriendlyUrls.Core" version="1.0.2" targetFramework="net472" />
  <package id="Microsoft.AspNet.ScriptManager.MSAjax" version="5.0.0" targetFramework="net472" />
  <package id="Microsoft.AspNet.ScriptManager.WebForms" version="5.0.0" targetFramework="net472" />
  ...
  <package id="System.Memory" version="4.5.1" targetFramework="net472" />
  <package id="System.Numerics.Vectors" version="4.4.0" targetFramework="net472" />
  <package id="System.Runtime.CompilerServices.Unsafe" version="4.5.0" targetFramework="net472" />
  <package id="System.Threading.Channels" version="4.5.0" targetFramework="net472" />
  <package id="System.Threading.Tasks.Extensions" version="4.5.1" targetFramework="net472" />
  <package id="WebGrease" version="1.6.0" targetFramework="net472" />
</packages>
```

<span data-ttu-id="fcde8-150">该`<packages>`元素包括所有必要的依赖项。</span><span class="sxs-lookup"><span data-stu-id="fcde8-150">The `<packages>` element includes all necessary dependencies.</span></span> <span data-ttu-id="fcde8-151">很难确定其中哪些包包含，因为您需要它们。</span><span class="sxs-lookup"><span data-stu-id="fcde8-151">It's difficult to identify which of these packages are included because you require them.</span></span> <span data-ttu-id="fcde8-152">某些`<package>`元素的列出只是为了满足您需要的依赖项的需求。</span><span class="sxs-lookup"><span data-stu-id="fcde8-152">Some `<package>` elements are listed simply to satisfy the needs of dependencies you require.</span></span>

<span data-ttu-id="fcde8-153">Blazor 项目列出了项目文件中`<ItemGroup>`的元素中所需的依赖项：</span><span class="sxs-lookup"><span data-stu-id="fcde8-153">The Blazor project lists the dependencies you require within an `<ItemGroup>` element in the project file:</span></span>

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

<span data-ttu-id="fcde8-154">一个NuGet包，简化了Web表单开发人员的生活是[Windows兼容性包](../../core/porting/windows-compat-pack.md)。</span><span class="sxs-lookup"><span data-stu-id="fcde8-154">One NuGet package that simplifies the life of Web Forms developers is the [Windows Compatibility Pack](../../core/porting/windows-compat-pack.md).</span></span> <span data-ttu-id="fcde8-155">尽管 .NET Core 是跨平台的，但某些功能仅在 Windows 上可用。</span><span class="sxs-lookup"><span data-stu-id="fcde8-155">Although .NET Core is cross-platform, some features are only available on Windows.</span></span> <span data-ttu-id="fcde8-156">通过安装兼容性包，可以获得特定于 Windows 的功能。</span><span class="sxs-lookup"><span data-stu-id="fcde8-156">Windows-specific features are made available by installing the compatibility pack.</span></span> <span data-ttu-id="fcde8-157">此类功能的示例包括注册表、WMI 和目录服务。</span><span class="sxs-lookup"><span data-stu-id="fcde8-157">Examples of such features include the Registry, WMI, and Directory Services.</span></span> <span data-ttu-id="fcde8-158">该软件包添加了大约 20，000 个 API，并激活了许多您可能已经熟悉的服务。</span><span class="sxs-lookup"><span data-stu-id="fcde8-158">The package adds around 20,000 APIs and activates many services with which you may already be familiar.</span></span> <span data-ttu-id="fcde8-159">eShop 项目不需要兼容性包;因此，eShop 项目不需要兼容性包。但是，如果项目使用特定于 Windows 的功能，则该包可简化迁移工作。</span><span class="sxs-lookup"><span data-stu-id="fcde8-159">The eShop project doesn't require the compatibility pack; but if your projects use Windows-specific features, the package eases the migration efforts.</span></span>

## <a name="enable-startup-process"></a><span data-ttu-id="fcde8-160">启用启动过程</span><span class="sxs-lookup"><span data-stu-id="fcde8-160">Enable startup process</span></span>

<span data-ttu-id="fcde8-161">Blazor 的启动过程从 Web 窗体更改，并遵循其他ASP.NET核心服务的类似设置。</span><span class="sxs-lookup"><span data-stu-id="fcde8-161">The startup process for Blazor has changed from Web Forms and follows a similar setup for other ASP.NET Core services.</span></span> <span data-ttu-id="fcde8-162">当托管服务器端时，Blazor 组件作为正常ASP.NET核心应用的一部分运行。</span><span class="sxs-lookup"><span data-stu-id="fcde8-162">When hosted server-side, Blazor components are run as part of a normal ASP.NET Core app.</span></span> <span data-ttu-id="fcde8-163">当使用 WebAssembly 在浏览器中托管时，Blazor 组件使用类似的托管模型。</span><span class="sxs-lookup"><span data-stu-id="fcde8-163">When hosted in the browser with WebAssembly, Blazor components use a similar hosting model.</span></span> <span data-ttu-id="fcde8-164">区别在于组件作为独立于任何后端进程的服务运行。</span><span class="sxs-lookup"><span data-stu-id="fcde8-164">The difference is the components are run as a separate service from any of the backend processes.</span></span> <span data-ttu-id="fcde8-165">无论哪种方式，启动都是类似的。</span><span class="sxs-lookup"><span data-stu-id="fcde8-165">Either way, the startup is similar.</span></span>

<span data-ttu-id="fcde8-166">*Global.asax.cs*文件是 Web 窗体项目的默认启动页。</span><span class="sxs-lookup"><span data-stu-id="fcde8-166">The *Global.asax.cs* file is the default startup page for Web Forms projects.</span></span> <span data-ttu-id="fcde8-167">在 eShop 项目中，此文件配置"控制反转 （IoC）"容器，并处理应用或请求的各种生命周期事件。</span><span class="sxs-lookup"><span data-stu-id="fcde8-167">In the eShop project, this file configures the Inversion of Control (IoC) container and handles the various lifecycle events of the app or request.</span></span> <span data-ttu-id="fcde8-168">其中一些事件使用中间件（如`Application_BeginRequest`）处理。</span><span class="sxs-lookup"><span data-stu-id="fcde8-168">Some of these events are handled with middleware (such as `Application_BeginRequest`).</span></span> <span data-ttu-id="fcde8-169">其他事件需要通过依赖项注入 （DI） 重写特定服务。</span><span class="sxs-lookup"><span data-stu-id="fcde8-169">Other events require the overriding of specific services via dependency injection (DI).</span></span>

<span data-ttu-id="fcde8-170">例如，eShop *Global.asax.cs*文件包含以下代码：</span><span class="sxs-lookup"><span data-stu-id="fcde8-170">By way of example, the *Global.asax.cs* file for eShop, contains the following code:</span></span>

```csharp
public class Global : HttpApplication, IContainerProviderAccessor
{
    private static readonly ILog _log = LogManager.GetLogger(System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

    static IContainerProvider _containerProvider;
    IContainer container;

    public IContainerProvider ContainerProvider
    {
        get { return _containerProvider; }
    }

    protected void Application_Start(object sender, EventArgs e)
    {
        // Code that runs on app startup
        RouteConfig.RegisterRoutes(RouteTable.Routes);
        BundleConfig.RegisterBundles(BundleTable.Bundles);
        ConfigureContainer();
        ConfigDataBase();
    }

    /// <summary>
    /// Track the machine name and the start time for the session inside the current session
    /// </summary>
    protected void Session_Start(Object sender, EventArgs e)
    {
        HttpContext.Current.Session["MachineName"] = Environment.MachineName;
        HttpContext.Current.Session["SessionStartTime"] = DateTime.Now;
    }

    /// <summary>
    /// http://docs.autofac.org/en/latest/integration/webforms.html
    /// </summary>
    private void ConfigureContainer()
    {
        var builder = new ContainerBuilder();
        var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);
        builder.RegisterModule(new ApplicationModule(mockData));
        container = builder.Build();
        _containerProvider = new ContainerProvider(container);
    }

    private void ConfigDataBase()
    {
        var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);

        if (!mockData)
        {
            Database.SetInitializer<CatalogDBContext>(container.Resolve<CatalogDBInitializer>());
        }
    }

    protected void Application_BeginRequest(object sender, EventArgs e)
    {
        //set the property to our new object
        LogicalThreadContext.Properties["activityid"] = new ActivityIdHelper();

        LogicalThreadContext.Properties["requestinfo"] = new WebRequestInfo();

        _log.Debug("Application_BeginRequest");
    }
}
```

<span data-ttu-id="fcde8-171">前面的文件将成为服务器端`Startup`Blazor 中的类：</span><span class="sxs-lookup"><span data-stu-id="fcde8-171">The preceding file becomes the `Startup` class in server-side Blazor:</span></span>

```csharp
public class Startup
{
    public Startup(IConfiguration configuration, IWebHostEnvironment env)
    {
        Configuration = configuration;
        Env = env;
    }

    public IConfiguration Configuration { get; }

    public IWebHostEnvironment Env { get; }

    // This method gets called by the runtime. Use this method to add services to the container.
    // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddRazorPages();
        services.AddServerSideBlazor();

        if (Configuration.GetValue<bool>("UseMockData"))
        {
            services.AddSingleton<ICatalogService, CatalogServiceMock>();
        }
        else
        {
            services.AddScoped<ICatalogService, CatalogService>();
            services.AddScoped<IDatabaseInitializer<CatalogDBContext>, CatalogDBInitializer>();
            services.AddSingleton<CatalogItemHiLoGenerator>();
            services.AddScoped(_ => new CatalogDBContext(Configuration.GetConnectionString("CatalogDBContext")));
        }
    }

    // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
    public void Configure(IApplicationBuilder app, ILoggerFactory loggerFactory)
    {
        loggerFactory.AddLog4Net("log4Net.xml");

        if (Env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
        else
        {
            app.UseExceptionHandler("/Home/Error");
        }

        // Middleware for Application_BeginRequest
        app.Use((ctx, next) =>
        {
            LogicalThreadContext.Properties["activityid"] = new ActivityIdHelper(ctx);
            LogicalThreadContext.Properties["requestinfo"] = new WebRequestInfo(ctx);
            return next();
        });

        app.UseStaticFiles();

        app.UseRouting();

        app.UseEndpoints(endpoints =>
        {
            endpoints.MapBlazorHub();
            endpoints.MapFallbackToPage("/_Host");
        });

        ConfigDataBase(app);
    }

    private void ConfigDataBase(IApplicationBuilder app)
    {
        using (var scope = app.ApplicationServices.CreateScope())
        {
            var initializer = scope.ServiceProvider.GetService<IDatabaseInitializer<CatalogDBContext>>();

            if (initializer != null)
            {
                Database.SetInitializer(initializer);
            }
        }
    }
}
```

<span data-ttu-id="fcde8-172">您可能会从 Web 窗体中注意到的一个重要变化是 DI 的突出性。</span><span class="sxs-lookup"><span data-stu-id="fcde8-172">One significant change you may notice from Web Forms is the prominence of DI.</span></span> <span data-ttu-id="fcde8-173">DI 一直是 ASP.NET核心设计的指导原则。</span><span class="sxs-lookup"><span data-stu-id="fcde8-173">DI has been a guiding principle in the ASP.NET Core design.</span></span> <span data-ttu-id="fcde8-174">它支持自定义ASP.NET核心框架的几乎所有方面。</span><span class="sxs-lookup"><span data-stu-id="fcde8-174">It supports customization of almost all aspects of the ASP.NET Core framework.</span></span> <span data-ttu-id="fcde8-175">甚至还有一个内置的服务提供商，可用于许多方案。</span><span class="sxs-lookup"><span data-stu-id="fcde8-175">There's even a built-in service provider that can be used for many scenarios.</span></span> <span data-ttu-id="fcde8-176">如果需要更多自定义，许多社区项目可以支持它。</span><span class="sxs-lookup"><span data-stu-id="fcde8-176">If more customization is required, it can be supported by the many community projects.</span></span> <span data-ttu-id="fcde8-177">例如，您可以进行第三方 DI 库投资。</span><span class="sxs-lookup"><span data-stu-id="fcde8-177">For example, you can carry forward your third-party DI library investment.</span></span>

<span data-ttu-id="fcde8-178">在原始的 eShop 应用中，有一些用于会话管理的配置。</span><span class="sxs-lookup"><span data-stu-id="fcde8-178">In the original eShop app, there's some configuration for session management.</span></span> <span data-ttu-id="fcde8-179">由于服务器端 Blazor 使用ASP.NET核心信号R进行通信，因此不支持会话状态，因为连接可能独立于 HTTP 上下文进行。</span><span class="sxs-lookup"><span data-stu-id="fcde8-179">Since server-side Blazor uses ASP.NET Core SignalR for communication, session state isn't supported as the connections may occur independent of an HTTP context.</span></span> <span data-ttu-id="fcde8-180">使用会话状态的应用需要在作为 Blazor 应用运行之前重新构建。</span><span class="sxs-lookup"><span data-stu-id="fcde8-180">An app that uses session state requires rearchitecting before running as a Blazor app.</span></span>

<span data-ttu-id="fcde8-181">有关应用启动的详细信息，请参阅[应用启动](app-startup.md)。</span><span class="sxs-lookup"><span data-stu-id="fcde8-181">For more information about app startup, see [App startup](app-startup.md).</span></span>

## <a name="migrate-http-modules-and-handlers-to-middleware"></a><span data-ttu-id="fcde8-182">将 HTTP 模块和处理程序迁移到中间件</span><span class="sxs-lookup"><span data-stu-id="fcde8-182">Migrate HTTP modules and handlers to middleware</span></span>

<span data-ttu-id="fcde8-183">HTTP 模块和处理程序是 Web 窗体中用于控制 HTTP 请求管道的常见模式。</span><span class="sxs-lookup"><span data-stu-id="fcde8-183">HTTP modules and handlers are common patterns in Web Forms to control the HTTP request pipeline.</span></span> <span data-ttu-id="fcde8-184">实现`IHttpModule`或`IHttpHandler`可以注册和处理传入请求的类。</span><span class="sxs-lookup"><span data-stu-id="fcde8-184">Classes that implement `IHttpModule` or `IHttpHandler` could be registered and process incoming requests.</span></span> <span data-ttu-id="fcde8-185">Web 窗体在*Web.config 文件中*配置模块和处理程序。</span><span class="sxs-lookup"><span data-stu-id="fcde8-185">Web Forms configures modules and handlers in the *web.config* file.</span></span> <span data-ttu-id="fcde8-186">Web 窗体还在很大程度上基于应用生命周期事件处理。</span><span class="sxs-lookup"><span data-stu-id="fcde8-186">Web Forms is also heavily based on app lifecycle event handling.</span></span> <span data-ttu-id="fcde8-187">ASP.NET核心使用中间件代替。</span><span class="sxs-lookup"><span data-stu-id="fcde8-187">ASP.NET Core uses middleware instead.</span></span> <span data-ttu-id="fcde8-188">中间件在`Configure``Startup`类的方法中注册。</span><span class="sxs-lookup"><span data-stu-id="fcde8-188">Middleware is registered in the `Configure` method of the `Startup` class.</span></span> <span data-ttu-id="fcde8-189">中间件执行顺序由注册订单确定。</span><span class="sxs-lookup"><span data-stu-id="fcde8-189">Middleware execution order is determined by the registration order.</span></span>

<span data-ttu-id="fcde8-190">在[启用启动过程](#enable-startup-process)部分中，Web 窗体提出了生命周期事件作为`Application_BeginRequest`方法。</span><span class="sxs-lookup"><span data-stu-id="fcde8-190">In the [Enable startup process](#enable-startup-process) section, a lifecycle event was raised by Web Forms as the `Application_BeginRequest` method.</span></span> <span data-ttu-id="fcde8-191">此事件在 ASP.NET 酷中不可用。</span><span class="sxs-lookup"><span data-stu-id="fcde8-191">This event isn't available in ASP.NET Core.</span></span> <span data-ttu-id="fcde8-192">实现此行为的一个方法是实现中间件，如*Startup.cs*文件示例中所示。</span><span class="sxs-lookup"><span data-stu-id="fcde8-192">One way to achieve this behavior is to implement middleware as seen in the *Startup.cs* file example.</span></span> <span data-ttu-id="fcde8-193">此中间件执行相同的逻辑，然后将控制权传输到中间件管道中的下一个处理程序。</span><span class="sxs-lookup"><span data-stu-id="fcde8-193">This middleware does the same logic and then transfers control to the next handler in the middleware pipeline.</span></span>

<span data-ttu-id="fcde8-194">有关迁移模块和处理程序的详细信息，请参阅将 HTTP[处理程序和模块迁移到ASP.NET核心中间件](/aspnet/core/migration/http-modules)。</span><span class="sxs-lookup"><span data-stu-id="fcde8-194">For more information on migrating modules and handlers, see [Migrate HTTP handlers and modules to ASP.NET Core middleware](/aspnet/core/migration/http-modules).</span></span>

## <a name="migrate-static-files"></a><span data-ttu-id="fcde8-195">迁移静态文件</span><span class="sxs-lookup"><span data-stu-id="fcde8-195">Migrate static files</span></span>

<span data-ttu-id="fcde8-196">要提供静态文件（例如，HTML、CSS、图像和 JavaScript），必须通过中间件公开这些文件。</span><span class="sxs-lookup"><span data-stu-id="fcde8-196">To serve static files (for example, HTML, CSS, images, and JavaScript), the files must be exposed by middleware.</span></span> <span data-ttu-id="fcde8-197">调用`UseStaticFiles`该方法可以从 Web 根路径提供静态文件。</span><span class="sxs-lookup"><span data-stu-id="fcde8-197">Calling the `UseStaticFiles` method enables the serving of static files from the web root path.</span></span> <span data-ttu-id="fcde8-198">默认 Web 根目录是*wwwroot，* 但可以自定义。</span><span class="sxs-lookup"><span data-stu-id="fcde8-198">The default web root directory is *wwwroot*, but it can be customized.</span></span> <span data-ttu-id="fcde8-199">如 eShop `Configure` `Startup`类的方法中包含的：</span><span class="sxs-lookup"><span data-stu-id="fcde8-199">As included in the `Configure` method of eShop's `Startup` class:</span></span>

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

<span data-ttu-id="fcde8-200">eShop 项目支持基本的静态文件访问。</span><span class="sxs-lookup"><span data-stu-id="fcde8-200">The eShop project enables basic static file access.</span></span> <span data-ttu-id="fcde8-201">有许多自定义可用于静态文件访问。</span><span class="sxs-lookup"><span data-stu-id="fcde8-201">There are many customizations available for static file access.</span></span> <span data-ttu-id="fcde8-202">有关启用默认文件或文件浏览器的信息，请参阅[ASP.NET 酷睿 中的静态文件](/aspnet/core/fundamentals/static-files)。</span><span class="sxs-lookup"><span data-stu-id="fcde8-202">For information on enabling default files or a file browser, see [Static files in ASP.NET Core](/aspnet/core/fundamentals/static-files).</span></span>

## <a name="migrate-runtime-bundling-and-minification-setup"></a><span data-ttu-id="fcde8-203">迁移运行时捆绑和最小化设置</span><span class="sxs-lookup"><span data-stu-id="fcde8-203">Migrate runtime bundling and minification setup</span></span>

<span data-ttu-id="fcde8-204">捆绑和分量化是性能优化技术，用于减少检索某些文件类型的服务器请求的数量和大小。</span><span class="sxs-lookup"><span data-stu-id="fcde8-204">Bundling and minification are performance optimization techniques for reducing the number and size of server requests to retrieve certain file types.</span></span> <span data-ttu-id="fcde8-205">在发送到客户端之前，JavaScript 和 CSS 通常会经历某种形式的捆绑或小化。</span><span class="sxs-lookup"><span data-stu-id="fcde8-205">JavaScript and CSS often undergo some form of bundling or minification before being sent to the client.</span></span> <span data-ttu-id="fcde8-206">在 web 窗体ASP.NET，这些优化在运行时处理。</span><span class="sxs-lookup"><span data-stu-id="fcde8-206">In ASP.NET Web Forms, these optimizations are handled at runtime.</span></span> <span data-ttu-id="fcde8-207">优化约定定义为*App_Start/BundleConfig.cs*文件。</span><span class="sxs-lookup"><span data-stu-id="fcde8-207">The optimization conventions are defined an *App_Start/BundleConfig.cs* file.</span></span> <span data-ttu-id="fcde8-208">在ASP.NET核心中，采用了一种更具声明性的方法。</span><span class="sxs-lookup"><span data-stu-id="fcde8-208">In ASP.NET Core, a more declarative approach is adopted.</span></span> <span data-ttu-id="fcde8-209">文件列出了要进行挖掘的文件以及特定的小化设置。</span><span class="sxs-lookup"><span data-stu-id="fcde8-209">A file lists the files to be minified, along with specific minification settings.</span></span>

<span data-ttu-id="fcde8-210">有关捆绑和最小化的详细信息，请参阅 ASP.NET[酷中捆绑和小化静态资产](/aspnet/core/client-side/bundling-and-minification)。</span><span class="sxs-lookup"><span data-stu-id="fcde8-210">For more information on bundling and minification, see [Bundle and minify static assets in ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).</span></span>

## <a name="migrate-aspx-pages"></a><span data-ttu-id="fcde8-211">迁移 ASPX 页面</span><span class="sxs-lookup"><span data-stu-id="fcde8-211">Migrate ASPX pages</span></span>

<span data-ttu-id="fcde8-212">Web 窗体应用中的页面是具有 *.aspx*扩展名的文件。</span><span class="sxs-lookup"><span data-stu-id="fcde8-212">A page in a Web Forms app is a file with the *.aspx* extension.</span></span> <span data-ttu-id="fcde8-213">Web 窗体页通常可以映射到 Blazor 中的组件。</span><span class="sxs-lookup"><span data-stu-id="fcde8-213">A Web Forms page can often be mapped to a component in Blazor.</span></span> <span data-ttu-id="fcde8-214">Blazor 组件创作在具有 *.razor*扩展名的文件中。</span><span class="sxs-lookup"><span data-stu-id="fcde8-214">A Blazor component is authored in a file with the *.razor* extension.</span></span> <span data-ttu-id="fcde8-215">对于 eShop 项目，五个页面将转换为 Razor 页面。</span><span class="sxs-lookup"><span data-stu-id="fcde8-215">For the eShop project, five pages are converted to a Razor page.</span></span>

<span data-ttu-id="fcde8-216">例如，详细信息视图由 Web 窗体项目中的三个文件组成：*详细信息.aspx、Details.aspx.cs\*\*Details.aspx.cs*和*Details.aspx.designer.cs*。</span><span class="sxs-lookup"><span data-stu-id="fcde8-216">For example, the details view is comprised of three files in the Web Forms project: *Details.aspx*, *Details.aspx.cs*, and *Details.aspx.designer.cs*.</span></span> <span data-ttu-id="fcde8-217">转换为 Blazor 时，代码后面和标记将合并为*详细信息。*</span><span class="sxs-lookup"><span data-stu-id="fcde8-217">When converting to Blazor, the code-behind and markup are combined into *Details.razor*.</span></span> <span data-ttu-id="fcde8-218">Razor 编译（等效于 *.designer.cs*文件中的内容）存储在*obj*目录中，默认情况下无法在**解决方案资源管理器**中查看。</span><span class="sxs-lookup"><span data-stu-id="fcde8-218">Razor compilation (equivalent to what's in *.designer.cs* files) is stored in the *obj* directory and aren't, by default, viewable in **Solution Explorer**.</span></span> <span data-ttu-id="fcde8-219">"Web 窗体"页由以下标记组成：</span><span class="sxs-lookup"><span data-stu-id="fcde8-219">The Web Forms page consists of the following markup:</span></span>

```aspx-csharp
<%@ Page Title="Details" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Details.aspx.cs" Inherits="eShopLegacyWebForms.Catalog.Details" %>

<asp:Content ID="Details" ContentPlaceHolderID="MainContent" runat="server">
    <h2 class="esh-body-title">Details</h2>

    <div class="container">
        <div class="row">
            <asp:Image runat="server" CssClass="col-md-6 esh-picture" ImageUrl='<%#"/Pics/" + product.PictureFileName%>' />
            <dl class="col-md-6 dl-horizontal">
                <dt>Name
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.Name%>' />
                </dd>

                <dt>Description
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.Description%>' />
                </dd>

                <dt>Brand
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.CatalogBrand.Brand%>' />
                </dd>

                <dt>Type
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.CatalogType.Type%>' />
                </dd>
                <dt>Price
                </dt>

                <dd>
                    <asp:Label CssClass="esh-price" runat="server" Text='<%#product.Price%>' />
                </dd>

                <dt>Picture name
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.PictureFileName%>' />
                </dd>

                <dt>Stock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.AvailableStock%>' />
                </dd>

                <dt>Restock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.RestockThreshold%>' />
                </dd>

                <dt>Max stock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.MaxStockThreshold%>' />
                </dd>

            </dl>
        </div>

        <div class="form-actions no-color esh-link-list">
            <a runat="server" href='<%# GetRouteUrl("EditProductRoute", new {id =product.Id}) %>' class="esh-link-item">Edit
            </a>
            |
            <a runat="server" href="~" class="esh-link-item">Back to list
            </a>
        </div>

    </div>
</asp:Content>
```

<span data-ttu-id="fcde8-220">前面的标记代码后面包括以下代码：</span><span class="sxs-lookup"><span data-stu-id="fcde8-220">The preceding markup's code-behind includes the following code:</span></span>

```csharp
using eShopLegacyWebForms.Models;
using eShopLegacyWebForms.Services;
using log4net;
using System;
using System.Web.UI;

namespace eShopLegacyWebForms.Catalog
{
    public partial class Details : System.Web.UI.Page
    {
        private static readonly ILog _log = LogManager.GetLogger(System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

        protected CatalogItem product;

        public ICatalogService CatalogService { get; set; }

        protected void Page_Load(object sender, EventArgs e)
        {
            var productId = Convert.ToInt32(Page.RouteData.Values["id"]);
            _log.Info($"Now loading... /Catalog/Details.aspx?id={productId}");
            product = CatalogService.FindCatalogItem(productId);

            this.DataBind();
        }
    }
}
```

<span data-ttu-id="fcde8-221">转换为 Blazor 后，Web 窗体页将转换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="fcde8-221">When converted to Blazor, the Web Forms page translates to the following code:</span></span>

```razor
@page "/Catalog/Details/{id:int}"
@inject ICatalogService CatalogService
@inject ILogger<Details> Logger

<h2 class="esh-body-title">Details</h2>

<div class="container">
    <div class="row">
        <img class="col-md-6 esh-picture" src="@($"/Pics/{_item.PictureFileName}")">

        <dl class="col-md-6 dl-horizontal">
            <dt>
                Name
            </dt>

            <dd>
                @_item.Name
            </dd>

            <dt>
                Description
            </dt>

            <dd>
                @_item.Description
            </dd>

            <dt>
                Brand
            </dt>

            <dd>
                @_item.CatalogBrand.Brand
            </dd>

            <dt>
                Type
            </dt>

            <dd>
                @_item.CatalogType.Type
            </dd>
            <dt>
                Price
            </dt>

            <dd>
                @_item.Price
            </dd>

            <dt>
                Picture name
            </dt>

            <dd>
                @_item.PictureFileName
            </dd>

            <dt>
                Stock
            </dt>

            <dd>
                @_item.AvailableStock
            </dd>

            <dt>
                Restock
            </dt>

            <dd>
                @_item.RestockThreshold
            </dd>

            <dt>
                Max stock
            </dt>

            <dd>
                @_item.MaxStockThreshold
            </dd>

        </dl>
    </div>

    <div class="form-actions no-color esh-link-list">
        <a href="@($"/Catalog/Edit/{_item.Id}")" class="esh-link-item">
            Edit
        </a>
        |
        <a href="/" class="esh-link-item">
            Back to list
        </a>
    </div>

</div>

@code {
    private CatalogItem _item;

    [Parameter]
    public int Id { get; set; }

    protected override void OnInitialized()
    {
        Logger.LogInformation("Now loading... /Catalog/Details/{Id}", Id);

        _item = CatalogService.FindCatalogItem(Id);
    }
}
```

<span data-ttu-id="fcde8-222">请注意，代码和标记位于同一文件中。</span><span class="sxs-lookup"><span data-stu-id="fcde8-222">Notice that the code and markup are in the same file.</span></span> <span data-ttu-id="fcde8-223">使用 属性`@inject`可以访问任何必需的服务。</span><span class="sxs-lookup"><span data-stu-id="fcde8-223">Any required services are made accessible with the `@inject` attribute.</span></span> <span data-ttu-id="fcde8-224">根据`@page`指令，可以在`Catalog/Details/{id}`路由上访问此页面。</span><span class="sxs-lookup"><span data-stu-id="fcde8-224">Per the `@page` directive, this page can be accessed at the `Catalog/Details/{id}` route.</span></span> <span data-ttu-id="fcde8-225">路由`{id}`占位符的值已限制为整数。</span><span class="sxs-lookup"><span data-stu-id="fcde8-225">The value of the route's `{id}` placeholder has been constrained to an integer.</span></span> <span data-ttu-id="fcde8-226">如[路由](pages-routing-layouts.md)部分所述，与 Web 窗体不同，Razor 组件显式表示其路由和包含的任何参数。</span><span class="sxs-lookup"><span data-stu-id="fcde8-226">As described in the [routing](pages-routing-layouts.md) section, unlike Web Forms, a Razor component explicitly states its route and any parameters that are included.</span></span> <span data-ttu-id="fcde8-227">许多 Web 窗体控件在 Blazor 中可能没有确切的对应控件。</span><span class="sxs-lookup"><span data-stu-id="fcde8-227">Many Web Forms controls may not have exact counterparts in Blazor.</span></span> <span data-ttu-id="fcde8-228">通常有一个等效的 HTML 代码段将服务于相同的目的。</span><span class="sxs-lookup"><span data-stu-id="fcde8-228">There's often an equivalent HTML snippet that will serve the same purpose.</span></span> <span data-ttu-id="fcde8-229">例如，`<asp:Label />`控件可以替换为 HTML`<label>`元素。</span><span class="sxs-lookup"><span data-stu-id="fcde8-229">For example, the `<asp:Label />` control can be replaced with an HTML `<label>` element.</span></span>

### <a name="model-validation-in-blazor"></a><span data-ttu-id="fcde8-230">布拉佐中的模型验证</span><span class="sxs-lookup"><span data-stu-id="fcde8-230">Model validation in Blazor</span></span>

<span data-ttu-id="fcde8-231">如果 Web 窗体代码包含验证，则可以通过很少对无的更改传输大部分内容。</span><span class="sxs-lookup"><span data-stu-id="fcde8-231">If your Web Forms code includes validation, you can transfer much of what you have with little-to-no changes.</span></span> <span data-ttu-id="fcde8-232">在 Blazor 中运行的一个好处是，无需自定义 JavaScript 即可运行相同的验证逻辑。</span><span class="sxs-lookup"><span data-stu-id="fcde8-232">A benefit to running in Blazor is that the same validation logic can be run without needing custom JavaScript.</span></span> <span data-ttu-id="fcde8-233">数据注释支持简单的模型验证。</span><span class="sxs-lookup"><span data-stu-id="fcde8-233">Data annotations enable easy model validation.</span></span>

<span data-ttu-id="fcde8-234">例如 *，Create.aspx*页具有具有验证的数据输入窗体。</span><span class="sxs-lookup"><span data-stu-id="fcde8-234">For example, the *Create.aspx* page has a data entry form with validation.</span></span> <span data-ttu-id="fcde8-235">示例代码段如下所示：</span><span class="sxs-lookup"><span data-stu-id="fcde8-235">An example snippet would look like this:</span></span>

```aspx
<div class="form-group">
    <label class="control-label col-md-2">Name</label>
    <div class="col-md-3">
        <asp:TextBox ID="Name" runat="server" CssClass="form-control"></asp:TextBox>
        <asp:RequiredFieldValidator runat="server" ControlToValidate="Name" Display="Dynamic"
            CssClass="field-validation-valid text-danger" ErrorMessage="The Name field is required." />
    </div>
</div>
```

<span data-ttu-id="fcde8-236">在 Blazor 中，等效标记在*Create.razor*文件中提供：</span><span class="sxs-lookup"><span data-stu-id="fcde8-236">In Blazor, the equivalent markup is provided in a *Create.razor* file:</span></span>

```razor
<EditForm Model="_item" OnValidSubmit="@...">
    <DataAnnotationsValidator />

    <div class="form-group">
        <label class="control-label col-md-2">Name</label>
        <div class="col-md-3">
            <InputText class="form-control" @bind-Value="_item.Name" />
            <ValidationMessage For="(() => _item.Name)" />
        </div>
    </div>

    ...
</EditForm>
```

<span data-ttu-id="fcde8-237">上下文`EditForm`包括验证支持，可以环绕输入。</span><span class="sxs-lookup"><span data-stu-id="fcde8-237">The `EditForm` context includes validation support and can be wrapped around input.</span></span> <span data-ttu-id="fcde8-238">数据注释是添加验证的常见方法。</span><span class="sxs-lookup"><span data-stu-id="fcde8-238">Data annotations are a common way to add validation.</span></span> <span data-ttu-id="fcde8-239">此类验证支持可通过`DataAnnotationsValidator`组件添加。</span><span class="sxs-lookup"><span data-stu-id="fcde8-239">Such validation support can be added via the `DataAnnotationsValidator` component.</span></span> <span data-ttu-id="fcde8-240">有关此机制的详细信息，请参阅[ASP.NET核心 Blazor 窗体和验证](/aspnet/core/blazor/forms-validation)。</span><span class="sxs-lookup"><span data-stu-id="fcde8-240">For more information on this mechanism, see [ASP.NET Core Blazor forms and validation](/aspnet/core/blazor/forms-validation).</span></span>

## <a name="migrate-built-in-web-forms-controls"></a><span data-ttu-id="fcde8-241">迁移内置 Web 窗体控件</span><span class="sxs-lookup"><span data-stu-id="fcde8-241">Migrate built-in Web Forms controls</span></span>

<span data-ttu-id="fcde8-242">*此内容即将推出。*</span><span class="sxs-lookup"><span data-stu-id="fcde8-242">*This content is coming soon.*</span></span>

## <a name="migrate-configuration"></a><span data-ttu-id="fcde8-243">迁移配置</span><span class="sxs-lookup"><span data-stu-id="fcde8-243">Migrate configuration</span></span>

<span data-ttu-id="fcde8-244">在 Web 窗体项目中，配置数据通常存储在*Web.config 文件中*。</span><span class="sxs-lookup"><span data-stu-id="fcde8-244">In a Web Forms project, configuration data is most commonly stored in the *web.config* file.</span></span> <span data-ttu-id="fcde8-245">配置数据与 访问一起`ConfigurationManager`。</span><span class="sxs-lookup"><span data-stu-id="fcde8-245">The configuration data is accessed with `ConfigurationManager`.</span></span> <span data-ttu-id="fcde8-246">分析对象通常需要服务。</span><span class="sxs-lookup"><span data-stu-id="fcde8-246">Services were often required to parse objects.</span></span> <span data-ttu-id="fcde8-247">使用 .NET 框架 4.7.2，通过 将可组合`ConfigurationBuilders`性添加到配置中。</span><span class="sxs-lookup"><span data-stu-id="fcde8-247">With .NET Framework 4.7.2, composability was added to configuration via `ConfigurationBuilders`.</span></span> <span data-ttu-id="fcde8-248">这些生成器允许开发人员添加各种配置源，然后在运行时组成这些源以检索必要的值。</span><span class="sxs-lookup"><span data-stu-id="fcde8-248">These builders allowed developers to add various sources for configuration that was then composed at runtime to retrieve the necessary values.</span></span>

<span data-ttu-id="fcde8-249">ASP.NET Core 引入了一个灵活的配置系统，允许您定义应用和部署使用的配置源或源。</span><span class="sxs-lookup"><span data-stu-id="fcde8-249">ASP.NET Core introduced a flexible configuration system that allows you to define the configuration source or sources used by your app and deployment.</span></span> <span data-ttu-id="fcde8-250">在`ConfigurationBuilder`Web 窗体应用中可能使用的基础结构是仿ASP.NET核心配置系统中使用的概念建模的。</span><span class="sxs-lookup"><span data-stu-id="fcde8-250">The `ConfigurationBuilder` infrastructure that you may be using in your Web Forms app was modeled after the concepts used in the ASP.NET Core configuration system.</span></span>

<span data-ttu-id="fcde8-251">以下代码段演示了 Web 窗体 eShop 项目如何使用*Web.config*来存储配置值：</span><span class="sxs-lookup"><span data-stu-id="fcde8-251">The following snippet demonstrates how the Web Forms eShop project uses *web.config* to store configuration values:</span></span>

```xml
<configuration>
  <configSections>
    <section name="entityFramework" type="System.Data.Entity.Internal.ConfigFile.EntityFrameworkSection, EntityFramework, Version=6.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" requirePermission="false" />
  </configSections>
  <connectionStrings>
    <add name="CatalogDBContext" connectionString="Data Source=(localdb)\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;" providerName="System.Data.SqlClient" />
  </connectionStrings>
  <appSettings>
    <add key="UseMockData" value="true" />
    <add key="UseCustomizationData" value="false" />
  </appSettings>
</configuration>
```

<span data-ttu-id="fcde8-252">机密（如数据库连接字符串）通常存储在*Web.config*中。机密不可避免地在不安全的位置（如源代码管理）中持续存在。</span><span class="sxs-lookup"><span data-stu-id="fcde8-252">It's common for secrets, such as database connection strings, to be stored within the *web.config*. The secrets are inevitably persisted in unsecure locations, such as source control.</span></span> <span data-ttu-id="fcde8-253">在ASP.NET核心上的 Blazor 上，前面基于 XML 的配置将替换为以下 JSON：</span><span class="sxs-lookup"><span data-stu-id="fcde8-253">With Blazor on ASP.NET Core, the preceding XML-based configuration is replaced with the following JSON:</span></span>

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

<span data-ttu-id="fcde8-254">JSON 是默认配置格式;但是，ASP.NET酷睿支持许多其他格式，包括 XML。</span><span class="sxs-lookup"><span data-stu-id="fcde8-254">JSON is the default configuration format; however, ASP.NET Core supports many other formats, including XML.</span></span> <span data-ttu-id="fcde8-255">还有几种社区支持的格式。</span><span class="sxs-lookup"><span data-stu-id="fcde8-255">There are also several community-supported formats.</span></span>

<span data-ttu-id="fcde8-256">Blazor 类中的构造函数通过称为构造`Startup`函数注入的`IConfiguration`DI 技术接受实例：</span><span class="sxs-lookup"><span data-stu-id="fcde8-256">The constructor in the Blazor project's `Startup` class accepts an `IConfiguration` instance through a DI technique known as constructor injection:</span></span>

```csharp
public class Startup
{
    public Startup(IConfiguration configuration, IWebHostEnvironment env)
    {
        Configuration = configuration;
        Env = env;
    }

    ...
}
```

<span data-ttu-id="fcde8-257">默认情况下，环境变量、JSON 文件（*应用设置.json*和应用*设置。环境\.json*）和命令行选项在配置对象中注册为有效的配置源。</span><span class="sxs-lookup"><span data-stu-id="fcde8-257">By default, environment variables, JSON files (*appsettings.json* and *appsettings.{Environment}.json*), and command-line options are registered as valid configuration sources in the configuration object.</span></span> <span data-ttu-id="fcde8-258">可通过 访问配置源`Configuration[key]`。</span><span class="sxs-lookup"><span data-stu-id="fcde8-258">The configuration sources can be accessed via `Configuration[key]`.</span></span> <span data-ttu-id="fcde8-259">更高级的技术是使用选项模式将配置数据绑定到对象。</span><span class="sxs-lookup"><span data-stu-id="fcde8-259">A more advanced technique is to bind the configuration data to objects using the options pattern.</span></span> <span data-ttu-id="fcde8-260">有关配置和选项模式的详细信息，请参阅 ASP.NET[核心中ASP.NET核心](/aspnet/core/fundamentals/configuration/)和[选项模式中的](/aspnet/core/fundamentals/configuration/options)配置。</span><span class="sxs-lookup"><span data-stu-id="fcde8-260">For more information on configuration and the options pattern, see [Configuration in ASP.NET Core](/aspnet/core/fundamentals/configuration/) and [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options), respectively.</span></span>

## <a name="migrate-data-access"></a><span data-ttu-id="fcde8-261">迁移数据访问</span><span class="sxs-lookup"><span data-stu-id="fcde8-261">Migrate data access</span></span>

<span data-ttu-id="fcde8-262">数据访问是任何应用的一个重要方面。</span><span class="sxs-lookup"><span data-stu-id="fcde8-262">Data access is an important aspect of any app.</span></span> <span data-ttu-id="fcde8-263">eShop 项目将目录信息存储在数据库中，并使用实体框架 （EF） 6 检索数据。</span><span class="sxs-lookup"><span data-stu-id="fcde8-263">The eShop project stores catalog information in a database and retrieves the data with Entity Framework (EF) 6.</span></span> <span data-ttu-id="fcde8-264">由于 .NET Core 3.0 中支持 EF 6，因此项目可以继续使用它。</span><span class="sxs-lookup"><span data-stu-id="fcde8-264">Since EF 6 is supported in .NET Core 3.0, the project can continue to use it.</span></span>

<span data-ttu-id="fcde8-265">eShop 需要进行以下与 EF 相关的更改：</span><span class="sxs-lookup"><span data-stu-id="fcde8-265">The following EF-related changes were necessary to eShop:</span></span>

- <span data-ttu-id="fcde8-266">在 .NET 框架`DbContext`中，对象接受窗体*名称_ConnectString*的字符串，并使用 中的`ConfigurationManager.AppSettings[ConnectionString]`连接字符串进行连接。</span><span class="sxs-lookup"><span data-stu-id="fcde8-266">In .NET Framework, the `DbContext` object accepts a string of the form *name=ConnectionString* and uses the connection string from `ConfigurationManager.AppSettings[ConnectionString]` to connect.</span></span> <span data-ttu-id="fcde8-267">在 .NET Core 中，不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="fcde8-267">In .NET Core, this isn't supported.</span></span> <span data-ttu-id="fcde8-268">必须提供连接字符串。</span><span class="sxs-lookup"><span data-stu-id="fcde8-268">The connection string must be supplied.</span></span>
- <span data-ttu-id="fcde8-269">以同步方式访问数据库。</span><span class="sxs-lookup"><span data-stu-id="fcde8-269">The database was accessed in a synchronous way.</span></span> <span data-ttu-id="fcde8-270">虽然这行得通，但可扩展性可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="fcde8-270">Though this works, scalability may suffer.</span></span> <span data-ttu-id="fcde8-271">此逻辑应移动到异步模式。</span><span class="sxs-lookup"><span data-stu-id="fcde8-271">This logic should be moved to an asynchronous pattern.</span></span>

<span data-ttu-id="fcde8-272">尽管对数据集绑定的本机支持不同，但 Blazor 在 Razor 页面中提供了灵活性和功能，其 C# 支持。</span><span class="sxs-lookup"><span data-stu-id="fcde8-272">Although there isn't the same native support for dataset binding, Blazor provides flexibility and power with its C# support in a Razor page.</span></span> <span data-ttu-id="fcde8-273">例如，您可以执行计算并显示结果。</span><span class="sxs-lookup"><span data-stu-id="fcde8-273">For example, you can perform calculations and display the result.</span></span> <span data-ttu-id="fcde8-274">有关 Blazor 中数据模式的详细信息，请参阅[数据访问](data.md)章节。</span><span class="sxs-lookup"><span data-stu-id="fcde8-274">For more information on data patterns in Blazor, see the [Data access](data.md) chapter.</span></span>

## <a name="architectural-changes"></a><span data-ttu-id="fcde8-275">体系结构更改</span><span class="sxs-lookup"><span data-stu-id="fcde8-275">Architectural changes</span></span>

<span data-ttu-id="fcde8-276">最后，在迁移到 Blazor 时需要考虑一些重要的体系结构差异。</span><span class="sxs-lookup"><span data-stu-id="fcde8-276">Finally, there are some important architectural differences to consider when migrating to Blazor.</span></span> <span data-ttu-id="fcde8-277">其中许多更改适用于基于 .NET Core 或 ASP.NET核心的任何更改。</span><span class="sxs-lookup"><span data-stu-id="fcde8-277">Many of these changes are applicable to anything based on .NET Core or ASP.NET Core.</span></span>

<span data-ttu-id="fcde8-278">由于 Blazor 建立在 .NET Core 上，因此在确保对 .NET Core 的支持时需要考虑。</span><span class="sxs-lookup"><span data-stu-id="fcde8-278">Because Blazor is built on .NET Core, there are considerations in ensuring support on .NET Core.</span></span> <span data-ttu-id="fcde8-279">一些主要更改包括删除以下功能：</span><span class="sxs-lookup"><span data-stu-id="fcde8-279">Some of the major changes include the removal of the following features:</span></span>

- <span data-ttu-id="fcde8-280">多个应用域</span><span class="sxs-lookup"><span data-stu-id="fcde8-280">Multiple AppDomains</span></span>
- <span data-ttu-id="fcde8-281">远程处理</span><span class="sxs-lookup"><span data-stu-id="fcde8-281">Remoting</span></span>
- <span data-ttu-id="fcde8-282">代码访问安全性 (CAS)</span><span class="sxs-lookup"><span data-stu-id="fcde8-282">Code Access Security (CAS)</span></span>
- <span data-ttu-id="fcde8-283">安全透明度</span><span class="sxs-lookup"><span data-stu-id="fcde8-283">Security Transparency</span></span>

<span data-ttu-id="fcde8-284">有关识别支持在 .NET Core 上运行的必要更改的技术的详细信息，请参阅[将代码从 .NET 框架移植到 .NET Core](/dotnet/core/porting)。</span><span class="sxs-lookup"><span data-stu-id="fcde8-284">For more information on techniques to identify necessary changes to support running on .NET Core, see [Port your code from .NET Framework to .NET Core](/dotnet/core/porting).</span></span>

<span data-ttu-id="fcde8-285">ASP.NET核心是ASP.NET的重新构想版本，并且有一些最初看起来并不明显的更改。</span><span class="sxs-lookup"><span data-stu-id="fcde8-285">ASP.NET Core is a reimagined version of ASP.NET and has some changes that may not initially seem obvious.</span></span> <span data-ttu-id="fcde8-286">主要更改包括：</span><span class="sxs-lookup"><span data-stu-id="fcde8-286">The main changes are:</span></span>

- <span data-ttu-id="fcde8-287">没有同步上下文，这意味着没有`HttpContext.Current`、`Thread.CurrentPrincipal`或其他静态访问器</span><span class="sxs-lookup"><span data-stu-id="fcde8-287">No synchronization context, which means there's no `HttpContext.Current`, `Thread.CurrentPrincipal`, or other static accessors</span></span>
- <span data-ttu-id="fcde8-288">无阴影复制</span><span class="sxs-lookup"><span data-stu-id="fcde8-288">No shadow copying</span></span>
- <span data-ttu-id="fcde8-289">无请求队列</span><span class="sxs-lookup"><span data-stu-id="fcde8-289">No request queue</span></span>

<span data-ttu-id="fcde8-290">ASP.NET Core 中的许多操作都是异步的，这允许更轻松地卸载 I/O 绑定的任务。</span><span class="sxs-lookup"><span data-stu-id="fcde8-290">Many operations in ASP.NET Core are asynchronous, which allows easier off-loading of I/O-bound tasks.</span></span> <span data-ttu-id="fcde8-291">请务必不要使用`Task.Wait()`或`Task.GetResult()`阻止，这可以快速耗尽线程池资源。</span><span class="sxs-lookup"><span data-stu-id="fcde8-291">It's important to never block by using `Task.Wait()` or `Task.GetResult()`, which can quickly exhaust thread pool resources.</span></span>

## <a name="migration-conclusion"></a><span data-ttu-id="fcde8-292">迁移结论</span><span class="sxs-lookup"><span data-stu-id="fcde8-292">Migration conclusion</span></span>

<span data-ttu-id="fcde8-293">此时，您已经看到许多示例，说明将 Web 窗体项目移动到 Blazor 需要什么。</span><span class="sxs-lookup"><span data-stu-id="fcde8-293">At this point, you've seen many examples of what it takes to move a Web Forms project to Blazor.</span></span> <span data-ttu-id="fcde8-294">有关完整示例，请参阅[eShopOnBlazor](https://github.com/dotnet-architecture/eShopOnBlazor)项目。</span><span class="sxs-lookup"><span data-stu-id="fcde8-294">For a full example, see the [eShopOnBlazor](https://github.com/dotnet-architecture/eShopOnBlazor) project.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="fcde8-295">上一步</span><span class="sxs-lookup"><span data-stu-id="fcde8-295">Previous</span></span>](security-authentication-authorization.md)
