---
title: .NET Core 和 .NET Standard 中的单元测试
description: 本文简要概述了 .NET Core 和.NET Standard 项目的单元测试。
author: ardalis
ms.author: wiwagn
ms.date: 08/30/2017
ms.custom: seodec18
ms.openlocfilehash: 3fdacd5beb2c6cbfc631d58e99a8741f7a6b233c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243969"
---
# <a name="unit-testing-in-net-core-and-net-standard"></a><span data-ttu-id="f3739-103">.NET Core 和 .NET Standard 中的单元测试</span><span class="sxs-lookup"><span data-stu-id="f3739-103">Unit testing in .NET Core and .NET Standard</span></span>

<span data-ttu-id="f3739-104">通过 .NET Core，可以轻松创建单元测试。</span><span class="sxs-lookup"><span data-stu-id="f3739-104">.NET Core makes it easy to create unit tests.</span></span> <span data-ttu-id="f3739-105">本文介绍了单元测试及其与其他类型的测试的不同之处。</span><span class="sxs-lookup"><span data-stu-id="f3739-105">This article introduces unit tests and illustrates how they differ from other kinds of tests.</span></span> <span data-ttu-id="f3739-106">页面底部附近的链接资源介绍了如何向解决方案添加测试项目。</span><span class="sxs-lookup"><span data-stu-id="f3739-106">The linked resources near the bottom of the page show you how to add a test project to your solution.</span></span> <span data-ttu-id="f3739-107">设置测试项目后，可使用命令行或 Visual Studio 运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="f3739-107">After you set up your test project, you will be able to run your unit tests using the command line or Visual Studio.</span></span>

<span data-ttu-id="f3739-108">.NET core 2.0 及更高版本支持 [.NET Standard 2.0](../../standard/net-standard.md)，我们将使用它的库来演示单元测试。</span><span class="sxs-lookup"><span data-stu-id="f3739-108">.NET Core 2.0 and later supports [.NET Standard 2.0](../../standard/net-standard.md), and we will use it's libraries to demonstrate unit tests.</span></span>

<span data-ttu-id="f3739-109">可以使用适用于 C#、F# 和 Visual Basic 的内置 .NET Core 2.0 及更高版本单元测试项目模板作为个人项目的起始点。</span><span class="sxs-lookup"><span data-stu-id="f3739-109">You are able to use built-in .NET Core 2.0 and later unit test project templates for C#, F# and Visual Basic as a starting point for your personal project.</span></span>

## <a name="what-are-unit-tests"></a><span data-ttu-id="f3739-110">什么是单元测试？</span><span class="sxs-lookup"><span data-stu-id="f3739-110">What are unit tests?</span></span>

<span data-ttu-id="f3739-111">使用自动测试是确保软件应用程序按作者期望执行操作的一种绝佳方式。</span><span class="sxs-lookup"><span data-stu-id="f3739-111">Having automated tests is a great way to ensure a software application does what its authors intend it to do.</span></span> <span data-ttu-id="f3739-112">软件应用程序有多种类型的测试。</span><span class="sxs-lookup"><span data-stu-id="f3739-112">There are multiple types of tests for software applications.</span></span> <span data-ttu-id="f3739-113">其中包括集成测试、Web 测试、负载测试和其他测试。</span><span class="sxs-lookup"><span data-stu-id="f3739-113">These include integration tests, web tests, load tests, and others.</span></span> <span data-ttu-id="f3739-114">“单元测试”用于测试个人软件组件或方法。</span><span class="sxs-lookup"><span data-stu-id="f3739-114">**Unit tests** test individual software components and methods.</span></span> <span data-ttu-id="f3739-115">单元测试仅应测试开发人员控件内的代码。</span><span class="sxs-lookup"><span data-stu-id="f3739-115">Unit tests should only test code within the developer’s control.</span></span> <span data-ttu-id="f3739-116">它们不应测试基础结构问题。</span><span class="sxs-lookup"><span data-stu-id="f3739-116">They should not test infrastructure concerns.</span></span> <span data-ttu-id="f3739-117">基础结构问题包括数据库、文件系统和网络资源。</span><span class="sxs-lookup"><span data-stu-id="f3739-117">Infrastructure concerns include databases, file systems, and network resources.</span></span> 

<span data-ttu-id="f3739-118">此外，请记住还可使用编写测试的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="f3739-118">Also, keep in mind there are best practices for writing tests.</span></span> <span data-ttu-id="f3739-119">例如，[测试驱动开发 (TDD)](https://deviq.com/test-driven-development/) 是指先编写单元测试，再编写该单元测试要检查的代码。</span><span class="sxs-lookup"><span data-stu-id="f3739-119">For example, [Test Driven Development (TDD)](https://deviq.com/test-driven-development/) is when a unit test is written before the code it is meant to check.</span></span> <span data-ttu-id="f3739-120">TDD 就像先编写书籍大纲，再编写该书籍。</span><span class="sxs-lookup"><span data-stu-id="f3739-120">TDD is like creating an outline for a book before we write it.</span></span> <span data-ttu-id="f3739-121">它旨在帮助开发人员编写更简单、更具可读性的高效代码。</span><span class="sxs-lookup"><span data-stu-id="f3739-121">It is meant to help developers write simpler, more readable, and efficient code.</span></span> 

> [!NOTE]
> <span data-ttu-id="f3739-122">ASP.NET 团队遵循[这些约定](https://github.com/aspnet/Home/wiki/Engineering-guidelines#unit-tests-and-functional-tests)帮助开发人员为测试类和方法提供合适的名称。</span><span class="sxs-lookup"><span data-stu-id="f3739-122">The ASP.NET team follows [these conventions](https://github.com/aspnet/Home/wiki/Engineering-guidelines#unit-tests-and-functional-tests) to help developers come up with good names for test classes and methods.</span></span>

<span data-ttu-id="f3739-123">编写单元测试时，尽量不要引入基础结构依赖项。</span><span class="sxs-lookup"><span data-stu-id="f3739-123">Try not to introduce dependencies on infrastructure when writing unit tests.</span></span> <span data-ttu-id="f3739-124">这些依赖项会降低测试速度，使测试更加脆弱，应将其保留供集成测试使用。</span><span class="sxs-lookup"><span data-stu-id="f3739-124">These make the tests slow and brittle, and should be reserved for integration tests.</span></span> <span data-ttu-id="f3739-125">可以通过遵循 [Explicit Dependencies Principle](https://deviq.com/explicit-dependencies-principle/)（显式依赖项原则）和使用 [Dependency Injection](/aspnet/core/fundamentals/dependency-injection)（依赖项注入）避免应用程序中的这些依赖项。</span><span class="sxs-lookup"><span data-stu-id="f3739-125">You can avoid these dependencies in your application by following the [Explicit Dependencies Principle](https://deviq.com/explicit-dependencies-principle/) and using [Dependency Injection](/aspnet/core/fundamentals/dependency-injection).</span></span> <span data-ttu-id="f3739-126">还可以将单元测试保留在单独的项目中，与集成测试相分隔。</span><span class="sxs-lookup"><span data-stu-id="f3739-126">You can also keep your unit tests in a separate project from your integration tests.</span></span> <span data-ttu-id="f3739-127">这可确保单元测试项目没有引用或依赖于基础结构包。</span><span class="sxs-lookup"><span data-stu-id="f3739-127">This ensures your unit test project doesn’t have references to or dependencies on infrastructure packages.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f3739-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f3739-128">Next steps</span></span>

<span data-ttu-id="f3739-129">有关 .NET Core 项目中的单元测试的详细信息：</span><span class="sxs-lookup"><span data-stu-id="f3739-129">More information on unit testing in .NET Core projects:</span></span>

<span data-ttu-id="f3739-130">.NET Core 单元测试项目支持：</span><span class="sxs-lookup"><span data-stu-id="f3739-130">.NET Core unit test projects are supported for:</span></span>
* [<span data-ttu-id="f3739-131">C#</span><span class="sxs-lookup"><span data-stu-id="f3739-131">C#</span></span>](../../csharp/index.md)
* [<span data-ttu-id="f3739-132">F#</span><span class="sxs-lookup"><span data-stu-id="f3739-132">F#</span></span>](../../fsharp/index.md)
* [<span data-ttu-id="f3739-133">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3739-133">Visual Basic</span></span>](../../visual-basic/index.md) 

<span data-ttu-id="f3739-134">还可以在以下各项之间进行选择：</span><span class="sxs-lookup"><span data-stu-id="f3739-134">You can also choose between:</span></span>
* [<span data-ttu-id="f3739-135">xUnit</span><span class="sxs-lookup"><span data-stu-id="f3739-135">xUnit</span></span>](https://xunit.github.io) 
* [<span data-ttu-id="f3739-136">NUnit</span><span class="sxs-lookup"><span data-stu-id="f3739-136">NUnit</span></span>](https://nunit.org)
* [<span data-ttu-id="f3739-137">MSTest</span><span class="sxs-lookup"><span data-stu-id="f3739-137">MSTest</span></span>](https://github.com/Microsoft/vstest-docs)

<span data-ttu-id="f3739-138">可在以下演练中了解详细信息：</span><span class="sxs-lookup"><span data-stu-id="f3739-138">You can learn more in the following walkthroughs:</span></span>

* <span data-ttu-id="f3739-139">[结合使用 .NET Core CLI 与 xUnit 和 C#](unit-testing-with-dotnet-test.md) 创建单元测试。</span><span class="sxs-lookup"><span data-stu-id="f3739-139">Create unit tests using [*xUnit* and *C#* with the .NET Core CLI](unit-testing-with-dotnet-test.md).</span></span>
* <span data-ttu-id="f3739-140">[结合使用 .NET Core CLI 与 NUnit 和 C#](unit-testing-with-nunit.md) 创建单元测试。</span><span class="sxs-lookup"><span data-stu-id="f3739-140">Create unit tests using [*NUnit* and *C#* with the .NET Core CLI](unit-testing-with-nunit.md).</span></span>
* <span data-ttu-id="f3739-141">[结合使用 .NET Core CLI 与 MSTest 和 C#](unit-testing-with-mstest.md) 创建单元测试。</span><span class="sxs-lookup"><span data-stu-id="f3739-141">Create unit tests using [*MSTest* and *C#* with the .NET Core CLI](unit-testing-with-mstest.md).</span></span>
* <span data-ttu-id="f3739-142">[结合使用 .NET Core CLI 与 xUnit 和 F#](unit-testing-fsharp-with-dotnet-test.md) 创建单元测试。</span><span class="sxs-lookup"><span data-stu-id="f3739-142">Create unit tests using [*xUnit* and *F#* with the .NET Core CLI](unit-testing-fsharp-with-dotnet-test.md).</span></span>
* <span data-ttu-id="f3739-143">[结合使用 .NET Core CLI 与 NUnit 和 F#](unit-testing-fsharp-with-nunit.md) 创建单元测试。</span><span class="sxs-lookup"><span data-stu-id="f3739-143">Create unit tests using [*NUnit* and *F#* with the .NET Core CLI](unit-testing-fsharp-with-nunit.md).</span></span>
* <span data-ttu-id="f3739-144">[结合使用 .NET Core CLI 与 MSTest 和 F#](unit-testing-fsharp-with-mstest.md) 创建单元测试。</span><span class="sxs-lookup"><span data-stu-id="f3739-144">Create unit tests using [*MSTest* and *F#* with the .NET Core CLI](unit-testing-fsharp-with-mstest.md).</span></span>
* <span data-ttu-id="f3739-145">[结合使用 .NET Core CLI 与 xUnit 和 Visual Basic](unit-testing-visual-basic-with-dotnet-test.md) 创建单元测试。</span><span class="sxs-lookup"><span data-stu-id="f3739-145">Create unit tests using [*xUnit* and *Visual Basic* with the .NET Core CLI](unit-testing-visual-basic-with-dotnet-test.md).</span></span>
* <span data-ttu-id="f3739-146">[结合使用 .NET Core CLI 与 NUnit 和 Visual Basic](unit-testing-visual-basic-with-nunit.md) 创建单元测试。</span><span class="sxs-lookup"><span data-stu-id="f3739-146">Create unit tests using [*NUnit* and *Visual Basic* with the .NET Core CLI](unit-testing-visual-basic-with-nunit.md).</span></span>
* <span data-ttu-id="f3739-147">[结合使用 .NET Core CLI 与 MSTest 和 Visual Basic](unit-testing-visual-basic-with-mstest.md) 创建单元测试。</span><span class="sxs-lookup"><span data-stu-id="f3739-147">Create unit tests using [*MSTest* and *Visual Basic* with the .NET Core CLI](unit-testing-visual-basic-with-mstest.md).</span></span>

<span data-ttu-id="f3739-148">可在以下文章中了解详细信息：</span><span class="sxs-lookup"><span data-stu-id="f3739-148">You can learn more in the following articles:</span></span>

* <span data-ttu-id="f3739-149">Visual Studio Enterprise 提供用于 .NET Core 的卓越测试工具。</span><span class="sxs-lookup"><span data-stu-id="f3739-149">Visual Studio Enterprise offers great testing tools for .NET Core.</span></span> <span data-ttu-id="f3739-150">有关详细信息，请查看 [Live Unit Testing](/visualstudio/test/live-unit-testing) 或[代码覆盖率](https://github.com/Microsoft/vstest-docs/blob/master/docs/analyze.md#working-with-code-coverage)。</span><span class="sxs-lookup"><span data-stu-id="f3739-150">Check out [Live Unit Testing](/visualstudio/test/live-unit-testing) or [code coverage](https://github.com/Microsoft/vstest-docs/blob/master/docs/analyze.md#working-with-code-coverage) to learn more.</span></span>
* <span data-ttu-id="f3739-151">有关如何运行选择性单元测试的详细信息，请参阅[运行选择性单元测试](selective-unit-tests.md)或[使用 Visual Studio 添加和排除测试](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods)。</span><span class="sxs-lookup"><span data-stu-id="f3739-151">For more information on how to run selective unit tests, see [Running selective unit tests](selective-unit-tests.md), or [including and excluding tests with Visual Studio](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods).</span></span>
* <span data-ttu-id="f3739-152">[如何通过 .NET Core 和 Visual Studio 使用 xUnit](https://xunit.github.io/docs/getting-started-dotnet-core.html)。</span><span class="sxs-lookup"><span data-stu-id="f3739-152">[How to use xUnit with .NET Core and Visual Studio](https://xunit.github.io/docs/getting-started-dotnet-core.html).</span></span>
