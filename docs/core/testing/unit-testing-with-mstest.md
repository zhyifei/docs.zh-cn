---
title: 使用 MSTest 和 .NET Core 进行 C# 单元测试
description: 通过使用 dotnet test 和 MSTest 分步生成示例解决方案的交互体验，了解 C# 和 .NET Core 中的单元测试概念。
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 09/08/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
ms.workload:
- dotnetcore
ms.openlocfilehash: 742e0f5707580f70ed068fff18faa7b5e2fd8625
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a><span data-ttu-id="b9337-104">使用 MSTest 和 .NET Core 进行 C# 单元测试</span><span class="sxs-lookup"><span data-stu-id="b9337-104">Unit testing C# with MSTest and .NET Core</span></span>

<span data-ttu-id="b9337-105">本教程介绍分步构建示例解决方案的交互式体验，以了解单元测试概念。</span><span class="sxs-lookup"><span data-stu-id="b9337-105">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="b9337-106">如果希望使用预构建解决方案学习本教程，请在开始前[查看或下载示例代码](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/)。</span><span class="sxs-lookup"><span data-stu-id="b9337-106">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="b9337-107">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="b9337-107">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="creating-the-source-project"></a><span data-ttu-id="b9337-108">创建源项目</span><span class="sxs-lookup"><span data-stu-id="b9337-108">Creating the source project</span></span>

<span data-ttu-id="b9337-109">打开 shell 窗口。</span><span class="sxs-lookup"><span data-stu-id="b9337-109">Open a shell window.</span></span> <span data-ttu-id="b9337-110">创建一个名为 *unit-testing-using-dotnet-test* 的目录，以保留该解决方案。</span><span class="sxs-lookup"><span data-stu-id="b9337-110">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="b9337-111">在此新目录中，运行 [`dotnet new sln`](../tools/dotnet-new.md) 为类库和测试项目创建新的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="b9337-111">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="b9337-112">接下来，创建 PrimeService 目录。</span><span class="sxs-lookup"><span data-stu-id="b9337-112">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="b9337-113">下图显示了当前的目录和文件结构：</span><span class="sxs-lookup"><span data-stu-id="b9337-113">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="b9337-114">将 *PrimeService* 作为当前目录，然后运行 [`dotnet new classlib`](../tools/dotnet-new.md) 以创建源项目。</span><span class="sxs-lookup"><span data-stu-id="b9337-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="b9337-115">将 *Class1.cs* 重命名为 *PrimeService.cs*。</span><span class="sxs-lookup"><span data-stu-id="b9337-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="b9337-116">为了使用由测试驱动的开发 (TDD)，需对 `PrimeService` 类创建故障实现：</span><span class="sxs-lookup"><span data-stu-id="b9337-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="b9337-117">将目录更改回 unit-testing-using-mstest 目录。</span><span class="sxs-lookup"><span data-stu-id="b9337-117">Change the directory back to the *unit-testing-using-mstest* directory.</span></span> <span data-ttu-id="b9337-118">运行 [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) 向解决方案添加类库项目。</span><span class="sxs-lookup"><span data-stu-id="b9337-118">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span> 

### <a name="creating-the-test-project"></a><span data-ttu-id="b9337-119">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="b9337-119">Creating the test project</span></span>

<span data-ttu-id="b9337-120">接下来，创建 PrimeService.Tests 目录。</span><span class="sxs-lookup"><span data-stu-id="b9337-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="b9337-121">下图显示了它的目录结构：</span><span class="sxs-lookup"><span data-stu-id="b9337-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="b9337-122">将 *PrimeService.Tests* 目录作为当前目录，并使用 [`dotnet new mstest`](../tools/dotnet-new.md) 创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="b9337-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="b9337-123">dotnet 新命令会创建一个将 MStest 用作测试库的测试项目。</span><span class="sxs-lookup"><span data-stu-id="b9337-123">The dotnet new command creates a test project that uses MStest as the test library.</span></span> <span data-ttu-id="b9337-124">生成的模板在 *PrimeServiceTests.csproj* 文件中配置测试运行程序：</span><span class="sxs-lookup"><span data-stu-id="b9337-124">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="b9337-125">测试项目需要其他包创建和运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="b9337-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="b9337-126">上一步中的 `dotnet new` 添加了 MSTest SDK、MSTest 测试框架和 MSTest 运行程序。</span><span class="sxs-lookup"><span data-stu-id="b9337-126">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="b9337-127">现在，将 `PrimeService` 类库作为另一个依赖项添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="b9337-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="b9337-128">使用 [`dotnet add reference`](../tools/dotnet-add-reference.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="b9337-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="b9337-129">可以在 GitHub 上的[示例存储库](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj)中看到整个文件。</span><span class="sxs-lookup"><span data-stu-id="b9337-129">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="b9337-130">下图显示了最终的解决方案布局：</span><span class="sxs-lookup"><span data-stu-id="b9337-130">The following outline shows the final solution layout:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="b9337-131">在 unit-testing-using-dotnet-test 目录中执行 [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md)。</span><span class="sxs-lookup"><span data-stu-id="b9337-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-dotnet-test* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="b9337-132">创建第一个测试</span><span class="sxs-lookup"><span data-stu-id="b9337-132">Creating the first test</span></span>

<span data-ttu-id="b9337-133">TDD 方法要求编写一个失败的测试，使其通过测试，然后重复该过程。</span><span class="sxs-lookup"><span data-stu-id="b9337-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="b9337-134">从 *PrimeService.Tests* 目录删除 *UnitTest1.cs*，并创建一个名为 *PrimeService_IsPrimeShould.cs* 且包含以下内容的新 C# 文件：</span><span class="sxs-lookup"><span data-stu-id="b9337-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestClass]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [TestMethod]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="b9337-135">`[TestClass]` 属性表示包含单元测试的类。</span><span class="sxs-lookup"><span data-stu-id="b9337-135">The `[TestClass]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="b9337-136">`[TestMethod]` 属性指示方法是测试方法。</span><span class="sxs-lookup"><span data-stu-id="b9337-136">The `[TestMethod]` attribute indicates a method is a test method.</span></span> 

<span data-ttu-id="b9337-137">保存此文件并执行 [`dotnet test`](../tools/dotnet-test.md) 以构建测试和类库，然后运行测试。</span><span class="sxs-lookup"><span data-stu-id="b9337-137">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="b9337-138">MSTest 测试运行程序包含要运行测试的程序入口点。</span><span class="sxs-lookup"><span data-stu-id="b9337-138">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="b9337-139">`dotnet test` 使用已创建的单元测试项目启动测试运行程序。</span><span class="sxs-lookup"><span data-stu-id="b9337-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="b9337-140">测试失败。</span><span class="sxs-lookup"><span data-stu-id="b9337-140">Your test fails.</span></span> <span data-ttu-id="b9337-141">尚未创建实现。</span><span class="sxs-lookup"><span data-stu-id="b9337-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="b9337-142">在起作用的 `PrimeService` 类中编写最简单的代码，使此测试通过：</span><span class="sxs-lookup"><span data-stu-id="b9337-142">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="b9337-143">在 unit-testing-using-mstest 目录中，再次运行 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="b9337-143">In the *unit-testing-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="b9337-144">`dotnet test` 命令构建 `PrimeService` 项目，然后构建 `PrimeService.Tests` 项目。</span><span class="sxs-lookup"><span data-stu-id="b9337-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="b9337-145">构建这两个项目后，该命令将运行此单项测试。</span><span class="sxs-lookup"><span data-stu-id="b9337-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="b9337-146">测试通过。</span><span class="sxs-lookup"><span data-stu-id="b9337-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="b9337-147">添加更多功能</span><span class="sxs-lookup"><span data-stu-id="b9337-147">Adding more features</span></span>

<span data-ttu-id="b9337-148">你已经通过了一个测试，现在可以编写更多测试。</span><span class="sxs-lookup"><span data-stu-id="b9337-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="b9337-149">质数有其他几种简单情况：0，-1。</span><span class="sxs-lookup"><span data-stu-id="b9337-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="b9337-150">可以添加具有 `[TestMethod]` 属性的新测试，但这很快就会变得枯燥乏味。</span><span class="sxs-lookup"><span data-stu-id="b9337-150">You could add new tests with the `[TestMethod]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="b9337-151">还有其他 MSTest 属性，使用这些属性可编写类似测试的套件。</span><span class="sxs-lookup"><span data-stu-id="b9337-151">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="b9337-152">`[DataTestMethod]` 属性表示执行相同代码，但具有不同输入参数的测试套件。</span><span class="sxs-lookup"><span data-stu-id="b9337-152">A `[DataTestMethod]`attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="b9337-153">可以使用 `[DataRow]` 属性来指定这些输入的值。</span><span class="sxs-lookup"><span data-stu-id="b9337-153">You can use the `[DataRow]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="b9337-154">可以不使用这两个属性创建新测试，而用来创建单个数据驱动的测试。</span><span class="sxs-lookup"><span data-stu-id="b9337-154">Instead of creating new tests, apply these two attributes to create a single data driven test.</span></span> <span data-ttu-id="b9337-155">数据驱动测试方法用于测试多个小于 2（即最小的质数）的值：</span><span class="sxs-lookup"><span data-stu-id="b9337-155">The data driven test is a method that tests several values less than two, which is the lowest prime number: :</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="b9337-156">运行 `dotnet test`，两项测试均失败。</span><span class="sxs-lookup"><span data-stu-id="b9337-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="b9337-157">若要使所有测试通过，可以更改方法开头的 `if` 子句：</span><span class="sxs-lookup"><span data-stu-id="b9337-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="b9337-158">通过在主库中添加更多测试、理论和代码继续循环访问。</span><span class="sxs-lookup"><span data-stu-id="b9337-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="b9337-159">你将拥有[已完成的测试版本](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs)和[库的完整实现](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs)。</span><span class="sxs-lookup"><span data-stu-id="b9337-159">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="b9337-160">你已生成一个小型库和该库的一组单元测试。</span><span class="sxs-lookup"><span data-stu-id="b9337-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="b9337-161">你已将解决方案结构化，使添加新包和新测试成为了正常工作流的一部分。</span><span class="sxs-lookup"><span data-stu-id="b9337-161">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="b9337-162">你已将多数的时间和精力集中在解决应用程序的目标上。</span><span class="sxs-lookup"><span data-stu-id="b9337-162">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
