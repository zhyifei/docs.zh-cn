---
title: 使用 NUnit 和 .NET Core 进行 C# 单元测试
description: 使用 dotnet test 和 NUnit 分步构建一个示例解决方案，在此交互式体验中学习 C# 和 .NET Core 中的单元测试概念。
author: rprouse
ms.date: 08/31/2018
ms.openlocfilehash: 253e07c16740a39566cf37ee5742a32342c78c49
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44188405"
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a><span data-ttu-id="2f1cb-103">使用 NUnit 和 .NET Core 进行 C# 单元测试</span><span class="sxs-lookup"><span data-stu-id="2f1cb-103">Unit testing C# with NUnit and .NET Core</span></span>

<span data-ttu-id="2f1cb-104">本教程介绍分步构建示例解决方案的交互式体验，以了解单元测试概念。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="2f1cb-105">如果希望使用预构建解决方案学习本教程，请在开始前[查看或下载示例代码](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/)。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) before you begin.</span></span> <span data-ttu-id="2f1cb-106">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2f1cb-107">系统必备</span><span class="sxs-lookup"><span data-stu-id="2f1cb-107">Prerequisites</span></span>

- <span data-ttu-id="2f1cb-108">[.NET Core SDK 2.1（版本2.1.400）](https://www.microsoft.com/net/download)或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-108">[.NET Core SDK 2.1 (v. 2.1.400)](https://www.microsoft.com/net/download) or later versions.</span></span>
- <span data-ttu-id="2f1cb-109">按需选择的文本编辑器或代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-109">A text editor or code editor of your choice.</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="2f1cb-110">创建源项目</span><span class="sxs-lookup"><span data-stu-id="2f1cb-110">Creating the source project</span></span>

<span data-ttu-id="2f1cb-111">打开 shell 窗口。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-111">Open a shell window.</span></span> <span data-ttu-id="2f1cb-112">创建一个名为 unit-testing-using-nunit 的目录，以保留该解决方案。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-112">Create a directory called *unit-testing-using-nunit* to hold the solution.</span></span> <span data-ttu-id="2f1cb-113">在此新目录中，运行以下命令，为类库和测试项目创建新的解决方案文件：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-113">Inside this new directory, run the following command to create a new solution file for the class library and the test project:</span></span>

```console
dotnet new sln
```
 
<span data-ttu-id="2f1cb-114">接下来，创建 PrimeService 目录。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-114">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="2f1cb-115">下图显示了当前的目录和文件结构：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-115">The following outline shows the directory and file structure so far:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

<span data-ttu-id="2f1cb-116">将 PrimeService 作为当前目录，并运行以下命令以创建源项目：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-116">Make *PrimeService* the current directory and run the following command to create the source project:</span></span>

```console
dotnet new classlib
```

<span data-ttu-id="2f1cb-117">将 *Class1.cs* 重命名为 *PrimeService.cs*。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-117">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="2f1cb-118">为了使用由测试驱动的开发 (TDD)，需对 `PrimeService` 类创建故障实现：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-118">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="2f1cb-119">将目录更改回 unit-testing-using-nunit 目录。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-119">Change the directory back to the *unit-testing-using-nunit* directory.</span></span> <span data-ttu-id="2f1cb-120">运行以下命令，向解决方案添加类库项目：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-120">Run the following command to add the class library project to the solution:</span></span>

```console
dotnet sln add PrimeService/PrimeService.csproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="2f1cb-121">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="2f1cb-121">Creating the test project</span></span>

<span data-ttu-id="2f1cb-122">接下来，创建 PrimeService.Tests 目录。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-122">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="2f1cb-123">下图显示了它的目录结构：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-123">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="2f1cb-124">将 PrimeService.Tests 目录作为当前目录，并使用以下命令创建一个新项目：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-124">Make the *PrimeService.Tests* directory the current directory and create a new project using the following command:</span></span>

```console
dotnet new nunit
```

<span data-ttu-id="2f1cb-125">[dotnet new](../tools/dotnet-new.md) 命令可创建一个将 NUnit 用作测试库的测试项目。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-125">The [dotnet new](../tools/dotnet-new.md) command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="2f1cb-126">生成的模板在 PrimeService.Tests.csproj 文件中配置测试运行程序：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-126">The generated template configures the test runner in the *PrimeService.Tests.csproj* file:</span></span>

[!code-xml[Packages](~/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj#Packages)]

<span data-ttu-id="2f1cb-127">测试项目需要其他包创建和运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-127">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="2f1cb-128">在上一步中，`dotnet new` 已添加 Microsoft 测试 SDK、NUnit 测试框架和 NUnit 测试适配器。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-128">`dotnet new` in the previous step added the Microsoft test SDK, the NUnit test framework, and the NUnit test adapter.</span></span> <span data-ttu-id="2f1cb-129">现在，将 `PrimeService` 类库作为另一个依赖项添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-129">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="2f1cb-130">使用 [`dotnet add reference`](../tools/dotnet-add-reference.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-130">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```console
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="2f1cb-131">可以在 GitHub 上的[示例存储库](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj)中看到整个文件。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-131">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="2f1cb-132">下图显示了最终的解决方案布局：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-132">The following outline shows the final solution layout:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.csproj
```

<span data-ttu-id="2f1cb-133">在 unit-testing-using-dotnet-test 目录中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-133">Execute the following command in the *unit-testing-using-dotnet-test* directory:</span></span>

```console
dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="2f1cb-134">创建第一个测试</span><span class="sxs-lookup"><span data-stu-id="2f1cb-134">Creating the first test</span></span>

<span data-ttu-id="2f1cb-135">TDD 方法要求编写一个失败的测试，使其通过测试，然后重复该过程。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-135">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="2f1cb-136">在 PrimeService.Tests 目录中，将 UnitTest1.cs 文件重命名为 PrimeService_IsPrimeShould.cs，并将其整个内容替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-136">In the *PrimeService.Tests* directory, rename the *UnitTest1.cs* file to *PrimeService_IsPrimeShould.cs* and replace its entire contents with the following code:</span></span>

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

<span data-ttu-id="2f1cb-137">`[TestFixture]` 属性表示包含单元测试的类。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-137">The `[TestFixture]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="2f1cb-138">`[Test]` 属性指示方法是测试方法。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-138">The `[Test]` attribute indicates a method is a test method.</span></span>

<span data-ttu-id="2f1cb-139">保存此文件并执行 [`dotnet test`](../tools/dotnet-test.md) 以构建测试和类库，然后运行测试。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-139">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="2f1cb-140">NUnit 测试运行程序包含要运行测试的程序入口点。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-140">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="2f1cb-141">`dotnet test` 使用已创建的单元测试项目启动测试运行程序。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-141">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="2f1cb-142">测试失败。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-142">Your test fails.</span></span> <span data-ttu-id="2f1cb-143">尚未创建实现。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-143">You haven't created the implementation yet.</span></span> <span data-ttu-id="2f1cb-144">在起作用的 `PrimeService` 类中编写最简单的代码，使此测试通过：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-144">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="2f1cb-145">在 unit-testing-using-nunit 目录中再次运行 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-145">In the *unit-testing-using-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="2f1cb-146">`dotnet test` 命令构建 `PrimeService` 项目，然后构建 `PrimeService.Tests` 项目。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-146">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="2f1cb-147">构建这两个项目后，该命令将运行此单项测试。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-147">After building both projects, it runs this single test.</span></span> <span data-ttu-id="2f1cb-148">测试通过。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-148">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="2f1cb-149">添加更多功能</span><span class="sxs-lookup"><span data-stu-id="2f1cb-149">Adding more features</span></span>

<span data-ttu-id="2f1cb-150">你已经通过了一个测试，现在可以编写更多测试。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-150">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="2f1cb-151">质数有其他几种简单情况：0，-1。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-151">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="2f1cb-152">可以添加具有 `[Test]` 属性的新测试，但这很快就会变得枯燥乏味。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-152">You could add new tests with the `[Test]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="2f1cb-153">还有其他 NUnit 属性可用于编写一套类似的测试。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-153">There are other NUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="2f1cb-154">`[TestCase]` 属性用于创建一套可执行相同代码但具有不同输入参数的测试。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-154">A `[TestCase]` attribute is used to create a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="2f1cb-155">可以使用 `[TestCase]` 属性来指定这些输入的值。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-155">You can use the `[TestCase]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="2f1cb-156">无需创建新的测试，而是应用此属性来创建数据驱动的单个测试。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-156">Instead of creating new tests, apply this attribute to create a single data driven test.</span></span> <span data-ttu-id="2f1cb-157">数据驱动的测试方法用于测试多个小于 2（即最小质数）的值：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-157">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="2f1cb-158">运行 `dotnet test`，两项测试均失败。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-158">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="2f1cb-159">若要使所有测试通过，可以在 PrimeService.cs 文件中更改 `Main` 方法开头的 `if` 子句：</span><span class="sxs-lookup"><span data-stu-id="2f1cb-159">To make all of the tests pass, change the `if` clause at the beginning of the `Main` method in the *PrimeService.cs* file:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="2f1cb-160">通过在主库中添加更多测试、理论和代码继续循环访问。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-160">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="2f1cb-161">你将拥有[已完成的测试版本](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs)和[库的完整实现](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs)。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-161">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="2f1cb-162">你已生成一个小型库和该库的一组单元测试。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-162">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="2f1cb-163">你已将解决方案结构化，使添加新包和新测试成为了正常工作流的一部分。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-163">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="2f1cb-164">你已将多数的时间和精力集中在解决应用程序的目标上。</span><span class="sxs-lookup"><span data-stu-id="2f1cb-164">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
