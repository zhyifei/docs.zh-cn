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
# <a name="health-monitoring"></a><span data-ttu-id="c7849-104">运行状况监视</span><span class="sxs-lookup"><span data-stu-id="c7849-104">Health monitoring</span></span>

<span data-ttu-id="c7849-105">运行状况监视，则可以允许容器和微服务的状态有关的接近实时的信息。</span><span class="sxs-lookup"><span data-stu-id="c7849-105">Health monitoring can allow near-real-time information about the state of your containers and microservices.</span></span> <span data-ttu-id="c7849-106">运行状况监视至关重要的操作系统微服务的多个方面和 orchestrators 在更高版本所述在阶段，执行部分应用升级时尤其重要。</span><span class="sxs-lookup"><span data-stu-id="c7849-106">Health monitoring is critical to multiple aspects of operating microservices and is especially important when orchestrators perform partial application upgrades in phases, as explained later.</span></span>

<span data-ttu-id="c7849-107">基于微服务的应用程序通常使用的检测信号或运行状况检查，以使其性能监视器、 计划程序时和 orchestrators 能够跟踪多种服务。</span><span class="sxs-lookup"><span data-stu-id="c7849-107">Microservices-based applications often use heartbeats or health checks to enable their performance monitors, schedulers, and orchestrators to keep track of the multitude of services.</span></span> <span data-ttu-id="c7849-108">如果服务不能发送某种形式的"我已处于活动状态"信号按需或按计划，你的应用程序时部署更新，或它可能只需太迟检测故障并不能停止最终会发生重大中断的级联故障可能会面临风险。</span><span class="sxs-lookup"><span data-stu-id="c7849-108">If services cannot send some sort of “I’m alive” signal, either on demand or on a schedule, your application might face risks when you deploy updates, or it might simply detect failures too late and not be able to stop cascading failures that can end up in major outages.</span></span>

<span data-ttu-id="c7849-109">在典型的模型中，服务发送有关其状态报告和聚合该信息，以提供您的应用程序的运行状况状态的总体视图。</span><span class="sxs-lookup"><span data-stu-id="c7849-109">In the typical model, services send reports about their status, and that information is aggregated to provide an overall view of the state of health of your application.</span></span> <span data-ttu-id="c7849-110">如果你使用的 orchestrator，你可以提供到 orchestrator 的群集的运行状况信息，以便群集可以采取相应的措施。</span><span class="sxs-lookup"><span data-stu-id="c7849-110">If you are using an orchestrator, you can provide health information to your orchestrator’s cluster, so that the cluster can act accordingly.</span></span> <span data-ttu-id="c7849-111">如果你投资高质量运行状况报告自定义的应用程序，可以检测和更加轻松地为你正在运行的应用程序中修复问题。</span><span class="sxs-lookup"><span data-stu-id="c7849-111">If you invest in high-quality health reporting that is customized for your application, you can detect and fix issues for your running application much more easily.</span></span>

## <a name="implementing-health-checks-in-aspnet-core-services"></a><span data-ttu-id="c7849-112">ASP.NET Core services 中实现运行状况检查</span><span class="sxs-lookup"><span data-stu-id="c7849-112">Implementing health checks in ASP.NET Core services</span></span>

<span data-ttu-id="c7849-113">在开发时 ASP.NET Core 微服务或 web 应用程序，你可以使用通过 ASP.NET 团队在名为 HealthChecks 库。</span><span class="sxs-lookup"><span data-stu-id="c7849-113">When developing an ASP.NET Core microservice or web application, you can use a library named HealthChecks from the ASP.NET team.</span></span> <span data-ttu-id="c7849-114">（截至自 2017 年 1 月，早期版本是可在 GitHub 上）。</span><span class="sxs-lookup"><span data-stu-id="c7849-114">(As of May 2017, an early release is available on GitHub).</span></span>

<span data-ttu-id="c7849-115">此库是易于使用，并提供功能，可让你验证你的应用程序 （如 SQL Server 数据库或远程 API） 所需的任何特定的外部资源正常工作。</span><span class="sxs-lookup"><span data-stu-id="c7849-115">This library is easy to use and provides features that let you validate that any specific external resource needed for your application (like a SQL Server database or remote API) is working properly.</span></span> <span data-ttu-id="c7849-116">当你使用此库时，你可以决定它表示资源是正常的如我们在后面介绍。</span><span class="sxs-lookup"><span data-stu-id="c7849-116">When you use this library, you can also decide what it means that the resource is healthy, as we explain later.</span></span>

<span data-ttu-id="c7849-117">若要使用此库，你需要先使用你微服务中的库。</span><span class="sxs-lookup"><span data-stu-id="c7849-117">In order to use this library, you need to first use the library in your microservices.</span></span> <span data-ttu-id="c7849-118">其次，你需要查询前端应用程序的运行状况报告。</span><span class="sxs-lookup"><span data-stu-id="c7849-118">Second, you need a front-end application that queries for the health reports.</span></span> <span data-ttu-id="c7849-119">前端应用程序可以是自定义 reporting 应用程序，或可能的业务流程本身可以相应地作出反应到运行状况状态。</span><span class="sxs-lookup"><span data-stu-id="c7849-119">That front end application could be a custom reporting application, or it could be an orchestrator itself that can react accordingly to the health states.</span></span>

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a><span data-ttu-id="c7849-120">使用你的后端 ASP.NET 微服务中的 HealthChecks 库</span><span class="sxs-lookup"><span data-stu-id="c7849-120">Using the HealthChecks library in your back end ASP.NET microservices</span></span>

<span data-ttu-id="c7849-121">你可以看到如何在 eShopOnContainers 示例应用程序中使用 HealthChecks 库。</span><span class="sxs-lookup"><span data-stu-id="c7849-121">You can see how the HealthChecks library is used in the eShopOnContainers sample application.</span></span> <span data-ttu-id="c7849-122">若要开始，你需要定义何谓针对每个微服务的正常状态。</span><span class="sxs-lookup"><span data-stu-id="c7849-122">To begin, you need to define what constitutes a healthy status for each microservice.</span></span> <span data-ttu-id="c7849-123">在示例应用程序，微服务都可通过 HTTP 和如果其相关的 SQL Server 数据库也是可用来访问 microservice API 是否工作正常。</span><span class="sxs-lookup"><span data-stu-id="c7849-123">In the sample application, the microservices are healthy if the microservice API is accessible via HTTP and if its related SQL Server database is also available.</span></span>

<span data-ttu-id="c7849-124">将来，你将能够作为 NuGet 程序包安装 HealthChecks 库。</span><span class="sxs-lookup"><span data-stu-id="c7849-124">In the future, you will be able to install the HealthChecks library as a NuGet package.</span></span> <span data-ttu-id="c7849-125">但截至撰写本文时，你需要下载并将代码编译为解决方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="c7849-125">But as of this writing, you need to download and compile the code as part of your solution.</span></span> <span data-ttu-id="c7849-126">克隆在 https://github.com/aspnet/HealthChecks 可用的代码并将以下文件夹复制到你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="c7849-126">Clone the code available at https://github.com/aspnet/HealthChecks and copy the following folders to your solution.</span></span>

  - <span data-ttu-id="c7849-127">src/常用</span><span class="sxs-lookup"><span data-stu-id="c7849-127">src/common</span></span>
  - <span data-ttu-id="c7849-128">src/Microsoft.AspNetCore.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="c7849-128">src/Microsoft.AspNetCore.HealthChecks</span></span>
  - <span data-ttu-id="c7849-129">src/Microsoft.Extensions.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="c7849-129">src/Microsoft.Extensions.HealthChecks</span></span>
  - <span data-ttu-id="c7849-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span><span class="sxs-lookup"><span data-stu-id="c7849-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span></span>

<span data-ttu-id="c7849-131">你也可以使用类似的 azure (Microsoft.Extensions.HealthChecks.AzureStorage)，但因为此版本的 eShopOnContainers 在 Azure 上没有任何依赖项的其他检查，不需要它。</span><span class="sxs-lookup"><span data-stu-id="c7849-131">You could also use additional checks like the ones for Azure (Microsoft.Extensions.HealthChecks.AzureStorage), but since this version of eShopOnContainers does not have any dependency on Azure, you do not need it.</span></span> <span data-ttu-id="c7849-132">因为 eShopOnContainers 基于 ASP.NET Core 不需要 ASP.NET 运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="c7849-132">You do not need the ASP.NET health checks, because eShopOnContainers is based on ASP.NET Core.</span></span>

<span data-ttu-id="c7849-133">图 10-6 显示在 Visual Studio 中，准备好由任何微服务用作构建基块 HealthChecks 库。</span><span class="sxs-lookup"><span data-stu-id="c7849-133">Figure 10-6 shows the HealthChecks library in Visual Studio, ready to be used as a building block by any microservices.</span></span>

![](./media/image6.png)

<span data-ttu-id="c7849-134">**图 10-6**。</span><span class="sxs-lookup"><span data-stu-id="c7849-134">**Figure 10-6**.</span></span> <span data-ttu-id="c7849-135">ASP.NET： 在 Visual Studio 解决方案核心 HealthChecks library 源代码</span><span class="sxs-lookup"><span data-stu-id="c7849-135">ASP.NET Core HealthChecks library source code in a Visual Studio solution</span></span>

<span data-ttu-id="c7849-136">因为引入了更早版本，以在每个微服务项目中执行操作的第一个操作是添加对三个 HealthChecks 库的引用。</span><span class="sxs-lookup"><span data-stu-id="c7849-136">As introduced earlier, the first thing to do in each microservice project is to add a reference to the three HealthChecks libraries.</span></span> <span data-ttu-id="c7849-137">之后，你可以添加你想要在该微服务中执行的运行状况检查操作。</span><span class="sxs-lookup"><span data-stu-id="c7849-137">After that, you add the health check actions that you want to perform in that microservice.</span></span> <span data-ttu-id="c7849-138">这些操作基本上是在其他微服务 (HttpUrlCheck) 或数据库上的依赖项 (当前 SqlCheck\*对于 SQL Server 数据库)。</span><span class="sxs-lookup"><span data-stu-id="c7849-138">These actions are basically dependencies on other microservices (HttpUrlCheck) or databases (currently SqlCheck\* for SQL Server databases).</span></span> <span data-ttu-id="c7849-139">你添加的每个 ASP.NET 微服务或 ASP.NET web 应用程序的启动类中的操作。</span><span class="sxs-lookup"><span data-stu-id="c7849-139">You add the action within the Startup class of each ASP.NET microservice or ASP.NET web application.</span></span>

<span data-ttu-id="c7849-140">应通过将其所有 HTTP 或数据库的依赖项都添加为一个 AddHealthCheck 方法配置每个服务或 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c7849-140">Each service or web application should be configured by adding all its HTTP or database dependencies as one AddHealthCheck method.</span></span> <span data-ttu-id="c7849-141">例如，从 eShopOnContainers MVC web 应用程序依赖于许多服务，因此具有多个 AddCheck 方法添加到运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="c7849-141">For example, the MVC web application from eShopOnContainers depends on many services, therefore has several AddCheck methods added to the health checks.</span></span>

<span data-ttu-id="c7849-142">例如，下面的代码中可以看到如何目录微服务会在其 SQL Server 数据库上添加依赖项。</span><span class="sxs-lookup"><span data-stu-id="c7849-142">For instance, in the following code you can see how the catalog microservice adds a dependency on its SQL Server database.</span></span>

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

<span data-ttu-id="c7849-143">但是，eShopOnContainers MVC web 应用程序剩余的微服务上有多个依赖项。</span><span class="sxs-lookup"><span data-stu-id="c7849-143">However, the MVC web application of eShopOnContainers has multiple dependencies on the rest of the microservices.</span></span> <span data-ttu-id="c7849-144">因此，它调用一个 AddUrlCheck 方法为每个微服务，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="c7849-144">Therefore, it calls one AddUrlCheck method for each microservice, as shown in the following example:</span></span>

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

<span data-ttu-id="c7849-145">因此，微服务将不提供"正常"状态，直到所有检查也都处于正常状态。</span><span class="sxs-lookup"><span data-stu-id="c7849-145">Thus, a microservice will not provide a “healthy” status until all its checks are healthy as well.</span></span>

<span data-ttu-id="c7849-146">如果微服务没有依赖关系，在服务上或在 SQL Server 上，你应仅添加 Healthy("Ok") 检查。</span><span class="sxs-lookup"><span data-stu-id="c7849-146">If the microservice does not have a dependency on a service or on SQL Server, you should just add a Healthy("Ok") check.</span></span> <span data-ttu-id="c7849-147">下面的代码是从 eShopOnContainers basket.api 微服务。</span><span class="sxs-lookup"><span data-stu-id="c7849-147">The following code is from the eShopOnContainers basket.api microservice.</span></span> <span data-ttu-id="c7849-148">（篮 microservice 使用 Redis 缓存中，但库尚未包含 Redis 运行状况检查提供程序。）</span><span class="sxs-lookup"><span data-stu-id="c7849-148">(The basket microservice uses the Redis cache, but the library does not yet include a Redis health check provider.)</span></span>

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

<span data-ttu-id="c7849-149">它具有服务或 web 应用程序可通过公开运行状况检查终结点，若要启用 UseHealthChecks (\[*url\_为\_运行状况\_检查*\]) 扩展方法。</span><span class="sxs-lookup"><span data-stu-id="c7849-149">For a service or web application to expose the health check endpoint, it has to enable the UseHealthChecks(\[*url\_for\_health\_checks*\]) extension method.</span></span> <span data-ttu-id="c7849-150">此方法将在 WebHostBuilder 级别 ASP.NET 核心服务或 web 应用程序，如下面的代码中所示的 UseKestrel 之后立即程序类的主要方法。</span><span class="sxs-lookup"><span data-stu-id="c7849-150">This method goes at the WebHostBuilder level in the main method of the Program class of your ASP.NET Core service or web application, right after UseKestrel as shown in the code below.</span></span>

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

<span data-ttu-id="c7849-151">进程的工作原理如下： 每个微服务公开终结点 /hc。</span><span class="sxs-lookup"><span data-stu-id="c7849-151">The process works like this: each microservice exposes the endpoint /hc.</span></span> <span data-ttu-id="c7849-152">该终结点是由 HealthChecks 库 ASP.NET Core 中间件创建的。</span><span class="sxs-lookup"><span data-stu-id="c7849-152">That endpoint is created by the HealthChecks library ASP.NET Core middleware.</span></span> <span data-ttu-id="c7849-153">当调用该终结点时，它将运行 Startup 类的 AddHealthChecks 方法中配置的所有运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="c7849-153">When that endpoint is invoked, it runs all the health checks that are configured in the AddHealthChecks method in the Startup class.</span></span>

<span data-ttu-id="c7849-154">UseHealthChecks 方法需要使用一个端口或路径。</span><span class="sxs-lookup"><span data-stu-id="c7849-154">The UseHealthChecks method expects a port or a path.</span></span> <span data-ttu-id="c7849-155">该端口或路径是要用于检查服务的运行状况状态的终结点。</span><span class="sxs-lookup"><span data-stu-id="c7849-155">That port or path is the endpoint to use to check the health state of the service.</span></span> <span data-ttu-id="c7849-156">例如，目录微服务使用路径 /hc。</span><span class="sxs-lookup"><span data-stu-id="c7849-156">For instance, the catalog microservice uses the path /hc.</span></span>

### <a name="caching-health-check-responses"></a><span data-ttu-id="c7849-157">缓存的运行状况检查响应</span><span class="sxs-lookup"><span data-stu-id="c7849-157">Caching health check responses</span></span>

<span data-ttu-id="c7849-158">因为你不希望你的服务，导致拒绝服务 (DoS) 或只需不想通过检查资源影响服务性能过于频繁，你可以缓存返回，并配置每个运行状况检查缓存持续时间。</span><span class="sxs-lookup"><span data-stu-id="c7849-158">Since you do not want to cause a Denial of Service (DoS) in your services, or you simply do not want to impact service performance by checking resources too frequently, you can cache the returns and configure a cache duration for each health check.</span></span>

<span data-ttu-id="c7849-159">默认情况下，将缓存持续时间内部设置为 5 分钟，但你可以更改该缓存持续时间在每个运行状况检查，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="c7849-159">By default, the cache duration is internally set to 5 minutes, but you can change that cache duration on each health check, as in the following code:</span></span>

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a><span data-ttu-id="c7849-160">查询有关其运行状况状态的报表到你微服务</span><span class="sxs-lookup"><span data-stu-id="c7849-160">Querying your microservices to report about their health status</span></span>

<span data-ttu-id="c7849-161">当你配置了运行状况检查如下所述，在 Docker 中运行的微服务后时，你可以直接检查从浏览器是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="c7849-161">When you have configured health checks as described here, once the microservice is running in Docker, you can directly check from a browser if it is healthy.</span></span> <span data-ttu-id="c7849-162">（这未需要使你可以通过 localhost 或通过外部的 Docker 主机 IP 访问容器发布外 Docker 主机中，容器端口。）图 10-7 显示在浏览器和相应的响应的请求。</span><span class="sxs-lookup"><span data-stu-id="c7849-162">(This does require that you are publishing the container port out of the Docker host, so you can access the container through localhost or through the external Docker host IP.) Figure 10-7 shows a request in a browser and the corresponding response.</span></span>

![](./media/image7.png)

<span data-ttu-id="c7849-163">**图 10-7**。</span><span class="sxs-lookup"><span data-stu-id="c7849-163">**Figure 10-7**.</span></span> <span data-ttu-id="c7849-164">正在检查从浏览器单一服务的运行状况状态</span><span class="sxs-lookup"><span data-stu-id="c7849-164">Checking health status of a single service from a browser</span></span>

<span data-ttu-id="c7849-165">在该测试，你可以看到 （在端口 5101 上运行） catalog.api microservice 处于正常状态，在 JSON 中返回 HTTP 200 状态和状态信息。</span><span class="sxs-lookup"><span data-stu-id="c7849-165">In that test, you can see that the catalog.api microservice (running on port 5101) is healthy, returning HTTP status 200 and status information in JSON.</span></span> <span data-ttu-id="c7849-166">它还意味着，内部服务还将检查其 SQL Server 数据库依赖项的运行状况和，运行状况检查已其自身报告为正常。</span><span class="sxs-lookup"><span data-stu-id="c7849-166">It also means that internally the service also checked the health of its SQL Server database dependency and that health check was reported itself as healthy.</span></span>

## <a name="using-watchdogs"></a><span data-ttu-id="c7849-167">使用监视器</span><span class="sxs-lookup"><span data-stu-id="c7849-167">Using watchdogs</span></span>

<span data-ttu-id="c7849-168">监视程序是一种单独的服务，可以监视运行状况并通过使用前面介绍的 HealthChecks 库查询加载跨服务和报告有关微服务的运行状况。</span><span class="sxs-lookup"><span data-stu-id="c7849-168">A watchdog is a separate service that can watch health and load across services, and report health about the microservices by querying with the HealthChecks library introduced earlier.</span></span> <span data-ttu-id="c7849-169">这可以帮助防止不会检测基于视图的单个服务的错误。</span><span class="sxs-lookup"><span data-stu-id="c7849-169">This can help prevent errors that would not be detected based on the view of a single service.</span></span> <span data-ttu-id="c7849-170">监视器也是一个好的到可以为无需用户交互的已知条件执行修正操作的宿主代码。</span><span class="sxs-lookup"><span data-stu-id="c7849-170">Watchdogs also are a good place to host code that can perform remediation actions for known conditions without user interaction.</span></span>

<span data-ttu-id="c7849-171">EShopOnContainers 示例包含一个网页，显示示例运行状况检查报告，图 10-8 所示。</span><span class="sxs-lookup"><span data-stu-id="c7849-171">The eShopOnContainers sample contains a web page that displays sample health check reports, as shown in Figure 10-8.</span></span> <span data-ttu-id="c7849-172">这是最简单的监视器，您可以对，因为它只能是显示 eShopOnContainers 微服务和 web 应用程序的状态。</span><span class="sxs-lookup"><span data-stu-id="c7849-172">This is the simplest watchdog you could have, since all it does is shows the state of the microservices and web applications in eShopOnContainers.</span></span> <span data-ttu-id="c7849-173">通常，提供监视还执行操作时检测到不正常状态。</span><span class="sxs-lookup"><span data-stu-id="c7849-173">Usually a watchdog also takes actions when it detects unhealthy states.</span></span>

![](./media/image8.png)

<span data-ttu-id="c7849-174">**图 10-8**。</span><span class="sxs-lookup"><span data-stu-id="c7849-174">**Figure 10-8**.</span></span> <span data-ttu-id="c7849-175">示例 eShopOnContainers 中的运行状况检查报告</span><span class="sxs-lookup"><span data-stu-id="c7849-175">Sample health check report in eShopOnContainers</span></span>

<span data-ttu-id="c7849-176">总之，ASP.NET 核心 HealthChecks 库的 ASP.NET 中间件提供每个微服务构成的单个运行状况检查终结点。</span><span class="sxs-lookup"><span data-stu-id="c7849-176">In summary, the ASP.NET middleware of the ASP.NET Core HealthChecks library provides a single health check endpoint for each microservice.</span></span> <span data-ttu-id="c7849-177">这将执行在其中定义的所有运行状况检查，并返回具体取决于所有这些检查的总体运行状况状态。</span><span class="sxs-lookup"><span data-stu-id="c7849-177">This will execute all the health checks defined within it and return an overall health state depending on all those checks.</span></span>

<span data-ttu-id="c7849-178">HealthChecks 库是可扩展的将来的外部资源的新运行状况检查通过。</span><span class="sxs-lookup"><span data-stu-id="c7849-178">The HealthChecks library is extensible through new health checks of future external resources.</span></span> <span data-ttu-id="c7849-179">例如，我们预期，通过在将来库将具有的 Redis 缓存和其他数据库的运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="c7849-179">For example, we expect that in the future the library will have health checks for Redis cache and for other databases.</span></span> <span data-ttu-id="c7849-180">库允许运行状况报告多个服务或应用程序依赖关系，然后可以执行基于这些运行状况检查的操作。</span><span class="sxs-lookup"><span data-stu-id="c7849-180">The library allows health reporting by multiple service or application dependencies, and you can then take actions based on those health checks.</span></span>

## <a name="health-checks-when-using-orchestrators"></a><span data-ttu-id="c7849-181">使用 orchestrators 时的运行状况检查</span><span class="sxs-lookup"><span data-stu-id="c7849-181">Health checks when using orchestrators</span></span>

<span data-ttu-id="c7849-182">若要监视你微服务的可用性，orchestrators Docker Swarm、 等 Kubernetes，Service Fabric 将定期通过发送请求以测试微服务执行运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="c7849-182">To monitor the availability of your microservices, orchestrators like Docker Swarm, Kubernetes, and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="c7849-183">当 orchestrator 确定服务/容器不正常，则它会停止请求路由到该实例。</span><span class="sxs-lookup"><span data-stu-id="c7849-183">When an orchestrator determines that a service/container is unhealthy, it stops routing requests to that instance.</span></span> <span data-ttu-id="c7849-184">它通常还会创建该容器的新实例。</span><span class="sxs-lookup"><span data-stu-id="c7849-184">It also usually creates a new instance of that container.</span></span>

<span data-ttu-id="c7849-185">例如，大多数 orchestrators 可以使用运行状况检查用于管理零停机时间部署。</span><span class="sxs-lookup"><span data-stu-id="c7849-185">For instance, most orchestrators can use health checks to manage zero-downtime deployments.</span></span> <span data-ttu-id="c7849-186">仅当服务/容器更改为正常的状态将 orchestrator 开始将流量路由到服务/容器实例。</span><span class="sxs-lookup"><span data-stu-id="c7849-186">Only when the status of a service/container changes to healthy will the orchestrator start routing traffic to service/container instances.</span></span>

<span data-ttu-id="c7849-187">当 orchestrator 执行应用程序升级时，运行状况监视一点尤其重要。</span><span class="sxs-lookup"><span data-stu-id="c7849-187">Health monitoring is especially important when an orchestrator performs an application upgrade.</span></span> <span data-ttu-id="c7849-188">（如 Azure Service Fabric) 某些 orchestrators 更新中的服务阶段 — 例如，它们可能会更新每个应用程序升级的群集表面 1 / 5。</span><span class="sxs-lookup"><span data-stu-id="c7849-188">Some orchestrators (like Azure Service Fabric) update services in phases—for example, they might update one-fifth of the cluster surface for each application upgrade.</span></span> <span data-ttu-id="c7849-189">在同一时间升级的节点集称为*升级域*。</span><span class="sxs-lookup"><span data-stu-id="c7849-189">The set of nodes that is upgraded at the same time is referred to as an *upgrade domain*.</span></span> <span data-ttu-id="c7849-190">每个升级域已升级，并可供用户后，该升级域必须通过运行状况检查，然后部署将移到下一个升级域。</span><span class="sxs-lookup"><span data-stu-id="c7849-190">After each upgrade domain has been upgraded and is available to users, that upgrade domain must pass health checks before the deployment moves to the next upgrade domain.</span></span>

<span data-ttu-id="c7849-191">另一个方面，服务的运行状况报告从服务的度量值。</span><span class="sxs-lookup"><span data-stu-id="c7849-191">Another aspect of service health is reporting metrics from the service.</span></span> <span data-ttu-id="c7849-192">这是某些 orchestrators，Service Fabric 等的运行状况模型的一个高级的功能。</span><span class="sxs-lookup"><span data-stu-id="c7849-192">This is an advanced capability of the health model of some orchestrators, like Service Fabric.</span></span> <span data-ttu-id="c7849-193">当使用 orchestrator，因为它们用于平衡资源使用情况时，度量值很重要。</span><span class="sxs-lookup"><span data-stu-id="c7849-193">Metrics are important when using an orchestrator because they are used to balance resource usage.</span></span> <span data-ttu-id="c7849-194">度量值也可以是的系统运行状况指示符。</span><span class="sxs-lookup"><span data-stu-id="c7849-194">Metrics also can be an indicator of system health.</span></span> <span data-ttu-id="c7849-195">例如，你可能必须具有许多微服务的应用程序和每个实例报告请求每秒 (RPS) 度量值。</span><span class="sxs-lookup"><span data-stu-id="c7849-195">For example, you might have an application that has many microservices, and each instance reports a requests-per-second (RPS) metric.</span></span> <span data-ttu-id="c7849-196">如果一个服务使用比另一个服务的更多资源 （内存、 处理器等），orchestrator 无法服务实例中移动群集尝试维护甚至资源利用率。</span><span class="sxs-lookup"><span data-stu-id="c7849-196">If one service is using more resources (memory, processor, etc.) than another service, the orchestrator could move service instances around in the cluster to try to maintain even resource utilization.</span></span>

<span data-ttu-id="c7849-197">请注意，是否你使用 Azure Service Fabric，它提供其自己[运行状况监视模型](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)，这是更高级比简单的运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="c7849-197">Note that if you are using Azure Service Fabric, it provides its own [Health Monitoring model](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), which is more advanced than simple health checks.</span></span>

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a><span data-ttu-id="c7849-198">高级监视： 可视化效果、 分析和警报</span><span class="sxs-lookup"><span data-stu-id="c7849-198">Advanced monitoring: visualization, analysis, and alerts</span></span>

<span data-ttu-id="c7849-199">监视的最后一部分直观显示的事件流，对服务性能，报告和警报时检测到的问题。</span><span class="sxs-lookup"><span data-stu-id="c7849-199">The final part of monitoring is visualizing the event stream, reporting on service performance, and alerting when an issue is detected.</span></span> <span data-ttu-id="c7849-200">此方面的监视，你可以使用不同的解决方案。</span><span class="sxs-lookup"><span data-stu-id="c7849-200">You can use different solutions for this aspect of monitoring.</span></span>

<span data-ttu-id="c7849-201">你可以使用显示你的服务的状态的简单自定义应用程序，如自定义页上，我们介绍了当我们介绍了[ASP.NET 核心 HealthChecks](https://github.com/aspnet/HealthChecks)。</span><span class="sxs-lookup"><span data-stu-id="c7849-201">You can use simple custom applications showing the state of your services, like the custom page we showed when we explained [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks).</span></span> <span data-ttu-id="c7849-202">或者，可以使用更高级的工具，如 Azure Application Insights 和 Operations Management Suite 发出警报基于事件的流。</span><span class="sxs-lookup"><span data-stu-id="c7849-202">Or you could use more advanced tools like Azure Application Insights and Operations Management Suite to raise alerts based on the stream of events.</span></span>

<span data-ttu-id="c7849-203">最后，如果你已存储的所有事件流，你可以使用 Microsoft Power BI 或 Kibana 或 Splunk 之类的第三方解决方案来实现数据可视化效果。</span><span class="sxs-lookup"><span data-stu-id="c7849-203">Finally, if you were storing all the event streams, you can use Microsoft Power BI or a third-party solution like Kibana or Splunk to visualize the data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c7849-204">其他资源</span><span class="sxs-lookup"><span data-stu-id="c7849-204">Additional resources</span></span>

-   <span data-ttu-id="c7849-205">**ASP.NET 核心 HealthChecks** （早期发行版） [ *https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span><span class="sxs-lookup"><span data-stu-id="c7849-205">**ASP.NET Core HealthChecks** (early release) [*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span></span>

-   <span data-ttu-id="c7849-206">**Service Fabric 运行状况监视简介**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span><span class="sxs-lookup"><span data-stu-id="c7849-206">**Introduction to Service Fabric health monitoring**
[*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span></span>

-   <span data-ttu-id="c7849-207">**Azure 的 Application Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span><span class="sxs-lookup"><span data-stu-id="c7849-207">**Azure Application Insights**
[*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span></span>

-   <span data-ttu-id="c7849-208">**Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span><span class="sxs-lookup"><span data-stu-id="c7849-208">**Microsoft Operations Management Suite**
[*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="c7849-209">[以前](实现的线路的断路器-pattern.md) [下一步] (.../secure-net-microservices-web-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="c7849-209">[Previous] (implement-circuit-breaker-pattern.md) [Next] (../secure-net-microservices-web-applications/index.md)</span></span>
