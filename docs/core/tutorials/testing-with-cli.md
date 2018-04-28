---
title: 使用 .NET Core 命令行组织和测试项目
description: 本教程介绍如何从命令行组织和测试 .NET Core 项目。
author: cartermp
ms.author: mairaw
ms.date: 05/16/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 718f60d6321c1d24670ac177de64725d88bdd148
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="organizing-and-testing-projects-with-the-net-core-command-line"></a><span data-ttu-id="37322-103">使用 .NET Core 命令行组织和测试项目</span><span class="sxs-lookup"><span data-stu-id="37322-103">Organizing and testing projects with the .NET Core command line</span></span>

<span data-ttu-id="37322-104">本教程遵循[使用命令行在 Windows/Linux/macOS 上实现 .NET Core 入门](using-with-xplat-cli.md)，演示如何超越简单的创建控制台应用，开发更高级和组织更良好的应用程序。</span><span class="sxs-lookup"><span data-stu-id="37322-104">This tutorial follows [Getting started with .NET Core on Windows/Linux/macOS using the command line](using-with-xplat-cli.md), taking you beyond the creation of a simple console app to develop advanced and well-organized applications.</span></span> <span data-ttu-id="37322-105">在演示如何使用文件夹来组织代码后，本教程还将说明如何使用 [xUnit](https://xunit.github.io/) 测试框架扩展控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="37322-105">After showing you how to use folders to organize your code, this tutorial shows you how to extend a console application with the [xUnit](https://xunit.github.io/) testing framework.</span></span>

## <a name="using-folders-to-organize-code"></a><span data-ttu-id="37322-106">使用文件夹组织代码</span><span class="sxs-lookup"><span data-stu-id="37322-106">Using folders to organize code</span></span>

<span data-ttu-id="37322-107">如要要在控制台应用中引入新类型，可向该应用添加包含该类型的文件。</span><span class="sxs-lookup"><span data-stu-id="37322-107">If you want to introduce new types into a console app, you can do so by adding files containing the types to the app.</span></span> <span data-ttu-id="37322-108">例如，如果向项目添加包含 `AccountInformation` 和 `MonthlyReportRecords` 类型的文件，则项目文件结构是平面的，且易于导航：</span><span class="sxs-lookup"><span data-stu-id="37322-108">For example if you add files containing `AccountInformation` and `MonthlyReportRecords` types to your project, the project file structure is flat and easy to navigate:</span></span>

```
/MyProject
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="37322-109">但是，仅在项目规模相对较小时，此方法才适用。</span><span class="sxs-lookup"><span data-stu-id="37322-109">However, this only works well when the size of your project is relatively small.</span></span> <span data-ttu-id="37322-110">你能否想象在项目中添加 20 个类型时会发生什么？</span><span class="sxs-lookup"><span data-stu-id="37322-110">Can you imagine what will happen if you add 20 types to the project?</span></span> <span data-ttu-id="37322-111">项目的根目录中会散落许多文件，这样的项目必然会难以导航和维护。</span><span class="sxs-lookup"><span data-stu-id="37322-111">The project definitely wouldn't be easy to navigate and maintain with that many files littering the project's root directory.</span></span>

<span data-ttu-id="37322-112">要组织项目，请创建一个名为 Models 新文件夹，将其用于保存类型文件。</span><span class="sxs-lookup"><span data-stu-id="37322-112">To organize the project, create a new folder and name it *Models* to hold the type files.</span></span> <span data-ttu-id="37322-113">将类型文件放入 Models 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="37322-113">Place the type files into the *Models* folder:</span></span>

```
/MyProject
|__/Models
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="37322-114">按逻辑将文件分组到文件夹的项目易于导航和维护。</span><span class="sxs-lookup"><span data-stu-id="37322-114">Projects that logically group files into folders are easy to navigate and maintain.</span></span> <span data-ttu-id="37322-115">在下一节中，将创建一个更复杂的示例，它包含文件夹和单元测试。</span><span class="sxs-lookup"><span data-stu-id="37322-115">In the next section, you create a more complex sample with folders and unit testing.</span></span>

## <a name="organizing-and-testing-using-the-newtypes-pets-sample"></a><span data-ttu-id="37322-116">使用 NewTypes Pets 示例进行组织和测试</span><span class="sxs-lookup"><span data-stu-id="37322-116">Organizing and testing using the NewTypes Pets Sample</span></span>

### <a name="building-the-sample"></a><span data-ttu-id="37322-117">生成示例</span><span class="sxs-lookup"><span data-stu-id="37322-117">Building the sample</span></span>

<span data-ttu-id="37322-118">对于下列步骤，可使用 [NewTypes Pets 示例](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild)进行相关操作，也可以创建自己的文件与文件夹进行操作。</span><span class="sxs-lookup"><span data-stu-id="37322-118">For the following steps, you can either follow along using the [NewTypes Pets Sample](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild) or create your own files and folders.</span></span> <span data-ttu-id="37322-119">各类型按逻辑组织为文件夹结构，允许日后加入更多类型，测试也按逻辑放置在文件夹中，允许日后加入更多测试。</span><span class="sxs-lookup"><span data-stu-id="37322-119">The types are logically organized into a folder structure that permits the addition of more types later, and tests are also logically placed in folders permitting the addition of more tests later.</span></span>

<span data-ttu-id="37322-120">此示例包含两种类型 `Dog` 和 `Cat`，并使它们实现一个公共接口 `IPet`。</span><span class="sxs-lookup"><span data-stu-id="37322-120">The sample contains two types, `Dog` and `Cat`, and has them implement a common interface, `IPet`.</span></span> <span data-ttu-id="37322-121">对于 `NewTypes` 项目，目标是将与宠物相关的类型组织到 Pets 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="37322-121">For the `NewTypes` project, your goal is to organize the pet-related types into a *Pets* folder.</span></span> <span data-ttu-id="37322-122">如果之后添加了另一组类型（例如 WildAnimals），则将其与 Pets 文件夹一同放在 NewTypes 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="37322-122">If another set of types is added later, *WildAnimals* for example, they're placed in the *NewTypes* folder alongside the *Pets* folder.</span></span> <span data-ttu-id="37322-123">WildAnimals 文件夹可包含不属于宠物的动物类型，如 `Squirrel` 和 `Rabbit` 类型。</span><span class="sxs-lookup"><span data-stu-id="37322-123">The *WildAnimals* folder may contain types for animals that aren't pets, such as `Squirrel` and `Rabbit` types.</span></span> <span data-ttu-id="37322-124">按照这种方式添加类型，不会破坏项目的良好组织。</span><span class="sxs-lookup"><span data-stu-id="37322-124">In this way as types are added, the project remains well organized.</span></span> 

<span data-ttu-id="37322-125">创建以下文件夹结构，并指明文件内容：</span><span class="sxs-lookup"><span data-stu-id="37322-125">Create the following folder structure with file content indicated:</span></span>

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
```

<span data-ttu-id="37322-126">IPet.cs:</span><span class="sxs-lookup"><span data-stu-id="37322-126">*IPet.cs*:</span></span>

[!code-csharp[IPet interface](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/IPet.cs)]

<span data-ttu-id="37322-127">Dog.cs:</span><span class="sxs-lookup"><span data-stu-id="37322-127">*Dog.cs*:</span></span>

[!code-csharp[Dog class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Dog.cs)]

<span data-ttu-id="37322-128">Cat.cs:</span><span class="sxs-lookup"><span data-stu-id="37322-128">*Cat.cs*:</span></span>

[!code-csharp[Cat class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Cat.cs)]

<span data-ttu-id="37322-129">Program.cs:</span><span class="sxs-lookup"><span data-stu-id="37322-129">*Program.cs*:</span></span>

[!code-csharp[Main](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Program.cs)]

<span data-ttu-id="37322-130">NewTypes.csproj:</span><span class="sxs-lookup"><span data-stu-id="37322-130">*NewTypes.csproj*:</span></span>

[!code-xml[NewTypes csproj](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/NewTypes.csproj)]

<span data-ttu-id="37322-131">执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="37322-131">Execute the following commands:</span></span>

```console
dotnet run
```

<span data-ttu-id="37322-132">获得以下输出：</span><span class="sxs-lookup"><span data-stu-id="37322-132">Obtain the following output:</span></span>

```console
Woof!
Meow!
```

<span data-ttu-id="37322-133">可选练习：可通过扩展此项目添加新的宠物类型，如 `Bird`。</span><span class="sxs-lookup"><span data-stu-id="37322-133">Optional exercise: You can add a new pet type, such as a `Bird`, by extending this project.</span></span> <span data-ttu-id="37322-134">使鸟的 `TalkToOwner` 方法向所有者发出 `Tweet!`。</span><span class="sxs-lookup"><span data-stu-id="37322-134">Make the bird's `TalkToOwner` method give a `Tweet!` to the owner.</span></span> <span data-ttu-id="37322-135">再次运行应用。</span><span class="sxs-lookup"><span data-stu-id="37322-135">Run the app again.</span></span> <span data-ttu-id="37322-136">输出将包含 `Tweet!`</span><span class="sxs-lookup"><span data-stu-id="37322-136">The output will include `Tweet!`</span></span>

### <a name="testing-the-sample"></a><span data-ttu-id="37322-137">测试示例</span><span class="sxs-lookup"><span data-stu-id="37322-137">Testing the sample</span></span>

<span data-ttu-id="37322-138">`NewTypes` 项目已准备就绪，与宠物相关的类型均置于一个文件夹中，因此具有良好的组织。</span><span class="sxs-lookup"><span data-stu-id="37322-138">The `NewTypes` project is in place, and you've organized it by keeping the pets-related types in a folder.</span></span> <span data-ttu-id="37322-139">接下来，创建测试项目，并使用 [xUnit](https://xunit.github.io/) 测试框架开始编写测试。</span><span class="sxs-lookup"><span data-stu-id="37322-139">Next, create your test project and start writing tests with the [xUnit](https://xunit.github.io/) test framework.</span></span> <span data-ttu-id="37322-140">使用单元测试，可自动检查宠物类型的行为，确认其正常运行。</span><span class="sxs-lookup"><span data-stu-id="37322-140">Unit testing allows you to automatically check the bevahior of your pet types to confirm that they're operating properly.</span></span>

<span data-ttu-id="37322-141">创建 test 文件夹，并在其中包含一个 NewTypesTests 文件夹。</span><span class="sxs-lookup"><span data-stu-id="37322-141">Create a *test* folder with a *NewTypesTests* folder within it.</span></span> <span data-ttu-id="37322-142">在 NewTypesTests 文件夹的命令提示符中，执行 `dotnet new xunit`。</span><span class="sxs-lookup"><span data-stu-id="37322-142">At a command prompt from the *NewTypesTests* folder, execute `dotnet new xunit`.</span></span> <span data-ttu-id="37322-143">这将生成两个文件：NewTypesTests.csproj 和 UnitTest1.cs。</span><span class="sxs-lookup"><span data-stu-id="37322-143">This produces two files: *NewTypesTests.csproj* and *UnitTest1.cs*.</span></span>

<span data-ttu-id="37322-144">测试项目当前无法测试 `NewTypes` 中的类型，并且需要对 `NewTypes` 项目的项目引用。</span><span class="sxs-lookup"><span data-stu-id="37322-144">The test project cannot currently test the types in `NewTypes` and requires a project reference to the `NewTypes` project.</span></span> <span data-ttu-id="37322-145">要添加项目引用，请使用 [`dotnet add reference`](../tools/dotnet-add-reference.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="37322-145">To add a project reference, use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../../src/NewTypes/NewTypes.csproj
```

<span data-ttu-id="37322-146">还可以选择向 NewTypesTests.csproj 文件添加 `<ItemGroup>` 节点，手动添加项目引用：</span><span class="sxs-lookup"><span data-stu-id="37322-146">You also have the option of manually adding the project reference by adding an `<ItemGroup>` node to the *NewTypesTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="../../src/NewTypes/NewTypes.csproj" />
</ItemGroup>
```

<span data-ttu-id="37322-147">NewTypesTests.csproj:</span><span class="sxs-lookup"><span data-stu-id="37322-147">*NewTypesTests.csproj*:</span></span>

[!code-xml[NewTypesTests csproj](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/NewTypesTests.csproj)]

<span data-ttu-id="37322-148">NewTypesTests.csproj 文件包含下列内容：</span><span class="sxs-lookup"><span data-stu-id="37322-148">The *NewTypesTests.csproj* file contains the following:</span></span>

* <span data-ttu-id="37322-149">对 .NET 测试基础结构 `Microsoft.NET.Test.Sdk` 的包引用</span><span class="sxs-lookup"><span data-stu-id="37322-149">Package reference to `Microsoft.NET.Test.Sdk`, the .NET testing infrastructure</span></span>
* <span data-ttu-id="37322-150">对 xUnit 测试框架 `xunit` 的包引用</span><span class="sxs-lookup"><span data-stu-id="37322-150">Package reference to `xunit`, the xUnit testing framework</span></span>
* <span data-ttu-id="37322-151">对测试运行程序 `xunit.runner.visualstudio` 的包引用</span><span class="sxs-lookup"><span data-stu-id="37322-151">Package reference to `xunit.runner.visualstudio`, the test runner</span></span>
* <span data-ttu-id="37322-152">对要测试的代码 `NewTypes` 的项目引用</span><span class="sxs-lookup"><span data-stu-id="37322-152">Project reference to `NewTypes`, the code to test</span></span>

<span data-ttu-id="37322-153">将 UnitTest1.cs 的名称更改为 PetTests.cs，并将文件中的代码替换为下列内容：</span><span class="sxs-lookup"><span data-stu-id="37322-153">Change the name of *UnitTest1.cs* to *PetTests.cs* and replace the code in the file with the following:</span></span>

```csharp
using System;
using Xunit;
using Pets;

public class PetTests
{
    [Fact]
    public void DogTalkToOwnerReturnsWoof()
    {
        string expected = "Woof!";
        string actual = new Dog().TalkToOwner();
        
        Assert.NotEqual(expected, actual);
    }
    
    [Fact]
    public void CatTalkToOwnerReturnsMeow()
    {
        string expected = "Meow!";
        string actual = new Cat().TalkToOwner();
        
        Assert.NotEqual(expected, actual);
    }
}
```

<span data-ttu-id="37322-154">可选练习：如果先前向所有者添加了生成 `Tweet!` 的 `Bird` 类型，请向 PetTests.cs 文件 `BirdTalkToOwnerReturnsTweet` 添加测试方法，检查对于 `Bird` 类型，`TalkToOwner` 方法是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="37322-154">Optional exercise: If you added a `Bird` type earlier that yields a `Tweet!` to the owner, add a test method to the *PetTests.cs* file, `BirdTalkToOwnerReturnsTweet`, to check that the `TalkToOwner` method works correctly for the `Bird` type.</span></span>

> [!NOTE]
> <span data-ttu-id="37322-155">尽管期望 `expected` 和 `actual` 值相等，但使用 `Assert.NotEqual` 检查的初始断言表明它们并不相等。</span><span class="sxs-lookup"><span data-stu-id="37322-155">Although you expect that the `expected` and `actual` values are equal, the initial assertions with the `Assert.NotEqual` checks specify that they are *not equal*.</span></span> <span data-ttu-id="37322-156">务必使最初创建的测试失败一次，以检查测试的逻辑是否正确。</span><span class="sxs-lookup"><span data-stu-id="37322-156">Always initially create your tests to fail once in order to check the logic of the tests.</span></span> <span data-ttu-id="37322-157">这是测试驱动设计 (TDD) 方法中的一个重要步骤。</span><span class="sxs-lookup"><span data-stu-id="37322-157">This is an important step in test-driven design (TDD) methodology.</span></span> <span data-ttu-id="37322-158">在确认测试失败后，调整断言使测试通过。</span><span class="sxs-lookup"><span data-stu-id="37322-158">After you confirm the tests fail, you adjust the assertions to allow them to pass.</span></span>

<span data-ttu-id="37322-159">下面演示了完整的项目结构：</span><span class="sxs-lookup"><span data-stu-id="37322-159">The following shows the complete project structure:</span></span>

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__NewTypesTests.csproj
```

<span data-ttu-id="37322-160">在 test/NewTypesTests 目录中开始。</span><span class="sxs-lookup"><span data-stu-id="37322-160">Start in the *test/NewTypesTests* directory.</span></span> <span data-ttu-id="37322-161">使用 [`dotnet restore`](../tools/dotnet-restore.md) 命令还原测试项目。</span><span class="sxs-lookup"><span data-stu-id="37322-161">Restore the test project with the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="37322-162">使用 [`dotnet test`](../tools/dotnet-test.md) 命令运行测试。</span><span class="sxs-lookup"><span data-stu-id="37322-162">Run the tests with the [`dotnet test`](../tools/dotnet-test.md) command.</span></span> <span data-ttu-id="37322-163">此命令启动项目文件中指定的测试运行程序。</span><span class="sxs-lookup"><span data-stu-id="37322-163">This command starts the test runner specified in the project file.</span></span>

 [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

 
<span data-ttu-id="37322-164">测试按预期失败，控制台显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="37322-164">As expected, testing fails, and the console displays the following output:</span></span>
 
```
Test run for C:\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp1.1\NewTypesTests.dll(.NETCoreApp,Version=v1.1)
Microsoft (R) Test Execution Command Line Tool Version 15.0.0.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.7271827]   Discovering: NewTypesTests
[xUnit.net 00:00:00.8258687]   Discovered:  NewTypesTests
[xUnit.net 00:00:00.8663545]   Starting:    NewTypesTests
[xUnit.net 00:00:01.0109236]     PetTests.CatTalkToOwnerReturnsMeow [FAIL]
[xUnit.net 00:00:01.0119107]       Assert.NotEqual() Failure
[xUnit.net 00:00:01.0120278]       Expected: Not "Meow!"
[xUnit.net 00:00:01.0120968]       Actual:   "Meow!"
[xUnit.net 00:00:01.0130500]       Stack Trace:
[xUnit.net 00:00:01.0141240]         C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs(22,0): at PetTests.CatTalkToOwnerReturnsMeow()
[xUnit.net 00:00:01.0272364]     PetTests.DogTalkToOwnerReturnsWoof [FAIL]
[xUnit.net 00:00:01.0273649]       Assert.NotEqual() Failure
[xUnit.net 00:00:01.0274166]       Expected: Not "Woof!"
[xUnit.net 00:00:01.0274690]       Actual:   "Woof!"
[xUnit.net 00:00:01.0275264]       Stack Trace:
[xUnit.net 00:00:01.0275960]         C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs(13,0): at PetTests.DogTalkToOwnerReturnsWoof()
[xUnit.net 00:00:01.0294509]   Finished:    NewTypesTests
Failed   PetTests.CatTalkToOwnerReturnsMeow
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Meow!"
Actual:   "Meow!"
Stack Trace:
   at PetTests.CatTalkToOwnerReturnsMeow() in C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 22
Failed   PetTests.DogTalkToOwnerReturnsWoof
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Woof!"
Actual:   "Woof!"
Stack Trace:
   at PetTests.DogTalkToOwnerReturnsWoof() in C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 13

Total tests: 2. Passed: 0. Failed: 2. Skipped: 0.
Test Run Failed.
Test execution time: 2.1371 Seconds
```

<span data-ttu-id="37322-165">将测试的断言从 `Assert.NotEqual` 更改为 `Assert.Equal`：</span><span class="sxs-lookup"><span data-stu-id="37322-165">Change the assertions of your tests from `Assert.NotEqual` to `Assert.Equal`:</span></span>

[!code-csharp[PetTests class](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/PetTests.cs)]

<span data-ttu-id="37322-166">使用 `dotnet test` 命令重新运行测试，并获得以下输出：</span><span class="sxs-lookup"><span data-stu-id="37322-166">Re-run the tests with the `dotnet test` command and obtain the following output:</span></span>

```
Microsoft (R) Test Execution Command Line Tool Version 15.0.0.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:01.3882374]   Discovering: NewTypesTests
[xUnit.net 00:00:01.4767970]   Discovered:  NewTypesTests
[xUnit.net 00:00:01.5157667]   Starting:    NewTypesTests
[xUnit.net 00:00:01.6408870]   Finished:    NewTypesTests

Total tests: 2. Passed: 2. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.6634 Seconds
```

<span data-ttu-id="37322-167">测试通过。</span><span class="sxs-lookup"><span data-stu-id="37322-167">Testing passes.</span></span> <span data-ttu-id="37322-168">在与所有者谈话时，宠物类型的方法返回正确的值。</span><span class="sxs-lookup"><span data-stu-id="37322-168">The pet types' methods return the correct values when talking to the owner.</span></span>

<span data-ttu-id="37322-169">你已了解使用 xUnit 来组织和测试项目的方法。</span><span class="sxs-lookup"><span data-stu-id="37322-169">You've learned techniques for organizing and testing projects using xUnit.</span></span> <span data-ttu-id="37322-170">继续使用这些方法，将它们应用于自己的项目中。</span><span class="sxs-lookup"><span data-stu-id="37322-170">Go forward with these techniques applying them in your own projects.</span></span> <span data-ttu-id="37322-171">祝你编码愉快！</span><span class="sxs-lookup"><span data-stu-id="37322-171">*Happy coding!*</span></span>

