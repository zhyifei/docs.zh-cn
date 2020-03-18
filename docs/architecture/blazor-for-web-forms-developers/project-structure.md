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
# <a name="project-structure-for-blazor-apps"></a><span data-ttu-id="cf528-103">布拉佐应用程序的项目结构</span><span class="sxs-lookup"><span data-stu-id="cf528-103">Project structure for Blazor apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="cf528-104">尽管它们的项目结构存在显著差异，但 Web 窗体和 Blazor ASP.NET有许多类似的概念。</span><span class="sxs-lookup"><span data-stu-id="cf528-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="cf528-105">在这里，我们将查看 Blazor 项目的结构，并将其与ASP.NET Web 窗体项目进行比较。</span><span class="sxs-lookup"><span data-stu-id="cf528-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="cf528-106">要创建您的第一个 Blazor 应用程序，请按照[Blazor 入门步骤](/aspnet/core/blazor/get-started)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="cf528-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="cf528-107">您可以按照说明创建 Blazor Server 应用或托管在 ASP.NET 核心中的 Blazor WebAssembly 应用。</span><span class="sxs-lookup"><span data-stu-id="cf528-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="cf528-108">除了特定于宿主模型的逻辑之外，两个项目中的大多数代码都是相同的。</span><span class="sxs-lookup"><span data-stu-id="cf528-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="cf528-109">项目文件</span><span class="sxs-lookup"><span data-stu-id="cf528-109">Project file</span></span>

<span data-ttu-id="cf528-110">Blazor 服务器应用程序是 .NET 核心项目。</span><span class="sxs-lookup"><span data-stu-id="cf528-110">Blazor Server apps are .NET Core projects.</span></span> <span data-ttu-id="cf528-111">Blazor Server 应用的项目文件非常简单，因为它可以得到：</span><span class="sxs-lookup"><span data-stu-id="cf528-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="cf528-112">Blazor WebAssembly 应用的项目文件看起来更参与（确切的版本号可能有所不同）：</span><span class="sxs-lookup"><span data-stu-id="cf528-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

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

<span data-ttu-id="cf528-113">Blazor WebAssembly 项目的目标是 .NET 标准而不是 .NET Core，因为它们在基于 WebAssembly 的 .NET 运行时的浏览器中运行。</span><span class="sxs-lookup"><span data-stu-id="cf528-113">Blazor WebAssembly projects target .NET Standard instead of .NET Core because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="cf528-114">不能像在服务器或开发人员计算机上那样将 .NET 安装到 Web 浏览器中。</span><span class="sxs-lookup"><span data-stu-id="cf528-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="cf528-115">因此，该项目使用单个包引用引用 Blazor 框架。</span><span class="sxs-lookup"><span data-stu-id="cf528-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="cf528-116">相比之下，默认ASP.NET Web 窗体项目在其 *.csproj*文件中包含近 300 行 XML，其中大多数显式列出项目中的各种代码和内容文件。</span><span class="sxs-lookup"><span data-stu-id="cf528-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="cf528-117">基于 .NET Core 和 .NET 标准项目中的许多简化都来自通过引用`Microsoft.NET.Sdk.Web`SDK 导入的默认目标和属性，通常简称为 Web SDK。</span><span class="sxs-lookup"><span data-stu-id="cf528-117">Many of the simplifications in the .NET Core- and .NET Standard-based projects come from the default targets and properties imported by referencing the `Microsoft.NET.Sdk.Web` SDK, often referred to as simply the Web SDK.</span></span> <span data-ttu-id="cf528-118">Web SDK 包括通配符和其他简化项目中包含代码和内容文件的便利。</span><span class="sxs-lookup"><span data-stu-id="cf528-118">The Web SDK includes wildcards and other conveniences that simplify inclusion of code and content files in the project.</span></span> <span data-ttu-id="cf528-119">您无需显式列出文件。</span><span class="sxs-lookup"><span data-stu-id="cf528-119">You don't need to list the files explicitly.</span></span> <span data-ttu-id="cf528-120">在定位 .NET Core 时，Web SDK 还会添加对 .NET Core 和 ASP.NET核心共享框架的框架引用。</span><span class="sxs-lookup"><span data-stu-id="cf528-120">When targeting .NET Core, the Web SDK also adds framework references to both the .NET Core and ASP.NET Core shared frameworks.</span></span> <span data-ttu-id="cf528-121">框架在**解决方案资源管理器**窗口中**的依赖项** > **框架**节点中可见。</span><span class="sxs-lookup"><span data-stu-id="cf528-121">The frameworks are visible from the **Dependencies** > **Frameworks** node in the **Solution Explorer** window.</span></span> <span data-ttu-id="cf528-122">共享框架是安装 .NET Core 时安装在计算机上的程序集的集合。</span><span class="sxs-lookup"><span data-stu-id="cf528-122">The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.</span></span>

<span data-ttu-id="cf528-123">尽管它们受支持，但单个程序集引用在 .NET Core 项目中不太常见。</span><span class="sxs-lookup"><span data-stu-id="cf528-123">Although they're supported, individual assembly references are less common in .NET Core projects.</span></span> <span data-ttu-id="cf528-124">大多数项目依赖项都作为 NuGet 包引用处理。</span><span class="sxs-lookup"><span data-stu-id="cf528-124">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="cf528-125">您只需引用 .NET Core 项目中的顶级包依赖项。</span><span class="sxs-lookup"><span data-stu-id="cf528-125">You only need to reference top-level package dependencies in .NET Core projects.</span></span> <span data-ttu-id="cf528-126">自动包含传递依赖项。</span><span class="sxs-lookup"><span data-stu-id="cf528-126">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="cf528-127">程序包引用使用 元素添加到项目文件中`<PackageReference>`，而不是使用 ASP.NET Web 窗体项目中常见的*包.config*文件来引用包。</span><span class="sxs-lookup"><span data-stu-id="cf528-127">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="cf528-128">入口点</span><span class="sxs-lookup"><span data-stu-id="cf528-128">Entry point</span></span>

<span data-ttu-id="cf528-129">Blazor Server 应用的入口点在*Program.cs*文件中定义，正如您在控制台应用中看到的。</span><span class="sxs-lookup"><span data-stu-id="cf528-129">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="cf528-130">应用执行时，它使用特定于 Web 应用的默认值创建并运行 Web 主机实例。</span><span class="sxs-lookup"><span data-stu-id="cf528-130">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="cf528-131">Web 主机管理 Blazor Server 应用的生命周期并设置主机级服务。</span><span class="sxs-lookup"><span data-stu-id="cf528-131">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="cf528-132">此类服务的示例包括配置、日志记录、依赖项注入和 HTTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="cf528-132">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="cf528-133">此代码大部分是样板，通常保持不变。</span><span class="sxs-lookup"><span data-stu-id="cf528-133">This code is mostly boilerplate and is often left unchanged.</span></span>

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

<span data-ttu-id="cf528-134">Blazor WebAssembly 应用程序还在*Program.cs*中定义了入口点。</span><span class="sxs-lookup"><span data-stu-id="cf528-134">Blazor WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="cf528-135">代码看起来略有不同。</span><span class="sxs-lookup"><span data-stu-id="cf528-135">The code looks slightly different.</span></span> <span data-ttu-id="cf528-136">代码类似，因为它正在设置应用主机以向应用提供相同的主机级服务。</span><span class="sxs-lookup"><span data-stu-id="cf528-136">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="cf528-137">但是，WebAssembly 应用主机不会设置 HTTP 服务器，因为它直接在浏览器中执行。</span><span class="sxs-lookup"><span data-stu-id="cf528-137">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

<span data-ttu-id="cf528-138">Blazor 应用具有`Startup`一个类而不是*全局.asax*文件来定义应用程序的启动逻辑。</span><span class="sxs-lookup"><span data-stu-id="cf528-138">Blazor apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="cf528-139">该`Startup`类用于配置应用和任何特定于应用的服务。</span><span class="sxs-lookup"><span data-stu-id="cf528-139">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="cf528-140">在 Blazor Server 应用中`Startup`，类用于设置 Blazor 在客户端浏览器和服务器之间使用的实时连接的终结点。</span><span class="sxs-lookup"><span data-stu-id="cf528-140">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="cf528-141">在 Blazor WebAssembly 应用中`Startup`，类定义应用的根组件以及应呈现这些组件的位置。</span><span class="sxs-lookup"><span data-stu-id="cf528-141">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="cf528-142">我们将更深入地了解`Startup`[应用启动](./app-startup.md)部分中的类。</span><span class="sxs-lookup"><span data-stu-id="cf528-142">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="cf528-143">静态文件</span><span class="sxs-lookup"><span data-stu-id="cf528-143">Static files</span></span>

<span data-ttu-id="cf528-144">与 web 窗体项目ASP.NET不同，并非所有 Blazor 项目中的文件都可以请求作为静态文件。</span><span class="sxs-lookup"><span data-stu-id="cf528-144">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="cf528-145">只有*wwwroot*文件夹中的文件是 Web 地址寻址的。</span><span class="sxs-lookup"><span data-stu-id="cf528-145">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="cf528-146">此文件夹将引用到应用程序的"Web 根"。</span><span class="sxs-lookup"><span data-stu-id="cf528-146">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="cf528-147">应用 Web 根之外的任何内容*都无法*Web 寻址。</span><span class="sxs-lookup"><span data-stu-id="cf528-147">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="cf528-148">此设置提供了额外的安全级别，可防止意外在 Web 上公开项目文件。</span><span class="sxs-lookup"><span data-stu-id="cf528-148">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="cf528-149">配置</span><span class="sxs-lookup"><span data-stu-id="cf528-149">Configuration</span></span>

<span data-ttu-id="cf528-150">ASP.NET Web 窗体应用中的配置通常使用一个或多个*Web.config 文件*进行处理。</span><span class="sxs-lookup"><span data-stu-id="cf528-150">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> <span data-ttu-id="cf528-151">Blazor 应用程序通常没有*Web.config*文件。</span><span class="sxs-lookup"><span data-stu-id="cf528-151">Blazor apps don't typically have *web.config* files.</span></span> <span data-ttu-id="cf528-152">如果这样做，则该文件仅用于在 IIS 上托管时配置特定于 IIS 的设置。</span><span class="sxs-lookup"><span data-stu-id="cf528-152">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="cf528-153">相反，Blazor Server 应用使用ASP.NET核心配置抽象（Blazor WebAssembly 应用目前不支持相同的配置抽象，但这可能是将来添加的功能）。</span><span class="sxs-lookup"><span data-stu-id="cf528-153">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="cf528-154">例如，默认的 Blazor Server 应用程序将某些*设置存储在 appsettings.json*中。</span><span class="sxs-lookup"><span data-stu-id="cf528-154">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

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

<span data-ttu-id="cf528-155">我们将在"配置"部分中了解有关ASP.NET核心项目中[的配置](./config.md)。</span><span class="sxs-lookup"><span data-stu-id="cf528-155">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="cf528-156">Razor 组件</span><span class="sxs-lookup"><span data-stu-id="cf528-156">Razor components</span></span>

<span data-ttu-id="cf528-157">布拉佐项目中的大多数文件都是 *.razor*文件。</span><span class="sxs-lookup"><span data-stu-id="cf528-157">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="cf528-158">Razor 是基于 HTML 和 C# 的模板化语言，用于动态生成 Web UI。</span><span class="sxs-lookup"><span data-stu-id="cf528-158">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="cf528-159">*.razor*文件定义构成应用 UI 的组件。</span><span class="sxs-lookup"><span data-stu-id="cf528-159">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="cf528-160">在大多数情况下，布拉佐服务器和 Blazor WebAssembly 应用的组件都是相同的。</span><span class="sxs-lookup"><span data-stu-id="cf528-160">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="cf528-161">Blazor 中的组件类似于ASP.NET Web 窗体中的用户控件。</span><span class="sxs-lookup"><span data-stu-id="cf528-161">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="cf528-162">生成项目时，每个 Razor 组件文件都会编译为 .NET 类。</span><span class="sxs-lookup"><span data-stu-id="cf528-162">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="cf528-163">生成的类捕获组件的状态、呈现逻辑、生命周期方法、事件处理程序和其他逻辑。</span><span class="sxs-lookup"><span data-stu-id="cf528-163">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="cf528-164">我们将介绍使用 Blazor 部分构建[可重用 UI 组件](./components.md)的创作组件。</span><span class="sxs-lookup"><span data-stu-id="cf528-164">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="cf528-165">*_Imports.Razor*文件不是 Razor 组件文件。</span><span class="sxs-lookup"><span data-stu-id="cf528-165">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="cf528-166">相反，它们定义了一组 Razor 指令，以导入到同一文件夹中及其子文件夹中的其他 *.razor*文件中。</span><span class="sxs-lookup"><span data-stu-id="cf528-166">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="cf528-167">例如 *，_Imports.razor*文件是添加`using`常用命名空间语句的传统方法：</span><span class="sxs-lookup"><span data-stu-id="cf528-167">For example, a *_Imports.razor* file is a conventional way to add `using` statements for commonly used namespaces:</span></span>

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

## <a name="pages"></a><span data-ttu-id="cf528-168">页</span><span class="sxs-lookup"><span data-stu-id="cf528-168">Pages</span></span>

<span data-ttu-id="cf528-169">Blazor 应用程序中的页面在哪里？</span><span class="sxs-lookup"><span data-stu-id="cf528-169">Where are the pages in the Blazor apps?</span></span> <span data-ttu-id="cf528-170">Blazor 不会为可寻址页面定义单独的文件扩展名，如 ASP.NET Web 窗体应用中的 *.aspx*文件。</span><span class="sxs-lookup"><span data-stu-id="cf528-170">Blazor doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="cf528-171">相反，页面是通过为组件分配路由来定义的。</span><span class="sxs-lookup"><span data-stu-id="cf528-171">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="cf528-172">路由通常使用`@page`Razor 指令分配。</span><span class="sxs-lookup"><span data-stu-id="cf528-172">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="cf528-173">例如，`Counter`在*Pages/Counter.razor*文件中创作的组件定义了以下路由：</span><span class="sxs-lookup"><span data-stu-id="cf528-173">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="cf528-174">Blazor 中的路由是客户端处理的，而不是服务器上的。</span><span class="sxs-lookup"><span data-stu-id="cf528-174">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="cf528-175">当用户在浏览器中导航时，Blazor 会拦截导航，然后使用匹配的路由呈现组件。</span><span class="sxs-lookup"><span data-stu-id="cf528-175">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="cf528-176">组件路由当前未像使用 *.aspx*页一样由组件的文件位置推断。</span><span class="sxs-lookup"><span data-stu-id="cf528-176">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="cf528-177">此功能将来可能会添加。</span><span class="sxs-lookup"><span data-stu-id="cf528-177">This feature may be added in the future.</span></span> <span data-ttu-id="cf528-178">必须在组件上显式指定每个路由。</span><span class="sxs-lookup"><span data-stu-id="cf528-178">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="cf528-179">在*Pages*文件夹中存储可路由组件没有特殊含义，纯属惯例。</span><span class="sxs-lookup"><span data-stu-id="cf528-179">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="cf528-180">我们将在["页面"、路由和布局](./pages-routing-layouts.md)部分更详细地介绍 Blazor 中的路由。</span><span class="sxs-lookup"><span data-stu-id="cf528-180">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="cf528-181">布局</span><span class="sxs-lookup"><span data-stu-id="cf528-181">Layout</span></span>

<span data-ttu-id="cf528-182">在ASP.NET Web 窗体应用中，使用母版页 *（Site.Master*） 处理常见页面布局。</span><span class="sxs-lookup"><span data-stu-id="cf528-182">In ASP.NET Web Forms apps, common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="cf528-183">在 Blazor 应用中，页面布局使用布局组件 （*共享/MainLayout.razor）* 处理。</span><span class="sxs-lookup"><span data-stu-id="cf528-183">In Blazor apps, page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="cf528-184">布局组件将在[页面、路由和布局](./pages-routing-layouts.md)部分中详细讨论。</span><span class="sxs-lookup"><span data-stu-id="cf528-184">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-blazor"></a><span data-ttu-id="cf528-185">靴子布拉佐尔</span><span class="sxs-lookup"><span data-stu-id="cf528-185">Bootstrap Blazor</span></span>

<span data-ttu-id="cf528-186">要引导 Blazor，应用程序必须：</span><span class="sxs-lookup"><span data-stu-id="cf528-186">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="cf528-187">指定在页面上应呈现根组件 （*App.Razor*） 的位置。</span><span class="sxs-lookup"><span data-stu-id="cf528-187">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="cf528-188">添加相应的 Blazor 框架脚本。</span><span class="sxs-lookup"><span data-stu-id="cf528-188">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="cf528-189">在 Blazor Server 应用中，根组件的主机页在 *_Host.cshtml*文件中定义。</span><span class="sxs-lookup"><span data-stu-id="cf528-189">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="cf528-190">此文件定义剃刀页，而不是组件。</span><span class="sxs-lookup"><span data-stu-id="cf528-190">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="cf528-191">Razor 页面使用 Razor 语法来定义服务器可寻址页面，非常类似于 *.aspx*页面。</span><span class="sxs-lookup"><span data-stu-id="cf528-191">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="cf528-192">该方法`Html.RenderComponentAsync<TComponent>(RenderMode)`用于定义应呈现根级组件的位置。</span><span class="sxs-lookup"><span data-stu-id="cf528-192">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="cf528-193">该`RenderMode`选项指示组件的呈现方式。</span><span class="sxs-lookup"><span data-stu-id="cf528-193">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="cf528-194">下表概述了支持`RenderMode`的选项。</span><span class="sxs-lookup"><span data-stu-id="cf528-194">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="cf528-195">选项</span><span class="sxs-lookup"><span data-stu-id="cf528-195">Option</span></span>                        |<span data-ttu-id="cf528-196">说明</span><span class="sxs-lookup"><span data-stu-id="cf528-196">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="cf528-197">建立与浏览器的连接后以交互方式呈现</span><span class="sxs-lookup"><span data-stu-id="cf528-197">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="cf528-198">首先预渲染，然后以交互方式呈现</span><span class="sxs-lookup"><span data-stu-id="cf528-198">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="cf528-199">呈现为静态内容</span><span class="sxs-lookup"><span data-stu-id="cf528-199">Rendered as static content</span></span>|

<span data-ttu-id="cf528-200">对 *_framework/blazor.server.js*的脚本引用建立与服务器的实时连接，然后处理所有用户交互和 UI 更新。</span><span class="sxs-lookup"><span data-stu-id="cf528-200">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

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

<span data-ttu-id="cf528-201">在 Blazor WebAssembly 应用程序中，主机页是*wwwroot/index.html*下的简单静态 HTML 文件。</span><span class="sxs-lookup"><span data-stu-id="cf528-201">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="cf528-202">该`<app>`元素用于指示应呈现根组件的位置。</span><span class="sxs-lookup"><span data-stu-id="cf528-202">The `<app>` element is used to indicate where the root component should be rendered.</span></span>

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

<span data-ttu-id="cf528-203">要呈现的特定组件在应用`Startup.Configure`的方法中配置，并带有相应的 CSS 选择器，指示应呈现组件的位置。</span><span class="sxs-lookup"><span data-stu-id="cf528-203">The specific component to render is configured in the app's `Startup.Configure` method with a corresponding CSS selector indicating where the component should be rendered.</span></span>

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

## <a name="build-output"></a><span data-ttu-id="cf528-204">生成输出</span><span class="sxs-lookup"><span data-stu-id="cf528-204">Build output</span></span>

<span data-ttu-id="cf528-205">生成 Blazor 项目时，所有 Razor 组件和代码文件都编译到单个程序集中。</span><span class="sxs-lookup"><span data-stu-id="cf528-205">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="cf528-206">与web窗体项目ASP.NET不同，Blazor 不支持 UI 逻辑的运行时编译。</span><span class="sxs-lookup"><span data-stu-id="cf528-206">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="cf528-207">运行应用</span><span class="sxs-lookup"><span data-stu-id="cf528-207">Run the app</span></span>

<span data-ttu-id="cf528-208">要运行 Blazor 服务器应用，`F5`请按可视化工作室。</span><span class="sxs-lookup"><span data-stu-id="cf528-208">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> <span data-ttu-id="cf528-209">Blazor 应用不支持运行时编译。</span><span class="sxs-lookup"><span data-stu-id="cf528-209">Blazor apps don't support runtime compilation.</span></span> <span data-ttu-id="cf528-210">要查看代码和组件标记更改的结果，请重新生成并重新启动应用，并附加调试器。</span><span class="sxs-lookup"><span data-stu-id="cf528-210">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="cf528-211">如果在未附加调试器的情况下运行 （），Visual`Ctrl+F5`Studio 会监视文件更改，并在进行更改时重新启动应用。</span><span class="sxs-lookup"><span data-stu-id="cf528-211">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="cf528-212">在进行更改时，您可以手动刷新浏览器。</span><span class="sxs-lookup"><span data-stu-id="cf528-212">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="cf528-213">要运行 Blazor WebAssembly 应用，请选择以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="cf528-213">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="cf528-214">直接使用开发服务器运行客户端项目。</span><span class="sxs-lookup"><span data-stu-id="cf528-214">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="cf528-215">使用 ASP.NET 核心托管应用时运行服务器项目。</span><span class="sxs-lookup"><span data-stu-id="cf528-215">Run the server project when hosting the app with ASP.NET Core.</span></span>

<span data-ttu-id="cf528-216">Blazor WebAssembly 应用不支持使用可视化工作室进行调试。</span><span class="sxs-lookup"><span data-stu-id="cf528-216">Blazor WebAssembly apps don't support debugging using Visual Studio.</span></span> <span data-ttu-id="cf528-217">要运行应用，请使用`Ctrl+F5`而不是`F5`。</span><span class="sxs-lookup"><span data-stu-id="cf528-217">To run the app, use `Ctrl+F5` instead of `F5`.</span></span> <span data-ttu-id="cf528-218">您可以直接在浏览器中调试 Blazor WebAssembly 应用。</span><span class="sxs-lookup"><span data-stu-id="cf528-218">You can instead debug Blazor WebAssembly apps directly in the browser.</span></span> <span data-ttu-id="cf528-219">有关详细信息[，请参阅调试ASP.NET核心布拉佐尔](/aspnet/core/blazor/debug)。</span><span class="sxs-lookup"><span data-stu-id="cf528-219">See [Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="cf528-220">[上一个](hosting-models.md)
>[下一个](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="cf528-220">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
