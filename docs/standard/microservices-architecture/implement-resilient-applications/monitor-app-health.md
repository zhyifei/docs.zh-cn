---
title: "运行状况监视"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |运行状况监视"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: cbbad72f06bcaa882bc50083d9103b0872f51754
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="health-monitoring"></a>运行状况监视

运行状况监视，则可以允许容器和微服务的状态有关的接近实时的信息。 运行状况监视至关重要的操作系统微服务的多个方面和 orchestrators 在更高版本所述在阶段，执行部分应用升级时尤其重要。

基于微服务的应用程序通常使用的检测信号或运行状况检查，以使其性能监视器、 计划程序时和 orchestrators 能够跟踪多种服务。 如果服务不能发送某种形式的"我已处于活动状态"信号按需或按计划，你的应用程序时部署更新，或它可能只需太迟检测故障并不能停止最终会发生重大中断的级联故障可能会面临风险。

在典型的模型中，服务发送有关其状态报告和聚合该信息，以提供您的应用程序的运行状况状态的总体视图。 如果你使用的 orchestrator，你可以提供到 orchestrator 的群集的运行状况信息，以便群集可以采取相应的措施。 如果你投资高质量运行状况报告自定义的应用程序，可以检测和更加轻松地为你正在运行的应用程序中修复问题。

## <a name="implementing-health-checks-in-aspnet-core-services"></a>ASP.NET Core services 中实现运行状况检查

在开发时 ASP.NET Core 微服务或 web 应用程序，你可以使用通过 ASP.NET 团队在名为 HealthChecks 库。 （截至自 2017 年 1 月，早期版本是可在 GitHub 上）。

此库是易于使用，并提供功能，可让你验证你的应用程序 （如 SQL Server 数据库或远程 API） 所需的任何特定的外部资源正常工作。 当你使用此库时，你可以决定它表示资源是正常的如我们在后面介绍。

若要使用此库，你需要先使用你微服务中的库。 其次，你需要查询前端应用程序的运行状况报告。 前端应用程序可以是自定义 reporting 应用程序，或可能的业务流程本身可以相应地作出反应到运行状况状态。

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a>使用你的后端 ASP.NET 微服务中的 HealthChecks 库

你可以看到如何在 eShopOnContainers 示例应用程序中使用 HealthChecks 库。 若要开始，你需要定义何谓针对每个微服务的正常状态。 在示例应用程序，微服务都可通过 HTTP 和如果其相关的 SQL Server 数据库也是可用来访问 microservice API 是否工作正常。

将来，你将能够作为 NuGet 程序包安装 HealthChecks 库。 但截至撰写本文时，你需要下载并将代码编译为解决方案的一部分。 克隆在 https://github.com/aspnet/HealthChecks 可用的代码并将以下文件夹复制到你的解决方案。

  - src/常用
  - src/Microsoft.AspNetCore.HealthChecks
  - src/Microsoft.Extensions.HealthChecks
  - src/Microsoft.Extensions.HealthChecks.SqlServer

你也可以使用类似的 azure (Microsoft.Extensions.HealthChecks.AzureStorage)，但因为此版本的 eShopOnContainers 在 Azure 上没有任何依赖项的其他检查，不需要它。 因为 eShopOnContainers 基于 ASP.NET Core 不需要 ASP.NET 运行状况检查。

图 10-6 显示在 Visual Studio 中，准备好由任何微服务用作构建基块 HealthChecks 库。

![](./media/image6.png)

**图 10-6**。 ASP.NET： 在 Visual Studio 解决方案核心 HealthChecks library 源代码

因为引入了更早版本，以在每个微服务项目中执行操作的第一个操作是添加对三个 HealthChecks 库的引用。 之后，你可以添加你想要在该微服务中执行的运行状况检查操作。 这些操作基本上是在其他微服务 (HttpUrlCheck) 或数据库上的依赖项 (当前 SqlCheck\*对于 SQL Server 数据库)。 你添加的每个 ASP.NET 微服务或 ASP.NET web 应用程序的启动类中的操作。

应通过将其所有 HTTP 或数据库的依赖项都添加为一个 AddHealthCheck 方法配置每个服务或 web 应用程序。 例如，从 eShopOnContainers MVC web 应用程序依赖于许多服务，因此具有多个 AddCheck 方法添加到运行状况检查。

例如，下面的代码中可以看到如何目录微服务会在其 SQL Server 数据库上添加依赖项。

```csharp
// Startup.cs from Catalog.api microservice
//
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Add framework services
        services.AddHealthChecks(checks =>
        {
            checks.AddSqlCheck("CatalogDb", Configuration["ConnectionString"]);
        });
        // Other services
    }
}
```

但是，eShopOnContainers MVC web 应用程序剩余的微服务上有多个依赖项。 因此，它调用一个 AddUrlCheck 方法为每个微服务，如下面的示例中所示：

```csharp
// Startup.cs from the MVC web app
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();
        services.Configure<AppSettings>(Configuration);
        services.AddHealthChecks(checks =>
        {
            checks.AddUrlCheck(Configuration["CatalogUrl"]);
            checks.AddUrlCheck(Configuration["OrderingUrl"]);
            checks.AddUrlCheck(Configuration["BasketUrl"]);
            checks.AddUrlCheck(Configuration["IdentityUrl"]);
        });
    }
}
```

因此，微服务将不提供"正常"状态，直到所有检查也都处于正常状态。

如果微服务没有依赖关系，在服务上或在 SQL Server 上，你应仅添加 Healthy("Ok") 检查。 下面的代码是从 eShopOnContainers basket.api 微服务。 （篮 microservice 使用 Redis 缓存中，但库尚未包含 Redis 运行状况检查提供程序。）

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

它具有服务或 web 应用程序可通过公开运行状况检查终结点，若要启用 UseHealthChecks (\[*url\_为\_运行状况\_检查*\]) 扩展方法。 此方法将在 WebHostBuilder 级别 ASP.NET 核心服务或 web 应用程序，如下面的代码中所示的 UseKestrel 之后立即程序类的主要方法。

```csharp
namespace Microsoft.eShopOnContainers.WebMVC
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var host = new WebHostBuilder()
                .UseKestrel()
                .UseHealthChecks("/hc")
                .UseContentRoot(Directory.GetCurrentDirectory())
                .UseIISIntegration()
                .UseStartup<Startup>()
                .Build();
            host.Run();
        }
    }
}
```

进程的工作原理如下： 每个微服务公开终结点 /hc。 该终结点是由 HealthChecks 库 ASP.NET Core 中间件创建的。 当调用该终结点时，它将运行 Startup 类的 AddHealthChecks 方法中配置的所有运行状况检查。

UseHealthChecks 方法需要使用一个端口或路径。 该端口或路径是要用于检查服务的运行状况状态的终结点。 例如，目录微服务使用路径 /hc。

### <a name="caching-health-check-responses"></a>缓存的运行状况检查响应

因为你不希望你的服务，导致拒绝服务 (DoS) 或只需不想通过检查资源影响服务性能过于频繁，你可以缓存返回，并配置每个运行状况检查缓存持续时间。

默认情况下，将缓存持续时间内部设置为 5 分钟，但你可以更改该缓存持续时间在每个运行状况检查，如以下代码所示：

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a>查询有关其运行状况状态的报表到你微服务

当你配置了运行状况检查如下所述，在 Docker 中运行的微服务后时，你可以直接检查从浏览器是否正常运行。 （这未需要使你可以通过 localhost 或通过外部的 Docker 主机 IP 访问容器发布外 Docker 主机中，容器端口。）图 10-7 显示在浏览器和相应的响应的请求。

![](./media/image7.png)

**图 10-7**。 正在检查从浏览器单一服务的运行状况状态

在该测试，你可以看到 （在端口 5101 上运行） catalog.api microservice 处于正常状态，在 JSON 中返回 HTTP 200 状态和状态信息。 它还意味着，内部服务还将检查其 SQL Server 数据库依赖项的运行状况和，运行状况检查已其自身报告为正常。

## <a name="using-watchdogs"></a>使用监视器

监视程序是一种单独的服务，可以监视运行状况并通过使用前面介绍的 HealthChecks 库查询加载跨服务和报告有关微服务的运行状况。 这可以帮助防止不会检测基于视图的单个服务的错误。 监视器也是一个好的到可以为无需用户交互的已知条件执行修正操作的宿主代码。

EShopOnContainers 示例包含一个网页，显示示例运行状况检查报告，图 10-8 所示。 这是最简单的监视器，您可以对，因为它只能是显示 eShopOnContainers 微服务和 web 应用程序的状态。 通常，提供监视还执行操作时检测到不正常状态。

![](./media/image8.png)

**图 10-8**。 示例 eShopOnContainers 中的运行状况检查报告

总之，ASP.NET 核心 HealthChecks 库的 ASP.NET 中间件提供每个微服务构成的单个运行状况检查终结点。 这将执行在其中定义的所有运行状况检查，并返回具体取决于所有这些检查的总体运行状况状态。

HealthChecks 库是可扩展的将来的外部资源的新运行状况检查通过。 例如，我们预期，通过在将来库将具有的 Redis 缓存和其他数据库的运行状况检查。 库允许运行状况报告多个服务或应用程序依赖关系，然后可以执行基于这些运行状况检查的操作。

## <a name="health-checks-when-using-orchestrators"></a>使用 orchestrators 时的运行状况检查

若要监视你微服务的可用性，orchestrators Docker Swarm、 等 Kubernetes，Service Fabric 将定期通过发送请求以测试微服务执行运行状况检查。 当 orchestrator 确定服务/容器不正常，则它会停止请求路由到该实例。 它通常还会创建该容器的新实例。

例如，大多数 orchestrators 可以使用运行状况检查用于管理零停机时间部署。 仅当服务/容器更改为正常的状态将 orchestrator 开始将流量路由到服务/容器实例。

当 orchestrator 执行应用程序升级时，运行状况监视一点尤其重要。 （如 Azure Service Fabric) 某些 orchestrators 更新中的服务阶段 — 例如，它们可能会更新每个应用程序升级的群集表面 1 / 5。 在同一时间升级的节点集称为*升级域*。 每个升级域已升级，并可供用户后，该升级域必须通过运行状况检查，然后部署将移到下一个升级域。

另一个方面，服务的运行状况报告从服务的度量值。 这是某些 orchestrators，Service Fabric 等的运行状况模型的一个高级的功能。 当使用 orchestrator，因为它们用于平衡资源使用情况时，度量值很重要。 度量值也可以是的系统运行状况指示符。 例如，你可能必须具有许多微服务的应用程序和每个实例报告请求每秒 (RPS) 度量值。 如果一个服务使用比另一个服务的更多资源 （内存、 处理器等），orchestrator 无法服务实例中移动群集尝试维护甚至资源利用率。

请注意，是否你使用 Azure Service Fabric，它提供其自己[运行状况监视模型](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)，这是更高级比简单的运行状况检查。

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a>高级监视： 可视化效果、 分析和警报

监视的最后一部分直观显示的事件流，对服务性能，报告和警报时检测到的问题。 此方面的监视，你可以使用不同的解决方案。

你可以使用显示你的服务的状态的简单自定义应用程序，如自定义页上，我们介绍了当我们介绍了[ASP.NET 核心 HealthChecks](https://github.com/aspnet/HealthChecks)。 或者，可以使用更高级的工具，如 Azure Application Insights 和 Operations Management Suite 发出警报基于事件的流。

最后，如果你已存储的所有事件流，你可以使用 Microsoft Power BI 或 Kibana 或 Splunk 之类的第三方解决方案来实现数据可视化效果。

## <a name="additional-resources"></a>其他资源

-   **ASP.NET 核心 HealthChecks** （早期发行版） [ *https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)

-   **Service Fabric 运行状况监视简介**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)

-   **Azure 的 Application Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)

-   **Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)

>[!div class="step-by-step"]
[以前](实现的线路的断路器-pattern.md) [下一步] (.../secure-net-microservices-web-applications/index.md)
