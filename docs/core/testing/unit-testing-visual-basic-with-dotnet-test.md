---
title: 使用 dotnet test 和 xUnit 在 .NET Core 中进行 Visual Basic 单元测试
description: 通过使用 dotnet test 和 xUnit 分步生成 Visual Basic 示例解决方案的交互体验，了解 .NET Core 中的单元测试概念。
author: billwagner
ms.author: wiwagn
ms.date: 09/01/2017
ms.topic: article
dev_langs:
- vb
ms.prod: .net-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 863854bde4a7ae4fab7c182fa9ac273d545b6e0b
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-xunit"></a><span data-ttu-id="59ca2-103">使用 dotnet test 和 xUnit 进行 Visual Basic .NET Core 库单元测试</span><span class="sxs-lookup"><span data-stu-id="59ca2-103">Unit testing Visual Basic .NET Core libraries using dotnet test and xUnit</span></span>

<span data-ttu-id="59ca2-104">本教程介绍分步构建示例解决方案的交互式体验，以了解单元测试概念。</span><span class="sxs-lookup"><span data-stu-id="59ca2-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="59ca2-105">如果希望使用预构建解决方案学习本教程，请在开始前[查看或下载示例代码](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-dotnet-test)。</span><span class="sxs-lookup"><span data-stu-id="59ca2-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-dotnet-test) before you begin.</span></span> <span data-ttu-id="59ca2-106">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="59ca2-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="59ca2-107">创建源项目</span><span class="sxs-lookup"><span data-stu-id="59ca2-107">Creating the source project</span></span>

<span data-ttu-id="59ca2-108">打开 shell 窗口。</span><span class="sxs-lookup"><span data-stu-id="59ca2-108">Open a shell window.</span></span> <span data-ttu-id="59ca2-109">创建一个名为 unit-testing-vb-using-dotnet-test 的目录，以保留该解决方案。</span><span class="sxs-lookup"><span data-stu-id="59ca2-109">Create a directory called *unit-testing-vb-using-dotnet-test* to hold the solution.</span></span>
<span data-ttu-id="59ca2-110">在此新目录中，运行 [`dotnet new sln`](../tools/dotnet-new.md) 创建新的解决方案。</span><span class="sxs-lookup"><span data-stu-id="59ca2-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="59ca2-111">此做法便于管理类库和单元测试项目。</span><span class="sxs-lookup"><span data-stu-id="59ca2-111">This practice makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="59ca2-112">在解决方案目录中，创建 PrimeService 目录。</span><span class="sxs-lookup"><span data-stu-id="59ca2-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="59ca2-113">目前目录和文件结构如下所示：</span><span class="sxs-lookup"><span data-stu-id="59ca2-113">You have the following directory and file structure thus far:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

<span data-ttu-id="59ca2-114">将 *PrimeService* 作为当前目录，然后运行 [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) 以创建源项目。</span><span class="sxs-lookup"><span data-stu-id="59ca2-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="59ca2-115">将 Class1.VB 重命名为 PrimeService.VB。</span><span class="sxs-lookup"><span data-stu-id="59ca2-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="59ca2-116">为了使用由测试驱动的开发 (TDD)，需对 `PrimeService` 类创建故障实现：</span><span class="sxs-lookup"><span data-stu-id="59ca2-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

```vb
Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="59ca2-117">将目录更改回 unit-testing-vb-using-dotnet-test 目录。</span><span class="sxs-lookup"><span data-stu-id="59ca2-117">Change the directory back to the *unit-testing-vb-using-dotnet-test* directory.</span></span> <span data-ttu-id="59ca2-118">运行 [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) 向解决方案添加类库项目。</span><span class="sxs-lookup"><span data-stu-id="59ca2-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="59ca2-119">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="59ca2-119">Creating the test project</span></span>

<span data-ttu-id="59ca2-120">接下来，创建 PrimeService.Tests 目录。</span><span class="sxs-lookup"><span data-stu-id="59ca2-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="59ca2-121">下图显示了它的目录结构：</span><span class="sxs-lookup"><span data-stu-id="59ca2-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-vb-using-dotnet-test
    unit-testing-vb-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="59ca2-122">将 *PrimeService.Tests* 目录作为当前目录，并使用 [`dotnet new xunit -lang VB`](../tools/dotnet-new.md) 创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="59ca2-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="59ca2-123">此命令会创建将 xUnit 用作测试库的测试项目。</span><span class="sxs-lookup"><span data-stu-id="59ca2-123">This command creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="59ca2-124">生成的模板在 PrimeServiceTests.vbproj 中配置了测试运行程序：</span><span class="sxs-lookup"><span data-stu-id="59ca2-124">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="59ca2-125">测试项目需要其他包创建和运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="59ca2-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="59ca2-126">`dotnet new` 在以前的步骤中已添加 xUnit 和 xUnit 运行程序。</span><span class="sxs-lookup"><span data-stu-id="59ca2-126">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="59ca2-127">现在，将 `PrimeService` 类库作为另一个依赖项添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="59ca2-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="59ca2-128">使用 [`dotnet add reference`](../tools/dotnet-add-reference.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="59ca2-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="59ca2-129">可以在 GitHub 上的[示例存储库](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService.Tests.vbproj)中看到整个文件。</span><span class="sxs-lookup"><span data-stu-id="59ca2-129">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="59ca2-130">最终的文件夹布局将如下所示：</span><span class="sxs-lookup"><span data-stu-id="59ca2-130">You have the following final folder layout:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="59ca2-131">在 unit-testing-vb-using-dotnet-test 目录中执行 [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md)。</span><span class="sxs-lookup"><span data-stu-id="59ca2-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-using-dotnet-test* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="59ca2-132">创建第一个测试</span><span class="sxs-lookup"><span data-stu-id="59ca2-132">Creating the first test</span></span>

<span data-ttu-id="59ca2-133">TDD 方法要求编写一个失败的测试，使其通过测试，然后重复该过程。</span><span class="sxs-lookup"><span data-stu-id="59ca2-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="59ca2-134">从 PrimeService.Tests 目录删除 UnitTest1.vb，并创建一个名为 PrimeService_IsPrimeShould.VB 的新 Visual Basic 文件。</span><span class="sxs-lookup"><span data-stu-id="59ca2-134">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="59ca2-135">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="59ca2-135">Add the following code:</span></span>

```vb
Imports Xunit

Namespace PrimeService.Tests
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Fact>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="59ca2-136">`<Fact>` 属性表示由测试运行程序运行的测试方法。</span><span class="sxs-lookup"><span data-stu-id="59ca2-136">The `<Fact>` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="59ca2-137">在 unit-testing-using-dotnet-test 中，执行 [`dotnet test`](../tools/dotnet-test.md) 以构建测试和类库，然后运行测试。</span><span class="sxs-lookup"><span data-stu-id="59ca2-137">From the *unit-testing-using-dotnet-test*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="59ca2-138">xUnit 测试运行程序包含要运行测试的程序入口点。</span><span class="sxs-lookup"><span data-stu-id="59ca2-138">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="59ca2-139">`dotnet test` 使用已创建的单元测试项目启动测试运行程序。</span><span class="sxs-lookup"><span data-stu-id="59ca2-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="59ca2-140">测试失败。</span><span class="sxs-lookup"><span data-stu-id="59ca2-140">Your test fails.</span></span> <span data-ttu-id="59ca2-141">尚未创建实现。</span><span class="sxs-lookup"><span data-stu-id="59ca2-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="59ca2-142">在起作用的 `PrimeService` 类中编写最简单的代码，以生成此测试：</span><span class="sxs-lookup"><span data-stu-id="59ca2-142">Make this test by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

<span data-ttu-id="59ca2-143">在 unit-testing-vb-using-dotnet-test 目录中，再次运行 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="59ca2-143">In the *unit-testing-vb-using-dotnet-test* directory, run `dotnet test` again.</span></span> <span data-ttu-id="59ca2-144">`dotnet test` 命令构建 `PrimeService` 项目，然后构建 `PrimeService.Tests` 项目。</span><span class="sxs-lookup"><span data-stu-id="59ca2-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="59ca2-145">构建这两个项目后，该命令将运行此单项测试。</span><span class="sxs-lookup"><span data-stu-id="59ca2-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="59ca2-146">测试通过。</span><span class="sxs-lookup"><span data-stu-id="59ca2-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="59ca2-147">添加更多功能</span><span class="sxs-lookup"><span data-stu-id="59ca2-147">Adding more features</span></span>

<span data-ttu-id="59ca2-148">你已经通过了一个测试，现在可以编写更多测试。</span><span class="sxs-lookup"><span data-stu-id="59ca2-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="59ca2-149">质数有其他几种简单情况：0，-1。</span><span class="sxs-lookup"><span data-stu-id="59ca2-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="59ca2-150">可以将这些情况添加为具有 `<Fact>` 属性的新测试，但这很快就会变得枯燥乏味。</span><span class="sxs-lookup"><span data-stu-id="59ca2-150">You could add those cases as new tests with the `<Fact>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="59ca2-151">还有其他 xUnit 属性，可使你编写类似测试套件。</span><span class="sxs-lookup"><span data-stu-id="59ca2-151">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="59ca2-152">`<Theory>` 属性表示执行相同代码，但具有不同输入参数一系列测试。</span><span class="sxs-lookup"><span data-stu-id="59ca2-152">A `<Theory>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="59ca2-153">可以使用 `<InlineData>` 属性来指定这些输入的值。</span><span class="sxs-lookup"><span data-stu-id="59ca2-153">You can use the `<InlineData>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="59ca2-154">可以不使用这两个属性创建新测试，而用来创建单个索引。</span><span class="sxs-lookup"><span data-stu-id="59ca2-154">Instead of creating new tests, apply these two attributes to create a single theory.</span></span> <span data-ttu-id="59ca2-155">此索引是测试多个小于 2（即最小的质数）的值的方法：</span><span class="sxs-lookup"><span data-stu-id="59ca2-155">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="59ca2-156">运行 `dotnet test`，两项测试均失败。</span><span class="sxs-lookup"><span data-stu-id="59ca2-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="59ca2-157">若要使所有测试通过，可以更改方法开头的 `if` 子句：</span><span class="sxs-lookup"><span data-stu-id="59ca2-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="59ca2-158">通过在主库中添加更多测试、理论和代码继续循环访问。</span><span class="sxs-lookup"><span data-stu-id="59ca2-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="59ca2-159">你将拥有[已完成的测试版本](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb)和[库的完整实现](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService/PrimeService.vb)。</span><span class="sxs-lookup"><span data-stu-id="59ca2-159">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="59ca2-160">你已生成一个小型库和该库的一组单元测试。</span><span class="sxs-lookup"><span data-stu-id="59ca2-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="59ca2-161">你已将解决方案结构化，使添加新包和新测试成为了正常工作流的一部分。</span><span class="sxs-lookup"><span data-stu-id="59ca2-161">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="59ca2-162">你已将多数的时间和精力集中在解决应用程序的目标上。</span><span class="sxs-lookup"><span data-stu-id="59ca2-162">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
