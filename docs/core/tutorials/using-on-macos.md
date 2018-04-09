---
title: 在 macOS 上入门 .NET Core
description: 本文档提供使用 Visual Studio Code 创建 .NET Core 解决方案的步骤和工作流概述。
keywords: .NET, .NET Core, Mac, macOS, Visual Studio Code
author: bleroy
ms.author: mairaw
ms.date: 03/23/2017
ms.topic: get-started-article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8ad82148-dac8-4b31-9128-b0e9610f4d9b
ms.workload:
- dotnetcore
ms.openlocfilehash: 8c045e5625cee53acc4daa3c9fca524bc953b5a1
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="getting-started-with-net-core-on-macos"></a><span data-ttu-id="f731e-104">在 macOS 上入门 .NET Core</span><span class="sxs-lookup"><span data-stu-id="f731e-104">Getting started with .NET Core on macOS</span></span>

<span data-ttu-id="f731e-105">本文档提供为 macOS 创建 .NET Core 解决方案的步骤和工作流概述。</span><span class="sxs-lookup"><span data-stu-id="f731e-105">This document provides the steps and workflow to create a .NET Core solution for macOS.</span></span> <span data-ttu-id="f731e-106">了解到如何通过 [NuGet](https://www.nuget.org/) 创建项目、单元测试、使用调试工具和合并第三方库。</span><span class="sxs-lookup"><span data-stu-id="f731e-106">Learn how to create projects, unit tests, use the debugging tools, and incorporate third-party libraries via [NuGet](https://www.nuget.org/).</span></span>

> [!NOTE]
> <span data-ttu-id="f731e-107">本文在 macOS 上使用 [Visual Studio Code](http://code.visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="f731e-107">This article uses [Visual Studio Code](http://code.visualstudio.com) on macOS.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f731e-108">系统必备</span><span class="sxs-lookup"><span data-stu-id="f731e-108">Prerequisites</span></span>

<span data-ttu-id="f731e-109">获取 [.NET Core SDK](https://www.microsoft.com/net/core)。</span><span class="sxs-lookup"><span data-stu-id="f731e-109">Install the [.NET Core SDK](https://www.microsoft.com/net/core).</span></span> <span data-ttu-id="f731e-110">.NET Core SDK 包括最新版本的 .NET Core 框架和运行时。</span><span class="sxs-lookup"><span data-stu-id="f731e-110">The .NET Core SDK includes the latest release of the .NET Core framework and runtime.</span></span>

<span data-ttu-id="f731e-111">安装 [Visual Studio Code](http://code.visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="f731e-111">Install [Visual Studio Code](http://code.visualstudio.com).</span></span> <span data-ttu-id="f731e-112">在本文中，还将安装可提升 .NET Core 开发体验的 Visual Studio Code 扩展。</span><span class="sxs-lookup"><span data-stu-id="f731e-112">During the course of this article, you also install Visual Studio Code extensions that improve the .NET Core development experience.</span></span>

<span data-ttu-id="f731e-113">打开 Visual Studio Code，并按 <kbd>F1</kbd> 打开 Visual Studio Code 面板，从而安装 Visual Studio Code C# 扩展。</span><span class="sxs-lookup"><span data-stu-id="f731e-113">Install the Visual Studio Code C# extension by opening Visual Studio Code and pressing <kbd>F1</kbd> to open the Visual Studio Code palette.</span></span> <span data-ttu-id="f731e-114">键入 ext install ，查看扩展列表。</span><span class="sxs-lookup"><span data-stu-id="f731e-114">Type **ext install** to see the list of extensions.</span></span> <span data-ttu-id="f731e-115">选择 C# 扩展。</span><span class="sxs-lookup"><span data-stu-id="f731e-115">Select the C# extension.</span></span> <span data-ttu-id="f731e-116">重启 Visual Studio Code 以激活扩展。</span><span class="sxs-lookup"><span data-stu-id="f731e-116">Restart Visual Studio Code to activate the extension.</span></span> <span data-ttu-id="f731e-117">有关详细信息，请参阅 [Visual Basic Code C# 扩展文档](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)。</span><span class="sxs-lookup"><span data-stu-id="f731e-117">For more information, see the [Visual Studio Code C# Extension documentation](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="getting-started"></a><span data-ttu-id="f731e-118">入门</span><span class="sxs-lookup"><span data-stu-id="f731e-118">Getting started</span></span>

<span data-ttu-id="f731e-119">在本教程中，将创建三个项目：库项目、对该库项目的测试和使用该库的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="f731e-119">In this tutorial, you create three projects: a library project, tests for that library project, and a console application that makes use of the library.</span></span> <span data-ttu-id="f731e-120">对于此主题，可以在 GitHub 的 dotnet/docs 存储库中[查看或下载源](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/golden)。</span><span class="sxs-lookup"><span data-stu-id="f731e-120">You can [view or download the source](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/golden) for this topic at the dotnet/docs repository on GitHub.</span></span> <span data-ttu-id="f731e-121">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="f731e-121">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="f731e-122">启动 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="f731e-122">Start Visual Studio Code.</span></span> <span data-ttu-id="f731e-123">按 <kbd>Ctrl</kbd>+<kbd>\`</kbd>（反引号）或在菜单中依次选择“视图”>“集成终端”，在 Visual Studio Code 中打开嵌入式终端。</span><span class="sxs-lookup"><span data-stu-id="f731e-123">Press <kbd>Ctrl</kbd>+<kbd>\`</kbd> (the backquote or backtick character) or select **View > Integrated Terminal** from the menu to open an embedded terminal in Visual Studio Code.</span></span> <span data-ttu-id="f731e-124">若要在 Visual Studio Code 外部执行操作，仍可以使用资源管理器的“通过命令提示符打开”（在 Mac 或 Linux 上，为“在终端中打开”）命令打开外部 shell。</span><span class="sxs-lookup"><span data-stu-id="f731e-124">You can still open an external shell with the Explorer **Open in Command Prompt** command (**Open in Terminal** on Mac or Linux) if you prefer to work outside of Visual Studio Code.</span></span>

<span data-ttu-id="f731e-125">首先创建一个解决方案文件，它将用作一个或多个 .NET Core 项目的容器。</span><span class="sxs-lookup"><span data-stu-id="f731e-125">Begin by creating a solution file, which serves as a container for one or more .NET Core projects.</span></span> <span data-ttu-id="f731e-126">在终端中，创建 golden 文件夹并将其打开。</span><span class="sxs-lookup"><span data-stu-id="f731e-126">In the terminal, create a *golden* folder and open the folder.</span></span> <span data-ttu-id="f731e-127">此文件夹是解决方案的根目录。</span><span class="sxs-lookup"><span data-stu-id="f731e-127">This folder is the root of your solution.</span></span> <span data-ttu-id="f731e-128">运行 [`dotnet new`](../tools/dotnet-new.md) 命令，创建新的解决方案 golden.sln：</span><span class="sxs-lookup"><span data-stu-id="f731e-128">Run the [`dotnet new`](../tools/dotnet-new.md) command to create a new solution, *golden.sln*:</span></span>

```console
dotnet new sln
```

<span data-ttu-id="f731e-129">在 golden 文件夹中，执行下列命令来创建库项目，它将在库文件夹中生成 library.csproj 和 Class1.cs 这两个文件：</span><span class="sxs-lookup"><span data-stu-id="f731e-129">From the *golden* folder, execute the following command to create a library project, which produces two files,*library.csproj* and *Class1.cs*, in the *library* folder:</span></span>

```console
dotnet new classlib -o library
```

<span data-ttu-id="f731e-130">执行 [`dotnet sln`](../tools/dotnet-sln.md) 命令，将新创建的 library.csproj 添加到解决方案：</span><span class="sxs-lookup"><span data-stu-id="f731e-130">Execute the [`dotnet sln`](../tools/dotnet-sln.md) command to add the newly created *library.csproj* project to the solution:</span></span>

```console
dotnet sln add library/library.csproj
```

<span data-ttu-id="f731e-131">*library.csproj* 文件包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="f731e-131">The *library.csproj* file contains the following information:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard1.4</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="f731e-132">库方法以 JSON 格式串行化和反序列化对象。</span><span class="sxs-lookup"><span data-stu-id="f731e-132">Our library methods serialize and deserialize objects in JSON format.</span></span> <span data-ttu-id="f731e-133">若要支持 JSON 序列化和反序列化，请添加对 `Newtonsoft.Json` NuGet 包的引用。</span><span class="sxs-lookup"><span data-stu-id="f731e-133">To support JSON serialization and deserialization, add a reference to the `Newtonsoft.Json` NuGet package.</span></span> <span data-ttu-id="f731e-134">`dotnet add` 命令向项目添加新项。</span><span class="sxs-lookup"><span data-stu-id="f731e-134">The `dotnet add` command adds new items to a project.</span></span> <span data-ttu-id="f731e-135">若要添加对 NuGet 包的引用，请使用 [`dotnet add package`](../tools/dotnet-add-package.md) 命令并指定包的名称：</span><span class="sxs-lookup"><span data-stu-id="f731e-135">To add a reference to a NuGet package, use the [`dotnet add package`](../tools/dotnet-add-package.md) command and specify the name of the package:</span></span>

```console
dotnet add library package Newtonsoft.Json
```

<span data-ttu-id="f731e-136">这会将 `Newtonsoft.Json` 及其依赖项添加到库项目。</span><span class="sxs-lookup"><span data-stu-id="f731e-136">This adds `Newtonsoft.Json` and its dependencies to the library project.</span></span> <span data-ttu-id="f731e-137">或者，可以手动编辑 library.csproj 文件，并添加以下节点：</span><span class="sxs-lookup"><span data-stu-id="f731e-137">Alternatively, manually edit the *library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="10.0.1" />
</ItemGroup>
```

<span data-ttu-id="f731e-138">执行 [`dotnet restore`](../tools/dotnet-restore.md)（[请参阅注释](#dotnet-restore-note)），这将还原依赖项，并在库中创建 obj 文件夹，该文件夹中包含三个文件，其中一个是 project.assets.json 文件：</span><span class="sxs-lookup"><span data-stu-id="f731e-138">Execute [`dotnet restore`](../tools/dotnet-restore.md), ([see note](#dotnet-restore-note)) which restores dependencies and creates an *obj* folder inside *library* with three files in it, including a *project.assets.json* file:</span></span>

```console
dotnet restore
```

<span data-ttu-id="f731e-139">在库文件夹中，将文件 Class1.cs 重命名为 Thing.cs。</span><span class="sxs-lookup"><span data-stu-id="f731e-139">In the *library* folder, rename the file *Class1.cs* to *Thing.cs*.</span></span> <span data-ttu-id="f731e-140">将代码替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="f731e-140">Replace the code with the following:</span></span>

```csharp
using static Newtonsoft.Json.JsonConvert;

namespace Library
{
    public class Thing
    {
        public int Get(int left, int right) =>
            DeserializeObject<int>($"{left + right}");
    }
}
```

<span data-ttu-id="f731e-141">`Thing` 类包含一个公共方法 `Get`，它返回两个数字的总和，实现方法是将总和转换为字符串，然后反序列化为一个整数。</span><span class="sxs-lookup"><span data-stu-id="f731e-141">The `Thing` class contains one public method, `Get`, which returns the sum of two numbers but does so by converting the sum into a string and then deserializing it into an integer.</span></span> <span data-ttu-id="f731e-142">这将使用大量现代 C# 功能，如[`using static` 指令](../../csharp/language-reference/keywords/using-static.md)、[expression-bodied 成员](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members)和[字符串内插](../../csharp/language-reference/tokens/interpolated.md)。</span><span class="sxs-lookup"><span data-stu-id="f731e-142">This makes use of a number of modern C# features, such as [`using static` directives](../../csharp/language-reference/keywords/using-static.md), [expression-bodied members](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members), and [string interpolation](../../csharp/language-reference/tokens/interpolated.md).</span></span>

<span data-ttu-id="f731e-143">使用 [`dotnet build`](../tools/dotnet-build.md) 命令生成库。</span><span class="sxs-lookup"><span data-stu-id="f731e-143">Build the library with the [`dotnet build`](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="f731e-144">这将在 golden/library/bin/Debug/netstandard1.4 下生成一个 library.dll 文件：</span><span class="sxs-lookup"><span data-stu-id="f731e-144">This produces a *library.dll* file under *golden/library/bin/Debug/netstandard1.4*:</span></span>

```console
dotnet build
```

## <a name="create-the-test-project"></a><span data-ttu-id="f731e-145">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="f731e-145">Create the test project</span></span>

<span data-ttu-id="f731e-146">生成针对库的测试项目。</span><span class="sxs-lookup"><span data-stu-id="f731e-146">Build a test project for the library.</span></span> <span data-ttu-id="f731e-147">在 golden 文件夹中，创建一个新测试项目：</span><span class="sxs-lookup"><span data-stu-id="f731e-147">From the *golden* folder, create a new test project:</span></span>

```console
dotnet new xunit -o test-library
```

<span data-ttu-id="f731e-148">向解决方案添加测试项目：</span><span class="sxs-lookup"><span data-stu-id="f731e-148">Add the test project to the solution:</span></span>

```console
dotnet sln add test-library/test-library.csproj
```

<span data-ttu-id="f731e-149">在上一节创建的库中添加项目引用，这样编译器就可以查找并使用该库项目。</span><span class="sxs-lookup"><span data-stu-id="f731e-149">Add a project reference the library you created in the previous section so that the compiler can find and use the library project.</span></span> <span data-ttu-id="f731e-150">使用 [`dotnet add reference`](../tools/dotnet-add-reference.md) 命令：</span><span class="sxs-lookup"><span data-stu-id="f731e-150">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```console
dotnet add test-library/test-library.csproj reference library/library.csproj
```

<span data-ttu-id="f731e-151">或者，可以手动编辑 test-library.csproj 文件，并添加以下节点：</span><span class="sxs-lookup"><span data-stu-id="f731e-151">Alternatively, manually edit the *test-library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

<span data-ttu-id="f731e-152">现已正确配置依赖项，可以开始创建库的测试项目。</span><span class="sxs-lookup"><span data-stu-id="f731e-152">Now that the dependencies have been properly configured, create the tests for your library.</span></span> <span data-ttu-id="f731e-153">打开 *UnitTest1.cs*，用以下代码替代其内容：</span><span class="sxs-lookup"><span data-stu-id="f731e-153">Open *UnitTest1.cs* and replace its contents with the following code:</span></span>

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing() {
            Assert.NotEqual(42, new Thing().Get(19, 23));
        }
    }
}
```

<span data-ttu-id="f731e-154">请注意，在首次创建单元测试 (`Assert.NotEqual`) 时，已断言值 42 不等于 19+23（或 42），因此测试将失败。</span><span class="sxs-lookup"><span data-stu-id="f731e-154">Note that you assert the value 42 is not equal to 19+23 (or 42) when you first create the unit test (`Assert.NotEqual`), which will fail.</span></span> <span data-ttu-id="f731e-155">生成单元测试的一个重要步骤是：使创建的测试最初失败一次，以便确认其逻辑正确无误。</span><span class="sxs-lookup"><span data-stu-id="f731e-155">An important step in building unit tests is to create the test to fail once first to confirm its logic.</span></span>

<span data-ttu-id="f731e-156">在 golden 文件夹中，执行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f731e-156">From the *golden* folder, execute the following commands:</span></span>

```console
dotnet restore 
dotnet test test-library/test-library.csproj
```

<span data-ttu-id="f731e-157">这些命令将以递归形式查找所有项目，以还原依赖项、生成依赖性，并激活 xUnit 测试运行程序以运行测试。</span><span class="sxs-lookup"><span data-stu-id="f731e-157">These commands will recursively find all projects to restore dependencies, build them, and activate the xUnit test runner to run the tests.</span></span> <span data-ttu-id="f731e-158">该测试像预期那样失败。</span><span class="sxs-lookup"><span data-stu-id="f731e-158">The single test fails, as you expect.</span></span>

<span data-ttu-id="f731e-159">编辑 UnitTest1.cs 文件，将断言从 `Assert.NotEqual` 更改为 `Assert.Equal`。</span><span class="sxs-lookup"><span data-stu-id="f731e-159">Edit the *UnitTest1.cs* file and change the assertion from `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="f731e-160">在 goldden  文件夹中执行下列命令，重新运行测试，此次测试通过：</span><span class="sxs-lookup"><span data-stu-id="f731e-160">Execute the following command from the *golden* folder to re-run the test, which passes this time:</span></span>

```console
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a><span data-ttu-id="f731e-161">创建控制台应用</span><span class="sxs-lookup"><span data-stu-id="f731e-161">Create the console app</span></span>

<span data-ttu-id="f731e-162">通过以下步骤创建的控制台应用依赖于之前创建的库项目，并在运行时调用其库方法。</span><span class="sxs-lookup"><span data-stu-id="f731e-162">The console app you create over the following steps takes a dependency on the library project you created earlier and calls its library method when it runs.</span></span> <span data-ttu-id="f731e-163">使用此开发模式，可了解如何创建多个项目的可重用库。</span><span class="sxs-lookup"><span data-stu-id="f731e-163">Using this pattern of development, you see how to create reusable libraries for multiple projects.</span></span>

<span data-ttu-id="f731e-164">在 golden 文件夹中创建新的控制台应用程序：</span><span class="sxs-lookup"><span data-stu-id="f731e-164">Create a new console application from the *golden* folder:</span></span>

```console
dotnet new console -o app
```

<span data-ttu-id="f731e-165">向解决方案添加控制台应用项目：</span><span class="sxs-lookup"><span data-stu-id="f731e-165">Add the console app project to the solution:</span></span>

```console
dotnet sln add app/app.csproj
```

<span data-ttu-id="f731e-166">运行 `dotnet add reference` 命令，创建库的依赖项：</span><span class="sxs-lookup"><span data-stu-id="f731e-166">Create the dependency on the library by running the `dotnet add reference` command:</span></span>

```console
dotnet add app/app.csproj reference library/library.csproj
```

<span data-ttu-id="f731e-167">运行 `dotnet restore`（[请参阅注释](#dotnet-restore-note)），在解决方案中还原三个项目的依赖项。</span><span class="sxs-lookup"><span data-stu-id="f731e-167">Run `dotnet restore` ([see note](#dotnet-restore-note)) to restore the dependencies of the three projects in the solution.</span></span> <span data-ttu-id="f731e-168">打开 program.cs，并使用下列行替换 `Main` 方法中的内容：</span><span class="sxs-lookup"><span data-stu-id="f731e-168">Open *Program.cs* and replace the contents of the `Main` method with the following line:</span></span>

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

<span data-ttu-id="f731e-169">在 Program.cs 文件顶部添加两个 `using` 指令：</span><span class="sxs-lookup"><span data-stu-id="f731e-169">Add two `using` directives to the top of the *Program.cs* file:</span></span>

```csharp
using static System.Console;
using Library;
```

<span data-ttu-id="f731e-170">执行下列 `dotnet run` 命令，运行可执行文件，其中，`dotnet run` 后的 `-p` 选项用于指定主应用程序的项目。</span><span class="sxs-lookup"><span data-stu-id="f731e-170">Execute the following `dotnet run` command to run the executable, where the `-p` option to `dotnet run` specifies the project for the main application.</span></span> <span data-ttu-id="f731e-171">应用会生成字符串“The answer is 42”。</span><span class="sxs-lookup"><span data-stu-id="f731e-171">The app produces the string "The answer is 42".</span></span>

```console
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a><span data-ttu-id="f731e-172">调试应用程序</span><span class="sxs-lookup"><span data-stu-id="f731e-172">Debug the application</span></span>

<span data-ttu-id="f731e-173">在 `Main` 方法中的 `WriteLine` 语句处设置一个断点。</span><span class="sxs-lookup"><span data-stu-id="f731e-173">Set a breakpoint at the `WriteLine` statement in the `Main` method.</span></span> <span data-ttu-id="f731e-174">要实现此操作，可在光标位于 `WriteLine` 行之上时按 <kbd>F9</kbd> 键，也可在想要设置断点的行的左侧边缘中单击鼠标。</span><span class="sxs-lookup"><span data-stu-id="f731e-174">Do this by either pressing the <kbd>F9</kbd> key when the cursor is over the `WriteLine` line or by clicking the mouse in the left margin on the line where you want to set the breakpoint.</span></span> <span data-ttu-id="f731e-175">代码行旁边的边缘中将出现一个红色圆圈。</span><span class="sxs-lookup"><span data-stu-id="f731e-175">A red circle will appear in the margin next to the line of code.</span></span> <span data-ttu-id="f731e-176">到达断点时，将在执行断点行前停止执行代码。</span><span class="sxs-lookup"><span data-stu-id="f731e-176">When the breakpoint is reached, code execution will stop *before* the breakpoint line is executed.</span></span>

<span data-ttu-id="f731e-177">若要打开“调试器”选项卡，请在 Visual Studio Code 工具栏中选择“调试”图标，再从菜单栏中依次选择“视图”>“调试”，或使用键盘快捷方式 <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>：</span><span class="sxs-lookup"><span data-stu-id="f731e-177">Open the debugger tab by selecting the Debug icon in the Visual Studio Code toolbar, selecting **View > Debug** from the menu bar, or using the keyboard shortcut <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>:</span></span>

![Visual Studio Code 调试程序](./media/using-on-macos/vscodedebugger.png)

<span data-ttu-id="f731e-179">按“开始”按钮，在调试器下启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="f731e-179">Press the Play button to start the application under the debugger.</span></span> <span data-ttu-id="f731e-180">应用开始执行，运行到断点处停止。</span><span class="sxs-lookup"><span data-stu-id="f731e-180">The app begins execution and runs to the breakpoint, where it stops.</span></span> <span data-ttu-id="f731e-181">单步执行 `Get` 方法，确保已传入正确的参数。</span><span class="sxs-lookup"><span data-stu-id="f731e-181">Step into the `Get` method and make sure that you have passed in the correct arguments.</span></span> <span data-ttu-id="f731e-182">确认答案是 42。</span><span class="sxs-lookup"><span data-stu-id="f731e-182">Confirm that the answer is 42.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]