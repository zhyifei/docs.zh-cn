---
title: 测试 ASP.NET Core MVC 应用
description: 使用 ASP.NET Core 和 Azure 构建新式 Web 应用程序 | 测试 ASP.NET Core MVC 应用
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.openlocfilehash: b22e0e109144b4abd04cd4199cfdec244d8fa7af
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106497"
---
# <a name="test-aspnet-core-mvc-apps"></a>测试 ASP.NET Core MVC 应用

> _“如果你不喜欢对产品进行单元测试，很可能你的客户也不喜欢这样做。”_
>  _- 匿名用户-_

## <a name="summary"></a>总结

任何复杂程度的软件在响应更改方面皆可能意外失败。 因此，更改后，除最普通（或关键性最低）的应用程序外，其他所有应用程序均需测试。 手动测试是最慢、最不可靠且最昂贵的软件测试方式。 遗憾的是，如果应用程序在设计上不具备可测试性，这可能是唯一可用的方式。 按照章节 X 中所述体系结构原则编写的应用程序应具备单元可测试性，ASP.NET Core 应用程序还支持集成和功能测试。

## <a name="kinds-of-automated-tests"></a>自动测试类型

软件应用程序自动测试具有多种类型。 最简单最低级别的测试是单元测试。 级别稍高的测试包括集成测试和功能测试。 其他类型的测试不在本文讨论范围之内，例如 UI 测试、负载测试、压力测试和版本验收测试。

### <a name="unit-tests"></a>单元测试

单元测试可测试应用程序逻辑的单个部分。 可通过否定列举方式对其进行进一步描述。 单元测试并不测试代码如何处理依赖项或基础结构 - 这是集成测试的用途。 单元测试不测试编写代码所用的框架，你应假定其适用，如果不适用，请报告 bug 并编写代码解决。 单元测试完全在内存或进程中运行。 它不会与文件系统、网络或数据库通信。 单元测试仅测试代码。

因为单元测试仅测试单个代码单元，且无外部依赖项，所以执行速度应该非常快。 因此，可在数秒内运行数百个单元测试的测试套件。 请经常运行单元测试，最好是在每次推送到共享源代码管理存储库前运行，并且请运行生成服务器上每个自动生成。

### <a name="integration-tests"></a>集成测试

尽管建议封装与数据库和文件系统等基础结构交互的代码，但是仍会剩下一些此类代码，你可能需要对其进行测试。 应用程序依赖项完全解析时，还应验证代码层是否按预期方式交互。 这是集成测试的目的。 与单元测试相比，由于集成测试通常依赖外部依赖项和基础结构，因此其设置速度较慢，难度较大。 因此，如果可通过单元测试进行测试，请尽量避免使用集成测试。 如果可通过单元测试测试给定方案，请使用单元测试进行测试。 如果不能，再考虑使用集成测试。

与单元测试相比，集成测试通常具有更复杂的设置和拆卸过程。 例如，针对实际数据库运行的集成测试，在每次运行测试前，需要通过一种方式将数据库返回到已知状态。 随着不断添加新测试以及生产数据库架构不断发展，这些测试脚本的大小和复杂性会逐渐增加。 对于许多大型系统，将签入共享源代码管理更改前，在开发人员工作站上运行一整套集成测试并不实际。 这种情况下，可在生成服务器上运行集成测试。

LocalFileImageService 实现类实现用于从具有如下给定 ID 的特定文件夹提取和返回映像文件字节数的逻辑：

```csharp
public class LocalFileImageService : IImageService
{
    private readonly IHostingEnvironment _env;
    public LocalFileImageService(IHostingEnvironment env)
    {
        _env = env;
    }
    public byte[] GetImageBytesById(int id)
    {
        try
        {
            var contentRoot = _env.ContentRootPath + "//Pics";
            var path = Path.Combine(contentRoot, id + ".png");
            return File.ReadAllBytes(path);
        }
        catch (FileNotFoundException ex)
        {
            throw new CatalogImageMissingException(ex);
        }
    }
}
```

### <a name="functional-tests"></a>功能测试

集成测试从开发者角度编写，用于验证系统的一些组件是否能共同正常运行。 功能测试从用户角度编写，用于基于其要求验证系统的正确性。 下面的节选提供了一个有用的类比，有助于理解功能测试与单元测试的区别：

> “很多时候，开发系统类似于修建房屋。 虽然这个类比并不完全准确，但是我们可将其延伸，用以理解单元测试与功能测试的区别。 单元测试类似于巡查房屋建筑工地的建筑检查员。 建筑检查员专注于房屋的各种内部系统、地基、框架、电路、管道等。 他确保（测试）房屋各部分功能正常且安全，即符合建筑规范。 在这种情景下，功能测试类似于出现在同一建筑工地上的房主。 他假定房屋内部系统一切正常，建筑检查员履行了其检查职责。 房主关心的是住在这个房屋里的体验。 他关心房屋外观如何、每个房间是否大小合适、房屋是否能满足家庭需要，以及窗外是否有好的风景。 也就是说，房主对房屋执行功能测试。 他是站在用户角度。 建筑检察员则是对房屋进行单元测试。 他站在建筑商角度。”

来源：[单元测试与功能测试](http://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html)

我认为：“作为开发人员，我们的失败可能体现在两方面：我们构建应用的方式错误，或者我们的应用不能满足客户需求。” 单元测试可确保构建应用的方式正确；功能测试可确保我们的应用可满足客户需求。

由于功能测试在系统级别运行，所以可能需要一定程度的 UI 自动化。 与集成测试一样，它们通常也适用于某种类型的测试基础结构。 这使其比单元测试和集成测试更慢、更易发生故障。 应仅运行确保系统按用户期望运行所需数量的功能测试。

### <a name="testing-pyramid"></a>测试金字塔

Martin Fowler 提出了测试金字塔概念，如图 9-1 所示。

![](./media/image9-1.png)

图 9-1 测试金字塔

该金字塔的不同层次及其相对大小表示不同的测试类别，以及应为应用程序编写的测试数量。 如图所示，建议以大量单元测试作为基层，中间以较小的集成测试层作为支持，顶端为更小的功能测试层。 理想情况下，每层应仅包含较低层中无法充分执行的测试。 确定特定方案所需的测试类型时，请考虑此测试金字塔。

### <a name="what-to-test"></a>要测试的内容

对缺乏编写自动测试经验的开发人员而言，一个经常遇到的问题是确定测试内容。 不妨从测试条件逻辑开始。 如果方法中包含基于条件语句（if-else、switch 等）更改的行为，应能至少编写数个用于在某些条件下确定行为是否正确的的测试。 如果代码存在错误条件，建议通过代码为“主逻辑”编写至少一个测试（不含任何错误），并为“副逻辑”编写至少一个测试（含错误或非典型结果），以确保应用程序在错误情况下按预期运行。 最后，重点测试可能失败的项，而不是关注代码覆盖率等指标。 一般而言，高代码覆盖率比低代码覆盖率更好。 但是，与仅仅为了改善测试代码覆盖率指标而编写自动属性测试相比，编写复杂的业务关键型方法的测试更有意义。

## <a name="organizing-test-projects"></a>组织测试项目

可按最适合你的方式组织测试项目。 最好按照类型（单元测试和集成测试）以及测试内容（按项目和按命名空间）分离测试。 此分离由单个测试项目内的文件夹构成，还是由多个测试项目构成，这取决于设计决策。 虽然一个项目最为简单，但是对于包含多个测试的大型项目，或者为了更轻松地运行不同测试集，可能需要具有一系列不同的测试项目。 许多团队基于要测试的项目组织测试项目，对于具有很多项目的应用程序而言，这可能导致出现大量测试项目，在根据每个项目中的测试类型进行细分的情况下更是如此。 一种折衷方式是让每个测试类型、每个应用程序具有一个项目，测试项目内的文件夹指示要测试的项目（和类）。

一种常见方式是在“src”文件夹下组织应用程序项目，在平行的“tests”文件夹下组织应用程序的测试项目。 如果你认为这种组织方式有用，可以在 Visual Studio 中创建匹配的解决方案文件夹。

![](./media/image9-2.png)

图 9-2 解决方案中的测试组织

可使用你喜欢的任何测试框架。 xUnit 框架有效运行，编写所有 ASP.NET Core 和 EF Core 测试时皆使用此框架。 可使用图 9-3 中所示的模板或从使用 dotnet new xunit 的 CLI，在 Visual Studio 中添加 xUnit 测试项目。

![](./media/image9-3.png)

图 9-3 在 Visual Studio 中添加 xUnit 测试项目

### <a name="test-naming"></a>测试命名

应当以一致方式命名测试，名称指示每个测试的功能。 我使用的一种很成功的方式是根据其测试的类和方法命名测试类。 虽然这会产生许多小测试类，但是可非常清楚地表明每个测试的作用。 在设置测试类名称以标识待测试类和方法后，测试方法名称可用于指定要测试的行为。 这应包括预期行为以及任何应导致该行为的输入或假设。 部分示例测试名称：

- CatalogControllerGetImage.CallsImageServiceWithId

- CatalogControllerGetImage.LogsWarningGivenImageMissingException

- CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess

- CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException

此方式的一种变体是让每个测试类名称以“Should”结尾，并稍微修改其时态：

- CatalogControllerGetImage**Should**.**Call**ImageServiceWithId

- CatalogControllerGetImage**Should**.**Log**WarningGivenImageMissingException

虽然第二种命名方式略为冗长，但一些团队发现这种命名方式更加清楚。 任何情况下，请使用可提供测试行为见解的命名约定，以便一个或多个测试失败时，可通过其名称清楚了解已失败的事例。 避免使用 ControllerTests.Test1 等模糊的测试名称，因为查看测试结果时，此类名称不能提供任何价值。

如果使用类似上述会产生众多小测试类的命名约定，建议使用文件夹和命名空间进一步组织测试。 图 9-4 显示了一种在数个测试项目内按照文件夹组织测试的方式。

![](./media/image9-4.png)

**图 9-4**。 基于要测试的类按照文件夹组织测试类。

当然，如果特定应用程序类具有多个待测试的方法（以及由此产生的众多测试类），最好将其放置于该应用程序类对应的文件夹中。 该组织方式与在其他情况下将文件组织到文件夹并无差别。 如果一个包含许多其他文件的文件夹中具有三个或四个以上相关文件，最好将其移动到它们自己的子文件夹中。

## <a name="unit-testing-aspnet-core-apps"></a>对 ASP.NET Core 应用执行单元测试

在具有出色设计的 ASP.NET Core 应用程序中，大多数复杂性和业务逻辑会封装在业务实体以及各种服务中。 ASP.NET Core MVC 应用本身及其控制器、筛选器、视图模型和视图需要的单元测试极少。 特定操作的很多功能体现在该操作方法之外。 单元测试不能有效测试路由是否正常运行或测试全局错误。 同样，无法对任何筛选器（包括模型验证筛选器以及身份验证和授权筛选器）执行单元测试。 如果没有这些行为源，大多数操作方法应非常小，这会将其大量工作委托至服务（可独立于使用这些服务的控制器对这些服务执行测试）。

有时为对代码执行单元测试，需要重构代码。 通常，这涉及到确定抽象以及使用依赖项注入来访问待测试代码中的抽象，而不是直接针对基础结构编码。 例如，请思考以下用于显示图像的简单操作方法：

```csharp
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    var contentRoot = _env.ContentRootPath + "//Pics";
    var path = Path.Combine(contentRoot, id + ".png");
    Byte[] b = System.IO.File.ReadAllBytes(path);
    return File(b, "image/png");
}
```

System.IO.File 上的直接依赖项使得对此方法执行单元测试变得困难（它使用 System.IO.File 读取文件系统）。 可测试此行为以确保其按预期方式运行，但对实际文件执行此操作属于集成测试。 请注意，无法测试该方法的路由。稍后我们将了解如何通过功能测试快速执行此操作。

如果无法直接对文件系统行为执行单元测试，且无法测试路由，还能测试什么呢？ 通过重构确保单元测试的可行性后，可能会发现一些测试用例以及缺失行为，例如错误处理。 如未找到文件，此方法会执行什么操作？ 它应执行什么操作？ 本示例中，重构方法如下：

```csharp
[HttpGet("[controller]/pic/{id}")\]
public IActionResult GetImage(int id)
{
    byte[] imageBytes;
    try
    {
        imageBytes = _imageService.GetImageBytesById(id);
    }
    catch (CatalogImageMissingException ex)
    {
        _logger.LogWarning($"No image found for id: {id}");
        return NotFound();
    }
    return File(imageBytes, "image/png");
}
```

\_logger 和 \_imageService 皆作为依赖项注入。 现在，可测试是否传递到操作方法的相同 ID 被传递到 \_imageService，以及生成的字节是否作为 FileResult 的一部分返回。 还可测试错误日志记录是否按预期发生，以及如果映像缺失，是否返回 NotFound 结果（假定这是重要的应用程序行为，即不只是开发人员为诊断问题而添加的临时代码）。 已将实际文件逻辑移动到单独的实现服务，并已将其扩充，以在缺失文件的情况下返回特定于应用程序的异常。 可使用集成测试独立测试该实现。

## <a name="integration-testing-aspnet-core-apps"></a>对 ASP.NET Core 应用执行集成测试

该服务使用 IHostingEnvironment，正如 CatalogController 代码在重构到单独服务中前一样。 由于这是使用 IHostingEnvironment 的控制器中的唯一代码，该依赖项已从 CatalogController 的构造函数中移除。

若要测试该服务是否正常运行，需要创建一个已知测试映像文件，并验证该服务是否在特定输入下返回该文件。 请注意，勿将 mock 对象用于实际需要测试的行为（本例中为从文件系统读取）。 但是，mock 对象在设置集成测试时依然有用。 这种情况下，可以模拟 IHostingEnvironment，使其 ContentRootPath 指向要用于测试映像的文件夹。 以下是完整的工作集成测试类：

```csharp
public class LocalFileImageServiceGetImageBytesById
{
    private byte[] _testBytes = new byte[] { 0x01, 0x02, 0x03 };
    private readonly Mock<IHostingEnvironment> _mockEnvironment = new Mock<IHostingEnvironment>();
    private int _testImageId = 123;
    private string _testFileName = "123.png";
    public LocalFileImageServiceGetImageBytesById()
    {
        // create folder if necessary
        Directory.CreateDirectory(Path.Combine(GetFileDirectory(), "Pics"));
        string filePath = GetFilePath(_testFileName);
        System.IO.File.WriteAllBytes(filePath, _testBytes);
        _mockEnvironment.SetupGet<string>(m => m.ContentRootPath).Returns(GetFileDirectory());
    }
    private string GetFilePath(string fileName)
    {
        return Path.Combine(GetFileDirectory(), "Pics", fileName);
        }
            private string GetFileDirectory()
        {
            var location = System.Reflection.Assembly.GetEntryAssembly().Location;
            return Path.GetDirectoryName(location);
        }

        [Fact]
        public void ReturnsFileContentResultGivenValidId()
        {
            var fileService = new LocalFileImageService(_mockEnvironment.Object);
            var result = fileService.GetImageBytesById(_testImageId);
            Assert.Equal(_testBytes, result);
        }
    }
```

> [!NOTE]
> 测试本身非常简单，需要大量代码配置系统和创建测试基础结构（本例中是要从磁盘读取的实际文件）。 这对集成测试而言很常见，因为与单元测试相比，集成测试通常需要更复杂的设置。

## <a name="functional-testing-aspnet-core-apps"></a>对 ASP.NET Core 应用执行功能测试

对于 ASP.NET Core 应用程序，TestServer 类让编写功能测试非常容易。 使用 WebHostBuilder 配置 TestServer，这与通常为应用程序执行的操作相同。 虽然应像应用程序的实际主机那样配置该 WebHostBuilder，但是可以修改任何方面，以便使测试更加轻松。 大多数情况下，会对多个测试用例重复使用相同 TestServer，所以可使用可重用方法对其进行封装（可能在基类中）：

```csharp
public abstract class BaseWebTest
{
    protected readonly HttpClient _client;
    protected string _contentRoot;

    public BaseWebTest()
    {
        _client = GetClient();
    }

    protected HttpClient GetClient()
    {
        var startupAssembly = typeof(Startup).GetTypeInfo().Assembly;
        _contentRoot = GetProjectPath("src", startupAssembly);
        var builder = new WebHostBuilder()
        .UseContentRoot(_contentRoot)
        .UseStartup<Startup>();
        var server = new TestServer(builder);
        var client = server.CreateClient();
        return client;
    }
}
```

GetProjectPath 方法仅返回 Web 项目的物理路径（下载示例解决方案）。 本例中的 WebHostBuilder 仅指定 Web 应用程序的内容根的位置，并引用实际 Web 应用程序所使用的同一启动类。 若要使用 TestServer，请用标准 System.Net.HttpClient 类型对其发出请求。 TestServer 会公开一个有用的 CreateClient 方法，该方法提供可向 TestServer 上运行的应用程序发出请求的预配置客户端。 为 ASP.NET Core 应用程序编写功能测试时会用到此客户端（上述基测试中设置为受保护的 \_client 成员）：

```csharp
public class CatalogControllerGetImage : BaseWebTest
{
    [Fact]
    public async Task ReturnsFileContentResultGivenValidId()
    {
        var testFilePath = Path.Combine(_contentRoot, "pics//1.png");
        var expectedFileBytes = File.ReadAllBytes(testFilePath);
        var response = await _client.GetAsync("/catalog/pic/1");
        response.EnsureSuccessStatusCode();
        var streamResponse = await response.Content.ReadAsStreamAsync();
        byte[] byteResult;
        using (var ms = new MemoryStream())
        {
            streamResponse.CopyTo(ms);
            byteResult = ms.ToArray();
        }
        Assert.Equal(expectedFileBytes, byteResult);
    }
}
```

该功能测试执行完整的 ASP.NET Core MVC 应用程序堆栈，包括所有中间件、筛选器、绑定器等。 它验证特定路由（“/catalog/pic/1”）是否返回已知位置中文件的预期字节数组。 它无需设置实际 Web 服务器即可实现该操作，因此可避免使用实际 Web 服务器进行测试可能遇到的许多问题（例如防火墙设置问题）。 虽然针对 TestServer 运行的功能测试通常比集成测试和单元测试更慢，但是比测试 Web 服务器的网络上运行的测试速度更快。

>[!div class="step-by-step"]
[上一页](work-with-data-in-asp-net-core-apps.md)
[下一页](development-process-for-azure.md)
