---
title: 布拉佐应用程序的项目结构
description: 了解ASP.NET Web 窗体和 Blazor 项目的项目结构比较情况。
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 2c383e86ff22f5a3460476998992b66e9417cc11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401741"
---
# <a name="project-structure-for-blazor-apps"></a>布拉佐应用程序的项目结构

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

尽管它们的项目结构存在显著差异，但 Web 窗体和 Blazor ASP.NET有许多类似的概念。 在这里，我们将查看 Blazor 项目的结构，并将其与ASP.NET Web 窗体项目进行比较。

要创建您的第一个 Blazor 应用程序，请按照[Blazor 入门步骤](/aspnet/core/blazor/get-started)中的说明进行操作。 您可以按照说明创建 Blazor Server 应用或托管在 ASP.NET 核心中的 Blazor WebAssembly 应用。 除了特定于宿主模型的逻辑之外，两个项目中的大多数代码都是相同的。

## <a name="project-file"></a>项目文件

Blazor 服务器应用程序是 .NET 核心项目。 Blazor Server 应用的项目文件非常简单，因为它可以得到：

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Blazor WebAssembly 应用的项目文件看起来更参与（确切的版本号可能有所不同）：

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

Blazor WebAssembly 项目的目标是 .NET 标准而不是 .NET Core，因为它们在基于 WebAssembly 的 .NET 运行时的浏览器中运行。 不能像在服务器或开发人员计算机上那样将 .NET 安装到 Web 浏览器中。 因此，该项目使用单个包引用引用 Blazor 框架。

相比之下，默认ASP.NET Web 窗体项目在其 *.csproj*文件中包含近 300 行 XML，其中大多数显式列出项目中的各种代码和内容文件。 基于 .NET Core 和 .NET 标准项目中的许多简化都来自通过引用`Microsoft.NET.Sdk.Web`SDK 导入的默认目标和属性，通常简称为 Web SDK。 Web SDK 包括通配符和其他简化项目中包含代码和内容文件的便利。 您无需显式列出文件。 在定位 .NET Core 时，Web SDK 还会添加对 .NET Core 和 ASP.NET核心共享框架的框架引用。 框架在**解决方案资源管理器**窗口中**的依赖项** > **框架**节点中可见。 共享框架是安装 .NET Core 时安装在计算机上的程序集的集合。

尽管它们受支持，但单个程序集引用在 .NET Core 项目中不太常见。 大多数项目依赖项都作为 NuGet 包引用处理。 您只需引用 .NET Core 项目中的顶级包依赖项。 自动包含传递依赖项。 程序包引用使用 元素添加到项目文件中`<PackageReference>`，而不是使用 ASP.NET Web 窗体项目中常见的*包.config*文件来引用包。

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a>入口点

Blazor Server 应用的入口点在*Program.cs*文件中定义，正如您在控制台应用中看到的。 应用执行时，它使用特定于 Web 应用的默认值创建并运行 Web 主机实例。 Web 主机管理 Blazor Server 应用的生命周期并设置主机级服务。 此类服务的示例包括配置、日志记录、依赖项注入和 HTTP 服务器。 此代码大部分是样板，通常保持不变。

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

Blazor WebAssembly 应用程序还在*Program.cs*中定义了入口点。 代码看起来略有不同。 代码类似，因为它正在设置应用主机以向应用提供相同的主机级服务。 但是，WebAssembly 应用主机不会设置 HTTP 服务器，因为它直接在浏览器中执行。

Blazor 应用具有`Startup`一个类而不是*全局.asax*文件来定义应用程序的启动逻辑。 该`Startup`类用于配置应用和任何特定于应用的服务。 在 Blazor Server 应用中`Startup`，类用于设置 Blazor 在客户端浏览器和服务器之间使用的实时连接的终结点。 在 Blazor WebAssembly 应用中`Startup`，类定义应用的根组件以及应呈现这些组件的位置。 我们将更深入地了解`Startup`[应用启动](./app-startup.md)部分中的类。

## <a name="static-files"></a>静态文件

与 web 窗体项目ASP.NET不同，并非所有 Blazor 项目中的文件都可以请求作为静态文件。 只有*wwwroot*文件夹中的文件是 Web 地址寻址的。 此文件夹将引用到应用程序的"Web 根"。 应用 Web 根之外的任何内容*都无法*Web 寻址。 此设置提供了额外的安全级别，可防止意外在 Web 上公开项目文件。

## <a name="configuration"></a>配置

ASP.NET Web 窗体应用中的配置通常使用一个或多个*Web.config 文件*进行处理。 Blazor 应用程序通常没有*Web.config*文件。 如果这样做，则该文件仅用于在 IIS 上托管时配置特定于 IIS 的设置。 相反，Blazor Server 应用使用ASP.NET核心配置抽象（Blazor WebAssembly 应用目前不支持相同的配置抽象，但这可能是将来添加的功能）。 例如，默认的 Blazor Server 应用程序将某些*设置存储在 appsettings.json*中。

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

我们将在"配置"部分中了解有关ASP.NET核心项目中[的配置](./config.md)。

## <a name="razor-components"></a>Razor 组件

布拉佐项目中的大多数文件都是 *.razor*文件。 Razor 是基于 HTML 和 C# 的模板化语言，用于动态生成 Web UI。 *.razor*文件定义构成应用 UI 的组件。 在大多数情况下，布拉佐服务器和 Blazor WebAssembly 应用的组件都是相同的。 Blazor 中的组件类似于ASP.NET Web 窗体中的用户控件。

生成项目时，每个 Razor 组件文件都会编译为 .NET 类。 生成的类捕获组件的状态、呈现逻辑、生命周期方法、事件处理程序和其他逻辑。 我们将介绍使用 Blazor 部分构建[可重用 UI 组件](./components.md)的创作组件。

*_Imports.Razor*文件不是 Razor 组件文件。 相反，它们定义了一组 Razor 指令，以导入到同一文件夹中及其子文件夹中的其他 *.razor*文件中。 例如 *，_Imports.razor*文件是添加`using`常用命名空间语句的传统方法：

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

## <a name="pages"></a>页

Blazor 应用程序中的页面在哪里？ Blazor 不会为可寻址页面定义单独的文件扩展名，如 ASP.NET Web 窗体应用中的 *.aspx*文件。 相反，页面是通过为组件分配路由来定义的。 路由通常使用`@page`Razor 指令分配。 例如，`Counter`在*Pages/Counter.razor*文件中创作的组件定义了以下路由：

```razor
@page "/counter"
```

Blazor 中的路由是客户端处理的，而不是服务器上的。 当用户在浏览器中导航时，Blazor 会拦截导航，然后使用匹配的路由呈现组件。

组件路由当前未像使用 *.aspx*页一样由组件的文件位置推断。 此功能将来可能会添加。 必须在组件上显式指定每个路由。 在*Pages*文件夹中存储可路由组件没有特殊含义，纯属惯例。

我们将在["页面"、路由和布局](./pages-routing-layouts.md)部分更详细地介绍 Blazor 中的路由。

## <a name="layout"></a>布局

在ASP.NET Web 窗体应用中，使用母版页 *（Site.Master*） 处理常见页面布局。 在 Blazor 应用中，页面布局使用布局组件 （*共享/MainLayout.razor）* 处理。 布局组件将在[页面、路由和布局](./pages-routing-layouts.md)部分中详细讨论。

## <a name="bootstrap-blazor"></a>靴子布拉佐尔

要引导 Blazor，应用程序必须：

- 指定在页面上应呈现根组件 （*App.Razor*） 的位置。
- 添加相应的 Blazor 框架脚本。

在 Blazor Server 应用中，根组件的主机页在 *_Host.cshtml*文件中定义。 此文件定义剃刀页，而不是组件。 Razor 页面使用 Razor 语法来定义服务器可寻址页面，非常类似于 *.aspx*页面。 该方法`Html.RenderComponentAsync<TComponent>(RenderMode)`用于定义应呈现根级组件的位置。 该`RenderMode`选项指示组件的呈现方式。 下表概述了支持`RenderMode`的选项。

|选项                        |说明       |
|------------------------------|------------------|
|`RenderMode.Server`           |建立与浏览器的连接后以交互方式呈现|
|`RenderMode.ServerPrerendered`|首先预渲染，然后以交互方式呈现|
|`RenderMode.Static`           |呈现为静态内容|

对 *_framework/blazor.server.js*的脚本引用建立与服务器的实时连接，然后处理所有用户交互和 UI 更新。

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

在 Blazor WebAssembly 应用程序中，主机页是*wwwroot/index.html*下的简单静态 HTML 文件。 该`<app>`元素用于指示应呈现根组件的位置。

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

要呈现的特定组件在应用`Startup.Configure`的方法中配置，并带有相应的 CSS 选择器，指示应呈现组件的位置。

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

生成 Blazor 项目时，所有 Razor 组件和代码文件都编译到单个程序集中。 与web窗体项目ASP.NET不同，Blazor 不支持 UI 逻辑的运行时编译。

## <a name="run-the-app"></a>运行应用

要运行 Blazor 服务器应用，`F5`请按可视化工作室。 Blazor 应用不支持运行时编译。 要查看代码和组件标记更改的结果，请重新生成并重新启动应用，并附加调试器。 如果在未附加调试器的情况下运行 （），Visual`Ctrl+F5`Studio 会监视文件更改，并在进行更改时重新启动应用。 在进行更改时，您可以手动刷新浏览器。

要运行 Blazor WebAssembly 应用，请选择以下方法之一：

- 直接使用开发服务器运行客户端项目。
- 使用 ASP.NET 核心托管应用时运行服务器项目。

Blazor WebAssembly 应用不支持使用可视化工作室进行调试。 要运行应用，请使用`Ctrl+F5`而不是`F5`。 您可以直接在浏览器中调试 Blazor WebAssembly 应用。 有关详细信息[，请参阅调试ASP.NET核心布拉佐尔](/aspnet/core/blazor/debug)。

>[!div class="step-by-step"]
>[上一个](hosting-models.md)
>[下一个](app-startup.md)
