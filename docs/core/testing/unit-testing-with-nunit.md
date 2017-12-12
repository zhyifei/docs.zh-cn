---
title: "使用 NUnit 和 .NET Core 进行 C# 单元测试"
description: "使用 dotnet test 和 NUnit 分步构建一个示例解决方案，在此交互式体验中学习 C# 和 .NET Core 中的单元测试概念。"
keywords: NUnit, .NETm, .NET Core
author: rprouse
ms.date: 12/01/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.openlocfilehash: ad410497adc641e89bd9845ed69c063692ad2f73
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2017
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a><span data-ttu-id="4548b-104">使用 NUnit 和 .NET Core 进行 C# 单元测试</span><span class="sxs-lookup"><span data-stu-id="4548b-104">Unit testing C# with NUnit and .NET Core</span></span>

<span data-ttu-id="4548b-105">本教程介绍分步构建示例解决方案的交互式体验，以了解单元测试概念。</span><span class="sxs-lookup"><span data-stu-id="4548b-105">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="4548b-106">如果希望使用预构建解决方案学习本教程，请在开始前[查看或下载示例代码](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/)。</span><span class="sxs-lookup"><span data-stu-id="4548b-106">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/) before you begin.</span></span> <span data-ttu-id="4548b-107">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="4548b-107">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="4548b-108">创建源项目</span><span class="sxs-lookup"><span data-stu-id="4548b-108">Creating the source project</span></span>

<span data-ttu-id="4548b-109">打开 shell 窗口。</span><span class="sxs-lookup"><span data-stu-id="4548b-109">Open a shell window.</span></span> <span data-ttu-id="4548b-110">创建一个名为 unit-testing-using-nunit 的目录，以保留该解决方案。</span><span class="sxs-lookup"><span data-stu-id="4548b-110">Create a directory called *unit-testing-using-nunit* to hold the solution.</span></span> <span data-ttu-id="4548b-111">在此新目录中，运行 [`dotnet new sln`](../tools/dotnet-new.md) 为类库和测试项目创建新的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="4548b-111">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="4548b-112">接下来，创建 PrimeService 目录。</span><span class="sxs-lookup"><span data-stu-id="4548b-112">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="4548b-113">下图显示了当前的目录和文件结构：</span><span class="sxs-lookup"><span data-stu-id="4548b-113">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

<span data-ttu-id="4548b-114">将 *PrimeService* 作为当前目录，然后运行 [`dotnet new classlib`](../tools/dotnet-new.md) 以创建源项目。</span><span class="sxs-lookup"><span data-stu-id="4548b-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="4548b-115">将 *Class1.cs* 重命名为 *PrimeService.cs*。</span><span class="sxs-lookup"><span data-stu-id="4548b-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="4548b-116">为了使用由测试驱动的开发 (TDD)，需对 `PrimeService` 类创建故障实现：</span><span class="sxs-lookup"><span data-stu-id="4548b-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            throw new NotImplementedException("Please create a test first");
        }
    }
}
```

<span data-ttu-id="4548b-117">将目录更改回 unit-testing-using-nunit 目录。</span><span class="sxs-lookup"><span data-stu-id="4548b-117">Change the directory back to the *unit-testing-using-nunit* directory.</span></span> <span data-ttu-id="4548b-118">运行 [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) 向解决方案添加类库项目。</span><span class="sxs-lookup"><span data-stu-id="4548b-118">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="install-the-nunit-project-template"></a><span data-ttu-id="4548b-119">安装 NUnit 项目模板</span><span class="sxs-lookup"><span data-stu-id="4548b-119">Install the NUnit project template</span></span>

<span data-ttu-id="4548b-120">创建测试项目之前，需安装 NUnit 测试项目模板。</span><span class="sxs-lookup"><span data-stu-id="4548b-120">The NUnit test project templates need to be installed before creating a test project.</span></span> <span data-ttu-id="4548b-121">仅需在新建 NUnit 项目的开发人员计算机上安装一次。</span><span class="sxs-lookup"><span data-stu-id="4548b-121">This only needs to be done once on each developer machine where you'll create new NUnit projects.</span></span> <span data-ttu-id="4548b-122">运行 [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) 以安装 NUnit 模板.</span><span class="sxs-lookup"><span data-stu-id="4548b-122">Run [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) to install the NUnit templates.</span></span>

```
dotnet new -i NUnit3.DotNetNew.Template
```

### <a name="creating-the-test-project"></a><span data-ttu-id="4548b-123">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="4548b-123">Creating the test project</span></span>

<span data-ttu-id="4548b-124">接下来，创建 PrimeService.Tests 目录。</span><span class="sxs-lookup"><span data-stu-id="4548b-124">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="4548b-125">下图显示了它的目录结构：</span><span class="sxs-lookup"><span data-stu-id="4548b-125">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="4548b-126">将 *PrimeService.Tests* 目录作为当前目录，并使用 [`dotnet new nunit`](../tools/dotnet-new.md) 创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="4548b-126">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new nunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="4548b-127">dotnet 新命令会创建一个将 NUnit 用作测试库的测试项目。</span><span class="sxs-lookup"><span data-stu-id="4548b-127">The dotnet new command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="4548b-128">生成的模板在 *PrimeServiceTests.csproj* 文件中配置测试运行程序：</span><span class="sxs-lookup"><span data-stu-id="4548b-128">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="4548b-129">测试项目需要其他包创建和运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="4548b-129">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="4548b-130">在上一步中，`dotnet new` 已添加 Microsoft 测试 SDK、NUnit 测试框架和 NUnit 测试适配器。</span><span class="sxs-lookup"><span data-stu-id="4548b-130">`dotnet new` in the previous step added the Microsoft test SDK, the NUnit test framework, and the NUnit test adapter.</span></span> <span data-ttu-id="4548b-131">现在，将 `PrimeService` 类库作为另一个依赖项添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="4548b-131">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="4548b-132">使用 [`dotnet add reference`](../tools/dotnet-add-reference.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="4548b-132">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="4548b-133">可以在 GitHub 上的[示例存储库](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj)中看到整个文件。</span><span class="sxs-lookup"><span data-stu-id="4548b-133">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="4548b-134">下图显示了最终的解决方案布局：</span><span class="sxs-lookup"><span data-stu-id="4548b-134">The following outline shows the final solution layout:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="4548b-135">在 unit-testing-using-dotnet-test 目录中执行 [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md)。</span><span class="sxs-lookup"><span data-stu-id="4548b-135">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-dotnet-test* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="4548b-136">创建第一个测试</span><span class="sxs-lookup"><span data-stu-id="4548b-136">Creating the first test</span></span>

<span data-ttu-id="4548b-137">TDD 方法要求编写一个失败的测试，使其通过测试，然后重复该过程。</span><span class="sxs-lookup"><span data-stu-id="4548b-137">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="4548b-138">从 *PrimeService.Tests* 目录删除 *UnitTest1.cs*，并创建一个名为 *PrimeService_IsPrimeShould.cs* 且包含以下内容的新 C# 文件：</span><span class="sxs-lookup"><span data-stu-id="4548b-138">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Test]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="4548b-139">`[TestFixture]` 属性表示包含单元测试的类。</span><span class="sxs-lookup"><span data-stu-id="4548b-139">The `[TestFixture]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="4548b-140">`[Test]` 属性指示方法是测试方法。</span><span class="sxs-lookup"><span data-stu-id="4548b-140">The `[Test]` attribute indicates a method is a test method.</span></span>

<span data-ttu-id="4548b-141">保存此文件并执行 [`dotnet test`](../tools/dotnet-test.md) 以构建测试和类库，然后运行测试。</span><span class="sxs-lookup"><span data-stu-id="4548b-141">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="4548b-142">NUnit 测试运行程序包含要运行测试的程序入口点。</span><span class="sxs-lookup"><span data-stu-id="4548b-142">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="4548b-143">`dotnet test` 使用已创建的单元测试项目启动测试运行程序。</span><span class="sxs-lookup"><span data-stu-id="4548b-143">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="4548b-144">测试失败。</span><span class="sxs-lookup"><span data-stu-id="4548b-144">Your test fails.</span></span> <span data-ttu-id="4548b-145">尚未创建实现。</span><span class="sxs-lookup"><span data-stu-id="4548b-145">You haven't created the implementation yet.</span></span> <span data-ttu-id="4548b-146">在起作用的 `PrimeService` 类中编写最简单的代码，使此测试通过：</span><span class="sxs-lookup"><span data-stu-id="4548b-146">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first");
}
```

<span data-ttu-id="4548b-147">在 unit-testing-using-nunit 目录中再次运行 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="4548b-147">In the *unit-testing-using-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="4548b-148">`dotnet test` 命令构建 `PrimeService` 项目，然后构建 `PrimeService.Tests` 项目。</span><span class="sxs-lookup"><span data-stu-id="4548b-148">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="4548b-149">构建这两个项目后，该命令将运行此单项测试。</span><span class="sxs-lookup"><span data-stu-id="4548b-149">After building both projects, it runs this single test.</span></span> <span data-ttu-id="4548b-150">测试通过。</span><span class="sxs-lookup"><span data-stu-id="4548b-150">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="4548b-151">添加更多功能</span><span class="sxs-lookup"><span data-stu-id="4548b-151">Adding more features</span></span>

<span data-ttu-id="4548b-152">你已经通过了一个测试，现在可以编写更多测试。</span><span class="sxs-lookup"><span data-stu-id="4548b-152">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="4548b-153">质数有其他几种简单情况：0，-1。</span><span class="sxs-lookup"><span data-stu-id="4548b-153">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="4548b-154">可以添加具有 `[Test]` 属性的新测试，但这很快就会变得枯燥乏味。</span><span class="sxs-lookup"><span data-stu-id="4548b-154">You could add new tests with the `[Test]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="4548b-155">还有其他 NUnit 属性可用于编写一套类似的测试。</span><span class="sxs-lookup"><span data-stu-id="4548b-155">There are other NUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="4548b-156">`[TestCase]` 属性用于创建一套可执行相同代码但具有不同输入参数的测试。</span><span class="sxs-lookup"><span data-stu-id="4548b-156">A `[TestCase]` attribute is used to create a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="4548b-157">可以使用 `[TestCase]` 属性来指定这些输入的值。</span><span class="sxs-lookup"><span data-stu-id="4548b-157">You can use the `[TestCase]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="4548b-158">无需创建新的测试，而是应用此属性来创建数据驱动的单个测试。</span><span class="sxs-lookup"><span data-stu-id="4548b-158">Instead of creating new tests, apply this attribute to create a single data driven test.</span></span> <span data-ttu-id="4548b-159">数据驱动的测试方法用于测试多个小于 2（即最小质数）的值：</span><span class="sxs-lookup"><span data-stu-id="4548b-159">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="4548b-160">运行 `dotnet test`，两项测试均失败。</span><span class="sxs-lookup"><span data-stu-id="4548b-160">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="4548b-161">若要使所有测试通过，可以更改方法开头的 `if` 子句：</span><span class="sxs-lookup"><span data-stu-id="4548b-161">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="4548b-162">通过在主库中添加更多测试、理论和代码继续循环访问。</span><span class="sxs-lookup"><span data-stu-id="4548b-162">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="4548b-163">你将拥有[已完成的测试版本](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs)和[库的完整实现](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs)。</span><span class="sxs-lookup"><span data-stu-id="4548b-163">You have the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="4548b-164">你已生成一个小型库和该库的一组单元测试。</span><span class="sxs-lookup"><span data-stu-id="4548b-164">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="4548b-165">你已将解决方案结构化，使添加新包和新测试成为了正常工作流的一部分。</span><span class="sxs-lookup"><span data-stu-id="4548b-165">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="4548b-166">你已将多数的时间和精力集中在解决应用程序的目标上。</span><span class="sxs-lookup"><span data-stu-id="4548b-166">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
