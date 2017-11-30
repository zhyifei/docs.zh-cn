---
title: "测试 ASP.NET Core MVC 应用程序"
description: "设计使用 ASP.NET Core 和 Azure 的现代 Web 应用程序 |测试 ASP.NET Core MVC 应用程序"
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 4611ffa8334e124946e849306d3281b695830eb1
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2017
---
# <a name="test-aspnet-core-mvc-apps"></a><span data-ttu-id="b0263-103">测试 ASP.NET Core MVC 应用程序</span><span class="sxs-lookup"><span data-stu-id="b0263-103">Test ASP.NET Core MVC Apps</span></span>

> <span data-ttu-id="b0263-104">_"如果你不喜欢单元测试您的产品，最有可能你的客户不会喜欢对其进行测试，或者。"_</span><span class="sxs-lookup"><span data-stu-id="b0263-104">_"If you don't like unit testing your product, most likely your customers won't like to test it, either."_</span></span>
> <span data-ttu-id="b0263-105">_-匿名-</span><span class="sxs-lookup"><span data-stu-id="b0263-105">_- Anonymous-</span></span>

## <a name="summary"></a><span data-ttu-id="b0263-106">摘要</span><span class="sxs-lookup"><span data-stu-id="b0263-106">Summary</span></span>

<span data-ttu-id="b0263-107">软件的任何复杂性可能会以意外的方式，以响应更改失败。</span><span class="sxs-lookup"><span data-stu-id="b0263-107">Software of any complexity can fail in unexpected ways in response to changes.</span></span> <span data-ttu-id="b0263-108">因此，进行更改后需测试，除了最不重要的 （或严重程度最低的） 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b0263-108">Thus, testing after making changes is required for all but the most trivial (or least critical) applications.</span></span> <span data-ttu-id="b0263-109">手动测试时速度最慢，最不可靠成本最高的方式，以测试软件。</span><span class="sxs-lookup"><span data-stu-id="b0263-109">Manual testing is the slowest, least reliable, most expensive way to test software.</span></span> <span data-ttu-id="b0263-110">遗憾的是，如果应用程序未设计可测试性而言，它可以是可用的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="b0263-110">Unfortunately, if applications are not designed to be testable, it can be the only means available.</span></span> <span data-ttu-id="b0263-111">X 一章中编写的以下的体系结构原则布局的应用程序应为单元可测试性和 ASP.NET Core 应用程序支持自动的集成和功能以及测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-111">Applications written following the architectural principles laid out in chapter X should be unit testable, and ASP.NET Core applications support automated integration and functional testing as well.</span></span>

## <a name="kinds-of-automated-tests"></a><span data-ttu-id="b0263-112">类型的自动测试</span><span class="sxs-lookup"><span data-stu-id="b0263-112">Kinds of Automated Tests</span></span>

<span data-ttu-id="b0263-113">有许多种软件应用程序的自动测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-113">There are many kinds of automated tests for software applications.</span></span> <span data-ttu-id="b0263-114">最简单最低级别的测试是单元测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-114">The simplest, lowest level test is the unit test.</span></span> <span data-ttu-id="b0263-115">稍有更高的级别有集成测试和功能测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-115">At a slightly higher level there are integration tests and functional tests.</span></span> <span data-ttu-id="b0263-116">其他类型的测试，如 UI 测试、 负载测试、 压力测试和冒烟测试，不在本文的讨论范围之内。</span><span class="sxs-lookup"><span data-stu-id="b0263-116">Other kinds of tests, like UI tests, load tests, stress tests, and smoke tests, are beyond the scope of this document.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="b0263-117">单元测试</span><span class="sxs-lookup"><span data-stu-id="b0263-117">Unit Tests</span></span>

<span data-ttu-id="b0263-118">单元测试测试单个部件的应用程序的逻辑。</span><span class="sxs-lookup"><span data-stu-id="b0263-118">A unit test tests a single part of your application's logic.</span></span> <span data-ttu-id="b0263-119">一个进一步可以通过列出的一些操作，它不描述它。</span><span class="sxs-lookup"><span data-stu-id="b0263-119">One can further describe it by listing some of the things that it isn't.</span></span> <span data-ttu-id="b0263-120">单元测试不会测试你的代码适用于依赖关系或基础结构 – 即哪些集成测试的适用于。</span><span class="sxs-lookup"><span data-stu-id="b0263-120">A unit test doesn't test how your code works with dependencies or infrastructure – that's what integration tests are for.</span></span> <span data-ttu-id="b0263-121">单元测试不会测试编写代码的框架 – 你应假定它的工作或，如果你认为不、 bug 和一种解决方法的代码。</span><span class="sxs-lookup"><span data-stu-id="b0263-121">A unit test doesn't test the framework your code is written on – you should assume it works or, if you find it doesn't, file a bug and code a workaround.</span></span> <span data-ttu-id="b0263-122">单元测试完全运行在内存和进程中。</span><span class="sxs-lookup"><span data-stu-id="b0263-122">A unit test runs completely in memory and in process.</span></span> <span data-ttu-id="b0263-123">它不与文件系统、 网络或数据库进行通信。</span><span class="sxs-lookup"><span data-stu-id="b0263-123">It doesn't communicate with the file system, the network, or a database.</span></span> <span data-ttu-id="b0263-124">单元测试应仅测试你的代码。</span><span class="sxs-lookup"><span data-stu-id="b0263-124">Unit tests should only test your code.</span></span>

<span data-ttu-id="b0263-125">单元测试，因为他们测试单个单元的代码中，没有外部依赖项，事实应非常快地执行。</span><span class="sxs-lookup"><span data-stu-id="b0263-125">Unit tests, by virtue of the fact that they test only a single unit of your code, with no external dependencies, should execute extremely quickly.</span></span> <span data-ttu-id="b0263-126">因此，你应能够在几秒钟中运行的数百个单元测试的测试套件。</span><span class="sxs-lookup"><span data-stu-id="b0263-126">Thus, you should be able to run test suites of hundreds of unit tests in a few seconds.</span></span> <span data-ttu-id="b0263-127">它们通常情况下，理想情况下每个推送到共享的源控件存储库，和当然，如果使用每次自动生成前生成的服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="b0263-127">Run them frequently, ideally before every push to a shared source control repository, and certainly with every automated build on your build server.</span></span>

### <a name="integration-tests"></a><span data-ttu-id="b0263-128">集成测试</span><span class="sxs-lookup"><span data-stu-id="b0263-128">Integration Tests</span></span>

<span data-ttu-id="b0263-129">尽管它是一个封装与如数据库和文件系统的基础结构交互你代码的好办法，但你仍将该代码的一部分，并且你将可能想对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-129">Although it's a good idea to encapsulate your code that interacts with infrastructure like databases and file systems, you will still have some of that code, and you will probably want to test it.</span></span> <span data-ttu-id="b0263-130">此外，你应验证你的代码的层交互按预期完全解析你的应用程序依赖关系时。</span><span class="sxs-lookup"><span data-stu-id="b0263-130">Additionally, you should verify that your code's layers interact as you expect when your application's dependencies are fully resolved.</span></span> <span data-ttu-id="b0263-131">这是集成测试的责任。</span><span class="sxs-lookup"><span data-stu-id="b0263-131">This is the responsibility of integration tests.</span></span> <span data-ttu-id="b0263-132">集成测试往往速度较慢且更难设置比单元测试，因为它们通常依赖于外部依赖关系和基础结构。</span><span class="sxs-lookup"><span data-stu-id="b0263-132">Integration tests tend to be slower and more difficult to set up than unit tests, because they often depend on external dependencies and infrastructure.</span></span> <span data-ttu-id="b0263-133">因此，应避免测试可能具有单元测试集成测试的测试的操作。</span><span class="sxs-lookup"><span data-stu-id="b0263-133">Thus, you should avoid testing things that could be tests with unit tests in integration tests.</span></span> <span data-ttu-id="b0263-134">如果可以使用单元测试来测试给定的方案，你应测试它与单元测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-134">If you can test a given scenario with a unit test, you should test it with a unit test.</span></span> <span data-ttu-id="b0263-135">如果你不能则可以考虑使用的集成测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-135">If you can't, then consider using an integration test.</span></span>

<span data-ttu-id="b0263-136">集成测试通常将具有更复杂的设置和拆卸过程而不是单元测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-136">Integration tests will often have more complex setup and teardown procedures than unit tests.</span></span> <span data-ttu-id="b0263-137">例如，有违实际的数据库的集成测试将需要一种方法，以将该数据库返回到每个测试运行之前已知的状态。</span><span class="sxs-lookup"><span data-stu-id="b0263-137">For example, an integration test that goes against an actual database will need a way to return the database to a known state before each test run.</span></span> <span data-ttu-id="b0263-138">当添加新测试，并且生产数据库架构发生变化，这些脚本将可能因不断增长在大小和复杂性方面的测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-138">As new tests are added and the production database schema evolves, these test scripts will tend to grow in size and complexity.</span></span> <span data-ttu-id="b0263-139">在许多大型系统中，是不实际更改共享的源代码管理签入之前在开发工作站上运行的集成测试的完整套件。</span><span class="sxs-lookup"><span data-stu-id="b0263-139">In many large systems, it is impractical to run full suites of integration tests on developer workstations before checking in changes to shared source control.</span></span> <span data-ttu-id="b0263-140">在这些情况下，可能会在生成服务器上运行集成测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-140">In these cases, integration tests may be run on a build server.</span></span>

<span data-ttu-id="b0263-141">LocalFileImageService 实现类实现进行提取并返回从给定 id 的特定文件夹的图像文件的字节的逻辑：</span><span class="sxs-lookup"><span data-stu-id="b0263-141">The LocalFileImageService implementation class implements the logic for fetching and returning the bytes of an image file from a particular folder given an id:</span></span>

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

### <a name="functional-tests"></a><span data-ttu-id="b0263-142">功能测试</span><span class="sxs-lookup"><span data-stu-id="b0263-142">Functional Tests</span></span>

<span data-ttu-id="b0263-143">从开发人员，以验证系统的某些组件正常会在一起的角度编写的集成测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-143">Integration tests are written from the perspective of the developer, to verify that some components of the system work correctly together.</span></span> <span data-ttu-id="b0263-144">功能测试编写从用户的角度来看，并验证系统根据其需求的正确性。</span><span class="sxs-lookup"><span data-stu-id="b0263-144">Functional tests are written from the perspective of the user, and verify the correctness of the system based on its requirements.</span></span> <span data-ttu-id="b0263-145">以下摘录内容中提供了一个有用的类比，有关如何考虑功能测试，相比单元测试：</span><span class="sxs-lookup"><span data-stu-id="b0263-145">The following excerpt offers a useful analogy for how to think about functional tests, compared to unit tests:</span></span>

> <span data-ttu-id="b0263-146">"开发系统的很多时候被比作的建筑构建。</span><span class="sxs-lookup"><span data-stu-id="b0263-146">"Many times the development of a system is likened to the building of a house.</span></span> <span data-ttu-id="b0263-147">虽然此类比不完全正确，我们可以为了了解单元和功能测试之间的差异来扩展它。</span><span class="sxs-lookup"><span data-stu-id="b0263-147">While this analogy isn't quite correct, we can extend it for the purposes of understanding the difference between unit and functional tests.</span></span> <span data-ttu-id="b0263-148">单元测试功能类似于访问的建筑构造站点构建检查器。</span><span class="sxs-lookup"><span data-stu-id="b0263-148">Unit testing is analogous to a building inspector visiting a house's construction site.</span></span> <span data-ttu-id="b0263-149">他侧重于内部，foundation，组帧、 电力、 管线，等的各种内部系统。</span><span class="sxs-lookup"><span data-stu-id="b0263-149">He is focused on the various internal systems of the house, the foundation, framing, electrical, plumbing, and so on.</span></span> <span data-ttu-id="b0263-150">他可确保 （测试） 将正常工作的内部部件，并已将其安全地，即满足生成代码。</span><span class="sxs-lookup"><span data-stu-id="b0263-150">He ensures (tests) that the parts of the house will work correctly and safely, that is, meet the building code.</span></span> <span data-ttu-id="b0263-151">在此方案中的功能测试是类似于访问此相同的构造站点户主。</span><span class="sxs-lookup"><span data-stu-id="b0263-151">Functional tests in this scenario are analogous to the homeowner visiting this same construction site.</span></span> <span data-ttu-id="b0263-152">他假定该内部系统的适当地表现，构建检查器正在执行其任务。</span><span class="sxs-lookup"><span data-stu-id="b0263-152">He assumes that the internal systems will behave appropriately, that the building inspector is performing his task.</span></span> <span data-ttu-id="b0263-153">户主侧重于它将哪些如在此内部存活。</span><span class="sxs-lookup"><span data-stu-id="b0263-153">The homeowner is focused on what it will be like to live in this house.</span></span> <span data-ttu-id="b0263-154">他致力于内部的外观，包括各种文件室-喜欢大小、 house 是否适合系列的需求，是捕获早上 sun 最佳场所中的窗口。</span><span class="sxs-lookup"><span data-stu-id="b0263-154">He is concerned with how the house looks, are the various rooms a comfortable size, does the house fit the family's needs, are the windows in a good spot to catch the morning sun.</span></span> <span data-ttu-id="b0263-155">户主在内部执行功能测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-155">The homeowner is performing functional tests on the house.</span></span> <span data-ttu-id="b0263-156">他有用户的角度来看。</span><span class="sxs-lookup"><span data-stu-id="b0263-156">He has the user's perspective.</span></span> <span data-ttu-id="b0263-157">生成检查器在内部执行单元测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-157">The building inspector is performing unit tests on the house.</span></span> <span data-ttu-id="b0263-158">他有生成器的透视"。</span><span class="sxs-lookup"><span data-stu-id="b0263-158">He has the builder's perspective."</span></span>

<span data-ttu-id="b0263-159">源：[单元测试与功能测试](http://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html)</span><span class="sxs-lookup"><span data-stu-id="b0263-159">Source: [Unit Testing versus Functional Tests](http://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html)</span></span>

<span data-ttu-id="b0263-160">我最喜欢表达的"作为开发人员，我们失败两种方式： 我们生成错误，操作或我们生成错误的操作。"</span><span class="sxs-lookup"><span data-stu-id="b0263-160">I'm fond of saying "As developers, we fail in two ways: we build the thing wrong, or we build the wrong thing."</span></span> <span data-ttu-id="b0263-161">单元测试确保要生成的操作权限;功能测试确保要生成正确的操作。</span><span class="sxs-lookup"><span data-stu-id="b0263-161">Unit tests ensure you are building the thing right; functional tests ensure you are building the right thing.</span></span>

<span data-ttu-id="b0263-162">在系统级别运行功能测试，因为它们可能需要某种程度的 UI 自动化。</span><span class="sxs-lookup"><span data-stu-id="b0263-162">Since functional tests operate at the system level, they may require some degree of UI automation.</span></span> <span data-ttu-id="b0263-163">集成与测试一样，它们通常会使用某种类型的测试基础结构。</span><span class="sxs-lookup"><span data-stu-id="b0263-163">Like integration tests, they usually work with some kind of test infrastructure as well.</span></span> <span data-ttu-id="b0263-164">这使它们更慢且更加脆弱比单元和集成测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-164">This makes them slower and more brittle than unit and integration tests.</span></span> <span data-ttu-id="b0263-165">应仅具有以确信系统是否按用户预期方式运行所需的任意多个功能测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-165">You should have only as many functional tests as you need to be confident the system is behaving as users expect.</span></span>

### <a name="testing-pyramid"></a><span data-ttu-id="b0263-166">测试棱锥图</span><span class="sxs-lookup"><span data-stu-id="b0263-166">Testing Pyramid</span></span>

<span data-ttu-id="b0263-167">Martin Fowler 编写了有关测试棱锥图，它的一个示例显示图 9-1。</span><span class="sxs-lookup"><span data-stu-id="b0263-167">Martin Fowler wrote about the testing pyramid, an example of which is shown in Figure 9-1.</span></span>

![](./media/image9-1.png)

<span data-ttu-id="b0263-168">图 9-1 测试棱锥图</span><span class="sxs-lookup"><span data-stu-id="b0263-168">Figure 9-1 Testing Pyramid</span></span>

<span data-ttu-id="b0263-169">不同层的棱锥图和其相对大小，表示不同类型的测试和多少应编写你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b0263-169">The different layers of the pyramid, and their relative sizes, represent different kinds of tests and how many you should write for your application.</span></span> <span data-ttu-id="b0263-170">如你所见，建议是让有大量的单元测试，支持通过集成测试变得更小层的功能测试的较小的层。</span><span class="sxs-lookup"><span data-stu-id="b0263-170">As you can see, the recommendation is to have a large base of unit tests, supported by a smaller layer of integration tests, with an even smaller layer of functional tests.</span></span> <span data-ttu-id="b0263-171">每个层理想情况下仅应有测试中它无法在较低层充分地执行。</span><span class="sxs-lookup"><span data-stu-id="b0263-171">Each layer should ideally only have tests in it that cannot be performed adequately at a lower layer.</span></span> <span data-ttu-id="b0263-172">当你尝试决定特定方案需要哪种类型的测试时，请记住测试棱锥图。</span><span class="sxs-lookup"><span data-stu-id="b0263-172">Keep the testing pyramid in mind when you are trying to decide which kind of test you need for a particular scenario.</span></span>

### <a name="what-to-test"></a><span data-ttu-id="b0263-173">要测试的内容</span><span class="sxs-lookup"><span data-stu-id="b0263-173">What to Test</span></span>

<span data-ttu-id="b0263-174">常见的问题的开发人员是编写自动化的测试缺乏经验即将与要测试的内容。</span><span class="sxs-lookup"><span data-stu-id="b0263-174">A common problem for developers who are inexperienced with writing automated tests is coming up with what to test.</span></span> <span data-ttu-id="b0263-175">很好的起点是测试条件逻辑。</span><span class="sxs-lookup"><span data-stu-id="b0263-175">A good starting point is to test conditional logic.</span></span> <span data-ttu-id="b0263-176">必须具有更改基于条件语句的行为的方法的任意位置 （如果其他切换，等），你应该能够提出至少几个用于确认正确的行为在某些情况。</span><span class="sxs-lookup"><span data-stu-id="b0263-176">Anywhere you have a method with behavior that changes based on a conditional statement (if-else, switch, etc.), you should be able to come up at least a couple of tests that confirm the correct behavior for certain conditions.</span></span> <span data-ttu-id="b0263-177">如果代码有错误条件，最好是编写 （而不会错误），至少一个测试通过代码的"高兴路径"和"很遗憾路径"的至少一个测试 （出现错误或非典型结果） 以确认你的应用程序行为与预期在遇到错误时相同。</span><span class="sxs-lookup"><span data-stu-id="b0263-177">If your code has error conditions, it's good to write at least one test for the "happy path" through the code (with no errors), and at least one test for the "sad path" (with errors or atypical results) to confirm your application behaves as expected in the face of errors.</span></span> <span data-ttu-id="b0263-178">最后，尝试重点测试可能会失败的操作，而不是将重点放在代码覆盖率等度量值。</span><span class="sxs-lookup"><span data-stu-id="b0263-178">Finally, try to focus on testing things that can fail, rather than focusing on metrics like code coverage.</span></span> <span data-ttu-id="b0263-179">更多的代码覆盖率是通常小于，更好。</span><span class="sxs-lookup"><span data-stu-id="b0263-179">More code coverage is better than less, generally.</span></span> <span data-ttu-id="b0263-180">但是，编写非常复杂，且业务关键型方法的几个更多测试通常是时间的更好地使用比编写针对自动属性只是时间的为了改进测试代码覆盖率度量值的测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-180">However, writing a few more tests of a very complex and business-critical method is usually a better use of time than writing tests for auto-properties just to improve test code coverage metrics.</span></span>

## <a name="organizing-test-projects"></a><span data-ttu-id="b0263-181">组织测试项目</span><span class="sxs-lookup"><span data-stu-id="b0263-181">Organizing Test Projects</span></span>

<span data-ttu-id="b0263-182">但是，为你的工作原理最佳可以组织测试项目。</span><span class="sxs-lookup"><span data-stu-id="b0263-182">Test projects can be organized however works best for you.</span></span> <span data-ttu-id="b0263-183">它是单独的测试以及他们正在测试的 （按项目、 命名空间） 按类型 （集成测试中的单元测试） 和一个好办法。</span><span class="sxs-lookup"><span data-stu-id="b0263-183">It's a good idea to separate tests by type (unit test, integration test) and by what they are testing (by project, by namespace).</span></span> <span data-ttu-id="b0263-184">这种分离是否包含在一个测试项目或多个测试项目中的文件夹是一项设计决策。</span><span class="sxs-lookup"><span data-stu-id="b0263-184">Whether this separation consists of folders within a single test project, or multiple test projects, is a design decision.</span></span> <span data-ttu-id="b0263-185">其中一个项目是最简单，但适用于大型项目具有多项测试，或者为了更轻松地运行不同的测试集，你可能想要有几个不同的测试项目。</span><span class="sxs-lookup"><span data-stu-id="b0263-185">One project is simplest, but for large projects with many tests, or in order to more easily run different sets of tests, you might want to have several different test projects.</span></span> <span data-ttu-id="b0263-186">许多团队组织基于他们正在测试的测试，这使应用程序具有多个少数几个项目中可能会导致大量的测试项目中，尤其是如果你仍将这些分解根据类型的测试的每个项目中的项目的测试项目。</span><span class="sxs-lookup"><span data-stu-id="b0263-186">Many teams organize test projects based on the project they are testing, which for applications with more than a few projects can result in a large number of test projects, especially if you still break these down according to what kind of tests are in each project.</span></span> <span data-ttu-id="b0263-187">泄漏方法是测试的让每一种，每个应用程序，使用在测试项目，以指示所测试的项目 （和类） 的文件夹的一个项目。</span><span class="sxs-lookup"><span data-stu-id="b0263-187">A compromise approach is to have one project per kind of test, per application, with folders inside the test projects to indicate the project (and class) being tested.</span></span>

<span data-ttu-id="b0263-188">常见方法是用于组织 src 文件夹下的应用程序项目和并行的测试文件夹下的应用程序的测试项目。</span><span class="sxs-lookup"><span data-stu-id="b0263-188">A common approach is to organize the application projects under a ‘src' folder, and the application's test projects under a parallel ‘tests' folder.</span></span> <span data-ttu-id="b0263-189">如果你发现此组织很有用，可以在 Visual Studio 中，创建匹配的解决方案文件夹。</span><span class="sxs-lookup"><span data-stu-id="b0263-189">You can create matching solution folders in Visual Studio, if you find this organization useful.</span></span>

![](./media/image9-2.png)

<span data-ttu-id="b0263-190">图 9-2 测试组织你的解决方案中</span><span class="sxs-lookup"><span data-stu-id="b0263-190">Figure 9-2 Test organization in your solution</span></span>

<span data-ttu-id="b0263-191">你可以使用任何您喜欢的测试框架。</span><span class="sxs-lookup"><span data-stu-id="b0263-191">You can use whichever test framework you prefer.</span></span> <span data-ttu-id="b0263-192">XUnit 框架可以有效地工作，并就是用编写的所有 ASP.NET Core 和 EF 核心的测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-192">The xUnit framework works well and is what all of the ASP.NET Core and EF Core tests are written in.</span></span> <span data-ttu-id="b0263-193">在 Visual Studio 中使用显示在图 9-3 中，或从 CLI 使用 dotnet 新 xunit 的模板，可以添加 xUnit 测试项目。</span><span class="sxs-lookup"><span data-stu-id="b0263-193">You can add an xUnit test project in Visual Studio using the template shown in Figure 9-3, or from the CLI using dotnet new xunit.</span></span>

![](./media/image9-3.png)

<span data-ttu-id="b0263-194">图 9-3 添加 xUnit Visual Studio 中的测试项目</span><span class="sxs-lookup"><span data-stu-id="b0263-194">Figure 9-3 Add an xUnit Test Project in Visual Studio</span></span>

### <a name="test-naming"></a><span data-ttu-id="b0263-195">测试命名</span><span class="sxs-lookup"><span data-stu-id="b0263-195">Test Naming</span></span>

<span data-ttu-id="b0263-196">具有名称指明了每个测试的用途，应名称以一致的方式，测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-196">You should name your tests in a consistent fashion, with names that indicate what each test does.</span></span> <span data-ttu-id="b0263-197">我使用了与巨大成功的一种方法是对名称根据类和方法他们正在测试的测试类。</span><span class="sxs-lookup"><span data-stu-id="b0263-197">One approach I've had great success with is to name test classes according to the class and method they are testing.</span></span> <span data-ttu-id="b0263-198">这会导致许多小测试类，但它有助于极清除每个测试是负责。</span><span class="sxs-lookup"><span data-stu-id="b0263-198">This results in many small test classes, but it makes it extremely clear what each test is responsible for.</span></span> <span data-ttu-id="b0263-199">与测试的类名称，将设置为标识的类和要测试的方法，可以使用测试方法名称指定所测试的行为。</span><span class="sxs-lookup"><span data-stu-id="b0263-199">With the test class name set up to identify the class and method to be tested, the test method name can be used to specify the behavior being tested.</span></span> <span data-ttu-id="b0263-200">这应包括的预期的行为任何输入或应产生此行为的假设。</span><span class="sxs-lookup"><span data-stu-id="b0263-200">This should include the expected behavior and any inputs or assumptions that should yield this behavior.</span></span> <span data-ttu-id="b0263-201">一些示例测试名称：</span><span class="sxs-lookup"><span data-stu-id="b0263-201">Some example test names:</span></span>

-   <span data-ttu-id="b0263-202">CatalogControllerGetImage.CallsImageServiceWithId</span><span class="sxs-lookup"><span data-stu-id="b0263-202">CatalogControllerGetImage.CallsImageServiceWithId</span></span>

-   <span data-ttu-id="b0263-203">CatalogControllerGetImage.LogsWarningGivenImageMissingException</span><span class="sxs-lookup"><span data-stu-id="b0263-203">CatalogControllerGetImage.LogsWarningGivenImageMissingException</span></span>

-   <span data-ttu-id="b0263-204">CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess</span><span class="sxs-lookup"><span data-stu-id="b0263-204">CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess</span></span>

-   <span data-ttu-id="b0263-205">CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException</span><span class="sxs-lookup"><span data-stu-id="b0263-205">CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException</span></span>

<span data-ttu-id="b0263-206">此方法的变体结束"应该"每个测试类名称，并修改时态略有：</span><span class="sxs-lookup"><span data-stu-id="b0263-206">A variation of this approach ends each test class name with "Should" and modifies the tense slightly:</span></span>

-   <span data-ttu-id="b0263-207">CatalogControllerGetImage**应**。**调用**ImageServiceWithId</span><span class="sxs-lookup"><span data-stu-id="b0263-207">CatalogControllerGetImage**Should**.**Call**ImageServiceWithId</span></span>

-   <span data-ttu-id="b0263-208">CatalogControllerGetImage**应**。**日志**WarningGivenImageMissingException</span><span class="sxs-lookup"><span data-stu-id="b0263-208">CatalogControllerGetImage**Should**.**Log**WarningGivenImageMissingException</span></span>

<span data-ttu-id="b0263-209">一些团队发现的第二个命名的方法更清晰、 但略有更详细。</span><span class="sxs-lookup"><span data-stu-id="b0263-209">Some teams find the second naming approach clearer, though slightly more verbose.</span></span> <span data-ttu-id="b0263-210">在任何情况下，尝试使用深入了解测试行为的命名约定，因此当一个或多个测试失败时，很明显来自失败何种情况下其名称。</span><span class="sxs-lookup"><span data-stu-id="b0263-210">In any case, try to use a naming convention that provides insight into test behavior, so that when one or more tests fail, it's obvious from their names what cases have failed.</span></span> <span data-ttu-id="b0263-211">避免命名你的测试有一个大致，如 ControllerTests.Test1，因为当你在测试结果中看到它们时，这些不提供任何值。</span><span class="sxs-lookup"><span data-stu-id="b0263-211">Avoid naming you tests vaguely, such as ControllerTests.Test1, as these offer no value when you see them in test results.</span></span>

<span data-ttu-id="b0263-212">如果你遵循命名约定，如上面的产生许多小测试类，它是一个好办法进一步组织你的测试使用文件夹和命名空间。</span><span class="sxs-lookup"><span data-stu-id="b0263-212">If you follow a naming convention like the one above that produces many small test classes, it's a good idea to further organize your tests using folders and namespaces.</span></span> <span data-ttu-id="b0263-213">图 9-4 显示组织中多个测试项目文件夹中测试的一种方法。</span><span class="sxs-lookup"><span data-stu-id="b0263-213">Figure 9-4 shows one approach to organizing tests by folder within several test projects.</span></span>

![](./media/image9-4.png)

<span data-ttu-id="b0263-214">**图 9-4。**</span><span class="sxs-lookup"><span data-stu-id="b0263-214">**Figure 9-4.**</span></span> <span data-ttu-id="b0263-215">组织测试类基于类所测试的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b0263-215">Organizing test classes by folder based on class being tested.</span></span>

<span data-ttu-id="b0263-216">当然，如果特定应用程序类具有许多所测试的方法 （并且因此多测试类），可能有意义将这些应用程序类所对应的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b0263-216">Of course, if a particular application class has many methods being tested (and thus many test classes), it may make sense to place these in a folder corresponding to the application class.</span></span> <span data-ttu-id="b0263-217">此组织是如何在到其他位置的文件夹可能组织文件没有什么不同。</span><span class="sxs-lookup"><span data-stu-id="b0263-217">This organization is no different than how you might organize files into folders elsewhere.</span></span> <span data-ttu-id="b0263-218">如果你有多个三个或四个相关包含很多其他文件的文件夹中的文件，它很有帮助，以将它们移到其自己的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="b0263-218">If you have more than three or four related files in a folder containing many other files, it's often helpful to move them into their own subfolder.</span></span>

## <a name="unit-testing-aspnet-core-apps"></a><span data-ttu-id="b0263-219">单元测试 ASP.NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="b0263-219">Unit Testing ASP.NET Core Apps</span></span>

<span data-ttu-id="b0263-220">在设计良好的 ASP.NET Core 应用程序中，大部分的复杂性和业务逻辑将封装在业务实体和各种服务中。</span><span class="sxs-lookup"><span data-stu-id="b0263-220">In a well-designed ASP.NET Core application, most of the complexity and business logic will be encapsulated in business entities and a variety of services.</span></span> <span data-ttu-id="b0263-221">ASP.NET 核心 MVC 应用程序本身，其控制器、 筛选器、 viewmodel 和视图，应要求极少的单元测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-221">The ASP.NET Core MVC app itself, with its controllers, filters, viewmodels, and views, should require very few unit tests.</span></span> <span data-ttu-id="b0263-222">某个给定操作的功能大部分位于外部的操作方法本身。</span><span class="sxs-lookup"><span data-stu-id="b0263-222">Much of the functionality of a given action lies outside the action method itself.</span></span> <span data-ttu-id="b0263-223">测试是否路由正常运行，或全局错误处理，不能完成有效地与单元测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-223">Testing whether routing works correctly, or global error handling, cannot be done effectively with a unit test.</span></span> <span data-ttu-id="b0263-224">同样，任何筛选器，包括模型验证和身份验证和授权筛选器，不能为单元测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-224">Likewise, any filters, including model validation and authentication and authorization filters, cannot be unit tested.</span></span> <span data-ttu-id="b0263-225">没有这些源的行为，大多数操作方法应非常小，委托可以测试独立于使用它们的控制器的服务到其工作的大容量。</span><span class="sxs-lookup"><span data-stu-id="b0263-225">Without these sources of behavior, most action methods should be trivially small, delegating the bulk of their work to services that can be tested independent of the controller that uses them.</span></span>

<span data-ttu-id="b0263-226">有时，你将需要的重构到单元测试的代码中的排列它。</span><span class="sxs-lookup"><span data-stu-id="b0263-226">Sometimes you'll need to refactor your code in order to unit test it.</span></span> <span data-ttu-id="b0263-227">这通常涉及到标识抽象和依赖关系注入用于访问的抽象在代码中你想要测试，而不是直接根据基础结构的编码。</span><span class="sxs-lookup"><span data-stu-id="b0263-227">Frequently this involves identifying abstractions and using dependency injection to access the abstraction in the code you'd like to test, rather than coding directly against infrastructure.</span></span> <span data-ttu-id="b0263-228">例如，考虑此相当简单的操作方法，用于显示图像：</span><span class="sxs-lookup"><span data-stu-id="b0263-228">For example, consider this simple action method for displaying images:</span></span>

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

<span data-ttu-id="b0263-229">困难上 System.IO.File，它使用从文件系统读取其直接的依赖关系进行单元测试此方法。</span><span class="sxs-lookup"><span data-stu-id="b0263-229">Unit testing this method is made difficult by its direct dependency on System.IO.File, which it uses to read from the file system.</span></span> <span data-ttu-id="b0263-230">你可以测试此行为，以确保它按预期方式工作，但这样的实际文件是一种集成测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-230">You can test this behavior to ensure it works as expected, but doing so with real files is an integration test.</span></span> <span data-ttu-id="b0263-231">值得注意不能测试此方法的路由 – 你将看到如何执行此操作与一个功能测试将很快。</span><span class="sxs-lookup"><span data-stu-id="b0263-231">It's worth noting you can't test this method's route – you'll see how to do this with a functional test shortly.</span></span>

<span data-ttu-id="b0263-232">如果你不能单元测试文件系统行为直接，并且不能测试路由，什么是存在以测试？</span><span class="sxs-lookup"><span data-stu-id="b0263-232">If you can't unit test the file system behavior directly, and you can't test the route, what is there to test?</span></span> <span data-ttu-id="b0263-233">嗯，重构以使单元测试成为可能后, 您可能会发现一些测试用例和缺少的行为，例如错误处理。</span><span class="sxs-lookup"><span data-stu-id="b0263-233">Well, after refactoring to make unit testing possible, you may discover some test cases and missing behavior, such as error handling.</span></span> <span data-ttu-id="b0263-234">该方法作用是什么时未找到的文件？</span><span class="sxs-lookup"><span data-stu-id="b0263-234">What does the method do when a file isn't found?</span></span> <span data-ttu-id="b0263-235">它应该做什么？</span><span class="sxs-lookup"><span data-stu-id="b0263-235">What should it do?</span></span> <span data-ttu-id="b0263-236">在此示例中，已重构的方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="b0263-236">In this example, the refactored method looks like this:</span></span>

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

<span data-ttu-id="b0263-237">\_记录器和\_imageService 被注入依赖关系。</span><span class="sxs-lookup"><span data-stu-id="b0263-237">The \_logger and \_imageService are both injected as dependencies.</span></span> <span data-ttu-id="b0263-238">现在你可以测试该传递给的操作方法的相同 id 传递到\_imageService，并且所产生的字节返回 FileResult 的一部分。</span><span class="sxs-lookup"><span data-stu-id="b0263-238">Now you can test that the same id that is passed to the action method is passed to the \_imageService, and that the resulting bytes are returned as part of the FileResult.</span></span> <span data-ttu-id="b0263-239">你还可以测试，错误日志记录发生的情况按预期方式运行，如果映像已丢失，则返回 NotFound 结果假设这重要的应用程序行为 （即，不只是临时代码开发人员添加用于诊断问题）。</span><span class="sxs-lookup"><span data-stu-id="b0263-239">You can also test that error logging is happening as expected, and that a NotFound result is returned if the image is missing, assuming this is important application behavior (that is, not just temporary code the developer added to diagnose an issue).</span></span> <span data-ttu-id="b0263-240">实际文件逻辑已移动到一个单独实现服务，以及已扩充以返回特定于应用程序异常对于缺少的文件的情况。</span><span class="sxs-lookup"><span data-stu-id="b0263-240">The actual file logic has moved into a separate implementation service, and has been augmented to return an application-specific exception for the case of a missing file.</span></span> <span data-ttu-id="b0263-241">你可以测试此实现独立，使用的集成测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-241">You can test this implementation independently, using an integration test.</span></span>

## <a name="integration-testing-aspnet-core-apps"></a><span data-ttu-id="b0263-242">集成测试 ASP.NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="b0263-242">Integration Testing ASP.NET Core Apps</span></span>

```cs
    }
        catch (FileNotFoundException ex)
        {
            throw new CatalogImageMissingException(ex);
        }
    }
}
```

<span data-ttu-id="b0263-243">此服务使用 IHostingEnvironment，就像代码未重构到一个单独的服务之前 CatalogController。</span><span class="sxs-lookup"><span data-stu-id="b0263-243">This service uses the IHostingEnvironment, just as the CatalogController code did before it was refactored into a separate service.</span></span> <span data-ttu-id="b0263-244">由于是在使用 IHostingEnvironment 控制器中的唯一代码，该依赖项已从 CatalogController 的构造函数。</span><span class="sxs-lookup"><span data-stu-id="b0263-244">Since this was the only code in the controller that used IHostingEnvironment, that dependency was removed from CatalogController's constructor.</span></span>

<span data-ttu-id="b0263-245">若要测试此服务工作正常，你需要创建一个已知的测试的映像文件和验证，服务将返回它提供特定的输入。</span><span class="sxs-lookup"><span data-stu-id="b0263-245">To test that this service works correctly, you need to create a known test image file and verify that the service returns it given a specific input.</span></span> <span data-ttu-id="b0263-246">你应注意不是在你确实想要测试 （在此情况下，从文件系统读取） 的行为上使用模拟的对象。</span><span class="sxs-lookup"><span data-stu-id="b0263-246">You should take care not to use mock objects on the behavior you actually want to test (in this case, reading from the file system).</span></span> <span data-ttu-id="b0263-247">但是，模拟对象仍可能会很有用设置集成测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-247">However, mock objects may still be useful to set up integration tests.</span></span> <span data-ttu-id="b0263-248">在这种情况下，你可以模拟 IHostingEnvironment，以便其 ContentRootPath 指向你要用于测试映像的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b0263-248">In this case, you can mock IHostingEnvironment so that its ContentRootPath points to the folder you're going to use for your test image.</span></span> <span data-ttu-id="b0263-249">完成工作的集成测试的类如下所示：</span><span class="sxs-lookup"><span data-stu-id="b0263-249">The complete working integration test class is shown here:</span></span>

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
> <span data-ttu-id="b0263-250">测试本身是非常简单 – 大多数代码则需要配置系统并创建的测试的基础结构 （在这种情况下，实际文件中要从磁盘读取）。</span><span class="sxs-lookup"><span data-stu-id="b0263-250">that the test itself is very simple – the bulk of the code is necessary to configure the system and create the testing infrastructure (in this case, an actual file to be read from disk).</span></span> <span data-ttu-id="b0263-251">这是典型的集成测试，通常需要更复杂的安装程序工作比单元测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-251">This is typical for integration tests, which often require more complex setup work than unit tests.</span></span>

## <a name="functional-testing-aspnet-core-apps"></a><span data-ttu-id="b0263-252">功能来测试 ASP.NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="b0263-252">Functional Testing ASP.NET Core Apps</span></span>

<span data-ttu-id="b0263-253">对于 ASP.NET Core 应用程序，TestServer 类，使功能测试非常易于编写。</span><span class="sxs-lookup"><span data-stu-id="b0263-253">For ASP.NET Core applications, the TestServer class makes functional tests fairly easy to write.</span></span> <span data-ttu-id="b0263-254">就像通常对你的应用程序所做配置使用 WebHostBuilder TestServer。</span><span class="sxs-lookup"><span data-stu-id="b0263-254">You configure a TestServer using a WebHostBuilder, just as you normally do for your application.</span></span> <span data-ttu-id="b0263-255">此 WebHostBuilder 应配置一样应用程序的实际主机，但可以修改简化测试它的任何方面。</span><span class="sxs-lookup"><span data-stu-id="b0263-255">This WebHostBuilder should be configured just like your application's real host, but you can modify any aspects of it that make testing easier.</span></span> <span data-ttu-id="b0263-256">大多数情况下，您将重新使用相同 TestServer 许多测试用例，因此你可以将其封装中的可重用方法 （可能是中的基类）：</span><span class="sxs-lookup"><span data-stu-id="b0263-256">Most of the time, you'll reuse the same TestServer for many test cases, so you can encapsulate it in a reusable method (perhaps in a base class):</span></span>

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

<span data-ttu-id="b0263-257">GetProjectPath 方法只需返回到 web 项目 （下载示例解决方案） 的物理路径。</span><span class="sxs-lookup"><span data-stu-id="b0263-257">The GetProjectPath method simply returns the physical path to the web project (download sample solution).</span></span> <span data-ttu-id="b0263-258">WebHostBuilder 在这种情况下只需指定 web 应用程序内容的根，其中引用同一个实际的 web 应用程序使用的启动类。</span><span class="sxs-lookup"><span data-stu-id="b0263-258">The WebHostBuilder in this case simply specifies where the content root for the web application is, and references the same Startup class the real web application uses.</span></span> <span data-ttu-id="b0263-259">若要使用 TestServer，你使用的标准 System.Net.HttpClient 类型以使对它发出的请求。</span><span class="sxs-lookup"><span data-stu-id="b0263-259">To work with the TestServer, you use the standard System.Net.HttpClient type to make requests to it.</span></span> <span data-ttu-id="b0263-260">TestServer 公开一个提供已准备好在 TestServer 上运行的应用程序发出请求的预配置客户端的有用 CreateClient 方法。</span><span class="sxs-lookup"><span data-stu-id="b0263-260">TestServer exposes a helpful CreateClient method that provides a pre-configured client that is ready to make requests to the application running on the TestServer.</span></span> <span data-ttu-id="b0263-261">使用此客户端 (设置为受保护\_上述基础的测试上的客户端成员) 编写 ASP.NET Core 应用程序的功能测试时：</span><span class="sxs-lookup"><span data-stu-id="b0263-261">You use this client (set to the protected \_client member on the base test above) when writing functional tests for your ASP.NET Core application:</span></span>

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

<span data-ttu-id="b0263-262">此功能的测试执行完整的 ASP.NET 核心 MVC 应用程序堆栈，包括所有中间件、 筛选器、 联编程序、 可能处于的位置等。</span><span class="sxs-lookup"><span data-stu-id="b0263-262">This functional test exercises the full ASP.NET Core MVC application stack, including all middleware, filters, binders, etc. that may be in place.</span></span> <span data-ttu-id="b0263-263">它验证给定的路由 （"/ 目录/pic/1"） 返回的文件的预期的字节数组中的已知位置。</span><span class="sxs-lookup"><span data-stu-id="b0263-263">It verifies that a given route ("/catalog/pic/1") returns the expected byte array for a file in a known location.</span></span> <span data-ttu-id="b0263-264">它这样做无需设置实际的 web 服务器，并因此可避免很多易，使用实际的 web 服务器进行测试可以体验 （例如，其防火墙设置的问题）。</span><span class="sxs-lookup"><span data-stu-id="b0263-264">It does so without setting up a real web server, and so avoids much of the brittleness that using a real web server for testing can experience (for example, problems with firewall settings).</span></span> <span data-ttu-id="b0263-265">TestServer 针对运行的功能测试通常比集成和单元测试，要慢，但要大大快于通过网络与测试 web 服务器将运行的测试。</span><span class="sxs-lookup"><span data-stu-id="b0263-265">Functional tests that run against TestServer are usually slower than integration and unit tests, but are much faster than tests that would run over the network to a test web server.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="b0263-266">[以前](work-with-data-in-asp-net-core-apps.md) [下一步] (开发-过程-为-azure.md)</span><span class="sxs-lookup"><span data-stu-id="b0263-266">[Previous] (work-with-data-in-asp-net-core-apps.md) [Next] (development-process-for-azure.md)</span></span>
