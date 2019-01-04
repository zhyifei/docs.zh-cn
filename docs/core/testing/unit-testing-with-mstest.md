---
title: 使用 MSTest 和 .NET Core 进行 C# 单元测试
description: 通过使用 dotnet test 和 MSTest 分步生成示例解决方案的交互体验，了解 C# 和 .NET Core 中的单元测试概念。
author: ncarandini
ms.author: wiwagn
ms.date: 09/08/2017
ms.custom: seodec18
ms.openlocfilehash: d0da8640393e298c3a6e367433eaa68ebb88fad7
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170267"
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a><span data-ttu-id="fff3a-103">使用 MSTest 和 .NET Core 进行 C# 单元测试</span><span class="sxs-lookup"><span data-stu-id="fff3a-103">Unit testing C# with MSTest and .NET Core</span></span>

<span data-ttu-id="fff3a-104">本教程介绍分步构建示例解决方案的交互式体验，以了解单元测试概念。</span><span class="sxs-lookup"><span data-stu-id="fff3a-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="fff3a-105">如果希望使用预构建解决方案学习本教程，请在开始前[查看或下载示例代码](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/)。</span><span class="sxs-lookup"><span data-stu-id="fff3a-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="fff3a-106">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="fff3a-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="creating-the-source-project"></a><span data-ttu-id="fff3a-107">创建源项目</span><span class="sxs-lookup"><span data-stu-id="fff3a-107">Creating the source project</span></span>

<span data-ttu-id="fff3a-108">打开 shell 窗口。</span><span class="sxs-lookup"><span data-stu-id="fff3a-108">Open a shell window.</span></span> <span data-ttu-id="fff3a-109">创建一个名为 unit-testing-using-mstest 的目录，用以保存解决方案。</span><span class="sxs-lookup"><span data-stu-id="fff3a-109">Create a directory called *unit-testing-using-mstest* to hold the solution.</span></span> <span data-ttu-id="fff3a-110">在此新目录中，运行 [`dotnet new sln`](../tools/dotnet-new.md) 为类库和测试项目创建新的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="fff3a-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="fff3a-111">接下来，创建 PrimeService 目录。</span><span class="sxs-lookup"><span data-stu-id="fff3a-111">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="fff3a-112">下图显示了当前的目录和文件结构：</span><span class="sxs-lookup"><span data-stu-id="fff3a-112">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="fff3a-113">将 *PrimeService* 作为当前目录，然后运行 [`dotnet new classlib`](../tools/dotnet-new.md) 以创建源项目。</span><span class="sxs-lookup"><span data-stu-id="fff3a-113">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="fff3a-114">将 *Class1.cs* 重命名为 *PrimeService.cs*。</span><span class="sxs-lookup"><span data-stu-id="fff3a-114">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="fff3a-115">为了使用由测试驱动的开发 (TDD)，需对 `PrimeService` 类创建故障实现：</span><span class="sxs-lookup"><span data-stu-id="fff3a-115">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="fff3a-116">将目录更改回 unit-testing-using-mstest 目录。</span><span class="sxs-lookup"><span data-stu-id="fff3a-116">Change the directory back to the *unit-testing-using-mstest* directory.</span></span> <span data-ttu-id="fff3a-117">运行 [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) 向解决方案添加类库项目。</span><span class="sxs-lookup"><span data-stu-id="fff3a-117">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span> 

### <a name="creating-the-test-project"></a><span data-ttu-id="fff3a-118">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="fff3a-118">Creating the test project</span></span>

<span data-ttu-id="fff3a-119">接下来，创建 PrimeService.Tests 目录。</span><span class="sxs-lookup"><span data-stu-id="fff3a-119">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="fff3a-120">下图显示了它的目录结构：</span><span class="sxs-lookup"><span data-stu-id="fff3a-120">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="fff3a-121">将 *PrimeService.Tests* 目录作为当前目录，并使用 [`dotnet new mstest`](../tools/dotnet-new.md) 创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="fff3a-121">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="fff3a-122">dotnet 新命令会创建一个将 MStest 用作测试库的测试项目。</span><span class="sxs-lookup"><span data-stu-id="fff3a-122">The dotnet new command creates a test project that uses MStest as the test library.</span></span> <span data-ttu-id="fff3a-123">生成的模板在 *PrimeServiceTests.csproj* 文件中配置测试运行程序：</span><span class="sxs-lookup"><span data-stu-id="fff3a-123">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="fff3a-124">测试项目需要其他包创建和运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="fff3a-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="fff3a-125">上一步中的 `dotnet new` 添加了 MSTest SDK、MSTest 测试框架和 MSTest 运行程序。</span><span class="sxs-lookup"><span data-stu-id="fff3a-125">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="fff3a-126">现在，将 `PrimeService` 类库作为另一个依赖项添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="fff3a-126">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="fff3a-127">使用 [`dotnet add reference`](../tools/dotnet-add-reference.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="fff3a-127">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="fff3a-128">可以在 GitHub 上的[示例存储库](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj)中看到整个文件。</span><span class="sxs-lookup"><span data-stu-id="fff3a-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="fff3a-129">下图显示了最终的解决方案布局：</span><span class="sxs-lookup"><span data-stu-id="fff3a-129">The following outline shows the final solution layout:</span></span>

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

<span data-ttu-id="fff3a-130">在 unit-testing-using-mstest 目录中执行 [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md)。</span><span class="sxs-lookup"><span data-stu-id="fff3a-130">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-mstest* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="fff3a-131">创建第一个测试</span><span class="sxs-lookup"><span data-stu-id="fff3a-131">Creating the first test</span></span>

<span data-ttu-id="fff3a-132">TDD 方法要求编写一个失败的测试，使其通过测试，然后重复该过程。</span><span class="sxs-lookup"><span data-stu-id="fff3a-132">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="fff3a-133">从 *PrimeService.Tests* 目录删除 *UnitTest1.cs*，并创建一个名为 *PrimeService_IsPrimeShould.cs* 且包含以下内容的新 C# 文件：</span><span class="sxs-lookup"><span data-stu-id="fff3a-133">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

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

<span data-ttu-id="fff3a-134">`[TestClass]` 属性表示包含单元测试的类。</span><span class="sxs-lookup"><span data-stu-id="fff3a-134">The `[TestClass]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="fff3a-135">`[TestMethod]` 属性指示方法是测试方法。</span><span class="sxs-lookup"><span data-stu-id="fff3a-135">The `[TestMethod]` attribute indicates a method is a test method.</span></span> 

<span data-ttu-id="fff3a-136">保存此文件并执行 [`dotnet test`](../tools/dotnet-test.md) 以构建测试和类库，然后运行测试。</span><span class="sxs-lookup"><span data-stu-id="fff3a-136">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="fff3a-137">MSTest 测试运行程序包含要运行测试的程序入口点。</span><span class="sxs-lookup"><span data-stu-id="fff3a-137">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="fff3a-138">`dotnet test` 使用已创建的单元测试项目启动测试运行程序。</span><span class="sxs-lookup"><span data-stu-id="fff3a-138">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="fff3a-139">测试失败。</span><span class="sxs-lookup"><span data-stu-id="fff3a-139">Your test fails.</span></span> <span data-ttu-id="fff3a-140">尚未创建实现。</span><span class="sxs-lookup"><span data-stu-id="fff3a-140">You haven't created the implementation yet.</span></span> <span data-ttu-id="fff3a-141">在起作用的 `PrimeService` 类中编写最简单的代码，使此测试通过：</span><span class="sxs-lookup"><span data-stu-id="fff3a-141">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="fff3a-142">在 unit-testing-using-mstest 目录中，再次运行 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="fff3a-142">In the *unit-testing-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="fff3a-143">`dotnet test` 命令构建 `PrimeService` 项目，然后构建 `PrimeService.Tests` 项目。</span><span class="sxs-lookup"><span data-stu-id="fff3a-143">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="fff3a-144">构建这两个项目后，该命令将运行此单项测试。</span><span class="sxs-lookup"><span data-stu-id="fff3a-144">After building both projects, it runs this single test.</span></span> <span data-ttu-id="fff3a-145">测试通过。</span><span class="sxs-lookup"><span data-stu-id="fff3a-145">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="fff3a-146">添加更多功能</span><span class="sxs-lookup"><span data-stu-id="fff3a-146">Adding more features</span></span>

<span data-ttu-id="fff3a-147">你已经通过了一个测试，现在可以编写更多测试。</span><span class="sxs-lookup"><span data-stu-id="fff3a-147">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="fff3a-148">质数有其他几种简单情况：0、-1。</span><span class="sxs-lookup"><span data-stu-id="fff3a-148">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="fff3a-149">可以添加具有 `[TestMethod]` 属性的新测试，但这很快就会变得枯燥乏味。</span><span class="sxs-lookup"><span data-stu-id="fff3a-149">You could add new tests with the `[TestMethod]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="fff3a-150">还有其他 MSTest 属性，使用这些属性可编写类似测试的套件。</span><span class="sxs-lookup"><span data-stu-id="fff3a-150">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="fff3a-151">`[DataTestMethod]` 属性表示执行相同代码，但具有不同输入参数的测试套件。</span><span class="sxs-lookup"><span data-stu-id="fff3a-151">A `[DataTestMethod]`attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="fff3a-152">可以使用 `[DataRow]` 属性来指定这些输入的值。</span><span class="sxs-lookup"><span data-stu-id="fff3a-152">You can use the `[DataRow]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="fff3a-153">可以不使用这两个属性创建新测试，而用来创建单个数据驱动的测试。</span><span class="sxs-lookup"><span data-stu-id="fff3a-153">Instead of creating new tests, apply these two attributes to create a single data driven test.</span></span> <span data-ttu-id="fff3a-154">数据驱动的测试方法用于测试多个小于 2（即最小质数）的值：</span><span class="sxs-lookup"><span data-stu-id="fff3a-154">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="fff3a-155">运行 `dotnet test`，两项测试均失败。</span><span class="sxs-lookup"><span data-stu-id="fff3a-155">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="fff3a-156">若要使所有测试通过，可以更改方法开头的 `if` 子句：</span><span class="sxs-lookup"><span data-stu-id="fff3a-156">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="fff3a-157">通过在主库中添加更多测试、理论和代码继续循环访问。</span><span class="sxs-lookup"><span data-stu-id="fff3a-157">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="fff3a-158">你将拥有[已完成的测试版本](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs)和[库的完整实现](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs)。</span><span class="sxs-lookup"><span data-stu-id="fff3a-158">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="fff3a-159">你已生成一个小型库和该库的一组单元测试。</span><span class="sxs-lookup"><span data-stu-id="fff3a-159">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="fff3a-160">你已将解决方案结构化，使添加新包和新测试成为了正常工作流的一部分。</span><span class="sxs-lookup"><span data-stu-id="fff3a-160">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="fff3a-161">你已将多数的时间和精力集中在解决应用程序的目标上。</span><span class="sxs-lookup"><span data-stu-id="fff3a-161">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
