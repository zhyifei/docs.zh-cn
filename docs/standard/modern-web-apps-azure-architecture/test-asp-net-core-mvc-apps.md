---
title: "测试 ASP.NET Core MVC 应用程序"
description: "设计使用 ASP.NET Core 和 Azure 的现代 Web 应用程序 |测试 ASP.NET Core MVC 应用程序"
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d23d0accc33fb8335dff602d6e1d6c8689972906
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="test-aspnet-core-mvc-apps"></a>测试 ASP.NET Core MVC 应用程序

> _"如果你不喜欢单元测试您的产品，最有可能你的客户不会喜欢对其进行测试，或者。"_
> _-匿名-

## <a name="summary"></a>摘要

软件的任何复杂性可能会以意外的方式，以响应更改失败。 因此，进行更改后需测试，除了最不重要的 （或严重程度最低的） 应用程序。 手动测试时速度最慢，最不可靠成本最高的方式，以测试软件。 遗憾的是，如果应用程序未设计可测试性而言，它可以是可用的唯一方法。 X 一章中编写的以下的体系结构原则布局的应用程序应为单元可测试性和 ASP.NET Core 应用程序支持自动的集成和功能以及测试。

## <a name="kinds-of-automated-tests"></a>类型的自动测试

有许多种软件应用程序的自动测试。 最简单最低级别的测试是单元测试。 稍有更高的级别有集成测试和功能测试。 其他类型的测试，如 UI 测试、 负载测试、 压力测试和冒烟测试，不在本文的讨论范围之内。

### <a name="unit-tests"></a>单元测试

单元测试测试单个部件的应用程序的逻辑。 一个进一步可以通过列出的一些操作，它不描述它。 单元测试不会测试你的代码适用于依赖关系或基础结构 – 即哪些集成测试的适用于。 单元测试不会测试编写代码的框架 – 你应假定它的工作或，如果你认为不、 bug 和一种解决方法的代码。 单元测试完全运行在内存和进程中。 它不与文件系统、 网络或数据库进行通信。 单元测试应仅测试你的代码。

单元测试，因为他们测试单个单元的代码中，没有外部依赖项，事实应非常快地执行。 因此，你应能够在几秒钟中运行的数百个单元测试的测试套件。 它们通常情况下，理想情况下每个推送到共享的源控件存储库，和当然，如果使用每次自动生成前生成的服务器上运行。

### <a name="integration-tests"></a>集成测试

尽管它是一个封装与如数据库和文件系统的基础结构交互你代码的好办法，但你仍将该代码的一部分，并且你将可能想对其进行测试。 此外，你应验证你的代码的层交互按预期完全解析你的应用程序依赖关系时。 这是集成测试的责任。 集成测试往往速度较慢且更难设置比单元测试，因为它们通常依赖于外部依赖关系和基础结构。 因此，应避免测试可能具有单元测试集成测试的测试的操作。 如果可以使用单元测试来测试给定的方案，你应测试它与单元测试。 如果你不能则可以考虑使用的集成测试。

集成测试通常将具有更复杂的设置和拆卸过程而不是单元测试。 例如，有违实际的数据库的集成测试将需要一种方法，以将该数据库返回到每个测试运行之前已知的状态。 当添加新测试，并且生产数据库架构发生变化，这些脚本将可能因不断增长在大小和复杂性方面的测试。 在许多大型系统中，是不实际更改共享的源代码管理签入之前在开发工作站上运行的集成测试的完整套件。 在这些情况下，可能会在生成服务器上运行集成测试。

LocalFileImageService 实现类实现进行提取并返回从给定 id 的特定文件夹的图像文件的字节的逻辑：

```cs
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
```

### <a name="functional-tests"></a>功能测试

从开发人员，以验证系统的某些组件正常会在一起的角度编写的集成测试。 功能测试编写从用户的角度来看，并验证系统根据其需求的正确性。 以下摘录内容中提供了一个有用的类比，有关如何考虑功能测试，相比单元测试：

> "开发系统的很多时候被比作的建筑构建。 虽然此类比不完全正确，我们可以为了了解单元和功能测试之间的差异来扩展它。 单元测试功能类似于访问的建筑构造站点构建检查器。 他侧重于内部，foundation，组帧、 电力、 管线，等的各种内部系统。 他可确保 （测试） 将正常工作的内部部件，并已将其安全地，即满足生成代码。 在此方案中的功能测试是类似于访问此相同的构造站点户主。 他假定该内部系统的适当地表现，构建检查器正在执行其任务。 户主侧重于它将哪些如在此内部存活。 他致力于内部的外观，包括各种文件室-喜欢大小、 house 是否适合系列的需求，是捕获早上 sun 最佳场所中的窗口。 户主在内部执行功能测试。 他有用户的角度来看。 生成检查器在内部执行单元测试。 他有生成器的透视"。

源：[单元测试与功能测试](http://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html)

我最喜欢表达的"作为开发人员，我们失败两种方式： 我们生成错误，操作或我们生成错误的操作。" 单元测试确保要生成的操作权限;功能测试确保要生成正确的操作。

在系统级别运行功能测试，因为它们可能需要某种程度的 UI 自动化。 集成与测试一样，它们通常会使用某种类型的测试基础结构。 这使它们更慢且更加脆弱比单元和集成测试。 应仅具有以确信系统是否按用户预期方式运行所需的任意多个功能测试。

### <a name="testing-pyramid"></a>测试棱锥图

Martin Fowler 编写了有关测试棱锥图，它的一个示例显示图 9-1。

![](./media/image9-1.png)

图 9-1 测试棱锥图

不同层的棱锥图和其相对大小，表示不同类型的测试和多少应编写你的应用程序。 如你所见，建议是让有大量的单元测试，支持通过集成测试变得更小层的功能测试的较小的层。 每个层理想情况下仅应有测试中它无法在较低层充分地执行。 当你尝试决定特定方案需要哪种类型的测试时，请记住测试棱锥图。

### <a name="what-to-test"></a>要测试的内容

常见的问题的开发人员是编写自动化的测试缺乏经验即将与要测试的内容。 很好的起点是测试条件逻辑。 必须具有更改基于条件语句的行为的方法的任意位置 （如果其他切换，等），你应该能够提出至少几个用于确认正确的行为在某些情况。 如果代码有错误条件，最好是编写 （而不会错误），至少一个测试通过代码的"高兴路径"和"很遗憾路径"的至少一个测试 （出现错误或非典型结果） 以确认你的应用程序行为与预期在遇到错误时相同。 最后，尝试重点测试可能会失败的操作，而不是将重点放在代码覆盖率等度量值。 更多的代码覆盖率是通常小于，更好。 但是，编写非常复杂，且业务关键型方法的几个更多测试通常是时间的更好地使用比编写针对自动属性只是时间的为了改进测试代码覆盖率度量值的测试。

## <a name="organizing-test-projects"></a>组织测试项目

但是，为你的工作原理最佳可以组织测试项目。 它是单独的测试以及他们正在测试的 （按项目、 命名空间） 按类型 （集成测试中的单元测试） 和一个好办法。 这种分离是否包含在一个测试项目或多个测试项目中的文件夹是一项设计决策。 其中一个项目是最简单，但适用于大型项目具有多项测试，或者为了更轻松地运行不同的测试集，你可能想要有几个不同的测试项目。 许多团队组织基于他们正在测试的测试，这使应用程序具有多个少数几个项目中可能会导致大量的测试项目中，尤其是如果你仍将这些分解根据类型的测试的每个项目中的项目的测试项目。 泄漏方法是测试的让每一种，每个应用程序，使用在测试项目，以指示所测试的项目 （和类） 的文件夹的一个项目。

常见方法是用于组织 src 文件夹下的应用程序项目和并行的测试文件夹下的应用程序的测试项目。 如果你发现此组织很有用，可以在 Visual Studio 中，创建匹配的解决方案文件夹。

![](./media/image9-2.png)

图 9-2 测试组织你的解决方案中

你可以使用任何您喜欢的测试框架。 XUnit 框架可以有效地工作，并就是用编写的所有 ASP.NET Core 和 EF 核心的测试。 在 Visual Studio 中使用显示在图 9-3 中，或从 CLI 使用 dotnet 新 xunit 的模板，可以添加 xUnit 测试项目。

![](./media/image9-3.png)

图 9-3 添加 xUnit Visual Studio 中的测试项目

### <a name="test-naming"></a>测试命名

具有名称指明了每个测试的用途，应名称以一致的方式，测试。 我使用了与巨大成功的一种方法是对名称根据类和方法他们正在测试的测试类。 这会导致许多小测试类，但它有助于极清除每个测试是负责。 与测试的类名称，将设置为标识的类和要测试的方法，可以使用测试方法名称指定所测试的行为。 这应包括的预期的行为任何输入或应产生此行为的假设。 一些示例测试名称：

-   CatalogControllerGetImage.CallsImageServiceWithId

-   CatalogControllerGetImage.LogsWarningGivenImageMissingException

-   CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess

-   CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException

此方法的变体结束"应该"每个测试类名称，并修改时态略有：

-   CatalogControllerGetImage**Should**.**Call**ImageServiceWithId

-   CatalogControllerGetImage**Should**.**Log**WarningGivenImageMissingException

一些团队发现的第二个命名的方法更清晰、 但略有更详细。 在任何情况下，尝试使用深入了解测试行为的命名约定，因此当一个或多个测试失败时，很明显来自失败何种情况下其名称。 避免命名你的测试有一个大致，如 ControllerTests.Test1，因为当你在测试结果中看到它们时，这些不提供任何值。

如果你遵循命名约定，如上面的产生许多小测试类，它是一个好办法进一步组织你的测试使用文件夹和命名空间。 图 9-4 显示组织中多个测试项目文件夹中测试的一种方法。

![](./media/image9-4.png)

**图 9-4。** 组织测试类基于类所测试的文件夹。

当然，如果特定应用程序类具有许多所测试的方法 （并且因此多测试类），可能有意义将这些应用程序类所对应的文件夹中。 此组织是如何在到其他位置的文件夹可能组织文件没有什么不同。 如果你有多个三个或四个相关包含很多其他文件的文件夹中的文件，它很有帮助，以将它们移到其自己的子文件夹。

## <a name="unit-testing-aspnet-core-apps"></a>单元测试 ASP.NET Core 应用

在设计良好的 ASP.NET Core 应用程序中，大部分的复杂性和业务逻辑将封装在业务实体和各种服务中。 ASP.NET 核心 MVC 应用程序本身，其控制器、 筛选器、 viewmodel 和视图，应要求极少的单元测试。 某个给定操作的功能大部分位于外部的操作方法本身。 测试是否路由正常运行，或全局错误处理，不能完成有效地与单元测试。 同样，任何筛选器，包括模型验证和身份验证和授权筛选器，不能为单元测试。 没有这些源的行为，大多数操作方法应非常小，委托可以测试独立于使用它们的控制器的服务到其工作的大容量。

有时，你将需要的重构到单元测试的代码中的排列它。 这通常涉及到标识抽象和依赖关系注入用于访问的抽象在代码中你想要测试，而不是直接根据基础结构的编码。 例如，考虑此相当简单的操作方法，用于显示图像：

```cs
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    var contentRoot = _env.ContentRootPath + "//Pics";
    var path = Path.Combine(contentRoot, id + ".png");
    Byte[] b = System.IO.File.ReadAllBytes(path);
    return File(b, "image/png");
}
```

困难上 System.IO.File，它使用从文件系统读取其直接的依赖关系进行单元测试此方法。 你可以测试此行为，以确保它按预期方式工作，但这样的实际文件是一种集成测试。 值得注意不能测试此方法的路由 – 你将看到如何执行此操作与一个功能测试将很快。

如果你不能单元测试文件系统行为直接，并且不能测试路由，什么是存在以测试？ 嗯，重构以使单元测试成为可能后, 您可能会发现一些测试用例和缺少的行为，例如错误处理。 该方法作用是什么时未找到的文件？ 它应该做什么？ 在此示例中，已重构的方法如下所示：

```cs
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

\_记录器和\_imageService 被注入依赖关系。 现在你可以测试该传递给的操作方法的相同 id 传递到\_imageService，并且所产生的字节返回 FileResult 的一部分。 你还可以测试，错误日志记录发生的情况按预期方式运行，如果映像已丢失，则返回 NotFound 结果假设这重要的应用程序行为 （即，不只是临时代码开发人员添加用于诊断问题）。 实际文件逻辑已移动到一个单独实现服务，以及已扩充以返回特定于应用程序异常对于缺少的文件的情况。 你可以测试此实现独立，使用的集成测试。

## <a name="integration-testing-aspnet-core-apps"></a>集成测试 ASP.NET Core 应用

```cs
    }
        catch (FileNotFoundException ex)
        {
            throw new CatalogImageMissingException(ex);
        }
    }
}
```

此服务使用 IHostingEnvironment，就像代码未重构到一个单独的服务之前 CatalogController。 由于是在使用 IHostingEnvironment 控制器中的唯一代码，该依赖项已从 CatalogController 的构造函数。

若要测试此服务工作正常，你需要创建一个已知的测试的映像文件和验证，服务将返回它提供特定的输入。 你应注意不是在你确实想要测试 （在此情况下，从文件系统读取） 的行为上使用模拟的对象。 但是，模拟对象仍可能会很有用设置集成测试。 在这种情况下，你可以模拟 IHostingEnvironment，以便其 ContentRootPath 指向你要用于测试映像的文件夹。 完成工作的集成测试的类如下所示：

```cs
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
> 测试本身是非常简单 – 大多数代码则需要配置系统并创建的测试的基础结构 （在这种情况下，实际文件中要从磁盘读取）。 这是典型的集成测试，通常需要更复杂的安装程序工作比单元测试。

## <a name="functional-testing-aspnet-core-apps"></a>功能来测试 ASP.NET Core 应用

对于 ASP.NET Core 应用程序，TestServer 类，使功能测试非常易于编写。 就像通常对你的应用程序所做配置使用 WebHostBuilder TestServer。 此 WebHostBuilder 应配置一样应用程序的实际主机，但可以修改简化测试它的任何方面。 大多数情况下，您将重新使用相同 TestServer 许多测试用例，因此你可以将其封装中的可重用方法 （可能是中的基类）：

```cs
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
        .UseStartup&lt;Startup&gt;();
        var server = new TestServer(builder);
        var client = server.CreateClient();
        return client;
    }
}
```

GetProjectPath 方法只需返回到 web 项目 （下载示例解决方案） 的物理路径。 WebHostBuilder 在这种情况下只需指定 web 应用程序内容的根，其中引用同一个实际的 web 应用程序使用的启动类。 若要使用 TestServer，你使用的标准 System.Net.HttpClient 类型以使对它发出的请求。 TestServer 公开一个提供已准备好在 TestServer 上运行的应用程序发出请求的预配置客户端的有用 CreateClient 方法。 使用此客户端 (设置为受保护\_上述基础的测试上的客户端成员) 编写 ASP.NET Core 应用程序的功能测试时：

```cs
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

此功能的测试执行完整的 ASP.NET 核心 MVC 应用程序堆栈，包括所有中间件、 筛选器、 联编程序、 可能处于的位置等。 它验证给定的路由 （"/ 目录/pic/1"） 返回的文件的预期的字节数组中的已知位置。 它这样做无需设置实际的 web 服务器，并因此可避免很多易，使用实际的 web 服务器进行测试可以体验 （例如，其防火墙设置的问题）。 TestServer 针对运行的功能测试通常比集成和单元测试，要慢，但要大大快于通过网络与测试 web 服务器将运行的测试。

>[!div class="step-by-step"]
[以前](work-with-data-in-asp-net-core-apps.md) [下一步] (开发-过程-为-azure.md)
