---
title: 运行状况监视
description: 了解实现运行状况监视的一种方法。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/16/2018
ms.openlocfilehash: 666b55608ca4e5d18448e1a0b4a1735f3e856474
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362478"
---
# <a name="health-monitoring"></a><span data-ttu-id="39a05-103">运行状况监视</span><span class="sxs-lookup"><span data-stu-id="39a05-103">Health monitoring</span></span>

<span data-ttu-id="39a05-104">运行状况监视可以获取有关容器和微服务状态的近实时信息。</span><span class="sxs-lookup"><span data-stu-id="39a05-104">Health monitoring can allow near-real-time information about the state of your containers and microservices.</span></span> <span data-ttu-id="39a05-105">运行状况对于微服务操作的多个方面至关重要，并且在业务流程协调程序分阶段执行部分应用程序升级时尤为重要，稍后将对此进行说明。</span><span class="sxs-lookup"><span data-stu-id="39a05-105">Health monitoring is critical to multiple aspects of operating microservices and is especially important when orchestrators perform partial application upgrades in phases, as explained later.</span></span>

<span data-ttu-id="39a05-106">通常，基于微服务的应用程序借助检测信号或运行状况检查，使性能监视器、日程安排和业务流程协调程序得以对大量服务进行跟踪监测。</span><span class="sxs-lookup"><span data-stu-id="39a05-106">Microservices-based applications often use heartbeats or health checks to enable their performance monitors, schedulers, and orchestrators to keep track of the multitude of services.</span></span> <span data-ttu-id="39a05-107">如果服务无法按需或按计划发送某种表示“我处于活动状态”的信号，那么部署更新时，应用程序可能面临风险，或者它可能太晚才发现故障，并且无法阻止可能会导致重大故障的级联故障。</span><span class="sxs-lookup"><span data-stu-id="39a05-107">If services cannot send some sort of “I’m alive” signal, either on demand or on a schedule, your application might face risks when you deploy updates, or it might just detect failures too late and not be able to stop cascading failures that can end up in major outages.</span></span>

<span data-ttu-id="39a05-108">在典型模型中，服务发送有关其状态的报告，聚合这些信息便能整体了解应用程序运行状况。</span><span class="sxs-lookup"><span data-stu-id="39a05-108">In the typical model, services send reports about their status, and that information is aggregated to provide an overall view of the state of health of your application.</span></span> <span data-ttu-id="39a05-109">如果使用的是业务流程协调程序，则可以向业务流程协调程序的群集提供运行状况信息，以便群集可以执行相应操作。</span><span class="sxs-lookup"><span data-stu-id="39a05-109">If you're using an orchestrator, you can provide health information to your orchestrator’s cluster, so that the cluster can act accordingly.</span></span> <span data-ttu-id="39a05-110">如果使用为应用程序定制的高质量运行状况报告，则可以更轻松地检测到正在运行的应用程序存在的问题并进行修复。</span><span class="sxs-lookup"><span data-stu-id="39a05-110">If you invest in high-quality health reporting that's customized for your application, you can detect and fix issues for your running application much more easily.</span></span>

## <a name="implement-health-checks-in-aspnet-core-services"></a><span data-ttu-id="39a05-111">在 ASP.NET Core 服务中实现运行状况检查</span><span class="sxs-lookup"><span data-stu-id="39a05-111">Implement health checks in ASP.NET Core services</span></span>

<span data-ttu-id="39a05-112">部署 ASP.NET Core 微服务或 Web 应用程序时，可以使用 ASP.NET 团队中名为“Health Checks”的实验性带外库（非正式属于 ASP.NETCore 的部分，现已弃用）。</span><span class="sxs-lookup"><span data-stu-id="39a05-112">When developing an ASP.NET Core microservice or web application, you can use an experimental out-of-band library (not official as part of ASP.NETCore and now deprecated) named *Health Checks* from the ASP.NET team.</span></span> <span data-ttu-id="39a05-113">可在此 [dotnet-architecture GitHub 存储库](https://github.com/dotnet-architecture/HealthChecks)中获得。</span><span class="sxs-lookup"><span data-stu-id="39a05-113">It's available at this [dotnet-architecture GitHub repository](https://github.com/dotnet-architecture/HealthChecks).</span></span> <span data-ttu-id="39a05-114">而“Health Checks”的正式版[将在 ASP.NET Core 2.2 中发布](https://github.com/aspnet/Announcements/issues/307)（应于 2018 年年底正式发布）。</span><span class="sxs-lookup"><span data-stu-id="39a05-114">However, the official version of *Health Checks* [will be released in ASP.NET Core 2.2](https://github.com/aspnet/Announcements/issues/307) (Should be officially released by the end of 2018).</span></span>

<span data-ttu-id="39a05-115">该库使用方便，并提供了一些功能，可以用于验证应用程序（如 SQL Server 数据库或远程 API）所需的任何特定外部资源是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="39a05-115">This library is easy to use and provides features that let you validate that any specific external resource needed for your application (like a SQL Server database or remote API) is working properly.</span></span> <span data-ttu-id="39a05-116">使用该库时，还可以确定资源正常运行的定义，稍后将会介绍。</span><span class="sxs-lookup"><span data-stu-id="39a05-116">When you use this library, you can also decide what it means that the resource is healthy, as we explain later.</span></span>

<span data-ttu-id="39a05-117">为了使用该库，首先需要在微服务中使用此库。</span><span class="sxs-lookup"><span data-stu-id="39a05-117">In order to use this library, you need to first use the library in your microservices.</span></span> <span data-ttu-id="39a05-118">其次，需要查询运行状况报告的前端应用程序。</span><span class="sxs-lookup"><span data-stu-id="39a05-118">Second, you need a front-end application that queries for the health reports.</span></span> <span data-ttu-id="39a05-119">该前端应用程序可能是自定义报告应用程序，也可能是可以根据运行状况状态做出相应反应的业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="39a05-119">That front-end application could be a custom reporting application, or it could be an orchestrator itself that can react accordingly to the health states.</span></span>

### <a name="use-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a><span data-ttu-id="39a05-120">在后端 ASP.NET 微服务中使用 HealthChecks 库</span><span class="sxs-lookup"><span data-stu-id="39a05-120">Use the HealthChecks library in your back-end ASP.NET microservices</span></span>

<span data-ttu-id="39a05-121">可以查看 HealthChecks 库在 eShopOnContainers 示例应用程序中的使用情况。</span><span class="sxs-lookup"><span data-stu-id="39a05-121">You can see how the HealthChecks library is used in the eShopOnContainers sample application.</span></span> <span data-ttu-id="39a05-122">首先，需要定义每个微服务的正常运行状况的必备条件。</span><span class="sxs-lookup"><span data-stu-id="39a05-122">To begin, you need to define what constitutes a healthy status for each microservice.</span></span> <span data-ttu-id="39a05-123">在该示例应用程序中，如果可通过 HTTP 访问微服务 API 并且可以使用与其相关的 SQL Server 数据库，则该微服务的处于正常运行状态。</span><span class="sxs-lookup"><span data-stu-id="39a05-123">In the sample application, the microservices are healthy if the microservice API is accessible via HTTP and if its related SQL Server database is also available.</span></span>

<span data-ttu-id="39a05-124">之后，可以将 HealthChecks 库作为 NuGet 包进行安装。</span><span class="sxs-lookup"><span data-stu-id="39a05-124">In the future, you'll be able to install the HealthChecks library as a NuGet package.</span></span> <span data-ttu-id="39a05-125">但截至本文撰写时，解决方案还需下载并编译代码。</span><span class="sxs-lookup"><span data-stu-id="39a05-125">But as of this writing, you need to download and compile the code as part of your solution.</span></span> <span data-ttu-id="39a05-126">克隆 <https://github.com/dotnet-architecture/HealthChecks> 中可用的代码，并将以下文件夹复制到解决方案：</span><span class="sxs-lookup"><span data-stu-id="39a05-126">Clone the code available at <https://github.com/dotnet-architecture/HealthChecks> and copy the following folders to your solution:</span></span>

- <span data-ttu-id="39a05-127">src/common</span><span class="sxs-lookup"><span data-stu-id="39a05-127">src/common</span></span>
- <span data-ttu-id="39a05-128">src/Microsoft.AspNetCore.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="39a05-128">src/Microsoft.AspNetCore.HealthChecks</span></span>
- <span data-ttu-id="39a05-129">src/Microsoft.Extensions.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="39a05-129">src/Microsoft.Extensions.HealthChecks</span></span>
- <span data-ttu-id="39a05-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span><span class="sxs-lookup"><span data-stu-id="39a05-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span></span>

<span data-ttu-id="39a05-131">还可以使用附加检查（如针对 Azure 的 Microsoft.Extensions.HealthChecks.AzureStorage），但由于此版本的 eShopOnContainers 在 Azure 上没有任何依赖项，所以不需要附加检查。</span><span class="sxs-lookup"><span data-stu-id="39a05-131">You could also use additional checks like the ones for Azure (Microsoft.Extensions.HealthChecks.AzureStorage), but since this version of eShopOnContainers does not have any dependency on Azure, you do not need it.</span></span> <span data-ttu-id="39a05-132">因为 eShopOnContainers 是基于 ASP.NET Core 的，所以不需要 ASP.NET 运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="39a05-132">You do not need the ASP.NET health checks, because eShopOnContainers is based on ASP.NET Core.</span></span>

<span data-ttu-id="39a05-133">图 8-7 显示 Visual Studio 中的 HealthChecks 库，任何微服务均可以将该库用作构建基块。</span><span class="sxs-lookup"><span data-stu-id="39a05-133">Figure 8-7 shows the HealthChecks library in Visual Studio, ready to be used as a building block by any microservices.</span></span>

![HealthChecks 文件夹的解决方案资源管理器视图，其中显示三个项目。](./media/image6.png)

<span data-ttu-id="39a05-135">**图 8-7**。</span><span class="sxs-lookup"><span data-stu-id="39a05-135">**Figure 8-7**.</span></span> <span data-ttu-id="39a05-136">Visual Studio 解决方案中的 ASP.NET Core HealthChecks 库源代码</span><span class="sxs-lookup"><span data-stu-id="39a05-136">ASP.NET Core HealthChecks library source code in a Visual Studio solution</span></span>

<span data-ttu-id="39a05-137">如前所述，在每个微服务项目中要做的第一件事就是添加对这三个 HealthChecks 库的应用。</span><span class="sxs-lookup"><span data-stu-id="39a05-137">As introduced earlier, the first thing to do in each microservice project is to add a reference to the three HealthChecks libraries.</span></span> <span data-ttu-id="39a05-138">然后，添加要在该微服务中执行的运行状况检查操作。</span><span class="sxs-lookup"><span data-stu-id="39a05-138">After that, you add the health check actions that you want to perform in that microservice.</span></span> <span data-ttu-id="39a05-139">这些操作基本上是其他微服务 (HttpUrlCheck) 或数据库（目前用于 SQL Server 数据库的 SqlCheck\*）上的依赖项。</span><span class="sxs-lookup"><span data-stu-id="39a05-139">These actions are basically dependencies on other microservices (HttpUrlCheck) or databases (currently SqlCheck\* for SQL Server databases).</span></span> <span data-ttu-id="39a05-140">在每个 ASP.NET 微服务或 ASP.NET Web 应用程序的 Startup 类中添加该操作。</span><span class="sxs-lookup"><span data-stu-id="39a05-140">You add the action within the Startup class of each ASP.NET microservice or ASP.NET web application.</span></span>

<span data-ttu-id="39a05-141">应该将每个服务或 Web 应用程序的所有 HTTP 或数据库依赖项添加为一个 AddHealthCheck 方法，从而对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="39a05-141">Each service or web application should be configured by adding all its HTTP or database dependencies as one AddHealthCheck method.</span></span> <span data-ttu-id="39a05-142">例如，eShopOnContainers 的 MVC Web 应用程序依赖于多个服务，因此该应用程序的运行状况检查中需添加多个 AddCheck 方法。</span><span class="sxs-lookup"><span data-stu-id="39a05-142">For example, the MVC web application from eShopOnContainers depends on many services, therefore has several AddCheck methods added to the health checks.</span></span>

<span data-ttu-id="39a05-143">例如，通过以下（简化）代码，可以了解 catalog 微服务如何在其 SQL Server 数据库上添加依赖项。</span><span class="sxs-lookup"><span data-stu-id="39a05-143">For instance, in the following (simplified) code you can see how the catalog microservice adds a dependency on its SQL Server database.</span></span>

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

<span data-ttu-id="39a05-144">但是，eShopOnContainers 的 MVC Web 应用程序具有多个对其他微服务的依赖项。</span><span class="sxs-lookup"><span data-stu-id="39a05-144">However, the MVC web application of eShopOnContainers has multiple dependencies on the rest of the microservices.</span></span> <span data-ttu-id="39a05-145">因此，它为每个微服务调用一个 AddUrlCheck 方法，如以下（简化）示例所示：</span><span class="sxs-lookup"><span data-stu-id="39a05-145">Therefore, it calls one AddUrlCheck method for each microservice, as shown in the following (simplified) example:</span></span>

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

<span data-ttu-id="39a05-146">所以，在微服务的所有检查均处于正常状态后，该微服务才会显示为“正常运行”状态。</span><span class="sxs-lookup"><span data-stu-id="39a05-146">Thus, a microservice will not provide a “healthy” status until all its checks are healthy as well.</span></span>

<span data-ttu-id="39a05-147">如果微服务没有对服务或 SQL Server 的依赖项，则只需添加正常运行("Ok") 检查。</span><span class="sxs-lookup"><span data-stu-id="39a05-147">If the microservice does not have a dependency on a service or on SQL Server, you should just add a Healthy("Ok") check.</span></span> <span data-ttu-id="39a05-148">以下代码来自 eShopOnContainers `basket.api` 微服务。</span><span class="sxs-lookup"><span data-stu-id="39a05-148">The following code is from the eShopOnContainers `basket.api` microservice.</span></span> <span data-ttu-id="39a05-149">（basket 微服务使用 Redis 缓存，但是库中尚未包含 Redis 运行状况检查提供程序。）</span><span class="sxs-lookup"><span data-stu-id="39a05-149">(The basket microservice uses the Redis cache, but the library does not yet include a Redis health check provider.)</span></span>

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

<span data-ttu-id="39a05-150">为了使服务或 Web 应用程序公开运行状况检查终结点，必须启用 `UseHealthChecks([*url_for_health_checks*])` 扩展方法。</span><span class="sxs-lookup"><span data-stu-id="39a05-150">For a service or web application to expose the health check endpoint, it has to enable the `UseHealthChecks([*url_for_health_checks*])` extension method.</span></span> <span data-ttu-id="39a05-151">如以下简化代码所示，该方法紧随 <xref:Microsoft.AspNetCore.WebHost.CreateDefaultBuilder> 之后，在 ASP.NET Core 服务或 Web 应用程序的 `Program` 类主要方法中以 `WebHostBuilder` 级别使用：</span><span class="sxs-lookup"><span data-stu-id="39a05-151">This method goes at the `WebHostBuilder` level in the main method of the `Program` class of your ASP.NET Core service or web application, right after <xref:Microsoft.AspNetCore.WebHost.CreateDefaultBuilder> as shown in the following simplified code:</span></span>

```csharp
namespace Microsoft.eShopOnContainers.WebMVC
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var host = WebHost.CreateDefaultBuilder(args)
                .UseHealthChecks("/hc")
                .UseContentRoot(Directory.GetCurrentDirectory())
                .UseStartup<Startup>()
                .Build();

            host.Run();
        }
    }
}
```

<span data-ttu-id="39a05-152">该进程运行如下：每个微服务公开终结点 /hc。</span><span class="sxs-lookup"><span data-stu-id="39a05-152">The process works this way: each microservice exposes the endpoint /hc.</span></span> <span data-ttu-id="39a05-153">该终结点乃 HealthChecks 库 ASP.NET Core 中间件所创建。</span><span class="sxs-lookup"><span data-stu-id="39a05-153">That endpoint is created by the HealthChecks library ASP.NET Core middleware.</span></span> <span data-ttu-id="39a05-154">调用该终结点时，它将运行 Startup 类的 AddHealthChecks 方法中配置的所有运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="39a05-154">When that endpoint is invoked, it runs all the health checks that are configured in the AddHealthChecks method in the Startup class.</span></span>

<span data-ttu-id="39a05-155">UseHealthChecks 方法需要一个端口或路径。</span><span class="sxs-lookup"><span data-stu-id="39a05-155">The UseHealthChecks method expects a port or a path.</span></span> <span data-ttu-id="39a05-156">该端口或路径是用于检查服务的运行状况状态的终结点。</span><span class="sxs-lookup"><span data-stu-id="39a05-156">That port or path is the endpoint to use to check the health state of the service.</span></span> <span data-ttu-id="39a05-157">例如，catalog 微服务便是使用路径 /hc。</span><span class="sxs-lookup"><span data-stu-id="39a05-157">For instance, the catalog microservice uses the path /hc.</span></span>

### <a name="cache-health-check-responses"></a><span data-ttu-id="39a05-158">缓存运行状况检查的响应结果</span><span class="sxs-lookup"><span data-stu-id="39a05-158">Cache health check responses</span></span>

<span data-ttu-id="39a05-159">由于不希望在服务中引发拒绝服务 (DoS)，或不想因为频繁检查资源而影响服务性能，则可以缓存返回结果并为每个运行状况检查配置缓存持续时间。</span><span class="sxs-lookup"><span data-stu-id="39a05-159">Since you do not want to cause a Denial of Service (DoS) in your services, or you simply do not want to impact service performance by checking resources too frequently, you can cache the returns and configure a cache duration for each health check.</span></span>

<span data-ttu-id="39a05-160">默认情况下，缓存持续时间在内部设置为 5 分钟，但可以更改每个运行状况检查的缓存持续时间，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="39a05-160">By default, the cache duration is internally set to 5 minutes, but you can change that cache duration on each health check, as in the following code:</span></span>

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="query-your-microservices-to-report-about-their-health-status"></a><span data-ttu-id="39a05-161">查询微服务，以报告其运行状况状态</span><span class="sxs-lookup"><span data-stu-id="39a05-161">Query your microservices to report about their health status</span></span>

<span data-ttu-id="39a05-162">按照本文所述配置好运行状况检查后，每当在 Docker 上运行该微服务，便可直接通过浏览器检查其运行状况是否正常。</span><span class="sxs-lookup"><span data-stu-id="39a05-162">When you've configured health checks as described in this article and you have the microservice running in Docker, you can directly check from a browser if it's healthy.</span></span>

<span data-ttu-id="39a05-163">必须在 Docker 主机中发布容器端口，以便通过外部 Docker 主机 IP 或 `localhost` 访问该容器，如图 8-8 所示。</span><span class="sxs-lookup"><span data-stu-id="39a05-163">You have to publish the container port in the Docker host, so you can access the container through the external Docker host IP or through `localhost`, as shown in figure 8-8.</span></span>

![运行状况检查返回的 JSON 响应的浏览器视图](./media/image7.png)

<span data-ttu-id="39a05-165">**图 8-8**。</span><span class="sxs-lookup"><span data-stu-id="39a05-165">**Figure 8-8**.</span></span> <span data-ttu-id="39a05-166">通过浏览器检查单个服务的运行状况状态</span><span class="sxs-lookup"><span data-stu-id="39a05-166">Checking health status of a single service from a browser</span></span>

<span data-ttu-id="39a05-167">在该测试中，可以看到 catalog.api 微服务（在端口 5101 上运行）处于正常运行状态，并以 JSON 形式返回 HTTP 状态 200 和状态信息。</span><span class="sxs-lookup"><span data-stu-id="39a05-167">In that test, you can see that the catalog.api microservice (running on port 5101) is healthy, returning HTTP status 200 and status information in JSON.</span></span> <span data-ttu-id="39a05-168">这也表示该服务在内部检查了其 SQL Server 数据库依赖项的运行状况，并且运行状况检查报告显示其运行正常。</span><span class="sxs-lookup"><span data-stu-id="39a05-168">It also means that internally the service also checked the health of its SQL Server database dependency and that health check was reported itself as healthy.</span></span>

## <a name="use-watchdogs"></a><span data-ttu-id="39a05-169">使用监视程序</span><span class="sxs-lookup"><span data-stu-id="39a05-169">Use watchdogs</span></span>

<span data-ttu-id="39a05-170">监视程序是一项单独服务，可以监视多个服务的运行和负载状况，并借助前面介绍的 `HealthChecks` 库进行查询，从而报告微服务的运行状况。</span><span class="sxs-lookup"><span data-stu-id="39a05-170">A watchdog is a separate service that can watch health and load across services, and report health about the microservices by querying with the `HealthChecks` library introduced earlier.</span></span> <span data-ttu-id="39a05-171">这有助于防止某些根据单个服务视图检测不到的错误。</span><span class="sxs-lookup"><span data-stu-id="39a05-171">This can help prevent errors that would not be detected based on the view of a single service.</span></span> <span data-ttu-id="39a05-172">监视程序也是托管代码的好选择，可以在没有用户交互的情况下根据已知情况执行修正操作。</span><span class="sxs-lookup"><span data-stu-id="39a05-172">Watchdogs also are a good place to host code that can perform remediation actions for known conditions without user interaction.</span></span>

<span data-ttu-id="39a05-173">eShopOnContainers 示例包含一个网页，该网页显示了示例运行状况检查报告，如图 8-9 所示。</span><span class="sxs-lookup"><span data-stu-id="39a05-173">The eShopOnContainers sample contains a web page that displays sample health check reports, as shown in Figure 8-9.</span></span> <span data-ttu-id="39a05-174">这是最简单的监视程序，因为它只显示 eShopOnContainers 中的微服务和 Web 应用程序的状态。</span><span class="sxs-lookup"><span data-stu-id="39a05-174">This is the simplest watchdog you could have since it only shows the state of the microservices and web applications in eShopOnContainers.</span></span> <span data-ttu-id="39a05-175">通常，监视程序在检测到不正常运行状态时还会执行相应操作。</span><span class="sxs-lookup"><span data-stu-id="39a05-175">Usually a watchdog also takes actions when it detects unhealthy states.</span></span>

![WebStatus 应用的浏览器视图，显示来自 eShopOnContainers 的五个微服务的运行状况](./media/image8.png)

<span data-ttu-id="39a05-177">**图 8-9**。</span><span class="sxs-lookup"><span data-stu-id="39a05-177">**Figure 8-9**.</span></span> <span data-ttu-id="39a05-178">eShopOnContainers 中的示例运行状况检查报告</span><span class="sxs-lookup"><span data-stu-id="39a05-178">Sample health check report in eShopOnContainers</span></span>

<span data-ttu-id="39a05-179">总而言之，ASP.NET Core HealthChecks 库的 ASP.NET 中间件为每个微服务提供了单个运行状况检查终结点。</span><span class="sxs-lookup"><span data-stu-id="39a05-179">In summary, the ASP.NET middleware of the ASP.NET Core HealthChecks library provides a single health check endpoint for each microservice.</span></span> <span data-ttu-id="39a05-180">这将执行其中定义的所有运行状况检查，并根据这些检查返回总体运行状况状态。</span><span class="sxs-lookup"><span data-stu-id="39a05-180">This will execute all the health checks defined within it and return an overall health state depending on all those checks.</span></span>

<span data-ttu-id="39a05-181">通过对将来的外部资源执行新的运行状况检查，可扩展 HealthChecks 库。</span><span class="sxs-lookup"><span data-stu-id="39a05-181">The HealthChecks library is extensible through new health checks of future external resources.</span></span> <span data-ttu-id="39a05-182">例如，我们预计，将来该库中会具有针对 Redis 缓存和其他数据库的运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="39a05-182">For example, we expect that in the future the library will have health checks for Redis cache and for other databases.</span></span> <span data-ttu-id="39a05-183">该库能够报告多个服务或应用程序依赖项的运行状况，用户随后可以根据这些运行状况检查采取相应操作。</span><span class="sxs-lookup"><span data-stu-id="39a05-183">The library allows health reporting by multiple service or application dependencies, and you can then take actions based on those health checks.</span></span>

## <a name="health-checks-when-using-orchestrators"></a><span data-ttu-id="39a05-184">在使用业务流程协调程序的情况下执行运行状况检查</span><span class="sxs-lookup"><span data-stu-id="39a05-184">Health checks when using orchestrators</span></span>

<span data-ttu-id="39a05-185">若要监视微服务的可用性，Kubernetes 和 Service Fabric 等业务流程协调程序可通过发送微服务测试请求来定期执行运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="39a05-185">To monitor the availability of your microservices, orchestrators like Kubernetes and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="39a05-186">若业务流程协调程序确定某服务/容器运行不正常，它会停止向该实例路由请求。</span><span class="sxs-lookup"><span data-stu-id="39a05-186">When an orchestrator determines that a service/container is unhealthy, it stops routing requests to that instance.</span></span> <span data-ttu-id="39a05-187">通常，它还会为该容器创建新实例。</span><span class="sxs-lookup"><span data-stu-id="39a05-187">It also usually creates a new instance of that container.</span></span>

<span data-ttu-id="39a05-188">例如，大多数业务流程协调程序可以使用运行状况检查来管理不会停机的部署。</span><span class="sxs-lookup"><span data-stu-id="39a05-188">For instance, most orchestrators can use health checks to manage zero-downtime deployments.</span></span> <span data-ttu-id="39a05-189">仅当服务/容器的状态变为正常时，业务流程协调程序才会开始将流量路由到服务/容器实例。</span><span class="sxs-lookup"><span data-stu-id="39a05-189">Only when the status of a service/container changes to healthy will the orchestrator start routing traffic to service/container instances.</span></span>

<span data-ttu-id="39a05-190">当业务流程协调程序执行应用程序升级时，运行状况监视尤为重要。</span><span class="sxs-lookup"><span data-stu-id="39a05-190">Health monitoring is especially important when an orchestrator performs an application upgrade.</span></span> <span data-ttu-id="39a05-191">某些业务流程协调程序（如 Azure Service Fabric）会分阶段更新服务，例如，它们可能为每个应用程序升级更新五分之一的群集面。</span><span class="sxs-lookup"><span data-stu-id="39a05-191">Some orchestrators (like Azure Service Fabric) update services in phases—for example, they might update one-fifth of the cluster surface for each application upgrade.</span></span> <span data-ttu-id="39a05-192">同时升级的一组节点称为“升级域”。</span><span class="sxs-lookup"><span data-stu-id="39a05-192">The set of nodes that's upgraded at the same time is referred to as an *upgrade domain*.</span></span> <span data-ttu-id="39a05-193">完成每个升级域的升级操作并面向用户提供后，在部署进程移至下一升级域之前，该升级域必须通过运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="39a05-193">After each upgrade domain has been upgraded and is available to users, that upgrade domain must pass health checks before the deployment moves to the next upgrade domain.</span></span>

<span data-ttu-id="39a05-194">服务运行状况的另一方面是报告服务的指标。</span><span class="sxs-lookup"><span data-stu-id="39a05-194">Another aspect of service health is reporting metrics from the service.</span></span> <span data-ttu-id="39a05-195">这是某些业务流程协调程序（如 Service Fabric）运行状况模型的高级功能。</span><span class="sxs-lookup"><span data-stu-id="39a05-195">This is an advanced capability of the health model of some orchestrators, like Service Fabric.</span></span> <span data-ttu-id="39a05-196">因为要借助指标来平衡资源使用情况，所以在使用业务流程协调程序时，指标非常重要。</span><span class="sxs-lookup"><span data-stu-id="39a05-196">Metrics are important when using an orchestrator because they are used to balance resource usage.</span></span> <span data-ttu-id="39a05-197">指标也可以是系统运行状况的指示器。</span><span class="sxs-lookup"><span data-stu-id="39a05-197">Metrics also can be an indicator of system health.</span></span> <span data-ttu-id="39a05-198">例如，某个应用程序包含多个微服务，并且每个实例都会报告每秒的请求数 (RPS) 指标。</span><span class="sxs-lookup"><span data-stu-id="39a05-198">For example, you might have an application that has many microservices, and each instance reports a requests-per-second (RPS) metric.</span></span> <span data-ttu-id="39a05-199">如果某一服务使用的资源（内存、处理器等）比另一个服务多，则业务流程协调程序会在群集中移动服务实例，尝试使资源使用保持均衡状态。</span><span class="sxs-lookup"><span data-stu-id="39a05-199">If one service is using more resources (memory, processor, etc.) than another service, the orchestrator could move service instances around in the cluster to try to maintain even resource utilization.</span></span>

<span data-ttu-id="39a05-200">请注意，Azure Service Fabric 提供自己的[运行状况监视模型](/azure/service-fabric/service-fabric-health-introduction)，该模型比简单的运行状况检查更高级。</span><span class="sxs-lookup"><span data-stu-id="39a05-200">Note that Azure Service Fabric provides its own [Health Monitoring model](/azure/service-fabric/service-fabric-health-introduction), which is more advanced than simple health checks.</span></span>

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a><span data-ttu-id="39a05-201">高级监视：可视化、分析和警报</span><span class="sxs-lookup"><span data-stu-id="39a05-201">Advanced monitoring: visualization, analysis, and alerts</span></span>

<span data-ttu-id="39a05-202">监视的最后一部分是对事件流进行可视化、报告服务性能、以及在检测到问题时发出警报。</span><span class="sxs-lookup"><span data-stu-id="39a05-202">The final part of monitoring is visualizing the event stream, reporting on service performance, and alerting when an issue is detected.</span></span> <span data-ttu-id="39a05-203">可以使用不同的解决方案来进行这方面的监视。</span><span class="sxs-lookup"><span data-stu-id="39a05-203">You can use different solutions for this aspect of monitoring.</span></span>

<span data-ttu-id="39a05-204">可以使用显示服务状态的简单自定义应用程序，例如介绍 [ASP.NET Core HealthChecks](https://github.com/dotnet-architecture/HealthChecks) 时显示的自定义页。</span><span class="sxs-lookup"><span data-stu-id="39a05-204">You can use simple custom applications showing the state of your services, like the custom page shown when explaining the [ASP.NET Core HealthChecks](https://github.com/dotnet-architecture/HealthChecks).</span></span> <span data-ttu-id="39a05-205">或者，可以使用更高级的工具（如 Azure Application Insights）来根据事件流发出警报。</span><span class="sxs-lookup"><span data-stu-id="39a05-205">Or you could use more advanced tools like Azure Application Insights to raise alerts based on the stream of events.</span></span>

<span data-ttu-id="39a05-206">最后，如果要存储所有事件流，可以使用 Microsoft Power BI 或其他解决方案（如 Kibana 或 Splunk）来可视化数据。</span><span class="sxs-lookup"><span data-stu-id="39a05-206">Finally, if you're storing all the event streams, you can use Microsoft Power BI or other solutions like Kibana or Splunk to visualize the data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="39a05-207">其他资源</span><span class="sxs-lookup"><span data-stu-id="39a05-207">Additional resources</span></span>

- <span data-ttu-id="39a05-208">**ASP.NET Core HealthChecks**（实验性版本）\\</span><span class="sxs-lookup"><span data-stu-id="39a05-208">**ASP.NET Core HealthChecks** (experimental release)\\</span></span>
  [*https://github.com/dotnet-architecture/HealthChecks/*](https://github.com/dotnet-architecture/HealthChecks/)

- <span data-ttu-id="39a05-209">**Service Fabric 运行状况监视简介**\\</span><span class="sxs-lookup"><span data-stu-id="39a05-209">**Introduction to Service Fabric health monitoring**\\</span></span>
  [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](/azure/service-fabric/service-fabric-health-introduction)

- <span data-ttu-id="39a05-210">**Azure Application Insights**\\</span><span class="sxs-lookup"><span data-stu-id="39a05-210">**Azure Application Insights**\\</span></span>
  [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)

- <span data-ttu-id="39a05-211">**Microsoft Operations Management Suite**\\</span><span class="sxs-lookup"><span data-stu-id="39a05-211">**Microsoft Operations Management Suite**\\</span></span>
  [*https://www.microsoft.com/cloud-platform/operations-management-suite*](https://www.microsoft.com/cloud-platform/operations-management-suite)

>[!div class="step-by-step"]
><span data-ttu-id="39a05-212">[上一页](implement-circuit-breaker-pattern.md)
>[下一页](../secure-net-microservices-web-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="39a05-212">[Previous](implement-circuit-breaker-pattern.md)
[Next](../secure-net-microservices-web-applications/index.md)</span></span>