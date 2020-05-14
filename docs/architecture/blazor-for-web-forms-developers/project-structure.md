---
title: Blazor 应用的项目结构
description: 了解 ASP.NET Web 窗体和 Blazor 项目的项目结构比较。
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 7e622663bedce13c93b8d72f5a699d076e8139b7
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394770"
---
# <a name="project-structure-for-blazor-apps"></a>Blazor 应用的项目结构

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

尽管它们的项目结构明显不同，ASP.NET Web 窗体和 Blazor 也共享许多类似的概念。 在这里，我们将查看 Blazor 项目的结构，并将其与 ASP.NET Web 窗体项目进行比较。

若要创建第一个 Blazor 应用，请按照[Blazor 入门步骤](/aspnet/core/blazor/get-started)中的说明进行操作。 可以按照说明在 ASP.NET Core 中创建托管的 Blazor 服务器应用或 Blazor WebAssembly 应用。 除了托管模型特定的逻辑外，这两个项目中的大多数代码都是相同的。

## <a name="project-file"></a>项目文件

Blazor 服务器应用程序是 .NET Core 项目。 Blazor 服务器应用程序的项目文件与它一样简单：

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Blazor WebAssembly 应用程序的项目文件看起来稍微更多（具体版本号可能会有所不同）：

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <RazorLangVersion>3.0</RazorLangVersion>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.Blazor" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.Build" Version="3.1.0" PrivateAssets="all" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.HttpClient" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.DevServer" Version="3.1.0" PrivateAssets="all" />
  </ItemGroup>

  <ItemGroup>
    <ProjectReference Include="..\Shared\BlazorWebAssemblyApp1.Shared.csproj" />
  </ItemGroup>

</Project>
```

Blazor WebAssembly 项目目标 .NET Standard 而不是 .NET Core，因为它们在基于 WebAssembly 的 .NET 运行时上的浏览器中运行。 不能像在服务器或开发人员计算机上那样将 .NET 安装到 web 浏览器中。 因此，该项目使用单独的包引用来引用 Blazor framework。

相比之下，默认的 ASP.NET Web 窗体项目在其 *.csproj*文件中包含将近300行的 XML，其中的大多数行都显式列出了项目中的各种代码和内容文件。 .NET Core 和基于 .NET Standard 的项目中的许多简化来自通过引用 SDK 导入的默认目标和属性 `Microsoft.NET.Sdk.Web` ，通常称为 WEB SDK。 Web SDK 包括通配符和其他很便利，用于简化在项目中包含的代码和内容文件。 无需显式列出文件。 面向 .NET Core 时，Web SDK 还添加了对 .NET Core 和 ASP.NET Core 共享框架的框架引用。 框架在 "解决方案资源管理器" 窗口中的 "**依赖关系**  >  **框架**" 节点中可见。 **Solution Explorer** 共享框架是安装 .NET Core 时计算机上安装的程序集的集合。

尽管它们受支持，但在 .NET Core 项目中，各个程序集引用不太常见。 大多数项目依赖项都作为 NuGet 包引用处理。 只需引用 .NET Core 项目中的顶级包依赖项。 自动包含可传递的依赖项。 包引用会使用元素添加到项目文件中，而不是使用 ASP.NET Web 窗体项目中常见的*包 .config*文件来引用包。 `<PackageReference>`

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a>入口点

Blazor 服务器应用程序的入口点是在*Program.cs*文件中定义的，如控制台应用程序中所示。 当应用程序执行时，它将使用特定于 web 应用的默认值创建并运行 web 主机实例。 Web 主机管理 Blazor 服务器应用程序的生命周期，并设置主机级服务。 此类服务的示例包括配置、日志记录、依赖关系注入和 HTTP 服务器。 此代码主要是样板化的，通常保持不变。

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}
```

Blazor WebAssembly apps 还定义*Program.cs*中的入口点。 代码看起来略有不同。 此代码类似于设置应用程序主机以向应用程序提供相同的主机级服务。 不过，WebAssembly 应用主机不会设置 HTTP 服务器，因为它是直接在浏览器中执行的。

Blazor 应用程序有一个 `Startup` 类，而不是一个*global.asax*文件，用于定义应用程序的启动逻辑。 `Startup`类用于配置应用程序和任何特定于应用程序的服务。 在 Blazor 服务器应用中， `Startup` 类用于为客户端浏览器和服务器之间的 Blazor 使用的实时连接设置终结点。 在 Blazor WebAssembly 应用中， `Startup` 类定义应用的根组件及其呈现位置。 我们将深入了解 `Startup` [应用程序启动](./app-startup.md)部分中的类。

## <a name="static-files"></a>静态文件

与 ASP.NET Web 窗体项目不同，Blazor 项目中的所有文件都不能被请求为静态文件。 只有*wwwroot*文件夹中的文件可通过 web 寻址。 此文件夹被称为应用程序的 "web 根目录"。 应用程序的 web 根目录之外的任何内容都*无法*进行 web 寻址。 此设置提供了额外的安全级别，可防止在 web 上意外公开项目文件。

## <a name="configuration"></a>配置

ASP.NET Web 窗体应用中的配置通常使用一个或多个*web.config*文件进行处理。 Blazor apps 通常*不包含 web.config 文件。* 如果是这样，则在 IIS 上承载时，该文件仅用于配置 IIS 特定的设置。 相反，Blazor Server apps 使用 ASP.NET Core 配置抽象（Blazor WebAssembly 应用程序当前不支持相同的配置抽象，但这可能是将来添加的一项功能）。 例如，默认的 Blazor 服务器应用将一些设置存储在*appsettings*中。

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    }
  },
  "AllowedHosts": "*"
}
```

有关配置的详细信息，请参阅[配置](./config.md)节 ASP.NET Core 项目。

## <a name="razor-components"></a>Razor 组件

Blazor 项目中的大多数文件都是*razor*文件。 Razor 是一种基于 HTML 和 c # 的模板化语言，用于动态生成 web UI。 *Razor*文件定义构成应用程序的 UI 的组件。 大多数情况下，Blazor 服务器和 Blazor WebAssembly 应用程序的组件都是相同的。 Blazor 中的组件类似于 ASP.NET Web 窗体中的用户控件。

生成项目时，每个 Razor 组件文件都将编译为 .NET 类。 生成的类捕获组件的状态、呈现逻辑、生命周期方法、事件处理程序和其他逻辑。 我们将在[使用 Blazor 构建可重复使用的 UI 组件](./components.md)部分中了解如何创作组件。

*_Imports*文件不是 razor 组件文件。 相反，它们定义一组 Razor 指令以导入到同一文件夹及其子文件夹中的其他*razor*文件中。 例如， *_Imports razor*文件是一种为 `using` 常用命名空间添加指令的常规方法：

```razor
@using System.Net.Http
@using Microsoft.AspNetCore.Authorization
@using Microsoft.AspNetCore.Components.Authorization
@using Microsoft.AspNetCore.Components.Forms
@using Microsoft.AspNetCore.Components.Routing
@using Microsoft.AspNetCore.Components.Web
@using Microsoft.JSInterop
@using BlazorApp1
@using BlazorApp1.Shared
```

## <a name="pages"></a>页面

Blazor 应用中的页面位于何处？ Blazor 不会为可寻址页面定义单独的文件扩展名，例如 ASP.NET Web Forms apps 中的 *.aspx*文件。 而是通过将路由分配给组件来定义页面。 通常使用 `@page` Razor 指令分配路由。 例如， `Counter` 在*Pages/Counter*文件中编写的组件定义了以下路由：

```razor
@page "/counter"
```

Blazor 中的路由在客户端（而不是在服务器上）进行处理。 当用户在浏览器中导航时，Blazor 会截获导航，然后用匹配的路由呈现组件。

组件的文件位置目前不会推理组件路由，就像 *.aspx*页面一样。 将来可能会添加此功能。 必须在组件上显式指定每个路由。 在 "*页面*" 文件夹中存储可路由的组件无特殊含义，只是一种约定。

我们将在 "[页面"、"路由" 和 "布局](./pages-routing-layouts.md)" 部分的 Blazor 中更详细地介绍。

## <a name="layout"></a>布局

在 ASP.NET Web 窗体应用程序中，使用*母版页（master*）处理公用页面布局。 在 Blazor 应用中，使用布局组件（*Shared/MainLayout*）处理页面布局。 "[页面"、"路由" 和 "布局"](./pages-routing-layouts.md)部分中将更详细地讨论布局组件。

## <a name="bootstrap-blazor"></a>启动 Blazor

若要启动 Blazor，应用必须：

- 指定根组件（*app.config*）在页面上的呈现位置。
- 添加相应的 Blazor 框架脚本。

在 Blazor 服务器应用程序中，根组件的 "主机" 页在 *_Host.* # 文件中定义。 此文件定义了一个 Razor 页面，而不是一个组件。 Razor Pages 使用 Razor 语法来定义服务器可寻址页面，与 *.aspx*页面非常类似。 `Html.RenderComponentAsync<TComponent>(RenderMode)`方法用于定义根级别组件的呈现位置。 `RenderMode`选项指示组件的呈现方式。 下表概述了支持的 `RenderMode` 选项。

|选项                        |说明       |
|------------------------------|------------------|
|`RenderMode.Server`           |建立与浏览器的连接后交互呈现|
|`RenderMode.ServerPrerendered`|首先预呈现并以交互方式呈现|
|`RenderMode.Static`           |呈现为静态内容|

*_Framework/blazor.server.js*的脚本引用与服务器建立实时连接，并处理所有用户交互和 UI 更新。

```razor
@page "/"
@namespace BlazorApp1.Pages
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>BlazorApp1</title>
    <base href="~/" />
    <link rel="stylesheet" href="css/bootstrap/bootstrap.min.css" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>
        @(await Html.RenderComponentAsync<App>(RenderMode.ServerPrerendered))
    </app>

    <script src="_framework/blazor.server.js"></script>
</body>
</html>
```

在 Blazor WebAssembly 应用中，"主机" 页是 " *wwwroot/index.html*" 下的简单静态 HTML 文件。 `<app>`元素用于指示应呈现根组件的位置。

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>BlazorApp2</title>
    <base href="/" />
    <link href="css/bootstrap/bootstrap.min.css" rel="stylesheet" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>Loading...</app>

    <script src="_framework/blazor.webassembly.js"></script>
</body>
</html>
```

要呈现的特定组件是在应用程序的方法中配置的， `Startup.Configure` 对应的 CSS 选择器指示应呈现组件的位置。

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
    }

    public void Configure(IComponentsApplicationBuilder app)
    {
        app.AddComponent<App>("app");
    }
}
```

## <a name="build-output"></a>生成输出

生成 Blazor 项目时，所有 Razor 组件和代码文件都将编译为一个程序集。 与 ASP.NET Web 窗体项目不同，Blazor 不支持 UI 逻辑的运行时编译。

## <a name="run-the-app"></a>运行应用

若要运行 Blazor Server 应用程序，请 `F5` 在 Visual Studio 中按。 Blazor apps 不支持运行时编译。 若要查看代码和组件标记更改的结果，请在附加调试器的情况下重新生成并重新启动应用。 如果在未附加调试器的情况下运行（ `Ctrl+F5` ），则 Visual Studio 会监视文件更改，并在进行更改后重新启动应用。 进行更改后，手动刷新浏览器。

若要运行 Blazor WebAssembly 应用，请选择以下方法之一：

- 使用开发服务器直接运行客户端项目。
- 在将应用程序托管到 ASP.NET Core 时运行服务器项目。

Blazor WebAssembly apps 不支持使用 Visual Studio 进行调试。 若要运行应用，请使用 `Ctrl+F5` 而不是 `F5` 。 您可以改为直接在浏览器中调试 Blazor WebAssembly 应用程序。 有关详细信息，请参阅[Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) 。

>[!div class="step-by-step"]
>[上一页](hosting-models.md)
>[下一页](app-startup.md)
