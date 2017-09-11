---
title: "使用 MSTest 和 .NET Core 进行单元测试"
description: "如何配合使用 MSTest 与 .NET Core"
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d1cb9f6667e1317e74d246988ef1257d0712c431
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="unit-testing-with-mstest-and-net-core"></a><span data-ttu-id="a732b-104">使用 MSTest 和 .NET Core 进行单元测试</span><span class="sxs-lookup"><span data-stu-id="a732b-104">Unit testing with MSTest and .NET Core</span></span>

<span data-ttu-id="a732b-105">本教程介绍分步构建示例解决方案的交互式体验，以了解单元测试概念。</span><span class="sxs-lookup"><span data-stu-id="a732b-105">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="a732b-106">如果希望使用预构建解决方案学习本教程，请在开始前[查看或下载示例代码](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/)。</span><span class="sxs-lookup"><span data-stu-id="a732b-106">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="a732b-107">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="a732b-107">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="creating-the-source-project"></a><span data-ttu-id="a732b-108">创建源项目</span><span class="sxs-lookup"><span data-stu-id="a732b-108">Creating the source project</span></span>

<span data-ttu-id="a732b-109">打开 shell 窗口。</span><span class="sxs-lookup"><span data-stu-id="a732b-109">Open a shell window.</span></span> <span data-ttu-id="a732b-110">创建一个名为 *unit-testing-using-dotnet-test* 的目录，以保留该解决方案。</span><span class="sxs-lookup"><span data-stu-id="a732b-110">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="a732b-111">在此新目录中，创建一个 *PrimeService* 目录。</span><span class="sxs-lookup"><span data-stu-id="a732b-111">Inside this new directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="a732b-112">目录结构目前如下所示：</span><span class="sxs-lookup"><span data-stu-id="a732b-112">The directory structure thus far is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
```

<span data-ttu-id="a732b-113">将 *PrimeService* 作为当前目录，然后运行 [`dotnet new classlib`](../tools/dotnet-new.md) 以创建源项目。</span><span class="sxs-lookup"><span data-stu-id="a732b-113">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="a732b-114">将 *Class1.cs* 重命名为 *PrimeService.cs*。</span><span class="sxs-lookup"><span data-stu-id="a732b-114">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="a732b-115">为了使用由测试驱动的开发 (TDD)，需对 `PrimeService` 类创建故障实现：</span><span class="sxs-lookup"><span data-stu-id="a732b-115">To use test-driven development (TDD), you'll create a failing implementation of the `PrimeService` class:</span></span>

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

### <a name="creating-the-test-project"></a><span data-ttu-id="a732b-116">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="a732b-116">Creating the test project</span></span>

<span data-ttu-id="a732b-117">将目录更改回 unit-testing-using-mstest 目录，并创建 PrimeService.Tests 目录。</span><span class="sxs-lookup"><span data-stu-id="a732b-117">Change the directory back to the *unit-testing-using-mstest* directory and create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="a732b-118">目录结构如下所示：</span><span class="sxs-lookup"><span data-stu-id="a732b-118">The directory structure is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="a732b-119">将 *PrimeService.Tests* 目录作为当前目录，并使用 [`dotnet new mstest`](../tools/dotnet-new.md) 创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="a732b-119">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="a732b-120">这会创建一个将 MStest 用作测试库的测试项目。</span><span class="sxs-lookup"><span data-stu-id="a732b-120">This creates a test project that uses MStest as the test library.</span></span> <span data-ttu-id="a732b-121">生成的模板在 *PrimeServiceTests.csproj* 文件中配置测试运行程序：</span><span class="sxs-lookup"><span data-stu-id="a732b-121">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.11" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.11" />
</ItemGroup>
```

<span data-ttu-id="a732b-122">测试项目需要其他包创建和运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="a732b-122">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="a732b-123">上一步中的 `dotnet new` 添加了 MSTest SDK、MSTest 测试框架和 MSTest 运行程序。</span><span class="sxs-lookup"><span data-stu-id="a732b-123">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="a732b-124">现在，将 `PrimeService` 类库作为另一个依赖项添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="a732b-124">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="a732b-125">使用 [`dotnet add reference`](../tools/dotnet-add-reference.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="a732b-125">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="a732b-126">另一个选项是编辑 *PrimeService.Tests.csproj* 文件。</span><span class="sxs-lookup"><span data-stu-id="a732b-126">Another option is to edit the *PrimeService.Tests.csproj* file.</span></span> <span data-ttu-id="a732b-127">直接在第一个 `<ItemGroup>` 节点下，添加另一个具有库项目引用的 `<ItemGroup>`：</span><span class="sxs-lookup"><span data-stu-id="a732b-127">Directly under the first `<ItemGroup>` node, add another `<ItemGroup>` node with a reference to the library project:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

<span data-ttu-id="a732b-128">可以在 GitHub 上的[示例存储库](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj)中看到整个文件。</span><span class="sxs-lookup"><span data-stu-id="a732b-128">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="a732b-129">最终的解决方案布局如下所示：</span><span class="sxs-lookup"><span data-stu-id="a732b-129">The final solution layout is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService
        PrimeServiceTests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="a732b-130">创建第一个测试</span><span class="sxs-lookup"><span data-stu-id="a732b-130">Creating the first test</span></span>

<span data-ttu-id="a732b-131">在构建库或测试前，执行 *PrimeService.Tests* 目录中的 [`dotnet restore`](../tools/dotnet-restore.md)。</span><span class="sxs-lookup"><span data-stu-id="a732b-131">Before building the library or the tests, execute [`dotnet restore`](../tools/dotnet-restore.md) in the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="a732b-132">此命令将为每个项目还原所有必要的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="a732b-132">This command restores all the necessary NuGet packages for each project.</span></span>

<span data-ttu-id="a732b-133">TDD 方法要求编写一个失败的测试，使其通过测试，然后重复该过程。</span><span class="sxs-lookup"><span data-stu-id="a732b-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="a732b-134">从 *PrimeService.Tests* 目录删除 *UnitTest1.cs*，并创建一个名为 *PrimeService_IsPrimeShould.cs* 且包含以下内容的新 C# 文件：</span><span class="sxs-lookup"><span data-stu-id="a732b-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

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

            Assert.IsFalse(result, $"1 should not be prime");
        }
    }
}
```

<span data-ttu-id="a732b-135">`[TestClass]` 属性表示包含单元测试的类。</span><span class="sxs-lookup"><span data-stu-id="a732b-135">The `[TestClass]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="a732b-136">`[TestMethod]` 属性将方法表示为单个测试。</span><span class="sxs-lookup"><span data-stu-id="a732b-136">The `[TestMethod]` attribute denotes a method as a single test.</span></span> 

<span data-ttu-id="a732b-137">保存此文件并执行 [`dotnet test`](../tools/dotnet-test.md) 以构建测试和类库，然后运行测试。</span><span class="sxs-lookup"><span data-stu-id="a732b-137">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="a732b-138">MSTest 测试运行程序包含要运行测试的程序入口点。</span><span class="sxs-lookup"><span data-stu-id="a732b-138">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="a732b-139">`dotnet test` 启动测试运行程序，并向该测试运行程序提供命令行参数以指示包含测试的程序集。</span><span class="sxs-lookup"><span data-stu-id="a732b-139">`dotnet test` starts the test runner and provides a command-line argument to the test runner indicating the assembly that contains your tests.</span></span>

<span data-ttu-id="a732b-140">测试失败。</span><span class="sxs-lookup"><span data-stu-id="a732b-140">Your test fails.</span></span> <span data-ttu-id="a732b-141">尚未创建实现。</span><span class="sxs-lookup"><span data-stu-id="a732b-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="a732b-142">在 `PrimeService` 类中编写最简单的代码，使此测试通过：</span><span class="sxs-lookup"><span data-stu-id="a732b-142">Write the simplest code in the `PrimeService` class to make this test pass:</span></span>

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

<span data-ttu-id="a732b-143">在 *PrimeService.Tests* 目录中，再次运行 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="a732b-143">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="a732b-144">`dotnet test` 命令构建 `PrimeService` 项目，然后构建 `PrimeService.Tests` 项目。</span><span class="sxs-lookup"><span data-stu-id="a732b-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="a732b-145">构建这两个项目后，该命令将运行此单项测试。</span><span class="sxs-lookup"><span data-stu-id="a732b-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="a732b-146">测试通过。</span><span class="sxs-lookup"><span data-stu-id="a732b-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="a732b-147">添加更多功能</span><span class="sxs-lookup"><span data-stu-id="a732b-147">Adding more features</span></span>

<span data-ttu-id="a732b-148">你已经通过了一个测试，现在可以编写更多测试。</span><span class="sxs-lookup"><span data-stu-id="a732b-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="a732b-149">质数有其他几种简单情况：0，-1。</span><span class="sxs-lookup"><span data-stu-id="a732b-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="a732b-150">可以将其添加为具有 `[TestMethod]` 属性的新测试，但这很快就会变得枯燥乏味。</span><span class="sxs-lookup"><span data-stu-id="a732b-150">You could add those as new tests with the `[TestMethod]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="a732b-151">还有其他 MSTest 属性，使用这些属性可编写类似测试的套件。</span><span class="sxs-lookup"><span data-stu-id="a732b-151">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="a732b-152">`[DataTestMethod]` 属性表示执行相同代码，但具有不同输入参数的测试套件。</span><span class="sxs-lookup"><span data-stu-id="a732b-152">A `[DataTestMethod]`attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="a732b-153">可以使用 `[DataRow]` 属性来指定这些输入的值。</span><span class="sxs-lookup"><span data-stu-id="a732b-153">You can use the `[DataRow]` attribute to specify values for those inputs.</span></span> 
 
<span data-ttu-id="a732b-154">利用这两个属性来创建测试小于 2 的几个值的单个数据测试方法（而不是创建新测试），其中，2 是最小质数：</span><span class="sxs-lookup"><span data-stu-id="a732b-154">Instead of creating new tests, leverage these two attributes to create a single data test method that tests several values less than two, which is the lowest prime number:</span></span>

<span data-ttu-id="a732b-155">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span><span class="sxs-lookup"><span data-stu-id="a732b-155">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span></span>

<span data-ttu-id="a732b-156">运行 `dotnet test`，两项测试均失败。</span><span class="sxs-lookup"><span data-stu-id="a732b-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="a732b-157">若要使所有测试通过，可以更改方法开头的 `if` 子句：</span><span class="sxs-lookup"><span data-stu-id="a732b-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="a732b-158">通过在主库中添加更多测试、理论和代码继续循环访问。</span><span class="sxs-lookup"><span data-stu-id="a732b-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="a732b-159">将以[已完成的测试版本](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs)和[库的完整实现](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs)结束。</span><span class="sxs-lookup"><span data-stu-id="a732b-159">You'll end up with the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="a732b-160">你已生成一个小型库和该库的一组单元测试。</span><span class="sxs-lookup"><span data-stu-id="a732b-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="a732b-161">已结构化解决方案，以无缝添加新包和测试，并可将大部分时间和精力投入到解决应用程序的目标中。</span><span class="sxs-lookup"><span data-stu-id="a732b-161">You've structured the solution so that adding new packages and tests is seamless, and you can concentrate most of your time and effort on solving the goals of the applicaiton.</span></span>

