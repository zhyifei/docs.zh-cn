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
# <a name="migrate-from-aspnet-web-forms-to-blazor"></a>从ASP.NET Web 窗体迁移到布拉佐尔

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

将代码库从ASP.NET Web 窗体迁移到 Blazor 是一项耗时的任务，需要规划。 本章概述了该过程。 可以简化转换的是确保应用遵循*N 层*体系结构，其中应用模型（在本例中为 Web 窗体）与业务逻辑分开。 这种层的逻辑分离可以清楚地说明需要迁移到 .NET Core 和 Blazor 的内容。

在此示例中，使用[GitHub](https://github.com/dotnet-architecture/eShopOnBlazor)上可用的 eShop 应用。 eShop 是一种目录服务，通过表单输入和验证提供 CRUD 功能。

为什么工作应用应迁移到 Blazor？ 很多时候，没有必要。 ASP.NET Web 表单将继续支持多年。 但是，Blazor 提供的许多功能仅在迁移的应用上受支持。 这些功能包括：

- 框架中的性能改进，例如`Span<T>`
- 能够以 Web 程序集身份运行
- 对 Linux 和 macOS 的跨平台支持
- 应用本地部署或共享框架部署，不影响其他应用

如果这些或其他新功能足够吸引人，则迁移应用可能具有价值。 迁移可以采用不同的形状;它可以是整个应用，也可以只是需要更改的某些终结点。 迁移的决定最终基于开发人员要解决的业务问题。

## <a name="server-side-versus-client-side-hosting"></a>服务器端与客户端托管

如[托管模型](hosting-models.md)章节所述，Blazor 应用可以通过两种不同的方式托管：服务器端和客户端。 服务器端模型使用ASP.NET核心信号R连接来管理 DOM 更新，同时在服务器上运行任何实际代码。 客户端模型在浏览器中作为 WebAssembly 运行，不需要服务器连接。 有许多差异可能会影响特定应用：

- 以 WebAssembly 身份运行仍处于开发阶段，当前可能不支持所有功能（如线程处理）
- 客户端和服务器之间的聊天通信可能会导致服务器端模式下的延迟问题
- 访问数据库和内部或受保护服务需要使用客户端托管提供单独的服务

在编写本文时，服务器端模型更像 Web 窗体。 本章的大部分重点介绍服务器端托管模型，因为它已做好生产准备。

## <a name="create-a-new-project"></a>创建新项目

此初始迁移步骤是创建新项目。 此项目类型基于 .NET Core 的 SDK 样式项目，并简化了以前项目格式中使用的许多样板。 有关详细信息，请参阅有关[项目结构](project-structure.md)的章节。

创建项目后，安装上一个项目中使用的库。 在较旧的 Web 窗体项目中，您可能已使用*包.config*文件列出所需的 NuGet 包。 在新的 SDK 样式项目中，*包.config*已替换为`<PackageReference>`项目文件中的元素。 此方法的一个好处是，所有依赖项都是以过渡方式安装的。 您只列出您关心的顶级依赖项。

您正在使用的许多依赖项可用于 .NET Core，包括实体框架 6 和 log4net。 如果没有可用的 .NET Core 或 .NET 标准版本，则经常使用 .NET 框架版本。 您的里程可能会有所不同。 .NET Core 中不可用的任何 API 都会导致运行时错误。 Visual Studio 会通知您此类套餐。 在**解决方案资源管理器**中的项目的**参考节点**上会出现一个黄色图标。

在基于 Blazor 的 eShop 项目中，您可以看到已安装的软件包。 以前 *，package.config*文件列出了项目中使用的每个包，导致文件近 50 行长。 *包段. 配置*是：

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

该`<packages>`元素包括所有必要的依赖项。 很难确定其中哪些包包含，因为您需要它们。 某些`<package>`元素的列出只是为了满足您需要的依赖项的需求。

Blazor 项目列出了项目文件中`<ItemGroup>`的元素中所需的依赖项：

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

一个NuGet包，简化了Web表单开发人员的生活是[Windows兼容性包](../../core/porting/windows-compat-pack.md)。 尽管 .NET Core 是跨平台的，但某些功能仅在 Windows 上可用。 通过安装兼容性包，可以获得特定于 Windows 的功能。 此类功能的示例包括注册表、WMI 和目录服务。 该软件包添加了大约 20，000 个 API，并激活了许多您可能已经熟悉的服务。 eShop 项目不需要兼容性包;因此，eShop 项目不需要兼容性包。但是，如果项目使用特定于 Windows 的功能，则该包可简化迁移工作。

## <a name="enable-startup-process"></a>启用启动过程

Blazor 的启动过程从 Web 窗体更改，并遵循其他ASP.NET核心服务的类似设置。 当托管服务器端时，Blazor 组件作为正常ASP.NET核心应用的一部分运行。 当使用 WebAssembly 在浏览器中托管时，Blazor 组件使用类似的托管模型。 区别在于组件作为独立于任何后端进程的服务运行。 无论哪种方式，启动都是类似的。

*Global.asax.cs*文件是 Web 窗体项目的默认启动页。 在 eShop 项目中，此文件配置"控制反转 （IoC）"容器，并处理应用或请求的各种生命周期事件。 其中一些事件使用中间件（如`Application_BeginRequest`）处理。 其他事件需要通过依赖项注入 （DI） 重写特定服务。

例如，eShop *Global.asax.cs*文件包含以下代码：

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

前面的文件将成为服务器端`Startup`Blazor 中的类：

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

您可能会从 Web 窗体中注意到的一个重要变化是 DI 的突出性。 DI 一直是 ASP.NET核心设计的指导原则。 它支持自定义ASP.NET核心框架的几乎所有方面。 甚至还有一个内置的服务提供商，可用于许多方案。 如果需要更多自定义，许多社区项目可以支持它。 例如，您可以进行第三方 DI 库投资。

在原始的 eShop 应用中，有一些用于会话管理的配置。 由于服务器端 Blazor 使用ASP.NET核心信号R进行通信，因此不支持会话状态，因为连接可能独立于 HTTP 上下文进行。 使用会话状态的应用需要在作为 Blazor 应用运行之前重新构建。

有关应用启动的详细信息，请参阅[应用启动](app-startup.md)。

## <a name="migrate-http-modules-and-handlers-to-middleware"></a>将 HTTP 模块和处理程序迁移到中间件

HTTP 模块和处理程序是 Web 窗体中用于控制 HTTP 请求管道的常见模式。 实现`IHttpModule`或`IHttpHandler`可以注册和处理传入请求的类。 Web 窗体在*Web.config 文件中*配置模块和处理程序。 Web 窗体还在很大程度上基于应用生命周期事件处理。 ASP.NET核心使用中间件代替。 中间件在`Configure``Startup`类的方法中注册。 中间件执行顺序由注册订单确定。

在[启用启动过程](#enable-startup-process)部分中，Web 窗体提出了生命周期事件作为`Application_BeginRequest`方法。 此事件在 ASP.NET 酷中不可用。 实现此行为的一个方法是实现中间件，如*Startup.cs*文件示例中所示。 此中间件执行相同的逻辑，然后将控制权传输到中间件管道中的下一个处理程序。

有关迁移模块和处理程序的详细信息，请参阅将 HTTP[处理程序和模块迁移到ASP.NET核心中间件](/aspnet/core/migration/http-modules)。

## <a name="migrate-static-files"></a>迁移静态文件

要提供静态文件（例如，HTML、CSS、图像和 JavaScript），必须通过中间件公开这些文件。 调用`UseStaticFiles`该方法可以从 Web 根路径提供静态文件。 默认 Web 根目录是*wwwroot，* 但可以自定义。 如 eShop `Configure` `Startup`类的方法中包含的：

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

eShop 项目支持基本的静态文件访问。 有许多自定义可用于静态文件访问。 有关启用默认文件或文件浏览器的信息，请参阅[ASP.NET 酷睿 中的静态文件](/aspnet/core/fundamentals/static-files)。

## <a name="migrate-runtime-bundling-and-minification-setup"></a>迁移运行时捆绑和最小化设置

捆绑和分量化是性能优化技术，用于减少检索某些文件类型的服务器请求的数量和大小。 在发送到客户端之前，JavaScript 和 CSS 通常会经历某种形式的捆绑或小化。 在 web 窗体ASP.NET，这些优化在运行时处理。 优化约定定义为*App_Start/BundleConfig.cs*文件。 在ASP.NET核心中，采用了一种更具声明性的方法。 文件列出了要进行挖掘的文件以及特定的小化设置。

有关捆绑和最小化的详细信息，请参阅 ASP.NET[酷中捆绑和小化静态资产](/aspnet/core/client-side/bundling-and-minification)。

## <a name="migrate-aspx-pages"></a>迁移 ASPX 页面

Web 窗体应用中的页面是具有 *.aspx*扩展名的文件。 Web 窗体页通常可以映射到 Blazor 中的组件。 Blazor 组件创作在具有 *.razor*扩展名的文件中。 对于 eShop 项目，五个页面将转换为 Razor 页面。

例如，详细信息视图由 Web 窗体项目中的三个文件组成：*详细信息.aspx、Details.aspx.cs**Details.aspx.cs*和*Details.aspx.designer.cs*。 转换为 Blazor 时，代码后面和标记将合并为*详细信息。* Razor 编译（等效于 *.designer.cs*文件中的内容）存储在*obj*目录中，默认情况下无法在**解决方案资源管理器**中查看。 "Web 窗体"页由以下标记组成：

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

前面的标记代码后面包括以下代码：

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

转换为 Blazor 后，Web 窗体页将转换为以下代码：

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

请注意，代码和标记位于同一文件中。 使用 属性`@inject`可以访问任何必需的服务。 根据`@page`指令，可以在`Catalog/Details/{id}`路由上访问此页面。 路由`{id}`占位符的值已限制为整数。 如[路由](pages-routing-layouts.md)部分所述，与 Web 窗体不同，Razor 组件显式表示其路由和包含的任何参数。 许多 Web 窗体控件在 Blazor 中可能没有确切的对应控件。 通常有一个等效的 HTML 代码段将服务于相同的目的。 例如，`<asp:Label />`控件可以替换为 HTML`<label>`元素。

### <a name="model-validation-in-blazor"></a>布拉佐中的模型验证

如果 Web 窗体代码包含验证，则可以通过很少对无的更改传输大部分内容。 在 Blazor 中运行的一个好处是，无需自定义 JavaScript 即可运行相同的验证逻辑。 数据注释支持简单的模型验证。

例如 *，Create.aspx*页具有具有验证的数据输入窗体。 示例代码段如下所示：

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

在 Blazor 中，等效标记在*Create.razor*文件中提供：

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

上下文`EditForm`包括验证支持，可以环绕输入。 数据注释是添加验证的常见方法。 此类验证支持可通过`DataAnnotationsValidator`组件添加。 有关此机制的详细信息，请参阅[ASP.NET核心 Blazor 窗体和验证](/aspnet/core/blazor/forms-validation)。

## <a name="migrate-built-in-web-forms-controls"></a>迁移内置 Web 窗体控件

*此内容即将推出。*

## <a name="migrate-configuration"></a>迁移配置

在 Web 窗体项目中，配置数据通常存储在*Web.config 文件中*。 配置数据与 访问一起`ConfigurationManager`。 分析对象通常需要服务。 使用 .NET 框架 4.7.2，通过 将可组合`ConfigurationBuilders`性添加到配置中。 这些生成器允许开发人员添加各种配置源，然后在运行时组成这些源以检索必要的值。

ASP.NET Core 引入了一个灵活的配置系统，允许您定义应用和部署使用的配置源或源。 在`ConfigurationBuilder`Web 窗体应用中可能使用的基础结构是仿ASP.NET核心配置系统中使用的概念建模的。

以下代码段演示了 Web 窗体 eShop 项目如何使用*Web.config*来存储配置值：

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

机密（如数据库连接字符串）通常存储在*Web.config*中。机密不可避免地在不安全的位置（如源代码管理）中持续存在。 在ASP.NET核心上的 Blazor 上，前面基于 XML 的配置将替换为以下 JSON：

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

JSON 是默认配置格式;但是，ASP.NET酷睿支持许多其他格式，包括 XML。 还有几种社区支持的格式。

Blazor 类中的构造函数通过称为构造`Startup`函数注入的`IConfiguration`DI 技术接受实例：

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

默认情况下，环境变量、JSON 文件（*应用设置.json*和应用*设置。环境\.json*）和命令行选项在配置对象中注册为有效的配置源。 可通过 访问配置源`Configuration[key]`。 更高级的技术是使用选项模式将配置数据绑定到对象。 有关配置和选项模式的详细信息，请参阅 ASP.NET[核心中ASP.NET核心](/aspnet/core/fundamentals/configuration/)和[选项模式中的](/aspnet/core/fundamentals/configuration/options)配置。

## <a name="migrate-data-access"></a>迁移数据访问

数据访问是任何应用的一个重要方面。 eShop 项目将目录信息存储在数据库中，并使用实体框架 （EF） 6 检索数据。 由于 .NET Core 3.0 中支持 EF 6，因此项目可以继续使用它。

eShop 需要进行以下与 EF 相关的更改：

- 在 .NET 框架`DbContext`中，对象接受窗体*名称_ConnectString*的字符串，并使用 中的`ConfigurationManager.AppSettings[ConnectionString]`连接字符串进行连接。 在 .NET Core 中，不支持此功能。 必须提供连接字符串。
- 以同步方式访问数据库。 虽然这行得通，但可扩展性可能会受到影响。 此逻辑应移动到异步模式。

尽管对数据集绑定的本机支持不同，但 Blazor 在 Razor 页面中提供了灵活性和功能，其 C# 支持。 例如，您可以执行计算并显示结果。 有关 Blazor 中数据模式的详细信息，请参阅[数据访问](data.md)章节。

## <a name="architectural-changes"></a>体系结构更改

最后，在迁移到 Blazor 时需要考虑一些重要的体系结构差异。 其中许多更改适用于基于 .NET Core 或 ASP.NET核心的任何更改。

由于 Blazor 建立在 .NET Core 上，因此在确保对 .NET Core 的支持时需要考虑。 一些主要更改包括删除以下功能：

- 多个应用域
- 远程处理
- 代码访问安全性 (CAS)
- 安全透明度

有关识别支持在 .NET Core 上运行的必要更改的技术的详细信息，请参阅[将代码从 .NET 框架移植到 .NET Core](/dotnet/core/porting)。

ASP.NET核心是ASP.NET的重新构想版本，并且有一些最初看起来并不明显的更改。 主要更改包括：

- 没有同步上下文，这意味着没有`HttpContext.Current`、`Thread.CurrentPrincipal`或其他静态访问器
- 无阴影复制
- 无请求队列

ASP.NET Core 中的许多操作都是异步的，这允许更轻松地卸载 I/O 绑定的任务。 请务必不要使用`Task.Wait()`或`Task.GetResult()`阻止，这可以快速耗尽线程池资源。

## <a name="migration-conclusion"></a>迁移结论

此时，您已经看到许多示例，说明将 Web 窗体项目移动到 Blazor 需要什么。 有关完整示例，请参阅[eShopOnBlazor](https://github.com/dotnet-architecture/eShopOnBlazor)项目。

>[!div class="step-by-step"]
>[上一步](security-authentication-authorization.md)
