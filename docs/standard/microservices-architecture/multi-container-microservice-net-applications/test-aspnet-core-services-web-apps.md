---
title: "测试 ASP.NET 核心服务和 web 应用"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |测试 ASP.NET 核心服务和 web 应用"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f756a679befee676db2bf6d402fd7e34b1621b9d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="47fb4-104">测试 ASP.NET 核心服务和 web 应用</span><span class="sxs-lookup"><span data-stu-id="47fb4-104">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="47fb4-105">控制器是任何 ASP.NET 核心 API 服务和 ASP.NET MVC Web 应用程序的中央部分。</span><span class="sxs-lookup"><span data-stu-id="47fb4-105">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="47fb4-106">在这种情况下，你应具有它们的行为符合适用于你的应用程序的置信度。</span><span class="sxs-lookup"><span data-stu-id="47fb4-106">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="47fb4-107">自动的测试可以为您提供这种信心，并可以到达生产之前检测错误。</span><span class="sxs-lookup"><span data-stu-id="47fb4-107">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="47fb4-108">你需要测试控制器的处理方式根据有效或无效的输入和测试控制器响应基于业务它所执行的操作的结果。</span><span class="sxs-lookup"><span data-stu-id="47fb4-108">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="47fb4-109">但是，你应具有这些类型的测试你微服务：</span><span class="sxs-lookup"><span data-stu-id="47fb4-109">However, you should have these types of tests your microservices:</span></span>

-   <span data-ttu-id="47fb4-110">单元测试。</span><span class="sxs-lookup"><span data-stu-id="47fb4-110">Unit tests.</span></span> <span data-ttu-id="47fb4-111">这些都确保在应用程序的各个组件按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="47fb4-111">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="47fb4-112">断言测试组件 API。</span><span class="sxs-lookup"><span data-stu-id="47fb4-112">Assertions test the component API.</span></span>

-   <span data-ttu-id="47fb4-113">集成测试。</span><span class="sxs-lookup"><span data-stu-id="47fb4-113">Integration tests.</span></span> <span data-ttu-id="47fb4-114">这些都确保组件交互对等数据库外部项目，项目中如期起作用。</span><span class="sxs-lookup"><span data-stu-id="47fb4-114">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="47fb4-115">断言可以测试组件 API、 UI 或数据库 I/O 之类的操作日志记录等的副作用。</span><span class="sxs-lookup"><span data-stu-id="47fb4-115">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

-   <span data-ttu-id="47fb4-116">每个微服务的的功能测试。</span><span class="sxs-lookup"><span data-stu-id="47fb4-116">Functional tests for each microservice.</span></span> <span data-ttu-id="47fb4-117">这些都确保该应用程序有效中用户的角度来看的预期。</span><span class="sxs-lookup"><span data-stu-id="47fb4-117">These ensure that the application works as expected from the user’s perspective.</span></span>

-   <span data-ttu-id="47fb4-118">测试服务。</span><span class="sxs-lookup"><span data-stu-id="47fb4-118">Service tests.</span></span> <span data-ttu-id="47fb4-119">这些都确保端到端服务使用情况下，包括在同一时间，测试多个服务进行测试。</span><span class="sxs-lookup"><span data-stu-id="47fb4-119">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="47fb4-120">对于此类型的测试，你需要首先准备环境。</span><span class="sxs-lookup"><span data-stu-id="47fb4-120">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="47fb4-121">在这种情况下，这意味着启动服务 （例如，通过 docker-撰写向上）。</span><span class="sxs-lookup"><span data-stu-id="47fb4-121">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="47fb4-122">有关 ASP.NET 核心 Web Api 实现的单元测试</span><span class="sxs-lookup"><span data-stu-id="47fb4-122">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="47fb4-123">单元测试涉及在从其基础结构和依赖项隔离中测试应用程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="47fb4-123">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="47fb4-124">你的单元测试控制器逻辑，仅一次操作的内容或在测试方法时，不的行为及其依赖项或框架本身。</span><span class="sxs-lookup"><span data-stu-id="47fb4-124">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="47fb4-125">单元测试不能在组件之间的交互中发现问题-，它是集成测试的目的。</span><span class="sxs-lookup"><span data-stu-id="47fb4-125">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="47fb4-126">作为你的单元测试控制器操作，请确保您仅关注它们的行为。</span><span class="sxs-lookup"><span data-stu-id="47fb4-126">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="47fb4-127">控制器单元测试可避免等筛选器、 路由或模型绑定。</span><span class="sxs-lookup"><span data-stu-id="47fb4-127">A controller unit test avoids things like filters, routing, or model binding.</span></span> <span data-ttu-id="47fb4-128">因为它们侧重于测试只是一件事，单元测试通常是，编写简单且快速运行。</span><span class="sxs-lookup"><span data-stu-id="47fb4-128">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="47fb4-129">可以经常运行一组正确编写的单元测试，而无需多开销。</span><span class="sxs-lookup"><span data-stu-id="47fb4-129">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="47fb4-130">单元测试被实现基于测试框架，如 xUnit.net、 MSTest、 Moq 或使用 NUnit。</span><span class="sxs-lookup"><span data-stu-id="47fb4-130">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="47fb4-131">对于 eShopOnContainers 示例应用程序，我们将使用 XUnit。</span><span class="sxs-lookup"><span data-stu-id="47fb4-131">For the eShopOnContainers sample application, we are using XUnit.</span></span>

<span data-ttu-id="47fb4-132">当你为 Web API 控制器编写单元测试时，您将控制器类实例直接在 C 中使用新的关键字\#，以便将尽可能快运行测试。</span><span class="sxs-lookup"><span data-stu-id="47fb4-132">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="47fb4-133">下面的示例演示如何执行此操作时使用[XUnit](https://xunit.github.io/)作为测试框架。</span><span class="sxs-lookup"><span data-stu-id="47fb4-133">The following example shows how to do this when using [XUnit](https://xunit.github.io/) as the Test framework.</span></span>

```csharp
[Fact]
public void Add_new_Order_raises_new_event()
{
    // Arrange
    var street = " FakeStreet ";
    var city = "FakeCity";
    // Other variables omitted for brevity ...
    // Act
    var fakeOrder = new Order(new Address(street, city, state, country, zipcode),
        cardTypeId, cardNumber,
        cardSecurityNumber, cardHolderName,
        cardExpiration);
    // Assert
    Assert.Equal(fakeOrder.DomainEvents.Count, expectedResult);
}
```

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="47fb4-134">实现集成和为每个微服务的功能测试</span><span class="sxs-lookup"><span data-stu-id="47fb4-134">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="47fb4-135">如上所述，集成测试和功能测试具有不同的用途和目标。</span><span class="sxs-lookup"><span data-stu-id="47fb4-135">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="47fb4-136">但是，测试 ASP.NET Core 控制器时，会实现这两种方法非常相似，因此在本部分中我们专注于集成测试。</span><span class="sxs-lookup"><span data-stu-id="47fb4-136">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="47fb4-137">集成测试可确保应用程序的组件正常运行时组成。</span><span class="sxs-lookup"><span data-stu-id="47fb4-137">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="47fb4-138">ASP.NET 核心支持的集成测试使用单元测试框架和内置测试 web 宿主可以用于处理请求而无需网络开销。</span><span class="sxs-lookup"><span data-stu-id="47fb4-138">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="47fb4-139">与不同的单元测试，集成测试经常涉及应用程序基础结构问题，如数据库、 文件系统、 网络资源，或 web 请求和响应。</span><span class="sxs-lookup"><span data-stu-id="47fb4-139">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="47fb4-140">单元测试使用 fakes 或模拟替代这些问题的对象。</span><span class="sxs-lookup"><span data-stu-id="47fb4-140">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="47fb4-141">但集成测试的目的是确认系统按预期方式使用这些系统，以便用于集成测试您不要使用 fakes 或模拟对象能否正常运行。</span><span class="sxs-lookup"><span data-stu-id="47fb4-141">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="47fb4-142">相反，你可以包括基础结构，如从其他服务的数据库访问或服务调用。</span><span class="sxs-lookup"><span data-stu-id="47fb4-142">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="47fb4-143">因为集成测试会运用更大将代码段比单元测试，而且因为集成测试依赖于基础结构元素，它们往往数量级慢于单元测试。</span><span class="sxs-lookup"><span data-stu-id="47fb4-143">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="47fb4-144">因此，它是限制多少集成测试编写并运行一个好办法。</span><span class="sxs-lookup"><span data-stu-id="47fb4-144">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="47fb4-145">ASP.NET 核心包括内置测试 web 宿主可以用于处理 HTTP 请求，而无需网络开销，这意味着你都可以更快地运行这些测试，使用实际的 web 宿主时。</span><span class="sxs-lookup"><span data-stu-id="47fb4-145">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster when using a real web host.</span></span> <span data-ttu-id="47fb4-146">测试 web 主机中提供了 NuGet 组件作为 Microsoft.AspNetCore.TestHost。</span><span class="sxs-lookup"><span data-stu-id="47fb4-146">The test web host is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="47fb4-147">它可以添加到集成测试项目，并用于托管 ASP.NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="47fb4-147">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="47fb4-148">如你将创建集成测试的 ASP.NET Core 控制器时，可以看到下面的代码中，您实例化通过测试主机控制器。</span><span class="sxs-lookup"><span data-stu-id="47fb4-148">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="47fb4-149">这相当于 HTTP 请求，但它的运行速度更快。</span><span class="sxs-lookup"><span data-stu-id="47fb4-149">This is comparable to an HTTP request, but it runs faster.</span></span>

```csharp
public class PrimeWebDefaultRequestShould
{
    private readonly TestServer _server;
    private readonly HttpClient _client;

    public PrimeWebDefaultRequestShould()
    {
        // Arrange
        _server = new TestServer(new WebHostBuilder()
           .UseStartup<Startup>());
           _client = _server.CreateClient();
    }

    [Fact]
    public async Task ReturnHelloWorld()
    {
        // Act
        var response = await _client.GetAsync("/");
        response.EnsureSuccessStatusCode();
        var responseString = await response.Content.ReadAsStringAsync();
        // Assert
        Assert.Equal("Hello World!", responseString);
    }
}
```

#### <a name="additional-resources"></a><span data-ttu-id="47fb4-150">其他资源</span><span class="sxs-lookup"><span data-stu-id="47fb4-150">Additional resources</span></span>

-   <span data-ttu-id="47fb4-151">**Steve Smith。测试控制器**(ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)</span><span class="sxs-lookup"><span data-stu-id="47fb4-151">**Steve Smith. Testing controllers** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)</span></span>

-   <span data-ttu-id="47fb4-152">**Steve Smith。集成测试**(ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)</span><span class="sxs-lookup"><span data-stu-id="47fb4-152">**Steve Smith. Integration testing** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)</span></span>

-   <span data-ttu-id="47fb4-153">**.NET Core 使用 dotnet 测试中的单元测试**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)</span><span class="sxs-lookup"><span data-stu-id="47fb4-153">**Unit testing in .NET Core using dotnet test**
[*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)</span></span>

-   <span data-ttu-id="47fb4-154">**xUnit.net**。</span><span class="sxs-lookup"><span data-stu-id="47fb4-154">**xUnit.net**.</span></span> <span data-ttu-id="47fb4-155">官方网站。</span><span class="sxs-lookup"><span data-stu-id="47fb4-155">Official site.</span></span>
    [<span data-ttu-id="47fb4-156">*https://xunit.github.io/*</span><span class="sxs-lookup"><span data-stu-id="47fb4-156">*https://xunit.github.io/*</span></span>](https://xunit.github.io/)

-   <span data-ttu-id="47fb4-157">**单元测试基础知识。** 
     [ *https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)</span><span class="sxs-lookup"><span data-stu-id="47fb4-157">**Unit Test Basics.**
[*https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)</span></span>

-   <span data-ttu-id="47fb4-158">**Moq**。</span><span class="sxs-lookup"><span data-stu-id="47fb4-158">**Moq**.</span></span> <span data-ttu-id="47fb4-159">GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="47fb4-159">GitHub repo.</span></span>
    [<span data-ttu-id="47fb4-160">*https://github.com/moq/moq*</span><span class="sxs-lookup"><span data-stu-id="47fb4-160">*https://github.com/moq/moq*</span></span>](https://github.com/moq/moq)

-   <span data-ttu-id="47fb4-161">**NUnit**。</span><span class="sxs-lookup"><span data-stu-id="47fb4-161">**NUnit**.</span></span> <span data-ttu-id="47fb4-162">官方网站。</span><span class="sxs-lookup"><span data-stu-id="47fb4-162">Official site.</span></span>
    [<span data-ttu-id="47fb4-163">*https://www.nunit.org/*</span><span class="sxs-lookup"><span data-stu-id="47fb4-163">*https://www.nunit.org/*</span></span>](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="47fb4-164">实现服务在一个多容器应用程序上进行测试</span><span class="sxs-lookup"><span data-stu-id="47fb4-164">Implementing service tests on a multi-container application</span></span> 

<span data-ttu-id="47fb4-165">如前所述，在测试多容器应用程序时，所有微服务将需要在 Docker 主机或容器群集内运行。</span><span class="sxs-lookup"><span data-stu-id="47fb4-165">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="47fb4-166">包括多个操作涉及多个微服务的端到端服务测试需要部署和启动 Docker 主机中的整个应用程序，通过运行 docker-撰写向上 （或如果你使用的 orchestrator 的可比较机制）。</span><span class="sxs-lookup"><span data-stu-id="47fb4-166">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="47fb4-167">整个应用程序及其所有服务运行后，你可以执行端到端集成和功能测试。</span><span class="sxs-lookup"><span data-stu-id="47fb4-167">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="47fb4-168">有几种方法可以使用。</span><span class="sxs-lookup"><span data-stu-id="47fb4-168">There are a few approaches you can use.</span></span> <span data-ttu-id="47fb4-169">在你用于部署应用程序 （或类似的如 docker compose.ci.build.yml） docker-compose.yml 文件中，在解决方案级别可以展开要使用的入口点[dotnet 测试](https://docs.microsoft.com/dotnet/core/tools/dotnet-test)。</span><span class="sxs-lookup"><span data-stu-id="47fb4-169">In the docker-compose.yml file that you use to deploy the application (or similar ones, like docker-compose.ci.build.yml), at the solution level you can expand the entry point to use [dotnet test](https://docs.microsoft.com/dotnet/core/tools/dotnet-test).</span></span> <span data-ttu-id="47fb4-170">你还可以使用另一个将在您的目标的映像中运行测试的 compose 文件。</span><span class="sxs-lookup"><span data-stu-id="47fb4-170">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="47fb4-171">通过使用包括微服务和在容器上的数据库的集成测试 compose 的另一个文件，可以确保，相关的数据将始终重置为其原始状态运行测试之前。</span><span class="sxs-lookup"><span data-stu-id="47fb4-171">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="47fb4-172">撰写应用程序启动并运行后，你可以充分利用的断点和异常，如果你正在运行 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="47fb4-172">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="47fb4-173">或者，你可以在 Visual Studio Team Services 或任何其他支持 Docker 容器的 CI/CD 系统中 CI 管道中自动运行集成测试。</span><span class="sxs-lookup"><span data-stu-id="47fb4-173">Or you can run the integration tests automatically in your CI pipeline in Visual Studio Team Services or any other CI/CD system that supports Docker containers.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="47fb4-174">[以前](订阅-events.md) [下一步] (.../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="47fb4-174">[Previous] (subscribe-events.md) [Next] (../microservice-ddd-cqrs-patterns/index.md)</span></span>
