---
title: ".NET Core 中的单元测试"
description: "单元测试从未如此简单。 了解如何在 .NET Core 项目中使用单元测试。"
keywords: .NET, .NET Core
author: ardalis
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 815ac74c-4bd9-4a94-a87c-78288b27c0e2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 22647a9ad7723bbfcf0d54530b3c0538198e7c35
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="unit-testing-in-net-core"></a><span data-ttu-id="962fd-105">.NET Core 中的单元测试</span><span class="sxs-lookup"><span data-stu-id="962fd-105">Unit Testing in .NET Core</span></span>

<span data-ttu-id="962fd-106">由于在设计 .NET Core 时考虑到了可测试性，因此为应用程序创建单元测试比以往更加简单。</span><span class="sxs-lookup"><span data-stu-id="962fd-106">.NET Core has been designed with testability in mind, so that creating unit tests for your applications is easier than ever before.</span></span> <span data-ttu-id="962fd-107">本文简要介绍了单元测试（以及与其他类型测试的不同之处）。</span><span class="sxs-lookup"><span data-stu-id="962fd-107">This article briefly introduces unit tests (and how they differ from other kinds of tests).</span></span> <span data-ttu-id="962fd-108">链接的资源演示了如何将测试项目添加到解决方案，然后使用命令行或 Visual Studio 运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="962fd-108">Linked resources demonstrates how to add a test project to your solution and then run unit tests using either the command line or Visual Studio.</span></span>

## <a name="getting-started-with-testing"></a><span data-ttu-id="962fd-109">测试入门</span><span class="sxs-lookup"><span data-stu-id="962fd-109">Getting Started with Testing</span></span>
 
<span data-ttu-id="962fd-110">确保软件应用程序按作者的期望执行操作，其中最好的一种方法是拥有自动化测试套件。</span><span class="sxs-lookup"><span data-stu-id="962fd-110">Having a suite of automated tests is one of the best ways to ensure a software application does what its authors intended it to do.</span></span> <span data-ttu-id="962fd-111">有多种用于软件应用程序的不同测试，包括集成测试、Web 测试、负载测试等其他许多测试。</span><span class="sxs-lookup"><span data-stu-id="962fd-111">There are many different kinds of tests for software applications, including integration tests, web tests, load tests, and many others.</span></span> <span data-ttu-id="962fd-112">最低级别的测试为单元测试，此测试用于测试个人软件组件或方法。</span><span class="sxs-lookup"><span data-stu-id="962fd-112">At the lowest level are unit tests, which test individual software components or methods.</span></span> <span data-ttu-id="962fd-113">单元测试只应测试开发人员控件中的代码，而不应测试基础结构问题，如数据库、文件系统或网络资源等。</span><span class="sxs-lookup"><span data-stu-id="962fd-113">Unit tests should only test code within the developer’s control, and should not test infrastructure concerns, like databases, file systems, or network resources.</span></span> <span data-ttu-id="962fd-114">可以使用[测试驱动开发 (TDD)](http://deviq.com/test-driven-development/) 编写单元测试，或将其添加到现有代码以确认其正确性。</span><span class="sxs-lookup"><span data-stu-id="962fd-114">Unit tests may be written using [Test Driven Development (TDD)](http://deviq.com/test-driven-development/), or they can be added to existing code to confirm its correctness.</span></span> <span data-ttu-id="962fd-115">无论哪种情况，单元测试都应该是良好命名、快捷的小型测试，因为在理想情况下，希望能够在将更改推送到项目的共享代码存储库之前运行数百个单元测试。</span><span class="sxs-lookup"><span data-stu-id="962fd-115">In either case, they should be small, well-named, and fast, since ideally you will want to be able to run hundreds of them before pushing your changes into the project’s shared code repository.</span></span>

> [!NOTE]
> <span data-ttu-id="962fd-116">开发人员经常要想方设法地为测试类和方法提供合适的名称。</span><span class="sxs-lookup"><span data-stu-id="962fd-116">Developers often struggle with coming up with good names for their test classes and methods.</span></span> <span data-ttu-id="962fd-117">作为起点，ASP.NET 产品团队会遵循[这些约定](https://github.com/aspnet/Home/wiki/Engineering-guidelines#unit-tests-and-functional-tests)。</span><span class="sxs-lookup"><span data-stu-id="962fd-117">As a starting point, the ASP.NET product team follows [these conventions](https://github.com/aspnet/Home/wiki/Engineering-guidelines#unit-tests-and-functional-tests).</span></span>

<span data-ttu-id="962fd-118">编写单元测试时，注意不要在基础结构上意外引入了依赖项。</span><span class="sxs-lookup"><span data-stu-id="962fd-118">When writing unit tests, be careful you don’t accidentally introduce dependencies on infrastructure.</span></span> <span data-ttu-id="962fd-119">这些依赖项往往会降低测试速度，使测试更加脆弱，因此应将其保留供集成测试使用。</span><span class="sxs-lookup"><span data-stu-id="962fd-119">These tend to make tests slower and more brittle, and thus should be reserved for integration tests.</span></span> <span data-ttu-id="962fd-120">可以通过遵循 [Explicit Dependencies Principle](http://deviq.com/explicit-dependencies-principle/)（显示依赖项原则）和使用 [Dependency Injection](/aspnet/core/fundamentals/dependency-injection)（依赖项注入）从框架中请求依赖项，以此避免应用程序代码中的这些隐藏依赖项。</span><span class="sxs-lookup"><span data-stu-id="962fd-120">You can avoid these hidden dependencies in your application code by following the [Explicit Dependencies Principle](http://deviq.com/explicit-dependencies-principle/) and using [Dependency Injection](/aspnet/core/fundamentals/dependency-injection) to request your dependencies from the framework.</span></span> <span data-ttu-id="962fd-121">还可以将单元测试保留在单独的项目中，与集成测试相分隔，并确保单元测试项目没有引用或依赖于基础结构包。</span><span class="sxs-lookup"><span data-stu-id="962fd-121">You can also keep your unit tests in a separate project from your integration tests, and ensure your unit test project doesn’t have references to or dependencies on infrastructure packages.</span></span>

<span data-ttu-id="962fd-122">了解有关 .NET Core 项目中的单元测试的详细信息：</span><span class="sxs-lookup"><span data-stu-id="962fd-122">Learn more about unit testing in .NET Core projects:</span></span>

* <span data-ttu-id="962fd-123">请尝试此[使用 xUnit 和 .NET Core CLI 创建单元测试的演练](unit-testing-with-dotnet-test.md)。</span><span class="sxs-lookup"><span data-stu-id="962fd-123">Try this [walkthrough creating unit tests with xUnit and the .NET Core CLI](unit-testing-with-dotnet-test.md).</span></span> 
* <span data-ttu-id="962fd-124">XUnit 团队编写了一个教程，介绍[如何通过 .NET Core 和 Visual Studio 使用 xUnit](http://xunit.github.io/docs/getting-started-dotnet-core.html)。</span><span class="sxs-lookup"><span data-stu-id="962fd-124">The XUnit team has written a tutorial that shows [how to use xUnit with .NET Core and Visual Studio](http://xunit.github.io/docs/getting-started-dotnet-core.html).</span></span>
* <span data-ttu-id="962fd-125">如果要使用 MSTest，请尝试[使用 MSTest 和 .NET Core CLI 创建单元测试 的演练](unit-testing-with-mstest.md)。</span><span class="sxs-lookup"><span data-stu-id="962fd-125">If you prefer using MSTest, try the [walkthrough creating unit tests with MSTest and the .NET Core CLI](unit-testing-with-mstest.md).</span></span>
* <span data-ttu-id="962fd-126">有关如何使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。</span><span class="sxs-lookup"><span data-stu-id="962fd-126">For a additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

