---
title: 使用 dotnet test 和 xUnit 在 .NET Core 中进行 C# 代码单元测试
description: 通过使用 dotnet test 和 xUnit 分步生成示例解决方案的交互体验，了解 C# 和 .NET Core 中的单元测试概念。
author: ardalis
ms.author: wiwagn
ms.date: 11/29/2017
ms.custom: seodec18
ms.openlocfilehash: 97cf42c78154375ce06639d4a3029ed87b993ced
ms.sourcegitcommit: 8258515adc6c37ab6278e5a3d102d593246f8672
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "58504348"
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="4fe86-103">使用 dotnet test 和 xUnit 在 .NET Core 中进行 C# 单元测试</span><span class="sxs-lookup"><span data-stu-id="4fe86-103">Unit testing C# in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="4fe86-104">本教程介绍分步构建示例解决方案的交互式体验，以了解单元测试概念。</span><span class="sxs-lookup"><span data-stu-id="4fe86-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="4fe86-105">如果希望使用预构建解决方案学习本教程，请在开始前[查看或下载示例代码](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/)。</span><span class="sxs-lookup"><span data-stu-id="4fe86-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/) before you begin.</span></span> <span data-ttu-id="4fe86-106">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="4fe86-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="4fe86-107">创建源项目</span><span class="sxs-lookup"><span data-stu-id="4fe86-107">Creating the source project</span></span>

<span data-ttu-id="4fe86-108">打开 shell 窗口。</span><span class="sxs-lookup"><span data-stu-id="4fe86-108">Open a shell window.</span></span> <span data-ttu-id="4fe86-109">创建一个名为 *unit-testing-using-dotnet-test* 的目录，以保留该解决方案。</span><span class="sxs-lookup"><span data-stu-id="4fe86-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span>
<span data-ttu-id="4fe86-110">在此新目录中，运行 [`dotnet new sln`](../tools/dotnet-new.md) 创建新的解决方案。</span><span class="sxs-lookup"><span data-stu-id="4fe86-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="4fe86-111">通过解决方案，可轻松管理类库和单元测试项目。</span><span class="sxs-lookup"><span data-stu-id="4fe86-111">Having a solution makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="4fe86-112">在解决方案目录中，创建 PrimeService 目录。</span><span class="sxs-lookup"><span data-stu-id="4fe86-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="4fe86-113">现在，目录和文件结构应如下所示：</span><span class="sxs-lookup"><span data-stu-id="4fe86-113">The directory and file structure thus far should be as follows:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

<span data-ttu-id="4fe86-114">将 *PrimeService* 作为当前目录，然后运行 [`dotnet new classlib`](../tools/dotnet-new.md) 以创建源项目。</span><span class="sxs-lookup"><span data-stu-id="4fe86-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="4fe86-115">将 *Class1.cs* 重命名为 *PrimeService.cs*。</span><span class="sxs-lookup"><span data-stu-id="4fe86-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="4fe86-116">首先创建 `PrimeService` 类的失败实现：</span><span class="sxs-lookup"><span data-stu-id="4fe86-116">You first create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="4fe86-117">将目录更改回 unit-testing-using-dotnet-test 目录。</span><span class="sxs-lookup"><span data-stu-id="4fe86-117">Change the directory back to the *unit-testing-using-dotnet-test* directory.</span></span>

<span data-ttu-id="4fe86-118">运行 [dotnet sln](../tools/dotnet-sln.md) 命令，向解决方案添加类库项目：</span><span class="sxs-lookup"><span data-stu-id="4fe86-118">Run the [dotnet sln](../tools/dotnet-sln.md) command to add the class library project to the solution:</span></span>

```
dotnet sln add ./PrimeService/PrimeService.csproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="4fe86-119">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="4fe86-119">Creating the test project</span></span>

<span data-ttu-id="4fe86-120">接下来，创建 PrimeService.Tests 目录。</span><span class="sxs-lookup"><span data-stu-id="4fe86-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="4fe86-121">下图显示了它的目录结构：</span><span class="sxs-lookup"><span data-stu-id="4fe86-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="4fe86-122">将 *PrimeService.Tests* 目录作为当前目录，并使用 [`dotnet new xunit`](../tools/dotnet-new.md) 创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="4fe86-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="4fe86-123">此命令会创建将 [xUnit](https://xunit.github.io/) 用作测试库的测试项目。</span><span class="sxs-lookup"><span data-stu-id="4fe86-123">This command creates a test project that uses [xUnit](https://xunit.github.io/) as the test library.</span></span> <span data-ttu-id="4fe86-124">生成的模板在 PrimeServiceTests.csproj 文件中配置测试运行程序，类似以下代码：</span><span class="sxs-lookup"><span data-stu-id="4fe86-124">The generated template configures the test runner in the *PrimeServiceTests.csproj* file similar to the following code:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="4fe86-125">测试项目需要其他包创建和运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="4fe86-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="4fe86-126">`dotnet new` 在以前的步骤中已添加 xUnit 和 xUnit 运行程序。</span><span class="sxs-lookup"><span data-stu-id="4fe86-126">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="4fe86-127">现在，将 `PrimeService` 类库作为另一个依赖项添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="4fe86-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="4fe86-128">使用 [`dotnet add reference`](../tools/dotnet-add-reference.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="4fe86-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="4fe86-129">可以在 GitHub 上的[示例存储库](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj)中看到整个文件。</span><span class="sxs-lookup"><span data-stu-id="4fe86-129">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="4fe86-130">下面显示的是最终的解决方案布局：</span><span class="sxs-lookup"><span data-stu-id="4fe86-130">The following shows the final solution layout:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="4fe86-131">若要向解决方案添加测试项目，请在 unit-testing-using-dotnet-test 目录下运行 [dotnet sln](../tools/dotnet-sln.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="4fe86-131">To add the test project to the solution, run the [dotnet sln](../tools/dotnet-sln.md) command in the *unit-testing-using-dotnet-test* directory:</span></span>

```
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="4fe86-132">创建第一个测试</span><span class="sxs-lookup"><span data-stu-id="4fe86-132">Creating the first test</span></span>

<span data-ttu-id="4fe86-133">编写一个失败测试，使其通过，然后重复此过程。</span><span class="sxs-lookup"><span data-stu-id="4fe86-133">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="4fe86-134">从 PrimeService.Tests 目录删除 UnitTest1.cs，并创建一个名为 PrimeService_IsPrimeShould.cs 的新 C# 文件。</span><span class="sxs-lookup"><span data-stu-id="4fe86-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs*.</span></span> <span data-ttu-id="4fe86-135">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="4fe86-135">Add the following code:</span></span>

```csharp
using Xunit;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Fact]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="4fe86-136">`[Fact]` 属性指示由测试运行程序运行的测试方法。</span><span class="sxs-lookup"><span data-stu-id="4fe86-136">The `[Fact]` attribute indicates a test method that is run by the test runner.</span></span> <span data-ttu-id="4fe86-137">在 PrimeService.Tests 文件夹中，执行 [`dotnet test`](../tools/dotnet-test.md)，以生成测试和类库，然后运行测试。</span><span class="sxs-lookup"><span data-stu-id="4fe86-137">From the *PrimeService.Tests* folder, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="4fe86-138">xUnit 测试运行程序包含要运行测试的程序入口点。</span><span class="sxs-lookup"><span data-stu-id="4fe86-138">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="4fe86-139">`dotnet test` 使用已创建的单元测试项目启动测试运行程序。</span><span class="sxs-lookup"><span data-stu-id="4fe86-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="4fe86-140">测试失败。</span><span class="sxs-lookup"><span data-stu-id="4fe86-140">Your test fails.</span></span> <span data-ttu-id="4fe86-141">尚未创建实现。</span><span class="sxs-lookup"><span data-stu-id="4fe86-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="4fe86-142">在起作用的 `PrimeService` 类中编写最简单的代码，使此测试通过。</span><span class="sxs-lookup"><span data-stu-id="4fe86-142">Make this test pass by writing the simplest code in the `PrimeService` class that works.</span></span> <span data-ttu-id="4fe86-143">将现有的 `IsPrime` 方法实现替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="4fe86-143">Replace the existing `IsPrime` method implementation with the following code:</span></span>

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

<span data-ttu-id="4fe86-144">在 *PrimeService.Tests* 目录中，再次运行 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="4fe86-144">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="4fe86-145">`dotnet test` 命令构建 `PrimeService` 项目，然后构建 `PrimeService.Tests` 项目。</span><span class="sxs-lookup"><span data-stu-id="4fe86-145">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="4fe86-146">构建这两个项目后，该命令将运行此单项测试。</span><span class="sxs-lookup"><span data-stu-id="4fe86-146">After building both projects, it runs this single test.</span></span> <span data-ttu-id="4fe86-147">测试通过。</span><span class="sxs-lookup"><span data-stu-id="4fe86-147">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="4fe86-148">添加更多功能</span><span class="sxs-lookup"><span data-stu-id="4fe86-148">Adding more features</span></span>

<span data-ttu-id="4fe86-149">你已经通过了一个测试，现在可以编写更多测试。</span><span class="sxs-lookup"><span data-stu-id="4fe86-149">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="4fe86-150">质数有其他几种简单情况：0、-1。</span><span class="sxs-lookup"><span data-stu-id="4fe86-150">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="4fe86-151">可以将这些情况添加为具有 `[Fact]` 属性的新测试，但这很快就会变得枯燥乏味。</span><span class="sxs-lookup"><span data-stu-id="4fe86-151">You could add those cases as new tests with the `[Fact]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="4fe86-152">还有其他 xUnit 属性，可使你编写类似测试套件：</span><span class="sxs-lookup"><span data-stu-id="4fe86-152">There are other xUnit attributes that enable you to write a suite of similar tests:</span></span>

- <span data-ttu-id="4fe86-153">`[Theory]` 表示执行相同代码，但具有不同输入参数的测试套件。</span><span class="sxs-lookup"><span data-stu-id="4fe86-153">`[Theory]` represents a suite of tests that execute the same code but have different input arguments.</span></span>

- <span data-ttu-id="4fe86-154">`[InlineData]` 属性指定这些输入的值。</span><span class="sxs-lookup"><span data-stu-id="4fe86-154">`[InlineData]` attribute specifies values for those inputs.</span></span>

<span data-ttu-id="4fe86-155">可应用这两个属性（`[Theory]` 和 `[InlineData]`）在 PrimeService_IsPrimeShould.cs 文件中创建单一理论，而不是创建新测试。</span><span class="sxs-lookup"><span data-stu-id="4fe86-155">Instead of creating new tests, apply these two attributes, `[Theory]` and `[InlineData]`, to create a single theory in the *PrimeService_IsPrimeShould.cs* file.</span></span> <span data-ttu-id="4fe86-156">此索引是测试多个小于 2（即最小的质数）的值的方法：</span><span class="sxs-lookup"><span data-stu-id="4fe86-156">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="4fe86-157">再次运行 `dotnet test`，其中两个测试应失败。</span><span class="sxs-lookup"><span data-stu-id="4fe86-157">Run `dotnet test` again, and two of these tests should fail.</span></span> <span data-ttu-id="4fe86-158">若要使所有测试通过，可以在 PrimeService.cs 文件中更改 `IsPrime` 方法开头的 `if` 子句：</span><span class="sxs-lookup"><span data-stu-id="4fe86-158">To make all of the tests pass, change the `if` clause at the beginning of the `IsPrime` method in the *PrimeService.cs* file:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="4fe86-159">通过在主库中添加更多测试、理论和代码继续循环访问。</span><span class="sxs-lookup"><span data-stu-id="4fe86-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="4fe86-160">你将拥有[已完成的测试版本](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs)和[库的完整实现](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs)。</span><span class="sxs-lookup"><span data-stu-id="4fe86-160">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4fe86-161">其他资源</span><span class="sxs-lookup"><span data-stu-id="4fe86-161">Additional resources</span></span>

- [<span data-ttu-id="4fe86-162">xUnit.net 官方网站</span><span class="sxs-lookup"><span data-stu-id="4fe86-162">xUnit.net official site</span></span>](https://xunit.github.io)
- [<span data-ttu-id="4fe86-163">ASP.NET Core 中的测试控制器逻辑</span><span class="sxs-lookup"><span data-stu-id="4fe86-163">Testing controller logic in ASP.NET Core</span></span>](/aspnet/core/mvc/controllers/testing)
