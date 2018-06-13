---
title: 使用 dotnet test 和 NUnit 在 .NET Core 中进行 F# 库的单元测试
description: 使用 dotnet test 和 NUnit 分步构建一个示例解决方案，在此交互式体验中学习 .NET Core 中的 F# 单元测试概念。
author: rprouse
ms.date: 12/01/2017
dev_langs:
- fsharp
ms.openlocfilehash: c5653463ce43ab8660753aa03ef79ba10f339fac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215742"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-nunit"></a><span data-ttu-id="9d207-103">使用 dotnet test 和 NUnit 在 .NET Core 中进行 F# 库的单元测试</span><span class="sxs-lookup"><span data-stu-id="9d207-103">Unit testing F# libraries in .NET Core using dotnet test and NUnit</span></span>

<span data-ttu-id="9d207-104">本教程介绍分步构建示例解决方案的交互式体验，以了解单元测试概念。</span><span class="sxs-lookup"><span data-stu-id="9d207-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="9d207-105">如果希望使用预构建解决方案学习本教程，请在开始前[查看或下载示例代码](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-nunit/)。</span><span class="sxs-lookup"><span data-stu-id="9d207-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-nunit/) before you begin.</span></span> <span data-ttu-id="9d207-106">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="9d207-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="9d207-107">创建源项目</span><span class="sxs-lookup"><span data-stu-id="9d207-107">Creating the source project</span></span>

<span data-ttu-id="9d207-108">打开 shell 窗口。</span><span class="sxs-lookup"><span data-stu-id="9d207-108">Open a shell window.</span></span> <span data-ttu-id="9d207-109">创建一个名为 unit-testing-with-fsharp 的目录，以保留该解决方案。</span><span class="sxs-lookup"><span data-stu-id="9d207-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="9d207-110">在此新目录中，运行 [`dotnet new sln`](../tools/dotnet-new.md) 创建新的解决方案。</span><span class="sxs-lookup"><span data-stu-id="9d207-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="9d207-111">这样便于管理类库和单元测试项目。</span><span class="sxs-lookup"><span data-stu-id="9d207-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="9d207-112">在解决方案库中，创建 MathService 目录。</span><span class="sxs-lookup"><span data-stu-id="9d207-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="9d207-113">目录和文件结构目前如下所示：</span><span class="sxs-lookup"><span data-stu-id="9d207-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="9d207-114">将 MathService 作为当前目录，然后运行 [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) 以创建源项目。</span><span class="sxs-lookup"><span data-stu-id="9d207-114">Make *MathService* the current directory and run [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) to create the source project.</span></span>  <span data-ttu-id="9d207-115">为了使用由测试驱动的开发 (TDD)，需对数学服务创建故障实现：</span><span class="sxs-lookup"><span data-stu-id="9d207-115">To use test-driven development (TDD), you'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="9d207-116">将目录更改回 unit-testing-with-fsharp 目录。</span><span class="sxs-lookup"><span data-stu-id="9d207-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="9d207-117">运行 [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) 向解决方案添加类库项目。</span><span class="sxs-lookup"><span data-stu-id="9d207-117">Run [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="install-the-nunit-project-template"></a><span data-ttu-id="9d207-118">安装 NUnit 项目模板</span><span class="sxs-lookup"><span data-stu-id="9d207-118">Install the NUnit project template</span></span>

<span data-ttu-id="9d207-119">创建测试项目之前，需安装 NUnit 测试项目模板。</span><span class="sxs-lookup"><span data-stu-id="9d207-119">The NUnit test project templates need to be installed before creating a test project.</span></span> <span data-ttu-id="9d207-120">仅需在新建 NUnit 项目的开发人员计算机上安装一次。</span><span class="sxs-lookup"><span data-stu-id="9d207-120">This only needs to be done once on each developer machine where you'll create new NUnit projects.</span></span> <span data-ttu-id="9d207-121">运行 [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) 以安装 NUnit 模板.</span><span class="sxs-lookup"><span data-stu-id="9d207-121">Run [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) to install the NUnit templates.</span></span>

 ```
 dotnet new -i NUnit3.DotNetNew.Template
 ```

## <a name="creating-the-test-project"></a><span data-ttu-id="9d207-122">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="9d207-122">Creating the test project</span></span>

<span data-ttu-id="9d207-123">接下来，创建 MathService.Tests 目录。</span><span class="sxs-lookup"><span data-stu-id="9d207-123">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="9d207-124">下图显示了它的目录结构：</span><span class="sxs-lookup"><span data-stu-id="9d207-124">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="9d207-125">将 MathService.Tests 目录作为当前目录，并使用 [`dotnet new nunit -lang F#`](../tools/dotnet-new.md) 创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="9d207-125">Make the *MathService.Tests* directory the current directory and create a new project using [`dotnet new nunit -lang F#`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="9d207-126">这会创建一个将 NUnit 用作测试框架的测试项目。</span><span class="sxs-lookup"><span data-stu-id="9d207-126">This creates a test project that uses NUnit as the test framework.</span></span> <span data-ttu-id="9d207-127">生成的模板在 MathServiceTests.fsproj 中配置测试运行程序：</span><span class="sxs-lookup"><span data-stu-id="9d207-127">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="9d207-128">测试项目需要其他包创建和运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="9d207-128">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="9d207-129">在上一步中，`dotnet new` 已添加 NUnit 和 NUnit 测试适配器。</span><span class="sxs-lookup"><span data-stu-id="9d207-129">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="9d207-130">现在，将 `MathService` 类库作为另一个依赖项添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="9d207-130">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="9d207-131">使用 [`dotnet add reference`](../tools/dotnet-add-reference.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="9d207-131">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="9d207-132">可以在 GitHub 上的[示例存储库](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj)中看到整个文件。</span><span class="sxs-lookup"><span data-stu-id="9d207-132">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="9d207-133">最终的解决方案布局将如下所示：</span><span class="sxs-lookup"><span data-stu-id="9d207-133">You have the following final solution layout:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathServiceTests.fsproj
```

<span data-ttu-id="9d207-134">在 unit-testing-with-fsharp 目录中执行 [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md)。</span><span class="sxs-lookup"><span data-stu-id="9d207-134">Execute [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) in the *unit-testing-with-fsharp* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="9d207-135">创建第一个测试</span><span class="sxs-lookup"><span data-stu-id="9d207-135">Creating the first test</span></span>

<span data-ttu-id="9d207-136">TDD 方法要求编写一个失败的测试，使其通过测试，然后重复该过程。</span><span class="sxs-lookup"><span data-stu-id="9d207-136">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="9d207-137">打开 Tests.fs 并添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="9d207-137">Open *Tests.fs* and add the following code:</span></span>

```fsharp
namespace MathService.Tests

open System
open NUnit.Framework
open MathService

[<TestFixture>]
type TestClass () =

    [<Test>]
    member this.TestMethodPassing() =
        Assert.True(true)

    [<Test>]
     member this.FailEveryTime() = Assert.True(false)
```

<span data-ttu-id="9d207-138">`[<TestFixture>]` 属性表示包含测试的类。</span><span class="sxs-lookup"><span data-stu-id="9d207-138">The `[<TestFixture>]` attribute denotes a class that contains tests.</span></span> <span data-ttu-id="9d207-139">`[<Test>]` 属性表示由测试运行程序运行的测试方法。</span><span class="sxs-lookup"><span data-stu-id="9d207-139">The `[<Test>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="9d207-140">在 unit-testing-with-fsharp 目录中，执行 [`dotnet test`](../tools/dotnet-test.md) 以构建测试和类库，然后运行测试。</span><span class="sxs-lookup"><span data-stu-id="9d207-140">From the *unit-testing-with-fsharp* directory, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="9d207-141">NUnit 测试运行程序包含要运行测试的程序入口点。</span><span class="sxs-lookup"><span data-stu-id="9d207-141">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="9d207-142">`dotnet test` 使用已创建的单元测试项目启动测试运行程序。</span><span class="sxs-lookup"><span data-stu-id="9d207-142">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="9d207-143">这两个测试演示了最基本的已通过测试和未通过测试。</span><span class="sxs-lookup"><span data-stu-id="9d207-143">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="9d207-144">`My test` 通过，而 `Fail every time` 未通过。</span><span class="sxs-lookup"><span data-stu-id="9d207-144">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="9d207-145">现在创建针对 `squaresOfOdds` 方法的测试。</span><span class="sxs-lookup"><span data-stu-id="9d207-145">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="9d207-146">`squaresOfOdds` 方法返回输入序列中所有奇整数值的平方序列。</span><span class="sxs-lookup"><span data-stu-id="9d207-146">The `squaresOfOdds` method returns a sequence of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="9d207-147">可以以迭代的方式创建可验证此功能的测试，而非尝试同时写入所有的函数。</span><span class="sxs-lookup"><span data-stu-id="9d207-147">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="9d207-148">若要让每个测试都通过，意味着要针对此方法创建必要的功能。</span><span class="sxs-lookup"><span data-stu-id="9d207-148">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="9d207-149">可以编写的最简单的测试是调用包含所有偶数的 `squaresOfOdds`，它的结果应该是一个空整数序列。</span><span class="sxs-lookup"><span data-stu-id="9d207-149">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="9d207-150">此测试如下所示：</span><span class="sxs-lookup"><span data-stu-id="9d207-150">Here's that test:</span></span>

```fsharp
[<Test>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int>
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="9d207-151">请注意已将 `expected` 序列转换为列表。</span><span class="sxs-lookup"><span data-stu-id="9d207-151">Notice that the `expected` sequence has been converted to a list.</span></span> <span data-ttu-id="9d207-152">NUnit 框架依赖于许多标准 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="9d207-152">The NUnit framework relies on many standard .NET types.</span></span> <span data-ttu-id="9d207-153">此依赖关系表示公共接口和预期结果支持 <xref:System.Collections.ICollection>，而非 <xref:System.Collections.IEnumerable>。</span><span class="sxs-lookup"><span data-stu-id="9d207-153">That dependency means that your public interface and expected results support <xref:System.Collections.ICollection> rather than <xref:System.Collections.IEnumerable>.</span></span>

<span data-ttu-id="9d207-154">运行此测试时，会看到测试失败。</span><span class="sxs-lookup"><span data-stu-id="9d207-154">When you run the test, you see that your test fails.</span></span> <span data-ttu-id="9d207-155">尚未创建实现。</span><span class="sxs-lookup"><span data-stu-id="9d207-155">You haven't created the implementation yet.</span></span> <span data-ttu-id="9d207-156">在起作用的 `Mathservice` 类中编写最简单的代码，以生成此测试：</span><span class="sxs-lookup"><span data-stu-id="9d207-156">Make this test by writing the simplest code in the `Mathservice` class that works:</span></span>

```csharp
let squaresOfOdds xs =
    Seq.empty<int>
```

<span data-ttu-id="9d207-157">在 unit-testing-with-fsharp 目录中，再次运行 `dotnet test`。</span><span class="sxs-lookup"><span data-stu-id="9d207-157">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="9d207-158">`dotnet test` 命令构建 `MathService` 项目，然后构建 `MathService.Tests` 项目。</span><span class="sxs-lookup"><span data-stu-id="9d207-158">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="9d207-159">构建这两个项目后，该命令将运行此单项测试。</span><span class="sxs-lookup"><span data-stu-id="9d207-159">After building both projects, it runs this single test.</span></span> <span data-ttu-id="9d207-160">测试通过。</span><span class="sxs-lookup"><span data-stu-id="9d207-160">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="9d207-161">完成要求</span><span class="sxs-lookup"><span data-stu-id="9d207-161">Completing the requirements</span></span>

<span data-ttu-id="9d207-162">你已经通过了一个测试，现在可以编写更多测试。</span><span class="sxs-lookup"><span data-stu-id="9d207-162">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="9d207-163">下一个简单示例使用的序列包含的唯一奇数为 `1`。</span><span class="sxs-lookup"><span data-stu-id="9d207-163">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="9d207-164">数值 1 较为简单，因为 1 的平方是 1。</span><span class="sxs-lookup"><span data-stu-id="9d207-164">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="9d207-165">下一个测试如下所示：</span><span class="sxs-lookup"><span data-stu-id="9d207-165">Here's that next test:</span></span>

```fsharp
[<Test>]
member public this.TestOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="9d207-166">如果执行 `dotnet test`，新测试将失败。</span><span class="sxs-lookup"><span data-stu-id="9d207-166">Executing `dotnet test` fails the new test.</span></span> <span data-ttu-id="9d207-167">必须更新 `squaresOfOdds` 方法才能处理此新测试。</span><span class="sxs-lookup"><span data-stu-id="9d207-167">You must update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="9d207-168">必须筛选出序列中的所有偶数值，以使此测试通过。</span><span class="sxs-lookup"><span data-stu-id="9d207-168">You must filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="9d207-169">可以编写一个小筛选器函数并使用 `Seq.filter` 来实现此目的：</span><span class="sxs-lookup"><span data-stu-id="9d207-169">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
```

<span data-ttu-id="9d207-170">注意对 `Seq.toList` 的调用。</span><span class="sxs-lookup"><span data-stu-id="9d207-170">Notice the call to `Seq.toList`.</span></span> <span data-ttu-id="9d207-171">它会创建一个列表，此列表将实现 <xref:System.Collections.ICollection> 接口。</span><span class="sxs-lookup"><span data-stu-id="9d207-171">That creates a list, which implements the <xref:System.Collections.ICollection> interface.</span></span>

<span data-ttu-id="9d207-172">还要执行一个步骤：计算每个奇数的平方值。</span><span class="sxs-lookup"><span data-stu-id="9d207-172">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="9d207-173">从编写新测试开始：</span><span class="sxs-lookup"><span data-stu-id="9d207-173">Start by writing a new test:</span></span>

```fsharp
[<Test>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="9d207-174">可以通过映射操作传递经过筛选的序列来计算每个奇数的平方，以此方式来修复测试的缺陷：</span><span class="sxs-lookup"><span data-stu-id="9d207-174">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
```

<span data-ttu-id="9d207-175">你已生成一个小型库和该库的一组单元测试。</span><span class="sxs-lookup"><span data-stu-id="9d207-175">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="9d207-176">你已将解决方案结构化，使添加新包和新测试成为了正常工作流的一部分。</span><span class="sxs-lookup"><span data-stu-id="9d207-176">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="9d207-177">你已将多数的时间和精力集中在解决应用程序的目标上。</span><span class="sxs-lookup"><span data-stu-id="9d207-177">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
