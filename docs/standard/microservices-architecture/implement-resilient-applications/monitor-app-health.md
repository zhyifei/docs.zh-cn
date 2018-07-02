---
title: 运行状况监视
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 运行状况监视
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 62d4e9a26710a5c4b191287bf76192972f7e991b
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106536"
---
# <a name="health-monitoring"></a>运行状况监视

运行状况监视可以获取有关容器和微服务状态的近实时信息。 运行状况对于微服务操作的多个方面至关重要，并且在业务流程协调程序分阶段执行部分应用程序升级时尤为重要，稍后将对此进行说明。

通常，基于微服务的应用程序借助检测信号或运行状况检查，使性能监视器、日程安排和业务流程协调程序得以对大量服务进行跟踪监测。 如果服务无法按需或按计划发送某种表示“我处于活动状态”的信号，那么部署更新时，应用程序可能面临风险，或者它可能较晚发现故障，并且无法阻止可能会导致重大故障的级联故障。

在典型模型中，服务发送有关其状态的报告，聚合这些信息便能整体了解应用程序运行状况。 如果使用的是业务流程协调程序，则可以向业务流程协调程序的群集提供运行状况信息，以便群集可以执行相应操作。 如果使用为应用程序定制的高质量运行状况报告，则可以更轻松地检测到正在运行的应用程序存在的问题并进行修复。

## <a name="implementing-health-checks-in-aspnet-core-services"></a>在 ASP.NET Core 服务中实现运行状况检查

部署 ASP.NET Core 微服务或 Web 应用程序时，可以使用 ASP.NET 团队中名为 `HealthChecks` 的带外库（非正式属于 ASP.NETCore 的部分）。 可在此 [GitHub 存储库](https://github.com/dotnet-architecture/HealthChecks)中找到。

该库使用方便，并提供了一些功能，可以用于验证应用程序（如 SQL Server 数据库或远程 API）所需的任何特定外部资源是否正常工作。 使用该库时，还可以确定资源正常运行的定义，稍后将会介绍。

为了使用该库，首先需要在微服务中使用此库。 其次，需要查询运行状况报告的前端应用程序。 该前端应用程序可能是自定义报告应用程序，也可能是可以根据运行状态做出相应反应的业务流程协调程序。

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a>在后端 ASP.NET 微服务中使用 HealthChecks 库

可以查看 HealthChecks 库在 eShopOnContainers 示例应用程序中的使用情况。 首先，需要定义每个微服务的正常运行状况的必备条件。 在该示例应用程序中，如果可通过 HTTP 访问微服务 API 并且可以使用与其相关的 SQL Server 数据库，则该微服务的处于正常运行状态。

之后，可以将 HealthChecks 库作为 NuGet 包进行安装。 但截至本文撰写时，解决方案还需下载并编译代码。 克隆 https://github.com/dotnet-architecture/HealthChecks 中可用的代码，并将以下文件夹复制到解决方案：

  - src/common
  - src/Microsoft.AspNetCore.HealthChecks
  - src/Microsoft.Extensions.HealthChecks
  - src/Microsoft.Extensions.HealthChecks.SqlServer

还可以使用附加检查（如针对 Azure 的 Microsoft.Extensions.HealthChecks.AzureStorage），但由于此版本的 eShopOnContainers 在 Azure 上没有任何依赖项，所以不需要附加检查。 因为 eShopOnContainers 是基于 ASP.NET Core 的，所以不需要 ASP.NET 运行状况检查。

图 10-6 显示 Visual Studio 中的 HealthChecks 库，任何微服务均可以将该库用作构建基块。

![](./media/image6.png)

图 10-6。 Visual Studio 解决方案中的 ASP.NET Core HealthChecks 库源代码

如前所述，在每个微服务项目中要做的第一件事就是添加对这三个 HealthChecks 库的应用。 然后，添加要在该微服务中执行的运行状况检查操作。 这些操作基本上是其他微服务 (HttpUrlCheck) 或数据库（目前用于 SQL Server 数据库的 SqlCheck\*）上的依赖项。 在每个 ASP.NET 微服务或 ASP.NET Web 应用程序的 Startup 类中添加该操作。

应该将每个服务或 Web 应用程序的所有 HTTP 或数据库依赖项添加为一个 AddHealthCheck 方法，从而对其进行配置。 例如，eShopOnContainers 的 MVC Web 应用程序依赖于多个服务，因此该应用程序的运行状况检查中需添加多个 AddCheck 方法。

例如，通过以下代码，可以了解 catalog 微服务如何添加其 SQL Server 数据库上的依赖项。

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

但是，eShopOnContainers 的 MVC Web 应用程序具有多个对其他微服务的依赖项。 因此，它为每个微服务调用一个 AddUrlCheck 方法，如以下示例所示：

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

所以，在微服务的所有检查均处于正常状态后，该微服务才会显示为“正常运行”状态。

如果微服务没有对服务或 SQL Server 的依赖项，则只需添加正常运行("Ok") 检查。 以下代码来自 eShopOnContainers basket.api 微服务。 （basket 微服务使用 Redis 缓存，但是库中尚未包含 Redis 运行状况检查提供程序。）

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

为了使服务或 Web 应用程序公开运行状况检查终结点，必须启用 UseHealthChecks(\[url\_for\_health\_checks\]) 扩展方法。 如以下代码所示，该方法紧随 UseKestrel 之后，在 ASP.NET Core 服务或 Web 应用程序的 Program 类主要方法中以 WebHostBuilder 级别使用。

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

该进程运行如下：每个微服务公开终结点 /hc。 该终结点乃 HealthChecks 库 ASP.NET Core 中间件所创建。 调用该终结点时，它将运行 Startup 类的 AddHealthChecks 方法中配置的所有运行状况检查。

UseHealthChecks 方法需要一个端口或路径。 该端口或路径是用于检查服务的运行状况状态的终结点。 例如，catalog 微服务便是使用路径 /hc。

### <a name="caching-health-check-responses"></a>缓存运行状况检查的响应结果

由于不希望在服务中引发拒绝服务 (DoS)，或不想因为频繁检查资源而影响服务性能，则可以缓存返回结果并为每个运行状况检查配置缓存持续时间。

默认情况下，缓存持续时间在内部设置为 5 分钟，但可以更改每个运行状况检查的缓存持续时间，如以下代码所示：

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a>查询微服务，报告其运行状况信息

按照本文所述配置好运行状况检查后，每当在 Docker 上运行该微服务，便可直接通过浏览器检查其运行状况是否正常。 （这要求从 Docker 主机中发布容器端口，以便通过本地主机或外部 Docker 主机 IP 访问该容器。）图 10-7 显示浏览器中的请求以及相应的响应。

![](./media/image7.png)

图 10-7。 通过浏览器检查单个服务的运行状况状态

在该测试中，可以看到 catalog.api 微服务（在端口 5101 上运行）处于正常运行状态，并以 JSON 形式返回 HTTP 状态 200 和状态信息。 这也表示该服务在内部检查了其 SQL Server 数据库依赖项的运行状况，并且运行状况检查报告显示其运行正常。

## <a name="using-watchdogs"></a>使用监视程序

监视程序是一项单独服务，可以监视多个服务的运行和负载状况，并借助前面介绍的 HealthChecks 库进行查询，从而报告微服务的运行状况。 这有助于防止某些根据单个服务视图检测不到的错误。 监视程序也是托管代码的好选择，可以在没有用户交互的情况下根据已知情况执行修正操作。

eShopOnContainers 示例包含一个网页，该网页显示了示例运行状况检查报告，如图 10-8 所示。 这是最简单的监视程序，因为它只显示 eShopOnContainers 中的微服务和 Web 应用程序的状态。 通常，监视程序在检测到不正常运行状态时还会执行相应操作。

![](./media/image8.png)

图 10-8。 eShopOnContainers 中的示例运行状况检查报告

总而言之，ASP.NET Core HealthChecks 库的 ASP.NET 中间件为每个微服务提供了单个运行状况检查终结点。 这将执行其中定义的所有运行状况检查，并根据这些检查返回总体运行状况状态。

通过对将来的外部资源执行新的运行状况检查，可扩展 HealthChecks 库。 例如，我们预计，将来该库中会具有针对 Redis 缓存和其他数据库的运行状况检查。 该库能够报告多个服务或应用程序依赖项的运行状况，用户随后可以根据这些运行状况检查采取相应操作。

## <a name="health-checks-when-using-orchestrators"></a>在使用业务流程协调程序的情况下执行运行状况检查

若要监视微服务的可用性，Docker Swarm、Kubernetes 和 Service Fabric 等业务流程协调程序可通过发送微服务测试请求来定期执行运行状况检查。 若业务流程协调程序确定某服务/容器运行不正常，它会停止向该实例路由请求。 通常，它还会为该容器创建新实例。

例如，大多数业务流程协调程序可以使用运行状况检查来管理不会停机的部署。 仅当服务/容器的状态变为正常时，业务流程协调程序才会开始将流量路由到服务/容器实例。

当业务流程协调程序执行应用程序升级时，运行状况监视尤为重要。 某些业务流程协调程序（如 Azure Service Fabric）会分阶段更新服务，例如，它们可能为每个应用程序升级更新五分之一的群集面。 同时升级的一组节点称为升级域。 完成每个升级域的升级操作并面向用户提供后，在部署进程移至下一升级域之前，该升级域必须通过运行状况检查。

服务运行状况的另一方面是报告服务的指标。 这是某些业务流程协调程序（如 Service Fabric）运行状况模型的高级功能。 因为要借助指标来平衡资源使用情况，所以在使用业务流程协调程序时，指标非常重要。 指标也可以是系统运行状况的指示器。 例如，某个应用程序包含多个微服务，并且每个实例都会报告每秒的请求数 (RPS) 指标。 如果某一服务使用的资源（内存、处理器等）比另一个服务多，则业务流程协调程序会在群集中移动服务实例，尝试使资源使用保持均衡状态。

请注意，如果正在使用 Azure Service Fabric，它会提供自己的[运行状况监视模型](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)，该模型比简单的运行状况检查更高级。

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a>高级监视：可视化、分析和警报

监视的最后一部分是对事件流进行可视化、报告服务性能、以及在检测到问题时发出警报。 可以使用不同的解决方案来进行这方面的监视。

可以使用显示服务状态的简单自定义应用程序，例如介绍 [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks) 时显示的自定义页。 或者，可以使用更高级的工具（如 Azure Application Insights 和 Operations Management Suite）来根据事件流发出警报。

最后，如果要存储所有事件流，可以使用 Microsoft Power BI 或第三方解决方案（如 Kibana 或 Splunk）来可视化数据。

## <a name="additional-resources"></a>其他资源

-   **ASP.NET Core HealthChecks**（早期版本）[*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)

-   **Service Fabric 运行状况监视简介**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)

-   **Azure Application Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)

-   **Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)

>[!div class="step-by-step"]
[上一页](implement-circuit-breaker-pattern.md)
[下一页](../secure-net-microservices-web-applications/index.md)
