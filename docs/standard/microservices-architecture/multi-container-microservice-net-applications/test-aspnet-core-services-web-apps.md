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
# <a name="testing-aspnet-core-services-and-web-apps"></a>测试 ASP.NET 核心服务和 web 应用

控制器是任何 ASP.NET 核心 API 服务和 ASP.NET MVC Web 应用程序的中央部分。 在这种情况下，你应具有它们的行为符合适用于你的应用程序的置信度。 自动的测试可以为您提供这种信心，并可以到达生产之前检测错误。

你需要测试控制器的处理方式根据有效或无效的输入和测试控制器响应基于业务它所执行的操作的结果。 但是，你应具有这些类型的测试你微服务：

-   单元测试。 这些都确保在应用程序的各个组件按预期方式工作。 断言测试组件 API。

-   集成测试。 这些都确保组件交互对等数据库外部项目，项目中如期起作用。 断言可以测试组件 API、 UI 或数据库 I/O 之类的操作日志记录等的副作用。

-   每个微服务的的功能测试。 这些都确保该应用程序有效中用户的角度来看的预期。

-   测试服务。 这些都确保端到端服务使用情况下，包括在同一时间，测试多个服务进行测试。 对于此类型的测试，你需要首先准备环境。 在这种情况下，这意味着启动服务 （例如，通过 docker-撰写向上）。

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a>有关 ASP.NET 核心 Web Api 实现的单元测试

单元测试涉及在从其基础结构和依赖项隔离中测试应用程序的一部分。 你的单元测试控制器逻辑，仅一次操作的内容或在测试方法时，不的行为及其依赖项或框架本身。 单元测试不能在组件之间的交互中发现问题-，它是集成测试的目的。

作为你的单元测试控制器操作，请确保您仅关注它们的行为。 控制器单元测试可避免等筛选器、 路由或模型绑定。 因为它们侧重于测试只是一件事，单元测试通常是，编写简单且快速运行。 可以经常运行一组正确编写的单元测试，而无需多开销。

单元测试被实现基于测试框架，如 xUnit.net、 MSTest、 Moq 或使用 NUnit。 对于 eShopOnContainers 示例应用程序，我们将使用 XUnit。

当你为 Web API 控制器编写单元测试时，您将控制器类实例直接在 C 中使用新的关键字\#，以便将尽可能快运行测试。 下面的示例演示如何执行此操作时使用[XUnit](https://xunit.github.io/)作为测试框架。

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

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a>实现集成和为每个微服务的功能测试

如上所述，集成测试和功能测试具有不同的用途和目标。 但是，测试 ASP.NET Core 控制器时，会实现这两种方法非常相似，因此在本部分中我们专注于集成测试。

集成测试可确保应用程序的组件正常运行时组成。 ASP.NET 核心支持的集成测试使用单元测试框架和内置测试 web 宿主可以用于处理请求而无需网络开销。

与不同的单元测试，集成测试经常涉及应用程序基础结构问题，如数据库、 文件系统、 网络资源，或 web 请求和响应。 单元测试使用 fakes 或模拟替代这些问题的对象。 但集成测试的目的是确认系统按预期方式使用这些系统，以便用于集成测试您不要使用 fakes 或模拟对象能否正常运行。 相反，你可以包括基础结构，如从其他服务的数据库访问或服务调用。

因为集成测试会运用更大将代码段比单元测试，而且因为集成测试依赖于基础结构元素，它们往往数量级慢于单元测试。 因此，它是限制多少集成测试编写并运行一个好办法。

ASP.NET 核心包括内置测试 web 宿主可以用于处理 HTTP 请求，而无需网络开销，这意味着你都可以更快地运行这些测试，使用实际的 web 宿主时。 测试 web 主机中提供了 NuGet 组件作为 Microsoft.AspNetCore.TestHost。 它可以添加到集成测试项目，并用于托管 ASP.NET Core 应用程序。

如你将创建集成测试的 ASP.NET Core 控制器时，可以看到下面的代码中，您实例化通过测试主机控制器。 这相当于 HTTP 请求，但它的运行速度更快。

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

#### <a name="additional-resources"></a>其他资源

-   **Steve Smith。测试控制器**(ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)

-   **Steve Smith。集成测试**(ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)

-   **.NET Core 使用 dotnet 测试中的单元测试**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)

-   **xUnit.net**。 官方网站。
    [*https://xunit.github.io/*](https://xunit.github.io/)

-   **单元测试基础知识。** 
     [ *https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)

-   **Moq**。 GitHub 存储库。
    [*https://github.com/moq/moq*](https://github.com/moq/moq)

-   **NUnit**。 官方网站。
    [*https://www.nunit.org/*](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a>实现服务在一个多容器应用程序上进行测试 

如前所述，在测试多容器应用程序时，所有微服务将需要在 Docker 主机或容器群集内运行。 包括多个操作涉及多个微服务的端到端服务测试需要部署和启动 Docker 主机中的整个应用程序，通过运行 docker-撰写向上 （或如果你使用的 orchestrator 的可比较机制）。 整个应用程序及其所有服务运行后，你可以执行端到端集成和功能测试。

有几种方法可以使用。 在你用于部署应用程序 （或类似的如 docker compose.ci.build.yml） docker-compose.yml 文件中，在解决方案级别可以展开要使用的入口点[dotnet 测试](https://docs.microsoft.com/dotnet/core/tools/dotnet-test)。 你还可以使用另一个将在您的目标的映像中运行测试的 compose 文件。 通过使用包括微服务和在容器上的数据库的集成测试 compose 的另一个文件，可以确保，相关的数据将始终重置为其原始状态运行测试之前。

撰写应用程序启动并运行后，你可以充分利用的断点和异常，如果你正在运行 Visual Studio。 或者，你可以在 Visual Studio Team Services 或任何其他支持 Docker 容器的 CI/CD 系统中 CI 管道中自动运行集成测试。

>[!div class="step-by-step"]
[以前](订阅-events.md) [下一步] (.../microservice-ddd-cqrs-patterns/index.md)
