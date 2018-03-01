---
title: "使用 dotnet test 和 NUnit 在 .NET Core 中进行 Visual Basic 单元测试"
description: "使用 NUnit 分步构建一个 Visual Basic 示例解决方案，在此交互式体验中学习 .NET Core 中的单元测试概念。"
author: rprouse
ms.date: 12/01/2017
ms.topic: article
dev_langs:
- vb
ms.prod: .net-core
ms.openlocfilehash: 2166da36fe9d0297f03e7c38249135d281b9a5d6
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2017
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-nunit"></a><span data-ttu-id="6b0a8-103">使用 dotnet test 和 NUnit 进行 Visual Basic .NET Core 库的单元测试</span><span class="sxs-lookup"><span data-stu-id="6b0a8-103">Unit testing Visual Basic .NET Core libraries using dotnet test and NUnit</span></span>

<span data-ttu-id="6b0a8-104">本教程介绍分步构建示例解决方案的交互式体验，以了解单元测试概念。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="6b0a8-105">如果希望使用预构建解决方案学习本教程，请在开始前[查看或下载示例代码](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-vb-nunit/)。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-vb-nunit/) before you begin.</span></span> <span data-ttu-id="6b0a8-106">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="6b0a8-107">创建源项目</span><span class="sxs-lookup"><span data-stu-id="6b0a8-107">Creating the source project</span></span>

<span data-ttu-id="6b0a8-108">打开 shell 窗口。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-108">Open a shell window.</span></span> <span data-ttu-id="6b0a8-109">创建一个名为 unit-testing-vb-nunit 的目录，以保留该解决方案。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-109">Create a directory called *unit-testing-vb-nunit* to hold the solution.</span></span> <span data-ttu-id="6b0a8-110">在此新目录中，运行 [`dotnet new sln`](../tools/dotnet-new.md) 创建新的解决方案。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="6b0a8-111">此做法便于管理类库和单元测试项目。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-111">This practice makes it easier to manage both the class library and the unit test project.</span></span> <span data-ttu-id="6b0a8-112">在解决方案目录中，创建 PrimeService 目录。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="6b0a8-113">目前目录和文件结构如下所示：</span><span class="sxs-lookup"><span data-stu-id="6b0a8-113">You have the following directory and file structure thus far:</span></span>

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
```

<span data-ttu-id="6b0a8-114">将 *PrimeService* 作为当前目录，然后运行 [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) 以创建源项目。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="6b0a8-115">将 Class1.VB 重命名为 PrimeService.VB。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="6b0a8-116">为了使用由测试驱动的开发 (TDD)，需对 `PrimeService` 类创建故障实现：</span><span class="sxs-lookup"><span data-stu-id="6b0a8-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

```vb
Imports System

Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="6b0a8-117">将目录更改回 unit-testing-vb-using-stest 目录。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-117">Change the directory back to the *unit-testing-vb-using-stest* directory.</span></span> <span data-ttu-id="6b0a8-118">运行 [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) 向解决方案添加类库项目。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="install-the-nunit-project-template"></a><span data-ttu-id="6b0a8-119">安装 NUnit 项目模板</span><span class="sxs-lookup"><span data-stu-id="6b0a8-119">Install the NUnit project template</span></span>

<span data-ttu-id="6b0a8-120">创建测试项目之前，需安装 NUnit 测试项目模板。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-120">The NUnit test project templates need to be installed before creating a test project.</span></span> <span data-ttu-id="6b0a8-121">仅需在新建 NUnit 项目的开发人员计算机上安装一次。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-121">This only needs to be done once on each developer machine where you'll create new NUnit projects.</span></span> <span data-ttu-id="6b0a8-122">运行 [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) 以安装 NUnit 模板.</span><span class="sxs-lookup"><span data-stu-id="6b0a8-122">Run [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) to install the NUnit templates.</span></span>

 ```
 dotnet new -i NUnit3.DotNetNew.Template
 ```

## <a name="creating-the-test-project"></a><span data-ttu-id="6b0a8-123">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="6b0a8-123">Creating the test project</span></span>

<span data-ttu-id="6b0a8-124">接下来，创建 PrimeService.Tests 目录。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-124">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="6b0a8-125">下图显示了它的目录结构：</span><span class="sxs-lookup"><span data-stu-id="6b0a8-125">The following outline shows the directory structure:</span></span>

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="6b0a8-126">将 *PrimeService.Tests* 目录作为当前目录，并使用 [`dotnet new nunit -lang VB`](../tools/dotnet-new.md) 创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-126">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new nunit -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="6b0a8-127">此命令会创建一个将 NUnit 用作测试库的测试项目。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-127">This command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="6b0a8-128">生成的模板在 PrimeServiceTests.vbproj 中配置了测试运行程序：</span><span class="sxs-lookup"><span data-stu-id="6b0a8-128">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="6b0a8-129">测试项目需要其他包创建和运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-129">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="6b0a8-130">在上一步中，`dotnet new` 已添加 NUnit 和 NUnit 测试适配器。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-130">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="6b0a8-131">现在，将 `PrimeService` 类库作为另一个依赖项添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-131">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="6b0a8-132">使用 [`dotnet add reference`](../tools/dotnet-add-reference.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="6b0a8-132">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="6b0a8-133">可以在 GitHub 上的[示例存储库](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj)中看到整个文件。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-133">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="6b0a8-134">最终的解决方案布局将如下所示：</span><span class="sxs-lookup"><span data-stu-id="6b0a8-134">You have the following final solution layout:</span></span>

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="6b0a8-135">在 unit-testing-vb-nunit 目录中执行 [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md)。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-135">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-nunit* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="6b0a8-136">创建第一个测试</span><span class="sxs-lookup"><span data-stu-id="6b0a8-136">Creating the first test</span></span>

<span data-ttu-id="6b0a8-137">TDD 方法要求编写一个失败的测试，使其通过测试，然后重复该过程。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-137">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="6b0a8-138">从 PrimeService.Tests 目录删除 UnitTest1.vb，并创建一个名为 PrimeService_IsPrimeShould.VB 的新 Visual Basic 文件。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-138">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="6b0a8-139">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="6b0a8-139">Add the following code:</span></span>

```vb
Imports NUnit.Framework

Namespace PrimeService.Tests
    <TestFixture>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Test>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="6b0a8-140">`<TestFixture>` 属性指示包含测试的类。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-140">The `<TestFixture>` attribute indicates a class that contains tests.</span></span> <span data-ttu-id="6b0a8-141">`<Test>` 属性表示由测试运行程序运行的方法。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-141">The `<Test>` attribute denotes a method that is run by the test runner.</span></span> <span data-ttu-id="6b0a8-142">在 unit-testing-vb-nunit 中，执行 [`dotnet test`](../tools/dotnet-test.md) 以构建测试和类库，然后运行测试。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-142">From the *unit-testing-vb-nunit*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="6b0a8-143">NUnit 测试运行程序包含要运行测试的程序入口点。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-143">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="6b0a8-144">`dotnet test` 使用已创建的单元测试项目启动测试运行程序。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-144">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="6b0a8-145">测试失败。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-145">Your test fails.</span></span> <span data-ttu-id="6b0a8-146">尚未创建实现。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-146">You haven't created the implementation yet.</span></span> <span data-ttu-id="6b0a8-147">在起作用的 `PrimeService` 类中编写最简单的代码，以生成此测试：</span><span class="sxs-lookup"><span data-stu-id="6b0a8-147">Make this test by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

<span data-ttu-id="6b0a8-148">在 unit-testing-vb-nunit 目录中，再次运行 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-148">In the *unit-testing-vb-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="6b0a8-149">`dotnet test` 命令构建 `PrimeService` 项目，然后构建 `PrimeService.Tests` 项目。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-149">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="6b0a8-150">构建这两个项目后，该命令将运行此单项测试。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-150">After building both projects, it runs this single test.</span></span> <span data-ttu-id="6b0a8-151">测试通过。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-151">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="6b0a8-152">添加更多功能</span><span class="sxs-lookup"><span data-stu-id="6b0a8-152">Adding more features</span></span>

<span data-ttu-id="6b0a8-153">你已经通过了一个测试，现在可以编写更多测试。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-153">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="6b0a8-154">质数有其他几种简单情况：0，-1。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-154">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="6b0a8-155">可以将这些情况添加为具有 `<Test>` 属性的新测试，但这很快就会变得枯燥乏味。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-155">You could add those cases as new tests with the `<Test>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="6b0a8-156">还有其他 xUnit 属性，可使你编写类似测试套件。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-156">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="6b0a8-157">`<TestCase>` 属性表示执行相同代码，但具有不同输入参数一系列测试。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-157">A `<TestCase>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="6b0a8-158">可以使用 `<TestCase>` 属性来指定这些输入的值。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-158">You can use the `<TestCase>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="6b0a8-159">无需创建新测试，而是应用这两个属性来创建一系列测试，用于测试小于 2（最小质数）的几个值：</span><span class="sxs-lookup"><span data-stu-id="6b0a8-159">Instead of creating new tests, apply these two attributes to create a series of tests that test several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="6b0a8-160">运行 `dotnet test`，两项测试均失败。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-160">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="6b0a8-161">若要使所有测试通过，可以更改方法开头的 `if` 子句：</span><span class="sxs-lookup"><span data-stu-id="6b0a8-161">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="6b0a8-162">通过在主库中添加更多测试、理论和代码继续循环访问。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-162">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="6b0a8-163">你将拥有[已完成的测试版本](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb)和[库的完整实现](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb)。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-163">You have the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="6b0a8-164">你已生成一个小型库和该库的一组单元测试。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-164">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="6b0a8-165">你已将解决方案结构化，使添加新包和新测试成为了正常工作流的一部分。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-165">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="6b0a8-166">你已将多数的时间和精力集中在解决应用程序的目标上。</span><span class="sxs-lookup"><span data-stu-id="6b0a8-166">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
