---
title: "使用 .NET 测试和 xUnit 的 .NET Core 单元测试"
description: "通过使用 dotnet test 和 xUnit 分步生成示例解决方案的交互体验，了解 .NET Core 中的单元测试概念。"
author: ardalis
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.translationtype: HT
ms.sourcegitcommit: 867f9eb286fa7ff5ef3e9167c1ab944c81161216
ms.openlocfilehash: d989ee731d7ffd0439bac69afe1458e2aa10733a
ms.contentlocale: zh-cn
ms.lasthandoff: 08/17/2017

---
# <a name="unit-testing-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="30122-103">使用 .NET 测试和 xUnit 的 .NET Core 单元测试</span><span class="sxs-lookup"><span data-stu-id="30122-103">Unit testing in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="30122-104">本教程介绍分步构建示例解决方案的交互式体验，以了解单元测试概念。</span><span class="sxs-lookup"><span data-stu-id="30122-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="30122-105">如果希望使用预构建解决方案学习本教程，请在开始前[查看或下载示例代码](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/)。</span><span class="sxs-lookup"><span data-stu-id="30122-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) before you begin.</span></span> <span data-ttu-id="30122-106">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="30122-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="30122-107">创建源项目</span><span class="sxs-lookup"><span data-stu-id="30122-107">Creating the source project</span></span>

<span data-ttu-id="30122-108">打开 shell 窗口。</span><span class="sxs-lookup"><span data-stu-id="30122-108">Open a shell window.</span></span> <span data-ttu-id="30122-109">创建一个名为 *unit-testing-using-dotnet-test* 的目录，以保留该解决方案。</span><span class="sxs-lookup"><span data-stu-id="30122-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="30122-110">在此新目录中，创建一个 *PrimeService* 目录。</span><span class="sxs-lookup"><span data-stu-id="30122-110">Inside this new directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="30122-111">目录结构目前如下所示：</span><span class="sxs-lookup"><span data-stu-id="30122-111">The directory structure thus far is shown below:</span></span>

```
/unit-testing-using-dotnet-test
    /PrimeService
```

<span data-ttu-id="30122-112">将 *PrimeService* 作为当前目录，然后运行 [`dotnet new classlib`](../tools/dotnet-new.md) 以创建源项目。</span><span class="sxs-lookup"><span data-stu-id="30122-112">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="30122-113">将 *Class1.cs* 重命名为 *PrimeService.cs*。</span><span class="sxs-lookup"><span data-stu-id="30122-113">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="30122-114">为了使用由测试驱动的开发 (TDD)，需对 `PrimeService` 类创建故障实现：</span><span class="sxs-lookup"><span data-stu-id="30122-114">To use test-driven development (TDD), you'll create a failing implementation of the `PrimeService` class:</span></span>

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

## <a name="creating-the-test-project"></a><span data-ttu-id="30122-115">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="30122-115">Creating the test project</span></span>

<span data-ttu-id="30122-116">将目录更改回 unit-testing-using-dotnet-test 目录，并创建 PrimeService.Tests 目录。</span><span class="sxs-lookup"><span data-stu-id="30122-116">Change the directory back to the *unit-testing-using-dotnet-test* directory and create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="30122-117">目录结构如下所示：</span><span class="sxs-lookup"><span data-stu-id="30122-117">The directory structure is shown below:</span></span>

```
/unit-testing-using-dotnet-test
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="30122-118">将 *PrimeService.Tests* 目录作为当前目录，并使用 [`dotnet new xunit`](../tools/dotnet-new.md) 创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="30122-118">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="30122-119">这会创建将 xUnit 用作测试库的测试项目。</span><span class="sxs-lookup"><span data-stu-id="30122-119">This creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="30122-120">生成的模板在 *PrimeServiceTests.csproj* 中配置了测试运行程序：</span><span class="sxs-lookup"><span data-stu-id="30122-120">The generated template configures the test runner in the *PrimeServiceTests.csproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="30122-121">测试项目需要其他包创建和运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="30122-121">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="30122-122">`dotnet new` 在以前的步骤中已添加 xUnit 和 xUnit 运行程序。</span><span class="sxs-lookup"><span data-stu-id="30122-122">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="30122-123">现在，将 `PrimeService` 类库作为另一个依赖项添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="30122-123">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="30122-124">使用 [`dotnet add reference`](../tools/dotnet-add-reference.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="30122-124">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="30122-125">另一个选项是编辑 *PrimeService.Tests.csproj* 文件。</span><span class="sxs-lookup"><span data-stu-id="30122-125">Another option is to edit the *PrimeService.Tests.csproj* file.</span></span> <span data-ttu-id="30122-126">直接在第一个 `<ItemGroup>` 节点下，添加另一个具有库项目引用的 `<ItemGroup>`：</span><span class="sxs-lookup"><span data-stu-id="30122-126">Directly under the first `<ItemGroup>` node, add another `<ItemGroup>` node with a reference to the library project:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

<span data-ttu-id="30122-127">可以在 GitHub 上的[示例存储库](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj)中看到整个文件。</span><span class="sxs-lookup"><span data-stu-id="30122-127">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="30122-128">最终的解决方案布局如下所示：</span><span class="sxs-lookup"><span data-stu-id="30122-128">The final solution layout is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService
        PrimeServiceTests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="30122-129">创建第一个测试</span><span class="sxs-lookup"><span data-stu-id="30122-129">Creating the first test</span></span>

<span data-ttu-id="30122-130">在构建库或测试前，执行 *PrimeService.Tests* 目录中的 [`dotnet restore`](../tools/dotnet-restore.md)。</span><span class="sxs-lookup"><span data-stu-id="30122-130">Before building the library or the tests, execute [`dotnet restore`](../tools/dotnet-restore.md) in the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="30122-131">此命令将为每个项目还原所有必要的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="30122-131">This command restores all the necessary NuGet packages for each project.</span></span>

<span data-ttu-id="30122-132">TDD 方法要求编写一个失败的测试，使其通过测试，然后重复该过程。</span><span class="sxs-lookup"><span data-stu-id="30122-132">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="30122-133">从 *PrimeService.Tests* 目录删除 *UnitTest1.cs*，并创建一个名为 *PrimeService_IsPrimeShould.cs* 且包含以下内容的新 C# 文件：</span><span class="sxs-lookup"><span data-stu-id="30122-133">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

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

            Assert.False(result, $"1 should not be prime");
        }
    }
}
```

<span data-ttu-id="30122-134">`[Fact]` 属性将方法表示为单个测试。</span><span class="sxs-lookup"><span data-stu-id="30122-134">The `[Fact]` attribute denotes a method as a single test.</span></span> <span data-ttu-id="30122-135">执行 [`dotnet test`](../tools/dotnet-test.md) 以构建测试和类库，然后运行测试。</span><span class="sxs-lookup"><span data-stu-id="30122-135">Execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="30122-136">xUnit 测试运行程序包含要运行测试的程序入口点。</span><span class="sxs-lookup"><span data-stu-id="30122-136">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="30122-137">`dotnet test` 启动测试运行程序，并向该测试运行程序提供命令行参数以指示包含测试的程序集。</span><span class="sxs-lookup"><span data-stu-id="30122-137">`dotnet test` starts the test runner and provides a command-line argument to the test runner indicating the assembly that contains your tests.</span></span>

<span data-ttu-id="30122-138">测试失败。</span><span class="sxs-lookup"><span data-stu-id="30122-138">Your test fails.</span></span> <span data-ttu-id="30122-139">尚未创建实现。</span><span class="sxs-lookup"><span data-stu-id="30122-139">You haven't created the implementation yet.</span></span> <span data-ttu-id="30122-140">在 `PrimeService` 类中编写最简单的代码，使此测试通过：</span><span class="sxs-lookup"><span data-stu-id="30122-140">Write the simplest code in the `PrimeService` class to make this test pass:</span></span>

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

<span data-ttu-id="30122-141">在 *PrimeService.Tests* 目录中，再次运行 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="30122-141">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="30122-142">`dotnet test` 命令构建 `PrimeService` 项目，然后构建 `PrimeService.Tests` 项目。</span><span class="sxs-lookup"><span data-stu-id="30122-142">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="30122-143">构建这两个项目后，该命令将运行此单项测试。</span><span class="sxs-lookup"><span data-stu-id="30122-143">After building both projects, it runs this single test.</span></span> <span data-ttu-id="30122-144">测试通过。</span><span class="sxs-lookup"><span data-stu-id="30122-144">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="30122-145">添加更多功能</span><span class="sxs-lookup"><span data-stu-id="30122-145">Adding more features</span></span>

<span data-ttu-id="30122-146">你已经通过了一个测试，现在可以编写更多测试。</span><span class="sxs-lookup"><span data-stu-id="30122-146">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="30122-147">质数有其他几种简单情况：0，-1。</span><span class="sxs-lookup"><span data-stu-id="30122-147">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="30122-148">可以将其添加为具有 `[Fact]` 属性的新测试，但这很快就会变得枯燥乏味。</span><span class="sxs-lookup"><span data-stu-id="30122-148">You could add those as new tests with the `[Fact]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="30122-149">还有其他 xUnit 属性，可使你编写类似测试套件。</span><span class="sxs-lookup"><span data-stu-id="30122-149">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="30122-150">`[Theory]` 属性表示执行相同代码，但具有不同输入参数一系列测试。</span><span class="sxs-lookup"><span data-stu-id="30122-150">A `[Theory]` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="30122-151">可以使用 `[InlineData]` 属性来指定这些输入的值。</span><span class="sxs-lookup"><span data-stu-id="30122-151">You can use the `[InlineData]` attribute to specify values for those inputs.</span></span> 
 
<span data-ttu-id="30122-152">利用这两个属性来创建测试小于 2 的几个值的单个理论（而不是创建新测试），其中，2 是最小质数：</span><span class="sxs-lookup"><span data-stu-id="30122-152">Instead of creating new tests, leverage these two attributes to create a single theory that tests several values less than two, which is the lowest prime number:</span></span>

<span data-ttu-id="30122-153">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span><span class="sxs-lookup"><span data-stu-id="30122-153">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span></span>

<span data-ttu-id="30122-154">运行 `dotnet test`，两项测试均失败。</span><span class="sxs-lookup"><span data-stu-id="30122-154">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="30122-155">若要使所有测试通过，可以更改方法开头的 `if` 子句：</span><span class="sxs-lookup"><span data-stu-id="30122-155">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="30122-156">通过在主库中添加更多测试、理论和代码继续循环访问。</span><span class="sxs-lookup"><span data-stu-id="30122-156">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="30122-157">将以[已完成的测试版本](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs)和[库的完整实现](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs)结束。</span><span class="sxs-lookup"><span data-stu-id="30122-157">You'll end up with the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="30122-158">你已生成一个小型库和该库的一组单元测试。</span><span class="sxs-lookup"><span data-stu-id="30122-158">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="30122-159">已结构化解决方案，以无缝添加新包和测试，并可将大部分时间和精力投入到解决应用程序的目标中。</span><span class="sxs-lookup"><span data-stu-id="30122-159">You've structured the solution so that adding new packages and tests is seamless, and you can concentrate most of your time and effort on solving the goals of the applicaiton.</span></span>

